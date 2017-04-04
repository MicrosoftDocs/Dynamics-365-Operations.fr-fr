---
title: Recherches d&quot;utilisation pour trouver des informations
description: "Dans Microsoft Dynamics 365 pour les opérations, de nombreux champs ont des recherches qui vous aident facilement retrouver la valeur correcte ou souhaitée. Plusieurs améliorations ont été ajoutées aux recherches qui rendent ces contrôles plus utilisables et rendent les utilisateurs plus productives). Dans cette rubrique, vous vous renseignerez sur les nouvelles fonctions de recherche et recevez des conseils utiles pour obtenir l&quot;utilisation optimale règlement des recherches dans le système."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 6a25593632575dcd71fa4a3c9cf5b83c9f8ecd39
ms.lasthandoff: 03/31/2017


---

# <a name="use-lookups-to-find-information"></a>Recherches d'utilisation pour trouver des informations

Dans Microsoft Dynamics 365 pour les opérations, de nombreux champs ont des recherches qui vous aident facilement retrouver la valeur correcte ou souhaitée. Plusieurs améliorations ont été ajoutées aux recherches qui rendent ces contrôles plus utilisables et rendent les utilisateurs plus productives). Dans cette rubrique, vous vous renseignerez sur les nouvelles fonctions de recherche et recevez des conseils utiles pour obtenir l'utilisation optimale règlement des recherches dans le système.  

<a name="responsive-lookups"></a>Recherches confidentielles
------------------

Dans les versions antérieures de Dynamics 365 pour les opérations, en interagissant à un contrôle de recherche, un utilisateur doit prendre une action explicite d'ouvrir le menu déroulant. Cela peut s'être produits en entrant un astérisque (\*) dans le contrôle pour filtrer la recherche selon la valeur actuelle du contrôle, cliquant sur le bouton de menu déroulant, ou en utilisant ** ALT **+** vers le bas flèche ** raccourci clavier. Les contrôles de recherche ont été modifiés des manières suivantes de la fonctionnalité mieux avec des pratiques actuelles Web :

-   Les menus déroulante de recherche s'ouvriront désormais automatiquement après une légère pause en tapant, avec le contenu de menu déroulant ont filtré selon la valeur du contrôle de recherche.
    -   Notez que l'ancien comportement de l'ouverture automatique du déroulantes après avoir entré un astérisque (\*) a été désapprouvé.
-   Une fois le menu déroulant de recherche s'est ouvert, les éléments suivants se produit :
    -   Le curseur restera dans le contrôle de recherche (au lieu de la vue se déplaçant dans le menu déroulant) et vous pouvez continuer à modifier la valeur du contrôle. Toutefois, l'utilisateur peut utiliser ** Supérieur croisée de la flèche ** et ** vers le bas flèche ** toujours modifier des lignes dans le menu déroulant, et entre sélectionnez la ligne actuelle dans le menu déroulant.
    -   Le contenu du menu déroulant s'ajustera une fois les modifications soient apportées à la valeur du contrôle de recherche.

Par exemple, considérez un champ de recherche appelé ** ville **. 

Lorsque la vue est dans ** ville ** le champ, vous pouvez commencer à rechercher la ville que vous souhaitez en tapant des lettres, " nord-est « col ».  Après avoir indépendamment de saisir, la recherche s'ouvre automatiquement, filtré à les villes qui commencent par « col ». 

[typeaheadLookupExample d'![] (. /media/typeaheadlookupexample.png)](. /media/typeaheadlookupexample.png) 

À ce stade, le curseur est toujours dans le champ de recherche. Si vous passez de saisir ce qui signifie que la valeur est « colum », le contenu de recherche s'adapte automatiquement pour refléter la dernière valeur du contrôle. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Bien que la vue soit toujours dans le contrôle de recherche, vous pouvez également utiliser ** Supérieur croisée de la flèche ** ou ** vers le bas flèche ** des clés pour mettre la ligne en surbrillance à sélectionner. Si vous appuyez sur ** entrez ** la ligne en surbrillance est sélectionnée de la recherche et la valeur du contrôle est mise à jour. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Saisir dans plus que les ID
Lorsque vous entrez des données, il est naturel les utilisateurs tentent d'identifier une entité, telles qu'un client ou un fournisseur, en termes de nom et non un identificateur représentant l'entité. Dans la version actuelle de Dynamics 365 pour les opérations, de nombreux (mais toutes ses) recherches permettent désormais la saisie de données contextuelle. Cette fonction puissante permet à l'utilisateur pour remplir l'ID ou nom correspondant dans le contrôle de recherche. 

Par exemple, considérez ** compte client ** le champ lors de la création d'une commande client. Les ce champ affiche ** ID compte ** du client, mais un utilisateur préfèreraient généralement pour entrer ** nom du compte ** au lieu de l'** l'ID compte ** pour ce champ lors de la création d'une commande client, telles que « forêt vend en gros « au lieu de « US-003 ».

Si l'utilisateur a commencé à entrer ** ID compte ** dans le contrôle de recherche, le menu déroulant s'ouvrirait automatiquement comme décrit dans la section précédente et l'utilisateur verra la recherche comme suit.

[recherche contextuelle![lorsqu'un ID compte client est entré] (. /media/howtocontextuallookups-1.png)](. /media/howtocontextuallookups-1.png)

Toutefois, l'utilisateur peut également désormais entrer le début de l'** nom du compte ** également. Si c'est détecté, l'utilisateur voit la recherche suivante. Notez comment ** nom ** la colonne est déplacée corresponde à la première colonne dans la recherche, et comment la recherche est triée et est filtré selon ** nom ** la colonne.

[recherche contextuelle![lorsqu'un nom du client est entré] (. /media/howtocontextuallookups-2.png)](. /media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Utilisation des en-têtes de colonne de la grille pour filtrer et trier plus avancées
Les améliorations de recherche abordées dans les deux sections précédentes améliorent considérablement la capacité à un utilisateur d'accéder aux lignes dans une recherche sur « commence par » la recherche du ** ID ** ou ** nom ** le champ de recherche. Toutefois, il existe des situations dans lesquelles filtrer plus avancé (ou trier) est nécessaire pour trouver la ligne appropriée. Dans ce cas, demande de l'utilisateur pour utiliser les options de filtrage et de tri dans les en-têtes de colonne de la grille dans la recherche. Par exemple, considérez un employé entre une ligne de commande client qui doit localiser droite « flexibles » comme produit. Saisir « flexibles » en ** numéro d'article ** le contrôle n'est pas utile, car il n'y a aucun nom de produit qui commencent par « flexibles ». 

![emptyitemlookup](./media/emptyitemlookup.png) 

Au lieu de cela, demande de l'utilisateur pour effacer la valeur du contrôle de recherche, pour ouvrir le menu déroulant de recherche, et pour filtrer le menu déroulant à l'aide de l'en-tête de colonne de la grille, comme illustré ci-dessous. Un utilisateur de la souris (ou contact) peut uniquement cliquer sur (ou contact) n'importe quelle en-tête de colonne pour accéder aux options de filtrage et de tri pour cette colonne. Pour un utilisateur de clavier, les besoins d'utilisateur simplement ont appuyer ** ALT **+** vers le bas ** ** flèche ** une seconde fois d'entrer la vue dans le menu déroulant, après quoi l'utilisateur peut passer à la colonne appropriée, puis appuyez sur CTRL ** **+** G ** pour ouvrir le menu déroulant d'en-tête de colonne de la grille. 

[gridfilteritemlookup d'![] (. /media/gridfilteritemlookup.png)](. /media/gridfilteritemlookup.png) 

Une fois le filtre a été appliqué (voir l'image ci-après), l'utilisateur peut rechercher et sélectionner la ligne normalement. 

![filtereditemlookup](./media/filtereditemlookup.png)


