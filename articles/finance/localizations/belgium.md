---
title: Vue d’ensemble spécifique à la Belgique
description: Cette rubrique fournit une vue d’ensemble de la fonctionnalité spécifique à la Belgique.
author: anasyash
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: belgium
ms.author: anasyash
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 48e8ab9c46d3cc890adfec6ec84482fd584535f5
ms.sourcegitcommit: ed43ceae9b2ef3f616b81127bcf4c4b0862e23f5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2021
ms.locfileid: "7714845"
---
# <a name="belgium-overview"></a>Vue d’ensemble spécifique à la Belgique

[!include[banner](../includes/banner.md)]

Cette rubrique inclut des informations et des liens vers des ressources qui doivent être prises en compte pour les entités juridiques avec une adresse principale en Belgique.

## <a name="coda-bank-statement"></a>Relevé bancaire Coda
CODA est un format d’état qui est utilisé dans le système bancaire électronique belge. Pour plus d’informations, voir [Relevé bancaire CODA](emea-bel-coda-bank-statement-import.md).

## <a name="export-ledger-transactions"></a>Exporter les écritures comptables
Vous pouvez exporter des écritures comptables pour un intervalle spécifique, tel qu’un exercice, sous forme de fichier ASCII au format CED. Vous pouvez utiliser le traitement par lots pour exporter des transactions. Pour paramétrer le processus de traitement par lots, accédez à **Comptabilité** > **Périodique** > **Exporter les écritures comptables**. Pour plus d’informations, voir [Exporter les écritures comptables](emea-bel-export-ledger-transactions.md).

## <a name="intervat-tax-declaration"></a>Déclaration de taxe INTERVAT
Pour plus d’informations sur la configuration et la création de la déclaration de taxe INTERVAT pour les entités juridiques en Belgique uniquement, voir [Déclaration de taxe INTERVAT](emea-bel-intervat-tax-declaration.md). Pour plus d’informations sur les états standard qui peuvent vous aider avec la déclaration de taxe INTERVAT et l’analyse de rapprochement, voir [États de rapprochement pour la Belgique](emea-bel-reconciliation-reports.md).

## <a name="reports-for-belgium"></a>États pour la Belgique

| Rapport                     | Obtention de l’état | Informations supplémentaires                 |
|----------------------------|--------------------------|----------------------------------------|
|État BLWI (Belgisch Luxemburgs Wissel Instituut).|**Taxe** > **Déclarations** > **Commerce extérieur** > **BLWI** | Pour paramétrer les informations BLWI, voir [Paramétrer la déclaration de la balance des paiements (Belgique)](tasks/be-00011-set-up-payment-balance-reporting.md). Pour générer l’état BLWI, voir [Création et transfert de transactions vers l’état BLWI (Belgique)](tasks/be-00011-create-transfer-blwi.md).| 
|État PRODCOM|**Taxe** > **Déclarations** > **Commerce extérieur** > **PRODCOM**|Les fabricants de produits industriels envoient l’état PRODCOM au Nationaal Instituut voor de Statistiek (NIS), en réponse à l’enquête PRODCOM régulièrement mise en place. L’état PRODCOM affiche les statistiques de production pour les produits industriels fabriqués par des sociétés de production implantées en Belgique. Cet état est généralement utilisé par les chefs comptables et les comptables. Pour plus d’informations, voir [Paramétrer et mettre à jour PRODCOM](emea-bel-prodcom-report.md). |
|États sur les journaux|**Comptabilité** > **Recherches et états** > **États sur les journaux**|Périodiquement, les entreprises belges doivent imprimer un état pour chaque journal. Cet état fournit une liste chronologique de toutes les écritures dans les comptes de la comptabilité pour chaque journal. Ces rapports prouvent l’intégrité de la comptabilité et sont utilisés lors des audits financiers pour rapprocher le règlement de la TVA avec les écritures sur les comptes correspondants de la comptabilité. Pour plus d’informations, voir [États des journaux (Journaux de validation)](emea-bel-journal-reports.md). |
|Liste annuelle de TVA des ventes intérieures| **Taxe** > **Recherche et états** > **États de taxe** > **État du chiffre d’affaires des factures – Belgique** | L’état du chiffre d’affaires des factures est envoyé aux autorités une fois par an. Il est utilisé pour déclarer le chiffre d’affaires des clients belges assujettis à la TVA, si ce chiffre d’affaires dépasse un certain montant. L’état comprend les factures des transactions des clients pour lesquelles les clients ont un numéro d’entreprise formaté conformément aux directives des autorités belges. Pour plus d’informations, voir [Liste annuelle de TVA des ventes intérieures](emea-bel-annual-vat-listing-of-domestic-sales.md). |
|Déclaration d’échanges de biens, Belgique|  **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens** | Vous pouvez utiliser la page **Déclaration d’échanges de biens** pour générer et rapporter des informations sur le commerce entre pays/régions de l’Union européenne. La déclaration d’échanges de biens belge contient des informations sur le commerce de biens à déclarer. Pour plus d’informations, voir [Déclaration d’échanges de biens, Belgique](emea-bel-intrastat.md). |

## <a name="additional-resources"></a>Ressources supplémentaires

- [Portail de localisation Microsoft Dynamics : état belge](https://mbs.microsoft.com/files/customer/AX/Support/supportnews/Belgium.html) (nécessite le compte CustomerSource)
- [Vue d’ensemble des états électroniques](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)
- [Télécharger les configurations d’états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
- [Fonctions locales et relatives aux réglementations](../../fin-ops-core/dev-itpro/lcs-solutions/country-region.md?toc=%2ffin-and-ops%2ftoc.json)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
