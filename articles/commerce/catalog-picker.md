---
title: Module de sélection de catalogue
description: Cet article couvre les modules de sélection de catalogue et décrit comment les ajouter aux sites e-commerce B2B Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-04-21
ms.openlocfilehash: 642319eea7e40415fd32898f6ec07bfc86f3b1b1
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136942"
---
# <a name="catalog-picker-module"></a>Module de sélection de catalogue

[!include [banner](includes/banner.md)]

Cet article couvre les modules de sélection de catalogue et décrit comment les ajouter aux sites e-commerce B2B Microsoft Dynamics 365 Commerce.

Un module de sélection de catalogue est un conteneur spécial utilisé pour répertorier tous les catalogues de produits disponibles pour les achats des utilisateurs du site B2B. Plusieurs catalogues sont actuellement pris en charge uniquement pour les sites B2B.

L’illustration suivante présente un exemple d’un module de sélection de catalogue.

![Exemple d’un module de sélection de catalogue qui répertorie trois catalogues de produits.](./media/Catalog-picker-sample.png)

## <a name="add-a-catalog-picker-module-to-your-site"></a>Ajouter un module de sélection de catalogue à votre site

Pour ajouter un module de sélection de catalogue à votre site dans le générateur de site Commerce, procédez comme suit :

### <a name="create-a-catalog-picker-page"></a>Créer une page de sélection de catalogue

Tout d’abord, créez une page de sélection de catalogue.

1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Créer une page**, sous **Nom de la page**, entrez **sélection de catalogue**.
1. Sous **URL de la page**, entrez une URL pour la page, et sélectionnez **Suivant**.

    ![Créer une boîte de dialogue de nouvelle page.](./media/Create-catalog-picker-page.png)

1. Sous **Choisir un modèle**, sélectionnez **Contenu général**, puis sélectionnez **Suivant**.
1. Sous **Choisir une disposition**, sélectionnez **Disposition flexible**, puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**.
1. Sous **sélection de catalogue**, sélectionnez **Emplacement principal**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.

    ![Ajout d’un module à l’emplacement principal sous la sélection de catalogue.](./media/Author-web-page-catalog-picker-1.png)

1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Sélectionnez l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **sélection de catalogue**, puis cliquez sur **OK**.
1. Dans le volet de propriétés **sélection de catalogue**, sous **Titre**, sélectionnez **Catalogues**, puis saisissez un titre pour la page du sélection de catalogue.
1. En dessous de **Niveau de titre**, sélectionnez un niveau de titre, puis **OK**.
1. Sous **Texte enrichi**, saisissez le texte qui apparaîtra en haut de la page du sélection de catalogue.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

### <a name="add-a-link-on-your-account-page"></a>Ajouter un lien sur la page de votre compte

Ensuite, ajoutez une référence à votre page de sélection de catalogue sur votre page **Mon compte**.

1. Accédez à **Pages**, recherchez et sélectionnez la page **Mon compte** de votre site, puis sélectionnez **Modifier**.
1. Sous l’emplacement **Principal** de la page, sélectionnez l’emplacement **Vignette générique du compte**. 
1. Dans le volet des propriétés **Vignette générique du compte**, sous **Liens**, sélectionnez **Ajouter un lien d’action**, puis sélectionnez **Lien d’action**.
1. Dans la boîte de dialogue **Lien d’action**, sous **Texte du lien**, saisissez le texte du lien vers la page de votre sélection de catalogue.
1. Sous **Cible du lien**, sélectionnez **Ajouter un lien**.
1. Dans la boîte de dialogue **Ajouter un lien**, sélectionnez **Page personnalisée**, puis sélectionnez **Suivant**.
1. Sous **Nom**, sélectionnez votre page de sélection de catalogue, sélectionnez **Appliquer**, puis **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

L’illustration suivante montre un exemple de page de comptes avec une référence à la page de catalogue.

![Page de mes comptes avec lien vers le catalogue.](./media/my-accounts.png)

### <a name="add-a-link-from-the-header"></a>Ajouter un lien depuis l’en-tête

Enfin, ajoutez un lien depuis l’en-tête de votre site vers vos catalogues.

1. Accédez à **Fragments**, recherchez et sélectionnez le fragment d’en-tête de votre site, puis sélectionnez **Modifier**.
1. Sélectionnez l’emplacement **En-tête**. 
1. Dans le volet des propriétés **En-tête**, sous **Mes liens de compte**, sélectionnez **Ajouter un lien d’action**, puis sélectionnez **Lien d’action**.
1. Dans la boîte de dialogue **Lien d’action**, sous **Texte du lien**, saisissez le texte du lien vers la page de votre sélection de catalogue.
1. Sous **Cible du lien**, sélectionnez **Ajouter un lien**.
1. Dans la boîte de dialogue **Ajouter un lien**, sélectionnez **Page personnalisée**, puis sélectionnez **Suivant**.
1. Sous **Nom**, sélectionnez votre page de sélection de catalogue, sélectionnez **Appliquer**, puis **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment d’en-tête, puis **Publier** pour le publier.

L’illustration suivante montre un exemple d’en-tête de site Web de e-commerce avec un lien vers le catalogue B2B.

![En-tête du site Web de e-commerce avec lien déroulant vers le catalogue.](./media/catalog-in-header.png)


## <a name="additional-resources"></a>Ressources supplémentaires 

[Créer des catalogues Commerce pour les sites B2B](catalogs-b2b-sites.md)

[Impact d’extensibilité des catalogues Commerce pour les personnalisations B2B](catalogs-b2b-sites-dev.md)

[FAQ sur les catalogues Commerce pour le B2B](catalogs-b2b-sites-FAQ.md)

[Pages et modules Gestion des comptes](account-management.md)

[Module d’en-tête](author-header-module.md)
