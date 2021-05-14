---
title: Vous ne pouvez pas confirmer une expédition car il n'y a aucune quantité
description: Vous ne pouvez pas confirmer une expédition car il n'y a aucune quantité
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938468"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a>Vous ne pouvez pas confirmer une expédition car il n'y a aucune quantité

Code d'erreur : LoadLineWarningUpdatedToZero

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une expédition, le système affiche le message d'erreur suivant :

> La ligne de chargement de l’article %1 et de l’expédition %2 a été mise à jour pour avoir une quantité nulle en raison d’un paramétrage de livraisons incomplètes qui permet de rien expédier pour cet article.

Par conséquent, vous ne pouvez pas confirmer l'expédition pour le chargement.

## <a name="cause"></a>Cause

Le système évalue si la quantité prélevée est dans les limites attendues, en fonction de la quantité prélevée, de la quantité de la ligne de chargement et du pourcentage de livraisons incomplètes. Si le système constate que la quantité prélevée sur la ligne de chargement est 0 (zéro), vous ne pouvez pas confirmer l'expédition. Par exemple, ce problème peut se produire si le travail a été annulé et que le pourcentage de livraisons incomplètes sur la ligne de chargement est de 100 %.

## <a name="resolution"></a>Résolution

Vérifiez vos lignes de chargement pour vous assurer que le pourcentage et les quantités de livraisons incomplètes sont alignés sur le travail sélectionné.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.
1. Sur l'organisateur **Lignes de chargement**, sélectionnez la ligne de chargement de l'article qui dépasse le pourcentage de livraison incomplète.
1. Modifiez la valeur du champ **Livraison incomplète** ou du champ **Quantité** si nécessaire.

> [!TIP]
> Si le problème n'est toujours pas résolu, vous devrez peut-être effectuer plus de tâches de retrait pour les commandes client associées ou les commandes de transfert jusqu'à ce que la quantité disponible soit alignée sur le chargement ou l'expédition.
