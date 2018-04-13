---
title: Actions de workflow
description: "Cet article décrit les mesures que peut prendre chaque participant au processus d'approbation de workflow."
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bbaac72d8adb764c4b186b022100248b1c5a3804
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="workflow-actions"></a>Actions de workflow

[!INCLUDE [banner](../includes/banner.md)]

Cet article décrit les mesures que peut prendre chaque participant au processus d'approbation de workflow.

Un workflow peut impliquer plusieurs groupes de personnes : l'expéditeur, les personnes affectées aux tâches, les décideurs, et les approbateurs. Par exemple, dans le workflow d'état de dépenses suivant, Sam est l'expéditeur, les membres de la file d'attente sont les personnes affectées aux tâches, John est décideur et Frank, Sue et Ann sont les approbateurs.   

[![Workflow\_WithManualDecision](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif) 

Les sections suivantes expliquent les actions de workflow que chaque groupe peut effectuer.

## <a name="actions-that-an-originator-can-perform"></a>Actions qu'un expéditeur peut effectuer
L'expéditeur commence une instance de workflow en soumettant un document pour traitement. Par exemple, pour que Sam puisse soumettre son état de dépenses, il doit cliquer sur le bouton **Soumettre** sur la page **État de dépenses**.

## <a name="actions-that-a-task-assignee-can-perform"></a>Actions qu'une personne affectée à une tâche peut effectuer
Une tâche peut être affectée à plusieurs personnes ou à une file d'attente des éléments de travail contrôlée par plusieurs personnes. Toutefois, seule une personne peut réaliser une tâche. Supposons que Sam ait soumis un état de dépenses et qu'il ait dirigé ses reçus vers le département des états de dépenses de son organisation pour révision. 

Les membres du département États de dépenses d'Adventure Works surveillent la file d'attente. Supposons que Julie, membre de ce département, ait accepté la tâche de révision de l'état de dépenses et des reçus de Sam. Elle peut désormais effectuer l'une des actions suivantes : terminer, rejeter, déléguer, demander une modification, réaffecter ou lancer. 

**Remarque :** les actions disponibles peuvent varier selon la façon dont le développeur du logiciel a conçu la tâche.

### <a name="complete"></a>Terminer

Lorsqu'un utilisateur termine une tâche, le document qui a été soumis pour traitement est affecté à l'utilisateur suivant dans le workflow, le cas échéant. Si aucun traitement supplémentaire n'est nécessaire, le processus de workflow prend fin. 

Supposons que Julie, membre du département États de dépenses d'Adventure Works, ait accepté la tâche de révision de l'état de dépenses et des reçus de Sam. Lorsqu'elle a terminé sa révision, le document est affecté à John.

### <a name="reject"></a>Rejeter

Lorsqu'un utilisateur rejette un document, le processus de workflow prend fin. 

Supposons que Julie, membre du département États de dépenses d'Adventure Works, ait accepté la tâche de révision de l'état de dépenses et des reçus de Sam. Si Julie rejette l'état de dépenses, le processus de workflow prend fin. 

Sam peut ensuite soumettre à nouveau l'état de dépenses. Il peut effectuer des modifications d'abord, ou soumettre de nouveau la version d'origine. S'il soumet de nouveau l'état de dépenses, le processus de workflow démarre au niveau de la tâche de révision manuelle.

### <a name="delegate"></a>déléguer

Lorsqu'un utilisateur délègue une tâche, celle-ci est affectée à un autre utilisateur. 

Supposons que Julie, membre du département États de dépenses d'Adventure Works, ait accepté la tâche de révision de l'état de dépenses et des reçus de Sam. Julie délègue sa tâche à Tim, son assistant. 

Tim agit alors au nom de Julie. Par conséquent, lorsque Tim termine la tâche, l'état de dépenses est affecté à John, comme si Julie l'avait terminé elle-même.

### <a name="request-change"></a>Demander une modification

Lorsqu'un utilisateur demande la modification d'un document soumis, ce dernier est renvoyé à l'expéditeur. 

Supposons que Julie, membre du département États de dépenses d'Adventure Works, ait accepté la tâche de révision de l'état de dépenses et des reçus de Sam. Julie remarque des erreurs sur l'état de dépenses et demande qu'il soit modifié. L'état de dépenses est renvoyé à Sam. 

Sam peut soumettre de nouveau l'état de dépenses. Il peut effectuer les modifications demandées d'abord, ou soumettre de nouveau la version d'origine. S'il soumet de nouveau l'état de dépenses, un membre de la file d'attente des éléments de travail doit à nouveau examiner l'état de dépenses et les reçus.

### <a name="reassign"></a>Réaffecter

Les membres d'une file d'attente des éléments de travail peuvent réaffecter des documents de cette file d'attente à une autre file d'attente. 

Supposons que Julie, membre du département États de dépenses d'Adventure Works, surveille la file d'attente. Pour répartir la charge de travail, elle peut réaffecter l'état de dépenses, puis les reçus qui lui sont associés, à une autre file d'attente.

### <a name="release"></a>Lancement

Parfois, un membre de la file d'attente des éléments de travail peut accepter une tâche, mais décider ensuite qu'il ne peut pas la terminer. Dans ce cas, la personne ayant accepté la tâche peut relancer le document vers la file d'attente des éléments de travail. 

Supposons que Julie, membre du département États de dépenses d'Adventure Works, ait accepté la tâche de révision de l'état de dépenses et des reçus de Sam. Si Julie décide qu'elle ne peut pas accomplir la tâche, elle peut libérer le document. L'état de dépenses est alors renvoyé vers la file d'attente pour que d'autres membres du département États de dépenses d'Adventure Works puissent terminer la tâche.

## <a name="actions-that-a-decision-maker-can-perform"></a>Actions qu'un décideur peut effectuer
En général, un document est affecté à un décideur lorsque ce dernier doit répondre à une question. Le plus souvent, la réponse à la question est **Oui** ou **Non** ou **Vrai** ou **Faux**. Si le décideur ne choisit pas l'une de ces réponses, il (ou elle) peut déléguer la décision.

### <a name="choice-1-or-choice-2"></a>\[Choix 1\] ou \[Choix 2\]

Un décideur doit impérativement répondre à une question concernant le document. Le plus souvent, la réponse à la question est **Oui** ou **Non** ou **Vrai** ou **Faux**. Le choix de la réponse du décideur détermine la branche de workflow utilisée pour traiter le document. 

Supposons que l'état de dépenses de Sam soit affecté à John. John doit décider si les informations contenues dans le document nécessitent d'appeler le responsable de Sam. Si John décide qu'un appel est nécessaire, l'état de dépenses est affecté à Aretha, qui doit alors appeler le responsable de Sam. Si John décide qu'aucun appel n'est nécessaire, l'état de dépenses est affecté à Frank pour approbation.

### <a name="delegate"></a>Déléguer

Lorsqu'un décideur délègue une décision, le document est affecté à un autre utilisateur qui doit prendre la décision. 

Supposons que l'état de dépenses de Sam soit affecté à John. Ce dernier délègue la décision à Maria, son assistante. 

Maria agit alors au nom de John. Si Maria décide qu'il est nécessaire d'appeler le responsable de Sam, l'état de dépenses est affecté à Aretha, qui doit alors effectuer l'appel. Si Maria décide qu'aucun appel n'est nécessaire, l'état de dépenses est affecté à Frank pour approbation.

## <a name="actions-that-an-approver-can-perform"></a>Actions qu'un approbateur peut effectuer
Lorsqu'un document est affecté à un approbateur, celui-ci peut effectuer l'une des actions suivantes : approuver, rejeter, déléguer ou demander des modifications.

### <a name="approve"></a>Approuver

Lorsqu'un approbateur approuve un document, celui-ci est affecté à l'utilisateur suivant dans le workflow, le cas échéant. Si aucun traitement supplémentaire n'est nécessaire, le processus de workflow prend fin. 

Supposons que Sam ait envoyé un état de dépenses de 6 000 EUR, et que ce document soit affecté à Frank. Lorsque Frank approuve le document, celui-ci est affecté à Sue pour approbation. Lorsque Sue approuve l'état de dépenses, le processus de workflow prend fin.

### <a name="reject"></a>Rejeter

Lorsqu'un approbateur rejette un document, le processus de workflow prend fin. 

Supposons que Sam ait envoyé un état de dépenses de 12 000 EUR, et que ce document soit affecté à Sue. Si Sue rejette l'état de dépenses, le processus de workflow prend fin. 

Sam peut soumettre de nouveau l'état de dépenses. Il peut effectuer les modifications demandées d'abord, ou soumettre de nouveau la version d'origine de l'état de dépenses. Si Sam le soumet de nouveau, le processus de workflow reprend au niveau du processus d'approbation.

### <a name="delegate"></a>Déléguer

Lorsqu'un approbateur délègue un document, ce dernier est affecté à un autre utilisateur pour approbation. 

Supposons que Sam ait envoyé un état de dépenses de 12 000 EUR, et que ce document soit affecté à Frank. Ce dernier délègue l'état de dépenses à Ann. 

Ann agit ensuite au nom de Frank. Par conséquent, lorsque Ann approuve le document, ce dernier est affecté à Sue pour approbation, comme si Frank l'avait approuvé lui-même. Lorsque Sue a approuvé le document, ce dernier est envoyé à Ann pour approbation.

### <a name="request-change"></a>Demander une modification

Lorsqu'un approbateur demande la modification d'un document, ce dernier est renvoyé à l'expéditeur. 

Supposons que Sam ait envoyé un état de dépenses de 12 000 EUR, et que ce document soit affecté à Sue. Si Sue demande une modification, l'état de dépenses est renvoyé à Sam. 

Sam peut soumettre de nouveau l'état de dépenses. Il peut effectuer les modifications demandées d'abord, ou soumettre de nouveau la version d'origine de l'état de dépenses. S'il soumet de nouveau l'état de dépenses, celui-ci est renvoyé à Frank pour approbation, car Frank est le premier approbateur dans le processus d'approbation.




