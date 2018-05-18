--- 
title: "Exécuter un état qui utilise les dimensions financières comme sources de données"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 47ba48461a1c502a93df416d1acac1e85a841079
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="run-a-report-that-uses-financial-dimensions-as-a-data-source"></a>Exécuter un état qui utilise les dimensions financières comme sources de données

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER. Ces étapes peuvent être effectuées dans la société DEMF.

Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 3 : créer l'état) ». Vous devez également configurer les types de document par défaut sur la page Paramètres de gestion des états électroniques. Les types de document par défaut sont également définis lorsque vous téléchargez et importez une configuration ER. 


## <a name="run-report"></a>Exécuter l'état
1. Accédez à Administration d'organisation > États électroniques > Configurations.
2. Dans l'arborescence, développez « Exemple de modèle de dimensions financières ».
3. Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières\État du journal comptable ».
4. Cliquez sur Exécuter.
5. Dans le champ Nom de dimension, entrez ou sélectionnez une valeur.
    * Pour sélectionner toutes les dimensions de la société actuelle, entrez les informations suivantes : BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
6. Développez les enregistrements pour inclure la section.
7. Cliquez sur Filtre.
8. Sélectionnez la ligne de la table Journaux comptables et du champ Numéro de lot du journal.
9. Dans le champ Critères, tapez « 00057 ».
10. Cliquez sur OK.
11. Cliquez sur OK.
    * Examinez la sortie générée. Notez que pour chaque transaction du lot sélectionné, les dimensions financières de l'ensemble de dimensions correspondant sont présentées. Exécutez cet état et sélectionnez différentes dimensions pour vérifier que l'état n'est pas dépendant du nombre de dimensions sélectionnées ou du nombre de dimensions configurées pour cette instance de Dynamics 365 for Finance and Operations.  


