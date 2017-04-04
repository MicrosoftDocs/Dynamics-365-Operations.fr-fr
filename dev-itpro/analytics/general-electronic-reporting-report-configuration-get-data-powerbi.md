---
title: "Génération d&quot;états électronique de paramétrage pour fournir au projet BI d&quot;alimentation des données Dynamics 365 pour les opérations"
description: "Cette rubrique explique comment vous pouvez utiliser la configuration de génération d&quot;états électroniques (ER) pour organiser le transfert des données entre votre instance de Dynamics 365 for Operations vers les services Power BI. En guise d&quot;exemple, cette rubrique utilise les transactions de déclaration d&quot;échanges de biens comme données commerciales qui doivent être transférées. La visualisation de carte Power BI utilise ces données de transaction de déclaration d&quot;échanges de biens pour présenter une vue permettant l&quot;analyse des activités d&quot;importation/d&quot;exportation de la société sur l&quot;état Power BI."
author: kfend
manager: AnnBe
ms.date: 2016-10-31 13 - 22 - 29
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ed0192c44b6d7e88120c64e539ebb0ac3b379831
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-electronic-reporting-to-provide-power-bi-with-data-from-dynamics-365-for-operations"></a>Génération d'états électronique de paramétrage pour fournir au projet BI d'alimentation des données Dynamics 365 pour les opérations

Cette rubrique explique comment vous pouvez utiliser la configuration de génération d'états électroniques (ER) pour organiser le transfert des données entre votre instance de Dynamics 365 for Operations vers les services Power BI. En guise d'exemple, cette rubrique utilise les transactions de déclaration d'échanges de biens comme données commerciales qui doivent être transférées. La visualisation de carte Power BI utilise ces données de transaction de déclaration d'échanges de biens pour présenter une vue permettant l'analyse des activités d'importation/d'exportation de la société sur l'état Power BI.

<a name="overview"></a>Vue d'ensemble
--------

Microsoft Power BI est un ensemble de services logiciels, d'applications, et de connecteurs qui fonctionnent ensemble pour transformer des sources de données externes en analyses logiques, visuellement immersives et interactives. La génération d'états électroniques (ER) permet aux utilisateurs de Microsoft Dynamics 365 for Operations de configurer facilement des sources de données et d'organiser simplement le transfert des données de Dynamics 365 for Operations vers Power BI. Les données sont transférées en tant que fichiers dans le format de feuille de calcul OpenXML (fichier classeur Microsoft Excel). Les fichiers transférés sont stockés sur un serveur Microsoft SharePoint Server qui a été configuré à cette fin. Les fichiers stockés sont utilisés dans Power BI pour générer des états qui incluent des visualisations (tableaux, graphiques, cartes, etc.). Les états Power BI sont partagés avec les utilisateurs Power BI, et ils sont accessibles dans des tableaux de bord Power BI et sur les pages Dynamics 365 for Operations. Cette rubrique décrit les tâches suivantes :

-   Configurez Dynamics 365 for Operations.
-   Préparez votre configuration du format d'ER pour obtenir des données de Dynamics 365 for Operations.
-   Configurez l'environnement ER pour transférer des données vers Power BI.
-   Utilisez les données transférées pour créer un état Power BI.
-   Rendez l'état Power BI accessible dans Dynamics 365 for Operations.

## <a name="prerequisites"></a>Conditions préalables
Pour exécuter l'exemple décrit dans cette rubrique, vous devez disposer de l'accès suivant :

-   L'accès à Dynamics 365 for Operations pour l'un des rôles suivants :
    -   Développeur de gestion des états électroniques
    -   Consultant fonctionnel de gestion des états électroniques
    -   Administrateur système
-   L'accès au serveur SharePoint Server configuré pour être utilisé avec Dynamics 365 for Operations
-   L'accès à la structure Power BI

## <a name="configure-document-management-parameters"></a>Configurer les paramètres de gestion des documents
1.  Sur la page **Paramètres de gestion des documents**, configurez l'accès au serveur SharePoint Server qui sera utilisé dans la société à laquelle vous êtes connecté (la société DEMF dans cet exemple).
2.  Testez la connexion au serveur SharePoint Server pour vous assurer que vous en avez obtenu l'accès. [page Paramètres de gestion des documents![] (. /media/ger-power-bi-sharepoint-server-setting-1024x369.png)](. /media/ger-power-bi-sharepoint-server-setting.png)
3.  Ouvrez le site SharePoint configuré. Créez un dossier dans lequel ER stockera les fichiers Excel qui ont des données commerciales dont les états Power BI ont besoin comme sources d'ensembles de données Power BI.
4.  Dans Dynamics 365 for Operations, sur la page **Types de document**, créez un type de document qui sera utilisé pour accéder au dossier SharePoint que vous venez de créer. Entrez **Fichier** dans le champ **Groupe** et **SharePoint** dans le champ **Emplacement**, puis entrez l'adresse du dossier SharePoint. [page de types de documents![] (. /media/ger-power-bi-sharepoint-document-type-1024x485.png)](. /media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Configurer les paramètres ER
1.  Dans l'espace de travail **Génération des états électroniques**, cliquez sur le lien **Paramètres de gestion des états électroniques**.
2.  Sous l'onglet **Documents joints**, sélectionnez le type de document **Fichier** pour tous les champs.
3.  Dans l'espace de travail **Génération des états électroniques**, rendez le fournisseur requis actif en cliquant sur **Activer**. Pour plus d'informations, lisez le Guide de tâche **ER Sélectionner un fournisseur de services**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Utiliser un modèle de données ER comme source de données
Vous devez disposer d'un modèle de données ER comme source de données commerciales qui sera utilisé dans les états Power BI. Ce modèle de données est téléchargé dans le référentiel de configurations ER. Pour plus d'informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](download-electronic-reporting-configuration-lcs.md), ou lisez le Guide de tâche **ER Charger une configuration à partir de Lifecycle Services**. Sélectionnez **Déclaration d'échanges de biens **comme modèle de données qui sera téléchargé depuis le référentiel de configurations ER sélectionné. (Dans cet exemple, la version 1 du modèle est utilisée.) Vous pouvez alors accéder ** déclaration d'échanges de biens ** la configuration modèle d'ER sur ** des configurations ** la page. [page de configurations d'![] (. /media/ger-power-bi-data-model-1024x371.png)](. /media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Concevoir une configuration de format ER
Vous devez créer une configuration de format ER en utilisant le modèle de données **Déclaration d'échanges de biens** comme source de données commerciales. Cette configuration de format doit générer des résultats de sortie en tant que documents électroniques dans le format OpenXML (fichier Excel). Pour plus d'informations, lisez le Guide de tâche **ER Créer une configuration pour des états au format OPENXML**. Nommez la nouvelle configuration **Activités d'importation/d'exportation**, comme le montre l'illustration suivante. Utilisez le fichier Excel [Données ER - Détails de l'importation de et de l'exportation](https://go.microsoft.com/fwlink/?linkid=845208) comme modèle lorsque vous concevez le format ER. (Pour plus d'informations sur l'importation un modèle de format, jouez le Guide de tâche.) [configuration des activités d'importation/exportation![] (support/ger-power-bi-format-configuration.png)](support/ger-power-bi-format-configuration.png) pour modifier ** les activités d'importation/exportation ** formatent la configuration, procédez comme suit.

1.  Cliquez sur **Concepteur**.
2.  Sous l'onglet **Format**, nommez l'élément de fichier pour ce format **Fichier de sortie d'Excel**. [élément de fichier de sortie![Excel (]. /media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](. /media/ger-power-bi-format-configuration-file-element-name.png)
3.  Sous l'onglet **Mappage**, spécifiez le nom du fichier Excel qui sera généré dès que ce format sera exécuté. Configurez l'expression associée pour renvoyer la valeur **Détails d'importation et d'exportation** (l'extension du nom de fichier .xlsx sera ajoutée automatiquement). [![Format designer](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)
4.  Ajoutez un nouvel élément de source de données pour ce format. (Cette énumération sera nécessaire pour effectuer d'autres liaison de données.)
    1.  Nomment la source de données ** énumération d'\_de direction **.
    2.  Sélectionnez **Énumération de modèle de données** comme type de source de données.
    3.  Voir l'énumération de modèle de données **Direction**.

    [énumération d'\_de direction d'![] (. /media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](. /media/ger-power-bi-format-configuration-mapping-added-enum.png)
5.  Complétez la liaison des éléments du modèle de données **Déclaration d'échanges de biens** et des éléments du format défini, comme le montre l'illustration suivante. [![complétant la liaison] (. /media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](. /media/ger-power-bi-format-configuration-mapping-details.png)

Une fois qu'il s'exécute, le format ER génère le résultat de sortie au format Excel. Il envoie les détails des transactions de déclaration d'échanges de biens au résultat de sortie, et les sépare sous forme de transactions qui décrivent des activités d'importation ou des activités d'exportation. Cliquez sur ** exécution ** pour tester le nouveau format d'ER pour la liste des transactions de déclaration d'échanges de biens sur ** déclaration d'échanges de biens ** la page (** taxe ** &gt; ** déclarations ** &gt; ** commerce extérieur ** &gt; ** déclaration d'échanges de biens **). [page de déclaration![échanges de biens![] (. /media/ger-power-bi-format-test-run-transactions-1024x322.png)](. /media/ger-power-bi-format-test-run-transactions.png) Le résultat suivant de sortie est généré. Le fichier est nommé **Import and export details.xlsx**, tel que vous l'avez spécifié dans les paramètres du format. [importation et![exportation details.xlsx![] (. /media/ger-power-bi-format-test-run-output-1024x472.png)](. /media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Configurer la destination ER
Vous devez configurer la structure ER pour envoyer le résultat de sortie de la nouvelle configuration du format ER d'une manière particulière.

-   Le résultat de sortie doit être envoyé au dossier du serveur SharePoint Server sélectionné.
-   Chaque exécution de la configuration du format doit créer une version du même fichier Excel.

Sous ** génération d'états électronique ** la page (** Administration d'organisation ** &gt; ** génération d'états électronique **), cliquez sur ** destination électronique de génération d'états ** l'article, d'ajouter une nouvelle destination. Dans le champ **Référence**, sélectionnez la configuration du format **Activités d'importation/d'exportation** que vous avez créée précédemment. Procédez comme suit pour ajouter un enregistrement de destination de fichier pour référence.

1.  Dans le champ **Nom**, entrez le titre du fichier de destination.
2.  Dans le champ **Nom du fichier**, sélectionnez le nom **Fichier de sortie d'Excel** pour le composant du format de fichier Excel.

Cliquez sur le bouton **Paramètres** pour le nouvel enregistrement de destination. Puis, dans la boîte de dialogue **Paramètres de destination**, procédez comme suit.

1.  Sous l'onglet **Power BI**, définissez l'option **Activé** sur **Oui**.
2.  Dans le champ **SharePoint**, sélectionnez le type de document **Partagé** créé précédemment.

## <a name="schedule-execution-of-the-configured-er-format"></a>Programmer l'exécution du format ER configuré
Sous ** des configurations ** page (** Administration d'organisation ** &gt; ** génération d'états électronique ** &gt; ** des configurations **), dans l'arborescence de configurations, sélectionnez ** des activités d'importation/exportation ** la configuration que vous avez créée précédemment. Modifiez le statut de la version 1.1 de **Brouillon** à **Terminée** pour rendre ce format utilisable. [page de configurations d'![] (. /media/ger-power-bi-format-configuration-complete-1024x401.png)](. /media/ger-power-bi-format-configuration-complete.png) Sélectionnez la version terminée ** des activités d'importation/exportation ** de la configuration, puis cliquez sur ** exécution **. Notez que la destination configurée est appliquée au résultat de sortie qui est généré dans le format Excel. Définissez l'option **Traitement par lots** sur **Oui** pour d'exécuter cet état en mode sans assistance. Cliquez sur **Répétition** pour planifier la récurrence requise de cette exécution du traitement par lots. La récurrence définit la fréquence à laquelle les données mises à jour seront transférées de Dynamics 365 for Operations vers Power BI. [boîte de dialogue électronique de paramètres d'état![] (. /media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](. /media/ger-power-bi-format-configuration-run-to-schedule.png) Après avoir configuré, vous pouvez rechercher la tâche d'exécution de l'état des ER sur ** des traitements par lots ** la page (** des traitements par lots Recherches Administration &gt; du système &gt; **). [page de traitements par lots d'![] (. /media/ger-power-bi-format-configuration-running-job-1024x410.png)](. /media/ger-power-bi-format-configuration-running-job.png) Lorsque cette tâche est exécutée pour la première fois, la destination crée un nouveau fichier Excel qui contient le nom configuré dans le dossier sélectionné SharePoint. Chaque fois que la tâche est exécutée par la suite, la destination crée une version de ce fichier Excel. [nouvelle version![du fichier Excel (]. /media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](. /media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Créez un ensemble de données Power BI à l'aide du résultat de sortie du format ER
Connectez-vous à Power BI, puis ouvrez un groupe Power BI existant (espace de travail) ou créez un groupe. Cliquez sur ** ajoutez ** sous ** des fichiers ** dans ** importez ou connectez-vous aux données ** la section, ou cliquez sur le signe plus (**+**) de l'écran ** des datasets ** dans le volet gauche. [![créant un ensemble de données] (. /media/ger-power-bi-add-dataset-1024x524.png)](. /media/ger-power-bi-add-dataset.png) Sélectionnez ** SharePoint – Les sites d'équipe ** option, puis entrez le chemin du Server que vous utilisez (** https://ax7partner.spoppe.com** dans notre exemple). Puis accédez au dossier **/Shared Documents/GER data/PowerBI**, puis sélectionnez le fichier Excel que vous avez créé comme source de données pour le nouvel ensemble de données Power BI. [![sélectionnant le fichier Excel (]. /media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](. Cliquez sur /media/ger-power-bi-add-dataset-select-excel-file.png) ** connexion **, puis sur ** importation **. Un ensemble de données est créé, basé sur le fichier Excel sélectionné. L'ensemble de données peut également être ajouté automatiquement au tableau de bord nouvellement créé. [ensemble de données![sur le tableau de bord (]. /media/ger-power-bi-added-dataset-1024x489.png)](. /media/ger-power-bi-added-dataset.png) Configurer le programme d'actualisation pour ce dataset force une mise à jour. Les mises à jour périodiques activent la consommation de nouvelles données commerciales provenant de Dynamics 365 for Operations via l'exécution périodique de l'état ER à l'aide des nouvelles versions du fichier Excel créées dans le serveur SharePoint Server.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Créer un état Power BI à l'aide du nouvel ensemble de données
Pour créer un état Power BI, cliquez sur l'ensemble de données Power BI **Détails d'importation et d'exportation** que vous avez créé. Puis configurez la visualisation. Par exemple, sélectionnez la visualisation **Carte remplie**, et configurez-la comme suit :

-   Affectez le champ d'ensemble de données **CountryOrigin** au champ **Emplacement** de la visualisation de carte.
-   Affectez le champ d'ensemble de données **Montant** au champ **Saturation des couleurs** de la visualisation de carte.
-   Ajoutez les champs d'ensembles de données **Activité** et **Année** à la collection de champs **Filtres** de la visualisation de carte.

Enregistrez l'état Power BI comme **État de détails d'importation et d'exportation**. [importation![et rapport détaillé d'exportation] (. /media/ger-power-bi-added-report-1024x498.png)](. Note /media/ger-power-bi-added-report.png) affichant de carte les pays/régions qui sont mentionnées dans le fichier Excel (Autriche et la Suisse dans cet exemple). Ces pays/régions sont colorés pour afficher la proportion de montants facturés pour chacun. Mettez à jour la liste des transactions de déclaration d'échanges de biens. La transaction d'exportation qui provient d'Italie est ajoutée. [liste des transactions de déclaration d'échanges de biens entre![] (. /media/ger-power-bi-new-run-new-transaction-1024x321.png)](. En attente de /media/ger-power-bi-new-run-new-transaction.png) de la prochaine exécution prévue de l'état d'ER et la mise à jour programmée du dataset BI de courant. Examinez l'état Power BI (sélectionnez pour afficher les transactions d'importation uniquement). La carte mise à jour affiche maintenant l'Italie. [carte mise à jour par![] (. /media/ger-power-bi-new-run-new-map-1024x511.png)](. /media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-dynamics-365-for-operations"></a>Accéder à l'état Power BI dans Dynamics 365 for Operations
Paramétrez l'intégration entre Dynamics 365 for Operations et Power BI. Pour plus d'informations, voir [Configuration de l'intégration Power BI pour les espaces de travail](configure-power-bi-integration.md). Sous ** génération d'états électronique ** la page de l'espace de travail qui prend en charge l'intégration BI de courant (** Administration d'organisation ** &gt; ** des espaces de travail ** &gt; ** l'espace de travail électronique de génération d'états **), cliquez sur ** options ** &gt; ** ouvre le catalogue d'état **. Sélectionnez l'état Power BI **Détails de l'importation et de l'exportation** que vous avez créé, pour l'afficher comme élément d'action sur la page sélectionnée. Cliquez sur l'élément d'action pour ouvrir la page Dynamics 365 for Operations affichant l'état que vous avez conçu dans Power BI. [importation![et rapport détaillé d'exportation] (. /media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](. /media/ger-power-bi-review-bi-report-in-ax-form.png)

<a name="see-also"></a>Voir également :
--------

[Destinations des états électroniques](electronic-reporting-destinations.md)

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)


