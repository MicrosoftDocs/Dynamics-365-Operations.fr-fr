---
title: Gérer des attributs et des groupes d'attributs
description: Cette rubrique décrit comment utiliser les attributs pour décrire un produit et ses caractéristiques par le biais de champs définis par l'utilisateur.
author: ashishmsft
manager: AnnBe
ms.date: 04/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: EcoResCategoryAttribute, EcoResProductEntityAttributeTableFieldAssociation, EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResAttributeType, EcoResAttributeValue, EcoResCategoryAttributeGroup, EcoResCategoryFriendlyName
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application pdate 5, AX 8.0
ms.openlocfilehash: 70e2b52dd140660fe98c6ff07248a033ba4bd635
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979971"
---
# <a name="manage-attributes-and-attribute-groups"></a>Gérer des attributs et des groupes d'attributs

[!include [banner](includes/banner.md)]

Les *Attributs* permettent de décrire de façon plus précise un produit et ses caractéristiques dans les champs définis par l'utilisateur (tels que **Capacité de stockage**, **Capacité du disque dur**, **Est conforme à la norme Energy Star**, etc.). Les attributs peuvent être associés à diverses entités Commerce, telles que des canaux et des catégories de produits, et des valeurs par défaut peuvent être définies pour eux. Les produits héritent alors des attributs et des valeurs par défaut lorsqu'ils sont associés aux catégories de produits ou à des canaux. Les valeurs par défaut peuvent être remplacées au niveau du produit individuel, au niveau du canal ou dans un catalogue.


Par exemple, un produit de télévision classique peut avoir les attributs suivants.

| Catégorie   | Attribut                | Valeurs autorisées          | Valeur par défaut |
|------------|--------------------------|-----------------------------|---------------|
| TV et vidéo | Marque                    | Toute valeur de marque valide       | None          |
| TV         | Taille d'écran              | 20 à 80 pouces                | None          |
|            | Résolution verticale      | 480i720p1080i ou 1080p | 1080p         |
|            | Fréquence d'actualisation de l'écran      | 60 hz, 120 hz ou 240 hz       | 60 hz          |
|            | Entrées HDMI              | 0–10                        | 3             |
|            | Entrées DVI               | 0–10                        | 1             |
|            | Entrées composites         | 0–10                        | 2             |
|            | Entrées de composants         | 0–10                        | 1             |
| LCD        | Compatible 3D                 | Oui ou Non                   | Oui           |
|            | Activé pour la 3D               | Oui ou Non                   | N°            |
| Plasma     | Température de fonctionnement      | 0–43 degrés              | 32            |
|            | Température de fonctionnement        | 0–43 degrés              | 100           |
| Projection | Garantie du tube de projection | 612 ou 18 mois         | 12            |
|            | \# de tubes de projection   | 1–5                         | 3             |

## <a name="attributes-and-attribute-types"></a>Attributs et types d'attribut

Les attributs sont basés sur les *types d'attributs*. Le type d'attribut identifie le type de données pouvant être saisies pour un attribut spécifique. Les types d'attributs suivants sont pris en charge :

- **Devise** – Ce type prend en charge une valeur de devise. Il peut être lié (autrement dit, il peut prendre en charge une plage de valeurs), ou il peut être laissé ouvert.
- **Date et heure** – Ce type prend en charge une valeur de date et d'heure. Il peut être lié ou laissé ouvert.
- **Décimal** – Ce type prend en charge une valeur numérique qui inclue des décimales. Il prend également en charge une unité de mesure. Il peut être lié ou laissé ouvert.
- **Entier** – Ce type prend en charge une valeur numérique. Il prend également en charge une unité de mesure. Il peut être lié ou laissé ouvert.
- **Texte** – Ce type prend en charge une valeur de texte. Il prend également en charge un ensemble prédéfini de valeurs possibles (, c'est-à-dire une *énumération*).
- **Booléen** – Ce type prend en charge une valeur binaire (**vrai** ou **faux**).
- **Référence** – Ce type fait référence à d'autres attributs.

### <a name="set-up-attribute-types"></a>Paramétrer les types d'attributs

1. Connectez-vous au client back-office en tant que gestionnaire du commerce.
2. Allez dans **Gestion des informations sur les produits** &gt; **Configuration** &gt; **Catégories et attributs** &gt; **Types d'attributs**.
3. Créez deux types d'attribut de type **Texte**, définissez l'option **Liste fixe** sur **Oui**, puis ajoutez une liste de valeurs :

    - Nommez un type d'attribut **Forme des verres**, puis ajoutez des valeurs suivantes : **Ovale**, **Carré** et **Rectangle**.
    - Nomme l'autre type d'attribut **Marque de lunettes de soleil**, puis ajoutez des valeurs suivantes : **Ray ban**, **Aviator** et **Oakley**.

![Types d'attributs](media/AttributeType.png)

### <a name="set-up-an-attribute"></a>Paramétrer un attribut

1. Connectez-vous au client back-office en tant que gestionnaire du commerce.
2. Allez dans **Gestion des informations sur les produits** &gt; **Configuration** &gt; **Catégories et attributs** &gt; **Attributs**.
3. Créez un attribut nommé **Verres**.
4. Définissez le champ **Type d'attribut** sur **Forme des verres**.

![Attributs](media/Attribute.png)

## <a name="attribute-metadata"></a>Métadonnées d'attribut

*Métadonnées d'attribut* vous permet de sélectionner des options afin de spécifier la manière dont les attributs de chaque produit doivent se comporter. Par exemple, vous pouvez spécifier si les attributs sont obligatoires, s'ils peuvent être utilisés pour les recherches, et s'ils peuvent être utilisés comme filtre.

Pour les produits, les paramètres de métadonnées d'attribut peuvent être remplacés au niveau du canal. Cette capacité sera traitée plus loin dans cette rubrique.

Comme vous pouvez le remarquer, la page **Attributs** contient des options liées aux métadonnées d'attribut. Sous **Métadonnées d'attribut du PDV**, une option nommée **Peut être affiné** affecte le comportement des valeurs d'attribut du point de vente (PDV) ou la façon dont le système gère ces valeurs d'attribut. Seuls les attributs pour lesquels vous pouvez définir l'option **Peut être affiné** sur **Oui** s'affichent à des fins d'affinement ou de filtrage des produits dans le PDV.

Voici les options de métadonnées d'attributs restantes sur la page **Attributs** :

- Peut faire l'objet d'une recherche
- Peut être récupéré
- Peut être recherché
- Triable
- Autoriser les valeurs multiples
- Ignorer la casse et le format
- Correspondance parfaite

Ces options ont été initialement prévues pour optimiser la fonctionnalité de recherche pour la vitrine en ligne. Bien que Commerce ne comprenne pas de vitrine en ligne prête à l'emploi, un kit de développement logiciel (SDK) de publication de commerce électronique est inclus. Les clients peuvent utiliser ce kit SDK pour placer des produits dans un index de recherche de leur choix. Bien que les données de produit soient importées, les clients doivent toujours pouvoir distinguer les données pouvant faire l'objet d'une recherche, les données pouvant être interrogées, et ainsi de suite. Ainsi, ils peuvent créer un index optimal pour s'assurer qu'ils indexent uniquement les attributs qui, *selon eux*, doivent être indexés.

Pour plus d'informations sur l'objectif de ces options restantes, voir [Vue d'ensemble du schéma de recherche de SharePoint Server 2013](https://technet.microsoft.com/library/jj219669.aspx).

## <a name="filter-settings-for-attributes"></a>Paramètres de filtre pour les attributs

Les paramètres de filtre pour les attributs permettent de définir comment les filtres des attributs sont affichés dans le PDV. Pour accéder aux paramètres de filtre d'un attribut, sur la page **Attributs**, sélectionnez l'attribut, puis, dans le volet Actions, sélectionnez **Paramètres de filtre**.

La page **Préférences d'affichage du filtre** inclut les champs suivants :

- **Nom** – Par défaut, ce champ est défini sur le nom de l'attribut. Vous pouvez toutefois modifier la valeur.
- **Option d'affichage** – Les options disponibles sont les suivantes :

    - **Valeur unique** – Cette option est disponible pour les types d'attributs suivants : **Booléen**, **Devise**, **Décimal**, **Entier** et **Texte**. Cette option permet d'activer la sélection d'une valeur unique pour ces attributs dans le client à des fins d'affinement.
    - **Valeur multiple** – Cette option est disponible pour les types d'attributs suivants : **Devise**, **Décimal**, **Entier** et **Texte**. Cette option permet d'activer la sélection de plusieurs valeurs pour cet attribut dans le client à des fins d'affinement.

- **Contrôle d'affichage** – Les options disponibles sont les suivantes :

    - **Liste** – Cette option est disponible pour tous les types d'attributs.
    - **Plage** – Cette option est disponible pour les types d'attributs suivants : **Devise**, **Décimal** et **Entier**.
    - **Curseur** – Cette option est disponible pour les types d'attributs suivants : **Devise**, **Décimal** et **Entier**.
    - **Curseur avec barres** – Cette option est disponible pour les types d'attributs suivants : **Devise**, **Décimal** et **Entier**.

- **Valeur de seuil** – Ce paramètre est obligatoire si vous sélectionniez **Plage** comme type de contrôle d'affichage. Vous pouvez définir des valeurs à l'aide d'un point virgule (;) comme séparateur.

    Par exemple, pour le filtre comme **Volume du sac**, une valeur de seuil peut être **10 ; 20 ; 50 ; 100 ; 200 ; 500 ; 1 000 ; 5 000**. Dans ce cas, le PDV affiche les plages suivantes. Toutes les plages n'ayant aucun produit dans le résultat défini s'affichent estompées.

    - Inférieur à 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - Au moins 500

![Paramètres de filtre d'attribut](media/AttributeFilterSettings.PNG)

## <a name="attribute-groups"></a>Groupes d'attributs

Une fois les attributs définis, ils peuvent être affectés à des groupes d'attributs. Un *groupe d'attributs* permet de regrouper les attributs individuels d'un composant ou d'un sous-composant dans un modèle de configuration de produit. Un attribut peut être inclus dans plusieurs groupes d'attributs. Les groupes d'attributs peuvent aider les utilisateurs à configurer des produits, car les différentes sélections sont organisées dans un contexte spécifique. Les groupes d'attributs peuvent être affectés à des catégories ou à des canaux.

Vous pouvez également définir des valeurs par défaut pour les attributs inclus dans un groupe d'attributs. Par exemple, vous ajoutez un attribut pour la couleur à un groupe d'attributs et sélectionnez **Bleu** comme valeur d'attribut par défaut. Dans ce cas, lorsque le groupe d'attributs est ajouté à un produit qui inclut la couleur comme l'un de ses attributs, **Bleu** s'affiche comme couleur par défaut pour ce produit.

![Groupes d'attributs](media/AttributeGroup.png)

### <a name="create-an-attribute-group"></a>Création d'un groupe d'attributs

1. Connectez-vous au client back-office en tant que gestionnaire du commerce.
2. Allez dans **Gestion des informations sur les produits** &gt; **Configuration** &gt; **Catégories et attributs** &gt; **Groupes d'attributs**.
3. Créez un groupe d'attributs nommé **Lunettes de soleil de mode**.
4. Ajoutez les attributs suivants : **Forme des verres** et **Marque de lunettes de soleil**.

### <a name="assign-attribute-groups-to-categories"></a>Affecter des groupes d'attributs à des catégories

Un ou plusieurs groupes d'attributs peuvent être associés aux nœuds de catégorie dans les types de hiérarchies de catégories suivants : hiérarchie des produits Commerce, hiérarchie de catégories de navigation du canal et hiérarchie de catégories de produits supplémentaires. Ensuite, lorsque les produits sont classés en catégorie, ils héritent des attributs inclus aux groupes d'attributs.

![Hiérarchie de produits – Groupes d'attributs de produit](media/AGRetailProdHierarchy.PNG)

Procédez comme suit pour affecter des groupes d'attributs aux catégories de la hiérarchie des produits Commerce.

1. Connectez-vous au client back-office en tant que gestionnaire du commerce.
2. Accédez à **Commerce et vente au détail** &gt; **Gestion des catégories et des produits** &gt; **Hiérarchie des produits Commerce**.
3. Sélectionnez **Hiérarchie de navigation de mode**.
4. Sous **Vêtements pour hommes**, sélectionnez la catégorie **Pantalons**, puis dans l'organisateur **Groupes d'attributs de produits**, ajoutez un groupe d'attributs nommé **Ceinture pour hommes**.
5. Sélectionnez la catégorie **Lunettes de soleil de mode**, puis vérifiez les nouveaux attributs du groupe d'attributs **Lunettes de soleil de mode** en sélectionnant **Afficher les attributs**.

    Le groupe d'attributs doit afficher les nouveaux attributs **Forme des verres** et **Marque de lunettes de soleil**.

6. Sous **Vêtements pour hommes**, sélectionnez la catégorie **Pantalons**, puis vérifiez les attributs du groupe d'attributs **Ceinture pour hommes** en sélectionnant **Afficher les attributs**.

    Le groupe d'attributs doit afficher les attributs **Marque de ceinture pour hommes**, **Textile de la ceinture** et **Taille de la ceinture**.

> [!NOTE]
> Cette procédure peut également être utilisée pour affecter des groupes d'attributs aux catégories de la hiérarchie des catégories de navigation du canal et la hiérarchie de catégories de produits supplémentaire. Dans l'étape 2, utilisez les chemins de navigation suivants :
>
> - Commerce et vente au détail &gt; Gestion des catégories et des produits &gt; Catégories de navigation du canal
> - Commerce et vente au détail &gt; Gestion des catégories et des produits &gt; Catégories de produit supplémentaires

### <a name="assign-attribute-groups-to-stores"></a>Affecter des groupes d'attributs à des magasins

Un ou plusieurs groupes d'attributs peuvent être associés à un ou plusieurs magasins dans la hiérarchie du magasin. Ensuite, lorsque des produits sont enrichis pour des magasins spécifiques, ils héritent des attributs inclus dans les groupes d'attributs.

1. Connectez-vous au client back-office en tant que gestionnaire du commerce.
2. Accédez à **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Catégories de canal et attributs de produit**.
3. Affectez des groupes d'attributs au canal Houston :

    1. Sélectionnez le canal **Houston**.
    2. Dans l'organisateur **Groupe d'attributs**, sélectionnez **Ajouter**, puis dans le champ **Nom**, sélectionnez **SharePointProvisionedProductAttributeGroup**.
    3. Sélectionnez **Ajouter** de nouveau, puis dans le champ **Nom**, sélectionnez **Ceinture pour hommes**.
    4. Sélectionnez **Ajouter** de nouveau, puis dans le champ **Nom**, sélectionnez **Lunettes de soleil de mode**.

        > [!NOTE]
        > Une option vous permet de spécifier que ce canal doit hériter des groupes d'attributs de son canal parent dans la hiérarchie. Si vous définissez l'option **Hériter** sur **Oui**, le nœud du canal enfant hérite de tous les groupes d'attributs et de tous les attributs de ces groupes d'attributs.

4. Activez les attributs afin qu'ils soient disponibles dans le canal Houston :

    1. Sur le volet Actions, sélectionnez **Paramétrer les métadonnées d'attribut**.
    2. Sélectionner le nœud de catégorie **Mode**, puis dans l'organisateur **Attributs de produit de canal**, sélectionnez **Inclure l'attribut** pour chaque attribut.
    3. Sélectionner le nœud de catégorie **Accessoires de mode**, sélectionnez la catégorie **Lunettes de soleil de mode**, puis dans l'organisateur **Attributs de produit de canal**, sélectionnez **Inclure l'attribut** pour chaque attribut.
    4. Sélectionner le nœud de catégorie **Vêtements pour hommes**, sélectionnez la catégorie **Pantalons**, puis dans l'organisateur **Attributs de produit de canal**, sélectionnez **Inclure l'attribut** pour chaque attribut.

![Catégories de canal et attributs de produit – Groupes d'attributs](media/CCPAttrGrp.png)

## <a name="overriding-attribute-values"></a>Remplacement des valeurs d'attribut

Les valeurs par défaut des attributs peuvent être remplacées pour les produits individuels au niveau du produit. Pour des produits individuels, les valeurs par défaut peuvent également être remplacées dans des catalogues spécifiques qui sont ciblés à des canaux spécifiques.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Remplacer les valeurs d'attribut d'un produit individuel

1. Connectez-vous au client back-office en tant que gestionnaire du commerce.
2. Accédez à **Commerce et vente au détail** &gt; **Gestion des catégories et des produits** &gt; **Produits lancés par catégorie**.
3. Sélectionner le nœud de catégorie **Mode** &gt; **Accessoires de mode** &gt; **Lunettes de soleil de mode**.
4. Sélectionnez le produit requis dans la grille. Puis, sur le volet Actions, sous l'onglet **Produit**, dans le groupe **Paramétrer**, cliquez sur **Attributs de produit**.
5. Sélectionnez un attribut dans le volet gauche, puis mettez sa valeur à jour dans le volet droit.

![Page Détails de produit – Groupes d'attributs de produit](media/ProdDetailsProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-catalog"></a>Remplacer les valeurs d'attribut d'un produit dans un catalogue

1. Connectez-vous au client back-office en tant que gestionnaire du commerce.
2. Accédez à **Commerce et vente au détail** &gt; **Gestion des catalogues** &gt; **Tous les catalogues**.
3. Sélectionnez le catalogue **Catalogue de base de Fabrikam**.
4. Sélectionner le nœud de catégorie **Mode** &gt; **Accessoires de mode** &gt; **Lunettes de soleil de mode**.
5. Dans l'organisateur **Produits**, sélectionnez le produit requis, puis sélectionnez **Attributs** au-dessus de la grille de produit.
6. Dans les organisateurs suivants, mettez à jour les valeurs des attributs exigés :

    - Support de produit partagé
    - Attributs de produit partagés
    - Canal du support
    - Attributs de produit de canal

    > [!NOTE]
    > Si le support de produit partagé et les attributs de produit partagés sont créés, ils s'appliquent à tous les produits.

![Groupe d'attributs de produit du catalogue](media/CatalogProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-channel"></a>Remplacer les valeurs d'attribut d'un produit dans un canal

1. Connectez-vous au client back-office en tant que gestionnaire du commerce.
2. Accédez à **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Catégories de canal et attributs de produit**.
3. Sélectionnez le canal **Houston**.
4. Dans l'organisateur **Produits**, sélectionnez le produit requis, puis sélectionnez **Attributs** au-dessus de la grille de produit.

    > [!NOTE]
    > Si aucun produit n'est disponible, ajoutez des produits en sélectionnant **Ajouter** sur l'organisateur **Produits**, puis en sélectionnant les produits nécessaires dans la boîte de dialogue **Ajouter des produits**.

5. Dans les organisateurs suivants, mettez à jour les valeurs des attributs exigés :

    - Support de produit partagé
    - Attributs de produit partagés
    - Canal du support
    - Attributs de produit de canal

    > [!NOTE]
    > Si le support de produit partagé et les attributs de produit partagés sont créés, ils s'appliquent à tous les produits.


[!INCLUDE[footer-include](../includes/footer-banner.md)]