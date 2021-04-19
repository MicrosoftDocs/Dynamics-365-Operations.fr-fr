---
title: Expérience produit unifiée
description: Cette rubrique décrit l’intégration des données de produit entre les applications Finance and Operations et Dataverse.
author: t-benebo
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 3087ab8853b14308da9496eead7478822cec86b8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750738"
---
# <a name="unified-product-experience"></a>Expérience produit uniformisée

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Lorsqu’un écosystème professionnel est constitué d’applications Dynamics 365, comme Finance, Supply Chain Management et Sales, il est naturel pour les entreprises d’utiliser ces applications pour approvisionner les données de produit. En effet, ces applications offrent une infrastructure de produit robuste complétée par des concepts de tarification sophistiqués et des données de stock disponible précises. Les entreprises qui utilisent un système PLM (gestion des cycles de vie des produits) externe pour approvisionner les données de produit peuvent diriger les produits des applications Finance and Operations vers les autres applications Dynamics 365. L’expérience produit unifiée fournit le modèle de données de produit intégré dans Dataverse de sorte que tous les utilisateurs des applications, dont les utilisateurs de Power Platform, puissent tirer parti des données de produit enrichies provenant des applications Finance and Operations.

Voici le modèle de données produit de Sales.

![Modèle de données pour les produits dans CE](media/dual-write-product-4.jpg)

Voici le modèle de données de produit provenant des applications Finance and Operations.

![Modèle de données pour les produits dans Finance and Operations](media/dual-write-products-5.jpg)

Ces deux modèles de données produit ont été intégrés dans Dataverse comme indiqué ci-dessous.

![Modèle de données pour les produits des applications Dynamics 365](media/dual-write-products-6.jpg)

Les cartes de table de double écriture pour les produits ont été conçues afin de diriger les données de manière unidirectionnelle, quasiment en temps réel des applications Finance and Operations vers Dataverse. Toutefois, l’infrastructure de produit a été ouverte pour les rendre bidirectionnelles, le cas échéant. Même si vous pouvez les personnaliser, cela reste à votre propre risque, puisque Microsoft ne recommande pas cette approche.

## <a name="templates"></a>Modèles

Les informations de produit contiennent toutes les informations associées au produit et à sa définition, comme les dimensions du produit ou les dimensions de suivi et de stockage. Lorsque le tableau suivant s’affiche, un ensemble de cartes de tables est créé pour synchroniser les produits et les informations associées.

Applications Finance and Operations | Autres applications Dynamics 365 | Description
-----------------------|--------------------------------|---
Produits lancés V2 | msdyn\_sharedproductdetails | La table **msdyn\_sharedproductdetails** contient les colonnes des applications Finance and Operations qui définissent le produit et qui contiennent les informations de gestion et financières du produit. 
Produits distincts lancés pour Dataverse | Produit | La table **Produit** contient les colonnes qui définissent le produit. Elle comprend les différents produits (produits avec produit de sous-type) et les variantes de produit. Le tableau suivant présente les mises en correspondance.
Numéro de produit identifié par code-barres | msdyn\_productbarcodes | Les codes-barres de produit permettent d’identifier de manière unique les produits.
Paramètres de commande par défaut | msdyn\_productdefaultordersettings
Paramètres de commande par défaut spécifiques au produit | msdyn_productdefaultordersettings
Groupes de dimensions de produit | msdyn\_productdimensiongroups | Le groupe de dimensions de produit a défini quelles dimensions de produit définissent le produit. 
Groupes de dimension de stockage | msdyn\_productstoragedimensiongroups | Le groupe de dimensions de stockage de produit représente la méthode utilisée pour définir l’emplacement du produit dans l’entrepôt.
Groupes de dimension de suivi | msdyn\_producttrackingdimensiongroups | Le groupe de dimensions de suivi de produit représente la méthode utilisée pour suivre le produit dans le stock.
Couleurs | msdyn\_productcolors
Tailles | msdyn\_productsizes
Styles | msdyn\_productsytles
Configurations | msdyn\_productconfigurations
Couleurs de produit générique | msdyn_sharedproductcolors | La table **Couleur de produit partagée** indique les couleurs qu’un produit générique spécifique peut avoir. Ce concept effectue une migration vers Dataverse pour préserver la cohérence des données.
Tailles de produit générique | msdyn_sharedproductsizes | La table **Taille de produit partagée** indique les tailles qu’un produit générique spécifique peut avoir. Ce concept effectue une migration vers Dataverse pour préserver la cohérence des données.
Styles de produit générique | msdyn_sharedproductstyles | La table **Style de produit partagé** indique les styles qu’un produit générique spécifique peut avoir. Ce concept effectue une migration vers Dataverse pour préserver la cohérence des données.
Configurations de produit générique | msdyn_sharedproductconfigurations | La table **Configuration de produit partagée** indique les configurations qu’un produit générique spécifique peut avoir. Ce concept effectue une migration vers Dataverse pour préserver la cohérence des données.
Tous les produits | msdyn_globalproducts | La table Tous les produits contient tous les produits disponibles dans les applications Finance and Operations, à la fois les produits lancés et les produits non lancés.
Unité | UM
Conversion d’unités | msdyn_ unitofmeasureconversions
Conversion de l’unité de mesure spécifique au produit | msdyn_productspecificunitofmeasureconversion
Catégories de produits | msdyn_productcategories | Chacune des catégories de produit et des informations sur sa structure et ses caractéristiques sont contenues dans la table de catégorie de produit. 
Hiérarchie de catégories de produit | msdyn_productcategoryhierarhies | Vous utilisez les hiérarchies de produits pour classer par catégorie ou regrouper les produits. Les hiérarchies de catégories sont disponibles dans Dataverse à l’aide de la table de hiérarchie des catégories de produits. 
Rôles de hiérarchie de catégories de produit | msdyn_productcategoryhierarchies | Les hiérarchies de produits peuvent être utilisées pour plusieurs rôles dans D365 Finance and Operations. Pour indiquer quelle catégorie est utilisée dans chaque rôle, la table de rôle de catégorie du produit est utilisée. 
Affectations de catégorie de produit | msdyn_productcategoryassignments | Pour affecter un produit à une catégorie, la table d’affectations de catégorie de produit peut être utilisée.

## <a name="integration-of-products"></a>Intégration des produits

Dans ce modèle, le produit est représenté par la combinaison des deux tables dans Dataverse : **Produit** et **msdyn\_sharedproductdetails**. Tandis que la première table contient la définition d’un produit (l’identificateur unique du produit, le nom du produit et la description), la deuxième table contient les colonnes stockées au niveau du produit. La combinaison de ces deux tables est utilisée pour définir le produit selon le concept de l’unité de gestion de stock (SKU). Chaque produit lancé a ses informations dans les tables mentionnées (Produit et Détails du produit partagés). Pour mettre à jour tous les produits (lancés et non lancés), la table **Produits globaux** est utilisée. 

Comme le produit est représenté par un SKU, les concepts des produits distincts, les produits génériques, et des variantes de produit peuvent être capturés dans Dataverse de la façon suivante :

- **Produits avec le produit de sous-type** sont des produits définis par eux-mêmes. Aucune dimension ne doit être définie. Un exemple est un registre spécifique. Pour ces produits, une ligne est créée dans la table **Produit**, et une ligne est créée dans la table **msdyn\_sharedproductdetails**. Aucune ligne de famille de produits n’est créée.
- Les **Produits génériques** sont utilisés pour mettre à jour la définition et les règles qui déterminent le comportement dans les processus métier. En fonction de ces définitions, les produits distincts qui sont connus comme variantes de produit peuvent être générés. Par exemple, le t-shirt est le produit générique, et il sa couleur et sa taille sont ses dimensions. Les variantes peuvent être lancées avec différentes combinaisons de ces dimensions, comme un t-shirt bleu taille S ou un t-shirt vert taille M. Lors de l’intégration, une ligne par variante est créée dans la table du produit. Cette ligne contient les informations propres à la variante, comme les différentes dimensions. Les informations génériques pour le produit sont enregistrées dans la table **msdyn\_sharedproductdetails**. (Ces informations génériques sont répertoriées dans le produit générique.) Les informations de produit générique sont synchronisées vers Dataverse dès que le produit générique lancé est créé (mais avant le lancement des variantes).
- Les **Produits distincts** font référence à tous les sous-types et à toutes les variantes de produit. 

![Modèle de données pour les produits](media/dual-write-product.png)

Si la fonctionnalité de double écriture est activée, les produits de Finance and Operations seront synchronisés dans d’autres produits Dynamics 365 en mode **Brouillon**. Elles sont ajoutées à la première liste de prix avec la même devise. Autrement dit, elles sont ajoutées à la première liste de prix dans une application Dynamics 365 qui correspond à la devise de la table juridique dans laquelle le produit est lancé dans une application Finance and Operations. S’il n’y a pas de liste de prix pour la devise donnée, une liste de prix sera automatiquement créée et le produit lui sera attribué. 

L’implémentation actuelle des plugins à double écriture qui associent la liste de prix par défaut à l’unité recherche la devise associée à l’application Finance and Operations et identifie la première liste de prix dans l’application Customer Engagement en utilisant le tri alphabétique sur le nom de la liste de prix. Pour définir une liste de prix par défaut pour une devise spécifique lorsque vous avez plusieurs listes de prix pour cette devise, vous devez mettre à jour le nom de la liste de prix avec un nom commençant par une lettre antérieure dans l’ordre alphabétique par rapport aux autres listes de prix pour cette même devise.

Par défaut, les produits en provenance des applications Finance and Operations sont synchronisés avec les autres applications Dynamics 365 en mode **Brouillon**. Pour synchroniser le produit à l’état **Actif**, afin de pouvoir l’utiliser directement dans les devis de commande client, par exemple, le paramètre suivant doit être choisi : sous **Système > Adminstration > Administration système > Paramètres système > Ventes** sélectionnez **Créer des produits à l’état actif = Oui**. 

Lorsque les produits sont synchronisés, vous devez entrer une valeur pour le champ **Unité de vente** de l’application Finance and Operations, car il s’agit d’un champ obligatoire dans Sales.

La création de familles de produits à partir de Dynamics 365 Sales n’est pas prise en charge avec la synchronisation en double écriture des produits.

La synchronisation des produits se produit de l’application Finance and Operations vers Dataverse. Cela signifie que les valeurs des colonnes de table du produit peuvent être modifiées dans Dataverse, mais lorsque la synchronisation est déclenchée (lorsqu’une colonne de produit est modifié dans une application Finance and Operations), les valeurs seront remplacées dans Dataverse. 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [products](includes/EcoResReleasedDistinctProductCDSEntity-products.md)]

[!include [product details](includes/EcoResReleasedProductV2-msdyn-sharedproductdetails.md)]

[!include [global products](includes/EcoResEveryProductEntity-msdyn-globalproducts.md)]

## <a name="product-dimensions"></a>Dimensions de produit 

Les dimensions de produit sont des caractéristiques qui identifient une variante de produit. Les quatre dimensions de produit (Couleur, Taille, Style et Configuration) sont également mis en correspondance avec Dataverse pour définir les variantes de produit. L’illustration suivante présente le modèle de données pour la dimension de produit Couleur. Le même modèle s’applique aux dimensions Taille, Style et Configuration. 

![Modèle de données pour les dimensions de produit](media/dual-write-product-two.png)

[!include [product colors](includes/EcoResProductColorEntity-msdyn-productcolor.md)]

[!include [product sizes](includes/EcoResProductSizeEntity-msdyn-productsizes.md)]

[!include [product sizes](includes/EcoResProductStyleEntity-msdyn-productstyles.md)]

[!include [product sizes](includes/EcoResProductConfigurationsEntity-msdyn-productconfigurations.md)]

Lorsqu’un produit a différentes dimensions de produit (par exemple, un produit générique a des dimensions de produit Taille et Couleur), chaque produit distinct (à savoir, chaque variante de produit) est défini comme combinaison de ces dimensions de produit. Par exemple, le numéro de produit B0001 correspond à un t-shirt noir taille XS, le numéro de produit B0002 correspond à un t-shirt noir taille S. Dans ce cas, les combinaisons existantes des dimensions de produit sont définies. Par exemple, le t-shirt de l’exemple précédent peut être de taille XS et noir, de taille S et noir, de taille M et noir ou de taille L et noir, mais il ne peut pas être de taille XL et noir. Autrement dit, les dimensions de produit qu’un produit générique peut prendre sont spécifiées, et les variantes peuvent être lancées selon ces valeurs.

Pour mettre à jour les dimensions de produit qu’un produit générique peut prendre, les tables suivantes sont créées et mises en correspondance dans Dataverse pour chaque dimension de produit. Pour plus d’informations, voir [Vue d’ensemble des informations de produit](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/pim/product-information).

[!include [product colors](includes/EcoResProductMasterColorEntity-msdyn-sharedproductcolors.md)]

[!include [product sizes](includes/EcoResProductMasterSize-msdyn-sharedproductsizes.md)]

[!include [product styles](includes/EcoResProductMasterStyleEntity-msdyn-sharedproductstyles.md)]

[!include [product configurations](includes/EcoResProductMasterConfigurationEntity-msdyn-sharedproductconfigurations.md)]

[!include [product bar codes](includes/EcoResProductNumberIdentifiedBarcode-msdyn-productbarcodes.md)]

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Paramètres de commande par défaut et paramètres de commande par défaut spécifiques au produit

Les paramètres de commande par défaut définissent le site et l’entrepôt d’où les articles seront originaires ou stockés, les quantités minimales, maximales, multiples et standard qui seront utilisées pour le commerce ou la gestion des stocks, les délais, l’indicateur de fin, et la méthode de promesse de commande. Ces informations seront disponibles dans Dataverse à l’aide des paramètres de commande par défaut et de l’entité des paramètres de commande par défaut spécifiques au produit. Pour en savoir plus sur la fonctionnalité, voir la [Rubrique Paramètres de commande par défaut](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/default-order-settings).

[!include [product sizes](includes/InventProductDefaultOrderSettingsEntity-msdyn-productdefaultordersetting.md)]

[!include [product sizes](includes/InventProductSpecificOrderSettingsV2Entity-msdyn-productspecificdefaultordersetting.md)]

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Unité de mesure et conversions des unités de mesure

Les unités de mesure et les conversions respectives sont disponibles dans Dataverse suivant le modèle de données affiché dans le diagramme.

![Modèle de données pour l’unité de mesure](media/dual-write-product-three.png)

Le concept d’unité de mesure est intégré entre les applications Finance and Operations et les autres applications Dynamics 365. Pour chaque classe d’unités d’une application Finance and Operations, un groupe d’unités est créé dans une application Dynamics 365, qui contient les unités appartenant à la classe d’unités. Une unité de base par défaut est également créée pour chaque groupe d’unité. 

[!include [unit of measure](includes/UnitOfMeasureEntity-uom.md)]

[!include [unit of measure conversions](includes/UnitOfMeasureConversionEntity-msdyn-unitofmeasureconversions.md)]

[!include [product-specific unit of measure conversions](includes/EcoResProductSpecificUnitConversionEntity-msdyn-productspecificunitofmeasureconversions.md)]

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Synchronisation initiale de la mise en correspondance des données des unités entre Finance and Operations et Dataverse

### <a name="initial-synchronization-of-units"></a>Synchronisation initiale des unités

Lorsque l’écriture double est activée, les unités en provenance des applications Finance and Operations sont synchronisées avec les autres applications Dynamics 365. Les groupes d’unités synchronisés à partir des applications Finance and Operations dans Dataverse ont un indicateur défini sur « Géré en externe ».

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Mise en correspondance des unités et des données de groupes/classes d’unités à partir de Finance and Operations et des autres applications Dynamics 365

Premièrement, il est important de noter que la clé d’intégration de l’unité est msdyn_symbol. Par conséquent, cette valeur doit être unique dans Dataverse ou d’autres applications Dynamics 365. Parce que dans les autres applications Dynamics 365 c’est la paire « ID de groupe d’unités » et « Nom » qui définissent le côté unique d’une unité, vous devez tenir compte de différents scénarios pour mettre en correspondance les données d’unité entre les applications Finance and Operations et Dataverse.

Pour que les unités se mettent en correspondance/se chevauchent dans les applications Finance and Operations et les autres applications Dynamics 365 :

+ **L’unité appartient à un groupe d’unités dans les autres applications Dynamics 365 qui correspond à la classe d’unités associée dans les applications Finance and Operations**. Dans ce cas, la colonne msdyn_symbol dans les autres applications Dynamics 365 doit être renseigné avec le symbole d’unité des applications Finance and Operations. Par conséquent, lorsque les données seront mises en correspondance, et lorsque le groupe d’unités sera défini comme « Géré en externe » dans d’autres applications Dynamics 365.
+ **L’unité appartient à un groupe d’unités dans les autres applications Dynamics 365 qui ne correspond pas à la classe d’unités associée dans les applications Finance and Operations (aucune classe d’unités existante dans les applications Finance and Operations pour la classe d’unités dans les autres applications Dynamics 365).** Dans ce cas, le msdyn_symbol doit être renseigné avec une chaîne aléatoire. Notez que cette valeur doit être unique dans d’autres applications Dynamics 365.

Pour les unités et les classes d’unités dans Finance and Operations n’existant pas dans les autres applications Dynamics 365 :

Dans le cadre de la double écriture, des groupes d’unités à partir des applications Finance and Operations et leurs unités correspondantes sont créés et synchronisés dans les autres applications Dynamics 365 et Dataverse et le groupe d’unités sont définis sur « Géré en externe ». Aucun effort supplémentaire au démarrage n’est requis.

Pour les unités dans les autres applications Dynamics 365 qui n’existent pas dans les applications Finance and Operations :

La colonne msdyn_symbol doit être remplie pour toutes les unités. Les unités peuvent toujours être créées dans les applications Finance and Operations dans la classe d’unités correspondante (si elle existe). Si la classe d’unités n’existe pas, commencez par créer la classe d’unités (notez que vous ne pouvez pas créer une classe d’unités dans les applications Finance and Operations sauf par l’extension si vous étendez l’énumération) et elle doit correspondre à l’autre groupe d’unités dans les applications Dynamics 365. Vous pouvez ensuite créer la nouvelle unité. Notez que le symbole d’unité dans les applications Finance and Operations doit être le champ msdyn_symbol précédemment renseigné dans les autres applications Dynamics 365 pour l’unité.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Stratégies de produit : groupes de dimensions, de suivi et de stockage

Les stratégies de produit désignent des ensembles de stratégies utilisées pour définir des produits et leurs caractéristiques dans le stock. Le groupe de dimensions de produit, le groupe de dimensions de suivi de produit et le groupe de dimensions de stockage peuvent se présenter comme stratégies de produit. 

[!include [product dimension group](includes/EcoResProductDimensionGroup-msdyn-productdimensiongroups.md)]

[!include [product tracking dimension group](includes/EcoResTrackingDimensionGroup-msdyn-producttrackingdimensiongroups.md)]

[!include [product storage dimension group](includes/EcoResStorageDimensionGroup-msdyn-productstoragedimensiongroups.md)]

## <a name="product-hierarchies"></a>Hiérarchies de produit

[!include [product category hierarchy](includes/EcoResProductCategoryHierarchyEntity-msdyn-productcategoryhierarchy.md)]

[!include [product category](includes/EcoResProductCategoryEntity-msdyn-productcategory.md)]

[!include [product category assignments](includes/EcoResProductCategoryAssignmentEntity-msdyn-productcategoryassignment.md)]

[!include [product category role](includes/EcoResProductCategoryHierarchyRoleEntity-msdyn-productcategoryhierarchyrole.md)]


## <a name="integration-key-for-products"></a>Clé d’intégration pour les produits 

Pour identifier de manière unique les produits entre Dynamics 365 for Finance and Operations et les produits dans Dataverse, les clés d’intégration sont utilisées. Pour les produits, le **(numérodeproduit)** est la clé unique qui identifie un produit dans Dataverse. Il est composé par la concaténation de : **(société, msdyn_productnumber)**. Le champ **Société** indique l’entité juridique dans Finance and Operations et le champ **msdyn_productnumber** indique le numéro de produit pour le produit donné dans Finance and Operations. 

Pour les utilisateurs d’autres applications Dynamics 365, le produit est reconnu dans l’interface utilisateur avec le champ **msdyn_productnumber** (notez que le libellé de la colonne est **Numéro de produit**). Dans l’écran de produit les champs de société et de msydn_productnumber sont affichés. Toutefois, la colonne (numérodeproduit), la clé unique pour un produit, n’apparaît pas. 

Si vous créez des applications sur Dataverse, vous devez veiller à utiliser le **numéro de produit** (l’ID de produit unique) comme clé d’intégration. N’utilisez pas **msdyn_productnumber**, car il n’est pas unique. 

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Synchronisation initiale des produits et migration des données de Dataverse vers Finance and Operations

### <a name="initial-synchronization-of-products"></a>Synchronisation initiale des produits 

Lorsque la double écriture est activée, les produits des applications Finance and Operations sont synchronisés avec Dataverse et les applications Customer Engagement. Les produits créés dans Dataverse et les autres applications Dynamics 365 avant la publication de la double écriture ne seront pas mis à jour ou mis en correspondance avec les données des produits des applications Finance and Operations.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Mise en correspondance des données de produit à partir de Finance and Operations et des autres applications Dynamics 365

Si les mêmes produits sont conservés (chevauchement/correspondance) dans Finance and Operations et dans Dataverse et les autres applications Dynamics 365, lors de l’application de la double écriture, la synchronisation des produits de Finance and Operations a lieu et des doublons de ligne apparaissent dans Dataverse pour le même produit.
Pour éviter la situation précédente, si d’autres applications Dynamics 365 contiennent des produits qui se chevauchent/sont mis en correspondance avec Finance and Operations, l’administrateur activant la double écriture doit amorcer les colonnes **Société** (par ex. : « USMF ») et **msdyn_productnumber** (par ex. : « 1234:Black:S ») avant la synchronisation des produits. Autrement dit, ces deux colonnes au niveau du produit dans Dataverse doivent être renseignées avec la société concernée dans Finance and Operations avec laquelle le produit doit être mis en correspondance et avec son numéro de produit. 

Puis, lorsque la synchronisation est activée et survient, les produits en provenance de Finance and Operations sont synchronisés avec les produits associés dans Dataverse et les autres applications Dynamics 365. Ce champ s’applique aux produits distincts et des variantes de produit. 


### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migration des données de produit provenant des autres applications Dynamics 365 vers Finance and Operations

Si les autres applications Dynamics 365 contiennent des produits qui ne sont pas présents dans Finance and Operations, l’administrateur peut d’abord utiliser **EcoResReleasedProductCreationV2Entity** pour importer ces produits dans Finance and Operations. Il doit ensuite mettre en correspondance les données de produit en provenance de Finance and Operations et des autres applications Dynamics 365, comme décrit ci-dessus. 


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
