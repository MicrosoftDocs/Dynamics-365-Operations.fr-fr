---
title: Recherche d&quot;actions
description: "Cet article décrit la fonctionnalité de recherche d&quot;action dans Microsoft Dynamics 365 pour les opérations. La recherche d&quot;action vous aideront à rechercher et exécuter des actions sur une page."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 689d8f9fb0501c5007db21d41f126737af77b89e
ms.lasthandoff: 03/31/2017


---

# <a name="action-search"></a>Recherche d'actions

Cet article décrit la fonctionnalité de recherche d'action dans Microsoft Dynamics 365 pour les opérations. La recherche d'action vous aideront à rechercher et exécuter des actions sur une page.

<a name="introduction"></a>Introduction
------------

Les pages de Microsoft Dynamics 365 pour les opérations exposent principalement des commandes sur des Volets Actions, le volet Actions standard qui apparaît en haut de la page et les barres d'outils qui apparaissent dans d'autres sections de la page. Dans les versions précédentes, une clé incline la fonction vous a autorisé rapidement accéder n'importe quel bouton dans un volet Actions en appuyant sur la touche ALT Ensuite des séries de lettres. 

![keyTipsAX6 [] (. /media/keytipsax6.png)](. /media/keytipsax6.png) Toutefois, dans la version actuelle de Dynamics 365 pour des opérations, des touches accélératrices ne sont plus disponibles mais ont été remplacés par la fonction de recherche d'action. Cette nouvelle fonctionnalité permet de rechercher rapidement et d'exécuter un bouton à partir de n'importe quel Volet Actions visible.

## <a name="using-action-search"></a>Utilisation de la recherche d'actions
Pour utiliser la fonctionnalité de recherche d'actions, procédez comme suit.

1.  Dans le volet Actions, cliquez dans le champ **recherche d'actions**. (Le champ **recherche d'actions** contient une icône de loupe).
2.  Tapez la totalité ou une partie du nom du bouton que vous souhaitez exécuter. Vous pouvez également rechercher à l'aide de les mots chemin du bouton du «  ». (Pour plus d'informations, voir la section suivante de cet article.) Généralement, un bouton apparaît proche du haut des résultats répertorient après avoir entré deux et quatre caractères.
3.  Recherchez et exécutez le bouton dans la liste des résultats (à l'aide de la souris ou du clavier).

Une fois le bouton exécuté, la vue retourne à votre dernière position dans la page, afin de pouvoir continuer à travailler. 

[action-recherche-champ d'![] (. /media/action-search-field.png)](. /media/action-search-field.png)

Vous pouvez également commencer la recherche d'actions en appuyant sur Ctrl+/ ou Alt+Q. Appuyez sur le raccourci clavier de nouveau pour que la vue retourne sur votre dernière position dans la page.

## <a name="understanding-the-results-list"></a>Présentation de la liste des résultats
Souvent, dans Dynamics 365 pour les opérations, vous devez connaître l'emplacement et le contexte d'un bouton pour comprendre totalement l'objectif de ce bouton. Par conséquent, les informations supplémentaires sont affichées pour chaque article dans la liste des résultats, afin d'inclure précisément les boutons apparaissent dans la liste. En particulier, le « chemin d'accès » du bouton est affiché. Ce chemin d'accès peut inclure les noms des éléments d'interface utilisateur suivants, le cas échéant :

-   Onglets du volet Actions
-   Groupe de boutons
-   Bouton de menu (si le bouton est à l'intérieur d'un bouton de menu)
-   Séparateur de menu (si le bouton est à l'intérieur d'un groupe nommé à l'intérieur d'un bouton de menu)
-   Groupe ou onglet dans la page (par exemple, le nom d'un organisateur)

Par exemple, vous avez tapé **tot** dans le champ **recherche d'actions** et vous passez maintenant en revue la liste des résultats. La première entrée, pour un bouton nommé ** les totaux **, est mise en surbrillance. Un chemin du bouton ** commande client ** &gt; ** de vue ** est également affiché. ** Commande client ** la pièce du chemin correspond ** commande client ** à l'onglet dans le volet Actions, puis ** vue ** la pièce du chemin correspond ** vue ** dans le groupe sous cet onglet. De même, le chemin ** remise totale ** de le bouton (** vente ** &gt; ** calculez **) vous informe que ce bouton se trouve dans ** calculent ** groupe sous ** la vente ** onglet du volet Actions. Par conséquent, ces informations vous aide à inclure exactement que le bouton est déclenchée par la recherche d'action (si vous sélectionnez que bouton dans la liste des résultats). 

[action-recherche-champ-avec- données![] (. /media/action-search-field-with-data.png)](. /media/action-search-field-with-data.png) 

Dans l'exemple précédent, la recherche d'action a donné les résultats du volet Actions standard en haut d'une page. Toutefois, la recherche d'actions montre également les résultats des barres d'outils visibles qui sont situées dans d'autres endroits de la page. Par exemple, vous recherchez pour ** stock disponible ** vous en appuyant sur le bouton situé dans ** des lignes de commande client ** l'organisateur. Dans ce cas, le chemin de boutons dans la liste des résultats (** des lignes de commande client ** &gt; ** stock ** &gt; ** vue **) vous indique que ce bouton se trouve sous ** vue ** l'en-tête sous ** stock ** le bouton de menu sur ** des lignes de commande client ** l'organisateur. 

[stock disponible de![(]. réelles de /media/on - inventory.png)](. réelles de /media/on - inventory.png)

## <a name="action-search-vs-navigation-search"></a>Recherche d'actions/recherche de navigation
Bien que la recherche d'action est effectuée pour rechercher et des actions d'exécution d'une page, il existe un mécanisme distinct de recherche pour rechercher et accéder aux pages dans Dynamics 365 pour les opérations. Pour plus d'informations sur cette fonction, voir [recherche de navigation] () navigation-search.md article.


