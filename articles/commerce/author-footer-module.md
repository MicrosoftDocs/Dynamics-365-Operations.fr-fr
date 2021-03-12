---
title: Module Pied de page
description: Cette rubrique couvre les modules de pied de page et leur création dans Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 038fee32cbf1ed6b4967f440faaf3c0d4fa583f6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979945"
---
# <a name="footer-module"></a>Module Pied de page  

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de pied de page et décrit leur création dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Le module de pied de page est un conteneur spécial utilisé pour héberger les modules qui figurent dans le pied de page de la page. Par exemple, il peut inclure des liens vers des pages du site, telles que les pages **Nous contacter** et **Stocker des stratégies**.

L’image suivante montre un exemple de module de pied de page sur une page de site.

![Exemple de module de pied de page](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Propriétés du module de pied de page 

Comme la plupart des conteneurs, un module de pied de page prend en charge les propriétés pour l’en-tête et la largeur. Il prend également en charge l’addition de plusieurs modules de catégories de pieds de page. Chaque module de catégorie de pied de page qui est ajouté est affiché dans une colonne dans le module de pied de page.

## <a name="modules-available-in-a-footer-module"></a>Modules disponibles dans un module de pied de page

**Articles de pied de page** – Un module d’articles de pied de page peut contenir un en-tête, une image, et un lien. L’en-tête peut être utilisé seul ou en combinaison avec une image et un lien. Chaque lien dans le pied de page peut être configuré de sorte qu’il s’agisse juste de texte (par exemple, « Contactez-nous » et « Confidentialité »), ou afin qu’il comporte à la fois du texte et une image (par exemple, des liens vers des réseaux sociaux).

**Retour vers le haut** – A module Retour vers le haut fournit un lien de navigation rapide vers le haut de la page. Une destination est requise. La valeur par défaut de destination est \#, qui dirige l’utilisateur vers le haut de la page.

## <a name="create-a-footer-module"></a>Créer un module de pied de page

1. Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Catégorie de pied de page**, puis sélectionnez **OK**.
1. Dans l’emplacement **Catégorie de pied de page**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Élément de pied de page**, puis sélectionnez **OK**.
1. Sélectionnez l’emplacement **Élément de pied de page** puis, dans le volet de propriétés de droite, configurez l’en-tête, le lien et le texte du lien, et une image au besoin.
1. Pour ajouter d’autres éléments de pied de page, répétez les étapes 5 à 7 pour chacun.
1. Pour ajouter un lien « Retour vers le haut » à votre pied de page, sélectionnez le bouton représentant des points de suspension (**...**) dans l’emplacement **Catégorie de pied de page**, puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Retour vers le haut**, puis sélectionnez **OK**.
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
