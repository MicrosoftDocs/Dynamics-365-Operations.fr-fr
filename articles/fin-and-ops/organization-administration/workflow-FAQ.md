---
title: FAQ Workflow
description: Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2019
ms.locfileid: "773209"
---
# <a name="workflow-system"></a>Système de workflow

[!include [banner](../includes/banner.md)]

Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Notifications

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Pourquoi plusieurs notifications sont-elles reçues lorsqu'un élément de travail est rejeté ?
Lors du rejet d'un élément de travail, ce dernier est défini comme rejeté. Un autre élément de travail est créé et attribué à l'expéditeur. Autrement dit, une notification est envoyée à l'expéditeur concernant le rejet de l'élément de travail et une notification distincte est envoyée à l'utilisateur assigné au nouvel élément de travail « Modification requise ». 

Chaque notification correspond à un élément de travail différent, mais la similarité peut générer une confusion. Nous étudions des façons d'améliorer cela dans une prochaine version.
