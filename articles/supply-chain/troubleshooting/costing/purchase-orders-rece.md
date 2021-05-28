---
title: Les bons de commande reçus physiquement n'apparaissent pas dans le rapport de clôture des stocks
description: Les bons de commande reçus physiquement n'apparaissent pas dans le rapport de clôture des stocks Vérifier les quantités en cours.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026507"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>Les bons de commande reçus physiquement n'apparaissent pas dans le rapport de clôture des stocks

Numéro de la base de connaissances : 4612595

## <a name="symptoms"></a>Symptômes

Les bons de commande reçus physiquement n'apparaissent pas dans le rapport de clôture des stocks **Vérifier les quantités en cours**.

## <a name="resolution"></a>Résolution

Le rapport **Vérifier les quantités en cours** affiche les mouvements de sortie qui ne peuvent pas être réglés par rapport aux réceptions de stock mises à jour financièrement à la date de clôture sélectionnée. Vous pouvez choisir d'inclure les reçus physiques dans le rapport. Dans ce cas, les reçus physiques seront affichés s'ils peuvent couvrir les transactions d'émission qui ne peuvent pas être réglées. =Pour plus d’informations, voir [Préparation de l'exécution de la clôture de stock](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
