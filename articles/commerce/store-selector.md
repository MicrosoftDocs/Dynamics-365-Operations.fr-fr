---
title: Module Sélection de magasin
description: Cet article couvre le module de sélecteur de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
manager: annbe
ms.openlocfilehash: aa3aed837072cb6c3d4f7f92bec2f4b700408cf7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268324"
---
# <a name="store-selector-module"></a>Module Sélection de magasin

[!include [banner](includes/banner.md)]

Cet article couvre le module de sélecteur de magasins et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Les clients peuvent utiliser le module de sélection de magasin pour récupérer un produit dans un magasin sélectionné après un achat en ligne. Dans Commerce version 10.0.13, le module de sélection de magasin inclut également des fonctionnalités supplémentaires qui peuvent présenter une page **Rechercher un magasin** qui montre les magasins à proximité.

Le module de sélection de magasin permet aux utilisateurs d’entrer un lieu (ville, État, adresse, etc.) pour rechercher des magasins dans un rayon de recherche. Lorsque le module est ouvert pour la première fois, il utilise le lieu du navigateur du client pour trouver des magasins (si le consentement est fourni).

## <a name="store-selector-module-usage"></a>Utilisation du module Sélection de magasin

- Un module de sélection de magasin peut être utilisé sur une page de détails de produit pour sélectionner un magasin à retirer.
- Un module de sélection de magasin peut être utilisé sur une page de panier pour sélectionner un magasin de retrait.
- Un module de sélection de magasin peut être utilisé sur une page autonome qui affiche tous les magasins disponibles.

## <a name="fulfillment-group-setup-in-commerce-headquarters"></a>Configuration des groupes d’exécution dans Commerce Headquarters

Pour que le sélecteur de magasin affiche les magasins disponibles, le groupe d’exécution doit être configuré dans Commerce Headquarters. Pour plus d’informations, voir [Paramétrer les groupes d’exécution](customer-orders-overview.md#set-up-fulfillment-groups).

En outre, pour chaque magasin du groupe d’exécution, la latitude et la longitude de l’emplacement du magasin doivent être définies dans Commerce Headquarters.

Pour entrer les valeurs de longitude et de la latitude pour un emplacement de magasin dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Gestion des stocks \> Paramétrage \> Décomposition du stock**.
1. Sélectionnez l’emplacement de l’entrepôt dans le volet de gauche.
1. Dans le raccourci **Adresses**, sélectionnez **Avancé**.

    ![Exemple de détails d’un magasin dans Commerce Headquarters.](./media/Store-address.png)

1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans le raccourci **Général**, entrez des valeurs pour la **Latitude** et la **Longitude**.

    ![Exemple de configuration de latitude et de longitude pour un magasin dans Commerce Headquarters.](./media/Store-latitude-longitude.png)

1. Dans le volet Actions, sélectionnez **Enregistrer**. 

### <a name="hide-a-store-from-the-store-selector-module"></a>Masquer un magasin du module de sélection de magasin

Certains magasins d’un groupe de distribution peuvent ne pas être des lieux de retrait valides. Pour vous assurer que seuls les emplacements de retrait valides apparaissent comme options dans le module de sélection de magasin, suivez ces étapes dans Commerce Headquarters.

1. Accédez à **Retail et Commerce \> Paramétrage de Commerce \> Groupes d’exécution \> Tous les magasins**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Sous **Installer**, pour chaque magasin qui n’est pas un lieu de retrait valide, décochez la case **Est un emplacement de prélèvement**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Exécutez le programme de distribution 1070 **Configuration du canal**.

## <a name="bing-maps-integration"></a>Intégration Bing Cartes

Le module de sélection de magasin est intégré aux [interfaces de programmation d’application (API) REST Bing Cartes](/bingmaps/rest-services/) pour utiliser les fonctionnalités de géocodage et de suggestion automatique de Bing. Une clé API Bing Cartes est requise et doit être ajoutée à la page des paramètres partagés dans les sièges Commerce. L’API de géocodage est utilisée pour convertir un emplacement en valeurs de latitude et de longitude. L’intégration avec l’API de Suggestion automatique est utilisée pour afficher des suggestions de recherche lorsque les utilisateurs saisissent des lieux dans le champ de recherche.

Pour l’API REST de Suggestion automatique, vous devez vous assurer que les URL suivantes sont autorisées (également appelées « URL sur liste verte ») conformément à la stratégie de sécurité du contenu (CSP) de votre site. Ce paramétrage est effectué dans le générateur de site Commerce, en ajoutant des URL autorisées à différentes instructions CSP pour le site (par exemple, **img-src**). Pour plus d’informations, voir [Stratégie de sécurité du contenu](manage-csp.md). 

- À la directive **connect-src**, ajoutez **&#42;.bing.com**.
- À la directive **img-src**, ajoutez **&#42;.virtualearth.net**.
- Dans l’instruction **script-src**, **ajoutez &#42;.bing.com, &#42;.virtualearth.net**.
- Dans l’instruction **script style-src**, ajoutez **&#42;.bing.com**.

## <a name="pickup-in-store-mode"></a>Mode Retrait en magasin

Le module de sélection de magasin prend en charge un mode **Retrait en magasin** qui affiche une liste de magasins où un produit est disponible pour le retrait. Il affiche également les heures d’ouverture du magasin et l’inventaire des produits pour chaque magasin de la liste. Le module de sélection de magasin nécessite le contexte d’un produit pour rendre la disponibilité du produit et permettre à l’utilisateur d’ajouter le produit au panier, si le mode de livraison du produit est défini sur **retrait** dans le magasin sélectionné. Pour plus d’informations, voir [Paramètres de stock](inventory-settings.md). 

Le module du sélecteur de magasins peut être ajouté à un module de zone d’achat sur la page de détails du produit pour afficher les magasins où un produit est disponible pour retrait. Il peut également être ajouté à un module de panier. Dans ce cas, le module de sélection de magasin affiche les options de retrait pour chaque article du panier. Le module de sélecteur de magasin peut également être ajouté à d’autres pages ou modules via des extensions et des personnalisations.

Pour que ce scénario fonctionne, les produits doivent être configurés de sorte que le mode de livraison **retrait** soit utilisé. Sinon, le module ne sera pas affiché sur les pages de produit. Pour plus d’informations sur la configuration du mode de livraison, consultez [Configurer les modes de livraison](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

L’image suivante montre un exemple de module du sélecteur de magasins utilisé sur un PDP.

![Exemple d’un module du sélecteur de magasins utilisé sur un PDP.](./media/BOPIS.PNG)

> [!NOTE]
> Dans la version 10.0.16 et ultérieure, une nouvelle fonctionnalité peut être activée qui permet à une organisation de définir plusieurs modes de ramassage d’options de livraison pour les clients.  Si cette fonctionnalité est activée, le sélecteur de magasin et d’autres modules d’e-commerce seront améliorés pour permettre à l’acheteur de choisir parmi plusieurs options de livraison de ramassage potentielles si elles sont configurées.  Pour en savoir plus sur cette fonctionnalité, reportez-vous à [cette documentation](./multiple-pickup-modes.md). 

## <a name="find-stores-mode"></a>Mode Recherche de magasins

Le module de sélection de magasin prend également en charge un mode **Recherche de magasins**. Ce mode peut être utilisé pour créer une page d’emplacements de magasins qui affiche les magasins disponibles et leurs informations. Dans ce mode, le module de sélection de magasin fonctionne sans contexte de produit et peut être utilisé comme module autonome sur n’importe quelle page du site. De plus, si les paramètres pertinents sont activés pour le module, les utilisateurs peuvent sélectionner un magasin comme magasin préféré. Lorsqu’un magasin est sélectionné comme magasin préféré de l’utilisateur, l’ID de magasin est conservé dans le cookie du navigateur. Par conséquent, l’utilisateur doit accepter un message de consentement aux cookies.

L’illustration suivante montre un exemple de module de sélection de magasin utilisé avec un module de carte sur une page d’emplacements de magasin.

![Exemple d’un module de sélection de magasin et d’un module de carte sur une page d’emplacements de magasin.](./media/ecommerce-Storelocator.PNG)

## <a name="render-a-map"></a>Afficher une carte

Le module de sélection de magasin peut être utilisé avec le module de carte pour afficher les emplacements des magasins sur une carte. Pour plus d’informations sur le module de carte, voir [Module Carte](map-module.md)

## <a name="store-selector-module-properties"></a>Propriétés du module de sélecteur de magasins

| Nom de la propriété | Valeur | Description |
|---------------|-------|-------------|
| Titre | Détails | En-tête du module. |
| Mode | **Rechercher des magasins** ou **Retrait en magasin** | Le mode **Rechercher des magasins** affiche les magasins disponibles. Le mode **Retrait en magasin** permet aux utilisateurs de sélectionner un magasin pour le retrait. |
| Style | **Boîte de dialogue** ou **En ligne** | Le module peut être affiche en ligne ou dans une boîte de dialogue. |
| Définir comme store favori | **Vrai** ou **Faux** | Lorsque cette propriété est définie sur **True**, les utilisateurs peuvent définir un magasin préféré. Cette fonctionnalité nécessite que les utilisateurs acceptent un message de consentement aux cookies. |
| Afficher tous les magasins | **Vrai** ou **Faux** | Lorsque cette propriété est définie sur **True**, les utilisateurs peuvent contourner la propriété **Rayon de recherche** et voir tous les magasins. |
| Options de suggestion automatique : Résultats maximum | Nombre | Cette propriété définit le nombre maximal de résultats de suggestion automatique pouvant être affichés via l’API de suggestion automatique de Bing. |
| Rayon de recherche | Nombre | Cette propriété définit le rayon de recherche des magasins, en kilomètres. Si aucune valeur n’est spécifiée, le rayon de recherche par défaut, 50 kilomètres, est utilisé. |
| Conditions d’utilisation du service | URL |  Cette propriété spécifie l’URL des conditions d’utilisation de service requises pour utiliser le service Bing Cartes. |

## <a name="site-settings"></a>Paramètres du site

Le module sélecteur de magasin respecte les [Paramètres Ajouter un produit au panier](add-cart-settings.md). Une fois qu’un article a été ajouté au panier à partir du module de sélection de magasin, les utilisateurs du site voient les flux de travail configurés appropriés.

## <a name="add-a-store-selector-module-to-a-page"></a>Ajouter un module de sélecteur de magasins à une page

Pour le mode **Retrait en magasin**, le module ne peut être utilisé que sur les page de détails de produit et les pages de panier. Vous devez régler le mode sur **Retrait en magasin** dans le volet des propriétés du module.

- Pour plus d’informations sur l’ajout d’un module de sélecteur de magasins à un module de zone d’achat, consultez [Module de zone d’achat](add-buy-box.md). 
- Pour plus d’informations sur l’ajout d’un module de sélecteur de magasins à un module de panier, consultez [Module de panier](add-cart-module.md).

Pour configurer le module de sélection de magasin afin d’afficher les magasins disponibles pour une page d’emplacements de magasin, comme dans l’illustration qui apparaît plus haut dans cet article, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle marketing**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Créer une page**, sous **Nom de la page**, entrez **Emplacements magasin**, puis cliquez sur **Suivant**.
1. Sous **Choisir un modèle**, sélectionnez le **Modèle marketing** que vous avez créé, puis sélectionnez **Suivant**.
1. Sous **Choisir une mise en page**, sélectionnez une mise en page (par exemple, **Disposition flexible**), puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**. 
1. Dans l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur avec 2 colonnes**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module, définissez la valeur **Largeur** sur **Remplir le conteneur**.
1. Définissez la valeur de **Configuration de port d’affichage extra-petit** sur **100 %%**.
1. Définissez la valeur de **Configuration de port d’affichage petit** sur **100 %%**.
1. Définissez la valeur de **Configuration de port d’affichage moyen** sur **33 %% 67 %%**.
1. Définissez la valeur de **Configuration de port d’affichage grand** sur **33 %% 67 %%**.
1. Dans l’emplacement **Conteneur avec 2 colonnes**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Sélecteur de magasin**, puis cliquez sur **OK**.
1. Dans le volet des propriétés du module, définissez la valeur **Mode** sur **Recherche de magasins**.
1. Définissez la valeur du **Rayon de recherche** en miles.
1. Définissez d’autres propriétés, telles que **Définir comme magasin préféré**, **Afficher tous les magasins** et **Activer la suggestion automatique**, comme vous le souhaitez.
1. Dans l’emplacement **Conteneur avec 2 colonnes**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le module **Plan**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module, définissez les propriétés supplémentaires selon vos besoins.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.
 
## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Zone d’achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Visite rapide de PDP](quick-tour-pdp.md)

[Visite rapide du panier et du paiement](quick-tour-cart-checkout.md)

[Paramétrer des modes de livraison](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Gérer les Bing Cartes pour votre organisation](dev-itpro/manage-bing-maps.md)

[API REST Bing Cartes](/bingmaps/rest-services/)

[Module Cartes](map-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
