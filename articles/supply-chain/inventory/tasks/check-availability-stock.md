---
title: "Vérifier la disponibilité du stock"
description: "Cette procédure vous indique comment contrôler le stock physique disponible pour un article spécifique."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: d103eb52a498e6273b1fdb43fc10dae4133e76b2
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# Vérifier la disponibilité du stock

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous indique comment contrôler le stock physique disponible pour un article spécifique. Elle vous indique également comment obtenir des informations d'approvisionnement associées à un article. Le stock physique disponible représente le stock disponible (c'est-à-dire tout ce qui est acheté, reçu et enregistré). Le stock disponible inclut le stock disponible, mais également le stock commandé et prévu, mais pas encore reçu ou enregistré. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données. Si vous utilisez USMF, vous pouvez utiliser les valeurs des exemples affichées. Ces tâches sont généralement effectuées par un magasinier.


## Vérifier un article dans le stock disponible
1. Accédez à Gestion des stocks > Recherches et états > Stock disponible.
2. Sélectionnez la ligne Numéro d'article.
    * Pour rechercher le stock disponible par numéro d'article, sélectionnez la ligne où Tableau est défini sur Stock disponible et Champ est défini sur Numéro d'article.  
3. Dans le champ Critères, sélectionnez l'article à rechercher.
    * Si vous utilisez la société fictive USMF, vous pouvez sélectionner M9201.  
4. Cliquez sur OK.
5. Cliquez sur Dimensions.
    * L'onglet Dimensions vous permet de sélectionner la quantité de détails à afficher à propos du stock disponible. Si vous avez besoin de données liées à la réservation, vous devez afficher toutes les dimensions de stock pour les articles qui utilisent des processus avancés de l'entrepôt.  
6. Cliquez sur OK.
7. Dans le volet Actions, cliquez sur Informations associées.
    * Si vous ne voyez pas cette option, vous devez cliquer sur le bouton représentant des points de suspension pour afficher les options du volet d'action supplémentaires.  
8. Cliquez sur Vue d'ensemble de l'approvisionnement.
    * L'onglet Vue d'ensemble de l'approvisionnement fournit des informations d'approvisionnement pour un article spécifique, telles que la quantité disponible, le délai, et les informations fournisseur.  
9. Développez la section Disponible.
10. Développez la section Fournisseurs.
11. Fermez la page.
12. Fermez la page.

## Vérifier le stock physique disponible
1. Accédez à Gestion des entrepôts > Recherches et états > Stock physique disponible.
2. Tapez une valeur dans le champ Numéro d'article.
    * Vous pouvez utiliser les champs Site et Entrepôt pour filtrer la liste des articles.  
3. Actualisez la page.
4. Cliquez sur Affichage des dimensions.
    * L'onglet Affichage des dimensions vous permet de sélectionner la quantité de détails à afficher à propos du stock disponible.  
5. Cliquez sur OK.
6. Fermez la page.

## Vérifier le stock disponible par emplacement
1. Accédez à Gestion des entrepôts > Recherches et états > Disponible par emplacement.
2. Tapez une valeur dans le champ Entrepôts.
    * Si vous utilisez la société fictive USMF, vous pouvez utiliser 51.  
3. Actualisez la page.
4. Cliquez sur Affichage des dimensions.
5. Cliquez sur OK.
6. Fermez la page.
