---
title: Spécifier des emplacements de stockage personnalisé pour les documents générés
description: Cette rubrique explique comment étendre la liste des emplacements de stockage pour les documents qui sont générés aux formats des états électroniques.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 362ac7f10cc61e26be89dfbae0e84745d42588a3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680756"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a><span data-ttu-id="2563f-103">Spécifier des emplacements de stockage personnalisé pour les documents générés</span><span class="sxs-lookup"><span data-stu-id="2563f-103">Specify custom storage locations for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2563f-104">L’API de la structure des états électroniques permet d’étendre la liste des emplacements de stockage pour les documents générés aux formats des états électroniques.</span><span class="sxs-lookup"><span data-stu-id="2563f-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="2563f-105">Cette rubrique explique comment ajouter un emplacement de stockage personnalisé pour les documents générés en déléguant la tâche de création de destinations ER à la fabrique de destination par défaut, puis en implémentant une classe personnalisée ayant sa propre logique de destination.</span><span class="sxs-lookup"><span data-stu-id="2563f-105">This topic explains how to add a custom storage location for generated documents by delegating the task of creating ER destinations to the default destination factory and then implementing a custom class that has its own destination logic.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2563f-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="2563f-106">Prerequisites</span></span>

<span data-ttu-id="2563f-107">Déployez une topologie prenant en charge l’élaboration continue.</span><span class="sxs-lookup"><span data-stu-id="2563f-107">Deploy a topology that supports continuous build.</span></span> <span data-ttu-id="2563f-108">Pour plus d’informations, voir [Déployer des topologies prenant en charge l’élaboration continue et l’automatisation des tests](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span><span class="sxs-lookup"><span data-stu-id="2563f-108">For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span></span> <span data-ttu-id="2563f-109">Vous devez également avoir accès à cette topologie pour l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="2563f-109">You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="2563f-110">Développeur d’états électroniques</span><span class="sxs-lookup"><span data-stu-id="2563f-110">Electronic reporting developer</span></span>
- <span data-ttu-id="2563f-111">Consultant fonctionnel des états électroniques</span><span class="sxs-lookup"><span data-stu-id="2563f-111">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="2563f-112">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="2563f-112">System administrator</span></span>

<span data-ttu-id="2563f-113">Vous devez également avoir accès à l’environnement de développement pour cette topologie.</span><span class="sxs-lookup"><span data-stu-id="2563f-113">You must also have access to the development environment for this topology.</span></span>

<span data-ttu-id="2563f-114">Toutes les tâches de cette rubrique peuvent être effectuées dans l’entreprise **USMF**.</span><span class="sxs-lookup"><span data-stu-id="2563f-114">All the tasks in this topic can be completed in the **USMF** company.</span></span>

## <a name="import-the-fixed-asset-roll-forward-er-format"></a><span data-ttu-id="2563f-115">Importer le format ER de reprise des immobilisations</span><span class="sxs-lookup"><span data-stu-id="2563f-115">Import the Fixed asset roll forward ER format</span></span>

<span data-ttu-id="2563f-116">Pour générer les documents pour lesquels vous prévoyez d’ajouter un emplacement de stockage personnalisé, [importez](er-download-configurations-global-repo.md) la configuration du format ER **Reprise des immobilisations** dans la topologie actuelle.</span><span class="sxs-lookup"><span data-stu-id="2563f-116">To generate the documents that you plan to add a custom storage location for, [import](er-download-configurations-global-repo.md) the **Fixed asset roll forward** ER format configuration into the current topology.</span></span>

![Page du référentiel de configuration](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="2563f-118">Exécuter l’état de récupération d’immobilisation</span><span class="sxs-lookup"><span data-stu-id="2563f-118">Run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="2563f-119">Aller à **Immobilisations** \> **Demandes de renseignements et rapports** \> **Rapports de transaction** \> **Reprise des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="2563f-119">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="2563f-120">Dans le champ **Date de début**, entrez **1/1/2017** (1er janvier 2017).</span><span class="sxs-lookup"><span data-stu-id="2563f-120">In the **From date** field, enter **1/1/2017** (January 1, 2017).</span></span>
3. <span data-ttu-id="2563f-121">Dans le champ **Date de fin**, entrez **1/31/2017** (1er janvier 2017).</span><span class="sxs-lookup"><span data-stu-id="2563f-121">In the **To date** field, enter **1/31/2017** (January 31, 2017).</span></span>
4. <span data-ttu-id="2563f-122">Dans le champ **Devise**, sélectionnez **Devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="2563f-122">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="2563f-123">Dans le champ **Mappage de format**, sélectionnez **Reprise des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="2563f-123">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="2563f-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2563f-124">Select **OK**.</span></span>

![Boîte de dialogue de runtime pour le rapport de reprise des immobilisations](./media/er-custom-storage-generated-files-runtime-dialog.png)

<span data-ttu-id="2563f-126">Dans Microsoft Excel, examinez le document sortant généré et disponible pour téléchargement.</span><span class="sxs-lookup"><span data-stu-id="2563f-126">In Microsoft Excel, review the outbound document that is generated and available for download.</span></span> <span data-ttu-id="2563f-127">Ce comportement est le [comportement par défaut](electronic-reporting-destinations.md#default-behavior) pour un format ER pour lequel aucune [destination](electronic-reporting-destinations.md) n’est configurée, et qui s’exécute en mode interactif.</span><span class="sxs-lookup"><span data-stu-id="2563f-127">This behavior is the [default behavior](electronic-reporting-destinations.md#default-behavior) for an ER format that no [destinations](electronic-reporting-destinations.md) are configured for, and that is running in interactive mode.</span></span>

## <a name="review-the-source-code"></a><span data-ttu-id="2563f-128">Examiner le code source</span><span class="sxs-lookup"><span data-stu-id="2563f-128">Review the source code</span></span>

<span data-ttu-id="2563f-129">Examinez le code de la méthode `generateReportByGER()` de classe `AssetRollForwardService`.</span><span class="sxs-lookup"><span data-stu-id="2563f-129">Review the code of the `generateReportByGER()` method of the `AssetRollForwardService` class.</span></span> <span data-ttu-id="2563f-130">Notez que la méthode `Run()` est utilisée pour appeler la structure de gestion des états électroniques et générer l’état **Reprise des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="2563f-130">Notice that the `Run()` method is used to call the ER framework and generate the **Fixed asset roll forward** report.</span></span>

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

## <a name="modify-the-source-code"></a><span data-ttu-id="2563f-131">Modifier le code source</span><span class="sxs-lookup"><span data-stu-id="2563f-131">Modify the source code</span></span>

1. <span data-ttu-id="2563f-132">Dans votre projet Visual Studio, ajoutez une nouvelle classe (`AssetRollForwardDestination` dans cet exemple) et écrivez du code pour implémenter votre destination personnalisée pour les états **Reprise des immobilisations** générés.</span><span class="sxs-lookup"><span data-stu-id="2563f-132">In your Visual Studio project, add a new class (`AssetRollForwardDestination` in this example), and write code to implement your custom destination for **Fixed asset roll forward** reports that are generated.</span></span>

    - <span data-ttu-id="2563f-133">La méthode `new()` est conçue pour obtenir l’objet de destination ER d’origine et le paramètre logique de l’application qui spécifie l’emplacement personnalisé où les rapports générés doivent être stockés.</span><span class="sxs-lookup"><span data-stu-id="2563f-133">The `new()` method is designed to get the original ER destination object and the application logic–driven parameter that specifies the custom location where generated reports should be stored.</span></span> <span data-ttu-id="2563f-134">Dans cet exemple, l’emplacement personnalisé est le nom d’un dossier du système de fichiers local du serveur qui exécute le service Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="2563f-134">In this example, the custom location is the name of a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    - <span data-ttu-id="2563f-135">La méthode `saveFile()` est conçue pour enregistrer un document généré dans un dossier du système de fichiers local du serveur qui exécute le service AOS.</span><span class="sxs-lookup"><span data-stu-id="2563f-135">The `saveFile()` method is designed to save a generated document to a folder of the local file system of the server that runs the AOS service.</span></span>

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

2. <span data-ttu-id="2563f-136">Dans votre projet Visual Studio, ajoutez une nouvelle classe (`AssetRollForwardDestinationFactory` dans cet exemple), et écrivez du code pour configurer une fabrique de destination personnalisée qui délègue la création d’une destination à la fabrique de destination par défaut, et pour encapsuler une destination de fichier avec votre propre destination.</span><span class="sxs-lookup"><span data-stu-id="2563f-136">In your Visual Studio project, add a new class (`AssetRollForwardDestinationFactory` in this example), and write code to set up a custom destination factory that delegates the creation of a destination to the default destination factory, and to wrap a file destination with your own destination.</span></span>

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

3. <span data-ttu-id="2563f-137">Modifier la classe `AssetRollForwardService` existante et écrivez du code pour configurer une fabrique de destination personnalisée pour le générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2563f-137">Modify the existing `AssetRollForwardService` class, and write code to set up a custom destination factory for the report runner.</span></span> <span data-ttu-id="2563f-138">Notez que lorsqu’une fabrique de destination personnalisée est construite, le paramètre piloté par l’application qui spécifie un dossier cible est transmis.</span><span class="sxs-lookup"><span data-stu-id="2563f-138">Notice that when a custom destination factory is constructed, the application-driven parameter that specifies a target folder is passed.</span></span> <span data-ttu-id="2563f-139">De cette manière, ce dossier cible est utilisé pour stocker les fichiers générés.</span><span class="sxs-lookup"><span data-stu-id="2563f-139">In this way, that target folder is used to store generated files.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="2563f-140">Assurez-vous que le dossier spécifié (**c:\\0** dans cet exemple) est présent dans le système de fichiers local du serveur qui exécute le service AOS.</span><span class="sxs-lookup"><span data-stu-id="2563f-140">Make sure that the specified folder (**c:\\0** in this example) is present in the local file system of the server that runs the AOS service.</span></span> <span data-ttu-id="2563f-141">Sinon, une exception [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) sera levée lors de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="2563f-141">Otherwise, a [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) exception will be thrown at runtime.</span></span>

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

4. <span data-ttu-id="2563f-142">Recréez votre projet.</span><span class="sxs-lookup"><span data-stu-id="2563f-142">Rebuild your project.</span></span>

## <a name="re-run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="2563f-143">Ré-exécutez l’état de récupération d’immobilisation</span><span class="sxs-lookup"><span data-stu-id="2563f-143">Re-run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="2563f-144">Aller à **Immobilisations** \> **Demandes de renseignements et rapports** \> **Rapports de transaction** \> **Reprise des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="2563f-144">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="2563f-145">Dans le champ **Date de début**, entrez **1/1/2017**.</span><span class="sxs-lookup"><span data-stu-id="2563f-145">In the **From date** field, enter **1/1/2017**.</span></span>
3. <span data-ttu-id="2563f-146">Dans le champ **Date de fin**, entrez **1/31/2017**.</span><span class="sxs-lookup"><span data-stu-id="2563f-146">In the **To date** field, enter **1/31/2017**.</span></span>
4. <span data-ttu-id="2563f-147">Dans le champ **Devise**, sélectionnez **Devise comptable**.</span><span class="sxs-lookup"><span data-stu-id="2563f-147">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="2563f-148">Dans le champ **Mappage de format**, sélectionnez **Reprise des immobilisations**.</span><span class="sxs-lookup"><span data-stu-id="2563f-148">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="2563f-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2563f-149">Select **OK**.</span></span>
7. <span data-ttu-id="2563f-150">Explorez le dossier **C:\\0** local pour trouver le fichier généré.</span><span class="sxs-lookup"><span data-stu-id="2563f-150">Browse the local **C:\\0** folder to find the generated file.</span></span>

> [!NOTE]
> <span data-ttu-id="2563f-151">Parce que l’objet `originDestination` n’est pas utilisé dans l’objet `AssetRollForwardDestination` dans cet exemple, les configurations pour les [destinations](electronic-reporting-destinations.md) du format ER sera ignoré lors de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="2563f-151">Because the `originDestination` object isn't used in the `AssetRollForwardDestination` object in this example, the configurations for the ER format [destinations](electronic-reporting-destinations.md) will be ignored at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2563f-152">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2563f-152">Additional resources</span></span>

- [<span data-ttu-id="2563f-153">Destinations pour la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="2563f-153">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="2563f-154">Page d’accueil Extensibilité</span><span class="sxs-lookup"><span data-stu-id="2563f-154">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
