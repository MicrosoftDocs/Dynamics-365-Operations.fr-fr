---
title: Module Pied de page
description: Cette rubrique couvre les modules de pied de page et leur création dans Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c253cd9620180b09f2f5cae232e46d236deabdd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697311"
---
# <a name="footer-module"></a>Module Pied de page  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de pied de page et décrit leur création dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Le module de pied de page est un conteneur spécial utilisé pour héberger les modules qui figurent dans le pied de page de la page. Par exemple, il peut inclure des liens vers des pages du site, telles que les pages **Nous contacter** et **Stocker des stratégies**.

## <a name="footer-module-properties"></a>Propriétés du module de pied de page 

Comme la plupart des conteneurs, un module de pied de page prend en charge les propriétés pour l'en-tête et la largeur. Il prend également en charge l'addition de plusieurs modules de catégories de pieds de page. Chaque module de catégorie de pied de page qui est ajouté est affiché dans une colonne dans le module de pied de page.

## <a name="modules-available-in-a-footer-module"></a>Modules disponibles dans un module de pied de page

**Articles de pied de page** – Un module d'articles de pied de page peut contenir un en-tête, une image, et un lien. L'en-tête peut être utilisé seul ou en combinaison avec une image et un lien. Chaque lien dans le pied de page peut être configuré de sorte qu'il s'agisse juste de texte (par exemple, « Contactez-nous » et « Confidentialité »), ou afin qu'il comporte à la fois du texte et une image (par exemple, des liens vers des réseaux sociaux).

**Retour vers le haut** – A module Retour vers le haut fournit un lien de navigation rapide vers le haut de la page. Une destination est requise. La valeur par défaut de destination est #, qui dirige l'utilisateur vers le haut de la page.

## <a name="author-a-footer-module"></a>Créer un module de pied de page

1. Dans le volet de navigation, sélectionnez **Fragments**, puis sélectionnez **Nouveau fragment de page**.
1. Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez le module de pied de page, entrez un nom pour le fragment de page, puis sélectionnez **OK**.
1. Dans l'arborescence du contour à gauche, sélectionnez le bouton représentant des points de suspension (**...**) pour le module de pied de page, puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter le module**, sélectionnez le module de catégorie de pied de page, puis sélectionnez **OK**.
1. Dans l'arborescence du contour, sélectionnez le bouton représentant des points de suspension pour le module de catégorie de pied de page, puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter le module**, sélectionnez le module d'article de pied de page, puis sélectionnez **OK**.
1. Dans l'arborescence de contour, sélectionnez le module d'article de pied de page. Puis, dans le volet de propriétés de droite, configurez l'en-tête, le lien et le texte du lien, et une image au besoin.
1. Pour ajouter d'autres articles de pied de page, répétez les étapes 5 à 7.
1. Pour ajouter un lien « Retour vers le haut » à votre pied de page, sélectionnez le bouton représentant des points de suspension pour le module de catégorie de pied de page, puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter le module**, sélectionnez le module de retour vers le haut, puis sélectionnez **OK**.
1. Dans l'arborescence de contour, sélectionnez le module de retour vers le haut. Puis, dans le volet des propriétés de droite, configurez le module de retour vers le haut comme vous le souhaitez.
1. Enregistrez le fragment de page, archivez-le, et publiez-le.

Sur chaque modèle de page créé pour le site, procédez comme suit.

1. À l'emplacement **Principal** de la page par défaut, dans le module de pied de page, ajoutez le fragment de pied de page que vous avez créé.
1. Enregistrez le modèle, archivez-le, et publiez-le.

En ajoutant le fragment de page aux modèles de page, vous vous assurez que le pied de page s'affiche sur chaque page.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Paiement](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
