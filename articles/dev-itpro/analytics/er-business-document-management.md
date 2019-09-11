---
title: Vue d'ensemble du module Gestion de document commercial
description: Cette rubrique fournit des informations sur l'utilisation de la fonctionnalité Gestion de document commercial de la structure de gestion des états électroniques (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d756436373b10f9538788a3292135a73c9c45d04
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873151"
---
# <a name="business-document-management-overview"></a>Vue d'ensemble du module Gestion de document commercial

Les utilisateurs professionnels utilisent la [structure de gestion des états électroniques (ER)](general-electronic-reporting.md) pour configurer des formats pour les documents sortants conformément aux obligations légales de différents pays/régions. Ils peuvent également définir le flux de données pour spécifier quelles données d'application placer dans les documents générés. La structure de gestion des états électroniques génère des documents sortants dans des formats Microsoft Office (des classeurs Excel ou des documents Word) à l'aide de modèles prédéfinis. Les modèles sont renseignés avec les données requises conformément au flux de données configuré pendant la génération des documents requis. Chaque format configuré peut être publié dans le cadre d'une solution de gestion des états électroniques pour générer les documents sortants spécifiques. Cela est représenté par une configuration de format ER qui peut contenir des modèles qui vous permettent de générer différents documents sortants. Les utilisateurs professionnels peuvent utiliser cette structure pour gérer les documents commerciaux requis.

Le module **Gestion de document commercial** repose sur la structure d'ER et permet aux utilisateurs d'entreprise de modifier des modèles de documents commerciaux à l'aide du service Microsoft Office 365 ou de l'application de bureau Microsoft Office appropriée. Parmi les modifications apportées aux documents on trouve la modification des conceptions de documents commerciaux et l'ajout des espaces réservés pour les données supplémentaires dans Dynamics 365 for Finance and Operations sans modifier le code source ni faire de nouveaux déploiements. Aucune connaissance de la structure d'ER n'est nécessaire pour la mise à jour de modèles de documents commerciaux.

> [!NOTE]
> Notez que le module Gestion de document commercial permet de modifier les modèles utilisés pour produire des documents commerciaux, tels que les commandes, les factures, etc. Même si un modèle a été modifié et qu'une nouvelle version a été émise, cette version est utilisée pour générer les documents commerciaux requis. Le module Gestion de document commercial ne permet pas de modifier les documents commerciaux déjà générés.

## <a name="supported-deployments"></a>Déploiements pris en charge

Actuellement, la fonctionnalité Gestion de document commercial est implémentée uniquement pour les déploiements Cloud. Si cette fonctionnalité est indispensable pour un déploiement sur site, indiquez-le en laissant un commentaire sur le site [Idées](https://experience.dynamics.com/ideas/).

## <a name="supported-microsoft-office-applications"></a>Applications Microsoft Office prises en charge

Pour utiliser le module Gestion de document commercial pour modifier les modèles dans des formats Excel ou Word à l'aide des applications de bureau Microsoft Office, Microsoft Office 2010 ou une version ultérieure doit être installé. Cela est pris en charge dans le Cloud et le déploiement sur site de Finance and Operations.

## <a name="business-document-availability"></a>Disponibilité de la gestion de document commercial

Les états suivants, avec des modèles Excel, seront disponibles avec le lancement de la version préliminaire publique :

**Comptabilité client** (août 2019)

- Facture d'acompte de vente
- Bon de livraison de commande client

**Comptabilité fournisseur** (août 2019)

- Facture d'acompte d'achat
- Commande fournisseur
- Bon de livraison de commande fournisseur

Des états supplémentaires seront disponibles. Des notifications spécifiques sur les états supplémentaires seront envoyées séparément. 

La liste complète de tous les états prévus pour le lancement d'octobre 2019 figure dans [Génération d'états de documents commerciaux configurables dans Word et Excel](https://docs.microsoft.com/en-us/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details).

# <a name="example-enable-configure-and-use-business-document-management"></a>Exemple : activer, configurer, puis utiliser le module Gestion de document commercial

Pour en savoir plus sur cette fonctionnalité, exécutez l'exemple décrit dans cette rubrique.

## <a name="configure-er-parameters"></a>Configurer les paramètres ER

Comme le module Gestion de document commercial repose sur la structure de gestion des états électroniques, vous devez configurer les paramètres des états électroniques pour commencer à utiliser ce module. Pour ce faire, vous devez définir les paramètres des états électroniques comme décrit dans [Configurer la structure ER](electronic-reporting-er-configure-parameters.md). Vous devez également ajouter un nouveau fournisseur de configuration comme décrit dans [Créer des fournisseurs de configuration et les marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Espace de travail ER](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>Importer des solutions d'ER

Vous devez importer les configurations d'ER contenant les modèles de documents commerciaux dans l'instance Finance and Operations actuelle. Téléchargez et enregistrez localement les fichiers suivants pour exécuter cette procédure.

**Exemple de solution de facturation de client d'ER**

| **Fichier**                                  | **Contenu**                                |
|-------------------------------------------|--------------------------------------------|
| Customer invoicing model.version.2.xml    | [Configuration de modèle de données ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Customer FTI report (GER).version.2.3.xml | [Configurations de format ER de facture financière](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Exemple de solution de paiement par chèque d'ER**

| **Fichier**                                  | **Contenu**                                |
|-------------------------------------------|--------------------------------------------|
| Model for cheques.version.10.xml          | [Configuration de modèle de données ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Cheques printing format.version.10.9.xml  | [Configuration du format ER de paiement par chèque](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Exemple de solution de commerce extérieur d'ER**

| **Fichier**                                  | **Contenu**                                |
|-------------------------------------------|--------------------------------------------|
| Intrastat model.version.1.xml             | [Configuration de modèle de données ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Intrastat report.version.1.9.xml          | [Configuration du format ER d'état de contrôle de déclaration d'échanges de biens](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Procédez comme suit pour importer chaque fichier. Importez la configuration de *modèle de données* d'ER de chaque solution d'ER dans les tables ci-dessus avant d'importer la configuration de *format* d'ER correspondante.

1. Ouvrez la page **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2. Sélectionnez **Échanger** en haut de la page.
3. Sélectionnez **Charger depuis le fichier XML**.
4. Sélectionnez **Parcourir** pour charger le fichier XML requis.
5. Sélectionnez **OK** pour confirmer l'importation de la configuration.

![Page Configurations d'ER](./media/BDM-Overview-ERSolutions.png)

Pour plus d'informations sur l'importation des configurations d'ER, voir [Gérer le cycle de vie de la configuration des états électroniques](general-electronic-reporting-manage-configuration-lifecycle.md).

## <a name="enable-business-document-management"></a>Activer le module Gestion de document commercial

Pour démarrer le module Gestion de document commercial, vous devez ouvrir l'espace de travail **Gestion des fonctions** et activer la fonctionnalité **Gestion de document commercial**.

Procédez comme suit pour activer la fonctionnalité Gestion de document commercial pour toutes les entités juridiques.

1. Ouvrez l'espace de travail **Gestion des fonctionnalités**.
2. Dans l'onglet **Nouveau**, sélectionnez la fonctionnalité **Gestion de document commercial** dans la liste.
3. Sélectionnez **Activer maintenant** pour activer la fonctionnalité sélectionnée.
4. Actualisez la page pour accéder à la nouvelle fonctionnalité.

![Espace de travail Gestion des fonctionnalités](./media/BDM-Overview-FMEnabling.png)

Pour plus d'informations sur l'activation de nouvelles fonctionnalités, voir [Présentation de la gestion des fonctionnalités](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-parameters"></a>Configurer les paramètres

Utilisez les informations des sections suivantes pour paramétrer les paramètres de base pour le module Gestion de document commercial.

### <a name="prerequisites-for-parameter-setup"></a>Conditions requises pour le paramétrage
Avant de paramétrer le module Gestion de document commercial, vous devez paramétrer le type de document requis dans la structure de gestion des documents. Ce type de document est utilisé pour spécifier un stockage temporaire de documents dans les formats Office (Excel et Word) utilisés en tant que modèles pour les états ER. Le modèle de stockage temporaire peut être modifié à l'aide des applications de bureau Office.

Pour ce type de document, les valeurs d'attribut suivantes doivent être sélectionnées.

| **Nom d'attribut**  | **Valeur d'attribut**   |
|---------------------|-----------------------|
| Classe               | Fichier joint           |
| Regrouper               | Fichier                  |
| Emplacement            | SharePoint            |

Pour plus d'informations sur la définition des paramètres et des types de document requis pour le module Gestion de document commercial, voir [Configurer la gestion des documents](../../fin-and-ops/organization-administration/configure-document-management.md).

![Paramétrer un type de document pour la gestion des documents](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a>Définir les paramètres

Les paramètres de base du module Gestion de document commercial peuvent être définis sur la page **Paramètres de document commercial**. Seuls certains utilisateurs peuvent accéder à la page. Notamment :

- Les utilisateurs ayant le rôle d'**Administrateur système**.
- Les utilisateurs affectés à n'importe quel rôle qui est configuré pour exécuter la fonction, **Tenir à jour les paramètres du module Gestion de document commercial** (nom d'AOA **ERBDMaintainParameters**).

Suivez les procédures suivantes pour définir les paramètres de base pour toutes vos entités juridiques.

1. Connectez-vous à Finance and Operations en tant qu'utilisateur avec accès à la page **Paramètres de document commercial**.
2. Accédez à **Administration d'organisation** \> **Gestion des états électroniques** \> **Gestion de document commercial** \> **Paramètres de document commercial**.
3.  Sur la page **Paramètres de document commercial**, sous l'onglet **Documents joints**, dans le champ **Type de document SharePoint**, définissez le type de document à utiliser pour stocker temporairement des modèles dans des formats Office lorsqu'ils sont modifiés à l'aide des applications de bureau Office. 

> [!NOTE]
> Seuls les types de documents configurés à l'aide d'un emplacement SharePoint sont disponibles pour ce paramètre.

![Définition des paramètres du module Gestion de document commercial](./media/BDM-Overview-BDMSetting.png)

Le type de document sélectionné est spécifique à la société et sera utilisé lorsque l'utilisateur travaille avec le module Gestion de document commercial dans la société pour laquelle le type de document sélectionné est configuré. Lorsque l'utilisateur travaille avec le module Gestion de document commercial dans une autre société, le même type de document sélectionné est utilisé s'il a été configuré pour cette société. Lorsqu'un type de document a été configuré, il sera utilisé à la place de celui sélectionné dans le champ **Type de document SharePoint**.

## <a name="configure-access-permissions"></a>Configurer les autorisations d'accès

Par défaut, lorsque l'accès aux autorisations du module Gestion de document commercial n'est pas activé, chaque utilisateur qui a accès à l'espace de travail de ce module voit tous les modèles de solution d'ER disponibles dans Finance and Operations. L'espace de travail du module Gestion de document commercial n'affiche que les modèles résidant dans les configurations de format ER et marqués par une balise **Type de document commercial**.

![Page Configurations d'ER](./media/BDM-Overview-ERFormatTags.png)

La liste des modèles disponibles dans l'espace de travail du module Gestion de document commercial peut être restreinte en configurant des autorisations d'accès. Cela peut être important lorsque différents modèles sont utilisés pour produire des documents commerciaux pour différents domaines d'activité (zones fonctionnelles), et si vous voulez permettre à des utilisateurs spécifiques d'accéder à différents modèles à des fins de modification dans le module Gestion de document commercial.

Les autorisations d'accès au module Gestion de document commercial peuvent être définies dans **Configurateur des autorisations d'accès**. Seuls les utilisateurs suivants peuvent accéder à la page :

- Les utilisateurs ayant le rôle d'**Administrateur système**.
- Les utilisateurs affectés à un autre rôle configuré pour exécuter la fonction, **Configurer des autorisations pour pouvoir modifier les modèles de document commercial** (nom d'AOA **ERBDTemplatesSecurity**).

Procédez comme suit pour configurer l'accès aux autorisations du module Gestion de document commercial pour toutes les entités juridiques.

1. Connectez-vous à Finance and Operations en tant qu'utilisateur ayant accès à la page **Configurateur des autorisations d'accès**.
2. Accédez à **Administration d'organisation** \> **Gestion des états électroniques** \> **Gestion de document commercial** \> **Gérer les autorisations d'accès**.

Notez la notification vous informant que l'utilisation des autorisations d'accès pour le module Gestion de document commercial n'est pas activée actuellement.

![Configurateur de la page des autorisations d'accès du module Gestion de document commercial](./media/BDM-Overview-TemplatesAccess1.png)

Avec ce paramètre, chaque utilisateur affecté à n'importe quel rôle de sécurité qui est configuré pour effectuer la tâche **Modèles du module Gestion de document commercial** (nom d'AOA **ERBDManageTemplates**) peut ouvrir l'espace de travail du module Gestion de document commercial et modifier n'importe quel modèle disponible dans Finance and Operations.

L'illustration suivante indique ce qui est disponible dans l'espace de travail du module Gestion de document commercial pour les utilisateurs affectés au rôle **Commis à la comptabilité client**. Avec le paramètre des autorisations d'accès actuel, l'utilisateur peut modifier les modèles de documents commerciaux provenant de différentes zones fonctionnelles notamment la facturation, la génération d'états de réglementation, et les paiements.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-TemplatesForAlice1.png)

3. Dans la page **Configurateur des autorisations d'accès**, sélectionnez **Paramètre des autorisations d'accès**.
4. Dans la boîte de dialogue **Paramètres des autorisations d'accès pour modifier des modèles**, activez l'option **Appliquer des autorisations d'accès configurées**.
5. Sélectionnez **OK** pour confirmer que les autorisations d'accès du module Gestion de document commercial ont été activées.

![Configuration de la page des autorisations d'accès du module Gestion de document commercial](./media/BDM-Overview-TemplatesAccess2.png)

6. Sélectionnez **Ajouter** pour entrer un nouveau rôle métier pour lequel des autorisations d'accès aux modèles du module Gestion de document commercial doivent être configurées.
7. Dans la boîte de dialogue **Rôles de sécurité**, sélectionnez le rôle **Commis à la comptabilité client**, puis sélectionnez **OK** pour confirmer la sélection du rôle.
8. Dans l'onglet **Accéder aux autorisations par balise de configuration**, sélectionnez l'option **Nouveau**.
9. Dans le champ **Type de balise**, sélectionnez **Zone fonctionnelle**, puis dans le champ **ID**, sélectionnez **Facturation**.
10. Sélectionnez **Enregistrer** pour stocker les autorisations d'accès configurées pour le rôle sélectionné.

  Le paramètre actuel signifie que pour tout utilisateur affecté au rôle **Commis à la comptabilité client** et assumant la responsabilité, **Modèles du module Gestion de document commercial** (nom d'AOA **ERBDManageTemplates**), les modèles de configuration au format ER ayant la valeur **Facturation** définie pour la balise **Zone fonctionnelle** pourront être modifiés dans l'espace de travail du module Gestion de document commercial.

11. Basculez le volet **Informations associées** à partir du côté droit de la page actuelle. Le volet **Informations associées** montre comment les autorisations d'accès configurées sont appliquées, notamment quels modèles de configuration d'ER sont disponibles pour les utilisateurs affectés au rôle de **Commis à la comptabilité client**.

![Configuration de la page des autorisations d'accès du module Gestion de document commercial](./media/BDM-Overview-TemplatesAccess3.png)

12. Dans l'onglet **Accéder aux autorisations par configuration**, sélectionnez l'option **Ajouter**.
13. Dans la boîte de dialogue **Sélectionner une configuration**, marquez la configuration de format ER **État de déclaration d'échanges de biens**.
14. Sélectionnez **OK** pour confirmer l'entrée des configurations sélectionnées, puis sélectionnez **Enregistrer** pour enregistrer les autorisations d'accès configurées pour le rôle sélectionné.

Le paramètre actuel signifie que pour tout utilisateur affecté au rôle **Commis à la comptabilité client** et assumant la responsabilité, **Modèles du module Gestion de document commercial** (Nom d'AOA **ERBDManageTemplates**), les modèles suivants pourront être modifiés dans l'espace de travail du module Gestion de document commercial :

- Les modèles qui ont la valeur, **Facturation** pour la balise **Zone fonctionnelle**.
- Les modèles des configurations de format d'ER répertoriés sous l'onglet **Accéder aux autorisations par configuration** (modèles provenant de la configuration du format **État de déclaration d'échanges de biens** du domaine **Génération d'état statutaire** dans cet exemple).

![Configuration de la page des autorisations d'accès du module Gestion de document commercial](./media/BDM-Overview-TemplatesAccess4.png)

L'illustration suivante indique ce qui est disponible dans l'espace de travail du module Gestion de document commercial pour un utilisateur affecté au rôle **Commis à la comptabilité client**. Avec le paramètre des autorisations d'accès du module Gestion de document commercial, l'utilisateur peut modifier les modèles de documents commerciaux à partir du domaine **Facturation** et de la configuration de format ER **État de déclaration d'échanges de biens**. Les modèles provenant du domaine **Paiements** ne sont pas disponibles pour le rôle **Commis à la comptabilité client**.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> Les règles **Accéder aux autorisations par configuration** sont enregistrées à l'aide de l'ID d'identification unique d'une configuration de format d'ER. Cela signifie que ces règles ne sont pas supprimées lorsqu'une configuration d'ER qui y fait référence est supprimée. Lorsque vous importez des configurations supprimées dans cette instance de Finance and Operations, ces règles s'y rapporteront de nouveau. Il n'est pas nécessaire de paramétrer les règles de nouveau une fois que les configurations supprimées sont importées de nouveau.

## <a name="use-business-document-management-to-edit-templates"></a>Utiliser le module Gestion de document commercial pour modifier les modèles

Les utilisateurs professionnels peuvent accéder aux modèles de document commercial pour apporter des modifications dans l'espace de travail du module Gestion de document commercial. Seuls les utilisateurs suivants peuvent accéder à l'espace de travail du module Gestion de document commercial :

- Les utilisateurs ayant le rôle d'**Administrateur système**.
- Les utilisateurs affectés à n'importe quel rôle qui est configuré pour exécuter la fonction, **Modèles du module Gestion de document commercial** (nom d'AOA **ERBDManageTemplates**).

La procédure suivante permet de modifier des modèles de facture financière dans l'espace de travail du module Gestion de document commercial. Avant de pouvoir exécuter cette procédure, vous devez avoir effectué toutes les procédures précédentes dans cette rubrique.

1. Connectez-vous à Finance and Operations en tant qu'utilisateur avec accès à l'espace de travail du module Gestion de document commercial.
2. Ouvrez l'espace de travail du module Gestion de document commercial.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-EditingTemplate1.png)

L'onglet **Modèle** affiche le contenu du modèle sélectionné. Sélectionnez l'onglet **Détails** pour consulter les détails du modèle sélectionné ainsi que les détails d'une configuration de format d'ER dans lequel se trouve ce modèle. Notez que tous les modèles ont un statut **Publié**, et ne contiennent aucun détail dans la colonne **Révision**. Cela signifie que ces modèles n'ont pas encore été modifiés.

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>Lancer des modèles de modification détenus par votre fournisseur de configuration

1. Dans l'espace de travail du module Gestion de document commercial, sélectionnez le modèle **Format d'impression de chèque** dans la liste.
2. Sélectionnez l'onglet **Détails**.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-EditingTemplate2.png)

L'option **Modifier le modèle** est disponible pour le modèle sélectionné. Cette option est toujours disponible pour un modèle dans une configuration de format ER détenue par le fournisseur de configuration ER actif (**Litware, Inc.** dans cet exemple). Lorsque **Modifier le modèle** est sélectionné, le modèle existant de la version temporaire de la configuration sous-jacente de format ER peut être modifié.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Lancer des modèles de modification détenus par d'autres fournisseurs

1. Dans l'espace de travail du module Gestion de document commercial, sélectionnez le modèle **État FTI client (GER)** dans la liste.
2. Sélectionnez l'onglet **Détails**.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-EditingTemplate3.png)

L'option **Nouveau document** est disponible pour le modèle sélectionné. Cette option est toujours disponible pour un modèle dans une configuration de format ER fournie par un autre fournisseur (**Microsoft** dans cet exemple). Lorsque **Nouveau document** est sélectionné, un nouveau modèle peut être modifié. Le modèle modifié est ensuite stocké dans une nouvelle configuration de format ER qui est automatiquement générée.

### <a name="start-editing-a-template"></a>Commencer à modifier un modèle

1. Sélectionnez **Nouveau document** dans le modèle sélectionné.
2. Dans le champ **Titre**, changez le titre du modèle à modifier si nécessaire. Le texte sera utilisé pour nommer la configuration du format ER qui est automatiquement créée. Notez que la version temporaire de cette configuration (**Copie d'État FTI client (GER)**) qui contient le modèle modifié sera automatiquement marquée pour exécuter ce format ER pour l'utilisateur actuel. En même temps, le modèle d'origine non modifié de la configuration du format ER de base sera utilisé pour exécuter ce format ER pour tout autre utilisateur.
3. Dans le champ **Nom**, modifiez le nom de la première révision du modèle modifiable qui sera créé automatiquement.
4. Dans le champ **Commentaire**, modifiez la remarque de la révision créée automatiquement du modèle modifiable.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-EditingTemplate4.png)

5. Cliquez sur **OK** pour confirmer le début du processus de modification.

La page **Éditeur de modèle BDM** de Finance and Operations s'ouvre. Le modèle sélectionné sera disponible pour la modification en ligne à l'aide de Office 365.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-office-365"></a>Modifier un modèle dans Office 365

Modifiez le modèle à l'aide de la fonctionnalité d'Office 365. Par exemple, dans Office online, faites passer la police des invites de champ de l'en-tête de modèle de **Normal** à **Gras**. Ces modifications sont automatiquement enregistrées pour le modèle modifiable enregistré dans le principal stockage du modèle (par défaut, dans le stockage des objets blobs Azure) qui est configuré pour la structure ER.

![Page de l'éditeur de modèle du module Gestion de document commercial](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a>Modifier un modèle dans l'application de bureau Office

1. Sélectionnez l'option **Ouvrir dans l'application de bureau** pour modifier le modèle à l'aide de la fonctionnalité de l'application de bureau Office (Excel dans cet exemple). Le modèle modifiable est copié de la mémoire permanente vers le stockage temporaire configuré dans les paramètres du module Gestion de document commercial en tant que dossier SharePoint.
2. Confirmez que vous souhaitez ouvrir le modèle à partir du stockage de fichier temporaire dans l'application de bureau Office Excel.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-EditingLayout3.png)

3. Modifiez le modèle. Par exemple, modifiez la police des invites de champ de l'en-tête de modèle en faisant passer la couleur de **Normal** à **Bleu**.

![Page de l'éditeur de modèle du module Gestion de document commercial](./media/BDM-Overview-EditingLayout4.png)

4. Sélectionnez **Enregistrer** dans l'application de bureau Excel pour enregistrer les modifications du modèle dans le stockage temporaire.

![Page de l'éditeur de modèle du module Gestion de document commercial](./media/BDM-Overview-EditingLayout5.png)

5. Fermez l'application de bureau Excel.
6. Sélectionnez **Synchroniser la copie enregistrée** pour synchroniser le stockage temporaire de modèle avec le stockage permanent de modèle.

> [!NOTE]
> La copie du modèle modifiable dans le stockage de fichier temporaire est conservée pour la session actuelle du modèle uniquement. Une fois que cette session est terminée et que la page **Éditeur de modèle BDM** est fermée, cette copie est alors supprimée. Si vous avez modifié le modèle dans le stockage de fichier temporaire et que vous n'avez pas sélectionné **Synchroniser la copie enregistrée**, lorsque vous essayez de fermer la page **Éditeur de modèle BDM**, un message demande si vous souhaitez enregistrer les modifications introduites. Sélectionnez **Oui** si vous souhaitez enregistrer les modifications apportées au modèle dans l'emplacement du fichier permanent.

### <a name="validate-a-template"></a>Contrôler un modèle

1. Dans la page **Éditeur de modèle BDM**, sélectionnez **Rechercher des problèmes** pour valider le modèle modifié par rapport à la configuration sous-jacente de format ER. Suivez les recommandations (le cas échéant) pour aligner le modèle avec la structure du format à partir de la configuration du format ER de base.
2. Sélectionnez **Afficher le format** pour afficher la structure actuelle du format à partir de la configuration du format ER de base qui doit être alignée avec le modèle pouvant être modifié. 
3. Sélectionnez **Masquer le format** pour fermer le volet.

![Page Éditeur de modèle BDM](./media/BDM-Overview-EditingTemplate6.png)

4. Fermez la page **Éditeur de modèle BDM**.

Le modèle mis à jour est affiché dans l'onglet **Modèle** . Notez que le statut du modèle révisé est désormais **Brouillon** et la révision actuelle n'est plus vide. Cela signifie que le processus de modification de ce modèle a commencé.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>Tester le modèle modifié 

1. Dans Finance and Operations, sélectionnez la société, **USMF**.
2. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
3. Sélectionnez la facture **FTI-00000002**, puis sélectionnez **Gestion de l'impression**.
4. Sélectionnez le niveau de document **Module - Comptabilité client** \> **Documents** \> **Facture financière** \> **Document d'origine** pour spécifier la portée des factures aux fins de traitement.
5. Dans le champ **Format de l'état**, sélectionnez le format ER **Copie d'État FTI client (GER)** pour le niveau de document spécifié.

![Page Paramètre de gestion de l'impression](./media/BDM-Overview-TestRun1.png)

6. Appuyez sur **Échap** pour fermer la page actuelle.
7. Sélectionnez **Imprimer**, puis cliquez sur **Sélectionné**.
8. Téléchargez le document et ouvrez-le à l'aide de l'application de bureau Excel.

![Page Factures financières](./media/BDM-Overview-TestRun2.png)

Le modèle révisé est utilisé pour générer l'état de facture financière pour l'article sélectionné. Pour analyser la manière dont cet état est affecté par les modifications apportées au modèle, vous pouvez exécuter cet état dans une session de l'application immédiatement après avoir modifié le modèle dans une autre session de l'application.

### <a name="create-an-alternative-template-revision"></a>Créer une révision du modèle de remplacement

1. Ouvrez la page **Éditeur de modèle BDM** et sélectionnez le modèle **Copie d'État FTI client (GER)**.
2. Dans l'onglet **Révisions**, sélectionnez **Nouveau**.
3. Si nécessaire, dans le champ **Nom**, modifiez le nom de la deuxième révision et basez-le sur la première révision active.
4. Si nécessaire, dans le champ **Commentaire**, modifiez la remarque de la révision créée automatiquement du modèle modifiable.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-AddRevision.png)

Vous avez créé une révision de votre modèle qui a été enregistrée dans le stockage du modèle permanent. Vous pouvez désormais continuer à modifier le modèle de la deuxième révision actuellement sélectionné comme actif.

5. Sélectionnez la première révision, puis sélectionnez **Activer**. Vous pouvez sélectionner une autre révision comme active si à tout moment vous souhaitez revenir à la révision du modèle.
6. Sélectionnez la deuxième révision, puis sélectionnez **Supprimer**.
7. Sélectionnez **OK** pour confirmer la suppression de la révision sélectionnée. Vous pouvez supprimer n'importe quelle révision inactive si elle n'est plus nécessaire.

### <a name="delete-a-modified-template"></a>Supprimer un modèle modifié

1. Dans la page **Éditeur de modèle BDM**, sélectionnez l'onglet **Modèle**.
2. Sélectionnez **Supprimer**.
3. Si vous sélectionnez **OK** pour confirmer la suppression, le format ER **Copie d'État FTI client (GER)** avec le modèle modifié est alors supprimé. Sélectionnez **Annuler** pour explorer d'autres options.

### <a name="revoke-changes-of-template"></a>Annuler les modifications du modèle

Lorsque vous modifiez le modèle provenant d'un format ER qui appartient au fournisseur actif, vous avez l'option d'annuler les modifications introduites pour le modèle.

![Page de l'espace de travail du module Gestion de document commercial](./media/BDM-Overview-RevokeChanges.png)

1. Dans la page **Éditeur de modèle BDM**, sélectionnez l'onglet **Modèle**.
2. Sélectionnez **Annuler**.
3. Si vous sélectionnez **OK** pour annuler les modifications introduites pour le modèle, le modèle modifié est alors remplacé par le modèle d'origine et toutes les modifications sont supprimées. Lorsque vous annulez des modifications du modèle, vous pouvez supprimer le modèle. Sélectionnez **Annuler** pour explorer d'autres options.

### <a name="publish-a-modified-template"></a>Publier un modèle modifié
1. Dans la page **Éditeur de modèle BDM**, sur l'onglet **Modèle**, sélectionnez **Publier**.
2. Si vous sélectionnez **Ajouter** pour confirmer la publication, la version temporaire du format ER dérivé **Copie d'État FTI client (GER)** qui contient le modèle modifié est marquée comme terminée. Le modèle modifié devient disponible pour d'autres utilisateurs de Finance and Operations. Les versions terminées de ce format ER conserveront uniquement la dernière révision active de votre modèle. Les autres révisions seront supprimées. Sélectionnez **Annuler** pour explorer d'autres options.

## <a name="frequently-asked-questions"></a>Forum aux questions

#### <a name="i-selected-new-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-office-365-web-page"></a>J'ai sélectionné **Nouveau document**, mais plutôt que d'ouvrir la page **Éditeur de modèle BDM** dans Finance and Operations, je suis arrivé sur la page Web Office 365.
Il s'agit d'un problème connu de redirection d'Office 365 dans Finance and Operations. Cela se produit lorsque vous vous connectez à Office 365 la première fois. Pour contourner ce problème, sélectionnez le bouton **Précédent** de votre navigateur pour accéder à Finance and Operations.

#### <a name="i-understand-how-to-edit-a-template-by-using-office-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-adjusting-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-do-this-using-the-office-desktop-application"></a>Je sais comment modifier un modèle à l'aide d'Office 365 dans la première session d'application et utiliser le modèle dans la deuxième session d'application en modifiant le modèle pour voir comment mes modifications affectent le document commercial généré. Puis-je effectuer cette opération à l'aide de l'application de bureau Office ?
Oui, vous pouvez. Dans la première session de l'application, sélectionnez **Ouvrir dans l'application de bureau**. Votre modèle sera stocké dans le stockage de fichier temporaire et ouvert dans l'application de bureau Office. Procédez ensuite comme suit pour prévisualiser les modifications apportées au modèle dans le document commercial généré :

1. Apportez des modifications dans le modèle à l'aide de l'application de bureau Office.
2. Sélectionnez **Enregistrer** dans l'application de bureau Office.
3. Dans la page **Éditeur de modèle BDM** de la première session de l'application, sélectionnez **Synchroniser la copie enregistrée**.
4. Exécutez ce format ER de modèle dans la deuxième session de l'application.

#### <a name="i-get-the-error-value-cannot-be-null-parameter-name-externalid-when-i-select-open-in-desktop-app-how-do-i-work-around-this"></a>J'obtiens l'erreur « La valeur ne peut pas être nulle. Nom du paramètre : externalId » lorsque je sélectionne **Ouvrir dans l'application de bureau**. Comment résoudre cette erreur ? 
Vous êtes probablement connecté à l'instance actuelle de Finance and Operations du domaine Azure AD qui diffère du domaine Azure AD utilisé pour déployer cette instance de Finance and Operations. Comme le service SharePoint, qui permet d'enregistrer des modèles pour les rendre disponibles pour modification à l'aide des applications de bureau Office, appartient au même domaine que Finance and Operations, nous n'avons aucune autorisation pour accéder au service SharePoint. Pour résoudre ce problème, connectez-vous à l'instance de Finance and Operations en utilisant les informations d'identification d'un utilisateur ayant le domaine Azure AD approprié.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des états électroniques](general-electronic-reporting.md)

[Concevoir une configuration pour générer des états au format OPENXML](tasks/er-design-reports-openxml-2016-11.md)

[Créer des configurations de gestion d'états électroniques pour générer des états au format Word](tasks/er-design-configuration-word-2016-11.md)

[Intégrer des images et des formes dans les documents que vous générez ER à l'aide de la gestion des états électroniques (ER)](electronic-reporting-embed-images-shapes.md)

[Configurer la Gestion des états électroniques pour extraire les données dans Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)
