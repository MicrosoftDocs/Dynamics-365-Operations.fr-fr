---
title: Utilisation des codes motif de stade
description: Un code motif permet d'indiquer pourquoi un contrat de niveau de service a été annulé ou pourquoi la limite de temps définie par un contrat de niveau de service a été dépassée.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4acba8f723ceb3d629671833db59c97a900c9f01
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965703"
---
# <a name="use-stage-reason-codes"></a>Utilisation des codes motif de stade 

[!include [banner](../includes/banner.md)]


Un code motif permet d'indiquer pourquoi un contrat de niveau de service a été annulé ou pourquoi la limite de temps définie par un contrat de niveau de service a été dépassée.

Vous pouvez également indiquer qu'un code motif est nécessaire lorsqu'un contrat SLA est annulé ou lorsque la limite de temps définie dans un contrat SLA a été dépassée.

Si vous avez spécifié qu'un code motif est requis, vous devez entrer un code motif dans les situations suivantes :

  - lorsqu'une commande de service est déplacée à un stade qui arrête l'enregistrement du temps contre le contrat SLA pour cette commande de service ;

  - lorsqu'une commande de service est terminée ;

  - lorsque l'enregistrement du temps est arrêté manuellement.

## <a name="set-up-reason-codes"></a>Paramétrer des codes motif

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Commandes de service** \> **Codes motif du stade**.

2.  Dans l'écran **Codes motif du stade**, cliquez sur **Nouveau** pour créer un code motif de stade.

3.  Dans le champ **Codes motif du stade**, entrez un code motif de stade unique.

4.  Dans le champ **Description**, entrez une description du code motif de stade.

5.  Fermez l'écran pour enregistrer vos modifications.

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a>Demande des codes motif lors de l'annulation d'un contrat de niveau service

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Paramètres de gestion des services**.

2.  Dans l'écran **Paramètres de gestion des services**, cliquez sur le lien **Général**, puis activez la case à cocher **Code motif de l'annulation**.

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a>Demande des codes motif lors du dépassement de la limite de temps définie par le contrat SLA

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Paramètres de gestion des services**.

2.  Dans l'écran **Paramètres de gestion des services**, cliquez sur le lien **Général**, puis activez la case à cocher **Code motif du dépassement de l'heure**.

## <a name="see-also"></a>Voir également :

[Démarrage et arrêt de l'enregistrement de l'heure dans une commande de service](start-and-stop-time-recording-on-a-service-order.md)

  


