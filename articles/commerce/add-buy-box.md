---
title: Module de zone d’achat
description: Cet article couvre les modules de zone d’achat et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 7a3dfa347aac7b1ee7b318761c873beef8322bd9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270507"
---
# <a name="buy-box-module"></a>Module de zone d’achat

[!include [banner](includes/banner.md)]

Cet article couvre les modules de zone d’achat et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Le terme *zone d’achat* désigne généralement la zone d’une page de détails de produit « au-dessus du volet », et qui héberge toutes les principales informations requises pour effectuer un achat de produit. (Une zone qui est « au-dessus du volet » n’est visible que si la page est d’abord chargée, afin que les utilisateurs n’aient pas à faire défiler l’écran pour la voir.)

Un module Zone d’achat est un conteneur spécial utilisé pour héberger tous les modules qui sont affichés dans la zone de la zone d’achat d’une page de détails des produits.

L’URL d’une page de détails de produit inclut l’ID produit. Toutes les informations requises pour afficher un module de zone d’achat sont dérivées de cet ID produit. Si aucun ID produit n’est fourni, le module de zone d’achat ne s’affiche pas correctement sur une page. Par conséquent, un module de zone d’achat ne peut être utilisé que sur des pages qui ont un contexte de produit. Pour l’utiliser sur une page qui n’a pas de contexte de produit (par exemple, une page d’accueil ou une page marketing), vous devez effectuer des personnalisations supplémentaires.

L’image suivante montre un exemple de module de zone d’achat dans une page de détails d’un produit.

![Exemple d’un module de zone d’achat.](./media/ecommerce-pdp-buybox.PNG)

## <a name="buy-box-module-properties-and-slots"></a>Propriétés et emplacements des modules de zone d’achat 

Dans une page de détails des produits, une zone d’achat est divisée en deux espaces : un espace multimédia à gauche et un espace de contenu à droite. Par défaut, le rapport entre la largeur de la colonne de l’espace multimédia et la largeur de la colonne de l’espace de contenu est de 2:1. Sur les appareils mobiles, les deux espaces sont empilés, afin que les espaces apparaissent l’un en dessous de l’autre. Les thèmes peuvent être utilisés pour personnaliser les largeurs des colonnes et le rang d’empilement.

Un module de zone d’achat affiche le titre, la description, le prix et les notes d’un produit. Il permet également aux clients de sélectionner des variantes de produit ayant des attributs de produit différents, tels que la taille, le style et la couleur. Lorsqu’une variante de produit est sélectionnée, d’autres propriétés de la zone d’achat (par exemple, la description du produit et ses images) sont mises à jour pour refléter les informations variables. 

Un sélecteur de quantité est fourni, afin que les clients puissent spécifier la quantité d’articles à acheter. La quantité maximale pouvant être achetée peut être définie dans les paramètres du site.

À partir de la zone d’achat, les clients peuvent également effectuer des actions telles que l’ajout d’un produit au panier, l’ajout d’un produit à leur liste de souhaits et la sélection d’un lieu de prélèvement. Ces actions peuvent être effectuées sur un produit ou une variante de produit. Pour ajouter un produit à une liste de souhaits, le client doit être connecté.

Les thèmes peuvent être utilisés pour supprimer ou modifier l’ordre des commandes d’action et des propriétés produit de zone d’achat. 

## <a name="module-properties"></a>Propriétés du module

- **Balise de titre** – Cette propriété définit la balise d’en-tête du titre du produit. Si la zone d’achat se trouve en haut de la page, cette propriété doit être définie sur **h1** pour répondre aux normes d’accessibilité. 

- **Activer les recommandations « Acheter des looks similaires »** – Cette propriété permet à la zone d’achat d’afficher des liens vers des produits qui ressemblent à l’article actuellement consulté. Cette fonctionnalité est disponible dans Commerce version 10.0.13 et ultérieure.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Modules qui peuvent être utilisés dans un module de zone d’achat

- **Galerie multimédia** – Ce module permet de présenter des images d’un produit sur une page de détails des produits. Pour plus d’informations sur ce module, voir [Module Galerie multimédia](media-gallery-module.md).
- **Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement. Il permet aux utilisateurs d’entrer un emplacement pour trouver des magasins à proximité. Pour plus d’informations sur ce module, voir [Module du sélecteur de magasins](store-selector.md).
- **Partage social** – Ce module peut être ajouté à la zone d’achat pour permettre aux utilisateurs de partager des informations sur les produits sur les réseaux sociaux. Pour plus d’informations, voir [Module Partage social](social-share-module.md).

## <a name="buy-box-module-settings"></a>Paramètres du module Zone d’achat

Les paramètres de module de zone d’achat suivants peuvent être configurés sur **Paramètres du site \> Extensions** :

- **Limite de quantité de lignes du panier** – Cette propriété est utilisée pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier. Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.
- **Stock** – Pour plus d’informations sur l’application des paramètres de stock, voir [Appliquer les paramètres de stock](inventory-settings.md).
- **Ajouter le produit au panier** – Pour savoir comment postuler **Ajouter le produit au panier** paramètres, voir [Paramètres Ajouter un produit aux paramètres](add-cart-settings.md).

## <a name="buy-box-module-definition-extensions-in-the-adventure-works-theme"></a>Extensions de définition de module de zone d’achat dans le thème Adventure Works

Le module de zone d’achat fourni par le thème Adventure Works possède une extension de définition de module qui prend en charge l’implémentation d’un module de spécifications de produit dans un module d’accordéon dans une zone d’achat PDP. Pour présenter les attributs de spécification de produit dans une zone d’achat PDP, ajoutez un module de spécification de produit à l’emplacement du module d’accordéon à l’emplacement de la zone d’achat.


> [!IMPORTANT]
> Le thème Adventure Works est disponible à partir de la version 10.0.20 de Dynamics 365 Commerce.


## <a name="commerce-scale-unit-interaction"></a>Interaction avec Commerce Scale Unit

Le module de zone d’achat extrait les informations sur le produit à l’aide des API (Application Programming Interfaces) de Commerce Scale Unit. L’ID produit de la page de détails de produit est utilisée pour récupérer toutes les informations.

## <a name="add-a-buy-box-module-to-a-page"></a>Ajouter un module de zone d’achat à une page

Pour ajouter un module de zone d’achat à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Zone d’achat**.
1. Sous **Nom du fragment**, entrez le nom **Fragment de zone d’achat**, puis sélectionnez **OK**.
1. Dans l’emplacement **Galerie de supports** qui contient le module de zone d’achat, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Galerie de supports**, puis cliquez sur **OK**.
1. Dans l’emplacement **Sélecteur de magasin** qui contient le module de zone d’achat, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Sélecteur de magasin**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.
1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle PDP**, puis cliquez sur **OK**.
1. Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Page par défaut**, puis cliquez sur **OK**.
1. À l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Sélectionner un fragment**, sélectionnez le fragment **Fragment de zone d’achat** que vous avez créé, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Créer une page**, sous **Nom de la page**, entrez **Page PDP**, puis cliquez sur **Suivant**.
1. Sous **Choisir un modèle**, sélectionnez **Modèle PDP**, puis sélectionnez **Suivant**.
1. Sous **Choisir une mise en page**, sélectionnez une mise en page (par exemple, **Disposition flexible**), puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**.
1. À l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Sélectionner un fragment**, sélectionnez le fragment **Fragment de zone d’achat** que vous avez créé, puis cliquez sur **OK**.
1. Enregistrez et affichez un aperçu de la page. Ajoutez le paramètre de chaîne de requête **?productid=&lt;product id&gt;** à l’URL de la page d’aperçu. Ainsi, le contexte de produit est utilisé pour charger et afficher la page d’aperçu.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier. Une zone d’achat doit figurer sur la page de détails des produits.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Sélection de magasin](store-selector.md)

[Module Galerie multimédia](media-gallery-module.md)

[Module Conteneur](add-container-module.md)

[Module Panier](add-cart-module.md)

[Module Validation](add-checkout-module.md)

[Module de confirmation de commande](order-confirmation-module.md)

[Module d’en-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)

[Module Partage social](social-share-module.md)

[Paramètres Ajouter un produit dans le panier](add-cart-settings.md)

[Calculer la disponibilité des stocks pour les canaux de vente au détail](calculated-inventory-retail-channels.md)

[Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
