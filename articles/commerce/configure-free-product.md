---
title: Configurer un produit à acheter gratuitement
description: Cet article explique comment configurer un produit afin qu’il puisse être acheté gratuitement dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
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
ms.openlocfilehash: 88370085de047a5e0be773dde218770cfa242d14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280362"
---
# <a name="configure-a-product-to-be-purchased-for-free"></a>Configurer un produit à acheter gratuitement

[!include [banner](includes/banner.md)]


Cet article explique comment configurer un produit afin qu’il puisse être acheté gratuitement dans Microsoft Dynamics 365 Commerce.

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
