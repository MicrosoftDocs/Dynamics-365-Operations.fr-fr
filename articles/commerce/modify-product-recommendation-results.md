---
title: Gérer les résultats de recommandation produit fondées sur l'IA et le ML
description: Cette rubrique explique comment personnaliser les résultats de recommandation de produit basés sur l'intelligence artificielle et le Machine Learning (IA et ML) votre entreprise.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5da77f71fb2569adc011bb9ee9c8c795d85545f8
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025000"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a>Gérer les résultats de recommandation produit fondées sur l'IA et le ML


[!include [banner](includes/banner.md)]

Cette rubrique explique comment personnaliser les résultats de recommandation de produit basés sur l'intelligence artificielle et le Machine Learning (IA et ML) votre entreprise. 

Après avoir activé les recommandations de produit, les paramètres par défaut prennent effet ; ces paramètres peuvent servir pour de nombreux besoins. Il est recommandé prévoir du temps pour évaluer si les résultats correspondent au mouvement de vente de produits. Nous vous conseillons d'évaluer les résultats quelques jours avant de modifier les paramètres si nécessaire avant de tester à nouveau. 

## <a name="understanding-recommendation-list-parameters"></a>Compréhension des paramètres de la liste des recommandations

Avant de modifier les paramètres, renseignez-vous sur la façon dont ils vont affecter les résultats ci-dessous.

### <a name="trending-product-list"></a>Liste des produits « Tendance »

La liste de produits « Tendance » a deux paramètres modifiables :

![Exemple de paramètre par défaut de la liste « Tendance »](./media/exampletrendingparameters.png)

1. **Inclure les nouveaux produits des X dernier jours** - Les produits qui ont été ajoutés au cours du nombre de jours spécifié avant la date actuelle peuvent être utilisés pour sélectionner des candidats de produit. La valeur par défaut dans l'image suggère que les produits datant de 180 jours peuvent être utilisés dans la liste des produits tendance.
1. **Inclure les ventes des X dernier jours** - Les transactions de ventes qui ont eu lieu au cours du nombre de jours spécifié avant la date actuelle peuvent être utilisés pour commander des produits. La valeur par défaut ci-dessus suggère que tous les achats effectués d'un produit dans les 30 derniers jours soient utilisés pour déterminer l'emplacement du produit dans la liste de produits tendance. 

### <a name="best-selling-product-list"></a>Liste de produits « Meilleure vente »

En fonction de votre entreprise, la liste « Meilleure vente » peut apporter des résultats différents de ceux de la liste « Tendance », même si elles utilisent toutes les deux les données de transaction pour commander des produits. Comme les meilleures ventes n'ont aucune limité basée sur une date d'assortiment, les meilleures ventes peut encore mettre des produits plus anciens et très populaires en évidence qui peuvent avoir baissé dans la liste des tendances. 

La liste de produits « Meilleure vente » a un paramètre modifiable :

![Exemple de paramètre par défaut de liste de meilleures ventes](./media/examplebestsellingparameters.PNG)

1. **Inclure les ventes des X dernier jours** - Les transactions de ventes qui ont eu lieu au cours du nombre de jours spécifié avant la date actuelle peuvent être utilisés pour commander des produits. La valeur par défaut ci-dessus suggère que tous les achats effectués d'un produit dans les 30 derniers jours soient utilisés pour déterminer l'emplacement du produit dans la liste de produits les plus vendus. 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a>Manuellement ajouter ou supprimer des produits des listes de recommandations

### <a name="for-new-trending-or-best-selling-lists"></a>Pour les listes « Nouveau », « Tendance » ou « Meilleure vente »

1.  Accédez à **Retail et Commerce** > **Recommandations de produits** > **Paramètres des recommandations**.
1.  Dans la liste des paramètres partagés, sélectionnez **Listes des recommandations**.
1.  Sélectionnez la liste à laquelle ajouter ou supprimer des produits.
1.  Pour ajouter des produits à la table, sélectionnez **Ajouter une ligne**. 
1.  Sous la colonne Produit, recherchez un produit par **Nom** ou par **Numéro de produit.**

    ![Exemple de recherche d'un produit dans la nouvelle liste de produits](./media/examplenewlistconfiguration1.png)

1.  Dans la colonne Type de ligne, sélectionnez l'une des deux options :
    -   **Inclure** – force un produit au dessus de la liste
    -   **Exclure** – supprime un produit de la liste qui s'affiche
    
    ![Exemple d'inclusion ou d'exclusion d'un produit de la nouvelle liste de produits](./media/examplenewlistconfiguration2.png)

1.  La modification de l'**Ordre d'affichage** modifie l'ordre dans lequel les produits marqués à **Inclure** s'affichent dans la liste.
    - Si deux produits ont la même valeur d'**ordre d'affichage**, l'ordre final de ces deux résultats peut différer du back-office.
1.  Pour supprimer des produits de la table : sélectionnez la ligne à supprimer et sélectionnez **Supprimer**.


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a>Pour les listes « D'autres client aiment également » ou « Fréquemment achetés ensemble »

Dans le contexte des listes « Fréquemment achetés ensemble » ou « D'autres clients aiment également », l'apprentissage machine permet d'analyser les schémas d'achat des consommateurs pour recommander des produits liés généralement achetés ensemble pour un seul produit d'origine. 
 
Un *produit initial* est le produit pour lequel vous voulez générer des résultats. Dans le contexte de l'ajustement manuel des listes de recommandations, vous ajoutez ou supprimez des résultats pour ce produit. 

Procédez comme suit pour ajouter ou supprimer manuellement des résultats pour un produit d'origine :
1.  Sélectionnez le **Produit d'origine**. 
1.  Dans la colonne **Produit**, recherchez un produit par **Nom** ou **Numéro de produit.**
![Exemple de la recherche d'un produit sur la liste Fréquemment achetés ensemble](./media/exampleFBTlistconfiguration1.png)
1. Dans la colonne **Type de ligne**, sélectionnez l'une des deux options :
    - **Inclure** – force un produit au dessus de la liste
    - **Exclure** – supprime un produit de la liste qui s'affiche     
![Exemple de Inclure ou Exclure un produit sur la liste Fréquemment achetés ensemble](./media/exampleFBTlistconfiguration2.png)
1.  Pour supprimer des produits de la table : sélectionnez la ligne à supprimer et sélectionnez Supprimer.


## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des recommandations produit](product-recommendations.md)

[Activer les recommandations produit](enable-product-recommendations.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Ajouter des listes de recommandation produit aux pages](add-reco-list-to-page.md)

[Vue d'ensemble du module de collecte de produits](product-collection-module-overview.md)
