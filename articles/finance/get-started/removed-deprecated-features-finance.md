---
title: Fonctions supprimées ou obsolètes dans Dynamics 365 Finance
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer de Dynamics 365 Finance.
author: roschlom
ms.date: 04/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: e0db5c35e58ab7a7cbf31642072d25ee5d8ba868
ms.sourcegitcommit: 04817103dc8e87a679d371575927284b8ce080b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2021
ms.locfileid: "5898285"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Fonctions supprimées ou obsolètes dans Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer de Dynamics 365 Finance.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification. 

> [!NOTE]
> Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](/dynamics/s-e/global/axtechrefrep_61). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.20

### <a name="rtir-query-invoice-data-request-hu-format-configuration"></a>Configuration du format de demande de données de facture (HU) par requête RTIR

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Exclus du traitement de la messagerie électronique d'interopérabilité avec le système de facturation en ligne hongrois |
| **Remplacé par une autre fonctionnalité ?**   | N° |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : d'ici le 15 avril 2022, nous prévoyons de ne plus prendre en charge la configuration du format « Demande d'informations de facture (HU) par requête RTIR ». |


## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.17

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>Référentiel LCS comme option de stockage pour les configurations de gestion des états électroniques

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par le nouveau référentiel global RCS (Regulatory Configuration Service) |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Dynamics 365 Finance, produits Supply Chain Management et Project Operations|
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : à partir du 1er avril 2022, nous prévoyons de ne plus prendre en charge le référentiel Lifecycle Services (LCS) Microsoft Dynamics comme option de stockage pour les configurations de gestion des états électroniques. Les nouvelles configurations ER Microsoft seront publiées pour téléchargement exclusivement à partir du référentiel global. Le référentiel global est accessible à partir des produits Dynamics 365 et RCS. Pour plus d’informations, voir [Importer les configurations ER depuis RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.16

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>Formats de gestion des états électroniques « Déclaration de TVA (CZ) » et « Exportation des déclarations de contrôle (CZ) » pour la République tchèque

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par de nouveaux formats |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : d’ici le 22 janvier 2022, nous prévoyons de ne plus prendre en charge les formats de déclaration électronique (ER) « Déclaration de TVA (CZ) » et « Exportation des déclarations de contrôle (CZ) ». De nouveaux formats de déclaration de TVA XML (CZ), de déclaration de TVA Excel (CZ), de déclaration de contrôle de TVA XML (CZ) sont introduits à la place sous le modèle « Déclaration de taxe ». |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>« Format d’exportation des transactions comptables (BE) » Format de déclaration électronique et modèle correspondant « Exportation des transactions comptables (BE) » pour la Belgique

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par le nouveau format ER sous le modèle "fichier d’audit standard (SAF-T)».  |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : d’ici le 1er décembre 2021, nous prévoyons de ne plus prendre en charge le format de déclaration électronique (ER) et le modèle respectif de type "Exportation des transactions comptables (BE)». Un nouveau format "Exportation des données comptables (BE)» ainsi que le "mappage du modèle de données comptables" sont introduits à la place sous le modèle "Fichier d’audit standard (SAF-T)». |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>Déclaration "VAT 100" pour le Royaume-Uni au format SSRS

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par le nouveau format ER – format "Déclaration de TVA Excel (UK) » sous "Modèle de déclaration fiscale".  |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : d’ici le 1er décembre 2021, nous prévoyons de ne plus prendre en charge le "rapport TVA 100" au format SSRS. Un nouveau format "Déclaration de TVA Excel (Royaume-Uni)» sous "Modèle de déclaration fiscale" a été introduit dans la [Fonction TVA MTD](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La prise en charge d’Internet Explorer 11 pour Dynamics 365 est obsolète

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Depuis décembre 2020, la prise en charge de tous les produits Dynamics 365 dans Microsoft Internet Explorer 11 est obsolète et Internet Explorer 11 ne sera plus pris en charge après août 2021.<br><br>Cela aura un impact sur les clients qui utilisent des produits Dynamics 365 conçus pour être utilisés via une interface Internet Explorer 11. Après août 2021, Internet Explorer 11 ne sera pas pris en charge pour ces produits Dynamics 365. |
| **Remplacé par une autre fonctionnalité ?**   | Nous recommandons aux clients de passer à Microsoft Edge.|
| **Zones de produit affectées**         | Tous les produits Dynamics 365 |
| **Option de déploiement**              | Tous|
| **État**                         | Obsolète. Internet Explorer 11 ne sera plus pris en charge après août 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.12

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>États SSRS polonais : Registre de la TVA d’aval, Registre de la TVA sur les achats, Synthèse du registre de la TVA de l’UE - Référence de fonctionnalité PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pas autorisé légalement.  |
| **Remplacé par une autre fonctionnalité ?**   | Oui (format Excel pour fichier d’audit standard avec déclaration de TVA - JPK_VDEK) |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : d’ici le 1er juillet 2021, nous prévoyons de ne plus prendre en charge les états SSRS : **Registre de TVA d’aval, Registre de TVA sur les achats, Synthèse du registre de la TVA de l’UE - Référence de fonctionnalité PL-00014**. Un exemple de format Excel pour le fichier d’audit standard avec déclaration de TVA (JPK_VDEK) sera introduit à la place. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.11

### <a name="norwegian-standard-main-accounts"></a>Comptes principaux standard pour la Norvège

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Refonte  |
| **Remplacé par une autre fonctionnalité ?**   | Oui (remplacé par des paramètres spécifiques à l’application au format de gestion des états électroniques) |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : d’ici le 1er avril 2021, nous prévoyons de ne plus prendre en charge les fonctionnalités liées aux comptes principaux standard : champ de référence, tableau associé, entité de données. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.7

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>La boîte de dialogue de demande de modification du workflow n’inclut plus de liste déroulante de sélection de l’utilisateur

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par la fonctionnalité avec sélection de groupes de comptes.  |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Flux de travail |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : À partir du 1er décembre 2020, nous prévoyons de ne plus prendre en charge les types de documents chinois paramétrés sans sélection de groupes de comptes. Pour plus d’informations sur la nouvelle conception dans [Nouveautés de la version 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes
Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
