--- 
title: "Cycle de vie d'un lot de commandes de la création au démarrage"
description: "Cette procédure vous guide dans la première partie du cycle de vie d'un lot de commandes."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 94f706241545282fd2744c3be4edc253f2998aff
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="batch-order-lifecycle-from-create-to-start"></a>Cycle de vie d'un lot de commandes de la création au démarrage

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous guide dans la première partie du cycle de vie d'un lot de commandes.

De la création, à l'estimation de coût, en passant par la planification des tâches de production, jusqu'au lancement réel d'un lot de commandes.



Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. 



Les conditions préalables à l'exécution de la procédure avec un autre ensemble de données sont un produit lancé avec une formule active et une version de gamme.


## <a name="create-a-batch-order"></a>Création d'un lot de commandes
1. Accédez à Tous les ordres de fabrication.
2. Cliquez sur Nouveau lot de commandes.
3. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
4. Cliquez sur Créer.
5. Utilisez le filtre rapide pour filtrer sur le champ Production avec une valeur de « b ».

## <a name="view-production-formula-and-expected-co-products"></a>Afficher la formule de production et les coproduits prévus
1. Cliquez sur Ordre de fabrication dans le volet Actions.
2. Cliquez sur Formule.
3. Fermez la page.
4. Cliquez sur Co-produits.
5. Fermez la page.

## <a name="estimate-the-batch-order"></a>Estimer le lot de production
1. Cliquez sur Estimer.
2. Cliquez sur OK.
3. Cliquez sur Gérer les coûts dans le volet Actions.
4. Cliquez sur Afficher les détails du calcul.
5. Fermez la page.

## <a name="release-the-batch-order"></a>Lancer le lot de production
1. Cliquez sur Ordre de fabrication dans le volet Actions.
2. Cliquez sur Lancement.
3. Cliquez sur OK.

## <a name="schedule-production-jobs"></a>Planifier les tâches de production
1. Dans le volet Actions, cliquez sur Planification.
2. Cliquez sur Planifier les tâches.
3. Dans le champ Capacité finie, sélectionnez Non.
4. Dans le champ Matières limitées, sélectionnez Non.
5. Cliquez sur OK.
6. Cliquez sur Ordre de fabrication dans le volet Actions.
7. Cliquez sur Toutes les tâches.
8. Fermez la page.

## <a name="start-the-batch-order"></a>Démarrer le lot de commandes
1. Cliquez sur Démarrer.
2. Cliquez sur l'onglet Général.
3. Sélectionnez Non dans le champ Valider immédiatement les prélèvements.
4. Cliquez sur OK.
5. Cliquez sur Afficher dans le volet Actions.
6. Cliquez sur Prélèvements.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Fermez la page.
9. Fermez la page.
10. Cliquez sur Fiche production.
11. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
12. Fermez la page.
13. Fermez la page.


