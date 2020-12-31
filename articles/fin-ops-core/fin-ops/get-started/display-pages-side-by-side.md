---
title: Afficher côte à côte des pages à l’aide de la fonction Ouvrir dans une nouvelle fenêtre
description: Cet article explique comment afficher des pages côte à côte.
author: aneesmsft
manager: AnnBe
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b770fe44e4e12c515ca53def697fa345ce3eba3
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694443"
---
# <a name="show-pages-side-by-side-using-the-open-in-new-window-feature"></a>Afficher côte à côte des pages à l’aide de la fonction Ouvrir dans une nouvelle fenêtre

[!include [banner](../includes/banner.md)]

Cet article explique comment afficher des pages côte à côte.

Vous pouvez afficher plusieurs pages côte à côte pour accomplir des tâches plus rapidement. Par exemple, vous souhaitez peut-être valider ou entrer des lignes dans plusieurs journaux. Généralement, pour valider ou entrer des lignes dans plusieurs journaux, vous devez aller et venir entre la page qui affiche la liste des journaux, et la page qui affiche les lignes d’un journal donné. Toutefois, la fonction **Ouvrir dans une nouvelle fenêtre** vous permet d’afficher ces pages côte à côte afin de pouvoir effectuer vos tâches rapidement.

Dans la suite de l’exemple ci-dessus, quand vous affichez les lignes, vous pouvez cliquer sur l’icône **Ouvrir dans une nouvelle fenêtre**.

[![Cliquez sur l’icône Ouvrir dans une nouvelle fenêtre.](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)

Cliquer sur l’icône **Ouvrir dans une nouvelle fenêtre** ouvre la page des lignes dans une nouvelle fenêtre de navigateur, puis permet de revenir à la fenêtre précédente qui affichait la liste des journaux. Vous pouvez ensuite afficher les deux pages côte à côte. Lorsque vous avez terminer d’afficher un journal, vous pouvez modifier le journal sélectionné dans la page de liste de journal, alors la page des lignes dans la fenêtre contextuelle affichera automatiquement les lignes du journal récemment sélectionné.

[![Vous pouvez ensuite afficher les deux pages côte à côte.](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)

La liaison dynamique et l’actualisation se produisent en raison des relations qui existent entre les données sous-jacentes dans ces pages. Si le système ne se rend pas compte de la relation entre les données, la fenêtre contextuelle ne s’actualisera pas automatiquement en réponse à une modification dans la fenêtre dont elle provient.

Certaines pages ont plusieurs vues, comme la vue Grille, En-tête et Détails. L’icône **Ouvrir dans une nouvelle fenêtre** a pour effet que la page entière est ouverte dans la nouvelle fenêtre du navigateur. Par conséquent, vous ne pouvez pas conserver deux vues de la même page côte à côte à l’aide de la fonction **Ouvrir dans une nouvelle fenêtre** . Toutefois, presque toutes ces pages ont une liste de navigation qui permet de basculer entre les enregistrements et obtenir un résultat similaire.

Avant d’utiliser la fonctionnalité **Ouvrir dans une nouvelle fenêtre**, vous devez configurer le bloqueur de fenêtres contextuelles de votre navigateur pour autoriser toutes les fenêtres contextuelles de l’URL du site. Comme exemple, vous pouvez autoriser les fenêtres de « \*.dynamics.com ».

La fonction **Ouvrir dans une nouvelle fenêtre** n’est disponible que lorsqu’il existe plusieurs page ouvertes dans la fenêtre. En outre, la fenêtre contextuelle se ferme automatiquement lorsqu’il n’y a plus de page ouverte (autrement dit, lorsque la dernière page dans cette fenêtre est fermée.) Le système ferme également les pages ouvertes lorsque vous accédez à une autre zone de l’application. Par conséquent, si vous avez des fenêtres contextuelles ouvertes et que vous accédez à une autre zone de l’application, les fenêtres contextuelles sont automatiquement fermées car les pages de ces fenêtres ont été fermées par le système.

La barre supérieure dans les fenêtres contextuelles affiche des informations sur la société dans laquelle la page a été ouverte et est en lecture seule. Les fenêtres contextuelles s’appuient également sur les fenêtres du navigateur principal. Si la fenêtre principale est fermée ou actualisée, toutes les fenêtres contextuelles ouvertes passent en lecture seule. Si cette situation se produit, vous pouvez toujours voir les informations dans ces fenêtres, mais vous ne pourrez pas interagir avec.
