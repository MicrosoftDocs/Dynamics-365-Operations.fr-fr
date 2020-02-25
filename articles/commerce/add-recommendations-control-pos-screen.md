---
title: Ajouter un contrôle de recommandations à l'écran de transaction sur des périphériques de PDV
description: Cette rubrique décrit comment ajouter un contrôle de recommandations à l'écran de transaction sur un périphérique de point de vente (PDV) à l'aide du concepteur de mise en page de l'écran dans Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 6d6f48197a36f633e3cd63cbad4518f53946fc7f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022473"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a><span data-ttu-id="4273f-103">Ajouter un contrôle de recommandations à l'écran de transaction sur des périphériques de PDV</span><span class="sxs-lookup"><span data-stu-id="4273f-103">Add a recommendations control to the transaction screen on POS devices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="4273f-104">Cette rubrique décrit comment ajouter un contrôle de recommandations à l'écran de transaction sur un périphérique de point de vente (PDV) à l'aide du concepteur de mise en page de l'écran dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4273f-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="4273f-105">Pour en savoir plus sur les recommandations produit, consultez les [recommandations produit sur la documentation du PDV](product.md).</span><span class="sxs-lookup"><span data-stu-id="4273f-105">For more information about product recommendations, read the  [product recommendations on POS documentation](product.md).</span></span>


<span data-ttu-id="4273f-106">Vous pouvez afficher les recommandations de produit sur votre périphérique de PDV lorsque vous utilisez Commerce.</span><span class="sxs-lookup"><span data-stu-id="4273f-106">You can display product recommendations on your POS device when you use Commerce.</span></span> <span data-ttu-id="4273f-107">Pour afficher les recommandations de produit, vous devez ajouter un contrôle à l'écran de transaction à l'aide du concepteur de mise en page de l'écran.</span><span class="sxs-lookup"><span data-stu-id="4273f-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="4273f-108">Ouvrir le concepteur de mise en page de l'écran</span><span class="sxs-lookup"><span data-stu-id="4273f-108">Open Layout designer</span></span>

1. <span data-ttu-id="4273f-109">Accédez à **Commerce et vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **PDV** &gt; **Mises en page de l'écran**.</span><span class="sxs-lookup"><span data-stu-id="4273f-109">Go to **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="4273f-110">Utilisez le filtre rapide pour accéder à l'écran auquel vous souhaitez ajouter le contrôle.</span><span class="sxs-lookup"><span data-stu-id="4273f-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="4273f-111">Par exemple, filtrez le champ **ID mise en page de l'écran** à l'aide de la valeur **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="4273f-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="4273f-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4273f-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="4273f-113">Par exemple, sélectionnez **Nom : F2CP16:9M ID mise en page de l'écran : F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="4273f-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="4273f-114">Cliquez sur **Concepteur de mise en page**.</span><span class="sxs-lookup"><span data-stu-id="4273f-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="4273f-115">Suivez les invites pour lancer le concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="4273f-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="4273f-116">Lorsque vous êtes invité à entrer vos informations d'identification, entrez les mêmes informations d'identification que celles utilisées lors du lancement du concepteur de mise en page dans la page **Mises en page de l'écran**.</span><span class="sxs-lookup"><span data-stu-id="4273f-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="4273f-117">Lorsque vous vous connectez, une page similaire à celle illustrée ci-dessous s'affiche.</span><span class="sxs-lookup"><span data-stu-id="4273f-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="4273f-118">La mise en page diffère selon les personnalisations que vous avez apportées à votre magasin.</span><span class="sxs-lookup"><span data-stu-id="4273f-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="4273f-119">[![Concepteur de mise en page](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="4273f-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="4273f-120">Choisir une option d'affichage</span><span class="sxs-lookup"><span data-stu-id="4273f-120">Choose a display option</span></span>

<span data-ttu-id="4273f-121">Deux options de configuration sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="4273f-121">There are two configurations options available.</span></span> <span data-ttu-id="4273f-122">Choisissez l'option qui convient le mieux pour votre magasin, puis suivez les instructions restantes pour terminer le paramétrage du contrôle.</span><span class="sxs-lookup"><span data-stu-id="4273f-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="4273f-123">Les deux options sont :</span><span class="sxs-lookup"><span data-stu-id="4273f-123">The two options are:</span></span>

- <span data-ttu-id="4273f-124">Les recommandations sont toujours visibles.</span><span class="sxs-lookup"><span data-stu-id="4273f-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="4273f-125">Un onglet **Recommandations** s'affiche dans la grille à droite de l'écran.</span><span class="sxs-lookup"><span data-stu-id="4273f-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="4273f-126">Rendre les recommandations toujours visibles</span><span class="sxs-lookup"><span data-stu-id="4273f-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="4273f-127">Réduisez la hauteur de la zone des détails des lignes de transaction de manière à ce qu'elle soit identique à celle du volet Client à sa gauche.</span><span class="sxs-lookup"><span data-stu-id="4273f-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="4273f-128">[![Hauteur de la zone de détails des lignes de transaction réduite](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="4273f-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="4273f-129">Dans le menu à gauche, déplacez le contrôle de recommandations entre la zone des détails des lignes de transaction et le groupe de boutons en bas au centre de l'écran de transaction.</span><span class="sxs-lookup"><span data-stu-id="4273f-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="4273f-130">Redimensionnez le contrôle de manière à l'ajuster dans cet espace.</span><span class="sxs-lookup"><span data-stu-id="4273f-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="4273f-131">[![Contrôle de recommandations ajouté à la disposition](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="4273f-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="4273f-132">Cliquez sur **X** pour enregistrer et fermer le concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="4273f-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="4273f-133">Dans Commerce, accédez à **Commerce et vente au détail** &gt; **Informatique Commerce et vente au détail** &gt; **Programmes de distribution**.</span><span class="sxs-lookup"><span data-stu-id="4273f-133">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="4273f-134">Dans la liste, sélectionnez **Caisses enregistreuses 1090**.</span><span class="sxs-lookup"><span data-stu-id="4273f-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="4273f-135">Cliquez sur **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="4273f-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="4273f-136">Ajouter un onglet Recommandations au groupe de boutons à droite de l'écran</span><span class="sxs-lookup"><span data-stu-id="4273f-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="4273f-137">Cliquez avec le bouton droit dans l'espace vide sous le dernier onglet du groupe de boutons situé à droite de la page.</span><span class="sxs-lookup"><span data-stu-id="4273f-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="4273f-138">Cliquez sur**Personnaliser**.</span><span class="sxs-lookup"><span data-stu-id="4273f-138">Click **Customize**.</span></span>

    <span data-ttu-id="4273f-139">[![Personnalisation - Boîte de dialogue Contrôle de l'onglet](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="4273f-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="4273f-140">Cliquez sur **Nouvel onglet**.</span><span class="sxs-lookup"><span data-stu-id="4273f-140">Click **New tab**.</span></span>
4. <span data-ttu-id="4273f-141">Recherchez le nouvel onglet que vous venez d'ajouter.</span><span class="sxs-lookup"><span data-stu-id="4273f-141">Find the new tab that you just added.</span></span> <span data-ttu-id="4273f-142">Vous devrez peut-être faire défiler l'écran vers le bas.</span><span class="sxs-lookup"><span data-stu-id="4273f-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="4273f-143">Dans la liste déroulante **Contenu**, sélectionnez **Produits recommandés**.</span><span class="sxs-lookup"><span data-stu-id="4273f-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="4273f-144">[![Sélection de Produits recommandés dans le champ Contenu](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="4273f-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="4273f-145">Dans le champ **Libellé**, saisissez un nom pour l'onglet de recommandations. Par exemple, saisissez « Produits recommandés ».</span><span class="sxs-lookup"><span data-stu-id="4273f-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="4273f-146">Dans le champ **Image**, sélectionnez l'image à afficher sous l'onglet.</span><span class="sxs-lookup"><span data-stu-id="4273f-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="4273f-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4273f-147">Click **OK**.</span></span> <span data-ttu-id="4273f-148">Le nouvel onglet apparaît dans le groupe de boutons.</span><span class="sxs-lookup"><span data-stu-id="4273f-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="4273f-149">Cliquez sur **X** pour enregistrer et fermer le concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="4273f-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="4273f-150">Dans Commerce, accédez à **Commerce et vente au détail** &gt; **Informatique Commerce et vente au détail** &gt; **Programmes de distribution**.</span><span class="sxs-lookup"><span data-stu-id="4273f-150">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="4273f-151">Dans la liste, sélectionnez **Caisses enregistreuses 1090**.</span><span class="sxs-lookup"><span data-stu-id="4273f-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="4273f-152">Cliquez sur **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="4273f-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4273f-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4273f-153">Additional resources</span></span>

[<span data-ttu-id="4273f-154">Recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="4273f-154">Product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="4273f-155">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="4273f-155">Product recommendations overview</span></span>](../commerce/product-recommendations.md)
