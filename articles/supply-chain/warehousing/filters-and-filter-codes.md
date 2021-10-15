---
title: Configurer les filtres de produit pour les transactions en entrepôt
description: Cette rubrique décrit la configuration des filtres de produit et des codes filtre pour classer les articles en stock par catégorie dans un entrepôt. Vous pouvez également utiliser des filtres pour indiquer quels clients peuvent commander un article particulier et spécifier les articles qui peuvent être achetés par un fournisseur spécifique.
author: Mirzaab
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSFilters,WHSFilterGroupTable,EcoResProductDetailsExtended,WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 021ce940a4ea6d59719d1c6bc79532832cc2f3ff
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567677"
---
# <a name="configure-product-filters-for-warehouse-transactions"></a>Configurer les filtres de produit pour les transactions en entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la configuration des filtres de produit et des codes filtre pour classer les articles en stock par catégorie dans un entrepôt. Vous pouvez également utiliser des filtres pour indiquer quels clients peuvent commander un article particulier et spécifier les articles qui peuvent être achetés par un fournisseur spécifique.

En outre, vous pouvez paramétrer et utiliser des filtres de produit pour organiser automatiquement les articles en stock dans un entrepôt et combiner les articles filtrés en groupes de filtres. Les filtres peuvent être utilisés pour classer les articles dans des catégories pour les processus de gestion, d’achat et de vente. Vous souhaiterez peut-être regrouper les articles ou les séparer les uns des autres lorsque la manière dont ils sont traités est basée sur des restrictions de poids ou de manipulation. Vous pouvez également spécifier à quels clients ou fournisseurs un article peut être acheté ou vendu.

## <a name="prerequisites"></a>Conditions préalables

Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.

| Logiciel requis | Instructions |
|---|---|
| Avant de commencer à configurer les produits sur la page **Détails des produits lancés**, vous devez activer le traitement de l’entrepôt pour le groupe de dimensions de stockage du produit. | Accédez à **Gestion des informations sur les produits \> Configuration \> Groupes de dimensions et de variantes \> Groupes de dimensions de stockage** et sélectionnez ou créez un groupe de dimensions de stockage où l’option **Utiliser les processus de gestion d’entrepôt** est définie sur *Oui*. |
| Si vous prévoyez d’utiliser des filtres client et/ou des filtres fournisseur, vous devez activer leur utilisation dans les paramètres de gestion d’entrepôt. | Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**. Sur l’onglet **Filtres de produit**, définissez l’option **Activer les filtres client** et/ou **Activer les filtres fournisseur** sur *Oui*. |

## <a name="set-up-product-filters"></a>Paramétrer les filtres des produits

Les filtres des produits fournissent jusqu’à 10 caractéristiques **Titre du filtre**, qui sont des valeurs d’énumération (enum). Ces valeurs d’énumération peuvent être sélectionnées lorsque vous créez un filtre de produit. Les valeurs d’énumération *Code 1* à *Code 10* sont définies par le système et représentent une caractéristique ou un attribut spécifique d’un article. Par exemple, *Code 1* peut représenter des articles qui ont une classification de matières dangereuses. *Code 2* peut représenter des articles que seuls les fournisseurs peuvent acheter. Les filtres de produits définissent ensuite la valeur **Code de filtre** associée à une valeur **Titre du filtre**.

1. Accédez à **Gestion des entrepôts \> Configuration \> Filtres de produit \> Filtres de produit**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un filtre de produit à la grille.
1. Dans le champ **Titre de filtre**, sélectionnez une valeur.
1. Dans le champ **Code de filtre**, entrez une valeur.

    ![Paramétrage d’un filtre de produit.](media/Product_Filters10.png "Paramétrage d’un filtre de produit")

1. Dans le champ **Description**, entrez un nom pour le code. Par exemple, *Code 2* pourrait représenter des fournisseurs. Vous pouvez ensuite créer un filtre de produit pour un fournisseur ou un groupe de fournisseurs spécifique. Pour plus d’informations, voir la section [Paramétrage de codes filtre fournisseur](#vendor-product-filters) plus loin dans cette rubrique.

    ![Ensemble de filtres des produits.](media/Product_Filters.png "Ensemble de filtres des produits")

## <a name="set-up-product-filter-groups"></a>Configurer les groupes de filtre de produit

Vous pouvez utiliser des groupes de filtres pour regrouper les codes de filtre. Cette fonctionnalité est utile lorsqu’un groupe est utilisé dans une requête dans une instruction d’emplacement et que vous souhaitez rechercher le groupe plutôt qu’une série de codes. Chaque groupe de filtres est associé à un groupe d’articles.

> [!IMPORTANT]
> Tous les groupes de filtres de produit ne sont pas disponibles pour les codes de filtre supérieurs à *Code 4* (c’est à dire, *Code 5* à *Code 10*). Par exemple, pour les produits lancés, bien que tous les codes de filtre de produit soient ajoutés, le regroupement des codes de filtre n’est pas mis à jour. Ce comportement peut être mis à jour dans les versions ultérieures.

Pour paramétrer des groupes de filtres, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Filtres de produit \> Groupes de filtres de produit**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans les champs **Groupe 1** et **Groupe 2**, entrez les noms utilisés pour classer les articles par catégorie.
1. Dans l’organisateur **Détails**, sélectionnez **Nouveau** pour ajouter une ligne.
1. Dans les champs **Date/heure de début** et **Date/heure de fin**, saisissez les dates de début et de fin pour le groupe de filtres.
1. Dans le champ **Groupe d’articles**, sélectionnez le groupe d’articles auquel le filtre de produit doit s’appliquer.
1. Dans les champs **Code 1** à **Code 10**, sélectionnez les codes de filtre à inclure dans le groupe, si nécessaire.

    ![Groupe d’articles.](media/ProdFilterGroup.png "Groupe d’articles")

> [!NOTE]
> Si vous recevez un message d’erreur lorsque vous fermez la page, il est possible qu’un paramétrage de code soit manquant. Sur la page **Groupes d’articles**, vous pouvez rendre les codes obligatoires pour un groupe d’articles en sélectionnant les options **Attribuer le code de filtre 1 au groupe d’articles**, **Attribuer le code de filtre 2 au groupe d’articles**, et ainsi de suite.

## <a name="set-up-filter-codes-on-item-groups"></a>Paramétrage des codes filtre sur les groupes d’articles

En paramétrant des codes filtre sur un groupe d’articles, vous pouvez créer les codes requis pour les produits dans le groupe d’articles.

Pour paramétrer des codes filtre sur des groupes d’articles, procédez comme suit.

1. Accédez à **Gestion des stocks \> Configuration \> Stock \> Groupes d’articles**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un groupe d’articles.
1. Dans le champ **Groupe d’articles**, entrez un nom.
1. Dans le champ **Nom**, entrez une description.
1. Dans l’organisateur **Entrepôt**, sous **Filtre obligatoire**, activez les cases à cocher appropriées pour définir un ou plusieurs codes filtre qui doivent être spécifiés pour les produits associés au groupe d’articles.

    Pour mettre à jour un produit lancé, ouvrez sa page **Détails des produits lancés**, puis, dans le volet Actions, sélectionnez **Modifier**. Les filtres associés aux codes deviennent alors disponibles sur l’organisateur **Entrepôt**.

    ![Groupes d’articles.](media/ItemGroup10.png "Groupes d’articles")

1. Dans la section **Filtre de groupe d’articles**, cochez les cases des filtres qui doivent correspondre pour que le groupe de filtres soit le groupe de filtres par défaut pour un article.

    Par exemple, si les cases **Utiliser le code filtre 1** et **Utiliser le code filtre 2** sont sélectionnées, alors les deux codes filtre 1 et 2 de l’article doivent correspondre au paramétrage du groupe de filtres pour le groupe d’articles avant que le groupe de filtres ne puisse être sélectionné. Lorsque vous créez un article, le groupe de filtres sélectionné est le groupe de filtres par défaut dans les champs **Groupe 1** et **Groupe 2** sur l’organisateur **Entrepôt** de la page **Détails des produits lancés**.

> [!IMPORTANT]
> Les codes filtre de produit sont activés uniquement pour les articles qui utilisent la gestion avancée de l’entrepôt.

## <a name="specify-filter-codes-for-released-products"></a>Spécification de codes filtre pour les produits lancés

Procédez comme suit pour spécifier des codes filtre pour des produits lancés. Par exemple, vous pouvez utiliser des codes filtre pour regrouper les produits dangereux achetés par des fournisseurs spécifiques.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un produit.
1. Dans la boîte de dialogue **Nouveau produit lancé**, entrez les données requises pour créer la base d’un nouveau produit, puis sélectionnez **OK**.

    Les codes filtre de produit ne sont activés que si le groupe d’articles associé au produit a été configuré pour les codes filtre.

    Pour plus d’informations, voir [Créer un nouveau produit](../pim/tasks/create-new-product.md).

1. Sur l’organisateur **Entrepôt**, dans la section **Codes filtre de produit**, sélectionnez les codes filtre pour les champs **Code 1** à **Code 10**, si nécessaire, pour spécifier les codes filtre pour le produit.

## <a name="set-up-generally-available-items"></a>Paramétrage d’articles généralement disponibles

Vous pouvez rendre des articles en stock spécifiques disponibles uniquement pour les clients ou les fournisseurs, ou pour les clients et les fournisseurs.

> [!NOTE]
> Les filtres client et fournisseur ne s’appliquent pas aux articles paramétrés comme généralement disponibles.

Pour définir des articles généralement disponibles, suivez les étapes suivantes.

1. Accédez à **Gestion des entrepôts \> Configuration \> Filtres de produit \> Produits généralement disponibles**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un enregistrement.
1. Dans le champ **Client ou fournisseur**, sélectionnez *Client*, *Fournisseur* ou *Tout* pour rendre les articles disponibles pour les clients, les fournisseurs ou les deux.
1. Dans le champ **Date/heure de début**, entrez la date et l’heure auxquelles l’article sera disponible.
1. Dans le champ **Groupe d’articles**, sélectionnez un groupe d’articles.
1. Dans les champs **Code 1** à **Code 10**, sélectionnez les codes filtre pour limiter les articles qui sont généralement disponibles.

    Lorsque vous sélectionnez un groupe d’articles, vous définissez ce groupe d’articles comme étant généralement disponible. En sélectionnant des codes filtre dans ces champs, vous limitez les articles disponibles.

## <a name="set-up-customer-product-filters"></a>Configurer les filtres de produit des clients

Cette procédure facultative indique comment spécifier les articles qui doivent être disponibles pour un client en plus des articles qui sont rendus disponibles via le paramétrage de filtre sur la page **Articles généralement disponibles**. Vous pouvez paramétrer plusieurs filtres pour un même client.

Pour paramétrer des codes filtre client, suivez les étapes suivantes.

1. Allez dans **Ventes et marketing \> Clients \> Tous les clients**.
1. Sélectionnez un client.
1. Dans le volet Actions, sous l’onglet **Client**, dans le groupe **Paramétrer**, sélectionnez **Filtres de produit**.
1. Sur la page **Codes filtre de produit**, dans le volet Actions, sélectionnez **Nouveau**.
1. Dans les champs **Date/heure de début** et **Date/heure de fin**, saisissez les dates de début et de fin pour le groupe d’articles sélectionné.
1. Dans le champ **Groupe d’articles**, sélectionnez un groupe d’articles.
1. Dans les champs **Code 1** à **Code 10**, sélectionnez les codes filtre à utiliser comme critères pour limiter les articles disponibles pour les clients du groupe d’articles sélectionné. Vous devez effectuer une sélection pour chaque code filtre configuré pour le groupe d’articles.

## <a name="set-up-vendor-product-filters"></a><a name="vendor-product-filters"></a>Configurer les filtres de produit des fournisseurs

Cette procédure facultative indique comment spécifier les articles qui doivent être disponibles pour un fournisseur en plus des articles qui sont rendus disponibles via le paramétrage de filtre sur la page **Articles généralement disponibles**. Vous pouvez paramétrer plusieurs filtres pour un même fournisseur.

Pour paramétrer des codes filtre fournisseur, suivez les étapes suivantes.

1. Accédez à **Approvisionnements \> Fournisseurs \> Tous les fournisseurs**.
1. Sélectionnez un fournisseur.
1. Dans le volet Actions, sous l’onglet **Fournisseur**, dans le groupe **Paramétrer**, sélectionnez **Filtres de produit**.
1. Sur la page **Codes filtre**, dans le volet Actions, sélectionnez **Nouveau**.
1. Dans les champs **Date/heure de début** et **Date/heure de fin**, saisissez les dates de début et de fin pour le groupe d’articles sélectionné.
1. Dans le champ **Groupe d’articles**, sélectionnez un groupe d’articles.
1. Dans les champs **Code 1** à **Code 10**, sélectionnez les codes filtre à utiliser comme critères pour limiter les articles disponibles pour les fournisseurs du groupe d’articles sélectionné. Vous devez effectuer une sélection pour chaque code filtre configuré pour le groupe d’articles.

> [!NOTE]
> La configuration des filtres de produit fournisseur s’applique aux produits lancés pour lesquels les processus de gestion d’entrepôt sont activés pour le groupe de dimensions de stockage associé. Les codes de filtre sont utilisés pour déterminer si le système autorise les utilisateurs à acheter un article donné auprès d’un fournisseur donné lorsqu’ils créent des lignes de commande fournisseur. Microsoft Dynamics 365 Supply Chain Management a deux méthodes pour gérer l’approbation du fournisseur. S’il existe un ou plusieurs produits lancés où le champ **Méthode de vérification fournisseur approuvée** est défini sur *Avertissement seulement* ou *Non autorisé*, les deux méthodes d’approbation du fournisseur peuvent être activées pour ces articles. Cette situation peut entraîner des problèmes lorsque les utilisateurs créent des lignes de commande fournisseur.

## <a name="see-also"></a>Voir également :

[Pour plus d’informations, consultez le billet de blog Codes de filtrage entrepôt compatible WMS](http://blog.dynamics-for-operations.com/2017/09/26/wms-warehouse-filter-codes/)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]