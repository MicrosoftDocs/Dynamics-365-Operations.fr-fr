---
title: Afficher l'historique du flux de travail
description: Cette rubrique décrit les étapes pour afficher le statut d'un document qui a été envoyé au système de workflow pour traitement et approbation.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16c6594161f1fecd36183a6b8f2c798f52d70a9c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189796"
---
# <a name="view-workflow-history"></a>Afficher l'historique du flux de travail

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique décrit les étapes pour afficher le statut d'un document qui a été envoyé au système de workflow pour traitement et approbation. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Allez dans **Volet de navigation > Modules > Commun > Recherches > Workflow > Historique du workflow**.
    - Cet écran permet d'afficher le statut d'un document envoyé au système de workflow pour traitement et approbation.  
    - **ID d'instance** est le code d'identification de l'instance de workflow qui traite ou qui a traité le document.  
    - **Statut** est le statut de workflow du document.  
    - **ID du workflow** est le code d'identification du workflow qui traite ou qui a traité le document.  
    - **Document** est le code d'identification du document.  
    - **Type de document** est le type de document envoyé pour traitement.  
    - **Workflow** est le nom du workflow qui traite ou qui a traité le document.  
    - **Version** est le numéro de version du workflow qui traite ou qui a traité le document.  
    - **Date et heure de création** est la date et l'heure de l'envoi du document.  
    - **Temps écoulé** est le temps qui s'est écoulé depuis l'envoi du document.  
    - Le bouton **Reprendre** vous permet de reprendre le processus du workflow du document sélectionné.  
    - Le bouton **Rappeler** vous permet de rappeler le document sélectionné afin qu'il ne soit pas traité.   
2. Dans la liste, sélectionnez le lien dans la ligne souhaitée.
    - Assurez-vous que la section **Éléments de travail** est développée. Dans cette section, vous pouvez afficher les éléments de travail associés au document sélectionné. Par exemple, il se peut qu'il faille terminer une tâche ou approuver un document.  
    - Le bouton **Réaffecter** ouvre une boîte de dialogue dans laquelle vous pouvez réaffecter un élément de travail à un autre utilisateur.  
    - Assurez-vous que la section **Détails du suivi** est développée. Dans cette section, vous pouvez afficher l'historique du workflow du document sélectionné.  

