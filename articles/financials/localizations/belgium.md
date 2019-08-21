---
title: Belgique
description: Cette rubrique fournit une vue d'ensemble de la fonctionnalité spécifique à la Belgique.
author: ShylaThompson
manager: AnnBe
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: belgium
ms.author: shylaw
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 4e1ce18da6d8c5fddc5bd943e2032e203e2aedc9
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850714"
---
# <a name="belgium"></a>Belgique

[!include[banner](../includes/banner.md)]

Cette rubrique inclut des informations et des liens vers des ressources qui doivent être prises en compte pour les entités juridiques avec une adresse principale en Belgique.

## <a name="coda-bank-statement"></a>Relevé bancaire Coda
CODA est un format d'état qui est utilisé dans le système bancaire électronique belge. Pour plus d'informations, voir [Relevé bancaire CODA](emea-bel-coda-bank-statement-import.md).

## <a name="export-ledger-transactions"></a>Exporter les écritures comptables
Vous pouvez exporter des écritures comptables pour un intervalle spécifique, tel qu'un exercice, sous forme de fichier ASCII au format CED. Vous pouvez utiliser le traitement par lots pour exporter des transactions. Pour paramétrer le processus de traitement par lots, accédez à **Comptabilité** > **Périodique** > **Exporter les écritures comptables**.

## <a name="intervat-tax-declaration"></a>Déclaration de taxe INTERVAT
Pour plus d'informations sur la configuration et la création de la déclaration de taxe INTERVAT pour les entités juridiques en Belgique uniquement, voir [Déclaration de taxe INTERVAT](emea-bel-intervat-tax-declaration.md). Pour plus d'informations sur les états standard qui peuvent vous aider avec la déclaration de taxe INTERVAT et l'analyse de rapprochement, voir [États de rapprochement pour la Belgique](emea-bel-reconciliation-reports.md).

## <a name="reports-for-belgium"></a>États pour la Belgique

| Rapport                     | Obtention de l'état | Informations supplémentaires                 |
|----------------------------|--------------------------|----------------------------------------|
|État BLWI (Belgisch Luxemburgs Wissel Instituut).|**Taxe** > **Déclarations** > **Commerce extérieur** > **BLWI** | Pour paramétrer les informations BLWI, voir [Paramétrer la déclaration de la balance des paiements](tasks/be-00011-set-up-payment-balance-reporting.md). Pour générer l'état BLWI, voir [Création et transfert de transactions vers l'état BLWI](tasks/be-00011-create-transfer-blwi.md).| 
|État PRODCOM|**Taxe** > **Déclarations** > **Commerce extérieur** > **PRODCOM**|Les fabricants de produits industriels envoient l'état PRODCOM au Nationaal Instituut voor de Statistiek (NIS), en réponse à l'enquête PRODCOM régulièrement mise en place. L'état PRODCOM affiche les statistiques de production pour les produits industriels fabriqués par des sociétés de production implantées en Belgique. Cet état est généralement utilisé par les chefs comptables et les comptables. Pour plus d'informations, voir [Paramétrer et mettre à jour PRODCOM](emea-bel-prodcom-report.md). |

## <a name="additional-resources"></a>Ressources supplémentaires

- [Portail de localisation Microsoft Dynamics : état belge](https://mbs.microsoft.com/files/customer/AX/Support/supportnews/Belgium.html) (nécessite le compte CustomerSource)
- [Vue d'ensemble des états électroniques](../../dev-itpro/analytics/general-electronic-reporting.md)
- [Télécharger les configurations d'états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
- [Fonctions locales et relatives aux réglementations](../../dev-itpro/lcs-solutions/country-region.md?toc=/fin-and-ops/toc.json)
