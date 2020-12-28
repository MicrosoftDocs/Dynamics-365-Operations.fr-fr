---
title: Module Confirmation de commande
description: Cette rubrique couvre les modules de confirmation de commande et décrit leur utilisation dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bf33ebf9c0c5136f40fcd7e1012988d186c4169b
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2020
ms.locfileid: "4412431"
---
# <a name="order-confirmation-module"></a>Module de confirmation de commande

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de confirmation de commande et décrit leur utilisation dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Le module de confirmation de la commande permet d’afficher les détails de confirmation de commande une fois la commande passée. Il indique l’ID de confirmation de la commande, les coordonnées de contact de la commande et d’autres détails de commande comme les articles achetés, les informations de paiement, les options de retrait et le mode d’expédition.

## <a name="order-confirmation-module-properties"></a>Propriétés du module de confirmation de commande

| Nom de la propriété  | Valeurs | Description |
|----------------|--------|-------------|
| En-tête        | Texte d'en-tête et balise d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Le module de confirmation de commande peut avoir un en-tête. Par défaut, la balise d'en-tête **H2** sert pour l'en-tête. Toutefois, la balise peut être modifiée pour satisfaire aux exigences d’accessibilité. |
| Numéro du contact | Texte | Un numéro de contact peut être fourni pour les questions liées à la commande. |
| Afficher les informations sur le créneau horaire de retrait | Vrai ou Faux | Cette propriété est disponible dans Dynamics 365 Commerce 10.0.15 et plus. Lorsqu'elle est vraie, elle affiche les informations sur la plage horaire de retrait si elles sont fournies pour un article de retrait|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a>Modules pouvant être utilisés dans une page de confirmation de la commande

Lorsque vous créez une page de confirmation de la commande, vous pouvez ajouter d’autres modules pertinents au module de confirmation de la commande existant. Voici quelques exemples :

- **Module de recommandations** : il peut être ajouté à la page de confirmation de la commande pour suggérer d’autres produits au client.
- **Modules de marketing** : tout module de marketing peut être ajouté à la page de confirmation de la commande pour afficher le contenu marketing.

## <a name="add-an-order-confirmation-module-to-a-page"></a>Ajouter un module confirmation de commande à une page

Pour ajouter un module de confirmation de commande à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le **modèle de confirmation de commande**, puis cliquez sur **OK**.
1. Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Page par défaut**, puis sélectionnez **OK**.
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Confirmation de commande**, puis sélectionnez **OK**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher le modèle. Le module de confirmation de commande ne sera pas affiché, car il nécessite le contexte du numéro de confirmation de commande.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle de confirmation de commande**. Sous **Nom de la page**, entrez **Page de confirmation de la commande**, puis sélectionnez **OK**.
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Confirmation de commande**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module de confirmation de commande, sélectionnez **En-tête** à côté du symbole du crayon.
1. Dans le champ **Texte d’en-tête** de la boîte de dialogue **Titre**, entrez le texte de l’en-tête **Confirmation de la commande**, puis sélectionnez **OK**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Panier](add-cart-module.md)

[Module Icône de panier](cart-icon-module.md)

[Module Validation](add-checkout-module.md)

[Module Paiement](payment-module.md)

[Module Adresse d’expédition](ship-address-module.md)

[Module Options de livraison](delivery-options-module.md)

[Module d'information sur le retrait](pickup-info-module.md)

[Module Carte cadeau](add-giftcard.md)
