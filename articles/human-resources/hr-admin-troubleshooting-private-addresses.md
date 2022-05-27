---
title: Accéder aux adresses privées selon les rôles de sécurité
description: Cette rubrique explique comment résoudre le problème lorsqu’un client ne peut pas accéder aux adresses privées.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 213aada51a477257df0b079c95e74610854b5a4f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689576"
---
# <a name="access-to-private-addresses-by-security-role"></a>Accéder aux adresses privées selon les rôles de sécurité


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problème**

Une fois qu’un client duplique un rôle de sécurité et se connecte avec ce nouveau rôle, le client ne peut pas afficher les adresses marquées comme privées.

**Résolution**

Pour résoudre ce problème, le client doit procéder comme suit pour le rôle de sécurité dupliqué.

1. Accédez à **Administration d’organisation \> Carnet d’adresses global \> Paramètres du carnet d’adresses global**.
2. Sous l’onglet **Sécurité de l’emplacement privé**, déplacez le nouveau rôle de sécurité de la liste **Rôles disponibles** vers la liste **Rôles sélectionnés**.
3. Sélectionnez **Enregistrer**.

![Page des paramètres du carnet d’adresses global.](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
