---
title: Module d'en-tête
description: Cette rubrique couvre les modules d'en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a5f7ad7d9c5ff63c3c3a8fe38275eec0d138891d
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411202"
---
# <a name="header-module"></a>Module d'en-tête

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules d'en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Dans Dynamics 365 Commerce, un en-tête de page comprend plusieurs modules, tels que les modules d'en-tête, de menu de navigation, de recherche, de bannière promotionnelle et de consentement aux cookies. 

Le module d'en-tête comprend un logo de site, des liens vers la hiérarchie de navigation, des liens vers d'autres pages du site, un symbole de panier, un symbole de liste de souhaits, des options de connexion et la barre de recherche. Un module d'en-tête est automatiquement optimisé pour l'appareil sur lequel le site est affiché (autrement dit, pour un périphérique de bureau ou un appareil mobile). Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).

L'image suivante montre un exemple de module d'en-tête sur une page d'accueil.

![Exemple d'un module d'en-tête](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Propriétés d'un module d'en-tête

Un module d'en-tête prend en charge les propriétés suivantes : **Image de logo**, **Lien vers le logo** et **Liens de mon compte**. 

Les propriétés **Image de logo** et **Lien vers le logo** sont utilisées pour définir un logo sur la page. Pour plus d'informations, voir [Ajouter un logo](add-logo.md). 

La propriété **Liens de mon compte** peut être utilisée pour définir les pages de compte pour lesquelles le propriétaire du site souhaite afficher des liens rapides dans l'en-tête.

## <a name="modules-that-are-available-in-a-header-module"></a>Modules disponibles dans le module d'en-tête

Les modules suivants peuvent être utilisés dans un module d'en-tête :

- **Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d'autres liens de navigation statiques. La hiérarchie de navigation du canal peut être configurée dans Dynamics 365 Commerce. Le menu de navigation a une propriété **Source de navigation** qui est utilisée pour spécifier les éléments de menu statique et les éléments de menu de navigation Serveur de vente au détail comme source. Si des éléments de menu statique sont spécifiés comme source, des liens relatifs vers d'autres pages du site peuvent être fournis. Les articles configurés s'affichent alors comme navigation d'en-tête. 

- **Rechercher** – Le module de recherche permet aux utilisateurs d'entrer des critères de recherche pour des produits. L'URL de la page de recherche par défaut et les paramètres de la requête de recherche doivent être fournis à l'adresse **Paramètres du site \> Extensions**. Le module de recherche possède des propriétés qui vous permettent de supprimer l'étiquette ou le bouton de recherche selon vos besoins. Le module de recherche prend également en charge les options de suggestion automatique, telles que les résultats de recherche de produits, de mots clés et de catégories.

- **Icône de panier** - Le module d'icône de panier représente l'icône de panier, qui indique le nombre d'articles dans le panier à un moment donné. Pour plus d'informations, voir [Module Icône de panier](cart-icon-module.md).

## <a name="create-a-header-module-for-a-page"></a>Créer un module d'en-tête pour une page

Pour créer un module d'en-tête, procédez comme suit :

1. Accédez à **Fragments de page**, puis cliquez sur **Nouveau** pour créer un fragment.
1. Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment de page, puis sélectionnez **OK**.
1. Sélectionnez l'emplacement **Conteneur par défaut** puis, dans le volet des propriétés de droite, définissez la propriété **Largeur** sur **Remplir le conteneur**.
1. Dans l'emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez les modules **Bannière promotionnelle** et **Consentement aux cookies**, puis sélectionnez **OK**.
1. Dans l'emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Sélectionnez l'emplacement **Conteneur** puis, dans le volet des propriétés de droite, définissez la propriété **Largeur** sur **Remplir le conteneur**.
1. Dans l'emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **En-tête**, puis sélectionnez **OK**.
1. Dans l'emplacement **Menu de navigation** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Menu de navigation**, puis sélectionnez **OK**.
1. Dans le volet de propriétés du module de menu de navigation, configurez les propriétés selon vos besoins.
1. Dans l'emplacement **Recherche** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Recherche**, puis sélectionnez **OK**.
1. Dans le volet de propriétés du module de recherche, configurez les propriétés selon vos besoins.
1. Dans l'emplacement **Icône de panier** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Icône de panier**, puis sélectionnez **OK**.
1. Dans le volet de propriétés du module d'icône de panier, configurez les propriétés selon vos besoins. Si vous souhaitez que l'icône de panier affiche un résumé du panier (également connu sous le nom de mini panier) lorsque les utilisateurs la survolent, sélectionnez **Afficher le mini panier**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.

Pour vous assurer qu'un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.

1. Dans l'emplacement **En-tête** du module **Page par défaut**, ajoutez le fragment d'en-tête que vous avez créé.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module de zone d'achat](add-buy-box.md)

[Module de panier](add-cart-module.md)

[Module Icône de panier](cart-icon-module.md)

[Module de validation](add-checkout-module.md)

[Module de confirmation de commande](order-confirmation-module.md)

[Module d'en-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
