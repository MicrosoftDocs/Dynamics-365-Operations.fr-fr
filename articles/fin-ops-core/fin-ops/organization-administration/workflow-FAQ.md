---
title: FAQ Workflow
description: Cette rubrique répond à des questions fréquentes sur le système de workflow.
author: ChrisGarty
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64ce34cf38e4d6f37d9d417b70843a8308a408a8
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890355"
---
# <a name="workflow-faq"></a>FAQ sur les workflows

[!include [banner](../includes/banner.md)]

Cette rubrique répond à des questions fréquentes sur le système de workflow.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Pourquoi plusieurs notifications sont-elles reçues lorsqu’un élément de travail est rejeté ?
Lors du rejet d’un élément de travail, ce dernier est défini comme rejeté. Un autre élément de travail est créé et attribué à l’expéditeur. Autrement dit, une notification est envoyée à l’expéditeur concernant le rejet de l’élément de travail et une notification distincte est envoyée à l’utilisateur assigné au nouvel élément de travail « Modification requise ». 

Chaque notification correspond à un élément de travail différent, mais la similarité peut générer une confusion. Nous étudions des façons d’améliorer cela dans une prochaine version.

## <a name="why-are-my-workflow-exports-failing"></a>Pourquoi mes exportations de workflows échouent-elles ?
Il existe actuellement une limitation de la fonctionnalité d’exportation de workflows qui empêche les noms des workflows de dépasser 48 caractères. L’utilisation d’un nom de plus de 48 caractères peut entraîner une erreur « Échec du serveur à authentifier la demande » et/ou pour empêcher qu’un fichier soit exporté sans type de fichier. La publication de blog fournit davantage de détails, [Dépannage de l’exportation de workflows](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>L’auteur d’un workflow peut-il également approuver le workflow ?
Oui, l’auteur d’un workflow peut également approuver le workflow si il est configuré ainsi. Pour éviter ce comportement, définissez **Administration du système > Workflow > Paramètres de workflow > Général > Approbateur > Ne pas autoriser l’approbation par l’auteur** sur **Oui**.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>Puis-je ajouter des alertes aux workflows pour fournir des notifications aux utilisateurs ?
Voici quelques points clés à noter en ce qui concerne l’ajout d’alertes aux workflows pour fournir des notifications :
- Mécanismes des alertes par rapport aux notifications de workflow
    - Les alertes peuvent être paramétrées pour les modifications d’enregistrement. Les workflows modifient les enregistrements ; il est donc possible de paramétrer une alerte associée à une modification d’enregistrement causée par un workflow. Toutefois, comme des workflows ont différentes options intégrées de notification, avec les alertes n’est pas idéal.
- Notifications standard à partir des workflows 
    - Les workflows ont des notifications par e-mail intégrées. Un client peut configurer les notifications afin que les utilisateurs reçoivent des e-mails. Ces notifications ne snt pas converties en messages du Centre d’action pour les utilisateurs.
    - Dans une prochaine mise à jour, nous ajouterons un message du Centre d’action quand un élément de travail de workflow est affecté à un utilisateur. 
- Ajout de notifications à des workflows
    - Les messages du Centre d’actions peuvent être créés pour des utilisateurs spécifiques, tels qu’un message créé à partir d’un workflow dans X++.
    - [Les workflows comportent des événements commerciaux](../../dev-itpro/business-events/business-events-workflow.md) que le client peut utiliser pour faire en sorte que les flux disposent des notifications dont ils ont besoin.   

En résumé, si un utilisateur ne reçoit pas la notification appropriée en provenance du Centre d’actions lorsqu’un élément de travail de workflow leur est affecté, tirez parti des [Événements commerciaux de workflow](../../dev-itpro/business-events/business-events-workflow.md) avec Microsoft Power Automate pour fournir des notifications supplémentaires ou différentes.

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>Pourquoi l’éditeur de workflow ne peut-il pas démarrer dans AD FS ?
Lors de l’exécution sous Active Directory Federation Services (AD FS) dans un environnement mis à niveau, l’éditeur de workflow peut avoir des problèmes de démarrage. Si tel est le cas, assurez-vous que l’URL « https://dynamicsaxworkfloweditor/ » est ajoutée à la propriété **Microsoft Dynamics 365 for Operations On-premises – Workflow – Application native** dans les paramètres ADFS.

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>Pourquoi des blocages SQL se produisent-ils lors du traitement du workflow ? 
La valeur de champ par défaut pour le **Nombre d’éléments de workflow par traitement par lots** sur la page **Paramètres de workflow** est 0. Une valeur de 0 entraîne la modification de la valeur par défaut à 20 éléments par traitement par lots. Soyez prudent lorsque vous ajustez cette valeur, car un nombre élevé d’éléments par traitement par lots (> 40) peut entraîner des blocages SQL.

## <a name="what-is-the-workflow-enhanced-error-feature"></a>Qu’est-ce que la fonction Erreur de workflow améliorée ?
La fonction Erreur de workflow améliorée de la version 10.0.13 ajoute des codes d’erreur pour différencier les différentes classes d’erreurs de workflow. Les messages d’erreur signalés seront pour la plupart similaires avec des différences mineures pour les rendre plus clairs.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
