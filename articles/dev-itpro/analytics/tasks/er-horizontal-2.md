--- 
title: "Exécuter un format qui utilise des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format d'états électroniques pour générer des états en tant que fichiers de feuilles de calcul (Excel) OPENXML dans lesquels les colonnes requises peuvent être créées dynamiquement sous forme de plages extensibles horizontalement."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.openlocfilehash: 2d705d0d2803b5254adc27e6715c1eac311898a7
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="run-a-format-that-uses-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports"></a>Exécuter un format qui utilise des plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format d'états électroniques pour générer des états en tant que fichiers de feuilles de calcul (Excel) OPENXML dans lesquels les colonnes requises peuvent être créées dynamiquement sous forme de plages extensibles horizontalement. Ces étapes peuvent être effectuées dans la société DEMF.

Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les plages extensibles horizontalement pour ajouter dynamiquement des colonnes dans les états Excel (Partie 1 : Créer un format) ».

Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="find-created-format"></a>Rechercher le format créé
1. Accédez à Administration d'organisation > États électroniques > Configurations.
2. Dans l'arborescence, développez « Exemple de modèle de dimensions financières ».
3. Dans l'arborescence, sélectionnez « Exemple de modèle de dimensions financières\Exemple d'état avec des plages extensibles horizontalement ».

## <a name="execute-format-to-create-excel-output"></a>Exécuter le format pour créer la sortie Excel
1. Cliquez sur Exécuter.
2. Dans le champ Nom de dimension, tapez « BusinessUnit;CostCenter;Department ».
    * Dans le champ Nom de dimension, entrez ou sélectionnez une valeur.  Pour sélectionner toutes les dimensions de la société actuelle, entrez les informations suivantes : BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
3. Développez les enregistrements pour inclure la section.
4. Cliquez sur Filtre.
5. Sélectionnez la ligne de la table Journaux comptables et du champ Numéro de lot du journal.
6. Dans le champ Critères, tapez « 00057..00058 ».
    * 00057..00058  
7. Cliquez sur OK.
8. Cliquez sur OK.
    * Examinez la sortie générée. Notez que le fichier Excel nouvellement créé contient le même nombre de colonnes sélectionnées que pour les dimensions financières. L'en-tête d'état de ces colonnes représente les noms des dimensions financières. Les lignes de transactions de ces colonnes représentent les dimensions financières. Exécutez cet état et sélectionnez différentes dimensions pour vérifier que l'état n'est pas dépendant du nombre de dimensions sélectionnées ou du nombre de dimensions configurées pour cette instance de Dynamics 365 for Finance and Operations.  


