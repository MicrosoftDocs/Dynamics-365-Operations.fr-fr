---
title: Recherche d&quot;actions
description: "Cet article décrit la fonctionnalité de recherche d&quot;actions dans Microsoft Dynamics 365 for Operations. La recherche d&quot;actions vous aide à rechercher et à exécuter des actions sur une page."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ef5709889dcabd4c9ed760f57d210956f38c37e9
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="action-search"></a>Recherche d'actions

[!include[banner](../includes/banner.md)]


Cet article décrit la fonctionnalité de recherche d'actions dans Microsoft Dynamics 365 for Operations. La recherche d'actions vous aide à rechercher et à exécuter des actions sur une page.

<a name="introduction"></a>Introduction
------------

Les pages de Microsoft Dynamics 365 for Operations exposent principalement les commandes des volets Actions, le volet Actions standard qui apparaît en haut de la page et les barres d'outils qui apparaissent dans différentes sections de la page. Dans les versions précédentes, les fonctions des touches accélératrices vous permettent d'accéder rapidement à n'importe quel bouton du volet Actions en appuyant sur la touche Alt, puis sur des séries de lettres. 

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png) Toutefois, dans la version actuelle de Dynamics 365 for Operations, les touches accélératrices ne sont plus disponibles mais sont remplacées par la fonctionnalité de recherche d'action. Cette nouvelle fonctionnalité permet de rechercher rapidement et d'exécuter un bouton à partir de n'importe quel Volet Actions visible.

## <a name="using-action-search"></a>Utilisation de la recherche d'actions
Pour utiliser la fonctionnalité de recherche d'actions, procédez comme suit.

1.  Dans le volet Actions, cliquez dans le champ **recherche d'actions**. (Le champ **recherche d'actions** contient une icône de loupe).
2.  Tapez l'ensemble ou une partie du nom du bouton que vous souhaitez exécuter. Vous pouvez également effectuer une recherche à l'aide de mots du « chemin d'accès » du bouton. (Pour plus d'informations, voir la section suivante de cet article). Généralement, un bouton s'affiche près du haut de la liste des résultats une fois que vous ayez tapé deux à quatre caractères.
3.  Recherchez et exécutez le bouton dans la liste des résultats (à l'aide de la souris ou du clavier).

Une fois le bouton exécuté, la vue retourne à votre dernière position dans la page, afin de pouvoir continuer à travailler. 

[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)

Vous pouvez également commencer la recherche d'actions en appuyant sur Ctrl+/ ou Alt+Q. Appuyez sur le raccourci clavier de nouveau pour que la vue retourne sur votre dernière position dans la page.

## <a name="understanding-the-results-list"></a>Présentation de la liste des résultats
Souvent, dans Dynamics 365 for Operations, vous devez connaître l'emplacement et le contexte d'un bouton pour bien comprendre l'objet de ce bouton. Par conséquent, des informations supplémentaires sont affichées pour chaque élément de la liste des résultats, pour vous aider à savoir précisément quels boutons apparaissent dans la liste. En particulier, le « chemin d'accès » du bouton est affiché. Ce chemin d'accès peut inclure les noms des éléments d'interface utilisateur suivants, le cas échéant :

-   Onglets du volet Actions
-   Groupe de boutons
-   Bouton de menu (si le bouton est à l'intérieur d'un bouton de menu)
-   Séparateur de menu (si le bouton est à l'intérieur d'un groupe nommé à l'intérieur d'un bouton de menu)
-   Groupe ou onglet dans la page (par exemple, le nom d'un organisateur)

Par exemple, vous avez tapé **tot** dans le champ **recherche d'actions** et vous passez maintenant en revue la liste des résultats. La première entrée, pour un bouton nommé **Totaux**, est mise en surbrillance. Un chemin d'accès du bouton **Commande client** &gt; **Afficher** est également affiché. La partie **Commande client** du chemin d'accès correspond à l'onglet **Commande client** dans le volet Actions, et la partie **Afficher** du chemin d'accès correspond au groupe **Afficher** sous cet onglet. De même, le chemin d'accès du bouton **Remise totale** (**Vendre** &gt; **Calculer**) vous informe que ce bouton est situé dans le groupe **Calculer** sous l'onglet **Vendre** du volet Actions. C'est pourquoi, ces informations vous permettent de comprendre précisément quel bouton sera déclenché par la recherche d'actions (si vous sélectionnez ce bouton dans la liste des résultats). 

[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png) 

Dans l'exemple précédent, la recherche d'action a donné les résultats du volet Actions standard en haut d'une page. Toutefois, la recherche d'actions montre également les résultats des barres d'outils visibles qui sont situées dans d'autres endroits de la page. Par exemple, vous recherchez le bouton **Stock disponible** situé dans l'organisateur **Lignes de commande client**. Dans ce cas, le chemin d'accès du bouton dans la liste des résultats (**Lignes de commande client** &gt; **Stock** &gt; **Afficher**) vous informe que ce bouton est situé sous l'en-tête **Afficher** du bouton de menu **Stock** dans l'organisateur **Lignes de commande client**. 

[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Recherche d'actions/recherche de navigation
Alors que la recherche d'actions sert à rechercher et à exécuter des actions sur une page, il existe un mécanisme distinct pour rechercher des pages et les parcourir dans Dynamics 365 for Operations. Pour plus d'informations sur cette fonction, voir l'article [Recherche lors de la navigation](navigation-search.md).




