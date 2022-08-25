---
title: Module de confirmation de commande
description: Cet article couvre les modules de confirmation de commande et décrit leur utilisation dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 6011c7e4713813a02fa8f812ea8981fd6fa0253f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269133"
---
# <a name="order-confirmation-module"></a>Module de confirmation de commande

[!include [banner](includes/banner.md)]

Cet article couvre les modules de confirmation de commande et décrit leur utilisation dans Microsoft Dynamics 365 Commerce.

Le module de confirmation de la commande permet d’afficher les détails de confirmation de commande une fois la commande passée. Il indique l’ID de confirmation de la commande, les coordonnées de contact de la commande et d’autres détails de commande comme les articles achetés, les informations de paiement, les options de retrait et le mode d’expédition.

## <a name="order-confirmation-module-properties"></a>Propriétés du module de confirmation de commande

| Nom de la propriété  | Valeurs | Description |
|----------------|--------|-------------|
| En-tête        | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Le module de confirmation de commande peut avoir un en-tête. Par défaut, la balise d’en-tête **H2** sert pour l’en-tête. Toutefois, la balise peut être modifiée pour satisfaire aux exigences d’accessibilité. |
| Numéro du contact | Texte | Un numéro de contact peut être fourni pour les questions liées à la commande. |
| Afficher les informations sur le créneau horaire de retrait | Vrai ou Faux | Cette propriété est disponible dans Dynamics 365 Commerce 10.0.15 et plus. Lorsqu’elle est vraie, elle affiche les informations sur la plage horaire de retrait si elles sont fournies pour un article de retrait|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a>Modules pouvant être utilisés dans une page de confirmation de la commande

Lorsque vous créez une page de confirmation de la commande, vous pouvez ajouter d’autres modules pertinents au module de confirmation de la commande existant. Voici quelques exemples :

- **Module de recommandations** : il peut être ajouté à la page de confirmation de la commande pour suggérer d’autres produits au client.
- **Modules de marketing** : tout module de marketing peut être ajouté à la page de confirmation de la commande pour afficher le contenu marketing.

## <a name="add-an-order-confirmation-module-to-a-page"></a>Ajouter un module confirmation de commande à une page

Pour ajouter un module de confirmation de commande à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le **modèle de confirmation de commande**, puis cliquez sur **OK**.
1. Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Page par défaut**, puis cliquez sur **OK**.
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Confirmation de commande**, puis sélectionnez **OK**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher le modèle. Le module de confirmation de commande ne sera pas affiché, car il nécessite le contexte du numéro de confirmation de commande.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Créer une page**, sous **Nom de la page**, entrez **Page de confirmation de la commande**, puis cliquez sur **Suivant**.
1. Sous **Choisir un modèle**, sélectionnez **Modèle de confirmation de commande**, puis sélectionnez **Suivant**.
1. Sous **Choisir une mise en page**, sélectionnez une mise en page (par exemple, **Disposition flexible**), puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**. 
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Confirmation de commande**, puis sélectionnez **OK**.
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

[Module d’information sur le retrait](pickup-info-module.md)

[Module Carte cadeau](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
