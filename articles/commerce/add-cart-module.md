---
title: Module Panier
description: Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 3ba46fd90507a9cf8da92598c8449a2e553da352
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411271"
---
# <a name="cart-module"></a>Module Panier

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de panier affiche les articles qui ont été ajoutés au panier avant que le client ne passe à la caisse. Le module montre également un résumé de la commande et permet au client d'appliquer ou de supprimer des codes promotionnels.

Le module de panier prend en charge la caisse connectée et la caisse d'invité. Il prend également en charge un lien **Revenir aux achats**. Vous pouvez configurer l'itinéraire pour ce lien sous **Paramètres du site \> Extensions \> Itinéraires**.

Le module de panier affiche les données selon l'ID du panier, qui est un cookie de navigateur disponible sur tout le site. 

L'image suivante montre un exemple de page de panier sur le site Fabrikam.

![Exemple d'un module de panier](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a>Propriétés et emplacements du module de panier

Le module panier a une propriété **En-tête** qui peut être définie sur des valeurs telles que **Panier d'achat** et **Articles dans votre panier**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Modules qui peuvent être utilisés dans un module de panier

- **Bloc de texte** – Ce module prend en charge la messagerie personnalisée dans le module de panier. Les messages sont pilotés par le système de gestion de contenu (CMS). Tous les messages peuvent être ajoutés, tels que « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ».
- **Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement. Il permet aux utilisateurs d'entrer un emplacement pour trouver des magasins à proximité. Pour plus d'informations sur ce module, voir [Module du sélecteur de magasins](store-selector.md).

## <a name="module-properties"></a>Propriétés du module

Les paramètres de module de panier suivants peuvent être configurés sur **Paramètres du site \> Extensions** :

- **Quantité maximale** – Cette propriété est utilisé pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier. Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.
- **Stock** – Pour plus d'informations sur l'application des paramètres de stock, voir [Appliquer les paramètres de stock](inventory-settings.md).
- **Revenir aux achats** - Cette propriété est utilisée pour spécifier l'itinéraire pour le lien **Revenir aux achats**. L'itinéraire peut être configuré au niveau du site, permettant aux détaillants de ramener le client à la page d'accueil ou vers toute autre page du site.

## <a name="commerce-scale-unit-interaction"></a>Interaction avec l'unité d'échelle commerciale

Le module de panier extrait les informations sur le produit à l'aide des API d'unité d'échelle commerciale. L'ID panier du cookie du navigateur permet de récupérer toutes les informations sur le produit auprès de l'unité d'échelle commerciale.

## <a name="add-a-cart-module-to-a-page"></a>Ajouter un module de panier à une page

Pour ajouter un module de panier à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Fragments de page**, puis cliquez sur **Nouveau** pour créer un fragment.
1. Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez le module **Panier**.
1. Sous **Nom du fragment de page**, entrez le nom **Fragment de panier**, puis sélectionnez **OK**.
1. Sélectionnez l'emplacement **Panier**.
1. Dans le volet des propriétés à droite, sélectionnez le symbole du crayon, entrez le texte de l'en-tête dans le champ, puis sélectionnez le symbole de coche.
1. Dans l'emplacement **Panier**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Sélecteur de magasin**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.
1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le nouveau modèle.
1. Dans l'arborescence de contour, sélectionnez l'emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Sélectionner un fragment de page**, sélectionnez le fragment **Panier**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle que vous avez créé, entrez un nom de page, puis sélectionnez **OK**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module de sélection de magasin](store-selector.md)

[Module de zone d'achat](add-buy-box.md)

[Module icône de panier](cart-icon-module.md)

[Module de validation](add-checkout-module.md)

[Module de confirmation de commande](order-confirmation-module.md)

[Module d'en-tête](author-header-module.md)

[Module de pied de page](author-footer-module.md)

[Calculer la disponibilité des stocks pour les canaux de vente au détail](calculated-inventory-retail-channels.md)
