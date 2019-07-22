---
title: FAQ Workflow
description: Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 06/19/2019
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
ms.openlocfilehash: adcc9bbc422a3fddfd51d248daf95c0da6d4c9bb
ms.sourcegitcommit: 8cf77e9171d6cad8ae6c8bfad9e4f9a46fef6d23
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2019
ms.locfileid: "1688998"
---
# <a name="workflow-faq"></a>FAQ sur le workflow

[!include [banner](../includes/banner.md)]

Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Pourquoi plusieurs notifications sont-elles reçues lorsqu'un élément de travail est rejeté ?
Lors du rejet d'un élément de travail, ce dernier est défini comme rejeté. Un autre élément de travail est créé et attribué à l'expéditeur. Autrement dit, une notification est envoyée à l'expéditeur concernant le rejet de l'élément de travail et une notification distincte est envoyée à l'utilisateur assigné au nouvel élément de travail « Modification requise ». 

Chaque notification correspond à un élément de travail différent, mais la similarité peut générer une confusion. Nous étudions des façons d'améliorer cela dans une prochaine version.

## <a name="why-are-my-workflow-exports-failing"></a>Pourquoi mes exportations de workflows échouent-elles ?
Il existe actuellement une limitation de la fonctionnalité d'exportation de workflows qui empêche les noms des workflows de dépasser 48 caractères. L'utilisation d'un nom de plus de 48 caractères peut entraîner une erreur « Échec du serveur à authentifier la demande » et/ou pour empêcher qu'un fichier soit exporté sans type de fichier. La publication de blog suivante fournit davantage de détails [Dépannage de l'exportation de workflows](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>L'auteur d'un workflow peut-il également approuver le workflow ?
Oui, l'auteur d'un workflow peut également approuver le workflow si il est configuré ainsi. Pour éviter ce comportement, définissez **Paramètres de workflow > Général > Approbateur > Ne pas autoriser l'approbation par l'auteur** sur **Oui**.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>Puis-je ajouter des alertes aux workflows pour fournir des notifications aux utilisateurs ?
Voici quelques points clés à noter en ce qui concerne l'ajout d'alertes aux workflows pour fournir des notifications :
- Mécanismes des alertes par rapport aux notifications de workflow
    - Les alertes peuvent être paramétrées pour les modifications d'enregistrement. Les workflows modifient les enregistrements ; il est donc possible de paramétrer une alerte associée à une modification d'enregistrement causée par un workflow. Toutefois, comme des workflows ont différentes options intégrées de notification, avec les alertes n'est pas idéal.
- Notifications standard à partir des workflows 
    - Les workflows ont des notifications par e-mail intégrées. Un client peut configurer les notifications afin que les utilisateurs reçoivent des e-mails. Ces notifications ne snt pas converties en messages du Centre d'action pour les utilisateurs.
    - Dans une prochaine mise à jour, nous ajouterons un message du Centre d'action quand un élément de travail de workflow est affecté à un utilisateur. 
- Ajout de notifications à des workflows
    - Les messages du Centre d'actions peuvent être créés pour des utilisateurs spécifiques, tels qu'un message créé à partir d'un workflow dans X++.
    - [Les workflows comportent des événements commerciaux](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) que le client peut utiliser pour faire en sorte que les flux disposent des notifications dont ils ont besoin.   

En résumé, si un utilisateur ne reçoit pas la notification appropriée en provenance du Centre d'actions lorsqu'un élément de travail de workflow leur est affecté, tirez parti des [Événements commerciaux de workflow](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) avec Microsoft Flow pour fournir des notifications supplémentaires ou différentes.
