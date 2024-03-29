---
title: Déclaration de fin des ordres de fabrication
description: La déclaration de fin correspond à un stade de production. À ce stade, un produit fini est signalé et passé de l’ordre de fabrication au stock.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d509f0f732c1255a87bf810ab9a3bba3f61e2061f9a761ee0797b3fec45e45a3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717074"
---
# <a name="report-production-orders-as-finished"></a>Déclaration de fin des ordres de fabrication

[!include [banner](../includes/banner.md)]

La déclaration de fin correspond à un stade de production. À ce stade, un produit fini est signalé et passé de l’ordre de fabrication au stock.

Lorsqu’un ordre de fabrication est déclaré terminé, la quantité des produits finis déclarés terminés est mise à jour comme disponible dans le stock. Des quantités partielles de la quantité de l’ordre prévisionnel peuvent être déclarées terminées. Il est également possible de déclarer terminées les quantités d’erreur avec un motif d’erreur associé. Lorsque l’ordre de fabrication atteint le stade Déclaré terminé, cela indique qu’aucune quantité supplémentaire ne sera déclarée à l’ordre de fabrication.
Les caractéristiques suivantes sont également associées au processus de **Déclaration de fin** :
-   Il est possible de paramétrer la consommation des matières premières et du temps proportionnelles à la quantité déclarée (post-consommation)
-   Le travail de rangement peut être généré pour les articles activés pour les processus de l’entrepôt.
-   La valeur du coût standard ou prévisionnel des produits finis peut être paramétrée pour être déclarée aux comptes généraux.
-   Un ordre de qualité peut être créé pour la quantité déclarée selon la configuration d’une association de qualité.

La quantité est déclarée à l’emplacement de sortie. Le travail d’entrepôt est alors généré pour déplacer la quantité depuis l’emplacement de sortie vers sa destination finale définie par la directive d’emplacement pour le travail de rangement.

-   Un ordre de qualité peut être créé lorsqu’un ordre de fabrication est déclaré terminé si une association de qualité a été paramétrée.

## <a name="set-a-production-order-to-reporting-as-finished"></a>Définir un ordre de fabrication sur Déclaration de fin
Vous pouvez définir un ordre de fabrication sur **Déclaration de fini** via la fonction standard de mise à jour de l’ordre de fabrication ou via les journaux de gammes et de bons de travail, ou encore via le journal des **déclarations de fin**. Vous pouvez également mettre à jour le stade **Déclaration de fin** via les pages Terminal des bons de travail et Périphérique pour le bon de travail lorsque vous faites une déclaration concernant la dernière tâche de l’ordre de fabrication. Enfin, vous pouvez activer l’option **Déclaration de fin** comme processus pour la solution de l’appareil portable d’entrepôt.  





[!INCLUDE[footer-include](../../includes/footer-banner.md)]