---
title: Gérer des attributs et des groupes d’attributs
description: Cet article explique comment gérer les attributs et les groupes d’attributs pour décrire les produits et leurs caractéristiques dans Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.openlocfilehash: aad448ea733aabdff3dc4438dcb682d49e0665c0
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9386970"
---
# <a name="manage-attributes-and-attribute-groups"></a>Gérer des attributs et des groupes d’attributs

[!include [banner](includes/banner.md)]

Cet article explique comment gérer les attributs et les groupes d’attributs pour décrire les produits et leurs caractéristiques dans Microsoft Dynamics 365 Commerce.

Les *attributs* offrent une façon de décrire des produits et leurs caractéristiques via les champs définis par l’utilisateur. Les exemples incluent la taille de la mémoire, la capacité du disque dur et la conformité Energy Star.

Les attributs peuvent être associés à diverses entités Commerce, telles que des canaux et des catégories de produits, et des valeurs par défaut peuvent être définies pour eux. Lorsque les attributs sont associés aux catégories de produits ou à des canaux, ils héritent de ces attributs et de leurs valeurs par défaut. Les valeurs des attributs par défaut peuvent être remplacées au niveau du produit individuel, au niveau du canal ou dans un catalogue.

Par exemple, un produit de télévision classique peut avoir les attributs suivants.

| Catégorie   | Attribut           | Valeurs autorisées                        | Valeur par défaut |
|------------|---------------------|-------------------------------------------|---------------|
| TV et vidéo | Marque               | Toute valeur de marque valide                     | Aucune          |
| TV         | Taille d’écran         | 20 à 85 pouces                              | 55 pouces     |
|            | Résolution verticale | 4K (2160p), Full HD (1080p) ou HD (720p) | 4K (2160p)    |
|            | Fréquence d’actualisation de l’écran | 60 hz, 120 hz ou 240 hz                     | 60 hz          |
|            | Entrées HDMI         | 0–10                                      | 3             |

## <a name="attributes-and-attribute-types"></a>Attributs et types d’attribut

Les attributs sont basés sur les *types d’attributs*. Un type d’attribut identifie le type de données pouvant être saisies pour un attribut spécifique. Les types d’attributs suivants sont pris en charge dans Commerce :

- **Devise** – Ce type prend en charge une valeur de devise. Il peut être lié (autrement dit, il peut prendre en charge une plage de valeurs), ou il peut être laissé ouvert.
- **Date et heure** – Ce type prend en charge une valeur de date et d’heure. Il peut être lié ou laissé ouvert.
- **Décimal** – Ce type prend en charge une valeur numérique qui inclue des décimales. Il prend également en charge une unité de mesure. Il peut être lié ou laissé ouvert.
- **Entier** – Ce type prend en charge une valeur numérique. Il prend également en charge une unité de mesure. Il peut être lié ou laissé ouvert.
- **Texte** – Ce type prend en charge une valeur de texte. Il prend également en charge un ensemble prédéfini de valeurs possibles lorsque le paramètre **Liste fixe** est activé.
- **Booléen** – Ce type prend en charge une valeur binaire (**vrai** ou **faux**).
- **Référence** – Ce type fait référence à d’autres attributs.

> [!NOTE]
> En raison des [limitations de l’index de recherche Azure](/rest/api/searchservice/data-type-map-for-indexers-in-azure-search), l’attribut de type **Décimal** n’est pas pris en charge pour les expériences de recherche basées sur le cloud. La Recherche cognitive Azure ne prend pas en charge la conversion des attributs de type **Décimal** sur les types du champ d‘index cible **Edm.Double**, car cette conversion réduirait la précision.

### <a name="set-up-attribute-types"></a>Paramétrer les types d’attributs

Pour configurer des types d’attribut, suivez cet exemple de procédure.

1. Connectez-vous à Commerce headquarters comme responsable du commerce au détail.
1. Accédez à **Gestion des informations sur les produits \> Configuration \> Catégories et attributs \> Types d’attributs**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Nom du type d’attribut**, entrez **Type de sac**.
1. Dans le champ **Type**, sélectionnez **Texte**.
1. Définissez l’option **Liste fixe** sur **Oui**.
1. Sur l’organisateur **Valeurs**, sélectionnez **Ajouter**.
1. Dans la nouvelle ligne, dans le champ **Valeur**, entrez **Satchel**.
1. Ajoutez cinq lignes supplémentaires. Dans le champ **Valeur** de chacune, saisissez une valeur différente : **Pochette**, **Sac**, **Sac à dos**, **Sacoche**, ou **Portefeuille**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Nom du type d’attribut**, entrez **Marque de lunettes de soleil**.
1. Dans le champ **Type**, sélectionnez **Texte**.
1. Définissez l’option **Liste fixe** sur **Oui**.
1. Sur l’organisateur **Valeurs**, sélectionnez **Ajouter**.
1. Dans la nouvelle ligne, dans le champ **Valeur**, entrez **Ray ban**.
1. Ajoutez deux lignes supplémentaires. Dans le champ **Valeur** de chacune, saisissez une autre valeur : **Aviator** ou **Oakley**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

![Page des types d’attributs.](media/AttributeType_2022Series.png)

### <a name="set-up-an-attribute"></a>Paramétrer un attribut

Pour configurer un attribut, suivez cet exemple de procédure.

1. Connectez-vous à Commerce headquarters comme responsable du commerce au détail.
1. Accédez à **Gestion des informations sur les produits \> Configuration \> Catégories et attributs \> Attributs**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Nom**, entrez **Type de sac**.
1. Dans le champ **Nom du type d’attribut**, sélectionnez **Type de sac**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

![Page Attributs.](media/Attribute_2022Series.png)

## <a name="attribute-metadata"></a>Métadonnées d'attribut

*Métadonnées d’attribut* vous permet de sélectionner des options afin de spécifier la manière dont les attributs de chaque produit doivent se comporter. Par exemple, vous pouvez spécifier si les attributs sont obligatoires, s’ils peuvent être utilisés pour les recherches, et s’ils peuvent être utilisés comme filtre.

Pour les produits, les paramètres de métadonnées d’attribut peuvent être remplacés au niveau du canal.

Une page **Attributs** contient plusieurs options liées aux métadonnées d’attribut. Par exemple, si vous définissez l’option **Peut être affiné** sur **Oui** sous **Métadonnées d’attribut pour les canaux de commerce**, l’attribut est indiqué pour précision ou filtrage des produits sur les résultats de la recherche et les pages de navigation par catégorie. Pour configurer un attribut comme affinable, vous devez sélectionner tout d’abord **Paramètres de filtre** sur le volet Actions et confirmer les paramètres de filtre pour l’attribut.

## <a name="filter-settings-for-attributes"></a>Paramètres de filtre pour les attributs

Les paramètres de filtre pour les attributs permettent de définir comment les filtres des attributs sont affichés dans le point de vente (PDV). Pour accéder aux paramètres de filtre d’un attribut, sur la page **Attributs**, dans le volet Actions, sélectionnez **Paramètres de filtre**.

La page **Paramètres de filtre** inclut les champs suivants :

- **Nom** – Par défaut, ce champ est défini sur le nom de l’attribut. Vous pouvez toutefois modifier la valeur.
- **Option d’affichage** – Les options disponibles sont les suivantes :

    - **Valeur unique** – Cette option est disponible pour les types d’attributs suivants : **Booléen**, **Devise**, **Décimal**, **Entier** et **Texte**. Il ne permet de sélectionner qu’une seule valeur pour les affinements sur les pages de liste de produits, telles que la navigation par catégorie et les pages de résultats de recherche de produits.
    - **Valeur multiple** – Cette option est disponible pour les types d’attributs suivants : **Devise**, **Décimal**, **Entier** et **Texte**. Cette option permet d’activer la sélection de plusieurs valeurs pour cet attribut dans le client à des fins d’affinement.

- **Contrôle d’affichage** – Les options disponibles sont les suivantes :

    - **Liste** – Cette option est disponible pour tous les types d’attributs.
    - **Plage** – Cette option est disponible pour les types d’attributs suivants : **Devise**, **Décimal** et **Entier**.
    - **Curseur** – Cette option est disponible pour les types d’attributs suivants : **Devise**, **Décimal** et **Entier**.
    - **Curseur avec barres** – Cette option est disponible pour les types d’attributs suivants : **Devise**, **Décimal** et **Entier**.

- **Valeur de seuil** – Ce paramètre est obligatoire si vous sélectionniez **Plage** comme type de contrôle d’affichage. Vous pouvez définir des valeurs à l’aide d’un point virgule (;) comme séparateur.

    Par exemple, pour un attribut **Volume du sac** dont le type d’attribut est **Entier**, la valeur seuil peut être **10 ; 20 ; 50 ; 100 ; 200 ; 500 ; 1000 ; 5000**. Dans ce cas, le PDV affiche les plages suivantes. Toutes les plages n’ayant aucun produit dans le résultat défini s’affichent estompées.

    - Inférieur à 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - Au moins 500

Les paramètres de filtrage des attributs s’appliquent uniquement aux attributs de produit et peuvent être utilisés pour affiner la recherche de produits et les résultats de navigation par catégorie. Ils ne s’appliquent pas à la recherche de clients ou à la recherche de commandes, bien que les mêmes attributs puissent être utilisés pour enrichir les informations sur les clients ou les commandes.

Dans les modules Commerce par défaut, aucune prise en charge prête à l’emploi n’est disponible pour les paramètres de filtre **Contrôle d’affichage** tels que **Plage**, **Curseur** et **Curseur avec barres**. Les paramètres **Plage** et **Curseur** sont toujours pris en charge pour les solutions PDV, tandis que le paramètre **Curseur avec barres** s’applique aux anciennes vitrines SharePoint en ligne et sont toujours disponibles pour l’intégration de tiers et les scénarios personnalisés.

Nous recommandons que les attributs affinables aient un attribut de type **Texte** où l’option **Liste fixe** est activée et que vous gardez la liste gérable (jusqu’à 100-200 valeurs uniques). Si un raffinement a 1 000 valeurs uniques ou plus, il est plus approprié d’utiliser un attribut de type **Texte** où l’option **Liste fixe** est désactivée.

Les traductions sont essentielles pour les noms d’attributs et leurs valeurs. Pour les attributs de type **Texte** où l’option **Liste fixe** est activée, vous pouvez définir des traductions pour les valeurs d’attribut sous **Type d’attribut**. Pour chaque autre type d’attribut, vous pouvez définir des traductions sur la page où vous définissez les valeurs d’attribut. Par exemple, pour un attribut de type **Texte**, vous pouvez définir des traductions pour la valeur par défaut sur la page **Attributs**. Toutefois, si vous remplacez la valeur par défaut au niveau du produit, vous pouvez définir des traductions pour l’attribut sur la page de produit **Attributs du produit**.

Une fois qu’un attribut a été marqué comme affinable pour un canal, vous ne devez pas mettre à jour le type d’attribut. Sinon, vous affecterez la publication des données produit dans l’index de recherche. Au lieu de cela, nous vous recommandons de créer un attribut pour un nouveau type d’affinement et de retirer l’attribut précédent en le supprimant des autres groupes d’attributs.

La recherche par attributs est prise en charge, mais ne récupère les résultats que pour les correspondances exactes des mots de recherche. Par exemple, un attribut **Tissu** a une valeur définie sur **Coton cachemire**. Si un client recherche « Cach », aucun produit n’ayant **Coton cachemire** défini comme tissu n’est récupéré. Cependant, si un client recherche « Cachemire », « Coton » ou « Coton cachemire », des produits ayant **Coton cachemire** défini comme tissu sont récupérés.

### <a name="additional-attribute-metadata-options"></a>Options de métadonnées d’attribut supplémentaires

> [!NOTE]
> Ces options de métadonnées d’attribut ne s’appliquent qu’aux anciennes vitrines SharePoint en ligne et intégrations externes. Pour plus d’informations sur l’objectif de ces options de métadonnées d’attribut, voir [Vue d’ensemble du schéma de recherche de SharePoint Server 2013](/SharePoint/search/search-schema-overview).

Les options de métadonnées d’attributs supplémentaires suivantes sont également disponibles sur la page **Attributs** :

- Peut faire l’objet d’une recherche
- Peut être récupéré
- Peut être recherché
- Triable
- Ignorer la casse et le format
- Correspondance parfaite

Ces options ont été initialement prévues pour optimiser la fonctionnalité de recherche pour les anciennes vitrines SharePoint en ligne. Elles ne s’appliquent pas nécessairement aux sites Web de commerce électronique Commerce ou aux terminaux de point de vente. Étant donné que l’intégration sans affichage continue d’être prise en charge, ces options sont disponibles pour l’exportation de métadonnées d’attribut à l’aide du kit de développement logiciel (SDK) Commerce. Vous pouvez utiliser le SDK Commerce pour placer des produits dans un index de recherche externe personnalisé et optimisé. De cette manière, vous pouvez vous assurer que seuls les attributs qui doivent être indexés le sont.

## <a name="attribute-groups"></a>Groupes d'attributs

Un *groupe d’attributs* permet de regrouper les attributs individuels d’un composant ou d’un sous-composant dans un modèle de configuration de produit. Un attribut peut être inclus dans plusieurs groupes d’attributs. Les groupes d’attributs peuvent aider les utilisateurs à configurer des produits, car les différentes sélections sont organisées dans un contexte spécifique. Les groupes d’attributs peuvent être affectés à des catégories ou à des canaux. Vous pouvez également définir des valeurs par défaut pour les attributs inclus dans un groupe d’attributs.

![Page Groupes d’attributs.](media/AttributeGroup_2022Series.png)

### <a name="create-an-attribute-group"></a>Création d’un groupe d’attributs

Pour créer un groupe d’attributs, suivez cet exemple de procédure.

1. Connectez-vous à Commerce headquarters comme responsable du commerce au détail.
1. Accédez à **Gestion des informations sur les produits \> Configuration \> Catégories et attributs \> Groupes d’attributs**.
1. Créez un groupe d’attributs nommé **Chemises**.
1. Ajoutez les attributs suivants : **CleaningMethod**, **CollarType**, **Collection**, et **Design**.

> [!NOTE]
> Les valeurs d’ordre d’affichage des attributs dans le groupe d’attributs n’influencent ni ne s’appliquent à l’ordre des affinements dans les résultats de recherche et de navigation de catégorie. Elles ne s’appliquent qu’au scénario « attributs de commande ».

### <a name="assign-attribute-groups-to-categories"></a>Affecter des groupes d’attributs à des catégories

Un ou plusieurs groupes d’attributs peuvent être associés à des nœuds de catégorie dans les types de hiérarchies de catégories suivants :

- Hiérarchie des produits commerciaux
- Hiérarchie des catégories de navigation dans un canal
- Hiérarchie supplémentaire des catégories de produits

Lorsque des produits sont classés dans des catégories associées à des groupes d’attributs, ils héritent des attributs inclus dans ces groupes d’attributs.

![Organisateur Groupes d’attributs de produit sur la page Hiérarchie des produits Commerce.](media/AGRetailProdHierarchy_2022Series.png)

Procédez comme suit pour affecter des groupes d’attributs aux catégories de la hiérarchie des produits Commerce.

1. Connectez-vous à Commerce headquarters comme responsable du commerce au détail.
1. Accédez à **Commerce et vente au détail \> Produits et catégories \> Hiérarchie des produits Commerce**.
1. Sélectionnez la hiérarchie de navigation **Mode**.
1. Sous **Vêtements pour hommes**, sélectionnez la catégorie **Pantalons**, puis dans l’organisateur **Groupes d’attributs de produits**, ajoutez un groupe d’attributs nommé **Ceinture pour hommes**.
1. Sélectionnez la catégorie **Lunettes de soleil de mode**, puis vérifiez les nouveaux attributs du groupe d’attributs **Lunettes de soleil de mode** en sélectionnant **Afficher les attributs**. Le groupe d’attributs doit afficher les nouveaux attributs **Forme des verres** et **Marque de lunettes de soleil**.
1. Sélectionnez la catégorie **Pantalons**, puis vérifiez les attributs du groupe d’attributs **Ceinture pour hommes** en sélectionnant **Afficher les attributs**. Le groupe d’attributs doit afficher les attributs **Marque de ceinture pour hommes**, **Textile de la ceinture** et **Taille de la ceinture**.

Cette procédure peut également être utilisée pour affecter des groupes d’attributs aux catégories de la hiérarchie des catégories de navigation du canal et la hiérarchie de catégories de produits supplémentaire. Toutefois, à l’étape 2, utilisez l’un des chemins suivants, selon la hiérarchie à laquelle vous souhaitez affecter des groupes d’attributs :

- **Hiérarchie des catégories de navigation dans un canal :** Accédez à **Commerce et vente au détail \> Catégorie et gestion des produits \> Catégories de navigation dans un canal**.
- **Hiérarchie des catégories de produits supplémentaires :** Accédez à **Commerce et vente au détail \> Catégorie et gestion des produits \> Catégories de produits supplémentaires**.

> [!NOTE]
> Assurez-vous que vous associez uniquement des groupes d’attributs dans une hiérarchie de catégories sur l’organisateur **Groupes d’attributs de produit**, pas sur l’organisateur **Valeurs d’attribut de catégorie**. Si des attributs apparaissent sur l’organisateur **Valeurs d’attribut de catégorie**, sélectionnez **Modifier la hiérarchie des catégories** dans le volet Actions. Ensuite, sur l’organisateur **Groupes d’attributs de catégorie**, sélectionnez les nœuds de catégorie, puis sélectionnez **Retirer**. Il n’y a pas de prise en charge de la récupération des attributs par catégorie via Commerce Scale Unit.

## <a name="identify-viewable-and-refinable-attributes-for-commerce-channels-for-the-default-product-collection"></a>Identifier les attributs visualisables et affinables pour les canaux Commerce pour la collection de produits par défaut

Après avoir associé divers groupes d’attributs à des catégories dans diverses hiérarchies (hiérarchie de produits Commerce ou catégories de navigation dans un canal) et défini des valeurs d’attribut pour chaque produit, en fonction de l’association de catégorie, vous devez activer l’indicateur **Afficher l’attribut sur le canal** pour rendre ces attributs visibles dans un canal spécifique.

1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.
1. Sélectionnez **Définir des métadonnées d’attribut**, puis sélectionnez un attribut dans le volet de navigation de gauche.
1. Sur l’organisateur **Attributs de produit de canal** (et non l’organisateur **Attributs de catégorie**), définissez l’option **Afficher l’attribut sur le canal** sur **Oui** pour rendre l’attribut visible.
1. Si vous souhaitez que l’attribut soit également affinable, définissez l’option **Peut être affiné** sur **Oui**.

### <a name="control-visibility-of-dimension-based-refiners-such-as-size-style-and-color"></a>Contrôlez la visibilité des affinements basés sur les dimensions tels que la taille, le style et la couleur

Les dimensions du produit telles que la taille, le style et la couleur sont les affineurs les plus couramment utilisés. Pour rendre ces dimensions de produit disponibles en tant qu’affinements, vous devez associer un groupe d’attributs au niveau du canal qui contient une référence à un type d’attribut qui hérite automatiquement des valeurs issues des valeurs de dimension de produit.

Vous pouvez spécifier que les dimensions du produit sont visibles et affinables en mettant à jour les indicateurs sur la page **Catégories de canaux et attributs de produits**. Sélectionnez le nœud racine dans le volet de navigation, puis, sur l’organisateur **Attributs de produit de canal**, définissez l’option **Afficher l’attribut sur le canal** sur **Oui** pour les attributs **Taille**, **Style** et **Couleur**. Si vous souhaitez que ces attributs soient également affinables, définissez l’option **Peut être affiné** sur **Oui** pour chacun.

![Définition des métadonnées d’attribut pour les affinements de dimension.](./media/ProductDimensionRefinersMetadataSetup_2022Series.png)

Pour activer les attributs afin qu’ils soient disponibles dans le canal Houston basé sur les données de démonstration, suivez les étapes de cet exemple de procédure.

1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.
1. Sélectionnez le canal **Houston**.
1. Sur le volet Actions, sélectionnez **Paramétrer les métadonnées d’attribut**.
1. Sélectionner le nœud de catégorie **Mode**, puis dans l’organisateur **Attributs de produit de canal**, sélectionnez **Inclure l’attribut** pour chaque attribut.
1. Sélectionner le nœud de catégorie **Accessoires de mode**, sélectionnez la catégorie **Lunettes de soleil de mode**, puis dans l’organisateur **Attributs de produit de canal**, sélectionnez **Inclure l’attribut** pour chaque attribut.
1. Sélectionner le nœud de catégorie **Vêtements pour hommes**, sélectionnez la catégorie **Pantalons**, puis dans l’organisateur **Attributs de produit de canal**, sélectionnez **Inclure l’attribut** pour chaque attribut.
1. Après avoir mis à jour les métadonnées d’attribut pour vos attributs et affinements prévus, assurez-vous d’enregistrer vos modifications et d’exécuter la tâche **Publier les mises à jour du canal**. Ensuite, une fois les mises à jour publiées, vous devez exécuter les tâches suivantes : **1070** (**Configuration des canaux**), **1040** (**Produits**), et **1150** (**Catalogue**).

> [!NOTE]
> - Si votre entreprise nécessite que vous ajoutiez ou supprimiez fréquemment des produits dans la hiérarchie de navigation, ou que vous apportiez des modifications telles que la mise à jour des valeurs d’ordre d’affichage, l’ajout de nouvelles catégories et l’ajout de nouveaux groupes d’attributs aux catégories, nous vous recommandons de configurer la tâche **Publier les mises à jour du canal** pour une exécution comme tâche fréquente de traitement par lots. Sinon, déclenchez manuellement la tâche **Publier les mises à jour du canal**, puis les tâches Commerce Data Exchange (CDX) suivantes : **1070** (**Configuration du canal**), **1040** (**Produits**), et **1150** (**Catalogue**).
> - Une option **Hériter** vous permet de spécifier que ce canal doit hériter des groupes d’attributs de son canal parent dans la hiérarchie. Si vous définissez l’option **Hériter** sur **Oui**, le nœud du canal enfant hérite de tous les groupes d’attributs et de tous les attributs de ces groupes d’attributs.
> - Si le bouton **Définir les métadonnées d’attribut** du volet Actions n’est pas disponible, assurez-vous que **Hiérarchie de navigation** est associé à votre canal sur l’organisateur **Général**.
> - Vous ne devez associer aucun groupe d’attributs à l’exception des groupes d’attributs basés sur la dimension au niveau du canal (par exemple, sous **Groupes d’attributs** sur la page **Catégories de canaux et attributs de produits**).
> - Après l’introduction de la prise en charge des catalogues interentreprises (B2B) spécifiques au client dans Commerce version 10.0.27, vous devez identifier les configurations d’affinement et d’attribut pour chaque catalogue B2B de la même manière que celle décrite dans cet article.

## <a name="override-attribute-values"></a>Remplacer les valeurs d’attribut

Les valeurs par défaut des attributs peuvent être remplacées pour les produits individuels au niveau du produit. Elles peuvent également être remplacées dans des catalogues spécifiques qui sont ciblés à des canaux spécifiques.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Remplacer les valeurs d’attribut d’un produit individuel

Pour remplacer les valeurs d’attribut d’un produit individuel, suivez les étapes de cet exemple de procédure.

1. Connectez-vous à Commerce headquarters comme responsable du commerce au détail.
1. Accédez à **Commerce et vente au détail \> Gestion des catégories et des produits \> Produits lancés par catégorie**.
1. Sélectionnez **Mode \> Accessoires de mode \> Lunettes de soleil de mode**.
1. Sélectionnez le produit requis dans la grille. Puis, sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Paramétrer**, cliquez sur **Attributs de produit**.
1. Sélectionnez un attribut dans le volet gauche, puis mettez sa valeur à jour dans le volet droit.

![Page des valeurs d’attribut de produit](media/ProdDetailsProdAttrValues_2022Series.png)

### <a name="override-the-attribute-values-of-all-products-in-a-catalog"></a>Remplacer les valeurs d’attribut de tous les produits dans un catalogue

Pour remplacer les valeurs d’attribut de tous les produits dans un catalogue, suivez les étapes de cet exemple de procédure.

1. Connectez-vous à Commerce headquarters comme responsable du commerce au détail.
1. Accédez à **Commerce et vente au détail \> Gestion des catalogues \> Tous les catalogues**.
1. Sélectionnez le catalogue **Catalogue de base de Fabrikam**.
1. Sélectionnez **Mode \> Accessoires de mode \> Lunettes de soleil de mode**.
1. Dans l’organisateur **Produits**, sélectionnez le produit requis, puis sélectionnez **Attributs** au-dessus de la grille de produit.
1. Dans les organisateurs suivants, mettez à jour les valeurs des attributs exigés :

    - Support de produit partagé
    - Attributs de produit partagés
    - Canal du support
    - Attributs de produit de canal

### <a name="override-the-attribute-values-of-all-products-in-a-channel"></a>Remplacer les valeurs d’attribut de tous les produits dans un canal

Pour remplacer les valeurs d’attribut de tous les produits dans un canal, suivez les étapes de cet exemple de procédure.

1. Connectez-vous à Commerce headquarters comme responsable du commerce au détail.
1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.
1. Sélectionnez le canal **Houston**.
1. Dans l’organisateur **Produits**, sélectionnez le produit requis, puis sélectionnez **Attributs** au-dessus de la grille de produit.
1. Si aucun produit n’est disponible, sélectionnez **Ajouter** sur l’organisateur **Produits**, puis sélectionnez les produits nécessaires dans la boîte de dialogue **Ajouter des produits**.
1. Dans les organisateurs suivants, mettez à jour les valeurs des attributs exigés :

    - Support de produit partagé
    - Attributs de produit partagés
    - Canal du support
    - Attributs de produit de canal

### <a name="define-variant-specific-attribute-values-and-define-multiple-values-for-product-attributes"></a>Définir des valeurs d’attribut spécifiques à une variante et définir plusieurs valeurs pour les attributs de produit

Pour définir des valeurs d’attribut spécifiques à une variante et pour définir plusieurs valeurs pour les attributs de produit, suivez les étapes de cet exemple de procédure.

1. Connectez-vous à Commerce headquarters comme responsable du commerce au détail.
1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.
1. Sélectionnez le canal **Houston**.
1. Dans l’organisateur **Produits**, sélectionnez la variante de produit requise, puis sélectionnez **Attributs** au-dessus de la grille de produit.
1. Si aucun produit n’est disponible, sélectionnez **Ajouter** sur l’organisateur **Produits**, puis sélectionnez les variantes de produits nécessaires dans la boîte de dialogue **Ajouter des produits**.
1. Dans les organisateurs suivants, mettez à jour les valeurs des attributs exigés :

    - Support de produit partagé
    - Attributs de produit partagés
    - Canal du support
    - Attributs de produit de canal

#### <a name="example-of-variant-specific-attribute-configuration"></a>Exemple de configuration d’attribut spécifique à une variante
        
Dans cet exemple, le produit **P001-Principal** est une chaussure multi-activités qui se décline en trois variantes : **Course à pied**, **Marche**, et **Trekking**. Pour chaque variante, vous souhaitez définir de manière unique la valeur de l’attribut **Activité**. Sur l’organisateur **Produits** de la page **Catégories de canaux et attributs de produits** de votre canal, vous définissez la valeur d’attribut **Activité** pour les variantes, comme indiqué dans le tableau suivant.

| Variante     | Valeur d’attribut d’activité |
|-------------|--------------------------|
| P001 - Principal | Sports                   |
| P001-1      | En cours d’exécution                  |
| P001-2      | Marche                  |
| P001-3      | Trekking                 |

Si un utilisateur recherche « chaussure », le produit **P001-Principal** apparaît dans les résultats de la recherche. Si vous avez configuré l’attribut **Activité** comme affinable, l’affinement **Activité** ne répertorie que **Sports** comme une valeur affinable, car cette valeur a été définie pour l’attribut **Activité** au niveau du produit **P001-Principal**.

Par défaut, les attributs de niveau variante sont destinés à être utilisés uniquement sur les pages de détails du produit (PDP). Lorsque vous sélectionnez une variante de produit spécifique sur une PDP, les spécifications du produit sur la PDP sont mises à jour pour cette variante spécifique.

Pour que les affinements sélectionnent les valeurs d’attribut définies au niveau de la variante de produit, vous devez définir un attribut au niveau du produit générique, cocher la case **Autoriser plusieurs valeurs** et définir le type d’attribut sur **Texte**.

Ensuite, vous devez déterminer toutes les valeurs possibles pour vos variantes de produit. Pour l’attribut **Activité** utilisé dans cet exemple, les valeurs possibles peuvent inclure **Course à pied**, **Marche**, **Randonnée**, **Trekking**, **Camping**, **Sports nautiques**, et **Sports de neige**.

Une fois que vous avez déterminé les valeurs d’attribut de variante, vous pouvez les définir au niveau du produit générique en utilisant des valeurs séparées par des barres verticales. Pour l’attribut **Activité**, vous pouvez définir la valeur de l’attribut sur le produit générique comme **Course à pied|Marche|Randonnée|Trekking|Camping|Sports nautiques|Sports de neige**.

Ensuite, pour chaque variante, vous pouvez définir des valeurs d’attribut en saisissant des valeurs séparées par des barres verticales ou des valeurs uniques. Pour l’attribut **Activité**, vous pouvez configurer une variante de produit individuelle comme **Course à pied|Marche|Randonnée**, **Course à pied**, **Course à pied|Randonnée|Sports nautiques**, etc.

Une fois que vous avez défini les valeurs d’attribut de variante, sur la page **Catégories de canaux et attributs de produits**, dans le volet Actions, sélectionnez **Publier les mises à jour du canal**, puis exécutez les tâches **1150**, **1040**, et **1070**.

Une fois les travaux terminés et l’index de recherche mis à jour, toutes les valeurs attendues doivent apparaître dans les résultats de la recherche et les résultats de navigation dans les catégories.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
