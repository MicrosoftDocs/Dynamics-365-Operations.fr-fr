--- 
title: "Approuver les fournisseurs pour des catégories d'approvisionnement spécifiques"
description: "Quand une demande d'achat est créée, il peut y avoir une condition pour choisir un fournisseur agréé ou préféré, selon la façon dont les politiques d'achat sont définies."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 75486202c3fdcaff78a5592389c624d8e21fa969
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Approuver les fournisseurs pour des catégories d'approvisionnement spécifiques

[!include[task guide banner](../../includes/task-guide-banner.md)]

Quand une demande d'achat est créée, il peut y avoir une condition pour choisir un fournisseur agréé ou préféré, selon la façon dont les politiques d'achat sont définies. Cette procédure vous montre comment spécifier qu'un vendeur est agréé ou préféré pour une catégorie spécifique d'approvisionnement. Cette tâche est généralement effectuée par un professionnel de l'approvisionnement. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.

1. Accédez à Approvisionnements > Fournisseurs > Tous les fournisseurs.
2. Choisissez le fournisseur que vous voulez définir en tant que fournisseur agréé ou préféré pour une catégorie.
3. Cliquez sur Général dans le volet Actions.
4. Cliquez sur Catégories.
5. Cliquez sur Ajouter une catégorie.
6. Dans le champ Catégorie, sélectionnez BUREAU ET ACCESSOIRES DE BUREAU (BUREAU ET ACCESSOIRES DE BUREAU).
7. Dans le champ Statut de catégorie de fournisseur, sélectionnez Préféré.
    * Il est possible de spécifier plus d'un fournisseur préféré pour une catégorie.  
8. Cliquez sur Enregistrer.
9. Accédez à Approvisionnements > Catégories d'approvisionnement.
10. Dans l'arborescence, sélectionnez « CATÉGORIES D'APPROVISIONNEMENT DE L'ENTREPRISE\BUREAU ET ACCESSOIRES DE BUREAU ».
11. Développez la section Fournisseurs.
    * Vérifiez si le fournisseur que vous avez choisi apparaît en tant que fournisseur préféré pour la catégorie d'accessoires de bureau et de bureau. Si vous exécutez cette procédure en tant que guide de tâche, vous devrez peut-être cliquer sur le bouton Déverrouiller pour pouvoir faire descendre l'écran jusqu'à la liste de fournisseurs.  Il est également possible d'ajouter les fournisseurs préférés et agréés à cette page.  
12. Dans l'arborescence, développez BUREAU ET ACCESSOIRES DE BUREAU.
13. Dans l'arborescence, sélectionnez Ciseaux.
14. Choisissez Non dans le champ Héritez des fournisseurs de la catégorie parent.
15. Choisissez Oui dans le champ Héritez des fournisseurs de la catégorie parent.

