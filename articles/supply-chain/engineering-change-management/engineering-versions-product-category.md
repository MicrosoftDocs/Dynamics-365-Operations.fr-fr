---
title: Versions d'ingénierie et catégories de produits d'ingénierie
description: Cette rubrique fournit des informations sur le concept des versions d'ingénierie. Les versions d'ingénierie garantissent que les différents états d'un produit et de ses données sont tenus à jour et clairs, et qu'ils peuvent être visualisés dans le système.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgLookupDynastring, EngChgProductVersionNumberRule, EngChgEcmProductRoute, EngChgEcmRequestProducts, EngChgEcmProductRoute, EngChgEcmProductPreview,EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmProductCreate, EngChgEcmProductLookup, EngChgProductVersionPrCompany, ngChgProductTypeLookup, EngChgProductType, EngChgProductItemPart, EngChgProductItem, EngChgEcmCategory, EngChgEcmBomDesignerEditBom, EngChgEcmBomDesigner, EngChgEcmBOMCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: c15dcd0adfcf9b9022a919bd516dcf5117ea5041
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987477"
---
# <a name="engineering-versions-and-engineering-product-categories"></a>Versions d'ingénierie et catégories de produits d'ingénierie

[!include [banner](../includes/banner.md)]

Les produits d'ingénierie évoluent au cours de leur cycle de vie, pour de nombreuses raisons. Par exemple, des changements peuvent être introduits pour améliorer la facilité de maintenance du produit, changer un composant parce que le fournisseur ne le propose plus, répondre à de nouvelles informations ou corriger des erreurs dans la conception initiale. Il existe également de nombreuses raisons pour lesquelles ces modifications doivent être stockées dans le cadre d'un produit en cours, de manière à ce que les données précédentes ne soient pas écrasées. Voici quelques unes de ces raisons :

- Vous souhaitez garder une trace du produit tel qu'il a été fabriqué et livré à vos clients dans les états de cycle de vie précédents.
- Vous avez besoin d'un délai avant d'approuver et d'appliquer les modifications.
- Vous voulez avoir un horodatage pour chaque changement et vous voulez être en mesure de livrer les produits précédemment fabriqués séparément les uns des autres.

Les *versions d'ingénierie* garantissent que les différents états d'un produit et de ses données sont tenus à jour et clairs, et qu'ils peuvent être visualisés dans le système. Ce concept vous aide à maintenir la cohérence, à verrouiller la nomenclature pour la production, à éliminer la variabilité et à identifier facilement les modifications.

Généralement, la règle *format-ajustement-fonction* est appliquée pour déterminer si une modification nécessite un nouveau produit, une nouvelle version ou une mise à jour d'une version existante. Chacun des trois termes du nom de cette règle fait référence à un aspect spécifique d'une pièce, ce qui aide les ingénieurs à faire correspondre les pièces aux besoins. La règle format-ajustement-fonction augmente la flexibilité des modifications de conception, car une documentation et un coût de conception minimaux sont nécessaires pour modifier une pièce, à condition que l'ajustement, le format et la fonction du produit soient conservés.

- **Ajustement** fait référence à la capacité de la pièce ou de la fonction à se connecter, à s'accoupler ou à joindre une autre fonction ou pièce dans un assemblage. L'ajustement permet à la pièce de respecter les tolérances d'assemblage requises afin qu'elle puisse être utile.
- **Format** fait référence aux caractéristiques d'une pièce ou d'un assemblage, telles que les dimensions externes, le poids, la taille et l'aspect visuel. Le format est l'aspect le plus affecté par les choix esthétiques d'un ingénieur. Il comprend le boîtier, le châssis et le panneau de commande, qui deviennent la « face » extérieure du produit.
- **Fonction** est un critère qui est satisfait lorsque la pièce remplit efficacement et de manière fiable son objectif déclaré. Par exemple, dans un produit électronique, la fonction peut dépendre des composants à semi-conducteurs qui sont utilisés et du logiciel ou du micrologiciel. Souvent, cela peut également dépendre des caractéristiques du boîtier sélectionné. Deux des raisons les plus courantes pour lesquelles un boîtier peut échouer au critère de fonction sont les ports mal placés ou de taille médiocre, et l'étiquetage trompeur ou manquant. 

## <a name="engineering-versions"></a>Versions d’ingénierie

Lorsque vous utilisez des produits d'ingénierie, chaque produit a au moins une version d'ingénierie. La version d'ingénierie initiale est automatiquement créée lorsque vous créez un produit d'ingénierie. Chaque version d'ingénierie stocke les données d'ingénierie spécifiques à cette version. Voici quelques exemples de ces données :

- Le numéro de version et le numéro de version précédente (le cas échéant)
- Les dates de début et de fin
- Le statut actif de la version du produit, qui indique si la version peut être validée et utilisée dans les transactions (pour plus d'informations, voir [Disponibilité du produit](product-readiness.md) .)
- La société d'ingénierie qui a créé et possède le produit (pour plus d'informations, voir [Sociétés d'ingénierie et règles de propriété des données](engineering-org-data-ownership-rules.md) .)
- Documents d'ingénierie connexes, tels qu'un manuel d'assemblage, des instructions d'utilisation, des images et des liens
- Les attributs d'ingénierie (pour plus d'informations, voir [Attributs d'ingénierie et recherche d'attributs d'ingénierie](engineering-attributes-and-search.md).)
- Les nomenclatures d'ingénierie
- Les gammes d'ingénierie

Vous pouvez mettre à jour ces données sur une version existante, ou créer une version, en utilisant un *ordre de modification technique*. (Pour plus d'informations, consultez [Gérer les modifications apportées aux produits d'ingénierie](engineering-change-management.md).) Si vous créez une version d'un produit, le système copie toutes les données importantes pour l'ingénierie dans cette nouvelle version. Vous pouvez ensuite modifier les données de cette nouvelle version. De cette manière, vous pouvez suivre des données spécifiques pour chaque version consécutive. Pour comparer les différences entre les versions d'ingénierie consécutives, inspectez l'ordre de modification technique, qui inclut les types de modification qui indiquent toutes les modifications.

Comme indiqué, la version d'ingénierie initiale est automatiquement créée lorsque vous créez un produit d'ingénierie. Le numéro de version de cette version suit la règle de numéro de version définie dans la catégorie d'ingénierie du produit. Pour passer à une version ultérieure, vous devez ajouter le produit à un ordre de modification technique en tant que ligne et vous devez définir le champ **Impact** sur *Nouvelle version*. L'ordre des modifications techniques comprendra les détails du changement de la version actuelle à la version suivante.

Notez qu'un produit d'ingénierie ne peut figurer que dans un seul ordre de modification technique à la fois. Cette restriction garantit l'exactitude des données et permet d'éviter les chevauchements ou les changements contradictoires dans le produit. Notez également que le champ **Ingénieur** dans la vue **En-tête** de l'ordre de modification d'ingénierie indique l'ingénieur responsable de l'ordre de modification. Si l'ingénieur appartient à une équipe définie dans le système, le champ **Responsable** montre le chef de cette équipe.

## <a name="track-versions-in-transactions"></a>Suivre les versions dans les transactions

Lorsque vous utilisez la gestion des modifications techniques, vos données de base produit incluent toujours une ou plusieurs versions d'ingénierie. Dans votre configuration de produits d'ingénierie, vous pouvez choisir si la version d'ingénierie fait également partie de *transactions logistiques*. (Pour plus d'informations, consultez la section [Configurer des catégories de produits d'ingénierie](#product-category) plus loin dans cette rubrique.) Si l'impact logistique est pertinent, il diffère par produit et par entreprise. Parfois, seule la dernière version d'un produit est utilisée. Par conséquent, lorsque vous introduisez une nouvelle version, la version précédente ne peut plus être utilisée. Dans d'autres cas, la version précédente est requise dans les transactions logistiques pour surmonter les défis suivants :

- Le service Logistique doit expédier deux pièces d'un produit à un client. Dans ce cas, vous devez décider si vous souhaitez ou autorisez l'envoi de deux versions différentes.
- On découvre plus tard qu'un problème survient et qu'il est lié à un changement spécifique. Dans ce cas, il peut être utile de déterminer exactement quelle version a été expédiée dans chaque commande.
- Les entreprises souhaitent généralement expédier les anciennes versions en premier, pour les éliminer progressivement du stock. Surtout pour les produits à faible volume, cette approche peut souvent être gérée en déterminant les dates de validité de la nouvelle version par rapport aux prédictions sur le moment où le stock de l'ancienne version sera épuisé. Cependant, parfois, vous ne pourrez peut-être pas faire cette comparaison, ou vous pouvez considérer l'incertitude des prévisions de niveau de stock comme trop élevée.

La décision de rendre les versions visibles dans l'inventaire dépend de facteurs tels que ceux mentionnés précédemment, ainsi que des pratiques de l'entreprise et d'autres considérations propres à chaque entreprise. Vous pouvez spécifier le comportement de la *catégorie de produit d'ingénierie*. Il s'appliquera ensuite à tous les produits créés à partir de cette catégorie, pour toutes les entreprises dans lesquelles le produit est lancé.

Pour les produits configurés de manière à avoir un impact logistique, la version d'ingénierie doit être spécifiée sur chaque transaction. Bien que le système proposera la *dernière version active*, vous pouvez sélectionner parmi toutes les versions actives disponibles pour l'entreprise. Pour les produits configurés de manière à ne pas avoir d'impact logistique, la version d'ingénierie n'est pas spécifiée sur chaque transaction. Cependant, le système utilise la dernière version active. Par exemple, lorsque vous ajoutez un produit à une nomenclature de production, la dernière version est utilisée et lorsque vous exécutez la planification principale, la dernière version est utilisée.

## <a name="set-up-engineering-product-categories"></a><a name="product-category"></a>Configurer des catégories de produits d'ingénierie

Une catégorie de produits d'ingénierie fournit une base pour créer un produit d'ingénierie spécifique. Chaque catégorie établit un ensemble de valeurs et de stratégies par défaut. Par conséquent, lorsque vous créez un produit d'ingénierie, vous sélectionnez d'abord la catégorie à partir de laquelle le créer.

Notez qu'un nouveau type de hiérarchie de catégories (*hiérarchie des produits d'ingénierie*) est automatiquement configuré pour vous. Vous pouvez créer manuellement les catégories en accédant à **Gestion du changement d'ingénierie \> Configurer \> Détails de la catégorie de produits d'ingénierie**.

Chaque catégorie de produit d'ingénierie établit le comportement par défaut des produits d'ingénierie créés en fonction de cette catégorie. Une fois que vous avez créé un produit d'ingénierie, vous ne pouvez pas modifier sa catégorie de produit d'ingénierie. Toutefois, si vous sélectionnez la catégorie incorrecte, vous pouvez supprimer le produit, puis le recréer.

Lorsqu'une catégorie de produit d'ingénierie est créée, vous ne pouvez pas modifier les paramètres suivants :

- Société d'ingénierie
- Type de produit
- Sous-type de produit
- Groupe de dimensions de produit
- Technologie de configuration
- Règle de numérotation de version

D'autres paramètres peuvent hériter des valeurs par défaut définies pour la catégorie de produit d'ingénierie. Cependant, selon les règles du système, ces valeurs peuvent être modifiées.

Pour utiliser des catégories de produits d'ingénierie, accédez à **Gestion du changement d'ingénierie \> Configurer \> Détails de la catégorie de produits d'ingénierie**. Suivez ensuite l’une des procédures suivantes.

- Pour créer une catégorie, sélectionnez **Nouveau** dans le volet Actions, puis définissez les champs comme décrit dans les sous-sections suivantes.
- Pour modifier une catégorie existante, sélectionnez-la dans le volet de liste, sélectionnez **Modifier** dans le volet Actions, puis définissez les champs comme décrit dans les sous-sections suivantes.
- Pour supprimer une catégorie existante, sélectionnez-la dans le volet de liste, puis sélectionnez **Supprimer** sur le volet Actions.

### <a name="header"></a>En-tête

Définissez les champs suivants sur l'en-tête d'une catégorie de produit d'ingénierie.

| Champ | Description |
|---|---|
| Nom | Permet d'entrer un nom pour la catégorie de produit d'ingénierie. |
| Société d'ingénierie | Sélectionnez la société d'ingénierie où les produits de cette catégorie de produits d'ingénierie peuvent être créés et où ils seront maintenus. |

### <a name="details-fasttab"></a>Raccourci Détails

Définissez les champs suivants sur le raccourci **Détails** d'une catégorie de produit d'ingénierie.

| Champ | Description |
|---|---|
| Type de produit | Sélectionnez si la catégorie s'applique aux produits ou services. |
| Suivre les versions dans les transactions | Sélectionnez si la version du produit doit être estampillée sur toutes les transactions (impact logistique). Par exemple, si vous suivez la version dans les transactions, chaque commande client indiquera quelle version spécifique du produit a été vendue dans cette commande client. Si vous ne suivez pas la version dans les transactions, les commandes client n'indiqueront pas quelle version spécifique a été vendue. Au lieu de cela, ils affichent toujours la dernière version.<ul><li>Si cette option est définie sur *Oui*, une fiche produit est créée pour le produit et chaque version du produit sera une variante qui utilise la dimension de produit *version*. Le champ **Sous-type de produit** est automatiquement défini sur *Produit générique* et vous devez sélectionner un groupe de dimensions de produit dans lequel la dimension *version* est active. Seuls les groupes de dimensions de produit où la *version* est une dimension active seront affichés. Vous pouvez créer des groupes de dimensions de produit en sélectionnant le bouton **Modifier** (symbole de crayon).</li><li>Si cette option est définie sur *Non*, la dimension du produit *version* ne sera pas utilisée. Vous pouvez ensuite choisir de créer un produit ou un produit générique utilisant les autres dimensions.</li></ul><p>Cette option est souvent utilisée pour les produits qui présentent une différence de coût entre les versions ou les produits pour lesquels des conditions différentes s'appliquent par rapport au client. Par conséquent, il est important d'indiquer quelle version a été utilisée dans chaque transaction.</p> |
| Sous-type de produit | Sélectionnez si la catégorie contiendra des produits ou des produits génériques. Pour les produits génériques, les dimensions du produit seront utilisées.
| Groupe de dimensions de produit | Le paramètre **Suivre les versions dans les transactions** vous aide à sélectionner le sous-type de produit. Si vous avez indiqué que vous souhaitez suivre la version dans les transactions, les groupes de dimensions de produit où la dimension de la *version* utilisée sera affichée. Sinon, seuls les groupes de dimensions de produit où la dimension de *version* n'est pas utilisée seront affichés. |
| État du cycle de vie du produit à la création | Configurez l'état du cycle de vie du produit par défaut qu'un produit d'ingénierie doit avoir lors de sa création. Pour plus d'informations, voir [États du cycle de vie du produit et transactions](product-lifecycle-state-transactions.md). |
| Règle de numérotation de version | Sélectionnez la règle du numéro de version qui s'applique à la catégorie :<ul><li>**Manuel** – Vous choisissez le numéro de version pour chaque nouvelle version.</li><li>**Automatique** – Le système définit le numéro de version en fonction d'un format que vous définissez. Lorsque vous configurez le format, utilisez le dièse (\#) pour représenter un chiffre et tout autre caractère pour représenter une valeur constante. Par exemple, si vous définissez le format comme *V-\#\#*, la première version sera « V-01 », la deuxième version sera « V-02 », et ainsi de suite.</li><li>**Liste** – Le système prend le numéro suivant dans une liste prédéfinie de valeurs personnalisées que vous définissez.</li></ul> |
| Appliquer l’application | Sélectionnez si les dates de validité des versions d'ingénierie doivent être consécutives ou s'il peut y avoir des écarts et des chevauchements. Ce paramètre affecte la manière dont vous pouvez utiliser les champs **Date de début** et **Date de fin** pour chaque version d'ingénierie où la catégorie s'applique.<ul><li>Si cette option est définie sur *Oui*, une valeur **Date de début** doit être spécifiée pour chaque version, et ni les chevauchements ni les écarts ne sont autorisés entre les versions. La plage de dates pour chaque version d'ingénierie est directement connectée aux versions d'ingénierie précédente et suivante, si elles existent. Dans ce scénario, la version la plus récente est toujours utilisée et les anciennes versions ne sont plus utilisées.</li><li>Si cette option est définie sur **Non**, il n'y a aucune restriction sur les champs de date de validité pour les versions d'ingénierie, et les chevauchements et les écarts sont autorisés. Dans ce scénario, plusieurs versions peuvent être actives en même temps et vous pouvez travailler avec n'importe quelle version active.</li></ul><p>Cette option affecte également les nomenclatures et les gammes connectées à une version de produit. Pour plus d'informations, voir la section [Connecter les nomenclatures et les gammes aux versions d'ingénierie](#boms-routes) plus loin dans cette rubrique.</p> |
| Utiliser la nomenclature de la règle de nombre | Définissez cette option sur *Oui* pour activer les règles de définition d'un numéro de produit à l'aide de séquences de numéros, de noms et de valeurs d'attributs d'ingénierie et de constantes de texte comme segments. Pour créer ou modifier des règles, sélectionnez le bouton **Modifier**. |
| Utiliser la nomenclature de la règle de nom | Définissez cette option sur *Oui* pour activer les règles de définition d'un nom à l'aide des noms d'attributs d'ingénierie, de valeurs d'attributs d'ingénierie et de constantes de texte comme segments. Pour créer ou modifier des règles, sélectionnez le bouton **Modifier**. |
| Utiliser la nomenclature de la règle de description | Définissez cette option sur *Oui* pour activer les règles de définition d'une description à l'aide des noms d'attributs d'ingénierie, de valeurs d'attributs d'ingénierie et de constantes de texte comme segments. Pour créer ou modifier des règles, sélectionnez le bouton **Modifier**. |

### <a name="attributes-fasttab"></a>Raccourci Attributs

Utilisez la grille sur le raccourci **Attributs** pour configurer les attributs d'ingénierie qui s'appliquent aux produits appartenant à cette catégorie. Pour plus d'informations sur la création des attributs d'ingénierie, voir [Attributs d'ingénierie et recherche d'attributs d'ingénierie](engineering-attributes-and-search.md).

Utilisez les boutons du raccourci **Attributs** pour ajouter, supprimer et organiser des attributs dans la grille.

Si vous modifiez la sélection d'attributs pour une catégorie d'ingénierie et qu'il existe déjà des produits basés sur cette catégorie, vous devez décider d'appliquer ou non vos modifications à ces produits. Si vous souhaitez que les produits existants reflètent les modifications, sélectionnez **Mettre à jour les produits existants** sur le raccourci **Attributs**.

Pour chaque ligne que vous ajoutez à la grille, définissez les champs suivants.

| Champ | Description |
|---|---|
| Nom | Sélectionnez l'attribut à ajouter. |
| Valeur | Sélectionnez la valeur par défaut pour l'attribut. |
| Obligatoire | Pour les attributs du type *Booléen*, si cette option est définie sur *Oui*, les utilisateurs doivent définir l'attribut sur *Oui*. Si cette option est définie sur *Non*, les utilisateurs peuvent définir l'attribut sur *Oui* ou *Non*. Pour les autres types de données, le paramètre de cette option est simplement informatif. |
| Attribut de traitement par lots | Sélectionnez si l'attribut doit être propagé via la fonctionnalité de traitement par lots. |

### <a name="readiness-policy-fasttab"></a>Raccourci de stratégie de disponibilité

Utilisez le champ **Stratégie de disponibilité du produit** pour sélectionner la stratégie de disponibilité qui s'applique aux produits appartenant à cette catégorie. Pour plus d’informations, voir [Disponibilité du produit](product-readiness.md).

### <a name="release-policy-fasttab"></a>Raccourci de stratégie de lancement

Utilisez le champ **Stratégie de lancement du produit** pour sélectionner la stratégie de lancement qui s'applique aux produits appartenant à cette catégorie. Pour plus d'informations, voir [Lancement de structures de produit](release-product-structure.md).

## <a name="connect-boms-and-routes-to-engineering-versions"></a><a name="boms-routes"></a>Connectez les nomenclatures et les gammes aux versions d'ingénierie

Le paramètre de l'option **Appliquer la prise d’effet** est importante pour la connexion des nomenclatures et des gammes à chaque version d'ingénierie. Vous pouvez activer plusieurs nomenclatures ou gammes par produit uniquement s'il existe une différence dans l'un des paramètres suivants :

- Dimension de produit
- Quantité
- Site
- Dates de prise d’effet

Les nomenclatures et les gammes d'ingénierie sont créés à partir de la version d'ingénierie à laquelle ils s'appliquent. Ils peuvent être reconnus par la coche dans la case **Contrôle technique**. Lorsque vous travaillez avec des nomenclatures et des gammes d'ingénierie, vous ne les concevez généralement pas en utilisant des quantités différentes. De plus, vous ne concevez généralement pas différentes nomenclatures par site. De plus, pour les nomenclatures d'ingénierie et les gammes, les dates de validité sont toujours tirées de la version d'ingénierie. Par conséquent, une version d'ingénierie, sa nomenclature et sa gamme auront tous les mêmes dates de validité.

Pour les produits sur lesquels vous utilisez la dimension de produit *version* (avec l'impact logistique sur les transactions), la version est également ajoutée aux nomenclatures et aux gammes. Ce comportement permet de différencier les nomenclatures et les gammes des versions consécutives, quel que soit le paramètre **Applique la prise d'effet**.

Pour les produits sur lesquels vous n'utilisez pas la dimension de produit *version* (sans l'impact logistique sur les transactions), la version n'est pas ajoutée aux nomenclatures ou aux gammes. Par conséquent, il n'y aura aucune différence entre les nomenclatures et les gammes des versions consécutives. Dans ce cas, nous vous recommandons vivement de définir l'option **Appliquer la prise d'effet** sur *Oui*. De cette manière, vous évitez le chevauchement des versions d'ingénierie et vous pouvez également activer la nomenclature et la gamme d'une version plus récente sans avoir à désactiver au préalable la nomenclature et la gamme de la version précédente. Si vous définissez l'option **Appliquer la prise d'effet** sur *Oui* dans ce cas, vous devez désactiver manuellement les nomenclatures et les gammes des anciennes versions avant de pouvoir activer la dernière version.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]