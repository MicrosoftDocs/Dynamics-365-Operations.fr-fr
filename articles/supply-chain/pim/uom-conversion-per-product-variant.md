---
title: Conversion d’unité de mesure selon la variante de produit
description: Cet article explique comment paramétrer les conversions d’unités de mesure selon les variantes de produit. Elle inclut un exemple de paramétrage.
author: t-benebo
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: a605e510ac8faa1f92e105c9fcc30222ef78e05e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869631"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Conversion d’unité de mesure selon la variante de produit

[!include [banner](../includes/banner.md)]

Cet article explique comment paramétrer les conversions d’unités de mesure pour différentes variantes de produit.

Vous pouvez utiliser les variantes de produit pour créer des variations d’un seul produit au lieu de créer plusieurs produits à mettre à jour. Par exemple, une variante de produit peut être un T-shirt d’une taille et d’une couleur données.

Auparavant, les conversions d’unités ne pouvaient être configurées que sur la fiche produit. Par conséquent, toutes les variantes de produit avaient les mêmes règles de conversion d’unité. Cependant, lorsque la fonctionnalité *Conversions d’unités de mesure pour les variantes de produit* est activée, si vos T-shirts sont vendus dans des boîtes et que le nombre de T-shirts pouvant être emballés dans une boîte dépend de la taille des T-shirts, vous pouvez maintenant configurer des conversions d’unités entre les différentes tailles de chemises et les boîtes utilisées pour l’emballage.

## <a name="turn-on-the-feature-in-your-system"></a>Activez la fonctionnalité dans votre système

Si vous ne voyez pas cette fonctionnalité dans votre système, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Conversions d’unités de mesure pour les variantes de produit*.

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Paramétrage d’un produit pour la conversion d’unités par variante

Les variantes de produit peuvent être créées uniquement pour les produits génériques. Pour plus d’informations, voir [Création d’un produit générique](tasks/create-product-master.md). La fonctionnalité *Conversions d’unités de mesure pour les variantes de produit* n’est pas disponible pour les produits configurés pour les processus en poids variable.

Pour configurer une fiche produit pour prendre en charge la conversion d’unités par variante, procédez comme suit :

1. Allez dans **Gestion des informations sur les produits \> Produits \> Produits génériques**.
1. Créez ou ouvrez une fiche produit pour accéder à la page **Détails du produit**.
1. Définissez l’option **Autoriser les conversions des unités de mesure** sur *Oui*.
1. Sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Paramétrer**, cliquez sur **Conversions d’unités**.
1. La page **Conversions d’unités** s’ouvre. Sélectionnez l’un des onglets suivants :

    - **Conversions intra-classe :** Sélectionnez cet onglet pour convertir entre les unités appartenant à la même classe d’unités.
    - **Conversions inter-classe :** Sélectionnez cet onglet pour convertir entre les unités appartenant à des classes d’unités différentes.

1. Cliquez sur **Nouveau** pour ajouter une nouvelle unité.
1. Définissez le champ **Créer une conversion pour** sur l’une des valeurs suivantes :

    - **Produit :** Si vous sélectionnez cette valeur, vous pouvez paramétrer une conversion d’unité pour le produit générique. Cette conversion d’unité sera utilisée comme solution de rechange pour toutes les variantes de produit pour lesquelles aucune conversion d’unité n’est définie.
    - **Variante de produit :** Si vous sélectionnez cette valeur, vous pouvez paramétrer une conversion d’unités pour une variante de produit spécifique. Utilisez le champ **Variante de produit** pour sélectionner la variante.

    ![Ajout d’une nouvelle conversion d’unité.](media/uom-new-conversion.png "Ajout d’une nouvelle conversion d’unité")

1. Utilisez les autres champs fournis pour configurer votre conversion d’unité.
1. Cliquez sur **OK** pour enregistrer la nouvelle conversion d’unité.

> [!TIP]
> Vous pouvez ouvrir la page **Conversions d’unités** d’un produit ou d’une variante de produit à partir de l’une des pages suivantes :
> 
> - Détails de produit
> - Détails des produits lancés
> - Variantes de produit lancé

## <a name="example-scenario"></a>Exemple de scénario

Dans ce scénario, une société vend des T-shirts dans les tailles S, M, L et XL. Le T-shirt est défini comme produit, et les différentes tailles sont définies en tant que variantes de ce produit. Les chemises sont emballées dans des boîtes. Pour les tailles S, M et L, il peut y avoir cinq chemises dans chaque boîte. Cependant, pour la taille XL, il n’y a de la place que pour quatre chemises dans chaque boîte.

La société souhaite suivre les différentes variantes de T-shirts dans l’unité *Pièces* mais vend les T-shirts dans l’unité *Boîtes*. Pour les tailles S, M et L, la conversion entre l’unité d’inventaire et l’unité de vente est de 1 boîte = 5 pièces. Pour une taille XL, la conversion est de 1 boîte = 4 pièces.

1. Sur la page **Détails des produits lancés** pour le produit **T-Shirt**, ouvrez la page **Conversions d’unité**.
1. Dans la page **Conversions d’unité**, paramétrez la conversion d’unité suivante pour la variante de produit lancé **XL**.

    | Champ                 | Paramètre                 |
    |-----------------------|-------------------------|
    | Créer une conversion pour | Variante de produit         |
    | Variante de produit       | T-shirt : : XL : : |
    | Unité - De             | Boîtes                   |
    | Facteur                | 4                       |
    | À l’unité               | Pièces                  |

1. Comme les variantes de produit **S**, **M** et **L** ont la même conversion d’unité entre les unités *Boîte* et *Pièces*, vous pouvez définir la conversion d’unité suivante pour ces variantes de produit dans le produit générique.

    | Champ                 | Paramètre |
    |-----------------------|---------|
    | Créer une conversion pour | Produit |
    | Produit               | T-shirt |
    | Unité - De             | Boîtes   |
    | Facteur                | 5       |
    | À l’unité               | Pièces  |

## <a name="using-excel-to-update-the-unit-conversions"></a>Utilisation d’Excel pour mettre à jour les conversions d’unité

Si un produit comporte de nombreuses variantes avec des conversions d’unités différentes, il est judicieux d’exporter les conversions d’unité vers un classeur Microsoft Excel, de les mettre à jour, puis de les publier à nouveau dans Dynamics 365 Supply Chain Management.

Pour exporter des conversions d’unité vers Excel, sur la page **Conversions d’unités**, dans le volet Actions, sélectionnez **Ouvrir dans Microsoft Office**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Gérer les unités de mesure](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]