---
title: Attributs d’ingénierie et recherche d’attributs d’ingénierie
description: Cette rubrique explique comment utiliser les attributs d’ingénierie pour spécifier toutes les caractéristiques non standard, afin de garantir que toutes les données de base produit peuvent être enregistrées dans le système. Il explique également comment vous pouvez utiliser la recherche d’attributs d’ingénierie pour trouver facilement des produits en fonction de ces caractéristiques enregistrées.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductAttributeSearch, EngChgMaintainAttributeInheritance, EngChgAttribute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: a367b95a65c45b1e7ac46e9ac96baa2417bf3e48e3d5bfeca21c82cc8c427c24
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714352"
---
# <a name="engineering-attributes-and-engineering-attribute-search"></a>Attributs d’ingénierie et recherche d’attributs d’ingénierie

[!include [banner](../includes/banner.md)]

Vous devez utiliser les attributs d’ingénierie pour spécifier toutes les caractéristiques non standard, afin de vous assurer que toutes les données de produit générique peuvent être enregistrées dans le système. Vous pouvez ensuite utiliser la recherche d’attributs d’ingénierie pour trouver facilement des produits en fonction de ces caractéristiques enregistrées.

## <a name="engineering-attributes"></a>Attributs d’ingénierie

En règle générale, les produits d’ingénierie ont de nombreuses caractéristiques et propriétés que vous devez capturer. Bien que vous puissiez enregistrer certaines des propriétés à l’aide des champs de produit standard, vous pouvez également créer des propriétés d’ingénierie si nécessaire. Vous pouvez définir vos propres *attributs d’ingénierie* et les intégrer à la définition du produit.

### <a name="create-engineering-attributes-and-attribute-types"></a>Créer des attributs d’ingénierie et des types d’attributs

Chaque attribut d’ingénierie doit appartenir à un *type d’attribut*. Cette exigence existe car chaque attribut d’ingénierie doit avoir un *Type de données* qui définit les types de valeurs qu’il peut contenir. Un type d’attribut d’ingénierie peut être un type standard (tel que du texte libre, un entier ou un décimal) ou un type personnalisé (tel qu’un texte comportant un ensemble spécifique de valeurs à sélectionner). Vous pouvez réutiliser chaque type d’attribut avec n’importe quel nombre d’attributs d’ingénierie.

#### <a name="set-up-engineering-attribute-types"></a>Paramétrer les types d’attributs d’ingénierie

Pour afficher, créer ou modifier un type d’attribut d’ingénierie, procédez comme suit.

1. Aller à **Gestion du changement d’ingénierie \> Configurer \> Attributs \> Types d’attributs**.
1. Sélectionnez un type d’attribut existant dans le volet de liste ou sélectionnez **Nouveau** dans le volet Actions pour créer un type d’attribut.
1. Définisse les champs suivants :

    - **Nom du type d’attribut** – Entrez un nom pour le type d’attribut.
    - **Type** – Sélectionnez un type de données standard (*Devise*, *DateHeure*, *Décimal*, *Entier*, *Texte*, *Booléen* ou *Référence*).
    - **Liste fixe** – Cette option n’est disponible que si vous définissez le champ **Type** sur *Texte*. Définissez-le sur *Oui* pour définir des valeurs spécifiques pour les attributs de ce type. Dans ce cas, une liste déroulante sera créée. Vous utilisez le raccourci **Valeur** pour établir les valeurs disponibles pour ce type d’attribut. Définissez cette option sur *Non* pour permettre aux utilisateurs d’entrer n’importe quelle valeur. Dans ce cas, un champ de saisie sera créé.
    - **Plage de valeurs** – Cette option n’est disponible que si vous définissez le champ **Type** sur *Entier*, *Décimal* ou *Devise*. Définissez-le sur *Oui* pour établir les valeurs minimales et maximales qui seront acceptées pour les attributs de ce type. Vous utilisez le raccourci **Intervalle** pour établir les valeurs minimum et maximum et (pour la devise) la devise qui s’applique aux limites que vous avez entrées. Définissez cette option sur *Non* pour accepter n’importe quelle valeur. 
    - **Unité de mesure** – Ce champ n’est disponible que si vous définissez le champ **Type** sur *Entier* ou *Décimal*. Sélectionnez l’unité de mesure qui s’applique à ce type d’attribut. Si aucune unité n’est requise, laissez ce champ vide.

#### <a name="set-up-engineering-attributes"></a>Paramétrer les attributs d’ingénierie

Pour afficher, créer ou modifier un attribut d’ingénierie, procédez comme suit.

1. Aller à **Gestion du changement d’ingénierie \> Configurer \> Attributs \> Attributs d’ingénierie**.
1. Sélectionnez un attribut existant dans le volet de liste ou sélectionnez **Nouveau** dans le volet Actions pour créer un attribut.
1. Définisse les champs suivants :

    - **Nom** – Entrez un nom pour l’attribut. Ce nom n’apparaît que sur la page **Attributs d’ingénierie**. Partout ailleurs dans le système, la valeur du **Nom convivial** est généralement affiché pour identifier l’attribut.
    - **Type d’attribut** – Sélectionnez un type d’attribut que vous avez défini dans la section précédente.
    - **Nom convivial** – Entrez un nom qui identifiera l’attribut dans le système (sauf sur la page **Attributs d’ingénierie**). 
    - **Description** – Entrez une description de l’attribut.
    - **Texte d’aide** – Entrez le texte d’aide qui indique aux autres utilisateurs à quoi sert l’attribut.
    - **Valeur par défaut** – Entrez une valeur par défaut pour l’attribut. Les options présentées dépendent du type d’attribut que vous avez sélectionné.
    - **Devise** – Si le type d’attribut que vous avez sélectionné est une devise, sélectionnez la devise que l’attribut acceptera et affichera les valeurs dans.

1. Si le type d’attribut que vous avez sélectionné est un entier ou un décimal, le raccourci **Intervalle** s’affiche. Dans cet organisateur, définissez les champs suivants si nécessaire :

    - **Action de tolérance** – Sélectionnez la manière dont le système doit répondre si un utilisateur entre une valeur en dehors de la plage spécifiée. Si vous sélectionnez *Avertissement*, un avertissement s’affiche, mais l’utilisateur peut enregistrer la valeur. Si vous sélectionnez *Non autorisé*, un avertissement s’affiche et la valeur ne peut pas être enregistrée tant que l’utilisateur ne l’a pas corrigée.
    - **Minimum** – Entrez la valeur minimale recommandée ou acceptée.
    - **Maximum** – Entrez la valeur maximale recommandée ou acceptée.

### <a name="connect-engineering-attributes-to-an-engineering-product-category"></a>Connectez les attributs d’ingénierie à une catégorie de produits d’ingénierie

Certains attributs d’ingénierie s’appliquent à tous les produits, tandis que d’autres sont spécifiques à des produits individuels ou à des catégories de produits. Par exemple, les attributs électriques ne sont pas requis pour les produits mécaniques. Par conséquent, vous pouvez configurer des *catégories de produits d’ingénierie*. Une catégorie de produits d’ingénierie établit l’ensemble des attributs d’ingénierie qui doivent faire partie de la définition des produits appartenant à cette catégorie. Vous pouvez également spécifier les attributs d’ingénierie obligatoires et s’il existe une valeur par défaut.

Pour plus d’informations sur l’utilisation des catégories de produits d’ingénierie, notamment sur la manière de connecter des attributs à des catégories, voir [Versions d’ingénierie et catégories de produits d’ingénierie](engineering-versions-product-category.md).

### <a name="set-values-for-engineering-attributes"></a>Définir les valeurs des attributs d’ingénierie

Les attributs d’ingénierie qui sont connectés à une catégorie de produits d’ingénierie sont présentés lorsque vous créez un produit d’ingénierie basé sur cette catégorie. À ce moment-là, vous pouvez définir des valeurs pour les attributs. Plus tard, ces valeurs peuvent être modifiées sur la page **Version d’ingénierie** ou dans le cadre de la gestion des modifications techniques dans un ordre de modification technique. Pour plus d’informations, voir [Gérer modifications des produits techniques](engineering-change-management.md).

### <a name="create-an-engineering-product"></a>Créer un produit d’ingénierie

Pour créer un produit d’ingénierie, ouvrez la page **Produits lancés**. Ensuite, sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Nouveau**, cliquez sur **Produit d’ingénierie**.

Vous devez spécifier la catégorie d’ingénierie à laquelle appartient le produit. La catégorie définira toutes les valeurs et caractéristiques par défaut du produit. Il définira également les attributs applicables au produit. Une fois la catégorie sélectionnée, des valeurs seront définies pour les attributs. Vous pouvez ensuite modifier ces valeurs.

## <a name="search-for-products-by-using-engineering-attribute-values"></a>Rechercher des produits à l’aide des valeurs d’attributs d’ingénierie

Vous pouvez utiliser la recherche d’attributs d’ingénierie pour rechercher des produits en recherchant leurs valeurs d’attributs d’ingénierie. Par conséquent, vous pouvez facilement trouver des produits d’ingénierie, en fonction de leurs caractéristiques. Vous pouvez rechercher dans les produits appartenant à une catégorie de produits d’ingénierie, ou vous pouvez rechercher dans tous les produits d’ingénierie.

La recherche est disponible sur les pages de données de base produit et à partir des postes transactionnels du système, tels que les commandes client. Pour un article transactionnel, vous pouvez utiliser la page **Recherche d’attributs d’ingénierie** pour rechercher un produit. Vous pouvez ensuite utiliser le bouton **Ajouter en tant que nouvelle ligne** pour ajouter le produit aux lignes de commande client. Les produits dans les résultats de la recherche peuvent également être ajoutés directement à la commande.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]