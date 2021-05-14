---
title: Vous ne pouvez pas confirmer une expédition car la quantité dépasse le pourcentage de livraison incomplète
description: Vous ne pouvez pas confirmer une expédition car la quantité dépasse le pourcentage de livraison incomplète
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
ms.openlocfilehash: 5339b9d800f7454e2a00c230a8d5deca3979c074
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938467"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a>Vous ne pouvez pas confirmer une expédition car la quantité dépasse le pourcentage de livraison incomplète

Code d’erreur : WAX1687

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une expédition, le système affiche le message d'erreur suivant :

> L'expédition pour le chargement %1 n'a pas pu être confirmée car la quantité pour l'article %2 dépasse le pourcentage défini pour la livraison incomplète.

Par conséquent, vous ne pouvez pas confirmer l'expédition pour le chargement.

## <a name="cause"></a>Cause

La quantité du chargement ou de l'expédition n'a été que partiellement prélevée. La quantité est actuellement inférieure à la quantité prélevée d'un pourcentage qui est en dehors du pourcentage de livraison incomplète autorisé.

## <a name="resolution"></a>Résolution

Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :

- Définissez la quantité de ligne de charge.
- Définissez le pourcentage de livraison incomplète.

### <a name="set-the-load-line-quantity"></a>Définir la quantité de ligne de chargement

Pour définir la quantité de ligne de chargement, procédez comme suit :

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.
1. Sur l'organisateur **Lignes de chargement**, sélectionnez la ligne de chargement de l'article qui dépasse le pourcentage de livraison incomplète.
1. Dans l’organisateur **Détails de ligne**, sélectionnez **Ordre**.
1. Dans le champ **Quantité**, définissez la valeur sur la quantité prélevée (c'est-à-dire sur la valeur **Quantité créée par le travail**), afin que la confirmation d'expédition puisse avoir lieu.

### <a name="set-the-underdelivery-percentage"></a>Définir le pourcentage de livraison incomplète

Pour définir le pourcentage de livraison incomplète, procédez comme suit :

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.
1. Sur l'organisateur **Lignes de chargement**, sélectionnez la ligne de chargement de l'article qui dépasse le pourcentage de livraison incomplète.
1. Dans l’organisateur **Détails de ligne**, sélectionnez **Général**.
1. Dans le champ **Livraison incomplète**, définissez la valeur sur un pourcentage plus élevé qui tient compte de la quantité prélevée par rapport à la quantité de chargement, afin que la confirmation d'expédition puisse avoir lieu.
