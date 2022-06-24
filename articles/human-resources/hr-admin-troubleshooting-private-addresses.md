---
title: Accéder aux adresses privées selon les rôles de sécurité
description: Cet article explique comment résoudre le problème lorsqu’un client ne peut pas accéder aux adresses privées.
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
ms.openlocfilehash: 7102bbcbecec0d88351e796e2c63663d956b86f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849679"
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
