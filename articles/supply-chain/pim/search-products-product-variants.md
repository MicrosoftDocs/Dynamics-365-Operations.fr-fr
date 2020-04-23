---
title: Recherche de produits et de variantes de produits lors de la saisie de commande
description: Utilisez le champ **Numéro de l'article** pour rechercher des produits et des variantes de produits lorsque vous créez manuellement une ligne de commande client ou une ligne de commande fournisseur. Cela vous permet de rechercher rapidement des variantes de produits lorsque vous avez uniquement la chaîne de configuration ou l'une des dimensions de produit disponibles.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRFullTextIndexField, MCRFullTextParameters, PurchTable, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 248534
ms.assetid: 99dd5ce1-0029-4f06-90e7-865e6d46d86e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 15a6439595174978e379aaf248cd565bdf636428
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209412"
---
# <a name="search-for-products-and-product-variants-during-order-entry"></a>Recherche de produits et de variantes de produits lors de la saisie de commande

[!include [banner](../includes/banner.md)]

Utilisez le champ **Numéro de l'article** pour rechercher des produits et des variantes de produits lorsque vous créez manuellement une ligne de commande client ou une ligne de commande fournisseur.  Cela vous permet de rechercher rapidement des variantes de produits lorsque vous avez uniquement la chaîne de configuration ou l'une des dimensions de produit disponibles.

Parfois, avoir trop de quelque chose n'est pas le plus judicieux, et c'est particulièrement vrai si vous vendez un certain nombre de produits similaires, et que vous tentez de vous souvenir des numéros d'articles ou des noms de produits pour rechercher le produit à insérer dans une commande client. Vous pouvez utiliser le champ **Numéro d'article** sur une ligne de commande client ou une ligne de commande fournisseur comme champ de recherche. Vous pouvez entrer n'importe quelle partie du nom, du numéro ou de la dimension d'un produit, et d'obtenir une recherche qui affiche tous les articles qui correspondent au mot de recherche.

## <a name="how-searchworks"></a>Procédure de recherche
Lorsque vous recherchez des produits ou des variantes de produits, il est important de bien comprendre comment la fonction de recherche permet de trouver les produits qui correspondent au texte que vous entrez. Les principales règles de recherche pour afficher des résultats de recherche sont :

-   Les résultats de la recherche renverront tous les enregistrements correspondants, quel que soit le champ dans lequel le texte de recherche est entré.
-   Le texte de recherche doit être présent dans l'enregistrement correspondant dans son intégralité.
-   Une correspondance sera renvoyée même si le texte de recherche se trouve au milieu d'une chaîne de texte dans l'enregistrement correspondant. Il ne doit pas s'afficher au début d'une chaîne de texte.
-   Le texte de recherche est traité comme une chaîne de texte unique même si elle contient un espace.

### <a name="examples"></a>Exemples

Les exemples suivants utilisent des produits et des variantes de produits pour illustrer comment la recherche est traitée dans des scénarios différents. **Conditions préalables :** Sous **Ventes et marketing &gt; Paramétrage &gt; Recherche &gt; Paramètres de recherche &gt; Type de recherche**, sélectionnez l'option  **Correspondance totale**.

| Type de produit     | Nom du produit    | Afficher le numéro du produit | numéro d'article | Configuration |
|------------------|-----------------|------------------------|-------------|---------------|
| Produit distinct | SpeakerMidRange | D0001                  | D0001       | N/A            |
| Variante de produit  | Haut-parleur actif  | D0010::Black :         | D0010       | 000005        |
| Variante de produit  | Haut-parleur actif  | D0010::White :         | D0010       | Blanc         |

Si vous saisissez « parleur » dans le champ **Numéro d'article**, vous obtiendrez tous les produits ci-dessus comme résultats de la recherche. Si vous entrez « black » dans le champ **Numéro d'article**, vous obtiendrez le deuxième produit comme résultat, car il a le texte « black » dans le numéro de produit d'affichage. Ces deux exemples illustrent que la recherche n'est pas uniquement au début du champ, une correspondance se produira même si le texte de la recherche se trouve au milieu d'une chaîne de texte dans l'enregistrement correspondant.  

Si vous entrez « 05 » vous obtiendrez uniquement la deuxième variante de produit comme résultat, car elle a « 05 » dans la configuration. Cela illustre que la recherche se fait dans tous les champs activés sur la page **Critères de recherche**.  

Si vous saisissez « parleur 05 » vous n'obtiendrez aucun résultat. Cela est dû au fait que la recherche recherche le texte complet entré. La recherche n'essaiera pas de trouver « parleur » et affinera les résultats à ceux contenant « 05 ».  

Vous pouvez limiter le nombre de résultats de la recherche à l'aide du champ **Nombre de résultats** sur la page **Ventes et marketing &gt; Paramétrage &gt; Recherche &gt; Paramètres de recherche** . Si vous définissez ce champ sur 0, tous les résultats de la recherche seront renvoyés. Si le définissez sur 10, par exemple, il renverra 10 résultats de recherche au maximum.

## <a name="configure-the-productsearch"></a>Configuration de la recherche de produit
Avant de pouvoir utiliser la fonction de recherche de produit et de variante de produit, procédez comme suit pour configurer la recherche de produit. [![3 étapes pour configurer la recherche de produit\_AXAppFall](./media/3-steps-to-configure-product-search_axappfall.png)](./media/3-steps-to-configure-product-search_axappfall.png)

### <a name="step-1include-all-the-relevant-product-and-product-variant-identifiers-and-dimensions-in-the-search-criteria"></a>Étape 1 : Inclure tous les produits et identificateurs et dimensions de variantes de produits appropriés dans les critères de recherche

Parmi les identificateurs et dimensions de produits et de variantes de produits selon lesquels vous pouvez effectuer la recherche, il y a  **Nom du produit, numéro d'article**, **Afficher le numéro de produit, la configuration, la couleur, la taille, le style, le nom de recherche, etc.**  

Accédez à la page **Ventes et marketing &gt; Paramétrage &gt; Recherche &gt; Critères de recherche**. La page **Critères de recherche** vous permet de définir des critères pour le client, le prospect, et la recherche de produit. Assurez-vous de filtrer la page à l'aide de critères de recherche de produit. Vous pouvez le faire en passant à **Produit** dans le menu de la page.  

Pour ajouter le numéro de produit d'affichage aux critères de recherche, cliquez sur **Nouveau** dans le menu de la page. Cela ajoute un nouvel enregistrement dans la grille **Critères de recherche**. Ouvrez la recherche de colonne **Nom de champ** et choisissez **DisplayProductNumber**. Pour ajouter la configuration du produit aux critères de recherche, créez un enregistrement dans la grille **Critères de recherche** et choisissez **configId** dans la colonne **Nom de champ**. De la même manière, créez un enregistrement avec **Nom de champ** **InventColorId** pour la dimension de la couleur, **InventSizeId** pour la dimension de la taille, et **InventStyleId** pour la dimension du style.

### <a name="step-2-populate-the-database-table-that-is-used-for-product-search"></a>Étape 2 : Remplir la table de la base de données utilisée pour la recherche de produit

Sur la page **Critères de recherche**, cliquez sur le bouton **Mettre à jour les données de recherche**. Dans la boîte de dialogue **Mettre à jour les données de recherche**, assurez-vous que  **Source** est défini sur **Produit**, puis cliquez sur **OK**. Le système regroupera dans un tableau tous les critères de recherche sélectionnés spécifiés à l'étape 1. Si vous avez de nombreux produits et variantes de produit, cette opération peut être assez longue et vous pouvez recevoir un avertissement. Nous vous recommandons de planifier le remplissage de la table de recherche sur le serveur de traitement par lots à une heure où le serveur n'est pas trop occupé.  

Tant que la table n'est pas remplie, la recherche de produit ne fournit pas de résultats corrects. Si vous ne recevez aucun résultat de recherche, assurez-vous que cette table est remplie.  

La table ne doit être remplie que lorsque les critères de recherche sont modifiés. Les produits et variantes lancés récemment sont automatiquement ajoutés à la table. Les produits et variantes supprimés sont automatiquement supprimés de la table.

### <a name="step-3-enable-the-lookup-for-product-search-on-sales-and-purchase-order-lines"></a>Étape 3 : Activer la recherche de produit pour les lignes de commande client et lignes de commande fournisseur

Vous pouvez activer cette fonctionnalité en accédant à **Ventes et marketing &gt; Paramétrage &gt; Recherche &gt; Paramètres de recherche** et en définissant **Activer la recherche pour la recherche** sur **Oui** dans l'onglet **Général**.  

Pour l'entrée de ligne de commande client, le comportement par défaut est d'ouvrir la page **Recherche de produit** lorsque vous commencez à taper dans le champ  **Numéro d'article**, puis que vous appuyez sur la touche  **Tabulation**. La page **Recherche de produit** modifie le contexte lors de la création de ligne de commande et peut être considérée comme inutilement intrusive. Si vous préférez obtenir les résultats de la recherche dans une recherche et ne pas perdre le contexte pendant la saisie de la ligne de commande, vous pouvez utiliser la recherche de recherche à la place. Si vous recherchez un produit ou une variante de produit, mais que vous ne sélectionnez rien dans la recherche et que vous appuyez sur la touche **Tabulation**, la page **Recherche de produit** s'affiche.



