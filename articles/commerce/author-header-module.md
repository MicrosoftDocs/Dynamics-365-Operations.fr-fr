---
title: Module d’en-tête
description: Cette rubrique couvre les modules d’en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: afdc12230ebad3d5db59c384b2f1066d2c7929339f282ed4880ff967b1fd2d8b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712788"
---
# <a name="header-module"></a>Module En-tête

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules d’en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.

Dans Dynamics 365 Commerce, un en-tête de page est configuré comme un fragment de page qui comprend l’en-tête, la bannière promotionnelle et les modules de consentement aux cookies. 

Le module d’en-tête comprend un logo de site, des liens vers la hiérarchie de navigation, des liens vers d’autres pages du site, un module d’icone de panier, un symbole de liste de souhaits, des options de connexion et la barre de recherche. Un module d’en-tête est automatiquement optimisé pour l’appareil sur lequel le site est affiché (autrement dit, pour un périphérique de bureau ou un appareil mobile). Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).

L’image suivante montre un exemple de module d’en-tête sur une page d’accueil.

![Exemple d’un module d’en-tête.](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Propriétés d’un module d’en-tête

Un module d’en-tête prend en charge les propriétés suivantes : **Image de logo**, **Lien vers le logo** et **Liens de mon compte**. 

Les propriétés **Image de logo** et **Lien vers le logo** sont utilisées pour définir un logo sur la page. Pour plus d’informations, voir [Ajouter un logo](add-logo.md). 

La propriété **Liens de mon compte** peut être utilisée pour définir les pages de compte pour lesquelles le propriétaire du site souhaite afficher des liens rapides dans l’en-tête.

## <a name="modules-that-are-available-within-a-header-module"></a>Modules disponibles dans un module d’en-tête

Les modules suivants peuvent être utilisés dans un module d’en-tête :

- **Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d’autres liens de navigation statiques. Pour plus d’informations, voir [Module Menu de navigation](nav-menu-module.md).

- **Rechercher** – Le module de recherche permet aux utilisateurs d’entrer des critères de recherche pour des produits. L’URL de la page de recherche par défaut et les paramètres de la requête de recherche doivent être fournis à l’adresse **Paramètres du site \> Extensions**. Le module de recherche possède des propriétés qui vous permettent de supprimer l’étiquette ou le bouton de recherche selon vos besoins. Le module de recherche prend également en charge les options de suggestion automatique, telles que les résultats de recherche de produits, de mots clés et de catégories.

- **Icône de panier** - Le module d’icône de panier représente l’icône de panier, qui indique le nombre d’articles dans le panier à un moment donné. Pour plus d’informations, voir [Module Icône de panier](cart-icon-module.md).

- **Sélecteur de site** - Le module de sélecteur de site permet aux utilisateurs de parcourir différents sites prédéfinis, en fonction du marché, des régions et des paramètres régionaux. Pour plus d’informations, voir [Module Sélecteur de site](site-selector.md).

- **Sélecteur de magasin** - Le module de sélecteur de magasin peut être inclus dans l’emplacement de sélecteur de magasin d’un module d’en-tête. Il permet aux utilisateurs de parcourir et de trouver des magasins à proximité. Les utilisateurs peuvent également spécifier un magasin préféré. Ce magasin sera alors affiché dans l’en-tête. Lorsque le module de sélecteur de magasin est inclus dans le module d’en-tête, sa propriété **Mode** doit être définie sur **Rechercher des magasins**. Pour plus d’informations, voir [Module Sélecteur de magasin](store-selector.md).

> [!NOTE]
> - La prise en charge de l’utilisation du module d’icônes de panier dans les modules d’en-tête est disponible depuis Dynamics 365 Commerce Version 10.0.11.
> - La prise en charge de l’utilisation du module de sélecteur de sites dans les modules d’en-tête est disponible depuis Dynamics 365 Commerce Version 10.0.14.
> - La prise en charge de l’utilisation du module de sélecteur de magasins dans les modules d’en-tête est disponible depuis Dynamics 365 Commerce Version 10.0.15.

## <a name="header-module-in-the-adventure-works-theme"></a>Module d'en-tête dans le thème Adventure Works

Dans le thème Adventure Works, le module d'en-tête prend en charge la propriété **Mobile Logo**. Cette propriété permet de spécifier un logo pour les fenêtres mobiles. La propriété **Mobile Logo** est disponible en tant qu'extension de définition de module.

> [!IMPORTANT]
> Le thème Adventure Works est disponible à partir de la version 10.0.20 de Dynamics 365 Commerce.

## <a name="create-a-header-fragment-for-a-page"></a>Créer un fragment d’en-tête pour une page

Pour créer un fragment d’en-tête, procédez comme suit :

1. Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment, puis sélectionnez **OK**.
1. Sélectionnez l’emplacement **Conteneur par défaut** puis, dans le volet des propriétés de droite, définissez la propriété **Largeur** sur **Remplir l’écran**.
1. Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez les modules **Consentement aux cookies**, **En-tête** et **Bannière promotionnelle**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module **Bannière promotionnelle**, sélectionnez **Ajouter un message**, puis sélectionnez **Message**.
1. Dans la boîte de dialogue **Message**, ajoutez du texte et des liens pour le contenu promotionnel, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module **Consentement aux cookies**, ajoutez et configurez du texte et un lien vers la page de confidentialité du site.
1. Dans l’emplacement **Menu de navigation** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Menu de navigation**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module du menu de navigation, sous **Source du menu de navigation**, sélectionnez **Retail Server**.
1. Dans le volet des propriétés du module du menu de navigation, sous **Éléments de menu statiques**, sélectionnez **Ajouter un élément de menu**, puis sélectionnez **Élément du menu**. 
1. Dans la boîte de dialogue **Élément du menu**, sous **Texte de l’élément de menu**, entrez « Contact ».
1. Dans la boîte de dialogue **Élément du menu**, sous **Cible du lien d’élément de menu**, sélectionnez **Ajouter un lien**.
1. Dans la boîte de dialogue **Ajouter un lien**, sélectionnez l’URL de la page « Contact » du site, puis sélectionnez **OK**.  
1. Dans la boîte de dialogue **Élément du menu**, sélectionnez **OK**.
1. Dans l’emplacement **Recherche** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Recherche**, puis sélectionnez **OK**.
1. Dans le volet de propriétés du module de recherche, configurez les propriétés selon vos besoins.
1. Dans l’emplacement **Icône de panier** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Icône de panier**, puis sélectionnez **OK**.
1. Dans le volet de propriétés du module d’icône de panier, configurez les propriétés selon vos besoins. Si vous souhaitez que l’icône de panier affiche un résumé du panier (également connu sous le nom de mini panier) lorsque les utilisateurs la survolent, sélectionnez **Afficher le mini panier**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.

Pour vous assurer qu’un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.

1. Dans l’emplacement **En-tête** du module **Page par défaut**, ajoutez le fragment d’en-tête que vous avez créé.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module Icône de panier](cart-icon-module.md)

[Module Bannière promotionnelle](add-alert.md)

[Module Menu de navigation](nav-menu-module.md) 

[Consentement du cookie](cookie-consent-module.md)

[Module Pied de page](author-footer-module.md)

[Module de sélecteur de site](site-selector.md)

[Module Sélection de magasin](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
