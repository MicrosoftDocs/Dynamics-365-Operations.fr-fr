---
title: Erreur de quantité correcte totale lors de la tentative de finalisation d’une commande
description: Lorsque vous essayez de finaliser un ordre de production et de déclarer que vous avez terminé, vous pouvez recevoir une erreur de quantité correcte totale. Cette page explique pourquoi et comment résoudre le problème.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5f0c2c2ca64ada9d72c0ebd04e7de561aaa52039
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476326"
---
# <a name="total-good-quantity-error-when-trying-to-end-a-production-order"></a>Erreur de quantité correcte totale lors de la tentative de finalisation d’un ordre de fabrication

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de publier un rapport en tant que journal terminé sur un ordre de fabrication, vous recevez le message d’erreur suivant :

> La quantité correcte totale déclarée terminée en production sera %1. Rétroaction pour la dernière opération de 0,00 au total.

## <a name="cause"></a>Cause

Ce problème se produit si les quantités enregistrées lors des dernières opérations étaient incorrectes. Par exemple, si la production est lancée, mais que la quantité à démarrer n’est pas allouée, le journal des fiches production sera enregistré sans aucune ligne. Pour confirmer la situation, ouvrez l’ordre de fabrication, puis, dans le volet Actions, sur l’onglet **Afficher**, sélectionnez **Fiche production**.

## <a name="resolution"></a>Résolution

Vous pouvez résoudre ce problème en publiant des journaux supplémentaires pour les opérations pour lesquelles les journaux n’ont pas été correctement validés. Redémarrez l’ordre de fabrication et sélectionnez pour valider les journaux supplémentaires. Cette action ne lancera pas l’ordre de fabrication, mais enregistrera les journaux. La fiche production doit alors indiquer les quantités enregistrées et vous devez être en mesure de terminer les ordres de fabrication avec succès.
