---
title: Appliquer les paramètres de stock
description: Cette rubrique couvre les paramètres de stock et décrit leur application dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: dfa8b2bdc03e3698feda26932db757421097140d
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517062"
---
# <a name="apply-inventory-settings"></a>Appliquer les paramètres de stock

[!include [banner](includes/banner.md)]

Cette rubrique couvre les paramètres de stock et décrit leur application dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les paramètres de stock spécifient si le stock doit être vérifié avant que des produits ne soient ajoutés au panier. Ils définissent également les messages de marchandisage liés au stock, tels que « En stock » et « Plus que quelques-uns ». Ces paramètres garantissent qu’un produit ne peut pas être acheté s’il est en rupture de stock.

Dynamics 365 Commerce fournit des estimations de la disponibilité des produits. Pour plus d’informations sur le calcul de la disponibilité estimée des produits, voir [Calculer la disponibilité des stocks pour les canaux de vente au détail](calculated-inventory-retail-channels.md).

Dans le générateur de site Commerce, il est possible de définir des seuils et des plages de stocks pour un produit ou une catégorie. Ils déterminent si l’inventaire peut être classé comme en stock, en stock faible ou en rupture de stock. Pour plus de détails, voir [Configurer les marges de stock et les niveaux de stock](inventory-buffers-levels.md).

> [!NOTE]
> La prise en charge des seuils et des plages de stock est disponible dans Dynamics 365 Commerce version 10.0.12.

## <a name="inventory-settings"></a>Paramètres de stock

Dans Commerce, les paramètres de stock sont définis dans **Paramètres du site \> Extensions \> Gestion du stock** dans le générateur de site. Il existe quatre paramètres de stock, dont l’un est obsolète (déconseillé) :

- **Activer la vérification du stock dans l’application** – Ce paramètre active une vérification du stock des produits. Les modules de zone d’achat, de panier et de prélèvement en magasin vérifieront alors le stock des produits et ne permettront d’ajouter un produit au panier que si le stock est disponible.
- **Niveau de stock basé sur** – Ce paramètre définit la façon dont les niveaux de stock sont calculés. Les valeurs disponibles sont **Total disponible**, **Disponible physique**, et **Seuil de rupture de stock**. Dans Commerce, il est possible de définir des seuils et des plages de stocks pour chaque produit et catégorie. Les API de stock renvoient des informations sur l’inventaire des produits pour les deux propriétés **Total disponible** et **Disponible physique**. Le distributeur décide si la valeur **Total disponible** ou **Disponible physique** doit être utilisée pour déterminer le nombre en stock et les plages correspondantes pour les statuts « en stock » et « en rupture de stock ».

    La valeur **Seuil de rupture de stock** du paramètre **Niveau de stock basé sur** est une valeur ancienne (héritée) et obsolète. Lorsqu’il est sélectionné, le nombre en stock est déterminé à partir des résultats de la valeur **Total disponible**, mais le seuil est défini par le paramètre numérique **Seuil de rupture de stock** décrit plus loin. Ce paramètre de seuil s’applique à tous les produits d’un site d'e-commerce. Si le stock est inférieur au seuil, un produit est considéré comme en rupture de stock. Sinon, il est considéré comme en stock. Les fonctionnalités de la valeur **Seuil de rupture de stock** sont limitées et nous vous déconseillons de l’utiliser dans la version 10.0.12 et les versions ultérieures.

- **Plages de stock** – Ce paramètre définit les plages de stock pour lesquelles des messages sont affichés sur les modules du site. Il est applicable uniquement si la valeur **Total disponible** ou la valeur **Disponible physique** est sélectionnée pour le paramètre **Niveau de stock basé sur**. Les valeurs disponibles sont **Tout**, **Stock faible et rupture de stock** et **En rupture de stock**.

    - Quand **Tout** est sélectionné, les messages pour toutes les plages de stock, depuis en stock (message « Disponible ») jusqu’à rupture de stock (message « Épuisé »), seront affichés.
    - Quand **Stock faible et rupture de stock** est sélectionné, les messages pour toutes les plages de stock, sauf en stock (message « Disponible »), seront affichés.
    - Quand **En rupture de stock** est sélectionné, seul le message « Épuisé » sera affiché.

- **Seuil de rupture de stock** – Cet ancien paramètre numérique ne prendra effet que si la valeur **Seuil de rupture de stock** est sélectionnée pour le paramètre **Niveau de stock basé sur**.

> [!IMPORTANT] 
> Ces paramètres sont disponibles dans la version 10.0.12 de Dynamics 365 Commerce. Si vous effectuez une mise à jour à partir d'une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour obtenir des instructions de mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Modules qui utilisent les paramètres de stock

Les modules Zone d’achat, Liste de souhaits, Sélecteur de magasin, Panier et Icône de panier utilisent les paramètres de stock pour afficher les plages et les messages de stock.

L’image suivante montre un exemple de page de détails du produit (PDP) qui affiche un message en stock (« Disponible »).

![Exemple d’un module PDP qui affiche un message en stock](./media/pdp-InStock.png)

L’image suivante montre un exemple de page PDP qui affiche un message de rupture de stock (« Épuisé »).

![Exemple d’un module PDP qui affiche un message de rupture de stock](./media/pdp-outofstock.png)

L’image suivante montre un exemple de panier qui affiche un message de stock (« Disponible »).

![Exemple d’un module de panier qui affiche un message en stock](./media/cart-instock.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Configurer des marges de stock et des niveaux de stock](inventory-buffers-levels.md)

[Module de panier](add-cart-module.md)

[Module de zone d’achat](add-buy-box.md)

[Pages et modules Gestion des comptes](account-management.md)

[Module Sélection de magasin](store-selector.md)

[Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md)
