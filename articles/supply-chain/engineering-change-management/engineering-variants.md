---
title: Générer des variantes pour les produits d’ingénierie
description: Cette rubrique décrit comment générer des variantes pour les produits d’ingénierie
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7921983a965af5557f54f608418c8ec922256ba6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103636"
---
# <a name="generate-variants-for-engineering-products"></a>Générer des variantes pour les produits d’ingénierie

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment générer des variantes pour les produits d’ingénierie.

## <a name="turn-variant-generation-for-engineering-products-on-or-off"></a>Activer ou désactiver la génération de variantes pour les produits d’ingénierie

La fonctionnalité décrite dans cette rubrique nécessite que les deux fonctionnalités *Gestion des modifications techniques* et *Génération des variantes pour les produits d’ingénierie* soient activées pour votre système. Pour plus d’informations sur l’activation ou la désactivation de ces fonctionnalités, reportez-vous à [Présentation de la gestion des modifications techniques](product-engineering-overview.md).

## <a name="generate-one-or-more-new-variants-of-an-engineering-product"></a>Générer une ou plusieurs nouvelles variantes d’un produit d’ingénierie

Vous pouvez créer une ou plusieurs variantes d’un produit sans copier les informations d’un produit existant. Ceci est utile lorsque vous devez créer plusieurs variantes de produit en même temps.

La procédure suivante fournit un exemple de création de plusieurs variantes incluant la dimension de couleur.

1. Ouvrez la page **Produits sortis** (par exemple, allez à **Gestion du changement d’ingénierie \> Commun \> Produits sortis**).
1. Sur le volet Actions, ouvrez l’onglet **Produit** et dans le groupe **Nouveau**, cliquez sur **Produit d’ingénierie**.
1. La boîte de dialogue **Nouveau produit** s’affiche. Sélectionnez la **Catégorie Ingénierie** correspondante.
1. Si la catégorie d’ingénierie que vous avez sélectionnée inclut des dimensions de variantes, vous pouvez alors définir des valeurs pour celles-ci maintenant. Pour cet exemple, si la catégorie a une dimension **Couleur**, vous pouvez la définir sur *Bleu*.
1. Effectuez d’autres réglages si nécessaire. Cliquez sur **OK** pour créer le produit.
1. Le produit et la variante bleue V-1 sont créés et le nouveau produit s’ouvre maintenant.
1. Ajoutez une nomenclature (BOM) et acheminez vers la variante si nécessaire.
1. Sur le volet Actions, ouvrez l’onglet **Produit** et, dans le groupe **Produit générique**, cliquez sur **Dimensions de produit**.
1. La page **Dimensions du produit** s’ouvre. Cette page comprend un onglet pour chaque dimension disponible. Sur chaque onglet, ajoutez une ligne pour chaque valeur que vous prendrez en charge pour chaque dimension pertinente. (Pour cet exemple, vous pouvez ajouter des lignes sur l’onglet **Couleur** pour *blanc*, *Jaune* et *Vert*).
1. Fermez la page et sélectionnez **Variantes de produit publiées**. Notez que la première variante que vous avez créée (bleu V-1) apparaît.
1. Dans le volet Actions, sous l’onglet **Variante de produit**, sélectionnez **Suggestions de variantes**.
1. Dans la boîte de dialogue **Suggestions de variantes** exécutez l'une des étapes suivantes :

    - En haut de la boîte de dialogue, il y a une section pour chaque dimension disponible. Pour chaque dimension, cochez la case de chaque valeur pour laquelle vous souhaitez générer une suggestion de variante, puis sélectionnez **Suggérer** sur la barre d'outils. Les suggestions pertinentes sont ajoutées à la section **Variantes suggérées**.
    - Sélectionnez **Tout suggérer** dans la barre d'outils pour générer des suggestions de variantes pour toutes les combinaisons disponibles de valeurs de dimension. Les suggestions sont ajoutées à la section **Variantes suggérées**.

1. Dans la section **Variantes suggérées**, cochez la case de chaque variante que vous souhaitez créer. Sélectionnez ensuite **Créer** pour générer et transmettre les variantes sélectionnées à la société d’ingénierie. Les conditions suivantes s'appliquent :

    - Aucune des variantes créées n’aura de nomenclature ou de gamme.
    - Les attributs de ces variantes seront par défaut de la catégorie ingénierie et ne seront pas copiés à partir de la variante précédente.

## <a name="generate-a-variant-as-a-copy-of-another-product-variant"></a>Générer une variante en tant que copie d’une autre variante de produit

Vous pouvez créer une variante d’un produit sur la base d’une autre variante de produit. La nomenclature et l’itinéraire de la variante de produit source sont copiés dans la nouvelle variante. Cela peut être utile pour les produits de fabrication discrète où il peut être utile de créer la nomenclature basée sur une nomenclature de départ et de suivre les modifications par rapport à la variante précédente. Pour maintenir la traçabilité, le système enregistre quelle variante a été copiée pour créer une copie.

La procédure suivante fournit un exemple de création d’une variante qui inclut la dimension de couleur en créant une copie d’une variante existante

1. Ouvrez la page **Produits sortis** (par exemple, allez à **Gestion du changement d’ingénierie \> Commun \> Produits sortis**).
1. Sur le volet Actions, ouvrez l’onglet **Produit** et dans le groupe **Nouveau**, cliquez sur **Produit d’ingénierie**.
1. La boîte de dialogue **Nouveau produit** s’affiche. Sélectionnez la **Catégorie Ingénierie** correspondante.
1. Si la catégorie d’ingénierie que vous avez sélectionnée inclut des dimensions de variantes, vous pouvez alors définir des valeurs pour celles-ci maintenant. Pour cet exemple, si la catégorie a une dimension **Couleur**, vous pouvez la définir sur *Bleu*.)
1. Effectuez d’autres réglages si nécessaire. Cliquez sur **OK** pour créer le produit.
1. Le produit et la variante bleue V-1 sont créés et le nouveau produit s’ouvre maintenant.
1. Ajoutez une nomenclature et acheminez vers la variante si nécessaire.
1. Ajoutez des attributs à la variante de produit si nécessaire.
1. Ajoutez la variante de produit bleue V-1 à un ordre de modification technique.
1. Réglez **Impact** à *Nouvelle variante*.
1. Sélectionnez la nouvelle valeur de couleur (par exemple, *blanc*). Notez que les conditions suivantes s’appliquent : 
    - La nouvelle variante a une nomenclature et un itinéraire qui ont été copiés de la variante précédente.
    - La nouvelle variante a les attributs copiés de la variante précédente.
1. Approuvez l’ordre de modification.
1. Traitez l’ordre de modification. Une fois l’ordre traité, la nouvelle variante V-1 sera créée et remise à la société d’ingénierie.
