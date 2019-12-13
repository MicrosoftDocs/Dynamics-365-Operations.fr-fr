---
title: Vue d'ensemble des pages de panier et de caisse
description: Cette rubrique fournit une vue d'ensemble des pages de caisse et de panier dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 347db3af36521e11dc70d5188dcc54b07efa1fbe
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697840"
---
# <a name="overview-of-cart-and-checkout-pages"></a>Vue d'ensemble des pages de panier et de caisse

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des pages de caisse et de panier dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

La page du panier d'un site web de commerce électronique affiche tous les articles qu'un client a ajoutés au panier. La page du panier est intégrée à l'aide du module de panier. Le module de panier est un conteneur qui héberge tous les modules nécessaires pour présenter les articles dans le panier. Le module de panier peut également utiliser d'autres modules pour afficher la synthèse de la commande et tous les codes promotionnels appliqués à la commande client.

La page de caisse d'un site web de commerce électronique présente un flux pas-à-pas que les clients suivent pour entrer toutes les informations requises pour passer une commande. Un module de caisse peut inclure les modules qui traitent l'adresse d'expédition, les méthodes d'expédition, les informations de facturation, le récapitulatif de commande, et d'autres informations liées à des commandes client.

## <a name="cart-page"></a>Page du panier

La page du panier sert de sac à provisions et inclut tous les articles ajoutés au panier.

L'illustration suivante affiche un exemple de page de panier qui a été générée à l'aide du kit de démarrage en ligne et le thème « Fabrikam ».

![Exemple d'une page de panier](./media/cart2.PNG)

Le corps principal de la page du panier affiche tous les articles que le client a ajoutés au panier. Toutes les remises applicables sont présentées. Ces remises incluent des remises complexes. Par exemple, elles comprennent des remises comme « Achetez-en 3 et obtenez 10 % de remise » ou « Achetez une bouteille et un sac à dos pour obtenir une remise de 10 % ». Le modules de synthèse de commande affiche le montant dû après que les remises, l'expédition, les taxes, etc., aient été appliquées. Il existe également un module de code promotionnel qui permet au client d'appliquer ou de supprimer des codes promotionnels.

Un client peut acheter de manière anonyme ou comme un utilisateur connecté. Si un client est connecté, les articles dans le panier sont conservés entre les sessions. Ainsi, le client peut continuer à effectuer des achats à partir de différents appareils.

Dans le panier, le client peut passer à la caisse. Un client peut initier la caisse comme utilisateur invité ou comme utilisateur connecté.

Pour plus d'informations sur la création d'une page de panier, voir [Ajout d'un module de panier à une page](add-cart-module.md).

## <a name="checkout-page"></a>Page de caisse

La page de caisse est celle où les clients entrent des informations requises pour passer une commande.

L'illustration suivante affiche un exemple de page de caisse qui a été générée à l'aide du kit de démarrage en ligne.

![Exemple d'une page de caisse](./media/Checkout.PNG)

Le corps principal de la page de caisse est là où toutes les informations de la commande sont collectées. Ces informations incluent l'adresse d'expédition, les options de livraison, et les informations de paiement. La caisse est un flux pas-à-pas, car les informations doivent être entrées dans un ordre spécifique pour être traitées. Par exemple, l'adresse d'expédition doit être entrée pour que les coûts d'expédition soient calculés et que le paiement puisse être autorisé.

### <a name="shipping-address"></a>Adresse d'expédition

Une adresse d'expédition est obligatoire si les articles doivent être expédiés. Le format des adresses d'expédition pour chaque paramètre régional peut être configuré dans Dynamics 365 Retail. Par exemple, si les articles sont expédiés aux États-Unis, l'adresse d'expédition doit inclure une adresse postale, un État, et le code postal. Une validation de la saisie de base est effectuée pour les champs d'adresse d'expédition, telle que le contrôle des caractères alphanumériques, de la longueur maximale, et des numéros. Bien que la validité de l'adresse elle-même ne soit pas vérifiée, cette vérification peut être effectuée à l'aide de services tiers personnalisés.

L'adresse de livraison est appliquée à tous les articles du panier pour lesquels l'option « expédier » est activée. Si vous utilisez le flux de caisse fourni dans le kit de démarrage en ligne, différents articles du panier ne peuvent pas être expédiés à certaines adresses. Si vous avez besoin de cette fonctionnalité, elle peut être mise en service via la personnalisation des modules de caisse.

Une fois l'adresse d'expédition fournie, les méthodes d'expédition qui sont disponibles dans le magasin en ligne Dynamics 365 Commerce sont affichées. Les méthodes d'expédition et les adresses qu'elles prennent en charge peuvent être configurées dans la vente au détail.

### <a name="payment"></a>Paiement

L'étape suivante du flux de caisse est le paiement. Dans le commerce électronique, plusieurs modes de paiement peuvent être utilisés pour passer commande, tels que des cartes de crédit, des cartes cadeaux, et des points de fidélité. Une combinaison de ces modes de paiement peut également être utilisée. Selon les modes de paiement utilisés, des informations supplémentaires peuvent être demandées. Par exemple, un paiement par carte de crédit nécessite une adresse de facturation. Les paiements par carte de crédit sont traités à l'aide du connecteur de paiement Adyen.

#### <a name="loyalty-points"></a>Points de fidélité

Au cours du flux de caisse, un client qui est membre d'un programme de fidélité et qui a accumulé des points de fidélité peut échanger ces points de fidélité lors d'une commande. Le module de points de fidélité est affiché uniquement si le client est un membre actuel d'un programme de fidélité. Pour les non membres et les utilisateurs invités, ce module est masqué.

#### <a name="gift-cards"></a>Cartes cadeaux

Le kit de démarrage en ligne permet d'échanger des cartes cadeaux pour une commande. Pour appliquer une carte cadeau interne, le client doit être connecté. Pour une sécurité supplémentaire, nous vous recommandons de personnaliser le flux à l'aide d'un code PIN pour les cartes cadeaux internes.

### <a name="signed-in-and-guest-users"></a>Utilisateurs connectés et invités

Le client peut terminer le processus de caisse comme utilisateur invité ou comme utilisateur connecté. Si le client se connecte, les informations de compte comme les adresses d'expédition enregistrées et les détails de carte de crédit enregistrés sont automatiquement récupérées.

### <a name="order-summary"></a>Synthèse de la commande

La caisse affiche une synthèse des articles de ligne dans le panier, afin que le client puisse vérifier la commande avant de la passer. Les articles de ligne ne peuvent pas être modifiés lors du flux de caisse. Toutefois, un lien vers le panier est fourni au cas où l'utilisateur veut retourner et modifier les articles de lignes.

Une fois que le client fournit les informations d'expédition et de facturation, le récapitulatif de commande reflète le montant dû après que les points de fidélité, les cartes cadeaux, et autres paiements ont été appliqués.

### <a name="order-confirmation-and-email"></a>E-mail et confirmation de commande

Lorsque le client passe une commande, un numéro de confirmation est fourni. À ce stade, le paiement a été autorisée mais pas facturé. Le paiement est facturé que lorsque l'ordre est honoré (c'est-à-dire, lorsqu'il est expédié ou prélevé).

Une fois qu'un ordre est créé, un e-mail de confirmation de commande est envoyé au client.

Pour plus d'informations sur la création d'une page de caisse, voir [Ajout d'un module de caisse à une page](add-checkout-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble de la page d'accueil](quick-tour-home-page.md)

[Vue d'ensemble de la page d'arrivée de la catégorie par défaut et de la page des résultats de la recherche](category-search-page-overview.md)

[Vue d'ensemble des pages de détails des produits](quick-tour-pdp.md)

[Vue d'ensemble des pages de gestion de compte](quick-tour-account-management.md)
