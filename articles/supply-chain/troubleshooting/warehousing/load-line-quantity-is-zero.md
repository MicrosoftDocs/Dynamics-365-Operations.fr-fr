---
title: Vous ne pouvez pas confirmer une expédition, car les lignes de chargement n’ont aucune quantité
description: Vous ne pouvez pas confirmer une expédition, car les lignes de chargement n’ont aucune quantité.
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 5dc5f8962ba37d21d7ef505fea940dc8767a9d9295588cb0e12e9eebe379a35c
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012167"
---
# <a name="you-cant-confirm-a-shipment-because-load-lines-have-zero-quantity"></a>Vous ne pouvez pas confirmer une expédition, car les lignes de chargement n’ont aucune quantité

Code d’erreur : WAX:LoadTableWarningAllLinesZero, WAX2543

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une expédition, le système affiche le message d’erreur suivant :

> Toutes les lignes du chargement %1 présentent la quantité zéro.  
> Impossible de confirmer l’expédition pour le chargement %1.

Par conséquent, vous ne pouvez pas confirmer l’expédition pour le chargement.

## <a name="cause"></a>Cause

Le système évalue si la ligne de chargement peut faire l’objet d’une confirmation d’expédition, en fonction des ID de travail créés, de la quantité de la ligne de chargement et du pourcentage de sous-livraison. Si le système constate qu’il n’y a pas d’ID de travail et si le pourcentage de sous-livraison est défini sur 100 %, vous ne pouvez pas confirmer l’expédition.

Par exemple, ce problème peut se produire si le travail a été annulé et que le pourcentage de livraisons incomplètes sur la ligne de chargement est de 100 %.

## <a name="resolution"></a>Résolution

Le chargement ou l’expédition est actuellement dans un état d’échec. Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :

- Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.
- Examiner vos lignes de chargement pour vous assurer que le pourcentage et les quantités de livraisons incomplètes sont alignés sur le travail sélectionné.

### <a name="review-your-load-lines-to-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent

Procédez comme suit pour examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Ouvrez le chargement pour lequel l’expédition ne peut pas être confirmée.
1. Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.
1. Notez la valeur du champ **Quantité créée**.
1. Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.
1. Vérifiez que le travail a été terminé à l’emplacement d’expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.
1. Si vous trouvez une incohérence, annulez le travail concerné, reconfigurez la directive de localisation et libérez à nouveau la charge. Pour obtenir des instruction, voir [Vous ne pouvez pas confirmer une expédition, car les articles n’ont pas été prélevés](picked-quantity-is-not-on-final.md).
1. Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.

### <a name="review-your-load-lines-to-make-sure-that-the-underdelivery-percentage-and-quantities-are-aligned-with-the-picked-work"></a>Examinez vos lignes de chargement pour vous assurer que le pourcentage et les quantités de livraisons incomplètes sont alignés sur le travail sélectionné

Utilisez la procédure suivante pour examinez vos lignes de chargement pour vous assurer que le pourcentage et les quantités de livraisons incomplètes sont alignés sur le travail sélectionné.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Ouvrez le chargement pour lequel l’expédition ne peut pas être confirmée.
1. Sur l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui dépasse le pourcentage de livraison incomplète.
1. Modifiez la valeur du champ **Livraison incomplète** ou du champ **Quantité** si nécessaire.

> [!TIP]
> Si le problème n’est toujours pas résolu, vous devrez peut-être effectuer plus de tâches de retrait pour les commandes client associées ou les commandes de transfert jusqu’à ce que la quantité disponible soit alignée sur le chargement ou l’expédition.
