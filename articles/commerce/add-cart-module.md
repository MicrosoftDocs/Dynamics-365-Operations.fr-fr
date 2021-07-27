---
title: Module Panier
description: Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 76d4bea9ad25494015a7bfeb324cb0e84dd024b7
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346850"
---
# <a name="cart-module"></a>Module Panier

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Un module de panier affiche les articles qui ont été ajoutés au panier avant que le client ne passe à la caisse. Le module montre également un résumé de la commande et permet au client d’appliquer ou de supprimer des codes promotionnels.

Le module de panier prend en charge la caisse connectée et la caisse d’invité. Il prend également en charge un lien **Revenir aux achats**. Vous pouvez configurer l’itinéraire pour ce lien sous **Paramètres du site \> Extensions \> Itinéraires**.

Le module de panier affiche les données selon l’ID du panier, qui est un cookie de navigateur disponible sur tout le site. 

L’image suivante montre un exemple de page de panier sur le site Fabrikam.

![Exemple de module de panier sur le site Fabrikam.](./media/cart2.PNG)

L’image suivante montre un exemple de page de panier sur le site Fabrikam. Dans cet exemple, des frais de traitement s’appliquent à un élément de ligne.

![Exemple de module de panier avec frais de traitement pour un élément de ligne.](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a>Propriétés et emplacements du module de panier

| Propriété | Valeurs | Description  |
|----------------|--------|-------------|
| Titre | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Un en-tête pour le panier, tel que « Panier d’achat » ou « Articles dans votre panier ». |
| Afficher les erreurs de rupture de stock | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, la page du panier affichera les erreurs liées au stock. Nous vous recommandons de définir cette propriété sur **True** si des contrôles de stock sont appliqués sur le site. |
| Afficher les frais d’expédition pour les lignes | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, les articles de ligne de panier afficheront les frais d’expédition, si ces informations sont disponibles. Cette fonctionnalité n’est pas prise en charge dans le thème Fabrikam, car les utilisateurs sélectionnent la livraison uniquement dans le processus de paiement. Cependant, cette fonctionnalité peut être activée dans d’autres workflows si elle est applicable. |
| Afficher les promotions disponibles| **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, le panier affiche les promotions disponibles, en fonction des articles du panier. Cette fonctionnalité est disponible dans Dynamics 365 Commerce version 10.0.16. |

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Modules qui peuvent être utilisés dans un module de panier

- **Bloc de texte** – Ce module prend en charge la messagerie personnalisée dans le module de panier. Les messages sont pilotés par le système de gestion de contenu (CMS). Tous les messages peuvent être ajoutés, tels que « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ».
- **Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement. Il permet aux utilisateurs d’entrer un emplacement pour trouver des magasins à proximité. Pour plus d’informations sur ce module, voir [Module du sélecteur de magasins](store-selector.md).

## <a name="module-properties"></a>Propriétés du module

Les paramètres de module de panier suivants peuvent être configurés sur **Paramètres du site \> Extensions** :

- **Quantité maximale** – Cette propriété est utilisé pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier. Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.
- **Stock** – Pour plus d’informations sur l’application des paramètres de stock, voir [Appliquer les paramètres de stock](inventory-settings.md).
- **Revenir aux achats** - Cette propriété est utilisée pour spécifier l’itinéraire pour le lien **Revenir aux achats**. L’itinéraire peut être configuré au niveau du site, permettant aux détaillants de ramener le client à la page d’accueil ou vers toute autre page du site.

> [!IMPORTANT]
> Dans Dynamics 365 Commerce version 10.0.14 et versions ultérieures, les articles du panier sont agrégés en fonction des paramètres définis dans le profil de fonctionnalité en ligne de la boutique en ligne dans Commerce Headquarters. Pour plus d’informations sur la création d’un profil de fonctionnalité en ligne et la définition des propriétés requises pour l’agrégation, voir [Créer un profil de fonctionnalité en ligne](online-functionality-profile.md).

## <a name="commerce-scale-unit-interaction"></a>Interaction avec Commerce Scale Unit

Le module de panier extrait les informations sur le produit à l’aide des API d’unité d’échelle commerciale. L’ID panier du cookie du navigateur permet de récupérer toutes les informations sur le produit auprès de l’unité d’échelle commerciale.

## <a name="add-a-cart-module-to-a-page"></a>Ajouter un module de panier à une page

Pour ajouter un module de panier à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Panier**.
1. Sous **Nom du fragment**, entrez le nom **Fragment de panier**, puis sélectionnez **OK**.
1. Sélectionnez l’emplacement **Panier**.
1. Dans le volet des propriétés à droite, sélectionnez le symbole du crayon, entrez le texte de l’en-tête dans le champ, puis sélectionnez le symbole de coche.
1. Dans l’emplacement **Panier**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Sélecteur de magasin**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.
1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le nouveau modèle.
1. Dans l’arborescence de contour, sélectionnez l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Sélectionner un fragment**, sélectionnez le fragment **Panier**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle que vous avez créé, entrez un nom de page, puis sélectionnez **OK**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Icône de panier](cart-icon-module.md)

[Module Validation](add-checkout-module.md)

[Module Paiement](payment-module.md)

[Module Adresse d’expédition](ship-address-module.md)

[Module Options de livraison](delivery-options-module.md)

[Module d’information sur le retrait](pickup-info-module.md)

[Module Détails de la commande](order-confirmation-module.md)

[Module Carte cadeau](add-giftcard.md)

[Calculer la disponibilité des stocks pour les canaux de vente au détail](calculated-inventory-retail-channels.md)

[Créer un profil de fonctionnalité en ligne](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]