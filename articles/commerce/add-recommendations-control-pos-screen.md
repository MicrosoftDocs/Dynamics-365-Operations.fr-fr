---
title: Ajouter des recommandations à l'écran de transaction
description: Cette rubrique décrit comment ajouter un contrôle de recommandations à l'écran de transaction sur un périphérique de point de vente (PDV) à l'aide du concepteur de mise en page de l'écran dans Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2e1ef6506833b35e61351600553a3bc29c20d5b2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980230"
---
# <a name="add-recommendations-to-the-transaction-screen"></a>Ajouter des recommandations à l'écran de transaction

[!include [banner](includes/banner.md)]


Cette rubrique décrit comment ajouter un contrôle de recommandations à l'écran de transaction sur un périphérique de point de vente (PDV) à l'aide du concepteur de mise en page de l'écran dans Microsoft Dynamics 365 Commerce. Pour en savoir plus sur les recommandations produit, consultez les [recommandations produit sur la documentation du PDV](product.md).


Vous pouvez afficher les recommandations de produit sur votre périphérique de PDV lorsque vous utilisez Commerce. Pour afficher les recommandations de produit, vous devez ajouter un contrôle à l'écran de transaction à l'aide du concepteur de mise en page de l'écran. 

## <a name="open-layout-designer"></a>Ouvrir le concepteur de mise en page de l'écran

1. Accédez à **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **PDV** &gt; **Mises en page de l'écran**.
2. Utilisez le filtre rapide pour accéder à l'écran auquel vous souhaitez ajouter le contrôle. Par exemple, filtrez le champ **ID mise en page de l'écran** à l'aide de la valeur **F2CP16:9M**.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Par exemple, sélectionnez **Nom : F2CP16:9M ID mise en page de l'écran : F2CP16:9M**.
4. Cliquez sur **Concepteur de mise en page**.
5. Suivez les invites pour lancer le concepteur de mise en page. Lorsque vous êtes invité à entrer vos informations d'identification, entrez les mêmes informations d'identification que celles utilisées lors du lancement du concepteur de mise en page dans la page **Mises en page de l'écran**.
6. Lorsque vous vous connectez, une page similaire à celle illustrée ci-dessous s'affiche. La mise en page diffère selon les personnalisations que vous avez apportées à votre magasin.


    [![Concepteur de mise en page](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Choisir une option d'affichage

Deux options de configuration sont disponibles. Choisissez l'option qui convient le mieux pour votre magasin, puis suivez les instructions restantes pour terminer le paramétrage du contrôle. Les deux options sont :

- Les recommandations sont toujours visibles.
- Un onglet **Recommandations** s'affiche dans la grille à droite de l'écran.

### <a name="make-recommendations-always-visible"></a>Rendre les recommandations toujours visibles


1. Réduisez la hauteur de la zone des détails des lignes de transaction de manière à ce qu'elle soit identique à celle du volet Client à sa gauche.


    [![Hauteur de la zone de détails des lignes de transaction réduite](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. Dans le menu à gauche, déplacez le contrôle de recommandations entre la zone des détails des lignes de transaction et le groupe de boutons en bas au centre de l'écran de transaction. Redimensionnez le contrôle de manière à l'ajuster dans cet espace.

    [![Contrôle de recommandations ajouté à la disposition](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)


3. Cliquez sur **X** pour enregistrer et fermer le concepteur de mise en page.
4. Dans Commerce, accédez à **Commerce et vente au détail** &gt; **Informatique Commerce et vente au détail** &gt; **Programmes de distribution**.
5. Dans la liste, sélectionnez **Caisses enregistreuses 1090**.
6. Cliquez sur **Exécuter maintenant**.


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Ajouter un onglet Recommandations au groupe de boutons à droite de l'écran

1. Cliquez avec le bouton droit dans l'espace vide sous le dernier onglet du groupe de boutons situé à droite de la page.

2. Cliquez sur **Personnaliser**.

    [![Personnalisation - Boîte de dialogue Contrôle de l'onglet](./media/pic-5.png)](./media/pic-5.png)

3. Cliquez sur **Nouvel onglet**.
4. Recherchez le nouvel onglet que vous venez d'ajouter. Vous devrez peut-être faire défiler l'écran vers le bas.
5. Dans la liste déroulante **Contenu**, sélectionnez **Produits recommandés**.

    [![Sélection de Produits recommandés dans le champ Contenu](./media/pic-6.png)](./media/pic-6.png)

6. Dans le champ **Libellé**, saisissez un nom pour l'onglet de recommandations. Par exemple, saisissez « Produits recommandés ».
7. Dans le champ **Image**, sélectionnez l'image à afficher sous l'onglet.
8. Cliquez sur **OK**. Le nouvel onglet apparaît dans le groupe de boutons.
9. Cliquez sur **X** pour enregistrer et fermer le concepteur de mise en page.
10. Dans Commerce, accédez à **Commerce et vente au détail** &gt; **Informatique Commerce et vente au détail** &gt; **Programmes de distribution**.
11. Dans la liste, sélectionnez **Caisses enregistreuses 1090**.
12. Cliquez sur **Exécuter maintenant**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des recommandations produit](product-recommendations.md)

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Activer les recommandations produit](enable-product-recommendations.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Activer les recommandations « acheter des aspects similaires »](shop-similar-looks.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]