---
title: Règles des propriété des sociétés d’ingénierie et des données
description: Cette rubrique explique comment vous pouvez utiliser une ou plusieurs sociétés d’ingénierie pour vous assurer que les données de base des produits sont créées et gérées de manière centralisée. Une société d’ingénierie représente l’entreprise qui possède les produits d’ingénierie et ses données pertinentes pour l’ingénierie.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEngineeringOrganization
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8bfb0a05fb608f1ee7c6377adaba0c15ee360579aefb74d8218ea4b3dfed9003
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716540"
---
# <a name="engineering-companies-and-data-ownership-rules"></a>Règles des propriété des sociétés d’ingénierie et des données

[!include [banner](../includes/banner.md)]

## <a name="engineering-companies-and-operational-companies"></a>Sociétés d’ingénierie et sociétés opérationnelles

Pour vous assurer que les données de base des produits sont créées et gérées de manière centralisée, vous pouvez utiliser une ou plusieurs *sociétés d’ingénierie*. Une société d’ingénierie possède les produits d’ingénierie et leurs données pertinentes pour l’ingénierie. Elle est toujours connectée à (basée sur) une *entité légale* existante, qui est aussi une entreprise. Grâce à cette connexion, le système établit un point d’entrée central pour toutes les données importantes pour l’ingénierie des produits d’ingénierie dans l’entreprise d’ingénierie. Dans ce point d’entrée central, les produits d’ingénierie sont créés et les données pertinentes pour l’ingénierie sont gérées. À partir de là, les produits d’ingénierie et les données pertinentes pour l’ingénierie seront diffusés aux *sociétés opérationnelles*, qui sont d’autres entités juridiques. (Pour plus d’informations sur la gestion des versions, voir [Structures des produits lancés](release-product-structure.md).) Ces sociétés opérationnelles utiliseront les données d’ingénierie telles qu’elles ont été conçues par la société d’ingénierie. Toutes les données logistiques sont gérées localement par chaque société d’ingénierie et société opérationnelle.

Pour créer une société d’ingénierie, accédez à **Gestion du changement d’ingénierie \> Configurer \> Organisations d’ingénierie**. Sélectionnez **Nouveau**, entrez un nom pour la société d’ingénierie et sélectionnez la société existante (entité juridique) sur laquelle elle est basée.

Si vous intégrez des systèmes de gestion du cycle de vie des produits externes, vous devez créer une unité commerciale (type d’entreprise) qui deviendra une entreprise externe.

## <a name="engineering-product-categories-and-engineering-companies"></a>Catégories de produits d’ingénierie et société d’ingénierie

*Catégories de produits d’ingénierie* vous garantit que les produits d’ingénierie sont créés conformément aux règles commerciales de votre entreprise et se comportent comme il se doit. Pour plus d’informations sur les catégories de produits d’ingénierie, voir [Versions d’ingénierie et catégories de produits d’ingénierie](engineering-versions-product-category.md).

Chaque catégorie de produits d’ingénierie appartient à une société d’ingénierie spécifique et ne peut créer que des produits appartenant à cette société. De même, le droit de maintenir un produit d’ingénierie appartient également à l’entreprise associée à la catégorie de produits d’ingénierie de ce produit.

## <a name="data-that-is-owned-by-the-engineering-company"></a>Données appartenant à la société d’ingénierie

Étant donné que la société d’ingénierie détient les données pertinentes pour l’ingénierie, elle contrôle les processus suivants :

- **Création de produits d’ingénierie :** Chaque société d’ingénierie ne peut créer que des produits d’ingénierie basés sur une catégorie de produits d’ingénierie qui lui appartient. Dans certains cas, les sociétés opérationnelles conservent leurs propres données locales liées à ces produits.
- **Création de versions d’ingénierie :** Lorsqu’une entreprise crée un produit d’ingénierie, le système crée automatiquement une version d’ingénierie initiale pour celui-ci. Seule la société d’ingénierie propriétaire pourra créer des versions de ce produit.
- **Création et tenue à jour d’attributs d’ingénierie :** Lorsqu’une entreprise crée un produit d’ingénierie, le système y ajoute automatiquement des attributs d’ingénierie. Seule la société d’ingénierie propriétaire pourra créer et gérer les valeurs de ces attributs. Pour plus d’informations sur les attributs d’ingénierie, voir [Attributs d’ingénierie et recherche d’attributs d’ingénierie](engineering-attributes-and-search.md).
- **Création et maintenance des nomenclatures (BOM) liées aux versions d’ingénierie :** L’entreprise d’ingénierie propriétaire peut connecter directement une nomenclature à une version de produit d’ingénierie. Lorsque ces nomenclatures sont validées pour d’autres entités juridiques, les modifications apportées aux données d’ingénierie sur les nomenclatures sont limitées des manières suivantes :

    - La société opérationnelle ne peut pas supprimer les lignes de nomenclature validées.
    - Les zones d’ingénierie des lignes de nomenclature sont en lecture seule pour la société opérationnelle. Tous les autres champs sont des champs d’implémentation logistique et peuvent être édités par la société opérationnelle.
    - La société opérationnelle peut ajouter des lignes de nomenclature à la même nomenclature. De cette manière, il peut ajouter des ajouts locaux, tels que des matériaux d’emballage ou des fluides de lubrification.
    - L’entreprise opérationnelle peut ajouter une nomenclature locale entièrement nouvelle. Cette modification peut être nécessaire dans les cas où, par exemple, aucune nomenclature n’est fournie lors de la validation. La société opérationnelle possède et gère ces nomenclatures locales. Pour plus d’informations sur la gestion des versions, voir [Structures des produit lancés](release-product-structure.md).
    - Toutes les nomenclatures et lignes de nomenclature locales sont conservées lorsque la société d’ingénierie met à jour sa nomenclature.

- **Création et maintenance des gammes liées aux versions d’ingénierie :** L’entreprise d’ingénierie peut connecter directement une gamme à chaque version de produit d’ingénierie. Lorsque ces gammes sont validées pour d’autres entités juridiques, les modifications apportées aux données d’ingénierie sur les gammes sont limitées des manières suivantes :

    - Les autres entités juridiques ne peuvent pas supprimer les données d’ingénierie sur les gammes.
    - Les autres entités juridiques peuvent ajouter des opérations à l’itinéraire. De cette façon, ils peuvent ajouter des étapes d’itinéraire locales.
    - Les entreprises opérationnelles peuvent ajouter des gammes locales entièrement nouvelles. Cette modification peut être nécessaire dans les cas où, par exemple, aucune gamme n’est fournie lors de la validation. Les sociétés opérationnelles possèdent et gèrent ces gammes locales. Pour plus d’informations sur la gestion des versions, voir [Structures des produit lancés](release-product-structure.md).
    - Toutes les modifications apportées localement sont conservées lorsque les mises à jour de la société d’ingénierie sont à nouveau publiées sur les itinéraires.

- **Création et maintenance de documents d’ingénierie :** La société d’ingénierie peut joindre des documents d’ingénierie à chaque version d’ingénierie.

    - Lorsque ces documents sont remis à d’autres entités juridiques, les documents sont protégés contre la suppression par la société opérationnelle.
    - D’autres entités juridiques peuvent ajouter des documents locaux entièrement nouveaux. La société opérationnelle possède et gère ces documents locaux.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]