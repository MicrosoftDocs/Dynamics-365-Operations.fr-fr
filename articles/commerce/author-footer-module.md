---
title: Module Pied de page
description: Cet article couvre les modules de pied de page et leur création dans Dynamics 365 Commerce.
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
ms.openlocfilehash: fefeed37ba0d0e800b9cd3cefcf207cde9a625d8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282955"
---
# <a name="footer-module"></a>Module Pied de page  

[!include [banner](includes/banner.md)]

Cet article couvre les modules de pied de page et décrit leur création dans Microsoft Dynamics 365 Commerce.

Le module de pied de page est un conteneur spécial utilisé pour héberger les modules qui figurent dans le pied de page de la page. Par exemple, il peut inclure des liens vers des pages du site, telles que les pages **Nous contacter** et **Stocker des stratégies**.

L’image suivante montre un exemple de module de pied de page sur une page de site.

![Exemple de module de pied de page.](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Propriétés du module de pied de page 

Comme la plupart des conteneurs, un module de pied de page prend en charge les propriétés pour l’en-tête et la largeur. Il prend également en charge l’addition de plusieurs modules de catégories de pieds de page. Chaque module de catégorie de pied de page qui est ajouté est affiché dans une colonne dans le module de pied de page.

## <a name="modules-available-in-a-footer-module"></a>Modules disponibles dans un module de pied de page

**Article de pied de page** – Un module d’article de pied de page peut contenir un en-tête ou un lien. L’en-tête est généralement utilisé comme titre de section de pied de page.  Chaque lien dans le pied de page peut être configuré de sorte qu’il s’agisse juste de texte (par exemple, « Contactez-nous » et « Confidentialité »), ou afin qu’il comporte à la fois du texte et une image (par exemple, des liens vers des réseaux sociaux). Si un en-tête et un lien sont fournis, la propriété d’en-tête prévaudra sur le lien. 

**Retour vers le haut** – A module Retour vers le haut fournit un lien de navigation rapide vers le haut de la page. Une destination est requise. La valeur par défaut de destination est \#, qui dirige l’utilisateur vers le haut de la page.

## <a name="create-a-footer-module"></a>Créer un module de pied de page

1. Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.
1. Dans la boîte de dialogue **Sélectionner un fragment**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment, puis cliquez sur **OK**.
1. Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Catégorie de pied de page**, puis cliquez sur **OK**.
1. Dans l’emplacement **Catégorie de pied de page**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Élément du pied de page**, puis cliquez sur **OK**.
1. Sélectionnez l’emplacement **Élément de pied de page** puis, dans le volet de propriétés de droite, configurez l’en-tête, le lien et le texte du lien, et une image au besoin.
1. Pour ajouter d’autres éléments de pied de page, répétez les étapes 5 à 7 pour chacun.
1. Pour ajouter un lien « Retour vers le haut » à votre pied de page, sélectionnez le bouton représentant des points de suspension (**...**) dans l’emplacement **Catégorie de pied de page**, puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Retour en haut**, puis cliquez sur **OK**.
1. Sélectionnez l’emplacement **Retour vers le haut** puis, dans le volet de propriétés de droite, configurez le texte et les autres propriétés du module selon vos besoins.
1. Sélectionnez **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.

Pour vous assurer qu’un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.

1. Dans l’emplacement **Pied de page** du module **Page par défaut**, ajoutez le fragment de pied de page que vous avez créé.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.

En ajoutant le fragment aux modèles de page, vous vous assurez que le pied de page s’affiche sur chaque page.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module Zone d’achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Validation](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
