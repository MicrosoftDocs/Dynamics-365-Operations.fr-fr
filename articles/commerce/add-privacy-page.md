---
title: Ajouter une page de stratégie de confidentialité
description: Cette rubrique décrit comment ajouter une page de stratégie de confidentialité à votre site dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 59a2d9712a73c607cf5521f8e79e8e2558854fc4
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3274209"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="ffb50-103">Ajouter une page de stratégie de confidentialité</span><span class="sxs-lookup"><span data-stu-id="ffb50-103">Add a privacy policy page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ffb50-104">Cette rubrique décrit comment ajouter une page de stratégie de confidentialité à votre site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ffb50-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ffb50-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="ffb50-105">Overview</span></span>

<span data-ttu-id="ffb50-106">Le respect de la confidentialité comprend des mesures organisationnelles qui informent les utilisateurs du site sur la façon dont leurs données sont collectées et traitées.</span><span class="sxs-lookup"><span data-stu-id="ffb50-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="ffb50-107">Les utilisateurs peuvent alors décider comment ils souhaitent que leurs données personnelles soient traitées et peuvent prendre les mesures appropriées.</span><span class="sxs-lookup"><span data-stu-id="ffb50-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="ffb50-108">Consulter la Déclaration de confidentialité Microsoft dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ffb50-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="ffb50-109">Pour consulter la Déclaration de confidentialité Microsoft lorsque vous êtes connecté aux outils de création Dynamics 365 Commerce, cliquez sur le bouton **Aide** (**?**) dans le coin supérieur droit, puis sélectionnez **Confidentialité et cookies**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="ffb50-110">Un nouvel onglet s'ouvre avec un lien vers la [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="ffb50-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="ffb50-111">Générer une page de stratégie de confidentialité pour votre site</span><span class="sxs-lookup"><span data-stu-id="ffb50-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="ffb50-112">Dans Dynamics 365 Commerce, il existe plusieurs façons de permettre aux utilisateurs de votre site d'accéder à votre stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="ffb50-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="ffb50-113">Cette section montre comment créer une page de stratégie de confidentialité, puis référencer la page à l'aide d'un fragment de pied de page.</span><span class="sxs-lookup"><span data-stu-id="ffb50-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="ffb50-114">Les conseils qui suivent sont un exemple qui montre comment créer une page de stratégie de confidentialité générique pour un site Commerce.</span><span class="sxs-lookup"><span data-stu-id="ffb50-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="ffb50-115">Vous êtes responsable de la conception et de la mise en œuvre d'une solution de page de stratégie de confidentialité qui répond le mieux aux exigences légales de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="ffb50-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="ffb50-116">Pour commencer, dans les outils de création, accédez au site pour lequel vous souhaitez créer une page de stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="ffb50-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="ffb50-117">Créer un modèle</span><span class="sxs-lookup"><span data-stu-id="ffb50-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="ffb50-118">Si un modèle pouvant être utilisé pour la page de stratégie de confidentialité a déjà été créé, passez directement à la section [Créer une page de stratégie de confidentialité](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="ffb50-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="ffb50-119">Pour créer un modèle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ffb50-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="ffb50-120">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un modèle de page.</span><span class="sxs-lookup"><span data-stu-id="ffb50-120">Go to **Templates**, and then select **New** to create a page template.</span></span>
1. <span data-ttu-id="ffb50-121">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de bannière promotionnelle**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-121">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="ffb50-122">Dans le modèle, ajoutez tous les modules requis aux emplacements de page requis.</span><span class="sxs-lookup"><span data-stu-id="ffb50-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="ffb50-123">Pour vous guider, passez la souris sur les points d'exclamation rouges.</span><span class="sxs-lookup"><span data-stu-id="ffb50-123">For guidance, hover over the red exclamation marks.</span></span> <span data-ttu-id="ffb50-124">(Par exemple, l'emplacement **En-tête HTML** peut nécessiter un module de **Script externe par défaut**.)</span><span class="sxs-lookup"><span data-stu-id="ffb50-124">(For example, the **HTML Head** slot might require a **Default External Script** module.)</span></span>
1. <span data-ttu-id="ffb50-125">Dans l'emplacement **Corps**, ajoutez un module de **Page par défaut**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="ffb50-126">Dans le module **Page par défaut**, à l'emplacement **Principal**, ajoutez un module de **Bloc de contenu riche**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="ffb50-127">Dans le module **Bloc riche en contenu**, ajoutez un module **Élément de bloc riche en contenu**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="ffb50-128">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="ffb50-128">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="ffb50-129">Générer une page de stratégie de confidentialité</span><span class="sxs-lookup"><span data-stu-id="ffb50-129">Build a privacy policy page</span></span>

<span data-ttu-id="ffb50-130">Pour générer une page de stratégie de confidentialité, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ffb50-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="ffb50-131">Accédez à **Pages**, puis cliquez sur **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="ffb50-131">Go to **Pages**, and then select **New** to create a page.</span></span>
1. <span data-ttu-id="ffb50-132">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle de la page de politique de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="ffb50-132">In the **Choose a template** dialog box, select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="ffb50-133">Entrez le nom et l'URL d'une page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-133">Enter a page name and page URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="ffb50-134">À l'emplacement **Principal** de la page, ajoutez un module **Bloc de contenu riche**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="ffb50-135">Dans le module **Bloc riche en contenu**, ajoutez un module **Élément de bloc riche en contenu**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="ffb50-136">Dans le volet des propriétés du module **Bloc riche en contenu**, sélectionnez **Ajouter une source de données**, puis sélectionnez **Contenu en texte enrichi**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="ffb50-137">Dans l'éditeur de texte enrichi, entrez le contenu de la page de stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="ffb50-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="ffb50-138">Développez l'éditeur de texte enrichi en mode plein écran selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ffb50-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="ffb50-139">Une fois le contenu saisi, sélectionnez **Aperçu** pour prévisualiser la page dans le navigateur web.</span><span class="sxs-lookup"><span data-stu-id="ffb50-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="ffb50-140">Effectuez tous les ajouts restants aux propriétés de la page et du module.</span><span class="sxs-lookup"><span data-stu-id="ffb50-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="ffb50-141">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="ffb50-141">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="ffb50-142">Pour publier l'URL de la page de stratégie de confidentialité, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ffb50-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="ffb50-143">Allez à **URL**et sélectionnez l'URL de la page de stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="ffb50-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="ffb50-144">Sélectionnez **Publier** pour publier l'URL sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ffb50-144">Select **Publish** to publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="ffb50-145">Créer un lien vers la page de stratégie de confidentialité dans un pied de page</span><span class="sxs-lookup"><span data-stu-id="ffb50-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="ffb50-146">Vous pouvez ajouter un lien vers la page de stratégie de confidentialité à un fragment.</span><span class="sxs-lookup"><span data-stu-id="ffb50-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="ffb50-147">De cette façon, vous pouvez partager le lien et le mettre à jour sur plusieurs pages de site en référençant le fragment.</span><span class="sxs-lookup"><span data-stu-id="ffb50-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="ffb50-148">Cet exemple montre comment ajouter un lien vers la page de stratégie de confidentialité à un fragment de pied de page.</span><span class="sxs-lookup"><span data-stu-id="ffb50-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="ffb50-149">Pour ajouter un lien à un fragment de pied de page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ffb50-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="ffb50-150">Accédez à **Fragments de page**, puis cliquez sur **Nouveau** pour créer un fragment de page.</span><span class="sxs-lookup"><span data-stu-id="ffb50-150">Go to **Page Fragments**, and then select **New** to create a page fragment.</span></span>
1. <span data-ttu-id="ffb50-151">Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez le module **Pied de page**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-151">In the **New Page Fragment** dialog box, select the **Footer** module.</span></span>
1. <span data-ttu-id="ffb50-152">Sous **Nom du fragment de page**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-152">Under **Page Fragment Name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="ffb50-153">Dans l'emplacement **Catégorie de pied de page**, ajoutez un module **Élément de pied de page**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-153">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="ffb50-154">Dans le volet de propriétés de droite, sélectionnez **Texte du lien**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-154">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="ffb50-155">Dans la boîte de dialogue **Texte du lien**, entrez le texte du lien et la cible du lien de la page de stratégie de confidentialité, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffb50-155">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>
1. <span data-ttu-id="ffb50-156">Pour obtenir l'URL de la page de stratégie de confidentialité, accédez à **Pages**, accédez à la page de stratégie de confidentialité et copiez l'URL à partir du volet des propriétés.</span><span class="sxs-lookup"><span data-stu-id="ffb50-156">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>
1. <span data-ttu-id="ffb50-157">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="ffb50-157">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ffb50-158">Prévisualisez le fragment et testez le lien vers la page de la stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="ffb50-158">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="ffb50-159">Le fragment peut maintenant être référencé dans le modèle pour d'autres pages de site.</span><span class="sxs-lookup"><span data-stu-id="ffb50-159">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="ffb50-160">Lorsque ce fragment est référencé dans le module **Pied de page** d'un modèle, la référence du lien apparaîtra sur toutes les pages créées à l'aide de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="ffb50-160">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ffb50-161">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ffb50-161">Additional resources</span></span>

[<span data-ttu-id="ffb50-162">Vue d'ensemble de la conformité</span><span class="sxs-lookup"><span data-stu-id="ffb50-162">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="ffb50-163">Fonctionnalités d'accessibilité</span><span class="sxs-lookup"><span data-stu-id="ffb50-163">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="ffb50-164">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="ffb50-164">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="ffb50-165">Remplacer les ID utilisateur associés aux modifications de contenu suivies</span><span class="sxs-lookup"><span data-stu-id="ffb50-165">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)
