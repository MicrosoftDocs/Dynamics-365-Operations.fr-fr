---
title: Déconnexion du client
description: Cette rubrique explique comment procéder si le client est déconnecté de l’environnement.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b15c5db19f1b07e3d469986ac700138ecb1d1525
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071133"
---
# <a name="client-disconnects"></a>Déconnexion du client


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Détails de l’environnement** 

Ce problème peut se produire dans tous les environnements.
 
**Symptôme** 

Le client est déconnecté de l’environnement et ne sait pas pourquoi. Le client reçoit un des messages d’erreur suivants :

- Votre connexion a été perdue. Cliquez sur Fermer pour continuer de travailler.
- Il semble que la connectivité réseau soit perdue. Cliquez sur Réessayer pour faire une nouvelle tentative.

**Alerte**

Ce problème se produit souvent lorsque les utilisateurs se trouvent à l’étape d’implémentation, comparent des informations entre les environnements de production et de test, puis oublient qu’ils passent d’une session à l’autre. Si les utilisateurs sont à cette étape, ils rencontreront probablement ce problème.

**Sortie** 

**Types de navigateur :** Google Chrome, Internet Explorer et Microsoft Edge

Microsoft Dynamics 365 Human Resources déconnecte les utilisateurs lorsque deux sessions différentes sont ouvertes en même temps pour le même utilisateur et le même type de navigateur. (Par exemple, l’utilisateur A affiche l’environnement 1 et l’environnement 2 dans chrome). Peu importe que les utilisateurs ouvrent différentes fenêtres de navigateur ou différents onglets. Si les mêmes informations d’identification de l’utilisateur sont utilisées pour se connecter à l’environnement 1 et à l’environnement 2 en même temps et dans le même type de navigateur, Human Resources déconnecte une des sessions.

**Solution**

Assurez-vous qu’un seul environnement est ouvert à la fois pour un type de navigateur donné. Les utilisateurs peuvent ouvrir plusieurs sessions dans le même environnement (c’est-à-dire, plusieurs onglets dans le même navigateur).

Les utilisateurs qui souhaitent passer d’un environnement à l’autre en même temps doivent ouvrir chaque environnement dans un type de navigateur différent. (Par exemple, l’utilisateur A peut afficher l’environnement 1 dans Chrome et l’environnement 2 dans Microsoft Edge.)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
