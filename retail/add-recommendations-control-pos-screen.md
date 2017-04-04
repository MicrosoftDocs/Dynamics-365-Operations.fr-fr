---
title: "Ajoutez un contrôle de recommandations à la page de transaction sur un périphérique de PDV"
description: "Cette rubrique décrit la procédure d&quot;ajout d&quot;un contrôle de recommandations à l&quot;écran des transactions sur un périphérique de (POS) de point de vente à l&quot;aide de le concepteur de mise en page de l&quot;écran dans Microsoft Dynamics 365 pour les opérations."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2377b1639a3c95fe6bba4754c4069cc12043e3d3
ms.lasthandoff: 03/31/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Ajoutez un contrôle de recommandations à la page de transaction sur un périphérique de PDV

Cette rubrique décrit la procédure d'ajout d'un contrôle de recommandations à l'écran des transactions sur un périphérique de (POS) de point de vente à l'aide de le concepteur de mise en page de l'écran dans Microsoft Dynamics 365 pour les opérations.

Vous pouvez afficher les recommandations de votre produit {{concernant:on}} périphérique du PDV lorsque vous utilisez Microsoft Dynamics 365 pour les opérations. le *Recommendations* sont des articles que votre client peut être intéressé $ selon leur historique d'achat, articles dans sa liste de souhait, et articles que d'autres clients ont acheté en ligne et dans les magasins de brique-et- physiques. Pour afficher les recommandations de produit, vous devez ajouter un contrôle à l'écran des transactions à l'aide de le concepteur de mise en page de l'écran.

## <a name="open-layout-designer"></a>Permet d'ouvrir le concepteur de mise en page
1.  Allez ** au détail et commerce ** &gt; ** au canal paramétré ** &gt; ** la configuration ** &gt; ** PDV ** &gt; ** les mises en page de l'écran **.
2.  Utilisez le filtre rapide pour accéder à l'écran auquel vous souhaitez ajouter le contrôle. Par exemple, filtrez ** ID mise en page de l'écran ** le champ à l'aide d'une valeur « F2CP16 : 9M ».
3.  Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Par exemple, sélectionnez le nom « : F2CP16 : ID mise en page de l'écran de 9M : F2CP16 : 9M ».
4.  Cliquez sur ** concepteur de mise en page **.
5.  Suivez les invites pour lancer le concepteur de mise en page. Lorsque vous êtes invité à sélectionner les informations d'identification, entrez les mêmes informations d'identification en cours de utilisation lorsque le concepteur de mise en page a été lancé ** les mises en page de l'écran ** de la page.
6.  Lorsque vous vous connectez, une page identique à celle apparaît ci-après. La mise en page est différente selon les personnalisations effectuées pour votre magasin.

![screenlayout-pic-1 [] (. /media/screenlayout-pic-1.png)](. /media/screenlayout-pic-1.png) Sélectionnez une option d'affichage
-----------------------

Il existe deux options de configurations disponibles. Choisissez l'option qui s'exécute le Délai pour votre magasin, puis suivez les instructions restantes de terminer de paramétrer le contrôle. Les deux options sont :
-   Les recommandations sont toujours afficher.
-   A ** recommandations ** onglet s'affiche dans la grille à droite de l'écran.

#### <a name="to-make-recommendations-always-visible"></a>Pour émettre des recommandations toujours visibles

1.  Réduire la hauteur de la zone de détails des lignes de transaction afin qu'elle soit la même hauteur que le panneau de client vers la gauche. [] (. /media/pic-2.png) [![screenlayout-pic-2] (. /media/screenlayout-pic-2.png)](. /media/screenlayout-pic-2.png)
2.  Dans le menu à gauche, l'faites et quitter la fonction glisser-déplacer le contrôle de recommandations situées entre à la zone de détails de ligne de transaction et le groupe de boutons du bas central de l'écran de transaction. Redimensionner le contrôle ce qui correspond de cet espace. [] (. /media/pic-3.png) [![screenlayout-pic-3] (. /media/screenlayout-pic-3.png)](. /media/screenlayout-pic-3.png)
3.  Les cliquez sur ** X ** pour enregistrer et fermer le concepteur de mise en page.
4.  Dans Dynamics 365 pour les opérations, passez ** au détail et commerce ** &gt; ** à l'IT au détail ** &gt; ** des programmes de distribution **.
5.  Dans la liste, sélectionnez ** 1090 livres **.
6.  Cliquez sur ** exécution désormais **.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Pour ajouter un onglet de recommandations au groupe de boutons à droite de l'écran

1.  Cliquez avec le bouton droit dans l'espace vide sous le dernier onglet du groupe de boutons situé à droite de la page.
2.  Cliquez sur ** personnalisez **.![pic-5 [] (. /media/pic-5.png)](. /media/pic-5.png)
3.  Cliquez sur ** nouvel onglet **.
4.  Cherchez le nouvel onglet que vous venez ajouté. Vous devrez peut-être faire défiler l'écran.
5.  Dans ** contenu ** la liste déroulante, sélectionnez ** les produits recommandés **. ![pic-6 [] (. /media/pic-6.png)](. /media/pic-6.png)
6.  Dans ** étiquette ** le champ, entrez un nom pour l'onglet de recommandations. Par exemple, tapez « produits recommandés ».
7.  Dans ** image ** le champ, sélectionnez l'image à afficher sous l'onglet.
8.  Click **OK**. Le nouvel onglet apparaît dans le groupe de boutons.
9.  Les cliquez sur ** X ** pour enregistrer et fermer le concepteur de mise en page.
10. Dans Dynamics 365 pour les opérations, passez ** au détail et commerce ** &gt; ** à l'IT au détail ** &gt; ** des programmes de distribution **.
11. Dans la liste, sélectionnez ** 1090 livres **.
12. Cliquez sur ** exécution désormais **.


<a name="see-also"></a>Voir également :
--------

[Vue d'ensemble personnalisée de recommandations de produit] (personalized-product-recommendations.md)


