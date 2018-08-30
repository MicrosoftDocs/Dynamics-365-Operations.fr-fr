---
title: "Afficher côte à côte des pages à l'aide de la fonctionnalité Ouvrir dans une nouvelle fenêtre"
description: "Cet article explique comment afficher des pages côte à côte dans Microsoft Dynamics 365 for Finance and Operations."
author: aneesmsft
manager: AnnBe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 8e3ef29618f11b0f247999e3a24e54bff44bf51a
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="show-pages-side-by-side-by-using-the-open-in-new-window-feature"></a>Afficher côte à côte des pages à l'aide de la fonctionnalité Ouvrir dans une nouvelle fenêtre

[!include [banner](../includes/banner.md)]

Cet article explique comment afficher des pages côte à côte dans Microsoft Dynamics 365 for Finance and Operations.

Microsoft Dynamics 365 for Finance and Operations vous aide à effectuer vos tâches plus efficacement. Dans certains cas, vous pouvez afficher plusieurs pages côte à côte pour accomplir des tâches plus rapidement. Par exemple, vous souhaitez peut-être valider ou entrer des lignes dans plusieurs journaux. Généralement, pour ce faire vous devez aller et venir entre la page qui affiche la liste des journaux, et la page qui affiche les lignes d'un journal donné. Toutefois, la fonction **Ouvrir dans une nouvelle fenêtre** vous permet d'afficher ces pages côte à côte afin de pouvoir effectuer vos tâches rapidement. 

Dans la suite de l'exemple ci-dessus, quand vous affichez les lignes, vous pouvez cliquer sur l'icône **Ouvrir dans une nouvelle fenêtre**. 

[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png) 

Cliquer sur l'icône **Ouvrir dans une nouvelle fenêtre** ouvre la page des lignes dans une nouvelle fenêtre de navigateur, puis permet de revenir à la fenêtre précédente qui affichait la liste des journaux. Vous pouvez ensuite afficher les deux pages côte à côte. Lorsque vous avez terminer d'afficher un journal, vous pouvez modifier le journal sélectionné dans la page de liste de journal, alors la page des lignes dans la fenêtre contextuelle affichera automatiquement les lignes du journal récemment sélectionné. 

[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png) 

La liaison dynamique et l'actualisation se produisent en raison des relations qui existent entre les données sous-jacentes dans ces pages. Si le système ne se rend pas compte de la relation entre les données, la fenêtre contextuelle ne s'actualisera pas automatiquement en réponse à une modification dans la fenêtre dont elle provient. 

Certaines pages ont plusieurs vues, comme la vue Grille, En-tête et Détails. L'icône **Ouvrir dans une nouvelle fenêtre** a pour effet que la page entière est ouverte dans la nouvelle fenêtre du navigateur. Par conséquent, vous ne pouvez pas conserver deux vues de la même page côte à côte à l'aide de la fonction **Ouvrir dans une nouvelle fenêtre** . Toutefois, presque toutes ces pages ont une liste de navigation qui permet de basculer entre les enregistrements et obtenir un résultat similaire. 

Avant d'utiliser la fonctionnalité **Ouvrir dans une nouvelle fenêtre**, vous devez configurer le bloqueur de fenêtres contextuelles de votre navigateur pour autoriser toutes les fenêtres contextuelles de l'URL du site Finance and Operations. Comme exemple, vous pouvez autoriser les fenêtres de « \*.dynamics.com ». 

La fonction **Ouvrir dans une nouvelle fenêtre** n'est disponible que lorsqu'il existe plusieurs page ouvertes dans la fenêtre. En outre, la fenêtre contextuelle se ferme automatiquement lorsqu'il n'y a plus de page ouverte (autrement dit, lorsque la dernière page dans cette fenêtre est fermée.) Finance and Operations ferme également les pages ouvertes lorsque vous accédez à une autre zone de l'application. Par conséquent, si vous avez des fenêtres contextuelles ouvertes et que vous accédez à une autre zone de l'application, les fenêtres contextuelles sont automatiquement fermées car les pages de ces fenêtres ont été fermées par le système. 

La barre supérieure dans les fenêtres contextuelles affiche des informations sur la société dans laquelle la page a été ouverte et est en lecture seule. Les fenêtres contextuelles s'appuient également sur les fenêtres du navigateur principal de Finance and Operations. Si la fenêtre principale est fermée ou actualisée, toutes les fenêtres contextuelles ouvertes passent en lecture seule. Cela signifie que vous pouvez toujours voir les informations dans ces fenêtres, mais vous ne pourrez pas interagir avec.




