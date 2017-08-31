--- 
title: "Création d'un traitement par lots"
description: "Un traitement par lots est un groupe de tâches soumis à une instance Serveur d'objets d'application (AOS) pour un traitement automatique."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ca2b755406fb7fce4b11457be86f6a8685004438
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-batch-job"></a>Création d'un traitement par lots

[!include[task guide banner](../../includes/task-guide-banner.md)]

Un traitement par lots est un groupe de tâches soumis à une instance Serveur d'objets d'application (AOS) pour un traitement automatique. L'exécution de traitements par lots utilise les informations d'authentification de sécurité de l'utilisateur qui a créé la tâche. Procédez comme suit pour créer un traitement par lots. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-the-batch-job"></a>Créer le traitement par lots
1. Allez dans Administration du système > Recherches > Traitements par lots.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Description de la tâche.
4. Dans le champ Date/heure de début réel, entrez une date et une heure.
5. Cliquez sur Enregistrer.

## <a name="create-a-recurrence"></a>Créer une répétition
1. Dans le volet Actions, cliquez sur Traitement par lots.
2. Cliquez sur Répétition.
    * Utilisez ces options pour entrer une gamme et un modèle pour la répétition.  
3. Cliquez sur OK.

## <a name="add-alerts"></a>Ajouter des alertes
1. Dans le volet Actions, cliquez sur Traitement par lots.
2. Cliquez sur Alertes.
    * Indiquez si vous voulez que des messages d'alerte soient envoyés à la fin du traitement par lots ou lorsque celui-ci rencontre une erreur ou est annulé. Spécifiez ensuite si vous souhaitez que les alertes soient affichées sous la forme de messages contextuels.   
3. Cliquez sur OK.


