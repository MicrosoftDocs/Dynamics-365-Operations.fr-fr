---
title: Vous ne pouvez pas confirmer une expédition en raison d'un problème avec le calendrier
description: Vous ne pouvez pas confirmer une expédition en raison d'un problème avec le calendrier
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
ms.openlocfilehash: 8aae45beeef1934760d620874897f46a1cf901995e2b83e148a1d56898d9c717
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735942"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a>Vous ne pouvez pas confirmer une expédition en raison d'un problème avec le calendrier

Code d’erreur : TRX2716

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une expédition, le système affiche le message d'erreur suivant :

> Le type de calendrier %1 nécessite le pointage à l'arrivée et au départ du rendez-vous %2.

Par conséquent, vous ne pouvez pas confirmer l'expédition pour le chargement.

## <a name="cause"></a>Cause

Il existe des rendez-vous actifs pour le chargement. Par exemple, il existe une règle qui exige l'enregistrement de l'arrivée du conducteur. Par conséquent, le chargement est actuellement dans un état où la confirmation d'expédition échoue.

## <a name="resolution"></a>Résolution

Vous devez rechercher et résoudre tous les problèmes liés aux rendez-vous actifs liés au chargement.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.
1. Dans le volet Actions, sous l’onglet **Transport**, dans le groupe **Rendez-vous**, sélectionnez **Planification de rendez-vous**.
1. Utilisez l’une des procédures suivantes :

    - Assurez-vous que l'arrivée/le départ du chauffeur a bien été effectué pour le rendez-vous.
    - Terminez ou annulez le rendez-vous.
    - Désactivez l'option **Arrivée du chauffeur obligatoire** pour la règle de rendez-vous associée.
