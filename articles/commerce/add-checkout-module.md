---
title: Module Paiement
description: Cette rubrique décrit comment ajouter un module de caisse à une nouvelle page et définir les propriétés requises.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1d913fdc9ab9a3dbf7d5534fba38add7f942652a
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686740"
---
# <a name="checkout-module"></a>Module Paiement

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit comment ajouter un module de caisse à une nouvelle page et définir les propriétés requises.

## <a name="overview"></a>Vue d’ensemble

Module de validation est un conteneur spécial qui héberge tous les modules requis pour créer une commande. Il présente un flux pas-à-pas qu’un client utilise pour entrer toutes les informations appropriées pour faire un achat. Il capture l’adresse d’expédition, la méthode d’expédition et les informations de facturation. Il fournit également un résumé de commande et d’autres informations liées à une commande client.

Un module de caisse affiche des données sur l’ID panier. Cet ID panier est enregistré comme cookie du navigateur. Un ID panier est requis pour afficher les informations dans le module de caisse, tels que les articles dans la commande, le montant total, et des remises. 

L’image suivante montre un exemple de module de caisse Fabrikam dans une page de caisse.

![Exemple d’un module de caisse](./media/Checkout.PNG)

## <a name="checkout-module-properties"></a>Propriétés du module de paiement

Un module de paiement affiche un résumé de la commande et fournit la fonctionnalité pour passer une commande. Pour rassembler toutes les informations client requises avant de passer une commande, des modules supplémentaires doivent être ajoutés au module de validation. Par conséquent, les détaillants ont la possibilité d’ajouter des modules personnalisés au flux de validation ou d’exclure des modules en fonction de leurs besoins.

| Nom de la propriété | Valeurs | Description |
|----------------|--------|-------------|
| En-tête d’achat | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | En-tête pour le module de caisse. |
| En-tête de synthèse de commande | Texte d’en-tête | En-tête pour la section de récapitulatif de commande du module. |
| En-tête des éléments de ligne du panier | Texte d’en-tête | En-tête pour les éléments de ligne du panier qui sont affichés dans le module de paiement. |
| Afficher les frais d’expédition en ligne | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, les frais de livraison applicables aux articles de ligne seront affichés sur les lignes du panier. Si la fonctionnalité **Frais d’en-tête sans prorata** est activée au siège Commerce, les frais d’expédition seront appliqués au niveau de l’en-tête et non au niveau de la ligne. Cette fonctionnalité a été ajoutée dans la version 10.0.13 de Commerce. |

## <a name="modules-that-can-be-used-in-the-checkout-module"></a>Modules qui peuvent être utilisés dans un module de caisse

- **Adresse d’expédition** – Ce module permet à un client ajouter ou de sélectionner l’adresse d’expédition pour une commande. Pour plus d’informations sur ce module, voir [Module Adresse de livraison](ship-address-module.md).

    L’image suivante montre un exemple de module d’adresse de livraison dans une page de caisse.

    ![Exemple de module d’adresse de livraison](./media/ecommerce-shippingaddress.PNG)

- **Options de livraison** – Ce module permet à un client sélectionner un mode de livraison pour une commande. Pour plus d’informations sur ce module, voir [Module Options de livraison](delivery-options-module.md).

    L’image suivante montre un exemple de module d’options de livraison dans une page de caisse.
 
    ![Exemple d’un module d’options de livraison](./media/ecommerce-deliveryoptions.PNG)

- **Conteneur de section de caisse** – Ce module est un conteneur dans lequel vous pouvez mettre plusieurs modules pour créer une section dans le flux de caisse. Par exemple, vous pouvez mettre tous les modules liés au paiement à l’intérieur de ce conteneur pour les faire apparaître comme une section. Ce module n’affecte que la disposition du flux.

- **Carte cadeau** – Ce module permet à un client de payer une commande à l’aide d’une carte cadeau. Pour plus d’informations sur ce module, voir [Module Carte cadeau](add-giftcard.md).

- **Points de fidélité** – Ce module permet à un client payer une commande à l’aide de ses points de fidélité. Il fournit une synthèse des points disponibles et points arrivant à expiration, et permet au client de sélectionner un nombre de point à échanger. Si le client n’est pas connecté ou s’il n’est pas un membre du programme de fidélité, ou si le montant total dans le panier est de 0 (zéro), ce module est automatiquement masqué.

- **Paiement** – Ce module permet à un client de payer une commande à l’aide d’une carte de crédit ou de débit. Les clients peuvent également fournir une adresse de facturation pour l’option de paiement qu’ils sélectionnent. Pour plus d’informations sur ce module, voir [Module Paiement](payment-module.md).

    L’image suivante montre un exemple de modules de carte cadeau, de points de fidélité et de paiement sur une page de caisse.

    ![Exemple de modules de carte cadeau, de points de fidélité et de paiement sur une page de caisse](./media/ecommerce-payments.PNG)

- **Informations de contact** – Ce module permet à un client d’ajouter ou de modifier des informations de contact (adresse e-mail) pour une commande.

- **Bloc de texte** – Ce module contient tous les messages pilotés par le système de gestion de contenu (CMS). Par exemple, il peut contenir un message indiquant : « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ». 

- **Conditions générales de paiement** – Ce module affiche un texte enrichi qui contient les conditions générales et une case à cocher pour l’entrée du client. La case à cocher est facultative et configurable. L’entrée est capturée par le module et peut être utilisée comme contrôle avant le déclenchement de la commande, mais elle n’est pas incluse dans les informations récapitulatives de la commande. Ce module peut être ajouté au conteneur de paiement, au conteneur de section de paiement ou à l’emplacement des conditions générales, en fonction des besoins de l’entreprise. S’il est ajouté au conteneur de paiement ou à l’emplacement du conteneur de la section de paiement, il apparaîtra comme une étape du processus de paiement. S’il est ajouté à l’emplacement des conditions générales, il apparaîtra près du bouton de placement de commande.

    L’image suivante montre un exemple de module de conditions générales sur une page de caisse.

    ![Exemple de conditions générales sur une page de paiement](./media/ecommerce-checkout-terms.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interaction avec Commerce Scale Unit

La plupart des informations de paiement, telles que l’adresse d’expédition et le mode d’expédition, sont enregistrées dans le panier et traitées dans le cadre de la commande. La seule exception est les informations de carte de crédit. Ces informations sont traitées directement à l’aide du connecteur de paiement Adyen. Le paiement est autorisé, mais il n’est facturé que lorsque la commande est exécutée.

## <a name="add-a-checkout-module-to-a-page-and-set-the-required-properties"></a>Ajouter un module de caisse à une page et définir les propriétés requises

Pour ajouter un module de caisse à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.
1. Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez le module **Caisse**.
1. Sous **Nom du fragment de page**, entrez le nom **Fragment de caisse**, puis sélectionnez **OK**.
1. Sélectionnez l’emplacement **Module de caisse**.
1. Dans le volet des propriétés à droite, sélectionnez le symbole du crayon, entrez le texte de l’en-tête dans le champ, puis sélectionnez le symbole de coche.
1. Dans l’emplacement **Informations de caisse**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez les modules **Adresse de livraison**, **Options de livraison**, **Conteneur de section de caisse**, et **Informations de contact**, puis sélectionnez **OK**.
1. Dans le module **Conteneur de section de caisse**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez les modules **Carte-cadeau**, **Points de fidélité** et **Paiement**, puis sélectionnez **OK**. Ainsi, vous vous assurez que tous les modes de paiement s’affichent dans la section.
1. À l’emplacement **Conditions générales**, ajoutez un module **Conditions de paiement** si nécessaire. Dans le volet des propriétés du module, configurez le texte des conditions générales comme il convient.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu du fragment. Certains modules qui n’ont pas de contexte de panier peuvent ne pas s’afficher dans l’aperçu.
1. Sélectionnez **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.
1. Créez un modèle qui utilise le nouveau fragment de caisse.
1. Créez une page de caisse qui utilise le nouveau modèle.

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Panier](add-cart-module.md)

[Module Icône de panier](cart-icon-module.md)

[Module Paiement](payment-module.md)

[Module Adresse d’expédition](ship-address-module.md)

[Module Options de livraison](delivery-options-module.md)

[Module Détails de la commande](order-confirmation-module.md)

[Module Carte cadeau](add-giftcard.md)
