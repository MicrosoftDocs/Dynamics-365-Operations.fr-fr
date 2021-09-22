---
title: Un élément d’offre groupée n’est pas pris en charge dans un processus intersociétés
description: L'élément d'offre groupée n'est pas disponible à l'achat. La commande client n'achète que les composants de l'élément d'offre groupée, pas l'élément d'offre groupée lui-même.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 21adc7d071837b762157364f6f8ed370c69c7fd3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476338"
---
# <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Un élément d’offre groupée n’est pas pris en charge dans un processus intersociétés

## <a name="symptoms"></a>Symptômes

L’élément d’offre groupée n’est pas disponible pour la commande fournisseur car, si vous examinez les lignes de commande client pour l’élément d’offre groupée, vous remarquerez que la quantité est *0* (zéro) et l’état est *Annulé*.

## <a name="resolution"></a>Résolution

Ce comportement est fait exprès. La commande client n’achète que les composants de l’élément d’offre groupée. Elle n’achète pas l’élément d’offre groupée lui-même. Si vous devez acheter une offre groupée, déterminez si vous devez la marquer comme élément d’offre groupée, car cette fonctionnalité est conçue pour les scénarios de constatation du produit. Pour plus d’informations sur les éléments d’offre groupée, voir [Offres groupées](/dynamics365/finance/accounts-receivable/revenue-recognition-setup).
