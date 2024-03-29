---
title: Appliquer les paramètres de stock
description: Cet article couvre les paramètres de stock et décrit leur application dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 49310a44f8b9c636734e04d4eed9445384b55791
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405318"
---
# <a name="apply-inventory-settings"></a>Appliquer les paramètres de stock

[!include [banner](includes/banner.md)]

Cet article couvre les paramètres de stock et décrit leur application dans Microsoft Dynamics 365 Commerce.

Les paramètres de stock spécifient si le stock doit être vérifié avant que des produits ne soient ajoutés au panier. Ils définissent également les messages de marchandisage liés au stock, tels que « En stock » et « Plus que quelques-uns ». Ces paramètres garantissent qu’un produit ne peut pas être acheté s’il est en rupture de stock.

Dynamics 365 Commerce fournit des estimations de la disponibilité des produits. Pour plus d’informations sur le calcul de la disponibilité estimée des produits, voir [Calculer la disponibilité des stocks pour les canaux de vente au détail](calculated-inventory-retail-channels.md).

Dans le générateur de site Commerce, il est possible de définir des seuils et des plages de stocks pour un produit ou une catégorie. Ils déterminent si l’inventaire peut être classé comme en stock, en stock faible ou en rupture de stock. Pour plus de détails, voir [Configurer les marges de stock et les niveaux de stock](inventory-buffers-levels.md).

> [!NOTE]
> La prise en charge des seuils et des plages de stock est disponible dans Dynamics 365 Commerce version 10.0.12.

## <a name="inventory-settings"></a>Paramètres de stock

Dans Commerce, les paramètres de stock sont définis dans **Paramètres du site \> Extensions \> Gestion du stock** dans le générateur de site. Il existe six paramètres de stock, dont l’un est obsolète (déconseillé) :

- **Activer la vérification du stock dans l’application** – Ce paramètre active une vérification du stock des produits. Les modules de zone d’achat, de panier et de prélèvement en magasin vérifieront alors le stock des produits et ne permettront d’ajouter un produit au panier que si le stock est disponible.
- **Niveau de stock basé sur** – Ce paramètre définit la façon dont les niveaux de stock sont calculés. Les valeurs disponibles sont **Total disponible**, **Disponible physique**, et **Seuil de rupture de stock**. Dans Commerce, il est possible de définir des seuils et des plages de stocks pour chaque produit et catégorie. Les API de stock renvoient des informations sur l’inventaire des produits pour les deux propriétés **Total disponible** et **Disponible physique**. Le distributeur décide si la valeur **Total disponible** ou **Disponible physique** doit être utilisée pour déterminer le nombre en stock et les plages correspondantes pour les statuts « en stock » et « en rupture de stock ».

    La valeur **Seuil de rupture de stock** du paramètre **Niveau de stock basé sur** est une valeur ancienne (héritée) et obsolète. Lorsqu’il est sélectionné, le nombre en stock est déterminé à partir des résultats de la valeur **Total disponible**, mais le seuil est défini par le paramètre numérique **Seuil de rupture de stock** décrit plus loin. Ce paramètre de seuil s’applique à tous les produits d’un site d’e-commerce. Si le stock est inférieur au seuil, un produit est considéré comme en rupture de stock. Sinon, il est considéré comme en stock. Les fonctionnalités de la valeur **Seuil de rupture de stock** sont limitées et nous vous déconseillons de l’utiliser dans la version 10.0.12 et les versions ultérieures.

- **Niveau d’inventaire pour plusieurs entrepôts** – Ce paramètre permet de calculer le niveau de stock par rapport à l’entrepôt par défaut ou à plusieurs entrepôts. L’option **Basé sur un entrepôt individuel** calcule les niveaux de stock en fonction de l’entrepôt par défaut. Alternativement, un site de commerce électronique peut pointer vers plusieurs entrepôts pour faciliter l’exécution. Dans ce cas, l’option **Basé sur l’agrégat pour les entrepôts d’expédition et de ramassage** est utilisée pour indiquer la disponibilité du stock. Par exemple, lorsqu’un client achète un article et sélectionne « expédition » comme mode de livraison, l’article peut être expédié à partir de n’importe quel entrepôt du groupe d’exécution qui dispose d’un stock disponible. La page de détails des produits (PDP) affichera un message « En stock » pour l’expédition si un entrepôt d’expédition disponible dans le groupe de traitement a du stock. 

    > [!IMPORTANT] 
    > Le paramètre **Niveau d’inventaire pour plusieurs entrepôts** est disponible à partir de la version 10.0.19 de Commerce. Si vous effectuez une mise à jour à partir d’une ancienne version de Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Paramètres de stock pour les pages de liste de produits** – Ce paramètre définit la manière dont les produits en rupture de stock sont affichés dans les listes de produits affichées par les modules de collecte de produits et de résultats de recherche. Les valeurs disponibles sont **Afficher dans l’ordre avec les autres produits**, **Masquer les produits en rupture de stock de la liste** et **Afficher les produits en rupture de stock en fin de liste**. Pour utiliser ce paramètre, vous devez d’abord configurer certains paramètres prérequis dans Commerce Headquarters. Pour plus d’informations, voir [Liste des produits tenant compte du stock](inventory-aware-product-listing.md).

    > [!IMPORTANT] 
    > Le paramètre **Paramètres de stock pour les pages de liste de produits** est disponible à partir de la version 10.0.20 de Commerce. Si vous effectuez une mise à jour à partir d’une ancienne version de Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Plages de stock** – Ce paramètre définit les messages de plages de stock affichés sur les modules du site. Il est applicable uniquement si la valeur **Total disponible** ou la valeur **Disponible physique** est sélectionnée pour le paramètre **Niveau de stock basé sur**. Les valeurs disponibles sont **Tout**, **Stock faible et rupture de stock** et **En rupture de stock**.

    - Quand **Tout** est sélectionné, les messages pour toutes les plages de stock, depuis en stock (message « Disponible ») jusqu’à rupture de stock (message « Épuisé »), seront affichés.
    - Quand **Stock faible et rupture de stock** est sélectionné, les messages pour toutes les plages de stock, sauf en stock (message « Disponible »), seront affichés.
    - Quand **En rupture de stock** est sélectionné, seul le message « Épuisé » sera affiché.

- **Seuil de rupture de stock** – Cet ancien paramètre numérique ne prendra effet que si la valeur **Seuil de rupture de stock** est sélectionnée pour le paramètre **Niveau de stock basé sur**.

> [!IMPORTANT] 
> Ces paramètres sont disponibles dans la version 10.0.12 de Dynamics 365 Commerce. Si vous effectuez une mise à jour à partir d’une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour obtenir des instructions de mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Modules qui utilisent les paramètres de stock

Les modules Zone d’achat, Liste de souhaits, Sélecteur de magasin, Panier et Icône de panier utilisent les paramètres de stock pour afficher les plages et les messages de stock.

Dans l’exemple de l’illustration suivante, un PDP affiche un message en stock (« Disponible »).

![Exemple d’un module PDP qui affiche un message en stock.](./media/pdp-InStock.png)

Dans l’exemple de l’illustration suivante, un PDP affiche un message « En rupture de stock ».

![Exemple d’un module PDP qui affiche un message de rupture de stock.](./media/pdp-outofstock.png)

Dans l’exemple de l’illustration suivante, un panier affiche un message en stock (« Disponible »).

![Exemple d’un module de panier qui affiche un message en stock.](./media/cart-instock.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Configurer des marges de stock et des niveaux de stock](inventory-buffers-levels.md)

[Module de panier](add-cart-module.md)

[Module de zone d’achat](add-buy-box.md)

[Pages et modules Gestion des comptes](account-management.md)

[Module Sélection de magasin](store-selector.md)

[Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
