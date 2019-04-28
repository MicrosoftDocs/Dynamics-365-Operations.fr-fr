---
title: Le client Talent se déconnecte
description: Cette rubrique explique comment procéder si le client est déconnecté de son environnement et ne sait pas pourquoi.
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
ms.openlocfilehash: 885e2d743cd2b01588546327840508f6f7e95958
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "859918"
---
# <a name="talent-client-disconnects"></a>Le client Talent se déconnecte

[!include [banner](includes/banner.md)]

**Détails de l'environnement** 

Ce problème peut se produire dans tous les environnements.
 
**Symptôme** 

Le client est déconnecté de son environnement et ne sait pas pourquoi. Le client reçoit un des messages d'erreur suivants :

- Votre connexion a été perdue. Cliquez sur Fermer pour continuer de travailler.
- Il semble que la connectivité réseau soit perdue. Cliquez sur Réessayer pour faire une nouvelle tentative.

**Alerte**

Ce problème se produit souvent lorsque les utilisateurs se trouvent à l'étape d'implémentation, comparent des informations entre les environnements de production et de test, puis oublient qu'ils passent d'une session à l'autre. Si les utilisateurs sont à cette étape, ils rencontreront probablement ce problème.

**Problème** 

**Types de navigateur :** Google Chrome, Internet Explorer et Microsoft Edge

La plateforme Microsoft Dynamics 365 for Talent déconnecte les utilisateurs lorsque deux sessions différentes sont ouvertes en même temps pour le même utilisateur et le même type de navigateur. (Par exemple, l'utilisateur A affiche l'environnement 1 et l'environnement 2 dans chrome). Peu importe que les utilisateurs ouvrent différentes fenêtres de navigateur ou différents onglets. Si les mêmes informations d'identification de l'utilisateur sont utilisées pour se connecter à l'environnement 1 et à l'environnement 2 en même temps et dans le même type de navigateur, Talent déconnecte une des sessions.

**Solution**

Assurez-vous qu'un seul environnement est ouvert à la fois pour un type de navigateur donné. Les utilisateurs peuvent ouvrir plusieurs sessions dans le même environnement (c'est-à-dire, plusieurs onglets dans le même navigateur).

Les utilisateurs qui souhaitent passer d'un environnement à l'autre en même temps doivent ouvrir chaque environnement dans un type de navigateur différent. (Par exemple, l'utilisateur A peut afficher l'environnement 1 dans Chrome et l'environnement 2 dans Microsoft Edge.)
