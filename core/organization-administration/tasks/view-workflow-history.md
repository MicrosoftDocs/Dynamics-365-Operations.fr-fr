--- 
title: Afficher l'historique du workflow
description: "Utilisez ces étapes pour afficher le statut d'un document envoyé au système de workflow pour traitement et approbation."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a0e16467972596ad6d8b0d9785e68b487150781c
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="view-workflow-history"></a>Afficher l'historique du workflow

[!include[task guide banner](../../includes/task-guide-banner.md)]

Utilisez ces étapes pour afficher le statut d'un document envoyé au système de workflow pour traitement et approbation. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Accédez à Commun > Recherches > Workflow > Historique du workflow.
    * Cet écran permet d'afficher le statut d'un document envoyé au système de workflow pour traitement et approbation.  
    * L'ID d'instance est le code d'identification de l'instance de workflow qui traite ou qui a traité le document.  
    * Statut est le statut de workflow du document.  
    * ID du workflow est le code d'identification du workflow qui traite ou qui a traité le document.  
    * Document est le code d'identification du document.  
    * Type de document est le type de document envoyé pour traitement.  
    * Workflow est le nom du workflow qui traite ou qui a traité le document.  
    * Version est le numéro de version du workflow qui traite ou qui a traité le document.  
    * Date et heure de création est la date et l'heure de l'envoi du document.  
    * Temps écoulé est le temps qui s'est écoulé depuis l'envoi du document.  
    * Le bouton Reprendre vous permet de reprendre le processus du workflow du document sélectionné.  
    * Le bouton Rappeler vous permet de rappeler le document sélectionné afin qu'il ne soit pas traité.   
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Assurez-vous que la section Éléments de travail est développée.    Dans cette section, vous pouvez afficher les éléments de travail associés au document sélectionné. Par exemple, il se peut qu'il faille terminer une tâche ou approuver un document.  
    * Le bouton Réaffecter ouvre une boîte de dialogue dans laquelle vous pouvez réaffecter un élément de travail à un autre utilisateur.  
    * Assurez-vous que la section Détails du suivi est développée.    Dans cette section, vous pouvez afficher l'historique du workflow du document sélectionné.  


