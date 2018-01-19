---
title: "Ajouter un contrôle de recommandations à la page de transaction sur un périphérique de PDV"
description: "Cette rubrique décrit comment ajouter un contrôle de recommandations à l'écran de transaction sur un périphérique de point de vente (PDV) à l'aide du concepteur de mise en page de l'écran dans Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 0d366997fbb6f23474047fa8c465a594491c46ad
ms.contentlocale: fr-fr
ms.lasthandoff: 01/19/2018

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a><span data-ttu-id="b2ecf-103">Ajouter un contrôle de recommandations à la page de transaction sur un périphérique de PDV</span><span class="sxs-lookup"><span data-stu-id="b2ecf-103">Add a recommendations control to the transaction page on a POS device</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="b2ecf-104">Cette rubrique décrit comment ajouter un contrôle de recommandations à l'écran de transaction sur un périphérique de point de vente (PDV) à l'aide du concepteur de mise en page de l'écran dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="b2ecf-105">Vous pouvez afficher les recommandations de produit sur votre périphérique de PDV lorsque vous utilisez Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-105">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="b2ecf-106">Les *Recommandations* sont des articles susceptibles d'intéresser vos clients en fonction de leur historique d'achat, des articles de leur liste de souhaits et des articles achetés par d'autres clients en ligne ou dans des magasins traditionnels.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-106">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="b2ecf-107">Pour afficher les recommandations de produit, vous devez ajouter un contrôle à l'écran de transaction à l'aide du concepteur de mise en page de l'écran.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="b2ecf-108">Ouvrir le concepteur de mise en page de l'écran</span><span class="sxs-lookup"><span data-stu-id="b2ecf-108">Open Layout designer</span></span>
1.  <span data-ttu-id="b2ecf-109">Accédez à **Vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **PDV** &gt; **Mises en page de l'écran**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2.  <span data-ttu-id="b2ecf-110">Utilisez le filtre rapide pour accéder à l'écran auquel vous souhaitez ajouter le contrôle.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="b2ecf-111">Par exemple, filtrez le champ **ID mise en page de l'écran** à l'aide de la valeur « F2CP16:9M ».</span><span class="sxs-lookup"><span data-stu-id="b2ecf-111">For example, filter on the **Screen layout ID** field using a value of ‘F2CP16:9M’.</span></span>
3.  <span data-ttu-id="b2ecf-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="b2ecf-113">Par exemple, sélectionnez «Nom : F2CP16:9M ID mise en page de l'écran : F2CP16:9M ».</span><span class="sxs-lookup"><span data-stu-id="b2ecf-113">For example, select ‘Name: F2CP16:9M Screen Layout ID: F2CP16:9M’.</span></span>
4.  <span data-ttu-id="b2ecf-114">Cliquez sur **Concepteur de mise en page**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-114">Click **Layout designer**.</span></span>
5.  <span data-ttu-id="b2ecf-115">Suivez les invites pour lancer le concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="b2ecf-116">Lorsque vous êtes invité à entrer vos informations d'identification, entrez les mêmes informations d'identification que celles utilisées lors du lancement du concepteur de mise en page dans la page **Mises en page de l'écran**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6.  <span data-ttu-id="b2ecf-117">Lorsque vous vous connectez, une page similaire à celle illustrée ci-dessous s'affiche.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="b2ecf-118">La mise en page diffère selon les personnalisations que vous avez apportées à votre magasin.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-118">The layout will be different depending on the customizations that were made for your store.</span></span>

<span data-ttu-id="b2ecf-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choisir une option d'affichage</span><span class="sxs-lookup"><span data-stu-id="b2ecf-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choose a display option</span></span>
-----------------------

<span data-ttu-id="b2ecf-120">Deux options de configuration sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-120">There are two configurations options available.</span></span> <span data-ttu-id="b2ecf-121">Choisissez l'option qui convient le mieux pour votre magasin, puis suivez les instructions restantes pour terminer le paramétrage du contrôle.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-121">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="b2ecf-122">Les deux options sont :</span><span class="sxs-lookup"><span data-stu-id="b2ecf-122">The two options are:</span></span>
-   <span data-ttu-id="b2ecf-123">Les recommandations sont toujours visibles.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-123">Recommendations are always visible.</span></span>
-   <span data-ttu-id="b2ecf-124">Un onglet **Recommandations** s'affiche dans la grille à droite de l'écran.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-124">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

#### <a name="to-make-recommendations-always-visible"></a><span data-ttu-id="b2ecf-125">Pour rendre les recommandations toujours visibles</span><span class="sxs-lookup"><span data-stu-id="b2ecf-125">To make recommendations always visible</span></span>

1.  <span data-ttu-id="b2ecf-126">Réduisez la hauteur de la zone des détails des lignes de transaction de manière à ce qu'elle soit identique à celle du volet Client à sa gauche.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="b2ecf-126">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>
2.  <span data-ttu-id="b2ecf-127">Dans le menu à gauche, déplacez le contrôle de recommandations entre la zone des détails des lignes de transaction et le groupe de boutons en bas au centre de l'écran de transaction.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-127">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="b2ecf-128">Redimensionnez le contrôle de manière à l'ajuster dans cet espace.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="b2ecf-128">Resize the control so it fits in that space.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>
3.  <span data-ttu-id="b2ecf-129">Cliquez sur **X** pour enregistrer et fermer le concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-129">Click the **X** to save and exit Layout designer.</span></span>
4.  <span data-ttu-id="b2ecf-130">Dans Dynamics 365 for Retail, accédez à **Vente au détail** &gt; **Informatique au détail** &gt; **Programmes de distribution**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-130">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5.  <span data-ttu-id="b2ecf-131">Dans la liste, sélectionnez **Caisses enregistreuses 1090**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-131">In the list, select **1090 Registers**.</span></span>
6.  <span data-ttu-id="b2ecf-132">Cliquez sur **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-132">Click **Run now**.</span></span>

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="b2ecf-133">Pour ajouter un onglet Recommandations au groupe de boutons à droite de l'écran</span><span class="sxs-lookup"><span data-stu-id="b2ecf-133">To add a Recommendations tab to the button grid on the right side of the screen</span></span>

1.  <span data-ttu-id="b2ecf-134">Cliquez avec le bouton droit dans l'espace vide sous le dernier onglet du groupe de boutons situé à droite de la page.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-134">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2.  <span data-ttu-id="b2ecf-135">Cliquez sur **Personnaliser**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="b2ecf-135">Click **Customize**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span></span>
3.  <span data-ttu-id="b2ecf-136">Cliquez sur **Nouvel onglet**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-136">Click **New tab**.</span></span>
4.  <span data-ttu-id="b2ecf-137">Recherchez le nouvel onglet que vous venez d'ajouter.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-137">Find the new tab that you just added.</span></span> <span data-ttu-id="b2ecf-138">Vous devrez peut-être faire défiler l'écran vers le bas.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-138">You may need to scroll down.</span></span>
5.  <span data-ttu-id="b2ecf-139">Dans la liste déroulante **Contenu**, sélectionnez **Produits recommandés**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-139">In the **Contents** drop-down, select **Recommended products**.</span></span> <span data-ttu-id="b2ecf-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="b2ecf-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span></span>
6.  <span data-ttu-id="b2ecf-141">Dans le champ **Libellé**, saisissez un nom pour l'onglet de recommandations. Par exemple, saisissez « Produits recommandés ».</span><span class="sxs-lookup"><span data-stu-id="b2ecf-141">In the **Label** field, type a name for the recommendations tab. For example, type ‘Recommended products’.</span></span>
7.  <span data-ttu-id="b2ecf-142">Dans le champ **Image**, sélectionnez l'image à afficher sous l'onglet.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-142">In the **Image** field, select the image to appear on the tab.</span></span>
8.  <span data-ttu-id="b2ecf-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-143">Click **OK**.</span></span> <span data-ttu-id="b2ecf-144">Le nouvel onglet apparaît dans le groupe de boutons.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-144">The new tab appears in the button grid.</span></span>
9.  <span data-ttu-id="b2ecf-145">Cliquez sur **X** pour enregistrer et fermer le concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-145">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="b2ecf-146">Dans Dynamics 365 for Retail, accédez à **Vente au détail** &gt; **Informatique au détail** &gt; **Programmes de distribution**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-146">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="b2ecf-147">Dans la liste, sélectionnez **Caisses enregistreuses 1090**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-147">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="b2ecf-148">Cliquez sur **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="b2ecf-148">Click **Run now**.</span></span>


<a name="see-also"></a><span data-ttu-id="b2ecf-149">Voir également :</span><span class="sxs-lookup"><span data-stu-id="b2ecf-149">See also</span></span>
--------

[<span data-ttu-id="b2ecf-150">Vue d'ensemble des recommandations de produit personnalisées</span><span class="sxs-lookup"><span data-stu-id="b2ecf-150">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)




