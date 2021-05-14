---
title: Vous ne pouvez pas confirmer une expédition car les articles n'ont pas été retirés
description: Vous ne pouvez pas confirmer une expédition car les articles n'ont pas été retirés
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938469"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Vous ne pouvez pas confirmer une expédition car les articles n'ont pas été retirés

Code d'erreur : LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une expédition, le système affiche le message d'erreur suivant :

> Certains des articles nécessaires pour le chargement %1 n'ont pas encore été prélevés et ont été déplacés vers l'emplacement d'expédition final.

Par conséquent, vous ne pouvez pas confirmer l'expédition pour le chargement.

## <a name="cause"></a>Cause

Le chargement ou l'expédition ne peut pas être confirmé dans son état actuel car l'une des conditions suivantes peut exister :

- Le travail associé n'a pas encore été sélectionné et déplacé vers le lieu d'expédition final.
- La quantité retirée ne correspond pas à celle créée sur la ligne de chargement.

## <a name="resolution"></a>Résolution

Vérifiez les commandes client associées ou les commandes de transfert pour le chargement ou l'expédition. Assurez-vous que tous les travaux connexes ont été effectués à l'emplacement d'expédition finale et que les quantités correspondent.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.
1. Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.
1. Notez la valeur du champ **Quantité créée**.
1. Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.
1. Vérifiez que le travail a été terminé à l'emplacement d'expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.
1. Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.
