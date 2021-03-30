---
title: Définir des limites de quantité de produits pour les sites de commerce électronique B2B
description: Cette rubrique décrit comment définir des limites de quantité de produits pour les sites de commerce électronique B2B.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1208b968e476ccbc7a726facf1db896c7bf3c36f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211175"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a>Définir des limites de quantité de produits pour les sites de commerce électronique B2B

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment définir des limites de quantité de produits pour les sites de commerce électronique B2B.

La plupart des produits ont une unité de mesure qui définit leur regroupement. Le regroupement affecte la manière dont les produits peuvent être vendus. Certains produits peuvent avoir un regroupement supplémentaire pour les quantités. Ce regroupement détermine si les produits peuvent être vendus sous forme d'unités individuelles ou multiples, et s'il existe une limite de quantité de commande minimale ou maximale à respecter.

La fonctionnalité de limitation de quantité garantit que les quantités minimales, maximales, multiples et standard configurées dans Microsoft Dynamics 365 Commerce (dans les paramètres de commande par défaut ou dans les paramètres du site de création de site Commerce) sont appliqués aux commandes des clients passées sur un site d’e-commerce. Les limites de quantité de produits ne sont actuellement pas prises en charge pour le point de vente (PDV) et les centres d'appels.

De nombreux détaillants offrent la possibilité que les commandes client (également appelées commandes spéciales) répondent à diverses exigences de produit et de traitement. Voici quelques scénarios classiques :

- Un client souhaite que des variantes spécifiques de produits soient vendues par multiples.
- Un client souhaite prélever les produits dans un magasin ou un emplacement qui diffère du magasin ou de l’emplacement où il a acheté ces produits. Cependant, les normes d'emballage pour les magasins diffèrent de celles pour la distribution des ventes en ligne.
- Un client souhaite acheter un produit en édition limitée dont la quantité maximale pouvant être achetée est limitée.

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a>Activez la fonction des paramètres de commande par défaut dans Commerce Headquarters

Avant de pouvoir définir des limites de quantité de produits, la fonction des paramètres de commande par défaut doit être activée dans Commerce Headquarters.

Pour activer la fonction des paramètres de commande par défaut, procédez comme suit :

1. Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
1. Recherchez et sélectionnez la fonction **Prise en charge du site et des paramètres de commande par défaut dans la commande client**.
1. En bas du volet droit, sélectionnez **Activer maintenant**. 

## <a name="define-quantity-settings"></a>Définir des paramètres de quantité 

Vous pouvez définir les paramètres de quantité sur la page **Paramètres de commande par défaut**.

Pour définir les paramètres de quantité, procédez comme suit : 

1. Accédez à Produit **Retail et Commerce \> Produits et catégories \> Produits lancés par catégorie**.
1. Sélectionnez un produit lancé.
1. Dans le volet Actions, sur l’onglet **Gérer le stock**, dans le groupe **Paramètres de commande**, sélectionnez **Paramètres de commande par défaut**. 
1. Sur la page **Paramètres de commande par défaut**, sur le raccourci **Commande client**, dans la section **Quantité vendue**, définissez les quantités de produit vendues :

    - **Multiple** - Multiples dans lesquels le produit peut être acheté.
    - **Quantité minimale de commande** - Le nombre minimum de produits devant être achetés.
    - **Quantité maximale de commande** - Le nombre maximal de produits pouvant être achetés.
    - **Quantité de commande standard** - La quantité par défaut qui est automatiquement saisie lorsque le produit est sélectionné.

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a>Activer la fonctionnalité de limites de quantité de commande B2B dans le générateur de site Commerce

Pour activer la fonctionnalité de limites de quantité de commande B2B dans le générateur de site Commerce, procédez comme suit :

1. Accédez à **Paramètres du site \> Extensions**
1. Sous **Activer les limites de quantité de commande**, sélectionnez **Activé pour les clients B2B** dans le menu déroulant. 

> [!NOTE] 
> Les paramètres de création de site mis à jour ne prennent effet qu'après la mise à jour du fichier app.settings.json. Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un site d'e-commerce B2B](set-up-b2b-site.md)

[Créer des hiérarchies de modélisation organisationnelle pour les organisations B2B](org-model.md)

[Gérer les utilisateurs des partenaires commerciaux sur les sites e-commerce B2B](manage-b2b-users.md)

[Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]