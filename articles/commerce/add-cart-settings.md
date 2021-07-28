---
title: Appliquer les paramètres Ajouter un produit dans le panier
description: Cette rubrique couvre les paramètres « Ajouter le produit au panier » et décrit comment les appliquer à Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 55b81e7c644f884b052853206f312ac796031600
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479454"
---
# <a name="apply-add-product-to-cart-settings"></a>Appliquer les paramètres Ajouter un produit dans le panier

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique couvre les paramètres **Ajouter le produit au panier** et décrit comment les appliquer à Microsoft Dynamics 365 Commerce.

Différents workflows sont pris en charge lorsqu'un produit est ajouté au panier sur un site d'e-commerce Dynamics 365 Commerce. Par exemple, l'utilisateur du site peut être redirigé vers la page du panier. Alternativement, l'utilisateur peut rester sur la page actuelle mais recevoir une notification qui confirme que le produit a été ajouté au panier.

Pour prendre en charge les différents workflows, un champ **Ajouter le produit au panier** est disponible sur **Paramètres \> Extensions** dans le générateur de site Commerce. Sélectionnez l'une des options de configuration suivantes pour implémenter le workflow correspondant :

- **Accéder à la page du panier** : lorsque les utilisateurs ajoutent un article au panier, ils atteignent la page du panier.
- **Afficher la notification** : lorsque les utilisateurs ajoutent un article au panier, ils reçoivent une notification de confirmation et peuvent continuer à naviguer sur la page des détails du produit.
- **Afficher le mini-panier** : lorsque les utilisateurs ajoutent un article au panier, le contenu du mini-panier s'affiche. Les utilisateurs peuvent consulter tous les articles du panier et passer au paiement s'ils sont prêts.
- **Afficher la notification à l'aide du module de notifications** : lorsque les utilisateurs ajoutent un article au panier, le module de notifications est utilisé pour afficher une notification de confirmation. Pour que cette option de paramétrage fonctionne, le module de notifications doit être ajouté à l'en-tête de page.
- **Ne pas accéder à la page du panier** : lorsque les utilisateurs ajoutent un article au panier, ils restent sur la page actuelle.

L'illustration suivante montre un exemple d'option de paramètres **Ajouter le produit au panier** dans le générateur de site.

![Exemple d'options de configuration Ajouter un produit au panier dans le générateur de site](./media/AW_sitesettings.PNG)

> [!IMPORTANT]
> - Les paramètres de site **Ajouter un article au panier** sont disponibles depuis la version 10.0.11 de Dynamics 365 Commerce. Si vous effectuez une mise à jour à partir d’une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour obtenir des instructions sur la mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).
> - L'option de paramètre **Afficher le mini-panier** est disponible à partir de la version 10.0.20 de Dynamics 365 Commerce. Si vous effectuez une mise à jour à partir d’une ancienne version de Dynamics 365 Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour obtenir des instructions sur la mise à jour du fichier appsettings.json, consultez [Mise à jour du kit de développement logiciel et de la bibliothèque de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

L’image suivante montre un exemple de notification de confirmation « ajouté au panier » sur le site Fabrikam.

![Exemple de notification de confirmation « ajouté au panier » sur le site Fabrikam](./media/ecommerce-addtocart-notifications.PNG)

L’image suivante montre un exemple de notification de confirmation « ajouté au panier » sur le site Adventure Works.

![Exemple de notification de confirmation « ajouté au panier » sur le site Adventure Works](./media/AW_minicart.PNG)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module de zone d’achat](add-buy-box.md)

[Module Sélection de magasin](store-selector.md)
