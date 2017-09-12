--- 
title: "Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale"
description: "Cette procédure montre comment calculer des propositions de couverture minimale basées sur des transactions historiques et comment mettre à jour la couverture d'article avec ces propositions."
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d278b20724006ec3b3aa557738e8b130ca2bba15
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment calculer des propositions de couverture minimale basées sur des transactions historiques et comment mettre à jour la couverture d'article avec ces propositions. Cette opération est effectuée à l'aide du journal du stock de sécurité. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF. Cette tâche est destinée au responsable de production, pour aider à maintenir la couverture minimale.


## Créer un nouveau nom de journal de stock
1. Allez dans Noms du journal du stock de sécurité.
2. Cliquez sur Nouveau.
3. Tapez Matériel dans le champ Nom.
4. Tapez Matériel dans le champ Description.
5. Fermez la page.

## Créer un journal du stock de sécurité
1. Allez dans Calcul du stock de sécurité.
2. Cliquez sur Nouveau.
3. Saisissez ou sélectionnez une valeur dans le champ Nom.
    * Choisissez le nom du journal de stock de sécurité que vous avez créé, par exemple, Matériel.  
4. Cliquez sur Créer des lignes.
5. Entrez une date dans le champ Date de début.
    * Définissez la date 02/01/2015.  
6. Entrez une date dans le champ Date de fin.
    * Définissez la date 30/12/2015.  
7. Cliquez sur OK.
    * Ceci créera des lignes pour les dimensions qui ont des mouvements de stock.  

## Calculer la proposition
1. Cliquez sur Calculer la proposition.
2. Sélectionnez l'option Utiliser la sortie moyenne pendant le délai.
3. Définissez le facteur de multiplication sur 10.
    * Le facteur de multiplication est employé pour ajuster la proposition. Les données de démonstration ne contiennent que quelques transactions, vous devrez donc définir le facteur pour obtenir une proposition réaliste.  
4. Cliquez sur OK.
    * Faites défiler vers le bas jusqu'à M0002 et M0003. Affichez la colonne Quantité minimale calculée.   

## Mettre à jour la quantité minimale
1. Entrez un nombre dans le champ Nouvelle quantité minimale.
    * Mettre à jour la nouvelle quantité minimale pour correspondre à la valeur de la quantité minimale calculée. Si le minimum calculé est zéro, vous pouvez entrer la valeur future désirée. Par exemple, vous pouvez entrer la quantité minimale calculée dans ce champ pour M0002 qui a l'entrepôt 12.  
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Par exemple, vous pouvez choisir M0002 qui a l'entrepôt 12.  
3. Entrez un nombre dans le champ Nouvelle quantité minimale.
    * Mettre à jour la nouvelle quantité minimale pour correspondre à la valeur de la quantité minimale calculée. Si le minimum calculé est zéro, vous pouvez entrer la valeur future désirée.  

## Valider la nouvelle quantité minimale et contrôler le résultat
1. Cliquez sur Valider.
2. Cliquez sur OK.
3. Cliquez pour suivre le lien dans le champ Numéro d'article.
4. Cliquez pour suivre le lien dans le champ Numéro d'article.
5. Cliquez sur Planifier dans le volet Actions.
6. Cliquez sur Couverture de l'article.
    * Notez que la quantité minimale a été mise à jour avec la nouvelle quantité minimale du journal du stock de sécurité.  


