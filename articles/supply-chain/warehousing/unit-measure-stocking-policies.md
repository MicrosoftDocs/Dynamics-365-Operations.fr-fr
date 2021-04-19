---
title: Stratégies d’unité de mesure et de stockage
description: Cet article décrit la manière dont les unités par défaut, les séquences d’unité et les conversions d’unités sont utilisées dans les processus d’entrepôt.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetails, EcoResProductDetailsExtended, EcoResStorageDimensionGroup, InventItemOrderSetup, UnitOfMeasureConversion, WHSRFMenuItem, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29611
ms.assetid: 4b5ca875-9a06-416d-9ac0-cc3ab8f7338e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc99a6b03dace15f479e60e9f91e0d53cc0987cf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811483"
---
# <a name="unit-of-measure-and-stocking-policies"></a>Stratégies d’unité de mesure et de stockage

[!include [banner](../includes/banner.md)]

Cet article décrit la manière dont les unités par défaut, les séquences d’unité et les conversions d’unités sont utilisées dans les processus d’entrepôt.

Les groupes de séquences d’unités définissent la séquence d’unités qui peut être utilisée dans les opérations d’entrepôt. Ils sont créés dans la page **Groupes de séquences d’unités**. La séquence indique la relation des différentes unités. Par exemple, vous stockez des palettes contenant des cartons avec plusieurs articles. Dans ce cas, vous devez fournir les trois différentes unités et l’ordre logique des couches. Les groupes de séquences d’unités permettent de définir les stratégies de regroupement des contenants et les unités par défaut à utiliser pour différents processus d’entrepôt. Cet article s’applique à la solution d’entreposage avancée qui est disponible dans le module Gestion des entrepôts et à la solution d’entreposage plus basique qui est disponible dans le module Gestion des stocks.

## <a name="unit-sequence-groups-for-released-products"></a>Groupes de séquences d’unités pour les produits lancés
Si vous souhaitez utiliser des produits lancés dans les processus de travail d’entrepôt, un groupe de séquences d’unités doit leur être affecté. Si vous validez un produit associé à un groupe de dimensions de stockage et que l’option **Utiliser les processus de gestion des entrepôts** pour le groupe de dimensions de stockage est défini sur **Oui**, vous recevez un message d’erreur si un ID de groupe de séquences d’unités n’est pas défini pour le produit. Si le groupe de séquences d’unités que vous utilisez contient plusieurs lignes (et donc plusieurs unités), vous devez paramétrer une conversion d’unités entre les unités. Ce paramétrage est réalisé dans la page **Conversions d’unités**. L’unité la plus petite d’un groupe de séquences que vous associez à un produit lancé doit correspondre à l’unité de stock définie pour le produit correspondant. L’unité de stock est l’unité utilisée pour les calculs de base du stock disponible. Vous pouvez également paramétrer des conversions d’unité de mesure pour les variantes de produit des produits génériques à l’aide de l’option **Autoriser les conversions des unités de mesure**.

## <a name="license-plate-grouping"></a>Regroupement de contenants
Vous pouvez indiquer si les réceptions de plus ou moins d’une unité spécifique doivent être regroupées dans un contenant ou divisées en un contenant pour chaque unité. Pour définir ce comportement, utilisez l’option **Regroupement de contenants** sous l’onglet **Détails de ligne** de la page **Groupes de séquences d’unités**. Si vous souhaitez utiliser le regroupement de contenants lorsque vous traitez un travail avec un appareil mobile, l’option **Regroupement de contenants** doit être sélectionnée sur l’option de menu **Appareil mobile**. Par exemple, vous utilisez un appareil mobile pour enregistrer un article associé à un groupe de séquences d’unités contenant deux lignes. La première ligne concerne l’unité Pièces, et l’option **Regroupement de contenants** est définie sur **Oui**. La deuxième ligne concerne l’unité Palette, et l’option **Regroupement de contenants** est définie sur **Non**. Dans ce cas, le système peut automatiquement guider le fractionnement et la création de contenants par 100 pièces.

## <a name="units-for-cycle-counting"></a>Unités pour l’inventaire tournant
Pour définir les unités à utiliser dans le cadre des processus d’inventaire tournant, sélectionnez l’option **Utiliser l’unité pour l’inventaire tournant** dans la page **Groupes de séquences d’unités**. Vous pouvez sélectionner un maximum de quatre unités dans le groupe de séquences. Si vous sélectionnez plus de quatre unités, les unités supplémentaires ne s’affichent pas sur l’appareil mobile.

## <a name="default-units-for-mobile-device-receiving-processes"></a>Unités par défaut pour les processus de réception sur des appareils mobiles
Pour définir les unités par défaut à utiliser pour les processus de réception sur des appareils mobiles, activez les options **Unité par défaut pour les achats et les transferts** et **Unité par défaut pour la production** dans la page **Groupes de séquences d’unités**. Par exemple, vous pouvez spécifier que, par défaut, le système doit utiliser des quantités de palette lorsque le stock disponible pour la commande fournisseur est reçu à l’aide d’un appareil mobile, mais que l’unité de gestion de stock doit être Pièces. Pour obtenir la conversion du nombre de pièces contenues dans chaque palette, vous devez définir une conversion d’unités, par exemple, 100 Pcs = 1 PL.

## <a name="default-order-settings"></a>Paramètres de commande par défaut
Dans le cadre de la création des produits lancés, vous devez sélectionner les unités par défaut pour les achats, les ventes et le stock pour traiter les différentes commandes. Vous pouvez définir les unités et les quantités par défaut pour les différents documents sources à l’aide des pages **Paramètres de commande par défaut** et **Paramètres de commande spécifiques au site**. Vous pouvez accéder à ces pages à partir de la page **Produits lancés**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]