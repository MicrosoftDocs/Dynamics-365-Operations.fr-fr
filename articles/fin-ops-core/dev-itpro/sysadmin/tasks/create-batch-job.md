---
title: Création d’un traitement par lots
description: Un traitement par lots est un groupe de tâches soumis à une instance Serveur d’objets d’application (AOS) pour un traitement automatique.
author: matapg007
ms.date: 11/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: matgupta
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
ms.openlocfilehash: 06fb9a18e70c316be97645ba76f9462cd3ccc729
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292448"
---
# <a name="create-a-batch-job"></a>Création d’un traitement par lots

[!include [banner](../../includes/banner.md)]

Un traitement par lots est un groupe de tâches soumis à une instance Serveur d’objets d’application (AOS) pour un traitement automatique. L’exécution de traitements par lots utilise les informations d’authentification de sécurité de l’utilisateur qui a créé la tâche. Procédez comme suit pour créer un traitement par lots. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-the-batch-job"></a>Créer le traitement par lots
1. Accédez à **Volet de navigation pane > Modules > Administration système> Recherches > Traitements par lots**.
2. Cliquez sur **Nouveau**.
3. Entrez une description de la tâche de traitement par lots dans le champ **Description de la tâche**.
4. Dans le champ **Date/heure de début réel**, entrez la date et l’heure auxquelles la tâche de traitement par lots doit s’exécuter.
5. Cliquez sur **Enregistrer**.

## <a name="create-a-recurrence"></a>Créer une répétition
1. Dans le volet Actions, cliquez sur **Tâche de traitement par lots**.
2. Sélectionnez **Récurrence**. Utilisez ces options pour entrer une gamme et un modèle pour la répétition.  
3. Cliquez sur **OK**.

## <a name="add-alerts"></a>Ajouter des alertes
1. Dans le volet Actions, cliquez sur **Tâche de traitement par lots**.
2. Sélectionnez **Alertes**. Indiquez si vous voulez que des messages d’alerte soient envoyés à la fin du traitement par lots ou lorsque celui-ci rencontre une erreur ou est annulé. Spécifiez ensuite si vous souhaitez que les alertes soient affichées sous la forme de messages contextuels.   
3. Cliquez sur **OK**.

## <a name="add-a-task-to-a-batch-job"></a>Ajouter une tâche à un traitement par lots
1.  Sur la page **Tâches de traitement par lots**, sélectionnez **Afficher les tâches**.
2.  Cliquez sur **Ctrl+N** pour créer une tâche.
3.  Entrez une description de la tâche de traitement par lots.
4.  Dans le champ **Comptes société**, sélectionnez la base de données de la société dans laquelle la tâche doit s’exécuter.
5.  Dans le champ **Nom de classe**, sélectionnez le processus que la tâche doit exécuter. 
6.  Si nécessaire, sélectionnez un groupe de traitements par lots pour la tâche.

    Les tâches client doivent être attribuées à un tel groupe. Elles sont automatiquement affectées au groupe de traitements par lots par défaut (également appelé groupe de traitements par lots vides).

7.  Cliquez sur **Ctrl+S** pour enregistrer la tâche.
8.  Pour rendre la tâche sélectionnée dépendante d’une autre tâche du travail, sélectionnez la grille **A des conditions**, puis suivez ces étapes pour chaque condition que vous souhaitez définir :

    1. Cliquez sur **Ctrl+N** pour créer une condition.
    2. Sélectionnez l’ID tâche de la tâche parent.
    3. Sélectionnez le statut que la tâche parent doit atteindre pour qu’une tâche dépendante puisse s’exécuter.
    4. Cliquez sur **Ctrl+S** pour enregistrer la condition.

    Si vous définissez plusieurs conditions et que *toutes* les conditions doivent être remplies pour que la tâche dépendante puisse s’exécuter, sélectionnez le type de condition **toutes**. Si la tâche dépendante peut s’exécuter si l’*une* des conditions est remplie, sélectionnez le type de condition **N’importe laquelle**.

9.  Sélectionnez la manière dont les échecs de tâche doivent être traités. Pour ne pas tenir compte de l’échec d’une tâche spécifique, sur l’onglet **Général**, sélectionnez l’option **Ignorer l’échec de la tâche** de cette tâche. Si cette option est sélectionnée, l’échec de la tâche n’entraînera pas celui du traitement. Par ailleurs, le champ **Nombre maximal de nouvelles tentatives** permet d’indiquer le nombre maximal de tentatives d’exécution au-delà duquel la tâche est considérée en échec. Il est recommandé de ne pas définir le champ **Nombre maximal de nouvelles tentatives** sur une valeur supérieure à **5**.

    Pour plus d’informations sur les nouvelles tentatives sur les tâches de traitement par lots, consultez [Activer les nouvelles tentatives sur les tâches de traitement par lots](../retryable-batch.md).

## <a name="adjust-batch-job-status"></a>Ajuster le statut du traitement par lots
1. Accédez à **Administration du système > Recherches > Traitements par lots**.
2. Sélectionnez le traitement par lots approprié.
3. Dans le volet Actions, cliquez sur **Traitement par lots > Fonctions > Modifier le statut**.
4. Sélectionnez le statut approprié :
    - **Retenir** : Définissez le traitement par lots comme **retenu** de sorte qu’il soit différé dans le planificateur de traitement par lots. Équivalent à *arrêter*.
    - **En attente** : Définissez le traitement par lots comme **en attente** pour qu’il attende d’être prélevé par le planificateur de traitement par lots. Équivalent à *lancer*.
5. Cliquez sur **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
