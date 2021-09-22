---
title: Les prix unitaires sur les commandes fournisseur ne sont pas calculés en fonction de la conversion des unités
description: Les prix unitaires sur les commandes fournisseur ne sont pas calculés en fonction de la conversion des unités
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 4695f4661c3abb8ab38e3ca74b513e8529e37d20
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476331"
---
# <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Les prix unitaires sur les commandes fournisseur ne sont pas calculés en fonction de la conversion des unités

## <a name="symptoms"></a>Symptômes

Lorsqu’une unité est modifiée sur une commande fournisseur, les prix de l’accord commercial ne sont pas recalculés en fonction des définitions de la conversion d’unité.

## <a name="cause"></a>Cause

Les prix sont toujours obtenus à partir d’accords commerciaux (ou d’autres paramètres de prix dans le système, tels que les accords de vente ou les prix des articles) et ils sont définis pour une unité.

Si l’unité est modifiée sur une ligne de commande, le système recherche un prix pour la nouvelle unité et applique ce prix. Si aucun prix n’est trouvé pour l’unité, le système n’applique pas de prix. La conversion d’unité ne peut pas être utilisée pour recalculer le prix dans une autre unité. Théoriquement, le prix d’une boîte de dix pourrait ne pas être égal à dix fois le prix d’une boîte.

## <a name="workaround"></a>Solution de contournement

Une façon de contourner ce problème consiste à vous assurer qu’il existe des accords commerciaux pour les unités qui, selon vous, seront utilisées sur les lignes de commande de l’article.
