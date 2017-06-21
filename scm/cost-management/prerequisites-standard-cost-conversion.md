---
title: "Conditions préalables à la conversion de coût standard"
description: "Cette rubrique décrit les tâches à effectuer avant d'exécuter une conversion de coût standard."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 50891
ms.assetid: 73af66cf-c924-45be-837a-a648dbd05a31
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7a9cac200301ea58e4dd9047cd9ff42648126b8e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="prerequisites-for-a-standard-cost-conversion"></a>Conditions préalables à la conversion de coût standard

[!include[banner](../includes/banner.md)]


Cette rubrique décrit les tâches à effectuer avant d'exécuter une conversion de coût standard. 

Avant d'exécuter une conversion du coût standard, procédez comme suit :

1.  Définissez un **groupe de modèles d'article** pour les coûts standard. La page Groupes de modèles d'article permet de créer un groupe de modèles d'article utilisant un modèle de stock de coût standard. Lors du paramétrage d'une conversion de coût standard, vous affectez ce groupe de modèles d'article aux articles à convertir.
2.  Affectez un **groupe de coûts** à chaque article.
    -   Le groupe de coûts affecté à un article acheté peut servir de base pour l'affectation de comptes généraux associés aux coûts standard, tels que l'affectation de comptes généraux pour des écarts de prix d'achat. Dans un environnement de fabrication, le groupe de coûts affecté aux composants achetés propose également la segmentation des coûts dans les coûts calculés d'un article fabriqué.
    -   Le groupe de coûts affecté à l'article fabriqué peut servir de base à l'affectation de comptes généraux associés aux coûts standard, tels que l'affectation de comptes généraux à des écarts de production.

3.  Affectez une **quantité de commande standard** à un article fabriqué lorsque ses coûts sont constants. La quantité de commande standard pour un article fabriqué agit comme une taille de lot comptable pour l'amortissement des coûts constants, ou l'application d'un prorata, tels que les temps de réglage des opérations de gamme ou une quantité de composants constants dans une nomenclature.
4.  Affectez les **comptes généraux** associés aux coûts standard, notamment l'écart de réévaluation du coût. Utilisez la page **Validation** (**Gestion des stocks** &gt; **Paramétrage**) pour affecter les comptes généraux associés aux coûts standard. Pour le processus de conversion de coûts standard, vous devez au moins affecter le compte pour l'écart de réévaluation du coût pour tous les articles et groupes de coûts. La page **Plan de comptes** permet de définir les comptes généraux nécessaires aux coûts standard. La page **Combinaisons de transactions** permet d'activer l'utilisation des relations de coûts (pour des tableaux, des groupes et pour tous) avant de définir les règles de validation d'articles.
5.  Définissez les paramètres de stock associés aux coûts standard. L'onglet **Séquences de numéros** de la page **Paramètres de gestion des stocks et des entrepôts** permet d'affecter une séquence de numéros aux N° documents de réévaluation. Ces derniers sont générés lorsque la conversion du coût standard modifie la valeur en stock d'un article. La page **Paramètres de gestion des stocks et des entrepôts** permet de définir les paramètres de contrôle des coûts (sous l'onglet **Comptabilité de stock**) pour définir deux paramètres associés aux coûts standard.
    -   Utilisez le champ **Analyse des coûts** pour sélectionner le n° ou la comptabilité auxiliaire. La sélection de Comptabilité auxiliaire est appelée « analyse active des coûts ». Une analyse active des coûts est très importante pour le calcul, la retenue et l'affichage de la segmentation des groupes de coûts dans une structure de produits à plusieurs niveaux pour des articles de coûts standard. Lorsque l'analyse des coûts est active, vous pouvez déclarer et analyser les éléments suivants dans un niveau, dans plusieurs niveaux ou dans le format total :
        1.  stock ;
        2.  travaux en cours ;
        3.  coût des marchandises vendues par groupe de coûts

        Une analyse active des coûts signifie que l'activation du coût d'un article fabriqué entraînera le stockage du résultat dans la segmentation des groupes de coûts dans l'enregistrement des coûts de l'article. Si vous ne renseignez pas le champ **Analyse des coûts**, la segmentation des groupes de coûts ne sera pas mise à jour pour les articles de coûts standard. Un coût standard d'article fabriqué sera donc calculé et mis à jour en tant que montant unique sans segmentation des groupes de coûts et les contributions de coûts des composants fabriqués seront regroupées sur le montant unique.
    -   Le champ **Écarts par rapport à standard** permet de sélectionner un groupe récapitulé ou un groupe par coût. La sélection par groupe par coûts permet d'identifier les écarts de prix d'achat et les écarts de production par groupe de coûts. Elle permet également d'identifier les quatre types d'écarts de production (taille du lot, quantité, prix et écarts de remplacement). Si vous sélectionnez un groupe récapitulé, vous ne pouvez pas identifier les écarts par groupe de coûts, ni les quatre types d'écarts de production. Vous pouvez uniquement afficher un écart de production récapitulé. La stratégie d'écarts de coûts standard fonctionne indépendamment de la stratégie d'analyse des coûts. Vous pouvez donc ne choisir aucune stratégie d'analyse des coûts et sélectionner des écarts par groupe de coûts, pour que les écarts de production par groupe de coûts soient tout de même capturés.






