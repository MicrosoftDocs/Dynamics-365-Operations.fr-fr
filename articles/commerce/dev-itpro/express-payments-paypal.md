---
title: Configurer les paiements express pour PayPal
description: Cet article décrit comment configurer les paiements express pour PayPal afin d'activer des fonctionnalités de paiement plus rapides dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: b69b7384992fb86370ff6881824a7d2c9a77d2c4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905280"
---
# <a name="configure-express-payments-for-paypal"></a>Configurer les paiements express pour PayPal

[!include [banner](../includes/banner.md)]

Cet article décrit comment configurer les paiements express pour PayPal afin d'activer des fonctionnalités de paiement plus rapides dans Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Termes clés

| Terme | Description |
|---|---|
| Portefeuille PayPal | L'expérience client et l'intégration prises en charge par le connecteur PayPal. Il est également connu sous le nom de bouton PayPal. |
| Portefeuille | Un type de paiement qui n'inclut pas les caractéristiques de paiement traditionnelles, telles que la plage de numéros d'identification bancaire (BIN) et la date d'expiration, qui sont utilisées pour différencier les types de cartes de crédit et de débit. |
| Paiement express | Un module Commerce qui prend en charge un comportement de paiement plus rapide lorsque des méthodes de paiement prises en charge sont utilisées. Cet article couvre l'utilisation du module de paiement express avec PayPal. |

Dynamics 365 Commerce offre une intégration prête à l'emploi pour PayPal Wallet. Lorsque Dynamics 365 Payment Connector pour PayPal est configuré, le bouton PayPal apparaît comme mode de paiement sélectionnable lors du paiement de la commande en ligne. Lorsque les utilisateurs sélectionnent PayPal, ils sont invités à effectuer leur paiement directement via PayPal, puis sont renvoyés à la vitrine en ligne pour terminer leur commande. Le paiement du panier PayPal permet aux clients d'utiliser les informations de leur compte de paiement pour pré-remplir le formulaire de paiement, afin qu'ils puissent terminer le processus de paiement plus rapidement.

Commerce a ajouté un module de paiement express pour faciliter les paiements express. Le module de paiement express peut être utilisé dans un fragment qui peut être inclus sur une page de paiement ou de panier. Lorsque PayPal est configuré, la même référence de connecteur Dynamics 365 Payment Connector pour PayPal est utilisée pour l'option de paiement express et l'option de paiement standard.

## <a name="paypal-checkout-in-commerce"></a>Paiement PayPal dans Commerce

### <a name="prerequisites"></a>Conditions préalables

Configurez le portefeuille PayPal pour votre environnement comme décrit dans [Dynamics 365 Payment Connector pour PayPal](../paypal.md).

Si vous utilisez PayPal comme option dans le processus de paiement standard (où les utilisateurs saisissent manuellement leurs informations de compte sans utiliser les actions de pré-remplissage express de paiement), suivez les instructions de configuration dans [Module de paiement](../payment-module.md).

### <a name="payment-express-module-with-paypal"></a>Module de paiement express avec PayPal

Le module de paiement express fonctionne avec les méthodes de paiement compatibles pour offrir aux clients du site la possibilité de payer plus rapidement en préremplissant les informations de leur compte de service de paiement lors du processus de paiement. Le module de paiement express utilise le connecteur de paiement configuré pour pré-remplir le formulaire de paiement avec les détails du compte utilisateur tels que l'adresse, les coordonnées et le mode de paiement sélectionné.

Lorsque le paiement express PayPal est utilisé et qu'un utilisateur sélectionne le bouton PayPal dans la section de paiement express de la page de paiement, une fenêtre iFrame de paiement PayPal est ouverte. L'utilisateur se connecte ensuite à son compte PayPal pour utiliser l'adresse de livraison, l'adresse de facturation, l'adresse e-mail et le mode de paiement PayPal de son choix pour payer la transaction.

Une fois que l'utilisateur a terminé l'action dans la fenêtre PayPal, il est redirigé vers la page de paiement du site Commerce, où le formulaire de paiement est pré-rempli avec les détails sélectionnés. Dans le flux de paiement express, la première option de livraison disponible pour l'adresse de livraison renvoyée sera préremplie pour l'utilisateur. L'utilisateur a alors la possibilité de revoir la commande et de modifier les détails de la commande avant de sélectionner **Passer la commande** pour finaliser la commande.

### <a name="add-the-payment-express-module-with-paypal-to-a-fragment"></a>Ajouter le module de paiement express avec PayPal à un fragment

Pour ajouter le module de paiement express avec PayPal à un fragment dans le générateur de site Commerce, procédez comme suit.

1. Accédez à votre site.
1. Dans le volet de navigation gauche, sélectionnez **Fragments**, puis sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Nouveau fragment**, recherchez et sélectionnez le module **Paiement express**, puis, sous **Nom du fragment**, entrez un nom pour le fragment (par exemple, **Paiement express**).
1. Cliquez sur **OK** pour créer le fragment.
1. Dans la vue d'ensemble, sélectionnez le slot du module de paiement express que vous avez créé.
1. Dans le volet des propriétés, sélectionnez **Titre**.
1. Dans la boîte de dialogue **Titre**, dans le champ **Texte d'en-tête**, saisissez le texte d'en-tête que vous souhaitez afficher pour la section Paiement express de votre site (par exemple, **Paiement express**).
1. En dessous de **Niveau de titre**, sélectionnez le niveau de titre (par exemple, **H2**).
1. Cliquez sur **OK**.
1. Dans le volet des propriétés, dans le champ **Hauteur de l'élément iFrame**, entrez ou ajustez la hauteur de l'élément iFrame (par exemple, **60**).
1. Dans le champ **Types d’appels d’offres pris en charge**, entrez **PayPal**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Ajouter le fragment de paiement express à la page de paiement

Pour ajouter le fragment de paiement express à la page de paiement dans le créateur de site, procédez comme suit.

1. Accédez à votre site.
1. Dans le volet de navigation de gauche, sélectionnez **Pages**, puis sélectionnez la page de paiement de votre site.
1. Sélectionnez **Modifier** pour modifier la page.
1. Dans l’emplacement **Principal**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.

    > [!NOTE]
    > Si un module de conteneur contenant un fragment de paiement existe déjà, déplacez la section de paiement express afin qu'elle apparaisse au-dessus du conteneur de paiement existant dans l'emplacement **Principal**. La section de paiement express sera alors affichée au-dessus du conteneur de paiement normal. Pour déplacer un module de conteneur vers le haut ou vers le bas, sélectionnez le bouton représentant des points de suspension (**...**) pour le module, puis sélectionnez **Déplacer vers le haut** ou **Déplacer vers le bas**.

1. Dans le volet des propriétés **Conteneur**, nous vous recommandons de configurer les paramètres de propriété de la manière suivante :

    - **Disposition du conteneur** - Sélectionnez **Empilé**.
    - **Largeur** - Sélectionnez **Remplir le conteneur**.
    - **Enfants affichés** - Sélectionnez **Trois**.

1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Sélectionner un fragment**, recherchez et sélectionnez le fragment de paiement express que vous avez créé au préalable, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Ajouter le fragment de paiement express à la page de panier

Pour ajouter le fragment de paiement express à la page de panier dans le créateur de site, procédez comme suit.

1. Accédez à votre site.
1. Dans le volet de navigation de gauche, sélectionnez **Pages**, puis sélectionnez la page de panier de votre site.
1. Sélectionnez **Modifier** pour modifier la page.
1. Dans l'emplacement **Principal**, trouvez le conteneur qui contient le module **Panier**. Le module **Panier** contiendra un emplacement **Paiement express**.
1. Sélectionnez l’emplacement **Paiement express**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le module **Paiement express**, puis sélectionnez **OK**.
1. Dans le volet de propriétés, dans le champ **Types d’offre pris en charge**, entrez **Paypal**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

### <a name="modes-of-delivery"></a>Modes de livraison

Lorsque le module de paiement express est configuré pour utiliser PayPal, la première option de livraison renvoyée pour l'adresse de livraison sélectionnée pour le compte PayPal sera préremplie. Les utilisateurs pourront modifier l'adresse de livraison s'ils le souhaitent.

L'ordre du mode de livraison est configuré dans la section **Modes de livraison** pour le canal dans Commerce Headquarters. Pour plus d’informations, voir [Paramétrer des modes de livraison](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Le module de paiement utilisera également le module d'options de livraison lorsque les modes de livraison sont rendus lors du paiement. Pour plus d’informations, voir [Module Options de livraison](../delivery-options-module.md).

Des modes de livraison sont ajoutés à la liste de la boutique en ligne de Commerce Headquarters. Accédez à **Vente au détail et commerce \> Canaux \> Magasins en ligne**, et sélectionnez l'ID de canal pour votre boutique. Sélectionnez ensuite **Configurer \> Modes de livraison**. Les modes de livraison des modules qui sont affichés dans la configuration apparaîtront de manière similaire sur le site. Pour ajouter ou supprimer des modes de livraison pour un canal de vente au détail ou un produit, sélectionnez **Gérer les modes de livraison** dans le volet Actions.

## <a name="additional-resources"></a>Ressources supplémentaires

[FAQ Paiements](payments-retail.md)

[Module Validation](../add-checkout-module.md)

[Module Paiement](../payment-module.md)

[Paramétrer des modes de livraison](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Module Options de livraison](../delivery-options-module.md)
