---
title: Fonctions supprimées ou déconseillées dans Dynamics 365 Finance
description: Cet article décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer de Dynamics 365 Finance.
author: kfend
ms.date: 10/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 25d13aa26565e5753b87c843b43cf46f8276b642
ms.sourcegitcommit: 6c05bcd27e6ee72f01cb66e2cfd1e929e0365830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2022
ms.locfileid: "9854077"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Fonctions supprimées ou déconseillées dans Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Cet article décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer de Dynamics 365 Finance.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification. 

> [!NOTE]
> Des informations détaillées sur les objets dans les applications de finances et d’opérations peuvent être consultés dans les [États de référence technique](/dynamics/s-e/global/axtechrefrep_61). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés de chaque version des applications de finances et d’opérations.

## <a name="features-removed-or-deprecated-in-the-finance-10031-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.31

### <a name="edifact-paymul-at-configuration-under-payment-model"></a>Configuration EDIFACT PAYMUL (AT) sous Modèle de paiement

| &nbsp;  | &nbsp;  |
|---|---|
| **Motif de l’abandon/de la suppression** | Remplacé par un nouveau format basé sur ISO 20022 pain.001.001.09. | 
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Application |
| **Option de déploiement**              | Tout |
| **Status**                         | Obsolète : les banques autrichiennes obsolèteront EDICFACT-PAYMUL pour les paiements transfrontaliers d’ici novembre 2022 et le remplaceront par la version XML pain.001.001.09N. Une nouvelle configuration a été ajoutée sous le référentiel de configuration globale qui permet aux utilisateurs de compléter la demande de paiement transfrontalier. |

## <a name="features-removed-or-deprecated-in-the-finance-10030-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.30

### <a name="revenue-recognition"></a>Prise en compte de revenu

[Prise en compte de revenu](../../finance/accounts-receivable/revenue-recognition-overview.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Motif de l’abandon/de la suppression** |Remplacé par une fonctionnalité améliorée, [Facturation de l’abonnement](../../finance/accounts-receivable/subscription-billing-summary.md)
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées** | Application |
| **Option de déploiement** | Tout |
| **Status** | Obsolète : après avril 2023, la fonctionnalité de comptabilisation des revenus dans Dynamics 365 Finance ne sera plus prise en charge avec les correctifs de bogues. Les clients seront invités à utiliser la fonctionnalité améliorée, [Facturation de l’abonnement](../../finance/accounts-receivable/subscription-billing-summary.md). En octobre 2023, la fonctionnalité de comptabilisation des revenus ne sera plus disponible. Les clients seront invités à utiliser la fonctionnalité améliorée, Facturation de l’abonnement. Pour la fonctionnalité groupée dans le cadre de la reconnaissance des revenus, aucune fonctionnalité de remplacement n’est prévue pour le moment.|

## <a name="features-removed-or-deprecated-in-the-finance-10029-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.29

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Ordres de transfert des stocks avec taxe sur le prix de transfert

[Ordres de transfert des stocks avec taxe sur le prix de transfert](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Motif de l’abandon/de la suppression** | Remplacé par une fonctionnalité améliorée, [Ordres de transfert de stock pour l’Inde](../../finance/localizations/apac-ind-stock-transfer.md)|
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées** | Application |
| **Option de déploiement** | Tout |
| **Status** | Obsolète : Après avril 2023, la fonctionnalité **Ordres de transfert de stock qui ont une taxe sur le prix de transfert** ne sera plus prise en charge avec les correctifs de bogues et les correctifs de sécurité. Les clients seront invités à utiliser la fonctionnalité améliorée, [Ordres de transfert de stock pour l’Inde](../../finance/localizations/apac-ind-stock-transfer.md). Après octobre 2023, la fonctionnalité **Ordres de transfert de stock qui ont une taxe sur le prix de transfert** ne sera plus disponible, et les clients seront invités à passer à la fonctionnalité améliorée. |

### <a name="bank-statement-import-and-export-of-positive-pay-file"></a>Importation et exportation des relevés bancaires du fichier de paiement positif

| &nbsp;  | &nbsp;  |
|---|---|
| **Motif de l’abandon/de la suppression** |Remplacé par une fonctionnalité améliorée, importez des relevés bancaires et exportez des fichiers de paiement positifs.| 
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Application |
| **Option de déploiement**              | Tout |
| **Status**                         | Déconseillé : la fonctionnalité XSLT d’importation et d’exportation de fichiers ne sera plus prise en charge avec les correctifs de bogues et les correctifs de sécurité. Les clients seront invités à utiliser la fonctionnalité améliorée : [Configurez des fichiers de paiement positifs à l’aide de rapports électroniques](../../finance/accounts-payable/set-up-positive-pay-er.md) et [Configurez l’importation avancée de rapprochement bancaire à l’aide de la génération de rapports électroniques](../../finance/accounts-payable/import-bai2-er.md). Après septembre 2022, la fonctionnalité XSLT ne sera plus disponible et les clients seront invités à passer à la fonctionnalité améliorée.|


## <a name="features-removed-or-deprecated-in-the-finance-10026-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.26

### <a name="sales-tax-report-for-finland-design-based-on-reporting-codes"></a>Déclaration de taxe pour la Finlande (conception basée sur les codes de déclaration)

[Déclaration de taxe pour la Finlande](../localizations/emea-fin-sales-tax-payment-report-finland.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par une nouvelle conception de déclaration de TVA, [Déclaration de TVA pour la Finlande](../localizations/emea-fin-vat-declaration.md). |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Application |
| **Option de déploiement**              | Tout |
| **Status**                         | Obsolète : d’ici le 1er mars 2023, nous prévoyons de ne plus prendre en charge la déclaration de taxe pour la Finlande (présentation d’état finlandaise). De nouveaux formats ER de **déclaration de TVA XML (FI**) et de **déclaration de TVA Excel (FI)** sont introduits sous le modèle **Déclaration de taxe**. |

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.24

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>Déclaration de taxe pour la Suède (conception basée sur les codes de déclaration)

[Déclaration de taxe pour la Suède](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par une nouvelle conception de déclaration de TVA, [Déclaration de TVA pour la Suède](../localizations/emea-swe-vat-declaration-sweden.md) |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tout |
| **Status**                         | Obsolète : d’ici le 1er décembre 2022, nous prévoyons de ne plus prendre en charge la déclaration de taxe pour la Suède (présentation d’état suédois). De nouveaux formats ER de **déclaration de TVA XML (SE**) et de **déclaration de TVA Excel (SE)** sont introduits sous le modèle **Déclaration de taxe**. |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>Déclaration de TVA pour l’Autriche (conception basée sur les codes de déclaration)

[Détails de la déclaration de TVA pour l’Autriche](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par une nouvelle conception de déclaration de TVA, [Déclaration de TVA pour l’Autriche](../localizations/emea-aut-vat-declaration-austria.md) |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tout |
| **Status**                         | Obsolète : d’ici le 1er décembre 2022, nous prévoyons de ne plus prendre en charge le format ER de **déclaration de TVA (AT)** sous **Modèle de déclaration de TVA**. De nouveaux formats de **déclaration de TVA XML (AT)** et de **déclaration de TVA Excel (AT)** sont introduits sous le modèle **Déclaration de taxe**. |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes-electronic-tax-declaration-log-menu-item-and-page-electronic-tax-declaration-setup-menu-item-and-page-german-report-layout-taxreport_de-ssrs-format"></a>Déclaration ELSTER pour l’Allemagne (conception basée sur les codes de déclaration), \"Journal de déclaration de taxe électronique\" élément de menu et page, \"Paramétrage de la déclaration de taxe électronique\" élément de menu et page, format SSRS (TaxReport_DE) de disposition de rapport allemande

[Déclaration de TVA](../localizations/emea-de-vat-declaration.md)</br>
[Configurer une déclaration de taxe électronique pour l’Allemagne](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par une nouvelle conception de déclaration de TVA, [Déclaration de TVA pour l’Allemagne](../localizations/emea-deu-vat-declaration-germany.md) |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tous |
| **Status**                         | Obsolète : d’ici le 1er décembre 2022, nous prévoyons de ne plus prendre en charge les format d’états électroniques (ER) **Elster (DE)** et le **modèle Elster**. De nouveaux formats ER de **Déclaration de TVA XML (DE)** et de **Déclaration de TVA Excel (DE)** sont introduits sous le modèle **Déclaration de taxe**. Nous ne prendrons plus non plus en charge l’élément de menu et la page **Taxe** \> **Déclarations** \> **Taxe de vente** \> **Journal de déclaration fiscale électronique**, l’élément de menu et la page **Taxe** \> **Configuration** \> **Taxe de vente** \> **Configuration de la déclaration de taxe électronique**, l’élément de menu et la page **Taxe** \> **Configuration** \> **Taxe de vente** \> **Certificats fiscaux électroniques** et la disposition du rapport allemand (TaxReport\_DE) au format SQL Server Reporting Services (SSRS). Le processus de déclaration de TVA en Allemagne est pris en charge dans la fonctionnalité de [messagerie électronique](../general-ledger/electronic-messaging.md). Pour plus d’informations, voir [Déclaration de TVA pour l’Allemagne](../localizations/emea-deu-vat-declaration-germany.md). |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes-electronic-ob-declaration-menu-item-and-page-dutch-report-layout-taxreport_nl-ssrs-format"></a>Déclaration OB pour les Pays-Bas (conception basée sur les codes de déclaration), l’élément de menu et la page \"Déclaration OB électronique\", disposition du rapport néerlandais (TaxReport_NL) au format SSRS

[Déclaration OB](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par une nouvelle conception de déclaration de TVA, [Déclaration de TVA pour les Pays-Bas](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tous |
| **Status**                         | Obsolète : d’ici le 1er décembre 2022, nous prévoyons de ne plus prendre en charge le format d’états électroniques (ER) de **Déclaration OB (P.-B.)** et le **Modèle de déclaration OB**. De nouveaux formats d’états électroniques (ER) de **Déclaration de TVA XML (NL)** et de **Déclaration de TVA Excel (NL)** sont introduits sous le modèle **Déclaration de taxe**. Nous ne prendrons plus non plus en charge l’élément de menu et la page **Taxe** \> **Déclarations** \> **Taxe de vente** \> **Déclaration OB électronique**, et le format SSRS de la disposition du rapport néerlandais (TaxReport_NL). Le processus de déclaration de TVA aux Pays-Bas est pris en charge dans la fonctionnalité de [messagerie électronique](../general-ledger/electronic-messaging.md). Pour plus d’informations, voir [Déclaration de TVA pour les Pays-Bas](../localizations/emea-nl-vat-declaration-netherlands.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.20

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>Configuration du format de rapport électronique (ER) "Demande de données de facture (HU) par requête RTIR"

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Exclus du traitement de la messagerie électronique d’interopérabilité avec le système de facturation en ligne hongrois |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : d’ici le 15 avril 2022, nous prévoyons de ne plus prendre en charge la configuration du format « Demande d’informations de facture (HU) par requête RTIR ». |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>"Fichier d’audit FEC français" Format de reporting électronique (ER) pour la France sous format "Sortie de fichier d’audit allemand"

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par le nouveau format "FEC audit file (FR) » |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : d’ici le 1er mai 2022, nous prévoyons de ne plus prendre en charge le format "Fichier d’audit FEC français" pour la France sous le format "Sortie de fichier d’audit allemand". Le nouveau format de fichier d’audit FEC (FR) est introduit à la place sous le "Modèle d’exportation de données". |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.17

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>Référentiel LCS comme option de stockage pour les configurations de gestion des états électroniques

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Remplacé par le nouveau référentiel global RCS (Regulatory Configuration Service) |
| **Remplacé par une autre fonctionnalité ?**   | Oui |
| **Zones de produit affectées**         | Produits Dynamics 365 Finance, Supply Chain Management et Project Operations|
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : à partir du 1er avril 2022, nous prévoyons de ne plus prendre en charge le référentiel Lifecycle Services (LCS) Microsoft Dynamics comme option de stockage pour les configurations de gestion des états électroniques. Les nouvelles configurations ER Microsoft seront publiées pour téléchargement exclusivement à partir du référentiel global. Le référentiel global est accessible à partir des produits Dynamics 365 et RCS. Pour plus d’informations, consultez [Importer des configurations ER depuis RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) et [Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)](../localizations/rcs-lcs-repo-dep-faq.md). |

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
| **Remplacé par une autre fonctionnalité ?**   | Nous recommandons aux clients de passer à Microsoft Edge.|
| **Zones de produit affectées**         | Tous les produits Dynamics 365 |
| **Option de déploiement**              | Tous|
| **État**                         | Obsolète. Internet Explorer 11 ne sera plus pris en charge après août 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Fonctions supprimées ou obsolètes dans Finance version 10.0.12

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Non obsolète : États SSRS polonais : Registre de la TVA d’aval, Registre de la TVA sur les achats, Synthèse du registre de la TVA de l’UE - Référence de fonctionnalité PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Pas autorisé légalement.  |
| **Remplacé par une autre fonctionnalité ?**   | Oui (format Excel pour fichier d’audit standard avec déclaration de TVA - JPK_VDEK) |
| **Zones de produit affectées**         | Demande |
| **Option de déploiement**              | Tous |
| **État**                         | Non obsolète : À compter du 27 avril 2021, nous prévoyons de continuer à prendre en charge les états SSRS : **Registre de TVA d’aval, Registre de TVA sur les achats, Synthèse du registre de la TVA de l’UE - Référence de fonctionnalité PL-00014**. Un exemple de format Excel pour le fichier d’audit standard avec déclaration de TVA (JPK_VDEK) a également été introduit. |

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

