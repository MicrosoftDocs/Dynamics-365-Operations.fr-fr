---
title: Fonctions de la plateforme supprimées ou déconseillées
description: Cet article décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer dans les mises à jour de plateforme des applications de finances et d’opérations.
author: sericks007
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 6283e07b87dc169d3cbaa71a371839ab9b2d6150
ms.sourcegitcommit: ee13b854cbd52a3aa33e2449a296aed775862594
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2022
ms.locfileid: "9799034"
---
# <a name="removed-or-deprecated-platform-features"></a>Fonctions de la plateforme supprimées ou déconseillées

[!include [banner](../includes/banner.md)]

Cet article décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer dans les mises à jour de plateforme des applications de finances et d’opérations.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification. 

Des informations détaillées sur les objets dans les applications de finances et d’opérations peuvent être consultés dans les [États de référence technique](/dynamics/s-e/global/axtechrefrep_61). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés de chaque version des applications de finances et d’opérations.

## <a name="feature-deprecation-effective-august-2022"></a>Notification d’abandon de fonctionnalités à compter d’août 2022

### <a name="lifecycle-services-lcs-features-deprecated-in-august-2022"></a>Fonctionnalités Lifecycle Services (LCS) obsolètes en août 2022

Dans le cadre de l’effort de travail [One Dynamics One Platform](/dynamics365-release-plan/2022wave2/finance-operations/finance-operations-crossapp-capabilities/one-dynamics-one-platform), les fonctionnalités LCS suivantes sont obsolètes.

| Nom de la fonction | Utilisé avec AX 2012 ? | Utilisé avec les applications de finances et d’opérations ? | Remplacé par une autre fonctionnalité ? |
|--------------|--------------------|----------------------------------------|------------------------------|
| Annonces | Oui | Oui | Oui : Des bannières existent sur les pages de projet et d’environnement individuelles pour les notifications. |
| Gestionnaire de configuration | Oui | N° | N° |
| Analyse de vidage sur incident | Oui | N° | N° |
| Commentaires et bogues | Oui | Oui | N° |
| Mon abonnement | Oui | Oui | N° |
| Office 365 | Oui | Oui | Oui : Azure Active Directory ou Portail d’administration Microsoft. |
| Analyse d’impact | N° | Oui | N° |
| Estimateur de l’impact économique total | N° | Oui | N° |
| Demandes de service | N° | Oui | Oui : [Déploiements en libre service](../deployment/infrastructure-stack.md) |
| Intégration de SharePoint | Oui | Oui | N° |
| Gestionnaire de configuration et de données | N° | Oui | N° |
| Packages de données de processus | N° | Oui | Oui : [Cadre d’importation et d’exportation de données (DIXF)](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job) |
| Mise à jour de l’environnement | N° | Oui | Oui : [Les mises à jour du service One Version](../lifecycle-services/oneversion-overview.md) sont disponibles. |
| Outil de sizing d’infrastructure | Oui | N° | N° |
| Dimensionnement de la licence | Oui | N° | N° |
| Analyseur de charge | Oui | N° | N° |
| Analyse de la personnalisation | Oui | N° | N° |
| Monitoring | Oui | Oui | N° |
| Modélisation de processus métier Gestion Visio | Oui | Oui | N° |
| AX 2012 gestion de l’environnement cloud | Oui | N° | N° |
| Connecteurs Azure RDFE | Oui | Oui | N° |
| Versions AX 2012 | Oui | N° | N° |
| Articles de travail stockés dans le stockage LCS | Oui | Oui | N° |
| Demandes de correctif | Oui | Oui | N° |


### <a name="transport-layer-security-tls-rsa-cipher-suites"></a>Suites de chiffrement RSA Sécurité de couche de transport (TLS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous supprimons la liste suivante de suites de chiffrement pour nous conformer à nos protocoles de sécurité actuels.<br><br>TLS_RSA_WITH_AES_256_GCM_SHA384<br>TLS_RSA_WITH_AES_128_GCM_SHA256<br>TLS_RSA_WITH_AES_256_CBC_SHA256<br>TLS_RSA_WITH_AES_128_CBC_SHA256<br>TLS_RSA_WITH_AES_256_CBC_SHA<br>TLS_RSA_WITH_AES_256_CBC_SHA  |
| **Remplacé par une autre fonctionnalité ?**   | À compter de janvier 2023, les clients ne pourront utiliser que nos [suites de chiffrement standard](/power-platform/admin/server-cipher-tls-requirements). Ce changement a un impact sur vos clients et serveurs qui communiquent avec nos serveurs, par exemple, il peut avoir un impact sur vos intégrations tierces qui ne respectent pas nos suites de chiffrement standard. |
| **Zones de produit affectées**         | Applications de finances et d’opérations |
| **Option de déploiement**              | Déploiements cloud |
| **Status**                         | Obsolète. Les clients doivent mettre à jour leurs serveurs avant janvier 2023. Pour plus d’informations sur la configuration de l’ordre de la Suite de chiffrement TLS, consultez [Gérer la sécurité de la couche de transport (TLS)](/windows-server/security/tls/manage-tls).  |


## <a name="feature-deprecation-effective-june-2022"></a>Notification d’abandon de fonctionnalités à compter de juin 2022

### <a name="finance-and-operations-dynamics-365-mobile-application-and-mobile-platform"></a>Application mobile et plateforme mobile des applications de finances et d’opérations (Dynamics 365) 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous abandonnons l’application et la plateforme mobiles des applications de finances et d’opérations (Dynamics 365) pour les consolider en une plateforme mobile unique, qui est Power Apps. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, des expériences mobiles sur les données de l’application de finances et d’opérations peuvent être créées avec l’intégration de Power Platform. Consultez le [billet de blog](https://cloudblogs.microsoft.com/dynamics365/it/2022/06/03/finance-and-operations-dynamics-365-mobile-app-to-be-deprecated/) et [Créer des expériences mobiles](../power-platform/build-mobile-experiences.md) pour plus d’informations. |
| **Zones de produit affectées**         | Applications de finances et d’opérations |
| **Option de déploiement**              | Tout |
| **Status**                         | Obsolète. La date de fin du support est prévue pour octobre 2024. |


## <a name="platform-updates-for-version-10029-of-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.29

### <a name="panorama-tab-style"></a>Style d’onglet Panorama

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les pages à défilement horizontal s’alignent sur des modèles de mise en page obsolètes qui présentent des problèmes d’utilisabilité et d’accessibilité connus.  |
| **Remplacé par une autre fonctionnalité ?**   | Non, mais d’autres styles d’onglets sont toujours disponibles. |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tout |
| **Status**                         | Obsolète. |


## <a name="feature-deprecation-effective-april-2022"></a>Notification d’abandon de fonctionnalités à compter d’avril 2022

### <a name="xml-url-resolution-in-data-management"></a>Résolution d’URL XML dans la gestion des données 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous supprimons la prise en charge de la résolution d’URL XML car cela a été identifié comme une vulnérabilité de sécurité potentielle. Cela signifie que les ressources externes associées aux fichiers XML ne seront plus résolues.  |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Applications de finances et d’opérations |
| **Option de déploiement**              | Tout |
| **Status**                         | Obsolète. |

## <a name="feature-deprecation-effective-march-14-2022"></a>Notification d’abandon de fonctionnalités à compter du 14 mars 2022

### <a name="xslt-scripting-in-data-management"></a>Script XSLT dans Gestion des données

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La prise en charge des scripts XSLT dans Gestion des données est obsolète pour améliorer la sécurité et la protection des données dans les applications de finances et d’opérations.  |
| **Remplacé par une autre fonctionnalité ?**   | Non Les clients et les éditeurs de logiciels indépendants doivent envisager de réimplémenter leurs solutions selon le langage X++, à la place des scripts XSLT. |
| **Zones de produit affectées**         | Applications de finances et d’opérations |
| **Option de déploiement**              | Tout |
| **Status**                         | Désapprouvé <br><br>**Exception :** les clients qui utilisent actuellement les scripts XLST. Ils peuvent continuer à l’utiliser jusqu’à la mise à jour vers la version 10.0.30 ou ultérieure. Pour les versions antérieures, l’exception expirera le 31 janvier 2023. Les clients avec cette exception ont reçu une notification dans le centre de messages disponible dans le centre d’administration Microsoft 365. |

## <a name="feature-removal-effective-october-2021"></a>Suppression de la fonctionnalité à compter d’octobre 2021

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Rapports SQL Microsoft Azure dans Lifecycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Toutes les activités et le suivi sont effectués en interne, par la plate-forme, grâce à l’automatisation. Cela ne nécessite aucune intervention manuelle.|
| **Remplacé par une autre fonctionnalité ?**   | Oui, il existe maintenant un système automatisé, ce qui rend ces capacités obsolètes. |
| **Zones de produit affectées**         | Rapports SQL : DTU actuel, Détails du DTU actuel, Obtenir les détails du verrouillage, Liste du guide du plan actuel, Obtenir la liste des ID de requête, Obtenir le plan de requête SQL pour un ID de plan donné, Obtenir les plans de requête et le statut d’exécution, Obtenir la configuration de l’accélérateur, Obtenir les statistiques d’attente, Répertorier les requêtes les plus chères |
| **Option de déploiement**              | Déploiement dans le cloud : affecte les environnements de production gérés par Microsoft et les environnements de bac à sable de niveau 2 à 5. |
| **Statut**                         | Supprimé(e) |

### <a name="azure-sql-actions-in-lcs"></a>Actions Azure SQL dans LCS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous abandonnons certaines actions SQL dans LCS. Toutes les activités et le suivi sont effectués en interne, par la plate-forme, grâce à l’automatisation. Cela ne nécessite aucune intervention manuelle. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, il existe maintenant un système automatisé, ce qui rend ces capacités obsolètes. |
| **Zones de produit affectées**         | Actions SQL : Créer un guide de plan pour forcer l’ID de plan, Créer un guide de plan pour ajouter des conseils de table, Supprimer un guide de plan, Désactiver/Activer les verrous de page et l’escalade de verrous, Mettre à jour les statistiques sur une table, Régénérer l’index, Créer un index |
| **Option de déploiement**              | Déploiement dans le cloud : affecte les environnements de production gérés par Microsoft et les environnements de bac à sable de niveau 2 à 5. |
| **Statut**                         | Supprimé(e) |


## <a name="feature-deprecation-effective-october-2021"></a>Notification d’abandon de fonctionnalités à compter d’octobre 2021

### <a name="show-related-document-attachments-feature"></a>Fonctionnalité "Afficher les pièces jointes des documents associés"

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La fonctionnalité renvoyait des résultats inattendus. |
| **Remplacé par une autre fonctionnalité ?**   | Non. Tout autre projet concernant cette fonctionnalité sera communiqué par le biais de notre processus de divulgation de vague de publication standard. |
| **Zones de produit affectées**         | Client Web - Expérience de pièce jointe de document |
| **Option de déploiement**              | Tout |
| **Status**                         | Désapprouvé  |

## <a name="platform-updates-for-version-10023-of-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.23

### <a name="ondbsynchronize-event"></a>Événement OnDBSynchronize

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Il n’y a aucun contrôle pour exécuter cet événement. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, déplacer les méthodes existantes souscrites par l’événement **OnDBSynchronize** à une classe étendue SysSetup. |
| **Zones de produit affectées**         | Synchronisation de base de données |
| **Option de déploiement**              | Tout |
| **Statut**                         | Obsolète. La date de retrait prévue est octobre 2022. |


### <a name="systemnotificationsmanageraddnotification-api"></a>API SystemNotificationsManager.AddNotification

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Microsoft requiert des paramètres supplémentaires au moment de l’ajout de notifications. |
| **Remplacé par une autre fonctionnalité ?**   | Oui l’API **SystemNotificationsManager.AddSystemNotification()**. Cette API nécessite que vous définissiez explicitement ExpirationDateTime et RuleID pour les notifications générées. |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tout |
| **Statut**                         | Obsolète. La date de retrait prévue est Avril 2023. |

## <a name="platform-updates-for-version-10021-of-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.21

### <a name="skype-for-business-online-support"></a>Assistance Skype Entreprise en ligne

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Skype Entreprise en ligne a été retiré. Pour plus d’informations, consultez [Le service Skype Entreprise en ligne a été retiré](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/the-skype-for-business-online-service-has-retired/ba-p/2596601). |
| **Remplacé par une autre fonctionnalité ?**   | Pas pour le moment, bien que nous puissions envisager d’ajouter la présence de Teams à l’avenir.|
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tout |
| **Statut**                         | Obsolète. Le paramètre **Skype activé** a été désactivé à partir de la version 10.0.21. La suppression de ce paramètre est prévue pour avril 2022 ; cependant, la fonctionnalité cessera de fonctionner après la fermeture du service par l’équipe Skype. |
 
## <a name="feature-deprecation-effective-august-2021"></a>Notification d’abandon de fonctionnalités à compter d’août 2021

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Rapports SQL Microsoft Azure dans Lifecycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Toutes les activités et le suivi sont effectués en interne, par la plate-forme, grâce à l’automatisation. Cela ne nécessite aucune intervention manuelle.|
| **Remplacé par une autre fonctionnalité ?**   | Oui, il existe maintenant un système automatisé, ce qui rend ces capacités obsolètes. |
| **Zones de produit affectées**         | Rapports SQL : DTU actuel, Détails du DTU actuel, Obtenir les détails du verrouillage, Liste du guide du plan actuel, Obtenir la liste des ID de requête, Obtenir le plan de requête SQL pour un ID de plan donné, Obtenir les plans de requête et le statut d’exécution, Obtenir la configuration de l’accélérateur, Obtenir les statistiques d’attente, Répertorier les requêtes les plus chères |
| **Option de déploiement**              | Déploiement dans le cloud : affecte les environnements de production gérés par Microsoft et les environnements de bac à sable de niveau 2 à 5. |
| **Statut**                         | Obsolète : date de suppression prévue est octobre 2021. |

### <a name="azure-sql-actions-in-lcs"></a>Actions Azure SQL dans LCS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous abandonnons certaines actions SQL dans LCS. Toutes les activités et le suivi sont effectués en interne, par la plate-forme, grâce à l’automatisation. Cela ne nécessite aucune intervention manuelle. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, il existe maintenant un système automatisé, ce qui rend ces capacités obsolètes. |
| **Zones de produit affectées**         | Actions SQL : Créer un guide de plan pour forcer l’ID de plan, Créer un guide de plan pour ajouter des conseils de table, Supprimer un guide de plan, Désactiver/Activer les verrous de page et l’escalade de verrous, Mettre à jour les statistiques sur une table, Régénérer l’index, Créer un index |
| **Option de déploiement**              | Déploiement dans le cloud : affecte les environnements de production gérés par Microsoft et les environnements de bac à sable de niveau 2 à 5. |
| **Statut**                         | Obsolète : date de suppression prévue est octobre 2021. |

## <a name="feature-deprecation-effective-may-2021"></a>Notification d’abandon de fonctionnalités à compter de mai 2021

### <a name="globalization-portal-in-lifecycle-services-lcs"></a>Portail de globalisation de Lifecycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Nous abandonnons le portail de globalisation de LCS, car cette fonctionnalité a été remplacée par d’autres services basés sur LCS. |
| **Remplacé par une autre fonctionnalité ?**   | Oui, cette fonctionnalité est remplacée par la [Recherche d’incidents](../lifecycle-services/issue-search-lcs.md) de LCS et le [Service d’envoi d’alertes de réglementation de Dynamics](../lcs-solutions/submit-localization-alerts.md). |
| **Zones de produit affectées**         | Portail de globalisation de LCS|
| **Option de déploiement**              | Déploiement cloud |
| **Statut**                         | Obsolète : date de suppression prévue est mai 2022. |


## <a name="feature-removed-effective-january-28-2021"></a>Fonctionnalité supprimée à compter du 28 janvier 2021

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>Traitement par lots pour gérer la défragmentation de l’index SQL

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Afin de réduire les frais généraux d’exploitation, de surveillance et de maintenance de la gestion des index par les clients, cette fonctionnalité a été supprimée. |
| **Remplacé par une autre fonctionnalité ?**   | À l’avenir, la maintenance de l’index sera effectuée par les services Microsoft. Elle se produira de manière continue sans affecter les charges de travail des utilisateurs. |
| **Zones de produit affectées**         | Applications de finances et d’opérations|
| **Option de déploiement**              | Déploiement dans le cloud : affecte les environnements de production gérés par Microsoft et les environnements de bac à sable de niveau 2 à 5. |
| **Statut**                         | Cette fonctionnalité est supprimée. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.17


### <a name="visual-studio-2015"></a>Visual Studio 2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pour prendre en charge les dernières versions de Visual Studio, certaines modifications doivent être apportées aux extensions X++ pour Visual Studio. Ces modifications sont incompatibles avec Visual Studio 2015. |
| **Remplacé par une autre fonctionnalité ?**   | Visual Studio 2017 remplacera Visual Studio 2015 comme version déployée et requise. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tous |
| **Statut**                         | Obsolète : après la mise à jour, les outils X++ précédents seront supprimés de Visual Studio 2015, et les outils mis à jour ne seront pas installés sur Visual Studio 2015. Il n’y a aucun impact sur les builds hébergées. Pour les machines virtuelles de build, le pipeline de build (définition de build) doit être mis à jour manuellement pour modifier la dépendance de MSBuild 14.0 (Visual Studio 2015) vers MSBuild 15.0 (Visual Studio 2017) comme décrit dans [Mettre à jour un pipeline hérité dans Azure Pipelines](../dev-tools/pipeline-msbuild-update.md). |

### <a name="user-avatar"></a>Avatar de l’utilisateur 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’avatar de l’utilisateur qui s’affiche à droite de la barre de navigation a été récupéré à l’aide d’une API du contrôle d’en-tête de Dynamics 365, qui n’est plus utilisé. |
| **Remplacé par une autre fonctionnalité ?**   | À la place, les utilisateurs verront leurs initiales dans un cercle dans la barre de navigation. Ce même visuel est actuellement utilisé sur les machines de développement. |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tous |
| **Statut**                         | Supprimé à partir de la version 10.0.17 |

### <a name="enterprise-portal-ep-deprecation"></a>Abandon de Enterprise Portal (EP)  

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les artefacts de métadonnées associés à Dynamics AX 2012 Enterprise Portal (EP) ne sont plus utilisés, car EP n’a jamais été pris en charge dans les applications de finances et d’opérations. |
| **Remplacé par une autre fonctionnalité ?**   | N° |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tous |
| **Statut**                         | Obsolète : tout le code EP devrait être supprimé dans la version d’octobre 2021. |

## <a name="deprecation-effective-december-2020"></a>Abandon à compter de décembre 2020

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La prise en charge d’Internet Explorer 11 pour Dynamics 365 est obsolète

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Depuis décembre 2020, la prise en charge de tous les produits Dynamics 365 et Dynamics Lifecycle Services (LCS) dans Microsoft Internet Explorer 11 est obsolète et Internet Explorer 11 ne sera plus pris en charge après août 2021.<br><br>Cela aura un impact sur les clients qui utilisent des produits Dynamics 365 et LCS conçus pour être utilisés via une interface Internet Explorer 11. Après août 2021, Internet Explorer 11 ne sera pas pris en charge pour ces produits Dynamics 365 et LCS. |
| **Remplacé par une autre fonctionnalité ?**   | Nous recommandons aux clients de passer à Microsoft Edge.|
| **Zones de produit affectées**         | Tous les produits Dynamics 365 et LCS |
| **Option de déploiement**              | Tout|
| **Status**                         | Obsolète : Internet Explorer 11 ne sera plus pris en charge après août 2021.|

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.15

### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Module complémentaire Visual Studio pour appliquer des correctifs de métadonnées

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les correctifs de métadonnées ne sont plus pris en charge dans les mises à jour des services [One Version](../../fin-ops/get-started/one-version.md) introduites en juillet 2018 avec la version 8.1. |
| **Remplacé par une autre fonctionnalité ?**   | Les correctifs de métadonnées individuels ne sont pas disponibles pour les versions prises en charge. Les mises à jour qualité cumulatives sont appliquées à la place. |
| **Zones de produit affectées**         | Modules complémentaires Visual Studio |
| **Option de déploiement**              | Machines virtuelles de développement |
| **Statut**                         | Avec la version 10.0.15, le complément n’est plus inclus dans les outils Visual Studio. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.14

### <a name="online-users-page"></a>Page Utilisateurs en ligne 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Il s’agit d’une page héritée qui a été créée pour l’architecture client / serveur précédente. Les informations sur cette page ne sont pas toujours exactes, ce qui peut être déroutant et trompeur. |
| **Remplacé par une autre fonctionnalité ?**   | Nous fournirons une nouvelle page dans une future mise à jour.|
| **Zones de produit affectées**         | Administration du système |
| **Option de déploiement**              | Tous |
| **Statut**                         | D’ici octobre 2021, cet écran sera supprimé.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.13


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Code personnalisé défini dans les propriétés du rapport SSRS 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | En général, le code personnalisé offre des avantages limités tout en nécessitant en même temps des ressources et des calculs importants pour être pris en charge. Le code personnalisé est principalement utilisé par les auteurs de rapports pour appeler des méthodes publiques à partir d’un assembly de code personnalisé. Cependant, le service hébergé dans le cloud ne prend pas en charge les références aux assemblys personnalisés pour les rapports SSRS. |
| **Remplacé par une autre fonctionnalité ?**   | Les auteurs de rapports peuvent choisir de continuer à référencer les API .NET publiques pour les opérations Math, Conversion et Format à partir de n’importe quelle expression de zone de texte. Pour plus d’informations, voir la rubrique [Ajouter du code à un rapport (SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs).  |
| **Zones de produit affectées**         | Sous-ensemble de conceptions de rapport d’application définies dans RDL qui contiennent du code personnalisé. |
| **Option de déploiement**              | Tous |
| **Statut**                         | Avec la version 10.0.13, le compilateur commencera à émettre un avertissement pour les instances où du code personnalisé est détecté dans une définition de rapport SSRS. Pour résoudre le problème, ouvrez la définition de conception de rapport et supprimez tous les artefacts de code personnalisé. Cet avertissement sera remplacé par une erreur du compilateur dans une future mise à jour.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Mise à niveau de trois bibliothèques de composants jQuery 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Trois bibliothèques de composants jQuery sont en cours de mise à jour pour des correctifs de sécurité et pour maintenir l’actualité.   
| **Remplacé par une autre fonctionnalité ?**   | Les bibliothèques suivantes sont affectées : jQuery (vers la version 3.5.0 depuis la version 2.1.4), jQuery UI (vers la version 1.12.1 depuis la version 1.11.4), jQuery qTip (vers la version 3.0.3 depuis la version 2.2.1). Des conseils sur la migration ont été fournis en ligne par jQuery.  |
| **Zones de produit affectées**         | Contrôles extensibles, en particulier du code JavaScript personnalisé utilisant des API obsolètes ou supprimées |
| **Option de déploiement**              | Tout |
| **Statut**                         | Avec la version 10.0.13 /Platform update 37, les clients peuvent éventuellement passer aux dernières bibliothèques en activant la fonction "Mettre à niveau trois bibliothèques de composants jQuery". Le passage aux nouvelles bibliothèques sera obligatoire avec la version d’avril 2021 pour laisser le temps nécessaire à la migration des API concernées.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Contrôle de grille existant/API forceLegacyGrid()

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le contrôle de grille existant est remplacé par le nouveau contrôle de grille. |
| **Remplacé par une autre fonctionnalité ?**   | Le [nouveau contrôle de grille](../..//fin-ops/get-started/grid-capabilities.md) |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tout |
| **Statut**                         | Dans la version 10.0.13, le nouveau contrôle de grille est généralement disponible et les clients peuvent éventuellement activer cette fonctionnalité. Le nouveau contrôle du réseau est activé par défaut avec la version d’octobre 2021 et devrait être obligatoire en avril 2022. Quand le nouveau contrôle de grille deviendra obligatoire, l’API **forceLegacyGrid()** ne sera plus disponible. |

### <a name="personalization-without-saved-views"></a>Personnalisation sans vues enregistrées 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le sous-système de personnalisation a été remanié avec la fonction de vues enregistrées, afin qu’il ait de meilleures performances et offre des capacités supplémentaires. |
| **Remplacé par une autre fonctionnalité ?**   | Vues enregistrées |
| **Zones de produit affectées**         | Client Web |
| **Option de déploiement**              | Tout |
| **Statut**                         | Dans la version 10.0.13/Platform Update 37, la fonctionnalité des vues enregistrées est généralement disponible et les clients peuvent éventuellement activer cette fonctionnalité. La fonctionnalité Vues enregistrées deviendra obligatoire dans la version d’octobre 2021. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.12

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Extensions de formulaire de contrôle de grille ou de groupe contenant des références de champ non valides

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La propriété de groupe de données sur les contrôles de grille ou de groupe est utilisée pour afficher automatiquement tous les champs d’un groupe de champs. Un contrôle de grille ou de groupe ajouté par une extension peut contenir des champs qui ne sont plus définis sur le groupe de champs, ou il peut y avoir des champs manquants qui sont définis sur le groupe de champs. Cela peut entraîner un comportement incohérent au moment de l’exécution. Les mises à jour de la plateforme pour la version 10.0.12 des applications de finances et d’opérations classent désormais ce problème en tant qu’*avertissement* de compilateur. Pour résoudre ce problème, ouvrez l’extension de formulaire et enregistrez-la.
| **Remplacé par une autre fonctionnalité ?**   | Cet avertissement du compilateur sera remplacé par une erreur du compilateur dans une future mise à jour. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **Statut**                         | Un avertissement de compilateur est introduit dans les mises à jour de la plateforme pour la version 10.0.12 des applications de finances et d’opérations. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.11

### <a name="explicit-safe-lists-for-self-service-environments"></a>Liste sécurisée explicite pour les environnements en libre service

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le processus de déplacement de l’IP vers des listes sécurisées a changé. Le libre service ne prend plus en charge les listes sécurisées IP. |
| **Remplacé par une autre fonctionnalité ?**   | Pour plus d’informations, voir [Configuration de l’accès conditionnel Azure Active Directory](/appcenter/general/configuring-aad-conditional-access).|
| **Zones de produit affectées**         | Sécurité |
| **Option de déploiement**              | Cloud |
| **Statut**                         | Obsolète : Cette fonctionnalité est totalement obsolète pour les déploiements en libre service. |

### <a name="visual-studio-2015"></a>Visual Studio 2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pour prendre en charge les dernières versions de Visual Studio, certaines modifications doivent être apportées aux extensions X++ pour Visual Studio. Ces modifications sont incompatibles avec Visual Studio 2015. |
| **Remplacé par une autre fonctionnalité ?**   | Visual Studio 2017 remplacera Visual Studio 2015 comme version déployée et requise. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tous |
| **Statut**                         | Les machines virtuelles déployées sur la version 10.0.13 (Platform update 37) ou ultérieure contiennent Visual Studio 2017. La version 10.0.16 (Platform update 40) est la version finale avec prise en charge de Visual Studio 2015. Les machines virtuelles avec uniquement Visual Studio 2015 ne pourront pas se mettre à jour vers la version 10.0.17 (Platform update 41). |

### <a name="field-groups-containing-invalid-field-references"></a>Groupes de champ contenant des références de champs non valides

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les groupes de champs dans les définitions de métadonnées de table peuvent contenir des références de champ qui ne sont pas valides. Si ces groupes de champ sont déployés, ils peuvent provoquer des erreurs d’exécution dans Financial Reporting et Microsoft SQL Server Reporting Services (SSRS). Platform Update 23 a introduit un *avertissement* de compilateur qui a permis de résoudre ce problème de métadonnées. Les mises à jour de la plateforme pour la version 10.0.11 des applications de finances et d’opérations classent désormais ce problème en tant qu’*erreur* de compilateur.<p>Pour régler ce problème, procédez comme suit :</p><ol><li>Supprimez la référence de champ non valide de la définition du groupe de champs de table.</li><li>Recompilez.</li><li>Veillez à ce que toutes les erreurs soient corrigées.</li></ol> |
| **Remplacé par une autre fonctionnalité ?**   | Cette erreur du compilateur remplace définitivement l’avertissement du compilateur.  |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **Statut**                         | Obsolète : L’avertissement de compilation est une erreur de compilation avec les mises à jour de la plateforme pour la version 10.0.11 des applications de finances et d’opérations. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licences ISV créées à l’aide de l’algorithme de hachage SHA1

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le processus de création de licences de fournisseur de logiciels indépendant (ISV) a changé. Pour plus d’informations, voir [Licence de fournisseur de logiciels indépendant (ISV)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Remplacé par une autre fonctionnalité ?**   | Oui. Utilisez Windows PowerShell pour créer des licences. |
| **Zones de produit affectées**         | Outils de développement Visual Studio |
| **Option de déploiement**              | Tout |
| **Statut**                         | Obsolète : Licences ISV créées à l’aide de l’algorithme de hachage SHA1. Cet algorithme dépendait des certificats créés à l’aide de l’utilitaire MakeCert, et cet utilitaire est obsolète.<br><br>Obsolète : L’utilisation de SHA1 à des fins de sécurité ou de hachage. SHA1 cessera de fonctionner au début de 2021. Par conséquent, il ne devrait plus être utilisé.<br><br>Supprimé : Prise en charge des demandes entrantes ou sortantes TLS (Transport Layer Security) 1.0 et TLS 1.1. |

## <a name="platform-update-32"></a>Update 32 de la plateforme

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>La boîte de dialogue de demande de modification du workflow n’inclut plus de liste déroulante de sélection de l’utilisateur

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Il s’agissait d’un problème de sécurité, car la demande de modification pouvait être envoyée à un utilisateur indésirable. Il s’agissait également d’un problème d’utilisation, car cela obligeait l’utilisateur à déterminer le créateur du workflow et à le sélectionner manuellement.  |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Workflow |
| **Option de déploiement**              | Tous |
| **Statut**                         | La liste déroulante de sélection de l’utilisateur a été supprimée de la boîte de dialogue de demande de modification dans Platform update 32. Les demandes de modification seront automatiquement envoyées à l’expéditeur comme prévu. Pour plus d’informations sur cette fonctionnalité, consultez [Actions dans les processus d’approbation de workflow](../../fin-ops/organization-administration/workflow-actions.md?toc=%2fdynamics365%2fcommerce%2ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Les liens de suivi intégrés ne sont plus pris en charge dans les documents paginés rendus par le service hébergé par le cloud 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les URL de navigation intégrées dans des documents rendus par le service peuvent contenir des données de l’entreprise sensibles. Nous supprimons le support des liens de suivi intégrés dans les documents par mesure de prudence pour protéger davantage les données des clients. Les utilisateurs bénéficieront de performances améliorées tout en produisant des documents interactivement suite à ce changement.  |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Génération d’états |
| **Option de déploiement**              | Tout |
| **Statut**                         | Cette fonctionnalité est supprimée activement du service.<br><br>Le client moderne offre de nombreuses options pour produire des vues qui comprennent des liens générés automatiquement pour contribuer à la navigation dans l’application. Les documents paginés rendus par le service sont recommandés pour les communications externes qui sont envoyées par courrier électronique, archivées et imprimées pour les destinataires. Nous avons amélioré l’expérience de prévisualisation des documents directement dans le navigateur, ce qui offre un accès direct aux imprimantes locales. Pour plus d’informations, voir [Afficher un aperçu des documents PDF avec une visionneuse intégrée](../analytics/preview-pdf-documents.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes
Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../migration-upgrade/deprecated-features.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

