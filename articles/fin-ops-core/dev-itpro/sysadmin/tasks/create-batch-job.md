---
title: Création d’un traitement par lots
description: Un traitement par lots est un groupe de tâches soumis à une instance Serveur d’objets d’application (AOS) pour un traitement automatique.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4360cd7068658a170f5b44c2ce7c71c39c44fa8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679886"
---
# <a name="create-a-batch-job"></a>Création d’un traitement par lots

[!include [banner](../../includes/banner.md)]

Un traitement par lots est un groupe de tâches soumis à une instance Serveur d’objets d’application (AOS) pour un traitement automatique. L’exécution de traitements par lots utilise les informations d’authentification de sécurité de l’utilisateur qui a créé la tâche. Procédez comme suit pour créer un traitement par lots. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-the-batch-job"></a>Créer le traitement par lots
1. Accédez à **Volet de navigation pane > Modules > Administration système> Recherches > Traitements par lots**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Description de la tâche**.
4. Dans le champ **Date/heure de début réel**, entrez une date et une heure.
5. Cliquez sur **Enregistrer**.

## <a name="create-a-recurrence"></a>Créer une répétition
1. Dans le volet Actions, cliquez sur **Traitement par lots**.
2. Cliquez sur **Répétition**. Utilisez ces options pour entrer une gamme et un modèle pour la répétition.  
3. Cliquez sur **OK**.

## <a name="add-alerts"></a>Ajouter des alertes
1. Dans le volet Actions, cliquez sur **Traitement par lots**.
2. Cliquez sur **Alertes**. Indiquez si vous voulez que des messages d’alerte soient envoyés à la fin du traitement par lots ou lorsque celui-ci rencontre une erreur ou est annulé. Spécifiez ensuite si vous souhaitez que les alertes soient affichées sous la forme de messages contextuels.   
3. Cliquez sur **OK**.

## <a name="adjust-batch-job-status"></a>Ajuster le statut du traitement par lots
1. Accédez à **Administration du système > Recherches > Traitements par lots**.
2. Sélectionnez le traitement par lots approprié.
3. Dans le volet Actions, cliquez sur **Traitement par lots > Fonctions > Modifier le statut**.
4. Sélectionnez le statut approprié :
    - **Retenir** : Définissez le traitement par lots comme **retenu** de sorte qu’il soit différé dans le planificateur de traitement par lots. Équivalent à *arrêter*.
    - **En attente** : Définissez le traitement par lots comme **en attente** pour qu’il attende d’être prélevé par le planificateur de traitement par lots. Équivalent à *lancer*.
5. Cliquez sur **OK**.
