---
title: Expérience produit uniformisée
description: Cet article décrit l’intégration des données de produit entre les applications de finances et d’opérations et Dataverse.
author: t-benebo
ms.date: 06/23/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 89ef56510ec971ef97fc9eb5c80768527abf5f88
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288920"
---
# <a name="unified-product-experience"></a>Expérience produit uniformisée

[!include [banner](../../includes/banner.md)]



Lorsqu’un écosystème professionnel est constitué d’applications Dynamics 365, comme Finance, Supply Chain Management et Sales, il est naturel pour les entreprises d’utiliser ces applications pour approvisionner les données de produit. En effet, ces applications offrent une infrastructure de produit robuste complétée par des concepts de tarification sophistiqués et des données de stock disponible précises. Les entreprises qui utilisent un système PLM (gestion du cycle de vie du produit) pour approvisionner les données de produit peuvent diriger les produits des applications de finances et d’opérations vers d’autres applications Dynamics 365. L’expérience produit unifiée fournit le modèle de données de produit intégré à Dataverse, de telle sorte que tous les utilisateurs des applications, y compris les utilisateurs Power Platform, peuvent tirer parti des données produit enrichies provenant des applications de finances et d’opérations.

Voici le modèle de données produit de Sales.

![Modèle de données pour les produits dans CE.](media/dual-write-product-4.jpg)

Voici le modèle de données produit provenant des applications de finances et d’opérations.

![Modèle de données pour les produits de finances et d’opérations.](media/dual-write-products-5.jpg)

Ces deux modèles de données produit ont été intégrés dans Dataverse comme indiqué ci-dessous.

![Modèle de données pour les produits des applications Dynamics 365.](media/dual-write-products-6.jpg)

Les cartes de table en double écriture pour les produits ont été conçues afin de diriger les données de manière unidirectionnelle ; il s’agit là d’une expérience quasiment en temps réel des applications de finances et d’opérations vers Dataverse. Toutefois, l’infrastructure de produit a été ouverte pour les rendre bidirectionnelles, le cas échéant. Même si vous pouvez les personnaliser, cela reste à votre propre risque, puisque Microsoft ne recommande pas cette approche.

## <a name="templates"></a>Modèles

Les informations de produit contiennent toutes les informations associées au produit et à sa définition, comme les dimensions du produit ou les dimensions de suivi et de stockage. Lorsque le tableau suivant s’affiche, un ensemble de cartes de tables est créé pour synchroniser les produits et les informations associées.

Applications de finances et d'opérations | Autres applications Dynamics 365 | Description
-----------------------|--------------------------------|---
[Tous les produits](mapping-reference.md#138) | msdyn_globalproducts | La table Tous les produits contient tous les produits disponibles dans les applications de finances et d’opérations, à la fois les produits lancés et les produits non lancés.
[Produits distincts lancés pour CDS](mapping-reference.md#213) | Produit | La table **Produit** contient les colonnes qui définissent le produit. Elle comprend les différents produits (produits avec produit de sous-type) et les variantes de produit. Le tableau suivant présente les mises en correspondance.
[Couleurs](mapping-reference.md#170) | msdyn\_productcolors
[Configurations](mapping-reference.md#171) | msdyn\_productconfigurations
[Paramètres de commande par défaut](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Catégories de produits](mapping-reference.md#166) | msdyn_productcategories | Chacune des catégories de produit et des informations sur sa structure et ses caractéristiques sont contenues dans la table de catégorie de produit.
[Affectations de catégorie de produit](mapping-reference.md#167) | msdyn_productcategoryassignments | Pour affecter un produit à une catégorie, la table d’affectations de catégorie de produit peut être utilisée.
[Hiérarchie de catégories de produit](mapping-reference.md#168) | msdyn_productcategoryhierarchies | Vous utilisez les hiérarchies de produits pour classer par catégorie ou regrouper les produits. Les hiérarchies de catégories sont disponibles dans Dataverse à l’aide de la table de hiérarchie des catégories de produits.
[Rôles de hiérarchie de catégories de produit](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles | Les hiérarchies de produit peuvent être utilisées pour plusieurs rôles dans les applications de finances et d’opérations de D365. Pour indiquer quelle catégorie est utilisée dans chaque rôle, la table de rôle de catégorie du produit est utilisée.
[Paramètres de commande par défaut du produit V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |
[Groupes de dimensions de produit](mapping-reference.md#173) | msdyn\_productdimensiongroups | Le groupe de dimensions de produit a défini quelles dimensions de produit définissent le produit.
[Couleurs de produit générique](mapping-reference.md#187) | msdyn_sharedproductcolors | La table **Couleur de produit partagée** indique les couleurs qu’un produit générique spécifique peut avoir. Ce concept effectue une migration vers Dataverse pour préserver la cohérence des données.
[Configurations de produit générique](mapping-reference.md#188) | msdyn_sharedproductconfigurations | La table **Configuration de produit partagée** indique les configurations qu’un produit générique spécifique peut avoir. Ce concept effectue une migration vers Dataverse pour préserver la cohérence des données.
[Tailles de produit générique](mapping-reference.md#190) | msdyn_sharedproductsizes | La table **Taille de produit partagée** indique les tailles qu’un produit générique spécifique peut avoir. Ce concept effectue une migration vers Dataverse pour préserver la cohérence des données.
[Styles de produit générique](mapping-reference.md#191) | msdyn_sharedproductstyles | La table **Style de produit partagé** indique les styles qu’un produit générique spécifique peut avoir. Ce concept effectue une migration vers Dataverse pour préserver la cohérence des données.
[Numéro de produit identifié par code-barres](mapping-reference.md#164) | msdyn\_productbarcodes | Les codes-barres de produit permettent d’identifier de manière unique les produits.
[Conversions d’unités spécifiques à un produit](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Produits lancés V2](mapping-reference.md#189) | msdyn\_sharedproductdetails | La table **msdyn\_sharedproductdetails** contient les colonnes des applications de finances et d’opérations qui définissent le produit, et qui contiennent les informations de gestion et les informations financières relatives au produit.
[Tailles](mapping-reference.md#174) | msdyn\_productsizes
[Groupes de dimension de stockage](mapping-reference.md#177) | msdyn_productstoragedimensiongroups | Le groupe de dimensions de stockage de produit représente la méthode utilisée pour définir l’emplacement du produit dans l’entrepôt.
[Styles](mapping-reference.md#178) | msdyn\_productstyles
[Groupes de dimension de suivi](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups | Le groupe de dimensions de suivi de produit représente la méthode utilisée pour suivre le produit dans le stock.
[Unités](mapping-reference.md#219) | UM
[Conversion d’unités](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="integration-of-products"></a>Intégration des produits

Dans ce modèle, le produit est représenté par la combinaison des deux tables dans Dataverse : **Produit** et **msdyn\_sharedproductdetails**. Tandis que la première table contient la définition d’un produit (l’identificateur unique du produit, le nom du produit et la description), la deuxième table contient les colonnes stockées au niveau du produit. La combinaison de ces deux tables est utilisée pour définir le produit selon le concept de l’unité de gestion de stock (SKU). Chaque produit lancé a ses informations dans les tables mentionnées (Produit et Détails du produit partagés). Pour mettre à jour tous les produits (lancés et non lancés), la table **Produits globaux** est utilisée.

Comme le produit est représenté par un SKU, les concepts des produits distincts, les produits génériques, et des variantes de produit peuvent être capturés dans Dataverse de la façon suivante :

- **Produits avec le produit de sous-type** sont des produits définis par eux-mêmes. Aucune dimension ne doit être définie. Un exemple est un registre spécifique. Pour ces produits, une ligne est créée dans la table **Produit**, et une ligne est créée dans la table **msdyn\_sharedproductdetails**. Aucune ligne de famille de produits n’est créée.
- Les **Produits génériques** sont utilisés pour mettre à jour la définition et les règles qui déterminent le comportement dans les processus métier. En fonction de ces définitions, les produits distincts qui sont connus comme variantes de produit peuvent être générés. Par exemple, le t-shirt est le produit générique, et il sa couleur et sa taille sont ses dimensions. Les variantes peuvent être lancées avec différentes combinaisons de ces dimensions, comme un t-shirt bleu taille S ou un t-shirt vert taille M. Lors de l’intégration, une ligne par variante est créée dans la table du produit. Cette ligne contient les informations propres à la variante, comme les différentes dimensions. Les informations génériques pour le produit sont enregistrées dans la table **msdyn\_sharedproductdetails**. (Ces informations génériques sont répertoriées dans le produit générique.) Les informations de produit générique sont synchronisées vers Dataverse dès que le produit générique lancé est créé (mais avant le lancement des variantes).
- Les **Produits distincts** font référence à tous les sous-types et à toutes les variantes de produit.

![Modèle de données pour les produits.](media/dual-write-product.png)

Si la fonctionnalité de double écriture est activée, les produits de finances et opérations seront synchronisés dans d’autres produits Dynamics 365 en mode **Brouillon**. Ils sont ajoutés à la première liste de prix avec la même devise que celle utilisée dans l’application d’engagement client et en utilisant le tri alphabétique sur le nom de la liste de prix. En d’autres termes, elles sont ajoutées à la première liste de prix dans une application Dynamics 365 qui correspond à la devise de votre table juridique où le produit est lancé dans une application de finances et d’opérations. S’il n’y a pas de liste de prix pour la devise donnée, une liste de prix sera automatiquement créée et le produit lui sera attribué.

L’implémentation actuelle des plug-ins à double écriture qui associent la liste de prix par défaut à l’unité recherche la devise associée à l’application de finances et d’opérations et identifie la première liste de prix dans l’application Customer Engagement en utilisant le tri alphabétique sur le nom de la liste de prix. Pour définir une liste de prix par défaut pour une devise spécifique lorsque vous avez plusieurs listes de prix pour cette devise, vous devez mettre à jour le nom de la liste de prix avec un nom commençant par une lettre antérieure dans l’ordre alphabétique par rapport aux autres listes de prix pour cette même devise. S’il n’a pas de liste de prix pour la devise donnée, une nouvelle est créée.

Par défaut, les produits des applications de finances et d’opérations sont synchronisés vers les autres applications Dynamics 365 à l’état **Brouillon**. Pour synchroniser le produit à l’état **Actif**, afin de pouvoir l’utiliser directement dans les devis de commande client, par exemple, le paramètre suivant doit être choisi : sous **Système > Adminstration > Administration système > Paramètres système > Ventes** sélectionnez **Créer des produits à l’état actif = Oui**.

Lorsque les produits sont synchronisés, vous devez entrer une valeur pour le champ **Unité de vente** de l’application de finances et d’opérations, car il s’agit d’un champ obligatoire dans Sales.

La création de familles de produits à partir de Dynamics 365 Sales n’est pas prise en charge avec la synchronisation en double écriture des produits.

La synchronisation des produits survient depuis l’application de finances et d’opérations vers Dataverse. Cela signifie que les valeurs des colonnes de table de produit peuvent être modifiées dans Dataverse, mais lorsque la synchronisation est déclenchée (lorsqu’une colonne de produit est modifiée dans une application de finances et d’opérations), les valeurs seront remplacées dans Dataverse.

Applications de finances et d'opérations | Applications Customer Engagement |
---|---
[Produits distincts lancés pour CDS](mapping-reference.md#213) | Produit |
[Produits lancés V2](mapping-reference.md#189) | msdyn_sharedproductdetails |
[Tous les produits](mapping-reference.md#138) | msdyn_globalproducts |

## <a name="product-dimensions"></a>Dimensions de produit

Les dimensions de produit sont des caractéristiques qui identifient une variante de produit. Les quatre dimensions de produit (Couleur, Taille, Style et Configuration) sont également mis en correspondance avec Dataverse pour définir les variantes de produit. L’illustration suivante présente le modèle de données pour la dimension de produit Couleur. Le même modèle s’applique aux dimensions Taille, Style et Configuration.

![Modèle de données pour les dimensions de produit.](media/dual-write-product-two.png)

Applications de finances et d’opérations | Applications Customer Engagement |
---|---
[Couleurs](mapping-reference.md#170) | msdyn\_productcolors
[Tailles](mapping-reference.md#174) | msdyn\_productsizes
[Styles](mapping-reference.md#178) | msdyn\_productstyles
[Configurations](mapping-reference.md#171) | msdyn\_productconfigurations

Lorsqu’un produit a différentes dimensions de produit (par exemple, un produit générique a des dimensions de produit Taille et Couleur), chaque produit distinct (à savoir, chaque variante de produit) est défini comme combinaison de ces dimensions de produit. Par exemple, le numéro de produit B0001 correspond à un t-shirt noir taille XS, le numéro de produit B0002 correspond à un t-shirt noir taille S. Dans ce cas, les combinaisons existantes des dimensions de produit sont définies. Par exemple, le t-shirt de l’exemple précédent peut être de taille XS et noir, de taille S et noir, de taille M et noir ou de taille L et noir, mais il ne peut pas être de taille XL et noir. Autrement dit, les dimensions de produit qu’un produit générique peut prendre sont spécifiées, et les variantes peuvent être lancées selon ces valeurs.

Pour mettre à jour les dimensions de produit qu’un produit générique peut prendre, les tables suivantes sont créées et mises en correspondance dans Dataverse pour chaque dimension de produit. Pour plus d’informations, voir [Vue d’ensemble des informations de produit](../../../../supply-chain/pim/product-information.md).

Applications de finances et d’opérations | Applications Customer Engagement |
---|---
[Couleurs de produit générique](mapping-reference.md#187) | msdyn_sharedproductcolors |
[Configurations de produit générique](mapping-reference.md#188) | msdyn_sharedproductconfigurations |
[Tailles de produit générique](mapping-reference.md#190) | msdyn_sharedproductsizes |
[Styles de produit générique](mapping-reference.md#191) | msdyn_sharedproductstyles |
[Numéro de produit identifié par code-barres](mapping-reference.md#164) | msdyn\_productbarcodes |

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Paramètres de commande par défaut et paramètres de commande par défaut spécifiques au produit

Les paramètres de commande par défaut définissent le site et l’entrepôt d’où les articles seront originaires ou stockés, les quantités minimales, maximales, multiples et standard qui seront utilisées pour le commerce ou la gestion des stocks, les délais, l’indicateur de fin, et la méthode de promesse de commande. Ces informations seront disponibles dans Dataverse à l’aide des paramètres de commande par défaut et de l’entité des paramètres de commande par défaut spécifiques au produit. Pour en savoir plus sur la fonctionnalité, consultez [l’article Paramètres de commande par défaut](../../../../supply-chain/production-control/default-order-settings.md).

Applications de finances et d’opérations | Applications Customer Engagement |
---|---
[Paramètres de commande par défaut](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Paramètres de commande par défaut du produit V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Unité de mesure et conversions des unités de mesure

Les unités de mesure et les conversions respectives sont disponibles dans Dataverse suivant le modèle de données affiché dans le diagramme.

![Modèle de données pour l’unité de mesure.](media/dual-write-product-three.png)

Le concept d’unité de mesure est intégré entre les applications de finances et d’opérations et toute autre application Dynamics 365. Pour chaque classe d’unités d’une application de finances et d’opérations, un groupe d’unités est créé dans une application Dynamics 365, qui contient les unités appartenant à la classe d’unités. Une unité de base par défaut est également créée pour chaque groupe d’unité.

Applications de finances et d’opérations | Applications Customer Engagement |
---|---
[Conversions d’unités spécifiques à un produit](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Unités](mapping-reference.md#219) | UM
[Conversion d’unités](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Synchronisation initiale de la mise en correspondance des données des unités entre les applications de finances et d’opérations et Dataverse

### <a name="initial-synchronization-of-units"></a>Synchronisation initiale des unités

Lorsque la double écriture est activée, les unités de finances et d’opérations sont synchronisées vers les autres applications Dynamics 365. Les groupes d’unités synchronisés depuis les applications de finances et d’opérations dans Dataverse ont un indicateur défini sur « Géré en externe ».

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Mise en correspondance des unités et des données des groupes/classes d’unités depuis les applications de finances et d’opérations et d’autres applications Dynamics 365

Premièrement, il est important de noter que la clé d’intégration de l’unité est msdyn_symbol. Par conséquent, cette valeur doit être unique dans Dataverse ou d’autres applications Dynamics 365. Parce que dans les autres applications Dynamics 365 c’est la paire « ID de groupe d’unités » et « Nom » qui définissent le côté unique d’une unité, vous devez tenir compte de différents scénarios pour mettre en correspondance les données entre les applications de finances et d’opérations et Dataverse.

Pour que les unités se mettent en correspondance/se chevauchent dans les applications de finances et d’opérations et d’autres applications Dynamics 365 :

+ **L’unité appartient à un groupe d’unités dans les autres applications Dynamics 365 qui correspond à la classe d’unités associée dans les applications de finances et d’opérations**. Dans ce cas, la colonne msdyn_symbol des autres applications Dynamics 365 doit être renseigné avec le symbole d’unité des applications de finances et d’opérations. Par conséquent, lorsque les données seront mises en correspondance, et lorsque le groupe d’unités sera défini comme « Géré en externe » dans d’autres applications Dynamics 365.
+ **L’unité appartient à un groupe d’unités dans d’autres applications Dynamics 365 qui ne correspond pas à la classe d’unités associée dans les applications de finances et d’opérations (aucune classe d’unités existante dans les applications de finances et d’opérations pour la classe d’unités dans d’autres applications Dynamics 365).** Dans ce cas, le msdyn_symbol doit être renseigné avec une chaîne aléatoire. Notez que cette valeur doit être unique dans d’autres applications Dynamics 365.

Pour les unités et les classes d’unités dans les applications de finances et d’opérations n’existant pas dans d’autres applications Dynamics 365 :

Dans le cadre de la double écriture, des groupes d’unités des applications de finances et d’opérations et leurs unités correspondantes sont créés et synchronisés dans d’autres applications Dynamics 365 et Dataverse et le groupe d’unités sera défini comme « Géré en externe ». Aucun effort supplémentaire au démarrage n’est requis.

Pour les unités dans les autres applications Dynamics 365 qui n’existent pas dans les applications de finances et d’opérations :

La colonne msdyn_symbol doit être remplie pour toutes les unités. Les unités peuvent toujours être créées dans les applications de finances et d’opérations dans la classe d’unités correspondante (si elle existe). Si la classe d’unités n’existe pas, d’abord la classe d’unités doit être créée (notez que vous ne pouvez pas créer une classe d’unités dans des applications de finances et d’opérations, hormis via l’extension si vous étendez l’énumération) et correspondre à l’autre groupe d’unités des applications Dynamics 365. Vous pouvez ensuite créer la nouvelle unité. Notez que le symbole d’unité dans les applications de finances et d’opérations doit être le champ msdyn_symbol précédemment renseigné dans d’autres applications Dynamics 365 pour l’unité.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Stratégies de produit : groupes de dimensions, de suivi et de stockage

Les stratégies de produit désignent des ensembles de stratégies utilisées pour définir des produits et leurs caractéristiques dans le stock. Le groupe de dimensions de produit, le groupe de dimensions de suivi de produit et le groupe de dimensions de stockage peuvent se présenter comme stratégies de produit.

Applications de finances et d’opérations | Applications Customer Engagement |
---|---
[Groupes de dimensions de produit](mapping-reference.md#173) | msdyn\_productdimensiongroups |
[Groupes de dimension de stockage](mapping-reference.md#177) | msdyn_productstoragedimensiongroups |
[Groupes de dimension de suivi](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups |

## <a name="product-hierarchies"></a>Hiérarchies de produit

Applications de finances et d’opérations | Applications Customer Engagement |
---|---
[Affectations de catégorie de produit](mapping-reference.md#167) | msdyn_productcategoryassignments |
[Hiérarchie de catégories de produit](mapping-reference.md#168) | msdyn_productcategoryhierarchies |
[Rôles de hiérarchie de catégories de produit](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles |

## <a name="integration-key-for-products"></a>Clé d’intégration pour les produits

Pour identifier de manière unique les produits entre Dynamics 365 Finance et les produits dans Dataverse, les clés d’intégration sont utilisées.
Pour les produits, le **(numérodeproduit)** est la clé unique qui identifie un produit dans Dataverse. Il est composé par la concaténation de : **(société, msdyn_productnumber)**. Le champ **société** indique l’entité juridique dans les applications de finances et d’opérations et **msdyn_productnumber** indique le numéro de produit pour le produit spécifique dans les applications de finances et d’opérations.

Pour les utilisateurs d’autres applications Dynamics 365, le produit est reconnu dans l’interface utilisateur avec le champ **msdyn_productnumber** (notez que le libellé de la colonne est **Numéro de produit**). Dans l’écran de produit les champs de société et de msydn_productnumber sont affichés. Toutefois, la colonne (numérodeproduit), la clé unique pour un produit, n’apparaît pas.

Si vous créez des applications sur Dataverse, vous devez veiller à utiliser le **numéro de produit** (l’ID de produit unique) comme clé d’intégration. N’utilisez pas **msdyn_productnumber**, car il n’est pas unique.

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Synchronisation initiale des produits et migration des données de Dataverse vers les applications de finances et d’opérations.

### <a name="initial-synchronization-of-products"></a>Synchronisation initiale des produits

Lorsque la double écriture est activée, les produits des applications de finances et d’opérations sont synchronisés avec Dataverse et les applications Customer Engagement. Les produits créés dans Dataverse et toute autre application Dynamics 365 avant la double écriture, ne seront pas mis à jour ou mis en correspondance avec les données de produit provenant des applications de finances et d’opérations.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Mise en correspondance des données de produit provenant des applications de finances et d’opérations et d’autres applications Dynamics 365

Si les mêmes produits sont conservés (se chevauchant/mis en correspondance) dans les applications de finances et d’opérations et dans Dataverse et toute autre application Dynamics 365, lors de l’application de la double écriture, la synchronisation des produits de finances et d’opérations aura lieu, et des doublons de ligne apparaîtront dans Dataverse pour le même produit.
Pour éviter la situation précédente, si d’autres applications Dynamics 365 ont des produits se chevauchent/sont mis en correspondance avec les applications de finances et d’opérations, l’administrateur activant la double écriture doit amorcer les colonnes **Société** (exemple : « USMF ») et **msdyn_productnumber** (exemple : « 1234:Black:S ») avant la synchronisation des produits. En d’autres termes, ces deux colonnes du produit dans Dataverse doivent être renseignés avec la société concernée dans les applications de finances et d’opérations avec laquelle le produit doit être mis en correspondance et avec son numéro de produit.

Puis, lorsque la synchronisation est activée et survient, les produits de finances et d’opérations seront synchronisés avec les produits associés dans Dataverse et toute autre application Dynamics 365. Ce champ s’applique aux produits distincts et des variantes de produit.

### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migration des données de produit provenant d’autres applications Dynamics 365 vers les applications de finances et d’opérations

Si d’autres applications Dynamics 365 ont des produits qui ne sont pas présents dans les applications de finances et d’opérations, l’administrateur peut d’abord utiliser **EcoResReleasedProductCreationV2Entity** pour importer ces produits dans les applications de finances et d’opérations. Et deuxièmement, pour mettre en correspondance les données du produit de finances et d’opérations et d’autres applications Dynamics 365, comme décrit ci-dessus.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

