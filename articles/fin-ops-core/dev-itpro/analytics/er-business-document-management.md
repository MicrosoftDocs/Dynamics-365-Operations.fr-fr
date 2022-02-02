---
title: Vue d’ensemble du module Gestion de document commercial
description: Cette rubrique fournit des informations sur l’utilisation de la fonctionnalité Gestion de document commercial de la structure de gestion des états électroniques (ER).
author: NickSelin
ms.date: 04/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERSecurityAccessEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: faea9d4d9b3fc8f3f1474b6bb2a8dc31cdc22511
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986249"
---
# <a name="business-document-management-overview"></a>Vue d’ensemble du module Gestion de document commercial

[!include [banner](../includes/banner.md)]

Les utilisateurs professionnels utilisent la structure de [Gestion des états électroniques (ER)](general-electronic-reporting.md) pour configurer des formats pour les documents sortants conformément aux obligations légales de différents pays/régions. Ils peuvent également définir le flux de données pour spécifier quelles données d’application placer dans les documents générés. La structure de gestion des états électroniques génère des documents sortants dans des formats Microsoft Office (des classeurs Excel ou des documents Word) à l’aide de modèles prédéfinis. Les modèles sont renseignés avec les données requises conformément au flux de données configuré pendant la génération des documents requis. Chaque format configuré peut être publié dans le cadre d’une solution de gestion des états électroniques pour générer les documents sortants spécifiques. Cela est représenté par une configuration de format ER qui peut contenir des modèles qui vous permettent de générer différents documents sortants. Les utilisateurs professionnels peuvent utiliser cette structure pour gérer les documents commerciaux requis.

Le module **Gestion de document commercial** repose sur la structure d’ER et permet aux utilisateurs d’entreprise de modifier des modèles de documents commerciaux à l’aide du service Microsoft 365 ou de l’application de bureau Microsoft Office appropriée. Parmi les modifications apportées aux documents on trouve la modification des conceptions de documents commerciaux et l’ajout des espaces réservés pour les données supplémentaires sans modifier le code source ni faire de nouveaux déploiements. Aucune connaissance de la structure d’ER n’est nécessaire pour la mise à jour de modèles de documents commerciaux.

> [!NOTE]
> Notez que le module Gestion de document commercial permet de modifier les modèles utilisés pour produire des documents commerciaux, tels que les commandes, les factures, etc. Même si un modèle a été modifié et qu’une nouvelle version a été émise, cette version est utilisée pour générer les documents commerciaux requis. Le module Gestion de document commercial ne permet pas de modifier les documents commerciaux déjà générés.

## <a name="supported-deployments"></a>Déploiements pris en charge

Actuellement, la fonctionnalité Gestion de document commercial est implémentée uniquement pour les déploiements Cloud. Si cette fonctionnalité est indispensable pour un déploiement sur site, indiquez-le en laissant un commentaire sur le site [Idées](https://experience.dynamics.com/ideas/).

## <a name="supported-microsoft-office-applications"></a>Applications Microsoft Office prises en charge

Pour utiliser le module Gestion de document commercial pour modifier les modèles dans des formats Excel ou Word à l’aide des applications de bureau Microsoft Office, Microsoft Office 2010 ou une version ultérieure doit être installé. Il n’est pas pris en charge dans le cloud et les déploiements locaux.

Pour utiliser le module Gestion de document commercial pour modifier les modèles dans des formats Excel ou Word à l’aide des applications Microsoft 365, vous devez avoir Microsoft 365 Office pour l’abonnement web. Ceci est pris en charge dans le déploiement cloud.

## <a name="business-document-availability"></a>Disponibilité de la gestion de document commercial

Pour une liste complète de tous les états prévus pour le lancement d’octobre 2019, voir [Génération d’états de documents commerciaux configurables dans Word et Excel](/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details).

Pour une liste complète de tous les états prévus pour le lancement d’octobre 2020, voir [Documents commerciaux configurables – Modèles Word](/dynamics365-release-plan/2020wave1/dynamics365-finance/configurable-business-documents-word-templates).

D’autres états seront disponibles dans les prochaines versions. Des notifications spécifiques sur les états supplémentaires seront envoyées séparément. Pour savoir comment consulter la liste des états actuellement disponibles, consultez la section [Liste des configurations de gestion des états électroniques qui ont été publiées dans Finance pour prendre en charge les documents commerciaux configurables](#list-of-configurations-cbd) ci-après.

Pour en savoir plus sur cette fonctionnalité, exécutez l’exemple décrit dans cette rubrique.

## <a name="configure-er-parameters"></a>Configurer les paramètres ER

Comme le module Gestion de document commercial repose sur la structure de gestion des états électroniques, vous devez configurer les paramètres des états électroniques pour commencer à utiliser ce module. Pour ce faire, vous devez définir les paramètres des états électroniques comme décrit dans [Configurer les états électroniques (ER)](electronic-reporting-er-configure-parameters.md). Vous devez également ajouter un nouveau fournisseur de configuration comme décrit dans [Créer des fournisseurs de configuration et les marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Espace de travail ER.](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>Importer des solutions d’ER

Des exemples de configurations ER sont utilisés dans l’exemple de cette procédure. Vous devez importer, dans votre instance actuelle de Dynamics 365 Finance, les configurations ER contenant les modèles de document commercial qui peuvent être modifiés à l’aide de la gestion des documents commerciaux. Téléchargez et enregistrez localement les fichiers suivants pour exécuter cette procédure.

**Exemple de solution de facturation de client d’ER**

| Fichier                                      | Contenu |
|-------------------------------------------|---------|
| Customer invoicing model.version.2.xml    | [Configuration de modèle de données ER](https://download.microsoft.com/download/b/f/a/bfa5cb52-e6e2-42bc-a4c0-77014a4c54e6/Customerinvoicingmodel.version.2.xml) |
| Customer FTI report (GER).version.2.3.xml | [Configurations de format ER de facture financière](https://download.microsoft.com/download/3/c/2/3c2e58f2-6e56-43d9-85ea-4c97252a108d/CustomerFTIreportGER.version.2.3.xml) |

**Exemple de solution de paiement par chèque d’ER**

| Fichier                                     | Contenu |
|------------------------------------------|---------|
| Model for cheques.version.10.xml         | [Configuration de modèle de données ER](https://download.microsoft.com/download/3/7/6/376cb0f6-181a-4895-a432-390ffca64162/Modelforcheques.version.10.xml) |
| Cheques printing format.version.10.9.xml | [Configuration du format ER de paiement par chèque](https://download.microsoft.com/download/6/d/6/6d61bfff-3d89-4377-9e34-2e3ee6d6df91/Chequesprintingformat.version.10.9.xml) |

**Exemple de solution de commerce extérieur d’ER**

| Fichier                             | Contenu |
|----------------------------------|---------|
| Intrastat model.version.1.xml    | [Configuration de modèle de données ER](https://download.microsoft.com/download/2/0/0/200d6ed1-eff8-48ec-ab75-175a4acf9714/Intrastatmodel.version.1.xml) |
| Intrastat report.version.1.9.xml | [Configuration du format ER d’état de contrôle de déclaration d’échanges de biens](https://download.microsoft.com/download/7/a/2/7a2a27c3-a8a5-42a1-9d04-f0a8e1ec1707/Intrastatreport.version.1.9.xml) |

Procédez comme suit pour importer chaque fichier. Importez la configuration de *modèle de données* d’ER de chaque solution d’ER dans les tables ci-dessus avant d’importer la configuration de *format* d’ER correspondante.

1. Ouvrez la page **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sélectionnez **Échanger** en haut de la page.
3. Sélectionnez **Charger depuis le fichier XML**.
4. Sélectionnez **Parcourir** pour charger le fichier XML requis.
5. Sélectionnez **OK** pour confirmer l’importation de la configuration.

![Page de configurations de gestion des états électroniques confirmant l’importation de la configuration.](./media/BDM-Overview-ERSolutions.png)

Sinon, vous pouvez importer les configurations officiellement au format ER publiées depuis Microsoft Dynamics Lifecycle Services (LCS). Par exemple, pour réexécuter cette procédure, vous pouvez importer la dernière version de la configuration de format ER **Facture financière (Excel)**. Le modèle de données de gestion des états électroniques correspondants et les configurations de mise en correspondance du modèle de gestion des états électroniques seront importés automatiquement.

![Page de contenu de bibliothèque d’actifs partagés LCS.](./media/BDM-Overview-SharedAssetLibrary.png)

Pour plus d’informations sur l’importation des configurations d’ER, voir [Gérer le cycle de vie de la configuration des états électroniques](general-electronic-reporting-manage-configuration-lifecycle.md).

## <a name="enable-business-document-management"></a>Activer le module Gestion de document commercial

Pour démarrer le module Gestion de document commercial, vous devez ouvrir l’espace de travail **Gestion des fonctions** et activer la fonctionnalité **Gestion de document commercial**.

Procédez comme suit pour activer la fonctionnalité Gestion de document commercial pour toutes les entités juridiques.

1. Ouvrez l’espace de travail **Gestion des fonctionnalités**.
2. Dans l’onglet **Nouveau**, sélectionnez la fonctionnalité **Gestion de document commercial** dans la liste.
3. Sélectionnez **Activer maintenant** pour activer la fonctionnalité sélectionnée.
4. Actualisez la page pour accéder à la nouvelle fonctionnalité.

> [!NOTE]
> Pour plus d’informations sur l’utilisation de la nouvelle interface utilisateur dans Gestion des documents commerciaux, consultez [Nouvelle interface utilisateur de document dans la gestion des documents commerciaux](er-business-document-management-new-template-ui.md).

![Espace de travail Gestion des fonctionnalités.](./media/BDM-Overview-FMEnabling.png)

Pour plus d’informations sur l’activation de nouvelles fonctionnalités, voir [Présentation de la gestion des fonctionnalités](../../fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-parameters"></a>Configurer les paramètres

Utilisez les informations des sections suivantes pour paramétrer les paramètres de base pour le module Gestion de document commercial.

### <a name="prerequisites-for-parameter-setup"></a>Conditions requises pour le paramétrage

Avant de paramétrer le module Gestion de document commercial, vous devez paramétrer le type de document requis dans la structure de gestion des documents. Ce type de document est utilisé pour spécifier un stockage temporaire de documents dans les formats Office (Excel et Word) utilisés en tant que modèles pour les états ER. Le modèle de stockage temporaire peut être modifié à l’aide des applications de bureau Office.

Pour ce type de document, les valeurs d’attribut suivantes doivent être sélectionnées.

| Nom d’attribut | Valeur d’attribut |
|----------------|-----------------|
| Classe          | Fichier joint     |
| Regrouper          | Fichier            |
| Emplacement       | SharePoint      |

Pour plus d’informations sur la définition des paramètres et des types de document requis pour le module Gestion de document commercial, voir [Configurer la gestion des documents](../../fin-ops/organization-administration/configure-document-management.md).

![Paramétrer un type de document pour la gestion des documents.](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a><a name="SetupBdmParameters"></a>Définir les paramètres

Les paramètres de base du module Gestion de document commercial peuvent être définis sur la page **Paramètres de document commercial**. Seuls certains utilisateurs peuvent accéder à la page. Notamment :

- Les utilisateurs ayant le rôle d’**Administrateur système**.
- Les utilisateurs affectés à n’importe quel rôle qui est configuré pour exécuter la fonction, **Tenir à jour les paramètres du module Gestion de document commercial** (nom d’AOA **ERBDMaintainParameters**).

Suivez les procédures suivantes pour définir les paramètres de base pour toutes vos entités juridiques.

1. Connectez-vous en tant qu’utilisateur avec accès à la page **Paramètres de document commercial**.
2. Accédez à **Administration d’organisation** \> **Gestion des états électroniques** \> **Gestion de document commercial** \> **Paramètres de document commercial**.
3. Sur la page **Paramètres de document commercial**, sous l’onglet **Documents joints**, dans le champ **Type de document SharePoint**, définissez le type de document à utiliser pour stocker temporairement des modèles dans des formats Office lorsqu’ils sont modifiés à l’aide des applications de bureau Office. 

> [!NOTE]
> Seuls les types de documents configurés à l’aide d’un emplacement SharePoint sont disponibles pour ce paramètre.

![Définition des paramètres du module Gestion de document commercial.](./media/BDM-Overview-BDMSetting.png)

Le type de document sélectionné est spécifique à la société et sera utilisé lorsque l’utilisateur travaille avec le module Gestion de document commercial dans la société pour laquelle le type de document sélectionné est configuré. Lorsque l’utilisateur travaille avec le module Gestion de document commercial dans une autre société, le même type de document sélectionné est utilisé s’il a été configuré pour cette société. Lorsqu’un type de document a été configuré, il sera utilisé à la place de celui sélectionné dans le champ **Type de document SharePoint**.

> [!NOTE]
> Le paramètre **Type de document SharePoint** définit un dossier SharePoint comme stockage temporaire pour les modèles modifiables à l’aide de Microsoft Excel ou de Word. Vous devez configurer ce paramètre si vous prévoyez d’utiliser ces applications de bureau Office pour modifier des modèles. Pour plus d’informations, voir [Modifier un modèle dans l’application de bureau Office](#EditInOfficeDesktopApp). Vous pouvez laisser ce paramètre vide si vous prévoyez de modifier le modèle en utilisant uniquement les fonctionnalités de Microsoft 365. Pour plus d’informations, voir [Modifier un modèle dans Microsoft 365](#EditInOffice365).

## <a name="configure-access-permissions"></a>Configurer les autorisations d’accès

Par défaut, lorsque l’accès aux autorisations du module Gestion de document commercial n’est pas activé, chaque utilisateur qui a accès à l’espace de travail de ce module voit tous les modèles de solution d’ER disponibles. L’espace de travail du module Gestion de document commercial n’affiche que les modèles résidant dans les configurations de format ER et marqués par une balise **Type de document commercial**.

![Page de configurations de gestion des états électroniques avec balise de type de document commercial.](./media/BDM-Overview-ERFormatTags.png)

La liste des modèles disponibles dans l’espace de travail du module Gestion de document commercial peut être restreinte en configurant des autorisations d’accès. Cela peut être important lorsque différents modèles sont utilisés pour produire des documents commerciaux pour différents domaines d’activité (zones fonctionnelles), et si vous voulez permettre à des utilisateurs spécifiques d’accéder à différents modèles à des fins de modification dans le module Gestion de document commercial.

Les autorisations d’accès au module Gestion de document commercial peuvent être définies dans **Configurateur des autorisations d’accès**. Seuls les utilisateurs suivants peuvent accéder à la page :

- Les utilisateurs ayant le rôle d’**Administrateur système**.
- Les utilisateurs affectés à un autre rôle configuré pour exécuter la fonction, **Configurer des autorisations pour pouvoir modifier les modèles de document commercial** (nom d’AOA **ERBDTemplatesSecurity**).

Procédez comme suit pour configurer l’accès aux autorisations du module Gestion de document commercial pour toutes les entités juridiques.

1. Connectez-vous en tant qu’utilisateur ayant accès à la page **Configurateur des autorisations d’accès**.
2. Accédez à **Administration d’organisation** \> **Gestion des états électroniques** \> **Gestion de document commercial** \> **Gérer les autorisations d’accès**.

    Notez la notification vous informant que l’utilisation des autorisations d’accès pour le module Gestion de document commercial n’est pas activée actuellement.

    ![Configurateur de la page des autorisations d’accès du module Gestion de document commercial.](./media/BDM-Overview-TemplatesAccess1.png)

    Avec ce paramètre, chaque utilisateur affecté à n’importe quel rôle de sécurité qui est configuré pour effectuer la tâche **Modèles du module Gestion de document commercial** (nom d’AOA **ERBDManageTemplates**) peut ouvrir l’espace de travail du module Gestion de document commercial et modifier n’importe quel modèle disponible.

    L’illustration suivante indique ce qui est disponible dans l’espace de travail du module Gestion de document commercial pour les utilisateurs affectés au rôle **Commis à la comptabilité client**. Avec le paramètre des autorisations d’accès actuel, l’utilisateur peut modifier les modèles de documents commerciaux provenant de différentes zones fonctionnelles notamment la facturation, la génération d’états de réglementation, et les paiements.

    ![Page de l’espace de travail de gestion des documents commerciaux pour le commis à la comptabilité client.](./media/BDM-Overview-TemplatesForAlice1.png)

3. Dans la page **Configurateur des autorisations d’accès**, sélectionnez **Paramètre des autorisations d’accès**.
4. Dans la boîte de dialogue **Paramètres des autorisations d’accès pour modifier des modèles**, activez l’option **Appliquer des autorisations d’accès configurées**.
5. Sélectionnez **OK** pour confirmer que les autorisations d’accès du module Gestion de document commercial ont été activées.

    ![Confirmer les autorisations d’accès du module Gestion de document commercial.](./media/BDM-Overview-TemplatesAccess2.png)

6. Sélectionnez **Ajouter** pour entrer un nouveau rôle métier pour lequel des autorisations d’accès aux modèles du module Gestion de document commercial doivent être configurées.
7. Dans la boîte de dialogue **Rôles de sécurité**, sélectionnez le rôle **Commis à la comptabilité client**, puis sélectionnez **OK** pour confirmer la sélection du rôle.
8. Dans l’onglet **Accéder aux autorisations par balise de configuration**, sélectionnez l’option **Nouveau**.
9. Dans le champ **Type de balise**, sélectionnez **Zone fonctionnelle**, puis dans le champ **ID**, sélectionnez **Facturation**.
10. Sélectionnez **Enregistrer** pour stocker les autorisations d’accès configurées pour le rôle sélectionné.

    Le paramètre actuel signifie que pour tout utilisateur affecté au rôle **Commis à la comptabilité client** et assumant la responsabilité, **Modèles du module Gestion de document commercial** (nom d’AOA **ERBDManageTemplates**), les modèles de configuration au format ER ayant la valeur **Facturation** définie pour la balise **Zone fonctionnelle** pourront être modifiés dans l’espace de travail du module Gestion de document commercial.

11. Basculez le volet **Informations associées** à partir du côté droit de la page actuelle. Le volet **Informations associées** montre comment les autorisations d’accès configurées sont appliquées, notamment quels modèles de configuration d’ER sont disponibles pour les utilisateurs affectés au rôle de **Commis à la comptabilité client**.

    ![Volet d’informations connexes sur la page Configurateur des autorisations d’accès.](./media/BDM-Overview-TemplatesAccess3.png)

12. Dans l’onglet **Accéder aux autorisations par configuration**, sélectionnez l’option **Ajouter**.
13. Dans la boîte de dialogue **Sélectionner une configuration**, marquez la configuration de format ER **État de déclaration d’échanges de biens**.
14. Sélectionnez **OK** pour confirmer l’entrée des configurations sélectionnées, puis sélectionnez **Enregistrer** pour enregistrer les autorisations d’accès configurées pour le rôle sélectionné.

Le paramètre actuel signifie que pour tout utilisateur affecté au rôle **Commis à la comptabilité client** et assumant la responsabilité, **Modèles du module Gestion de document commercial** (Nom d’AOA **ERBDManageTemplates**), les modèles suivants pourront être modifiés dans l’espace de travail du module Gestion de document commercial :

- Les modèles qui ont la valeur, **Facturation** pour la balise **Zone fonctionnelle**.
- Les modèles des configurations de format d’ER répertoriés sous l’onglet **Accéder aux autorisations par configuration** (modèles provenant de la configuration du format **État de déclaration d’échanges de biens** du domaine **Génération d’état statutaire** dans cet exemple).

![Organisateurs Autorisations d’accès sur la page Configurateur des autorisations d’accès.](./media/BDM-Overview-TemplatesAccess4.png)

L’illustration suivante indique ce qui est disponible dans l’espace de travail du module Gestion de document commercial pour un utilisateur affecté au rôle **Commis à la comptabilité client**. Avec le paramètre des autorisations d’accès du module Gestion de document commercial, l’utilisateur peut modifier les modèles de documents commerciaux à partir du domaine **Facturation** et de la configuration de format ER **État de déclaration d’échanges de biens**. Les modèles provenant du domaine **Paiements** ne sont pas disponibles pour le rôle **Commis à la comptabilité client**.

![Modification des modèles de document commercial sur la page de l’espace de travail Gestion des documents commerciaux.](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> Les règles **Accéder aux autorisations par configuration** sont enregistrées à l’aide de l’ID d’identification unique d’une configuration de format d’ER. Cela signifie que ces règles ne sont pas supprimées lorsqu’une configuration d’ER qui y fait référence est supprimée. Lorsque vous importez des configurations supprimées dans cette instance, ces règles s’y rapporteront de nouveau. Il n’est pas nécessaire de paramétrer les règles de nouveau une fois que les configurations supprimées sont importées de nouveau.

## <a name="use-business-document-management-to-edit-templates"></a>Utiliser le module Gestion de document commercial pour modifier les modèles

Les utilisateurs professionnels peuvent accéder aux modèles de document commercial pour apporter des modifications dans l’espace de travail du module Gestion de document commercial. Seuls les utilisateurs suivants peuvent accéder à l’espace de travail du module Gestion de document commercial :

- Les utilisateurs ayant le rôle d’**Administrateur système**.
- Les utilisateurs affectés à n’importe quel rôle qui est configuré pour exécuter la fonction, **Modèles du module Gestion de document commercial** (nom d’AOA **ERBDManageTemplates**).

La procédure suivante permet de modifier des modèles de facture financière dans l’espace de travail du module Gestion de document commercial. Avant de pouvoir exécuter cette procédure, vous devez avoir effectué toutes les procédures précédentes dans cette rubrique.

1. Connectez-vous en tant qu’utilisateur avec accès à l’espace de travail de gestion des documents commerciaux.
2. Ouvrez l’espace de travail du module Gestion de document commercial.

Quand la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** est désactivée dans l’espace de travail **Gestion des fonctionnalités**, la grille principale de l’espace de travail **Gestion des documents commerciaux** présente les modèles suivants :

- Les modèles appartenant à votre fournisseur de configuration de gestion des états électroniques (ER) (c’est-à-dire le fournisseur actuellement marqué comme actif dans l’espace de travail **Gestion des états électroniques**). Après avoir sélectionné l’un de ces modèles, vous pouvez sélectionner **Modifier le modèle** pour commencer ou continuer à le modifier.
- Modèles qui sont détenus par d’autres fournisseurs de configuration de gestion des états électroniques (ER). Après avoir sélectionné l’un de ces modèles, vous pouvez sélectionner **Nouveau document** pour en créer une copie qui appartient à votre fournisseur de configuration de gestion des états électroniques (ER), puis commencer à modifier la copie.

![Listes de modèles sur la page de l’espace de travail Gestion de documents commerciaux.](./media/BDM-Overview-EditingTemplate1.png)

L’onglet **Modèle** affiche le contenu du modèle sélectionné. Sélectionnez l’onglet **Détails** pour consulter les détails du modèle sélectionné ainsi que les détails d’une configuration de format d’ER dans lequel se trouve ce modèle. Notez que tous les modèles ont un statut **Publié**, et ne contiennent aucun détail dans la colonne **Révision**. Cela signifie que ces modèles n’ont pas encore été modifiés.

Quand la fonctionnalité **Expérience d’interface utilisateur de type bureau pour la gestion des documents commerciaux** est activée dans l’espace de travail **Gestion des fonctionnalités**, la grille principale dans l’espace de travail **Gestion des documents commerciaux** affiche des modèles détenus par votre fournisseur de configuration de la gestion des états électroniques (à savoir, le fournisseur actuellement marqué comme actif dans l’espace de travail **Gestion des états électroniques**). Après avoir sélectionné l’un de ces modèles, vous pouvez sélectionner **Modifier le modèle** pour commencer ou continuer à le modifier.

Pour travailler avec des modèles appartenant à d’autres fournisseurs de configuration de gestion des états électroniques (ER), sélectionnez **Nouveau document** pour créer une copie du modèle appartenant à votre fournisseur de gestion des états électroniques. Vous pouvez ensuite commencer à modifier la copie. Pour en savoir plus, voir [Nouvelle interface utilisateur de document dans la gestion des documents commerciaux](er-business-document-management-new-template-ui.md).

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>Lancer des modèles de modification détenus par votre fournisseur de configuration

1. Dans l’espace de travail du module Gestion de document commercial, sélectionnez le modèle **Format d’impression de chèque** dans la liste.
2. Sélectionnez l’onglet **Détails**.

![Page de l’espace de travail du module Gestion de document commercial, onglet Détails.](./media/BDM-Overview-EditingTemplate2.png)

L’option **Modifier le modèle** est disponible pour le modèle sélectionné. Cette option est toujours disponible pour un modèle dans une configuration de format ER détenue par le fournisseur de configuration ER actif (**Litware, Inc.** dans cet exemple). Lorsque **Modifier le modèle** est sélectionné, le modèle existant de la version temporaire de la configuration sous-jacente de format ER peut être modifié.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Lancer des modèles de modification détenus par d’autres fournisseurs

1. Dans l’espace de travail Gestion des documents commerciaux, sélectionnez le document que vous souhaitez utiliser comme modèle.

    ![Sélectionnez un document sur la page de l’espace de travail Gestion des documents commerciaux.](./media/BDM-Overview-EditingTemplate3.png)

2. Sélectionnez **Nouveau document** et dans le champ **Titre**, modifiez le titre du modèle modifiable si nécessaire. Le texte sera utilisé pour nommer la configuration du format ER qui est automatiquement créée. Notez que la version temporaire de cette configuration (**Copie d’État FTI client (GER)**) qui contient le modèle modifié sera automatiquement marquée pour exécuter ce format ER pour l’utilisateur actuel. En même temps, le modèle d’origine non modifié de la configuration du format ER de base sera utilisé pour exécuter ce format ER pour tout autre utilisateur.
3. Dans le champ **Nom**, modifiez le nom de la première révision du modèle modifiable qui sera créé automatiquement.
4. Dans le champ **Commentaire**, modifiez le commentaire de la révision créée automatiquement du modèle modifiable.
5. Cliquez sur **OK** pour confirmer le début du processus de modification.

![Confirmer le début du processus de modification pour créer un modèle.](./media/BDM-Overview-EditingTemplate4.png)

S’il n’y a aucun fournisseur, il vous sera proposé d’en créer un. S’il n’y a pas de fournisseur actif, il vous sera proposé d’en choisir un pour l’activer.

Pour créer un fournisseur, modifiez le nom du fournisseur dans le champ **Nom**, mettez à jour l’adresse Internet du nouveau fournisseur dans le champ **Adresse Internet** et sélectionnez **OK** pour confirmer.

   ![Créer un nouveau fournisseur dans BDM.](./media/bdm_create_provider.png)

Pour activer le fournisseur existant, choisissez le nom du fournisseur dans le champ **Fournisseur de configuration** et sélectionnez **OK** pour définir le fournisseur comme actif.

   ![Activer un fournisseur dans BDM.](./media/bdm_choose_provider.png)

> [!NOTE]
> Chaque modèle BDM fait référence au fournisseur en tant que l’auteur de la configuration. c’est pourquoi un fournisseur actif est requis pour le modèle.


L’option **Nouveau document** est toujours disponible pour un modèle dans une configuration au format ER fournie par un fournisseur actuel et un autre fournisseur (Microsoft dans cet exemple) qui n’a aucune révision. Le modèle modifié est ensuite stocké dans une nouvelle configuration de format ER qui est automatiquement générée.



### <a name="start-editing-a-template"></a>Commencer à modifier un modèle

1. Sélectionnez **Modifier document** dans le modèle sélectionné.
2. Dans le champ **Nom**, modifiez le nom de la première révision du modèle modifiable qui sera créé automatiquement.
3. Dans le champ **Commentaire**, modifiez la remarque de la révision créée automatiquement du modèle modifiable.

    ![Modifier un modèle sur la page de l’espace de travail Gestion de documents commerciaux.](./media/BDM-Overview-EditingTemplate5.png)

4. Cliquez sur **OK** pour confirmer le début du processus de modification.

La page **Éditeur de modèle BDM** s’ouvre. Le modèle sélectionné sera disponible pour la modification en ligne à l’aide de Microsoft 365.

![Page de l’éditeur de modèle du module Gestion de document commercial.](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-microsoft-365"></a><a name="EditInOffice365"></a>Modifier un modèle dans Microsoft 365

Vous pouvez modifier le modèle en utilisant Microsoft 365. Par exemple, dans Office online, faites passer la police des invites de champ de l’en-tête de modèle de **Normal** à **Gras**. Ces modifications sont automatiquement stockées dans le modèle modifiable qui est stocké dans le principal stockage du modèle (par défaut, dans le stockage d’objets blob Azure). La configuration s’adresse à la structure ER.

![Modification de la police en gras dans l’en-tête du modèle sur la page de l’éditeur de modèle de gestion de documents commerciaux.](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a><a name="EditInOfficeDesktopApp"></a>Modifier un modèle dans l’application de bureau Office

> [!NOTE]
> Cette fonction n’est disponible que lorsque le paramètre **Type de document SharePoint** est correctement configuré. Pour plus d’informations, voir [Configurer les paramètres](#SetupBdmParameters).

1. Sélectionnez l’option **Ouvrir dans l’application de bureau** pour modifier le modèle à l’aide de la fonctionnalité de l’application de bureau Office (Excel dans cet exemple). Le modèle modifiable est copié de la mémoire permanente vers le stockage temporaire configuré dans les paramètres du module Gestion de document commercial en tant que dossier SharePoint.
2. Confirmez que vous souhaitez ouvrir le modèle à partir du stockage de fichier temporaire dans l’application de bureau Office Excel.

    ![Modèle ouvert dans l’application de bureau Excel.](./media/BDM-Overview-EditingLayout3.png)

3. Modifiez le modèle. Par exemple, modifiez la police des invites de champ de l’en-tête de modèle en faisant passer la couleur de **Normal** à **Bleu**.

    ![Modifier la couleur de la police dans l’en-tête du modèle à l’aide de l’application de bureau Excel.](./media/BDM-Overview-EditingLayout4.png)

4. Sélectionnez **Enregistrer** dans l’application de bureau Excel pour enregistrer les modifications du modèle dans le stockage temporaire.

    ![Enregistrer les modifications dans la page de l’éditeur de modèle de gestion des documents commerciaux à l’aide de l’application de bureau Excel.](./media/BDM-Overview-EditingLayout5.png)

5. Fermez l’application de bureau Excel.
6. Sélectionnez **Synchroniser la copie enregistrée** pour synchroniser le stockage temporaire de modèle avec le stockage permanent de modèle.

> [!NOTE]
> La copie du modèle modifiable dans le stockage de fichier temporaire est conservée pour la session actuelle du modèle uniquement. Une fois que cette session est terminée et que la page **Éditeur de modèle BDM** est fermée, cette copie est alors supprimée. Si vous avez modifié le modèle dans le stockage de fichier temporaire et que vous n’avez pas sélectionné **Synchroniser la copie enregistrée**, lorsque vous essayez de fermer la page **Éditeur de modèle BDM**, un message demande si vous souhaitez enregistrer les modifications introduites. Sélectionnez **Oui** si vous souhaitez enregistrer les modifications apportées au modèle dans l’emplacement du fichier permanent.

### <a name="validate-a-template"></a>Contrôler un modèle

1. Dans la page **Éditeur de modèle BDM**, sélectionnez **Rechercher des problèmes** pour valider le modèle modifié par rapport à la configuration sous-jacente de format ER. Suivez les recommandations (le cas échéant) pour aligner le modèle avec la structure du format à partir de la configuration du format ER de base.
2. Sélectionnez **Afficher le format** pour afficher la structure actuelle du format à partir de la configuration du format ER de base qui doit être alignée avec le modèle pouvant être modifié. 
3. Sélectionnez **Masquer le format** pour fermer le volet.

    ![Page Éditeur de modèle BDM.](./media/BDM-Overview-EditingTemplate6.png)

4. Fermez la page **Éditeur de modèle BDM**.

Le modèle mis à jour est affiché dans l’onglet **Modèle** . Notez que le statut du modèle révisé est désormais **Brouillon** et la révision actuelle n’est plus vide. Cela signifie que le processus de modification de ce modèle a commencé.

![Afficher le modèle mis à jour sur la page de l’espace de travail Gestion de documents commerciaux.](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>Tester le modèle modifié 

1. Dans l’application, passez à la société, **USMF**.
2. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
3. Sélectionnez la facture **FTI-00000002**, puis sélectionnez **Gestion de l’impression**.
4. Sélectionnez le niveau de document **Module – Comptabilité client** \> **Documents** \> **Facture financière** \> **Document d’origine** pour spécifier la portée des factures aux fins de traitement.
5. Dans le champ **Format de l’état**, sélectionnez le format ER **Copie d’État FTI client (GER)** pour le niveau de document spécifié.

    ![Page Paramètre de gestion de l’impression.](./media/BDM-Overview-TestRun1.png)

6. Appuyez sur **Échap** pour fermer la page actuelle.
7. Sélectionnez **Imprimer**, puis **Sélectionné**.
8. Téléchargez le document et ouvrez-le à l’aide de l’application de bureau Excel.

![Page Factures financières.](./media/BDM-Overview-TestRun2.png)

Le modèle révisé est utilisé pour générer l’état de facture financière pour l’article sélectionné. Pour analyser la manière dont cet état est affecté par les modifications apportées au modèle, vous pouvez exécuter cet état dans une session de l’application immédiatement après avoir modifié le modèle dans une autre session de l’application.

### <a name="create-an-alternative-template-revision"></a>Créer une révision du modèle de remplacement

1. Ouvrez la page **Éditeur de modèle BDM** et sélectionnez le modèle **Copie d’État FTI client (GER)**.
2. Dans l’onglet **Révisions**, sélectionnez **Nouveau**.
3. Si nécessaire, dans le champ **Nom**, modifiez le nom de la deuxième révision et basez-le sur la première révision active.
4. Si nécessaire, dans le champ **Commentaire**, modifiez la remarque de la révision créée automatiquement du modèle modifiable.

    ![Créer des révisions sur le modèle mis à jour sur la page de l’espace de travail Gestion de documents commerciaux.](./media/BDM-Overview-AddRevision.png)

    Vous avez créé une révision de votre modèle qui a été enregistrée dans le stockage du modèle permanent. Vous pouvez désormais continuer à modifier le modèle de la deuxième révision actuellement sélectionné comme actif.

5. Sélectionnez la première révision, puis sélectionnez **Activer**. Vous pouvez sélectionner une autre révision comme active si à tout moment vous souhaitez revenir à la révision du modèle.
6. Sélectionnez la deuxième révision, puis sélectionnez **Supprimer**.
7. Sélectionnez **OK** pour confirmer la suppression de la révision sélectionnée. Vous pouvez supprimer n’importe quelle révision inactive si elle n’est plus nécessaire.

### <a name="delete-a-modified-template"></a>Supprimer un modèle modifié

1. Dans la page **Éditeur de modèle BDM**, sélectionnez l’onglet **Modèle**.
2. Sélectionnez **Supprimer**.
3. Si vous sélectionnez **OK** pour confirmer la suppression, le format ER **Copie d’État FTI client (GER)** avec le modèle modifié est alors supprimé. Sélectionnez **Annuler** pour explorer d’autres options.

### <a name="revoke-changes-of-template"></a>Annuler les modifications du modèle

Lorsque vous modifiez le modèle provenant d’un format ER qui appartient au fournisseur actif, vous avez l’option d’annuler les modifications introduites pour le modèle.

![Rejeter les modifications sur le modèle mis à jour sur la page de l’espace de travail Gestion de documents commerciaux.](./media/BDM-Overview-RevokeChanges.png)

1. Dans la page **Éditeur de modèle BDM**, sélectionnez l’onglet **Modèle**.
2. Sélectionnez **Annuler**.
3. Si vous sélectionnez **OK** pour annuler les modifications introduites pour le modèle, le modèle modifié est alors remplacé par le modèle d’origine et toutes les modifications sont supprimées. Lorsque vous annulez des modifications du modèle, vous pouvez supprimer le modèle. Sélectionnez **Annuler** pour explorer d’autres options.

### <a name="publish-a-modified-template"></a>Publier un modèle modifié

1. Dans la page **Éditeur de modèle BDM**, sur l’onglet **Modèle**, sélectionnez **Publier**.
2. Si vous sélectionnez **Ajouter** pour confirmer la publication, la version temporaire du format ER dérivé **Copie d’État FTI client (GER)** qui contient le modèle modifié est marquée comme terminée. Le modèle modifié devient disponible pour d’autres utilisateurs. Les versions terminées de ce format ER conserveront uniquement la dernière révision active de votre modèle. Les autres révisions seront supprimées. Sélectionnez **Annuler** pour explorer d’autres options.

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="i-selected-edit-document-but-instead-of-going-to-the-bdm-template-editor-page-in-finance-i-was-sent-to-the-microsoft-365-webpage"></a>J’ai sélectionné Modifier document, mais plutôt que d’ouvrir la page Éditeur de modèle BDM dans Finance, je suis arrivé sur la page web de Microsoft 365.

Il s’agit d’un problème connu avec la redirection Microsoft 365. Cela se produit lorsque vous vous connectez à Microsoft 365 pour la première fois. Pour contourner ce problème, sélectionnez **Retour** dans votre navigateur pour revenir à la page précédente.

### <a name="i-understand-how-to-edit-a-template-by-using-microsoft-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-and-adjust-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-use-the-office-desktop-application-in-the-same-way"></a>Je sais comment modifier un modèle à l’aide de Microsoft 365 dans la première session d’application et utiliser le modèle dans la deuxième session d’application, puis modifier le modèle pour voir comment mes modifications affectent le document commercial généré. Puis-je utiliser l’application de bureau Office de la même manière ?

Oui, vous pouvez. Dans la première session de l’application, sélectionnez **Ouvrir dans l’application de bureau**. Votre modèle sera stocké dans le stockage de fichier temporaire et ouvert dans l’application de bureau Office. Procédez ensuite comme suit pour prévisualiser les modifications apportées au modèle dans le document commercial généré :

1. Apportez des modifications dans le modèle à l’aide de l’application de bureau Office.
2. Sélectionnez **Enregistrer** dans l’application de bureau Office.
3. Dans la page **Éditeur de modèle BDM** de la première session de l’application, sélectionnez **Synchroniser la copie enregistrée**.
4. Exécutez ce format ER de modèle dans la deuxième session de l’application.

### <a name="when-i-select-open-in-desktop-app-i-receive-the-following-error-message-value-cannot-be-null-parameter-name-externalid-how-do-i-work-around-this-issue"></a>Lorsque je sélectionne Ouvrir dans l’application de bureau, je reçois le message d’erreur suivant : « La valeur ne peut pas être nulle. Nom du paramètre : externalId. » Comment résoudre ce problème ?

Vous êtes probablement connecté à l’instance actuelle de l’application du domaine Azure AD qui diffère du domaine Azure AD utilisé pour déployer cette instance. Comme le service SharePoint, qui permet d’enregistrer des modèles pour les rendre disponibles pour modification à l’aide des applications de bureau Office, appartient au même domaine, nous n’avons aucune autorisation pour accéder au service SharePoint. Pour résoudre ce problème, connectez-vous à l’instance actuelle en utilisant les informations d’identification d’un utilisateur ayant le domaine Azure AD approprié.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques (ER)](general-electronic-reporting.md)

[ER Concevoir une configuration pour générer des états au format OPENXML (novembre 2016)](tasks/er-design-reports-openxml-2016-11.md)

[Créer des configurations de gestion d’états électroniques pour générer des états au format Word](tasks/er-design-configuration-word-2016-11.md)

[Intégrer des images et des formes dans les documents que vous générez ER à l’aide de la gestion des états électroniques (ER)](electronic-reporting-embed-images-shapes.md)

[Configurer la gestion des états électroniques pour extraire les données dans Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)

## <a name="list-of-er-configurations-that-have-been-released-in-finance-to-support-configurable-business-documents"></a><a name="list-of-configurations-cbd"></a>Liste des configurations de gestion des états électroniques qui ont été publiées dans Finance pour prendre en charge les documents commerciaux configurables

La [liste](general-electronic-reporting.md#list-of-configurations) des configurations de gestion des états électroniques pour Finance est constamment mis à jour. Ouvrez le [référentiel global](er-download-configurations-global-repo.md) pour consulter la liste des configurations de gestion des états électroniques actuellement prises en charge. Vous pouvez [filtrer](../../../finance/localizations/enhanced-filtering-global-repo.md) le référentiel global pour examiner la liste des configurations de gestion des états électroniques utilisées pour prendre en charge les documents commerciaux configurables.

![Filtrage du contenu du référentiel global sur la page Référentiel de configuration.](./media/bdm-overview-filterglobalrepo.gif)

Le tableau suivant présente la liste des configurations de gestion des états électroniques prenant en charge les documents commerciaux configurables et qui ont été publiées dans Finance jusqu’en décembre 2020.

| Configuration de modèle de données    | Configurations de format                           |
|-----------------------------|-------------------------------------------------|
| Modèle de feuille de chargement        | Feuille de chargement (Excel)                          |
|                             | Feuille de chargement (Word)                           |
| Modèle de certificat d’origine | Certificat d’origine (Excel)                   |
|                             | Certificat d’origine (Word)                    |
| Modèle de facture               | Note de débit et de crédit client (Excel)          |
|                             | Note de débit et de crédit client (Word)           |
|                             | Facture financière (Excel)                       |
|                             | Facture financière (Excel) (BH)                  |
|                             | Facture financière (FR) (Excel)                  |
|                             | Facture financière (LT) (Excel)                  |
|                             | Facture financière (LV) (Excel)                  |
|                             | Facture financière (PL) (Excel)                  |
|                             | Facture financière (CZ) (Excel)                  |
|                             | Facture financière (EE) (Excel)                  |
|                             | Facture financière (HU) (Excel)                  |
|                             | Facture financière (TH) (Excel)                  |
|                             | Page Facture financière (Word)                        |
|                             | Éléments de ligne de contrat de projet (Excel)             |
|                             | Éléments de ligne de contrat de projet (CZ) (Excel)        |
|                             | Éléments de ligne de contrat de projet (Excel) (BH)        |
|                             | Éléments de ligne de contrat de projet (HU) (Excel)        |
|                             | Éléments de ligne de contrat de projet (LT) (Excel)        |
|                             | Éléments de ligne de contrat de projet (PL) (Excel)        |
|                             | Éléments de ligne de contrat de projet (Word)              |
|                             | Version de fidélisation des clients du projet (Excel)      |
|                             | Version de fidélisation des clients du projet (CZ) (Excel) |
|                             | Version de fidélisation des clients du projet (HU) (Excel) |
|                             | Version de fidélisation des clients du projet (LT) (Excel) |
|                             | Version de fidélisation des clients du projet (PL) (Excel) |
|                             | Version de fidélisation des clients du projet (TH) (Excel) |
|                             | Version de fidélisation des clients du projet (Word)       |
|                             | Facture de projet (Excel)                         |
|                             | Facture de projet (Word)                          |
|                             | Facture de projet (AE) (Excel)                    |
|                             | Facture de projet (CZ) (Excel)                    |
|                             | Facture de projet (Excel) (BH)                    |
|                             | Facture de projet (HU) (Excel)                    |
|                             | Facture de projet (JP) (Excel)                    |
|                             | Facture de projet (LT) (Excel)                    |
|                             | Facture de projet (PL) (Excel)                    |
|                             | Facture de projet (TH) (Excel)                    |
|                             | Facture de projet complète (MY) (Excel)               |
|                             | Facture de projet simple (MY) (Excel)             |
|                             | Facture de gestion projet (Excel)                  |
|                             | Facture de gestion projet (CZ) (Excel)             |
|                             | Facture de gestion projet (Excel) (BH)             |
|                             | Facture de gestion projet (HU) (Excel)             |
|                             | Facture de gestion projet (JP) (Excel)             |
|                             | Facture de gestion projet (LT) (Excel)             |
|                             | Facture de gestion projet (PL) (Excel)             |
|                             | Facture de gestion projet (Word)                   |
|                             | Facture d’acompte d’achat (Excel)                |
|                             | Facture d’acompte d’achat (Word)                 |
|                             | Facture d’acompte de vente (Excel)                   |
|                             | Facture d’acompte de vente (Word)                    |
|                             | Facture d’acompte de vente (PL) (Excel)              |
|                             | Facture de vente (Excel)                           |
|                             | Facture de vente (Excel) (BH)                      |
|                             | Facture de vente (Excel) (CZ)                      |
|                             | Facture de vente (Excel) (EE)                      |
|                             | Facture de vente (Excel) (FR)                      |
|                             | Facture de vente (Excel) (HU)                      |
|                             | Facture de vente (Excel) (IN)                      |
|                             | Facture de vente (Excel) (LT)                      |
|                             | Facture de vente (Excel) (LV)                      |
|                             | Facture de vente (Excel) (PL)                      |
|                             | Facture de vente (Excel) (TH)                      |
|                             | Facture de vente (Word)                            |
|                             | Facture commerciale TMS (Excel)                  |
|                             | Facture commerciale TMS (Word)                   |
|                             | Document à la facture fournisseur (Excel)                 |
|                             | Document à la facture fournisseur (CZ) (Excel)            |
|                             | Document à la facture fournisseur (HU) (Excel)            |
|                             | Document à la facture fournisseur (IN) (Excel)            |
|                             | Document à la facture fournisseur (LT) (Excel)            |
|                             | Document à la facture fournisseur (LV) (Excel)            |
|                             | Document à la facture fournisseur (MY) (Excel)            |
|                             | Document à la facture fournisseur (Word)                  |
| Modèle de commande                 | Confirmation de contrat (Excel)                  |
|                             | Confirmation de contrat (Word)                   |
|                             | Confirmation de contrat d’achat (Excel)         |
|                             | Confirmation de contrat d’achat (Word)          |
|                             | Commande fournisseur (Excel)                          |
|                             | Commande fournisseur (CZ) (Excel)                     |
|                             | Recherche de commande fournisseur (CZ) (Excel)             |
|                             | Commande fournisseur (HU) (Excel)                     |
|                             | Recherche de commande fournisseur (HU) (Excel)             |
|                             | Commande fournisseur (Word)                           |
|                             | Recherche de commande fournisseur (Excel)                  |
|                             | Recherche de commande fournisseur (Word)                   |
|                             | Confirmation de commande client (Excel)                |
|                             | Confirmation de commande client (CZ) (Excel)           |
|                             | Confirmation de commande client (HU) (Excel)           |
|                             | Confirmation de commande client (Word)                 |
| Modèle de liste d’emballage          | Contenu du conteneur (Excel)                      |
|                             | Contenu du conteneur (Word)                       |
|                             | Charger la liste (Excel)                               |
|                             | Charger la liste (Word)                                |
|                             | Prélèvement (Excel)                            |
|                             | Prélèvement (CZ) (Excel)                       |
|                             | Prélèvements (Word)                             |
|                             | Prélèvements de production (Excel)                    |
|                             | Prélèvements de production (Word)                     |
|                             | Prélèvements d’expédition pour le chargement (Excel)             |
|                             | Prélèvements d’expédition pour le chargement (Word)              |
|                             | Prélèvements d’expédition pour l’expédition (Excel)         |
|                             | Prélèvements d’expédition pour l’expédition (Word)          |
|                             | Prélèvements d’expédition pour la vague (Excel)             |
|                             | Prélèvements d’expédition pour la vague (Word)              |
| Modèle de paiement               | Conseil de paiement client (Excel)                 |
|                             | Conseil de paiement client (Word)                  |
|                             | Conseil de paiement fournisseur (Excel)                   |
|                             | Conseil de paiement fournisseur (Word)                    |
| Modèle de devis             | Devis de projet (Excel)                       |
|                             | Devis de projet (Word)                        |
|                             | Appel d’offre (Excel)                   |
|                             | Appel d’offre (Acceptation) (Excel)          |
|                             | Appel d’offre (Acceptation) (Word)           |
|                             | Appel d’offre (Rejet) (Excel)          |
|                             | Appel d’offre (Rejet) (Word)           |
|                             | Appel d’offre (Retour) (Excel)          |
|                             | Appel d’offre (Retour) (Word)           |
|                             | Appel d’offre (Word)                    |
|                             | Lignes du devis de vente (Excel)                         |
|                             | Lignes du devis de vente (CZ) (Excel)                    |
|                             | Lignes du devis de vente (HU) (Excel)                    |
|                             | Lignes du devis de vente (Word)                          |
|                             | Confirmation des lignes du devis de vente (Excel)            |
|                             | Confirmation des lignes du devis de vente (Word)             |
| Modèle de rapprochement        | Relevé de compte client, ext. (Excel)             |
|                             | Relevé de compte client, ext. (CN) (Excel)        |
|                             | Relevé de compte client, ext. (Word)              |
|                             | Relevé de compte client, France (Excel)          |
| Modèle de rappel              | Note de lettre de relance (Excel)                  |
|                             | Note de lettre de relance (CN) (Excel)             |
|                             | Note de lettre de relance (Word)                   |
|                             | Note d’intérêt client (Excel)                  |
|                             | Note d’intérêt client (Word)                   |
| Modèle de bordereau d’expédition               | Charger l’offre (Excel)                             |
|                             | Charger l’offre (Word)                              |
|                             | Bon de livraison de commande fournisseur (Excel)             |
|                             | Bon de livraison de commande fournisseur (CZ) (Excel)        |
|                             | Bon de livraison de commande fournisseur (Word)              |
|                             | Gamme (Excel)                                   |
|                             | Gamme (Word)                                    |
|                             | Bon de livraison de commande client (Excel)                |
|                             | Bon de livraison de commande client (CZ) (Excel)           |
|                             | Bon de livraison de commande client (LT) (Excel)           |
|                             | Bon de livraison de commande client (PL) (Excel)           |
|                             | Bon de livraison de commande client (Word)                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
