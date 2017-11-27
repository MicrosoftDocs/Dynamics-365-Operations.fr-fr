--- 
title: "Créer le format pour effectuer le comptage et la synthèse pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée."
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
ms.sourcegitcommit: 5d4f57ae2a309d9e15c1afe60c3e91d7d7eb3870
ms.openlocfilehash: 3c4ae958a03d4681a85f5b83d81fe64b9ac99cf5
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-format-for-counting-and-summing-for-electronic-reporting-er"></a>Créer le format pour effectuer le comptage et la synthèse pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques (ER) pour effectuer le comptage et la synthèse en fonction des données de la sortie de texte déjà générée. Ces étapes peuvent être effectuées dans n'importe quelle société.

Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».

Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Accéder à la liste des configurations fournies par Microsoft
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
    * Assurez-vous que le fournisseur « Litware, Inc. » est disponible et marqué comme actif.  
2. Sélectionnez le fournisseur « Litware, Inc. » .
3. Cliquez sur Référentiels.
    * Si un référentiel du type « Ressources opérationnelles » existe déjà, ignorez les étapes restantes de la sous-tâche actuelle.  
4. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
5. Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».
6. Cliquez sur Créer un référentiel.
7. Cliquez sur OK.

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>Obtenir les configurations de déclaration d'échanges de biens fournies par Microsoft
1. Cliquez sur Ouvrir.
2. Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».
3. Cliquez sur Importer.
    * Cliquez sur Importer pour la version 1.1 de la configuration sélectionnée.  
4. Cliquez sur Oui.
5. Fermez la page.
6. Fermez la page.
7. Cliquez sur Configurations des états.
8. Dans l'arborescence, développez « Modèle de déclaration d'échanges de biens ».
9. Dans l'arborescence, sélectionnez « Modèle de déclaration d'échanges de biens\Déclaration d'échanges de biens (Allemagne) ».


