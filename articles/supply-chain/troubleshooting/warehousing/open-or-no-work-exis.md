---
title: Vous ne pouvez pas confirmer une expédition car un élément est manquant ou incomplet
description: Vous ne pouvez pas confirmer une expédition car un élément est manquant ou incomplet
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 59def4427f9fff32fd3839bb9f9b5d5cccdc7720f92a84f1af3adad596d8b352
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730056"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a>Vous ne pouvez pas confirmer une expédition car un élément est manquant ou incomplet

Code d’erreur : WAX515

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une expédition, le système affiche le message d’erreur suivant :

> Impossible de confirmer l’expédition pour le chargement %1, car l’ensemble du travail pour le chargement doit être terminé.

Par conséquent, vous ne pouvez pas confirmer l’expédition pour le chargement.

## <a name="cause"></a>Cause

Le chargement ou l’expédition est actuellement dans un état d’échec. Avant de pouvoir confirmer l’expédition, il doit au moins exister certains travaux pour le chargement, et ils doivent tous avoir le statut *Clôturé* ou *Annulé*.

## <a name="resolution"></a>Résolution

Vérifiez les commandes client ou les ordres de transfert associés pour le chargement ou l’expédition, et assurez-vous que tous les travaux connexes ont été terminés ou annulés.

Vous pouvez travailler avec des expéditions et des chargements sur plusieurs pages. Les sous-sections suivantes fournissent quelques exemples.

### <a name="all-loads-page"></a>Page Tous les chargements

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel l’expédition ne peut pas être confirmée.
1. Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.
1. Inspectez le statut de chaque ID de travail. Faites le suivi de chaque ID de travail qui n’a pas le statut *Clôturé* ou *Annulé*.
1. Lorsque chaque ID de travail a un statut *Clôturé* ou *Annulé*, réessayez pour confirmer l’expédition.

### <a name="all-shipments-page"></a>Page Toutes les expéditions

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.
1. Sélectionnez l’expédition qui ne peut pas être confirmée.
1. Dans le volet Actions, sous l’onglet **Expéditions**, dans le groupe **Travail**, cliquez sur **Détails du travail**.
1. Inspectez le statut de chaque ID de travail. Faites le suivi de chaque ID de travail qui n’a pas le statut *Clôturé* ou *Annulé*.
1. Lorsque chaque ID de travail a un statut *Clôturé* ou *Annulé*, réessayez pour confirmer l’expédition.

### <a name="all-work-page"></a>Page Tout le travail

1. Accédez à **Gestion des entrepôts \> Travail\> Tout le travail**.
1. Sélectionnez le travail correspondant au numéro de commande pour lequel l’expédition ne peut pas être confirmée.
1. Dans le volet Actions, sous l’onglet **Expédition**, dans le groupe **Expédition**, sélectionnez **Confirmer l’expédition**.
1. Inspectez le statut de chaque ID de travail. Faites le suivi de chaque ID de travail qui n’a pas le statut *Clôturé* ou *Annulé*.
1. Lorsque chaque ID de travail a un statut *Clôturé* ou *Annulé*, réessayez pour confirmer l’expédition.
