---
title: Ajouter un contrôle de recommandations à l'écran de transaction sur des périphériques de PDV
description: Cette rubrique décrit comment ajouter un contrôle de recommandations à l'écran de transaction sur un périphérique de point de vente (PDV) à l'aide du concepteur de mise en page de l'écran dans Microsoft Dynamics 365 for Retail.
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
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
ms.openlocfilehash: f17da3db6fbc19548544a0c6c090a0b6db093673
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606847"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a><span data-ttu-id="df145-103">Ajouter un contrôle de recommandations à l'écran de transaction sur des périphériques de PDV</span><span class="sxs-lookup"><span data-stu-id="df145-103">Add a recommendations control to the transaction screen on POS devices</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="df145-104">Nous supprimons la version actuelle du service de recommandation de produit car nous remodelons cette fonction avec un meilleur algorithme et de nouvelles fonctionnalités orientées détail.</span><span class="sxs-lookup"><span data-stu-id="df145-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="df145-105">Pour plus d'informations voir [Fonctions supprimées ou obsolètes](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span><span class="sxs-lookup"><span data-stu-id="df145-105">For more information see [Removed or deprecated features](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span></span>

<span data-ttu-id="df145-106">Cette rubrique décrit comment ajouter un contrôle de recommandations à l'écran de transaction sur un périphérique de point de vente (PDV) à l'aide du concepteur de mise en page de l'écran dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="df145-106">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="df145-107">Vous pouvez afficher les recommandations de produit sur votre périphérique de PDV lorsque vous utilisez Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="df145-107">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="df145-108">Les *Recommandations* sont des articles susceptibles d'intéresser vos clients en fonction de leur historique d'achat, des articles de leur liste de souhaits et des articles achetés par d'autres clients en ligne ou dans des magasins traditionnels.</span><span class="sxs-lookup"><span data-stu-id="df145-108">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="df145-109">Pour afficher les recommandations de produit, vous devez ajouter un contrôle à l'écran de transaction à l'aide du concepteur de mise en page de l'écran.</span><span class="sxs-lookup"><span data-stu-id="df145-109">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="df145-110">Ouvrir le concepteur de mise en page de l'écran</span><span class="sxs-lookup"><span data-stu-id="df145-110">Open Layout designer</span></span>

1. <span data-ttu-id="df145-111">Accédez à **Vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **PDV** &gt; **Mises en page de l'écran**.</span><span class="sxs-lookup"><span data-stu-id="df145-111">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="df145-112">Utilisez le filtre rapide pour accéder à l'écran auquel vous souhaitez ajouter le contrôle.</span><span class="sxs-lookup"><span data-stu-id="df145-112">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="df145-113">Par exemple, filtrez le champ **ID mise en page de l'écran** à l'aide de la valeur **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="df145-113">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="df145-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="df145-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="df145-115">Par exemple, sélectionnez **Nom : F2CP16:9M ID mise en page de l'écran : F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="df145-115">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="df145-116">Cliquez sur **Concepteur de mise en page**.</span><span class="sxs-lookup"><span data-stu-id="df145-116">Click **Layout designer**.</span></span>
5. <span data-ttu-id="df145-117">Suivez les invites pour lancer le concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="df145-117">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="df145-118">Lorsque vous êtes invité à entrer vos informations d'identification, entrez les mêmes informations d'identification que celles utilisées lors du lancement du concepteur de mise en page dans la page **Mises en page de l'écran**.</span><span class="sxs-lookup"><span data-stu-id="df145-118">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="df145-119">Lorsque vous vous connectez, une page similaire à celle illustrée ci-dessous s'affiche.</span><span class="sxs-lookup"><span data-stu-id="df145-119">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="df145-120">La mise en page diffère selon les personnalisations que vous avez apportées à votre magasin.</span><span class="sxs-lookup"><span data-stu-id="df145-120">The layout will be different depending on the customizations that were made for your store.</span></span>

    <span data-ttu-id="df145-121">[![Concepteur de mise en page](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="df145-121">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="df145-122">Choisir une option d'affichage</span><span class="sxs-lookup"><span data-stu-id="df145-122">Choose a display option</span></span>

<span data-ttu-id="df145-123">Deux options de configuration sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="df145-123">There are two configurations options available.</span></span> <span data-ttu-id="df145-124">Choisissez l'option qui convient le mieux pour votre magasin, puis suivez les instructions restantes pour terminer le paramétrage du contrôle.</span><span class="sxs-lookup"><span data-stu-id="df145-124">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="df145-125">Les deux options sont :</span><span class="sxs-lookup"><span data-stu-id="df145-125">The two options are:</span></span>

- <span data-ttu-id="df145-126">Les recommandations sont toujours visibles.</span><span class="sxs-lookup"><span data-stu-id="df145-126">Recommendations are always visible.</span></span>
- <span data-ttu-id="df145-127">Un onglet **Recommandations** s'affiche dans la grille à droite de l'écran.</span><span class="sxs-lookup"><span data-stu-id="df145-127">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="df145-128">Rendre les recommandations toujours visibles</span><span class="sxs-lookup"><span data-stu-id="df145-128">Make recommendations always visible</span></span>

1. <span data-ttu-id="df145-129">Réduisez la hauteur de la zone des détails des lignes de transaction de manière à ce qu'elle soit identique à celle du volet Client à sa gauche.</span><span class="sxs-lookup"><span data-stu-id="df145-129">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>

    <span data-ttu-id="df145-130">[![Hauteur de la zone de détails des lignes de transaction réduite](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="df145-130">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="df145-131">Dans le menu à gauche, déplacez le contrôle de recommandations entre la zone des détails des lignes de transaction et le groupe de boutons en bas au centre de l'écran de transaction.</span><span class="sxs-lookup"><span data-stu-id="df145-131">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="df145-132">Redimensionnez le contrôle de manière à l'ajuster dans cet espace.</span><span class="sxs-lookup"><span data-stu-id="df145-132">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="df145-133">[![Contrôle de recommandations ajouté à la disposition](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="df145-133">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>

3. <span data-ttu-id="df145-134">Cliquez sur **X** pour enregistrer et fermer le concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="df145-134">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="df145-135">Dans Dynamics 365 for Retail, accédez à **Vente au détail** &gt; **Informatique de vente au détail** &gt; **Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="df145-135">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="df145-136">Dans la liste, sélectionnez  **Caisses enregistreuses 1090**.</span><span class="sxs-lookup"><span data-stu-id="df145-136">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="df145-137">Cliquez sur **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="df145-137">Click **Run now**.</span></span>

### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="df145-138">Ajouter un onglet Recommandations au groupe de boutons à droite de l'écran</span><span class="sxs-lookup"><span data-stu-id="df145-138">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="df145-139">Cliquez avec le bouton droit dans l'espace vide sous le dernier onglet du groupe de boutons situé à droite de la page.</span><span class="sxs-lookup"><span data-stu-id="df145-139">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2. <span data-ttu-id="df145-140">Cliquez sur **Personnaliser**.</span><span class="sxs-lookup"><span data-stu-id="df145-140">Click **Customize**.</span></span>

    <span data-ttu-id="df145-141">[![Personnalisation - Boîte de dialogue Contrôle de l'onglet](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="df145-141">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="df145-142">Cliquez sur **Nouvel onglet**.</span><span class="sxs-lookup"><span data-stu-id="df145-142">Click **New tab**.</span></span>
4. <span data-ttu-id="df145-143">Recherchez le nouvel onglet que vous venez d'ajouter.</span><span class="sxs-lookup"><span data-stu-id="df145-143">Find the new tab that you just added.</span></span> <span data-ttu-id="df145-144">Vous devrez peut-être faire défiler l'écran vers le bas.</span><span class="sxs-lookup"><span data-stu-id="df145-144">You may need to scroll down.</span></span>
5. <span data-ttu-id="df145-145">Dans la liste déroulante **Contenu**, sélectionnez **Produits recommandés**.</span><span class="sxs-lookup"><span data-stu-id="df145-145">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="df145-146">[![Sélection de Produits recommandés dans le champ Contenu](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="df145-146">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="df145-147">Dans le champ **Libellé**, saisissez un nom pour l'onglet de recommandations. Par exemple, saisissez « Produits recommandés ».</span><span class="sxs-lookup"><span data-stu-id="df145-147">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="df145-148">Dans le champ **Image**, sélectionnez l'image à afficher sous l'onglet.</span><span class="sxs-lookup"><span data-stu-id="df145-148">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="df145-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="df145-149">Click **OK**.</span></span> <span data-ttu-id="df145-150">Le nouvel onglet apparaît dans le groupe de boutons.</span><span class="sxs-lookup"><span data-stu-id="df145-150">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="df145-151">Cliquez sur **X** pour enregistrer et fermer le concepteur de mise en page.</span><span class="sxs-lookup"><span data-stu-id="df145-151">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="df145-152">Dans Dynamics 365 for Retail, accédez à **Vente au détail** &gt; **Informatique de vente au détail** &gt; **Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="df145-152">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="df145-153">Dans la liste, sélectionnez **Caisses enregistreuses 1090**.</span><span class="sxs-lookup"><span data-stu-id="df145-153">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="df145-154">Cliquez sur **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="df145-154">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df145-155">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="df145-155">Additional resources</span></span>

[<span data-ttu-id="df145-156">Vue d'ensemble des recommandations produit personnalisées</span><span class="sxs-lookup"><span data-stu-id="df145-156">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)
