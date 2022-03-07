---
title: Cycle de vie d'un lot de commandes de la création au démarrage
description: Cette procédure vous guide dans la première partie du cycle de vie d'un lot de commandes.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5fd04587c95ba8a48750f96302a11aeaf82308d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981404"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a>Cycle de vie d'un lot de commandes de la création au démarrage

[!include [banner](../../includes/banner.md)]

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

