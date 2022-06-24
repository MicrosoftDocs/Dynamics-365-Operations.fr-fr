---
title: Spécifier des emplacements de stockage personnalisé pour les documents générés
description: Cet article explique comment étendre la liste des emplacements de stockage pour les documents qui sont générés aux formats des états électroniques.
author: NickSelin
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 103a7e51fc6042e19b1db3b3d6b00436df15fd89
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898854"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a>Spécifier des emplacements de stockage personnalisé pour les documents générés

[!include[banner](../includes/banner.md)]

L’API de la structure des états électroniques permet d’étendre la liste des emplacements de stockage pour les documents générés aux formats des états électroniques. Cet article explique comment ajouter un emplacement de stockage personnalisé pour les documents générés en déléguant la tâche de création de destinations ER à la fabrique de destination par défaut, puis en implémentant une classe personnalisée ayant sa propre logique de destination.

## <a name="prerequisites"></a>Conditions préalables

Déployez une topologie prenant en charge l’élaboration continue. Pour plus d’informations, voir [Déployer des topologies prenant en charge l’élaboration continue et l’automatisation des tests](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation). Vous devez également avoir accès à cette topologie pour l’un des rôles suivants :

- Développeur d’états électroniques
- Consultant fonctionnel des états électroniques
- Administrateur système

Vous devez également avoir accès à l’environnement de développement pour cette topologie.

Toutes les tâches de cet article peuvent être effectuées dans l’entreprise **USMF**.

## <a name="import-the-fixed-asset-roll-forward-er-format"></a>Importer le format ER de reprise des immobilisations

Pour générer les documents pour lesquels vous prévoyez d’ajouter un emplacement de stockage personnalisé, [importez](er-download-configurations-global-repo.md) la configuration du format ER **Reprise des immobilisations** dans la topologie actuelle.

![Page du référentiel de configuration.](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a>Exécuter l’état de récupération d’immobilisation

1. Aller à **Immobilisations** \> **Demandes de renseignements et rapports** \> **Rapports de transaction** \> **Reprise des immobilisations**.
2. Dans le champ **Date de début**, entrez **1/1/2017** (1er janvier 2017).
3. Dans le champ **Date de fin**, entrez **1/31/2017** (1er janvier 2017).
4. Dans le champ **Devise**, sélectionnez **Devise comptable**.
5. Dans le champ **Mappage de format**, sélectionnez **Reprise des immobilisations**.
6. Cliquez sur **OK**.

![Boîte de dialogue de runtime pour l’état de reprise des immobilisations.](./media/er-custom-storage-generated-files-runtime-dialog.png)

Dans Microsoft Excel, examinez le document sortant généré et disponible pour téléchargement. Ce comportement est le [comportement par défaut](electronic-reporting-destinations.md#default-behavior) pour un format ER pour lequel aucune [destination](electronic-reporting-destinations.md) n’est configurée, et qui s’exécute en mode interactif.

## <a name="review-the-source-code"></a>Examiner le code source

Examinez le code de la méthode `generateReportByGER()` de classe `AssetRollForwardService`. Notez que la méthode `Run()` est utilisée pour appeler la structure de gestion des états électroniques et générer l’état **Reprise des immobilisations**.

```xpp
class AssetRollForwardService extends SysOperationServiceBase
{
    public const str ERFormatModelName = 'Fixed assets';
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'AssetRollForward';

    /// <summary>
    /// Generates report by general electronic reporting
    /// </summary>
    /// <param name = "_contract">The Asset Period Statement contract</param>
    public void generateReportByGER(AssetRollForwardContract _contract)
    {
        ERFormatMappingId   formatMappingId;
        AssetRollForwardDP  dataProvider;
        AssetRollForwardTmp assetRollForwardTmp;
        Query               query;

        query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
        dataProvider = AssetRollForwardDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

        if (assetRollForwardTmp)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                // Call ER to generate the report.
                ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName)
                    .withParameter(parameters)
                    .withFileDestination(_contract.getFileDestination())
                    .run();
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

## <a name="modify-the-source-code"></a>Modifier le code source

1. Dans votre projet Visual Studio, ajoutez une nouvelle classe (`AssetRollForwardDestination` dans cet exemple) et écrivez du code pour implémenter votre destination personnalisée pour les états **Reprise des immobilisations** générés.

    - La méthode `new()` est conçue pour obtenir l’objet de destination ER d’origine et le paramètre logique de l’application qui spécifie l’emplacement personnalisé où les rapports générés doivent être stockés. Dans cet exemple, l’emplacement personnalisé est le nom d’un dossier du système de fichiers local du serveur qui exécute le service Application Object Server (AOS).
    - La méthode `saveFile()` est conçue pour enregistrer un document généré dans un dossier du système de fichiers local du serveur qui exécute le service AOS.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;

    /// <summary>
    /// Destination class for <c>AssetRollForwardDestinationFactory</c> that stores a generated report.
    /// </summary>
    public class AssetRollForwardDestination implements ERIFileDestination
    {
        private ERIFileDestination originDestination;
        private str TargetFolder;

        /// <summary>
        /// Creates a stream for new file.
        /// </summary>
        /// <param name = "_fileName">Name of a new file.</param>
        /// <returns>Stream for new file.</returns>
        public System.IO.Stream newFileStream(System.String _fileName)
        {
            return originDestination.newFileStream(_fileName);
        }

        /// <summary>
        /// Saves file in destination.
        /// </summary>
        /// <param name = "_stream">A stream to save.</param>
        /// <param name = "_fileName">A file name.</param>
        /// <returns>Saved stream.</returns>
        public System.IO.Stream saveFile(System.IO.Stream _stream, System.String _fileName)
        {
            _stream.Seek(0, System.IO.SeekOrigin::Begin);
            using (var localStream = System.IO.File::OpenWrite(TargetFolder + _fileName))
            {
                _stream.CopyTo(localStream);
            }
            return _stream;
        }

        /// <summary>
        /// Constructs destination for fixed asset roll forward report.
        /// </summary>
        /// <param name = "_originDestination">The original destination.</param>
        /// <param name = "_TargetFoder">The folder to store a report that's being created.</param>
        /// <returns>The fixed asset roll forward destination.</returns>
        public static AssetRollForwardDestination construct(ERIFileDestination _originDestination, str _TargetFoder)
        {
            return new AssetRollForwardDestination(_originDestination, _TargetFoder);
        }

        protected void new(ERIFileDestination _originDestination, str _TargetFoder)
        {
            originDestination = _originDestination;
            TargetFolder = _TargetFoder;
        }
    }
    ```

2. Dans votre projet Visual Studio, ajoutez une nouvelle classe (`AssetRollForwardDestinationFactory` dans cet exemple), et écrivez du code pour configurer une fabrique de destination personnalisée qui délègue la création d’une destination à la fabrique de destination par défaut, et pour encapsuler une destination de fichier avec votre propre destination.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    using Microsoft.Dynamics365.LocalizationFramework.Format.FileGeneration;

    /// <summary>
    /// Destination factory for using <c>AssetRollForwardDestinationFactory</c>.
    /// </summary>
    public class AssetRollForwardDestinationFactory implements ERIFileDestinationFactory, ERIFileDestinationFactoryPostProcessor
    {
        private ERIFileDestinationFactory originDestinationFactory;
        private str TargetFolder;

        /// <summary>
        /// Creates file destination for print management.
        /// </summary>
        /// <param name = "_fileDestination">A default file destination.</param>
        /// <param name = "_identification">An identification strategy.</param>
        /// <param name = "_rootContext">A root context.</param>
        /// <param name = "_root">A root element.</param>
        /// <returns>A file destination.</returns>
        public ERIDataDrivenFileDestination createPrintMgmtDestination(
            ERIFileDestination _fileDestination,
            ERIObjectIdentificationStrategy _identification,
            ERTextFormatDataContext _rootContext,
            ERTextFormatIFileComponent _root)
        {
            ERIDataDrivenFileDestination dataDrivenDestination = originDestinationFactory.createPrintMgmtDestination(
                _fileDestination,
                _identification,
                _rootContext,
                _root);

            IFileDestinationHost fileDestinationHost = dataDrivenDestination as IFileDestinationHost;
            if (fileDestinationHost)
            {
                fileDestinationHost.FileDestination = AssetRollForwardDestination::construct(
                    fileDestinationHost.get_FileDestination(),
                    TargetFolder);
            }

            return dataDrivenDestination;
        }

        /// <summary>
        /// Constructs the fixed asset roll forward destination factory.
        /// </summary>
        /// <param name = "_originDestinationFactory">The original destination.</param>
        /// <param name = "_TargetFolder">The string containing a folder name that corresponds to the report, that's being created.</param>
        /// <returns>The destination factory for the fixed asset roll forward report.</returns>
        public static AssetRollForwardDestinationFactory construct(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            AssetRollForwardDestinationFactory destinationFactory = new AssetRollForwardDestinationFactory(_originDestinationFactory, _TargetFolder);

            ERIFileDestinationFactoryPostProcessorsHost factoryPostProcessing = ERCast::asObject(destinationFactory.originDestinationFactory) as ERIFileDestinationFactoryPostProcessorsHost;

            if (factoryPostProcessing)
            {
                factoryPostProcessing.addDestinationPostProcessor(destinationFactory);
            }
            return destinationFactory;
        }

        public ERIFileDestination processDestinationAfterCreation(ERIFileDestination _sourceDestination)
        {
            return AssetRollForwardDestination::construct(_sourceDestination, TargetFolder);
        }

        protected void new(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            originDestinationFactory = _originDestinationFactory;
            TargetFolder = _TargetFolder;
        }
    }
    ```

3. Modifier la classe `AssetRollForwardService` existante et écrivez du code pour configurer une fabrique de destination personnalisée pour le générateur de rapports. Notez que lorsqu’une fabrique de destination personnalisée est construite, le paramètre piloté par l’application qui spécifie un dossier cible est transmis. De cette manière, ce dossier cible est utilisé pour stocker les fichiers générés.

    > [!NOTE] 
    > Assurez-vous que le dossier spécifié (**c:\\0** dans cet exemple) est présent dans le système de fichiers local du serveur qui exécute le service AOS. Sinon, une exception [DirectoryNotFoundException](/dotnet/api/system.io.directorynotfoundexception) sera levée lors de l’exécution.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    /// <summary>
    /// The electronic reporting service class for fixed asset roll forward report
    /// </summary>
    class AssetRollForwardService extends SysOperationServiceBase
    {
        public const str ERFormatModelName = 'Fixed assets';
        public const str ERModelDataSourceName = 'model';
        public const str DefaultExportedFileName = 'AssetRollForward';

        /// <summary>
        /// Generates report by general electronic reporting
        /// </summary>
        /// <param name = "_contract">The Asset Period Statement contract</param>
        public void generateReportByGER(AssetRollForwardContract _contract)
        {
            ERFormatMappingId   formatMappingId;
            AssetRollForwardDP  dataProvider;
            AssetRollForwardTmp assetRollForwardTmp;
            Query               query;

            query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
            dataProvider = AssetRollForwardDP::construct();
            formatMappingId = _contract.parmFormatMapping();
            assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

            if (assetRollForwardTmp)
            {
                try
                {
                    ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                        .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                        .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                    // Call ER to generate the report.
                    ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());

                    ERIFileDestinationFactoryHost factoryHost = ERCast::asObject(formatMappingRun) as ERIFileDestinationFactoryHost;
                    if (factoryHost)
                    {
                        ERIFileDestinationFactory fileDestinationFactory = factoryHost.getFileDestinationFactory();
                        factoryHost.setFileDestinationFactory(AssetRollForwardDestinationFactory::construct(fileDestinationFactory, @'c:\0\'));
                        formatMappingRun.run();
                    }
                }
                catch
                {
                    // An error occurred while exporting data.
                    error("@SYP4861341");
                }
            }
            else
            {
                // There is no data available.
                info("@SYS300117");
            }
        }
    }
    ```

4. Recréez votre projet.

## <a name="re-run-the-fixed-asset-roll-forward-report"></a>Ré-exécutez l’état de récupération d’immobilisation

1. Aller à **Immobilisations** \> **Demandes de renseignements et rapports** \> **Rapports de transaction** \> **Reprise des immobilisations**.
2. Dans le champ **Date de début**, entrez **1/1/2017**.
3. Dans le champ **Date de fin**, entrez **1/31/2017**.
4. Dans le champ **Devise**, sélectionnez **Devise comptable**.
5. Dans le champ **Mappage de format**, sélectionnez **Reprise des immobilisations**.
6. Cliquez sur **OK**.
7. Explorez le dossier **C:\\0** local pour trouver le fichier généré.

> [!NOTE]
> Parce que l’objet `originDestination` n’est pas utilisé dans l’objet `AssetRollForwardDestination` dans cet exemple, les configurations pour les [destinations](electronic-reporting-destinations.md) du format ER sera ignoré lors de l’exécution.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)
- [Page d’accueil Extensibilité](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]