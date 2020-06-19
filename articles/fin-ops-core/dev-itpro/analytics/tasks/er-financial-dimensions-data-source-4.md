---
title: ER Utiliser les dimensions financières comme source de données (Partie 4 - Exécuter le rapport)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9a6f07d6c665097fabab4d3ec6d7fa5ba80b65d
ms.sourcegitcommit: d9125c20b21459076e4fd92fd9ebfe2e53a0431b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2020
ms.locfileid: "3406472"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER Utiliser les dimensions financières comme source de données (Partie 4 - Exécuter le rapport)

[!include [banner](../../includes/banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER. Ces étapes peuvent être effectuées dans la société DEMF.

Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les dimensions financières comme source de données (Partie 3 : créer l'état) ». Vous devez également configurer les types de document par défaut sur la page Paramètres de gestion des états électroniques. Les types de document par défaut sont également définis lorsque vous téléchargez et importez une configuration ER. 


## <a name="run-report"></a>Exécuter l'état
1. Accédez à Administration d'organisation > États électroniques > Configurations.
2. Dans l'arborescence, développez « Exemple de modèle de dimensions financières ».
3. Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières\État du journal comptable ».
4. Cliquez sur Exécuter.
![Page Configurations d'ER](../media/er-financial-dimensions-guides-run1.png)
5. Dans le champ Nom de dimension, entrez ou sélectionnez une valeur.
    * Pour sélectionner toutes les dimensions de la société actuelle, entrez les informations suivantes : BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
![Page Configurations d'ER](../media/er-financial-dimensions-guides-run2.png)
6. Développez les enregistrements pour inclure la section.
7. Cliquez sur Filtre.
8. Sélectionnez la ligne de la table Journaux comptables et du champ Numéro de lot du journal.
9. Dans le champ Critères, tapez « 00057 ».
10. Cliquez sur OK.
11. Cliquez sur OK.
![Page Configurations d'ER](../media/er-financial-dimensions-guides-run3.png)
    * Examinez la sortie générée. Pour chaque transaction du lot sélectionné, les dimensions financières de l'ensemble de dimensions correspondant sont présentées. Exécutez cet état et sélectionnez différentes dimensions pour vérifier que l'état n'est pas dépendant du nombre de dimensions sélectionnées ou du nombre de dimensions configurées pour cette instance.  
![Page Configurations d'ER](../media/er-financial-dimensions-guides-run4.png)
