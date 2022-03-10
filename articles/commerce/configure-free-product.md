---
title: Configurer un produit à acheter gratuitement
description: Cette rubrique explique comment configurer un produit afin qu’il puisse être acheté gratuitement dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 760b97a895758073c8ffd1209be4a5f7df0f13a8
ms.sourcegitcommit: 9c2bc045eafc05b39ed1a6b601ccef48bd62ec55
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7919448"
---
# <a name="configure-a-product-to-be-purchased-for-free"></a>Configurer un produit à acheter gratuitement

[!include [banner](includes/banner.md)]


Cette rubrique explique comment configurer un produit afin qu’il puisse être acheté gratuitement dans Microsoft Dynamics 365 Commerce.

## <a name="configure-the-product"></a>Configurer le produit

Pour vendre un produit gratuitement dans Dynamics 365 Commerce, vous devez définir son prix sur 0 (zéro). De plus, vous devez configurer le paramètre **Prix zéro valide** du produit.

Pour configurer le paramètre **Prix zéro valide** dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Produits et catégories \> Produits lancés par catégorie**.
1. Accédez au produit que vous souhaitez vendre gratuitement. 
1. Dans la section **Commerce** de la page du produit, définissez l’option **Prix zéro valide** sur **Oui**.

L’illustration suivante montre un exemple de produit où l’option **Prix zéro valide** est définie sur **Oui**.

![Exemple d’un produit où l’option Prix zéro valide est définie sur Oui.](./media/Zero-price.png)

## <a name="configure-the-online-stores-functionality-profile"></a>Configurer le profil de fonctionnalité de la boutique en ligne

Avant que les transactions gratuites puissent être traitées, vous devez configurer le paramètre **Autoriser le paiement sans paiement** du profil de fonctionnalité de votre boutique en ligne afin que les transactions sans paiement soient autorisées. Pour plus d’informations sur la création de profils de fonctionnalités, voir [Créer un profil de fonctionnalité en ligne](online-functionality-profile.md).

Pour configurer le paramètre **Autoriser le paiement sans paiement** dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage du magasin en ligne**.
1. Sur la page du profil de fonctionnalité de votre boutique, sous **Paiement**, définissez l’option **Autoriser le paiement sans paiement** sur **Oui**.

L’illustration suivante montre un exemple de profil de boutique en ligne où l’option **Autoriser le paiement sans paiement** est définie sur **Oui**.

![Exemple de profil de boutique en ligne où l’option Autoriser le paiement sans paiement est définie sur Oui.](./media/Zero-price-profile.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Gestion des prix de vente au détail](price-management.md)

[Créer un profil de fonctionnalité en ligne](online-functionality-profile.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
