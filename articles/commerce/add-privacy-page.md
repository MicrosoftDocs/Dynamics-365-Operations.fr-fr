---
title: Ajouter une page de stratégie de confidentialité
description: Cette rubrique décrit comment ajouter une page de stratégie de confidentialité à votre site dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/08/2020
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
ms.openlocfilehash: fd39ff5f8c5d97f2d524043b65627dc7e87fcf64
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946013"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="67ac8-103">Ajouter une page de stratégie de confidentialité</span><span class="sxs-lookup"><span data-stu-id="67ac8-103">Add a privacy policy page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="67ac8-104">Cette rubrique décrit comment ajouter une page de stratégie de confidentialité à votre site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="67ac8-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="67ac8-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="67ac8-105">Overview</span></span>

<span data-ttu-id="67ac8-106">Le respect de la confidentialité comprend des mesures organisationnelles qui informent les utilisateurs du site sur la façon dont leurs données sont collectées et traitées.</span><span class="sxs-lookup"><span data-stu-id="67ac8-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="67ac8-107">Les utilisateurs peuvent alors décider comment ils souhaitent que leurs données personnelles soient traitées et peuvent prendre les mesures appropriées.</span><span class="sxs-lookup"><span data-stu-id="67ac8-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="67ac8-108">Consulter la Déclaration de confidentialité Microsoft dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="67ac8-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="67ac8-109">Pour consulter la Déclaration de confidentialité Microsoft lorsque vous êtes connecté aux outils de création Dynamics 365 Commerce, cliquez sur le bouton **Aide** (**?**) dans le coin supérieur droit, puis sélectionnez **Confidentialité et cookies**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="67ac8-110">Un nouvel onglet s'ouvre avec un lien vers la [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="67ac8-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="67ac8-111">Générer une page de stratégie de confidentialité pour votre site</span><span class="sxs-lookup"><span data-stu-id="67ac8-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="67ac8-112">Dans Dynamics 365 Commerce, il existe plusieurs façons de permettre aux utilisateurs de votre site d'accéder à votre stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="67ac8-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="67ac8-113">Cette section montre comment créer une page de stratégie de confidentialité, puis référencer la page à l'aide d'un fragment de pied de page.</span><span class="sxs-lookup"><span data-stu-id="67ac8-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="67ac8-114">Les conseils qui suivent sont un exemple qui montre comment créer une page de stratégie de confidentialité générique pour un site Commerce.</span><span class="sxs-lookup"><span data-stu-id="67ac8-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="67ac8-115">Vous êtes responsable de la conception et de la mise en œuvre d'une solution de page de stratégie de confidentialité qui répond le mieux aux exigences légales de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="67ac8-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="67ac8-116">Pour commencer, dans les outils de création, accédez au site pour lequel vous souhaitez créer une page de stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="67ac8-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="67ac8-117">Créer un modèle</span><span class="sxs-lookup"><span data-stu-id="67ac8-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="67ac8-118">Si un modèle pouvant être utilisé pour la page de stratégie de confidentialité a déjà été créé, passez directement à la section [Créer une page de stratégie de confidentialité](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="67ac8-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="67ac8-119">Pour créer un modèle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="67ac8-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="67ac8-120">Accédez à **Modèles \> Nouveau modèle**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-120">Go to **Templates \> New Template**.</span></span>
1. <span data-ttu-id="67ac8-121">Entrez le nom du modèle, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-121">Enter the template name, and then select **OK**.</span></span>
1. <span data-ttu-id="67ac8-122">Dans le modèle, ajoutez tous les modules requis aux emplacements de page requis.</span><span class="sxs-lookup"><span data-stu-id="67ac8-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="67ac8-123">Pour vous guider, passez la souris sur les points d'exclamation rouges.</span><span class="sxs-lookup"><span data-stu-id="67ac8-123">For guidance, hover over the red exclamation marks.</span></span>

    <span data-ttu-id="67ac8-124">Par exemple, l'emplacement **En-tête HTML** peut nécessiter un module de **Script externe par défaut**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-124">For example, the **HTML Head** slot might require a **Default External Script** module.</span></span>

1. <span data-ttu-id="67ac8-125">Dans l'emplacement **Corps**, ajoutez un module de **Page par défaut**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="67ac8-126">Dans le module **Page par défaut**, à l'emplacement **Principal**, ajoutez un module de **Bloc de contenu riche**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="67ac8-127">Dans le module **Bloc riche en contenu**, ajoutez un module **Élément de bloc riche en contenu**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="67ac8-128">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="67ac8-128">Check the template in, and publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="67ac8-129">Générer une page de stratégie de confidentialité</span><span class="sxs-lookup"><span data-stu-id="67ac8-129">Build a privacy policy page</span></span>

<span data-ttu-id="67ac8-130">Pour générer une page de stratégie de confidentialité, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="67ac8-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="67ac8-131">Accédez à **Pages \> Nouvelle page**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-131">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="67ac8-132">Sélectionnez le modèle de la page de stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="67ac8-132">Select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="67ac8-133">Entrez le nom et l'URL d'une page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-133">Enter a page name and URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="67ac8-134">À l'emplacement **Principal** de la page, ajoutez un module **Bloc de contenu riche**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="67ac8-135">Dans le module **Bloc riche en contenu**, ajoutez un module **Élément de bloc riche en contenu**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="67ac8-136">Dans le volet des propriétés du module **Bloc riche en contenu**, sélectionnez **Ajouter une source de données**, puis sélectionnez **Contenu en texte enrichi**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="67ac8-137">Dans l'éditeur de texte enrichi, entrez le contenu de la page de stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="67ac8-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="67ac8-138">Développez l'éditeur de texte enrichi en mode plein écran selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="67ac8-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="67ac8-139">Une fois le contenu saisi, sélectionnez **Aperçu** pour prévisualiser la page dans le navigateur web.</span><span class="sxs-lookup"><span data-stu-id="67ac8-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="67ac8-140">Effectuez tous les ajouts restants aux propriétés de la page et du module.</span><span class="sxs-lookup"><span data-stu-id="67ac8-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="67ac8-141">Archivez la page de stratégie de confidentialité, et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="67ac8-141">Check the privacy policy page in, and publish it.</span></span>

<span data-ttu-id="67ac8-142">Pour publier l'URL de la page de stratégie de confidentialité, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="67ac8-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="67ac8-143">Allez à **URL**et sélectionnez l'URL de la page de stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="67ac8-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="67ac8-144">Publier l'URL sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="67ac8-144">Publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="67ac8-145">Créer un lien vers la page de stratégie de confidentialité dans un pied de page</span><span class="sxs-lookup"><span data-stu-id="67ac8-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="67ac8-146">Vous pouvez ajouter un lien vers la page de stratégie de confidentialité à un fragment.</span><span class="sxs-lookup"><span data-stu-id="67ac8-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="67ac8-147">De cette façon, vous pouvez partager le lien et le mettre à jour sur plusieurs pages de site en référençant le fragment.</span><span class="sxs-lookup"><span data-stu-id="67ac8-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="67ac8-148">Cet exemple montre comment ajouter un lien vers la page de stratégie de confidentialité à un fragment de pied de page.</span><span class="sxs-lookup"><span data-stu-id="67ac8-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="67ac8-149">Pour ajouter un lien à un fragment de pied de page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="67ac8-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="67ac8-150">Accédez à **Fragments de page \> Nouveau fragment de page**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-150">Go to **Page Fragments \> New Page Fragment**.</span></span>
1. <span data-ttu-id="67ac8-151">Sélectionnez le module **Pied de page**, puis entrez un nom dans le champ **Nom du fragment de page**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-151">Select the **Footer** module, and then enter a name in the **Page Fragment Name** field.</span></span>
1. <span data-ttu-id="67ac8-152">Dans l'emplacement **Catégorie de pied de page**, ajoutez un module **Élément de pied de page**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-152">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="67ac8-153">Dans le volet de propriétés de droite, sélectionnez **Texte du lien**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-153">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="67ac8-154">Dans la boîte de dialogue **Texte du lien**, entrez le texte du lien et la cible du lien de la page de stratégie de confidentialité, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="67ac8-154">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>

    <span data-ttu-id="67ac8-155">Pour obtenir l'URL de la page de stratégie de confidentialité, accédez à **Pages**, accédez à la page de stratégie de confidentialité et copiez l'URL à partir du volet des propriétés.</span><span class="sxs-lookup"><span data-stu-id="67ac8-155">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>

1. <span data-ttu-id="67ac8-156">Enregistrez le fragment, archivez-le, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="67ac8-156">Save the fragment, check it in, and publish it.</span></span>
1. <span data-ttu-id="67ac8-157">Prévisualisez le fragment et testez le lien vers la page de la stratégie de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="67ac8-157">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="67ac8-158">Le fragment peut maintenant être référencé dans le modèle pour d'autres pages de site.</span><span class="sxs-lookup"><span data-stu-id="67ac8-158">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="67ac8-159">Lorsque ce fragment est référencé dans le module **Pied de page** d'un modèle, la référence du lien apparaîtra sur toutes les pages créées à l'aide de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="67ac8-159">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="67ac8-160">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="67ac8-160">Additional resources</span></span>

[<span data-ttu-id="67ac8-161">Vue d'ensemble de la conformité</span><span class="sxs-lookup"><span data-stu-id="67ac8-161">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="67ac8-162">Fonctionnalités d'accessibilité</span><span class="sxs-lookup"><span data-stu-id="67ac8-162">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="67ac8-163">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="67ac8-163">Cookie compliance</span></span>](cookie-compliance.md)
