---
title: Accès aux adresses privées selon les rôles de sécurité
description: Cette rubrique explique comment résoudre le problème où un client ne peut pas accéder aux adresses privées.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 58f3322ad64f7de07e17d193ff665bd6536a4070
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897095"
---
# <a name="access-to-private-addresses-by-security-role"></a>Accès aux adresses privées selon les rôles de sécurité

**Problème**

Une fois qu'un client duplique un rôle de sécurité et se connecte avec ce nouveau rôle, le client ne peut pas afficher les adresses marquées comme privées.

**Résolution**

Pour résoudre ce problème, le client doit procéder comme suit pour le rôle de sécurité dupliqué.

1. Accédez à **Administration d'organisation \> Carnet d'adresses global \> Paramètres du carnet d'adresses global**.
2. Sous l'onglet **Sécurité de l'emplacement privé**, déplacez le nouveau rôle de sécurité de la liste **Rôles disponibles** vers la liste **Rôles sélectionnés**.
3. Sélectionnez **Enregistrer**.

![Page des paramètres du carnet d'adresses global](media/GAD-parameters.png)
