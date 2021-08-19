---
title: Dimensions de produit
description: 'Il existe cinq dimensions de produit : Couleur, Configuration, Taille, Style et Version. Vous combinez des dimensions de produit dans les groupes de dimensions et vous affectez des groupes de dimensions aux produits génériques. Les combinaisons de dimensions de produit déterminent la manière dont les variantes de produit sont définies.'
author: t-benebo
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle, EcoResVersionNameLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 680d5ed929a396bfb2d3c7f05351ab6c93d29256c825c618cb166aac444aa5d6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726895"
---
# <a name="product-dimensions"></a>Dimensions de produit

[!include [banner](../includes/banner.md)]

Il existe cinq dimensions de produit : Couleur, Configuration, Taille, Style et Version. Vous combinez des dimensions de produit dans les groupes de dimensions et vous affectez des groupes de dimensions aux produits génériques. Les combinaisons de dimensions de produit déterminent la manière dont les variantes de produit sont définies.

Les dimensions de produit sont des caractéristiques qui permettent d’identifier une variante de produit. Vous pouvez utiliser des combinaisons de dimensions de produit pour définir des variantes de produit. Vous devez définir au moins une dimension de produit pour un produit générique pour créer une variante de produit.

## <a name="product-variants"></a>Variantes de produit

Les variantes de produit sont également appelées des articles. Un article est un produit corporel, ce qui n’est pas le même qu’un service. Il est également possible de définir un produit générique de type de service. En utilisant le type de service, vous pouvez spécifier des variantes de produit qui incluent les services. Par exemple, vous pouvez spécifier un produit générique pour le travail de conseil et des variantes de produit pour le travail qui est effectué par les consultants supérieurs et les consultants juniors.

## <a name="product-dimensions"></a>Dimensions de produit

Une variante de produit peut être générée selon les valeurs de dimension de produit.

Les valeurs de dimension de produit pour les dimensions de taille, de couleur et de style peuvent être créées aux emplacements suivants :

- La page **Taille** (**Gestion des informations produit \> Installer \> Groupes de dimensions et de variantes \> Tailles**)
- La page **Couleur** (**Gestion des informations produit \> Installer \> Groupes de dimensions et de variantes \> Couleurs**)
- La page **Style** (**Gestion des informations produit \> Installer \> Groupes de dimensions et de variantes \> Styles**)

Les valeurs de dimension de produit pour la dimension de configuration sont généralement créées à l’aide du configurateur de produits ou du configurateur basé sur les dimensions. 

Les versions de produit sont généralement créées pour des versions spécifiques à mesure que le produit évolue au cours de son cycle de vie. Les versions de produit sont couvertes en détail plus loin dans cette rubrique.

Les dimensions de produit peuvent également être créées et tenues à jour dans la page **Dimensions de produit**, qui est accessible depuis les emplacements suivants :

- Allez dans **Gestion des informations sur les produits \> Produits \> Produits génériques**. Dans le volet Actions, sélectionnez **Dimensions de produit**.
- Accédez à **Gestion des informations sur les produits \> Produits \> Tous les produits et produits génériques**. Sélectionnez un produit générique. Dans le volet Actions, sélectionnez **Dimensions de produit**.
- Accédez à **Gestion des informations sur les produits \> Produits lancés**. Sélectionnez un produit générique. Sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Produit générique**, cliquez sur **Dimensions de produit**.

Le nombre de variantes que vous pouvez créer pour un article est limité par le nombre de combinaisons possibles de dimension de produit.

> [!TIP]
> Lorsque vous utilisez un produit sur une ligne de commande, par exemple, vous sélectionnez les dimensions de produit pour identifier la variante de produit avec laquelle vous souhaitez travailler.

## <a name="example"></a>Exemple

Une entreprise vend des jeans. Les articles, des *jeans*, utilisent les dimensions de produit de couleur et de taille. Ils sont vendus en trois couleurs et en six tailles différentes. Les couleurs sont le bleu, le noir et le marron. Les tailles sont XS, S, M, L, XL et XXL. Toutes les tailles ne sont pas disponibles dans les trois couleurs. Si toutes les combinaisons étaient disponibles, il y aurait 18 types différents de jeans. Toutefois, dans cet exemple, seules les neuf combinaisons de variantes de produit suivantes sont produites.

| Couleur | Taille |
|-------|------|
| Bleu  | XS   |
| Bleu  | Sa    |
| Bleu  | F    |
| Noir | F    |
| Noir | L    |
| Noir | XL   |
| Brun | L    |
| Brun | XL   |
| Brun | XXL  |

## <a name="the-version-product-dimension"></a>La dimension du produit de la version

La version est une dimension de produit destinée à vous aider à maintenir et à suivre plusieurs versions d’un produit tout au long de la chaîne d’approvisionnement. Le suivi des versions est essentiel au succès des fabricants qui opèrent dans un monde où les cycles de vie des produits diminuent constamment, les exigences de qualité et de fiabilité accrues et l’accent accru sur la sécurité des produits.

En tant que dimension de produit standard, la version se comportera de la même manière que les dimensions du produit existantes (taille, style, couleur et configuration). Par conséquent, vous pouvez l’utiliser à d’autres fins que le suivi des versions de produit.

### <a name="turn-on-the-version-dimension"></a><a name="enable-version-dim"></a>Activer la dimension de la version

#### <a name="before-you-turn-on-the-version-dimension"></a>Avant d’activer la dimension de la version

Lorsque vous activez la dimension de version, certaines fonctionnalités peuvent être interrompues ou cesser de fonctionner comme prévu si vous avez installé d’autres solutions qui ajoutent des personnalisations aux dimensions d’inventaire. Pour que la dimension de version soit entièrement fonctionnelle, vous devrez peut-être mettre à jour ces solutions afin qu’elles incluent la dimension de version dans leurs références aux dimensions de stock.

Lorsque vous testez la compatibilité de vos solutions avec la dimension de version, recherchez les éléments suivants :

1. **Fonctionnalité :** Plus important encore, toutes les personnalisations qui impliquent les dimensions de stock doivent être évaluées pour garantir qu’elles peuvent fonctionner conjointement avec la dimension de version.
1. **Références aux dimensions de l’inventaire :** Recherchez les références aux dimensions de l’inventaire (c’est-à-dire aux endroits où les dimensions sont explicitement référencées). Les références à `InventDimId` devraient être prêtes à l’emploi, mais recherchez des références au style ou à la couleur. Par exemple, assurez-vous de vérifier les éléments suivants :

    - Appels d’API dans les classes étendues
    - Toutes les références à des dimensions de stock spécifiques dans le code d’extension (ce code doit faire flotter la dimension de version avec les dimensions de style, de couleur et de taille.)

1. **Références aux appels d’API obsolètes :** Dans son introduction de la dimension de version, Microsoft a tenté de rendre obsolètes le moins d’API possible. Les quelques API rendues obsolètes émettent un avertissement lorsque vous activez la clé de configuration **Dimension du produit – version**. Les appels à ces API doivent être corrigés dans vos solutions étendues avant d’activer la dimension de version dans un système de production. Voici les API obsolètes spécifiques à la version :

    - RetailTransactionServiceInventory::getProductRecordId
    - EcoResProductNumberIdentifiedProductVariantEntity::find
    - EGAISAlcoholProduction_RU::findByItemDim
    - PCVariantConfiguration::findByProductMasterAndDimensions

1. **Plans :** Si des cartes utilisent les dimensions de stock, la mise en correspondance de relations correspondant à ces cartes doit être mis à jour afin qu’elles incluent la dimension de version. Dans le modèle étendu ou les extensions de table, recherchez les tables où les champs incluent des dimensions de stock.
1. **Fonctionnalité Microsoft Dynamics 365 Commerce :** Une fois activée, la dimension de version apparaîtra tout au long du code spécifique à Commerce dans Dynamics 365 Supply Chain Management. Cependant, la dimension de version n’est pas encore prise en charge par la base de données du canal Commerce ou dans les applications de point de vente (PDV) ou de e-commerce. Ces applications spécifiques au commerce ne prendront pas en charge les ventes/expéditions aux utilisateurs ou les retours/réceptions de stock par dimension de version. Les fonctions de recherche de disponibilité du stock ne détecteront pas le stock par dimension de version dans les applications Commerce. Ce comportement ressemble au comportement actuel de la dimension de configuration dans Commerce.

#### <a name="turn-on-the-version-dimension"></a>Activer la dimension de la version

Avant de pouvoir utiliser la dimension de version, vous devez l’activer sur votre système. Cette tâche nécessite des autorisations d’administrateur.

1. Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
1. Activez la fonctionnalité nommée *Version de dimension du produit*. (Pour plus d’informations, voir [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Mettez votre système en [Mode de Maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accédez à **Administration système \> Paramétrage \> Configuration des licences**.
1. Sur l’onglet **Clés de configuration**, développer **Commerce** et cochez la case **Dimension du produit – version**.
1. Désactivez le [Mode de Maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="areas-where-the-version-dimension-isnt-supported"></a>Zones dans lesquelles la dimension de version n’est pas prise en charge

Les zones suivantes ne prennent pas en charge la dimension de version (vous pouvez toujours utiliser ces zones, mais vous ne pourrez pas y ajouter des produits avec version (produits dans lesquels la dimension de version est utilisée)). Par exemple, vous ne pouvez pas ajouter un article avec version à un catalogue fournisseur. L’ajout de produits avec la dimension de version à ces zones provoquerait des changements importants.

- Relevé mensuel de l’objet de coût
- Cache du relevé des objets de coût
- Statistiques de ventes MCR par article
- Catalogues fournisseur
- EcoResProductDimensionGroupEntity

En outre, les fonctionnalités de création de commande et de traitement des commandes dans Commerce (par exemple, pour les commandes PDV, centre d’appels et e-commerce) ne prennent pas en charge la dimension de version. Il n’y a pas de calendrier confirmé quant au moment où les commandes Commerce seront améliorées pour les prendre en charge.

### <a name="functional-characteristics-of-the-version-dimension"></a>Caractéristiques fonctionnelles de la dimension de version

La dimension de version fonctionne comme les autres dimensions de produit. Cependant, en raison de sa nature spécifique et du fait qu’elle est destinée à maintenir et à suivre plusieurs versions d’un produit, elle se comporte légèrement différemment. Voici quelques-unes des différences et similitudes :

- **Il n’y a pas de groupe de versions.**

    Bien que le concept de groupes existe pour la taille, la couleur et le style (groupe de couleurs, groupe de tailles et groupe de styles), aucun concept de groupe de versions n’existe. Les groupes vous permettent de prédéfinir les valeurs applicables de sorte que lorsque, par exemple, vous attribuiez un groupe de couleurs à un produit, le produit puisse utiliser toutes les couleurs de ce groupe de couleurs. Ce concept ne s’applique pas à la dimension de version, car les versions prises par un produit ne sont pas prédéfinies lors de la création du produit. Au lieu de cela, les versions sont créées au cours du cycle de vie du produit, selon les besoins. En règle générale, si le format, l’ajustement et la fonction du produit restent les mêmes, vous créez une version au lieu d’un produit.

- **Les suggestions de variantes de produit fonctionnent comme elles le font actuellement.**

    Les suggestions de variantes de produit créeront des suggestions pour toutes les valeurs de dimension de version, comme elles le font pour les autres dimensions. Le processus de création et de publication de produits versionnés est le même que pour les produits utilisant d’autres dimensions. Lorsque vous créez un produit versionné, la première version (V1) sera créée en tant que dimension de produit et les variantes seront publiées. Au fur et à mesure que le produit change et qu’une nouvelle version est nécessaire, la nouvelle valeur de version (V2) sera ajoutée et les variantes requises seront publiées. On ne s’attend pas à ce que toutes les versions (V1, V2 et V3) soient créées à l’avance pour le produit.

> [!IMPORTANT]
> Si vous activez et utilisez la dimension de version, certaines solutions qui référencent les dimensions de stock peuvent cesser de fonctionner comme prévu. Pour confirmer et résoudre ces problèmes, contactez le fournisseur de logiciels indépendant (ISV) des solutions concernées. Pour plus d’informations, consultez [Activer la dimension de version](#enable-version-dim).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]