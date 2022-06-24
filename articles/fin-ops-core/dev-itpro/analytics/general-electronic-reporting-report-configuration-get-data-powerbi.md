---
title: Configurer la gestion des états électroniques (ER) pour extraire les données dans Power BI
description: Cet article explique comment vous pouvez utiliser la configuration de gestion des états électroniques (ER) pour organiser le transfert des données entre votre instance et les services Power BI.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e6903513dec4da20dbc4463fbae6a406fc06e1a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896732"
---
# <a name="configure-electronic-reporting-er-to-pull-data-into-power-bi"></a>Configurer la gestion des états électroniques (ER) pour extraire les données dans Power BI

[!include [banner](../includes/banner.md)]

Cet article explique comment vous pouvez utiliser la configuration de gestion des états électroniques (ER) pour organiser le transfert des données entre votre instance et les services Power BI. En guise d’exemple, cet article utilise les transactions de déclaration d’échanges de biens comme données commerciales qui doivent être transférées. La visualisation de carte Power BI utilise ces données de transaction de déclaration d’échanges de biens pour présenter une vue permettant l’analyse des activités d’importation/d’exportation de la société sur l’état Power BI.

## <a name="overview"></a>Vue d’ensemble

Microsoft Power BI est un ensemble de services logiciels, d’applications et de connecteurs qui fonctionnent ensemble pour transformer des sources de données externes en analyses logiques, visuellement immersives et interactives. La gestion des états électroniques (ER) permet aux utilisateurs de configurer facilement les sources de données et d’organiser le transfert des données à partir de l’application vers Power BI. Les données sont transférées en tant que fichiers dans le format de feuille de calcul OpenXML (fichier classeur Microsoft Excel). Les fichiers transférés sont stockés sur un serveur Microsoft SharePoint Server qui a été configuré à cette fin. Les fichiers stockés sont utilisés dans Power BI pour générer des états qui incluent des visualisations (tableaux, graphiques, cartes, etc.). Les états Power BI sont partagés avec les utilisateurs Power BI, et ils sont accessibles dans les tableaux de bord Power BI et sur les pages de l’application. Cet article décrit les tâches suivantes :

- Configurer Microsoft Dynamics 365 Finance.
- Préparez votre configuration du format de gestion des états électroniques pour obtenir des données de l’application Finance.
- Configurez l’environnement ER pour transférer des données vers Power BI.
- Utilisez les données transférées pour créer un état Power BI.
- Rendez l’état Power BI accessible dans Finance.

## <a name="prerequisites"></a>Conditions préalables
Pour exécuter l’exemple décrit dans cet article, vous devez disposer de l’accès suivant :

- L’accès pour l’un des rôles suivants :

    - Développeur d’états électroniques
    - Consultant fonctionnel de gestion des états électroniques
    - Administrateur système

- L’accès au serveur SharePoint qui est configuré pour être utilisé avec l’application
- L’accès au cadre Power BI

## <a name="configure-document-management-parameters"></a>Configurer les paramètres de gestion des documents
1. Sur la page **Paramètres de gestion des documents**, configurez l’accès au serveur SharePoint Server qui sera utilisé dans la société à laquelle vous êtes connecté (la société DEMF dans cet exemple).
2. Testez la connexion au serveur SharePoint Server pour vous assurer que vous en avez obtenu l’accès.

    [![Page Paramètres de gestion des documents.](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)

3. Ouvrez le site SharePoint configuré. Créez un dossier dans lequel ER stockera les fichiers Excel qui ont des données commerciales dont les états Power BI ont besoin comme sources d’ensembles de données Power BI.
4. Sur la page **Types de document**, créez un type de document qui sera utilisé pour accéder au dossier SharePoint que vous venez de créer. Entrez **Fichier** dans le champ **Groupe** et **SharePoint** dans le champ **Emplacement**, puis entrez l’adresse du dossier SharePoint.

    [![Page Types de documents.](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Configurer les paramètres ER
1. Dans l’espace de travail **Génération des états électroniques**, cliquez sur le lien **Paramètres de gestion des états électroniques**.
2. Sous l’onglet **Documents joints**, sélectionnez le type de document **Fichier** pour tous les champs.
3. Dans l’espace de travail **Génération des états électroniques**, rendez le fournisseur requis actif en cliquant sur **Activer**. Pour plus d’informations, lisez le Guide de tâche **ER Sélectionner un fournisseur de services**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Utiliser un modèle de données ER comme source de données
Vous devez disposer d’un modèle de données ER comme source de données commerciales qui sera utilisé dans les états Power BI. Ce modèle de données est téléchargé dans le référentiel de configurations ER. Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](download-electronic-reporting-configuration-lcs.md), ou lisez le Guide de tâche **ER Charger une configuration à partir de Lifecycle Services**. Sélectionnez **Déclaration d’échanges de biens** comme modèle de données qui sera téléchargé depuis le référentiel de configurations ER sélectionné. (Dans cet exemple, la version 1 du modèle est utilisée.) Vous pouvez alors accéder à la configuration du modèle ER **Déclaration d’échanges de biens** sur la page **Configurations**.

[![Configuration du modèle Intrastat ER sur la page Configurations.](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Concevoir une configuration de format ER
Vous devez créer une configuration de format ER en utilisant le modèle de données **Déclaration d’échanges de biens** comme source de données commerciales. Cette configuration de format doit générer des résultats de sortie en tant que documents électroniques dans le format OpenXML (fichier Excel). Pour plus d’informations, lisez le Guide de tâche **ER Créer une configuration pour des états au format OPENXML**. Nommez la nouvelle configuration **Activités d’importation/d’exportation**, comme le montre l’illustration suivante. Utilisez le fichier Excel [Données ER – Détails de l’importation de et de l’exportation](https://download.microsoft.com/download/f/7/5/f755c0fd-025c-4aa9-920b-909abb8302ad/ER-data-import-and-export-details.xlsx) comme modèle lorsque vous concevez le format ER. (Pour plus d’informations sur l’importation d’un modèle de format, lisez le Guide de tâche.)

[![Configuration des activités d’importation/d’exportation.](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png)

Pour modifier la configuration du format **Activités d’importation/d’exportation**, procédez comme suit.

1. Cliquez sur **Concepteur**.
2. Sous l’onglet **Format**, nommez l’élément de fichier pour ce format **Fichier de sortie d’Excel**.

    [![Élément du fichier de sortie Excel.](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)

3. Sous l’onglet **Mappage**, spécifiez le nom du fichier Excel qui sera généré dès que ce format sera exécuté. Configurez l’expression associée pour renvoyer la valeur **Détails d’importation et d’exportation** (l’extension du nom de fichier .xlsx sera ajoutée automatiquement).

    [![Concepteur de formats.](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)

4. Ajoutez un nouvel élément de source de données pour ce format. (Cette énumération sera nécessaire pour effectuer d’autres liaison de données.)

    1. Nommez la source de données **direction\_enum**.
    2. Sélectionnez **Énumération de modèle de données** comme type de source de données.
    3. Voir l’énumération de modèle de données **Direction**.

    [![direction_enum.](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)

5. Complétez la liaison des éléments du modèle de données **Déclaration d’échanges de biens** et des éléments du format défini, comme le montre l’illustration suivante.

    [![Fin de la liaison.](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

Une fois qu’il s’exécute, le format ER génère le résultat de sortie au format Excel. Il envoie les détails des transactions de déclaration d’échanges de biens au résultat de sortie, et les sépare sous forme de transactions qui décrivent des activités d’importation ou des activités d’exportation. Cliquez sur **Exécuter** pour tester le nouveau format ER pour la liste des transactions de déclaration d’échanges de biens sur la page **Déclaration d’échanges de biens** (**Taxe** &gt; **Déclarations** &gt; **Commerce extérieur** &gt; **Déclaration d’échanges de biens**).

[![Page Déclaration d’échanges de biens.](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png)

Le résultat de sortie suivant est généré. Le fichier est nommé **Import and export details.xlsx**, tel que vous l’avez spécifié dans les paramètres du format.

[![Import and export details.xlsx.](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Configurer la destination ER
Vous devez configurer la structure ER pour envoyer le résultat de sortie de la nouvelle configuration du format ER d’une manière particulière.

- Le résultat de sortie doit être envoyé au dossier du serveur SharePoint Server sélectionné.
- Chaque exécution de la configuration du format doit créer une version du même fichier Excel.

Sur la page **Génération d’états électroniques** (**Administration d’organisation** &gt; **Génération d’états électroniques**), cliquez sur l’élément **Destination de la génération d’états électroniques**, puis ajoutez une nouvelle destination. Dans le champ **Référence**, sélectionnez la configuration du format **Activités d’importation/d’exportation** que vous avez créée précédemment. Procédez comme suit pour ajouter un enregistrement de destination de fichier pour référence.

1. Dans le champ **Nom**, entrez le titre du fichier de destination.
2. Dans le champ **Nom du fichier**, sélectionnez le nom **Fichier de sortie d’Excel** pour le composant du format de fichier Excel.

Cliquez sur le bouton **Paramètres** pour le nouvel enregistrement de destination. Puis, dans la boîte de dialogue **Paramètres de destination**, procédez comme suit.

1. Sous l’onglet **Power BI**, définissez l’option **Activé** sur **Oui**.
2. Dans le champ **SharePoint**, sélectionnez le type de document **Partagé** créé précédemment.

## <a name="schedule-execution-of-the-configured-er-format"></a>Programmer l’exécution du format ER configuré
1. Sur la page **Configurations** (**Administration d’organisation** &gt; **Génération d’états électroniques** &gt; **Configurations**), dans l’arborescence des configurations, sélectionnez la configuration **Activités d’importation/d’exportations** que vous avez créée précédemment.
2. Modifiez le statut de la version 1.1 de **Brouillon** à **Terminée** pour rendre ce format utilisable.

    [![Configuration des activités d’importation / exportation sur la page Configurations.](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png)

3. Sélectionnez la version terminée de la configuration **Activités d’importation/d’exportation**, puis cliquez sur **Exécuter**. Notez que la destination configurée est appliquée au résultat de sortie qui est généré dans le format Excel.
4. Définissez l’option **Traitement par lots** sur **Oui** pour d’exécuter cet état en mode sans assistance.
5. Cliquez sur **Répétition** pour planifier la récurrence requise de cette exécution du traitement par lots. La récurrence définit la fréquence à laquelle les données mises à jour seront transférées vers Power BI.

    [![Boîte de dialogue Paramètres de génération d’états électroniques.](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png)

6. Après l’avoir configurée, vous pouvez rechercher la tâche d’exécution de l’état ER sur la page **Traitements par lots** (**Administration système &gt; Recherches &gt; Traitements par lots**).

    [![Page Traitements par lots.](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png)

7. Lorsque cette tâche est exécutée pour la première fois, la destination crée un fichier Excel qui contient le nom configuré du dossier SharePoint sélectionné. Chaque fois que la tâche est exécutée par la suite, la destination crée une version de ce fichier Excel.

    [![Nouvelle version du fichier Excel.](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Créez un ensemble de données Power BI à l’aide du résultat de sortie du format ER
1. Connectez-vous à Power BI, puis ouvrez un groupe Power BI existant (espace de travail) ou créez un groupe. Cliquez sur **Ajouter** sous **Fichiers** dans la section **Importer ou se connecter aux données** ou sur le signe (**+**) en regard de **Ensembles de données** dans le volet gauche.

    [![Création d’un ensemble de données.](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png)

2. Sélectionnez l’option **SharePoint – Sites d’équipe**, puis entrez le chemin d’accès du serveur SharePoint Server que vous utilisez (`https://ax7partner.litware.com` dans notre exemple).
3. Accédez au dossier **/Shared Documents/GER data/PowerBI**, puis sélectionnez le fichier Excel que vous avez créé comme source de données pour le nouvel ensemble de données Power BI.

    [![Sélection du fichier Excel.](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png)

4. Cliquez **Connecter**, puis sur **Importer**. Un ensemble de données est créé, basé sur le fichier Excel sélectionné. L’ensemble de données peut également être ajouté automatiquement au tableau de bord nouvellement créé.

    [![Ensemble de données sur le tableau de bord.](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png)

5. Configurez le programme d’actualisation pour cet ensemble de données pour forcer une mise à jour périodique. Les mises à jour périodiques activent la consommation de nouvelles données commerciales via l’exécution périodique de la gestion des états périodiques à l’aide des nouvelles versions du fichier Excel créées dans le serveur SharePoint Server.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Créer un état Power BI à l’aide du nouvel ensemble de données
1. Cliquez sur l’ensemble de données Power BI **Détails d’importation et d’exportation** que vous avez créé.
2. Configurez la visualisation. Par exemple, sélectionnez la visualisation **Carte remplie**, et configurez-la comme suit :

    - Affectez le champ d’ensemble de données **CountryOrigin** au champ **Emplacement** de la visualisation de carte.
    - Affectez le champ d’ensemble de données **Montant** au champ **Saturation des couleurs** de la visualisation de carte.
    - Ajoutez les champs d’ensembles de données **Activité** et **Année** à la collection de champs **Filtres** de la visualisation de carte.

3. Enregistrez l’état Power BI comme **État de détails d’importation et d’exportation**.

    [![État des détails d’importation et d’exportation.](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png)

    Notez que la carte affiche les pays/régions qui sont mentionnés dans le fichier Excel (Autriche et Suisse dans cet exemple). Ces pays/régions sont colorés pour afficher la proportion de montants facturés pour chacun.

4. Mettez à jour la liste des transactions de déclaration d’échanges de biens. La transaction d’exportation qui provient d’Italie est ajoutée.

    [![Liste des transactions de déclaration d’échanges de biens.](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png)

5. Attendez la prochaine exécution prévue de l’état ER et la prochaine mise à jour programmée de l’ensemble de données Power BI. Examinez l’état Power BI (sélectionnez pour afficher les transactions d’importation uniquement). La carte mise à jour affiche maintenant l’Italie.

    [![Carte mise à jour.](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-finance"></a>L’accès à l’état Power BI dans Finance
Configurez l’intégration à Power BI. Pour plus d’informations, voir [Configurer l’intégration Power BI pour les espaces de travail](configure-power-bi-integration.md).

1. Sur la page de l’espace de travail **Génération d’états électroniques** prenant en charge l’intégration de Power BI (**Administration d’organisation** &gt; **Espaces de travail** &gt; **Espace de travail électronique de génération d’états**), cliquez sur **Options** &gt; **Ouvrez le catalogue d’états**.
2. Sélectionnez l’état Power BI **Détails de l’importation et de l’exportation** que vous avez créé, pour l’afficher comme élément d’action sur la page sélectionnée.
3. Cliquez sur l’élément d’action pour ouvrir la page affichant l’état que vous avez conçu dans Power BI.

    [![État des détails d’importation et d’exportation conçu dans Power BI.](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)

[Vue d’ensemble des états électroniques (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
