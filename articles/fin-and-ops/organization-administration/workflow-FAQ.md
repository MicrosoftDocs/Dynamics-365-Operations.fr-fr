---
title: FAQ Workflow
description: Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509289"
---
# <a name="workflow-system"></a>Système de workflow

[!include [banner](../includes/banner.md)]

Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Notifications

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Pourquoi plusieurs notifications sont-elles reçues lorsqu'un élément de travail est rejeté ?
Lors du rejet d'un élément de travail, ce dernier est défini comme rejeté. Un autre élément de travail est créé et attribué à l'expéditeur. Autrement dit, une notification est envoyée à l'expéditeur concernant le rejet de l'élément de travail et une notification distincte est envoyée à l'utilisateur assigné au nouvel élément de travail « Modification requise ». 

Chaque notification correspond à un élément de travail différent, mais la similarité peut générer une confusion. Nous étudions des façons d'améliorer cela dans une prochaine version.

### <a name="why-are-my-workflow-exports-failing"></a>Pourquoi mes exportations de workflows échouent-elles ?
Il existe actuellement une limitation de la fonctionnalité d'exportation de workflows qui empêche les noms des workflows de dépasser 48 caractères. L'utilisation d'un nom de plus de 48 caractères peut entraîner une erreur « Échec du serveur à authentifier la demande » et/ou pour empêcher qu'un fichier soit exporté sans type de fichier. La publication de blog suivante fournit davantage de détails [Dépannage de l'exportation de workflows](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).
