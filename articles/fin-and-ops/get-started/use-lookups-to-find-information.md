---
title: "Trouver des informations à l'aide des recherches"
description: "Dans Microsoft Dynamics 365 for Finance and Operations, de nombreux champs sont pourvus d'une option de recherche qui vous permettent de facilement retrouver la valeur correcte ou souhaitée. Plusieurs améliorations ont été ajoutées aux recherches qui rendent ces commandes plus faciles à utiliser et augmentent la productivité des utilisateurs. Dans cette rubrique, vous découvrirez les nouvelles fonctionnalités de recherche et recevrez des conseils utiles pour exploiter les recherches de manière optimale dans le système."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 9de957490b2ca87949a7cbcecc9acb4e8b98aaaf
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="find-information-by-using-lookups"></a>Trouver des informations à l'aide des recherches

[!include [banner](../includes/banner.md)]

Dans Microsoft Dynamics 365 for Finance and Operations, de nombreux champs sont pourvus d'une option de recherche qui vous permettent de facilement retrouver la valeur correcte ou souhaitée. Plusieurs améliorations ont été ajoutées aux recherches qui rendent ces commandes plus faciles à utiliser et augmentent la productivité des utilisateurs. Dans cette rubrique, vous découvrirez les nouvelles fonctionnalités de recherche et recevrez des conseils utiles pour exploiter les recherches de manière optimale dans le système.

## <a name="responsive-lookups"></a>Recherches réactives

Dans les versions antérieures de Finance and Operations, lors de l'interaction avec un contrôle de recherche, l'utilisateur devait réaliser une action explicite pour ouvrir le menu déroulant. Il pouvait s'agir de taper un astérisque (\*) dans le champ de contrôle pour ouvrir la recherche fondée sur la valeur en cours du contrôle, de cliquer sur le bouton du menu déroulant ou d'utiliser le raccourci clavier **Alt**+**Flèche bas**. Les contrôles de recherche ont été modifiés des manières suivantes afin de mieux correspondre aux pratiques Web actuelles :

- Les menus déroulants de recherche s'ouvrent désormais automatiquement après une légère pause de la saisie, le contenu du menu déroulant étant filtré en fonction de la valeur du contrôle de recherche.

    Notez que l'ancien comportement d'ouverture automatique du menu déroulant après saisie d'un astérisque (\*) est obsolète.

- Une fois le menu déroulant de recherche ouvert, les événements suivants se produisent :

    - Le curseur reste dans le contrôle de recherche (au lieu de se déplacer dans le menu déroulant), de sorte que vous pouvez continuer à modifier la valeur dans le contrôle. Toutefois, l'utilisateur peut utiliser les touches **Flèche haut** et **Flèche bas** pour changer de ligne dans le menu déroulant et la touche Entrée pour sélectionner la ligne en cours.
    - Le contenu du menu déroulant s'ajuste quand des modifications sont apportées à la valeur du contrôle de recherche.

Par exemple, considérez un champ de recherche appelé **Ville**.

Lorsque le focus se trouve dans le champ **Ville**, vous pouvez commencer à rechercher la ville que vous souhaitez en tapant quelques lettres, telles que « col ». Quand la saisie s'arrête, la recherche s'ouvre automatiquement ; son filtre sélectionne les villes dont le nom commence par « col ».

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png)

À ce stade, le curseur est toujours dans le champ de recherche. Si vous poursuivez la saisie de sorte que la valeur soit « colum », le contenu de la recherche s'adapte automatiquement pour refléter la dernière valeur du contrôle.

![updateFilterLookupExample](./media/updatefilterlookupexample.png)

Bien que le focus soit toujours dans le contrôle de recherche, vous pouvez également utiliser les touches **Flèche haut** ou **Flèche bas** pour mettre en surbrillance la ligne que vous souhaitez. Si vous appuyez sur la touche **Entrée**, la ligne en surbrillance est sélectionnée à partir de la recherche, et la valeur du contrôle est actualisée.

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Saisie d'éléments autres que des ID

Lors de la saisie de données, il est naturel que les utilisateurs tentent d'identifier une entité, telles qu'un client ou un fournisseur, par son nom et non par un identifiant représentatif de l'entité. Dans la version actuelle de Finance and Operations, de nombreuses recherches (mais pas toutes), permettent désormais la saisie de données contextuelles. Cette fonctionnalité puissante permet à l'utilisateur de saisir l'ID ou le nom correspondant dans le contrôle de recherche.

Par exemple, pensez au champ **Compte client** lorsque vous créez une commande client. Ce champ affiche l'**ID compte** du client mais, en général, un utilisateur préfère saisir un **Nom du compte** au lieu d'un **ID compte** lorsqu'il crée une commande client ; par exemple, « Forest Wholesales » « au lieu de « US-003 ».

Si l'utilisateur a commencé à entrer l'**ID compte** dans le contrôle de recherche, le menu déroulant s'ouvre automatiquement, comme décrit dans la section précédente, et l'utilisateur voit la recherche telle qu'elle est illustrée ci-dessous.

[![Recherche contextuelle lors de la saisie d'un ID compte client](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

Toutefois, l'utilisateur peut désormais entrer le début d'un **ID compte** également. S'il est détecté, l'utilisateur voit la recherche suivante. Notez comment la colonne **Nom** se déplace pour devenir la première colonne de la recherche, et comment la recherche est triée et filtrée d'après la colonne **Nom**.

[![Recherche contextuelle lors de la saisie d'un nom de client](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Utilisation des en-têtes de colonne de la grille pour un filtrage et un tri plus avancés

Les perfectionnements de la recherche abordés dans les deux sections précédentes améliorent considérablement la capacité de l'utilisateur d'accéder aux lignes d'une recherche à partir d'une recherche « commence par » sur le champ **ID** ou **Nom**. Toutefois, il existe des situations dans lesquelles un filtrage (ou un tri) plus avancé est nécessaire pour trouver la ligne appropriée. Dans ces situations, l'utilisateur doit utiliser les options de filtrage et de tri dans les en-têtes de colonne de la grille dans la recherche. Par exemple, considérez un employé qui entre une ligne de commande client qui doit localiser le bon « câble » comme produit. Il n'est pas très utile de taper « câble » dans le contrôle **Numéro d'article**, car il n'existe aucun nom de produit commençant par « câble ».

![emptyitemlookup](./media/emptyitemlookup.png)

Au lieu de cela, l'utilisateur doit effacer la valeur du contrôle de recherche, ouvrir le menu déroulant de recherche, puis filtrer le menu déroulant à l'aide de l'en-tête de colonne de la grille, comme illustré ci-dessous. Un utilisateur avec souris (ou tactile) peut uniquement cliquer sur (ou toucher) n'importe quel en-tête de colonne pour accéder aux options de filtrage et de tri pour cette colonne. Pour un utilisateur au clavier, il suffit d'appuyer sur **Alt**+**Flèche** **bas** une deuxième fois pour déplacer le focus dans le menu déroulant; après quoi l'utilisateur peut utiliser les tabulations jusqu'à la colonne souhaitée puis appuyer sur **Ctrl**+**G** pour ouvrir le menu déroulant de l'en-tête de colonne de grille.

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png)

Une fois le filtre appliqué (voir l'image ci-dessous), l'utilisateur peut rechercher et sélectionner la ligne comme normalement.

![filtereditemlookup](./media/filtereditemlookup.png)

