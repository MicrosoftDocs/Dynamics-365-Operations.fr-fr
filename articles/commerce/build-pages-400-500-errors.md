---
title: Établir des pages personnalisées de réponse pour les erreurs de code statut 4xx/5xx
description: Cette rubrique décrit la procédure de création de pages de réponse personnalisées pour les erreurs de code statut 4xx et 5xx à l’aide des outils de création dans Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b35b3c07b1edd41e6a3763c0001529e125e4636
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799643"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="180fd-103">Établir des pages personnalisées de réponse pour les erreurs de code statut 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="180fd-103">Build custom response pages for 4xx/5xx status code errors</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="180fd-104">Cette rubrique décrit la procédure de création de pages de réponse personnalisées pour les erreurs de code statut 4xx et 5xx à l’aide des outils de création dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="180fd-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="180fd-105">Si une demande échoue, le serveur publie des réponses d’erreur du code statut HTTP.</span><span class="sxs-lookup"><span data-stu-id="180fd-105">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="180fd-106">Le code statut 404 est capturé et renvoyé si une page est introuvable, et le code statut 500 est capturé et renvoyé si une erreur de serveur est produit.</span><span class="sxs-lookup"><span data-stu-id="180fd-106">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="180fd-107">Dans Dynamics 365 Commerce, les utilisateurs de l’application peuvent générer les pages de réponse d’erreur du code statut personnalisées affichées aux utilisateurs pour ces réponses d’erreur du code statut.</span><span class="sxs-lookup"><span data-stu-id="180fd-107">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="180fd-108">Générer une page de réponse d’erreur du code statut</span><span class="sxs-lookup"><span data-stu-id="180fd-108">Build a status code error response page</span></span>

<span data-ttu-id="180fd-109">Pour commencer à générer une page de réponse d’erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="180fd-109">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="180fd-110">Dans votre navigateur web préféré, connectez-vous à Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="180fd-110">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="180fd-111">Sélectionnez le site pour lequel vous souhaitez créer une page de réponse d’erreur du code statut 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="180fd-111">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="180fd-112">Générer le modèle</span><span class="sxs-lookup"><span data-stu-id="180fd-112">Build the template</span></span>

<span data-ttu-id="180fd-113">Pour générer le modèle pour une page de réponse d’erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="180fd-113">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="180fd-114">Accédez à **Modèles**.</span><span class="sxs-lookup"><span data-stu-id="180fd-114">Go to **Templates**.</span></span>
1. <span data-ttu-id="180fd-115">Sélectionnez **Nouveau** pour créer un modèle de page.</span><span class="sxs-lookup"><span data-stu-id="180fd-115">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="180fd-116">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le nouveau modèle, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="180fd-116">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="180fd-117">Paramétrez le modèle, selon la structure de votre choix que vous voulez que la page de réponse d’erreur du code statut ait.</span><span class="sxs-lookup"><span data-stu-id="180fd-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="180fd-118">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="180fd-118">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="180fd-119">Générer la page de réponse d’erreur du code statut</span><span class="sxs-lookup"><span data-stu-id="180fd-119">Build the status code error response page</span></span>

<span data-ttu-id="180fd-120">Pour générer la page de réponse d’erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="180fd-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="180fd-121">Accédez à **Pages**.</span><span class="sxs-lookup"><span data-stu-id="180fd-121">Go to **Pages**.</span></span>
1. <span data-ttu-id="180fd-122">Sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="180fd-122">Select **New** to create a page.</span></span>
1. <span data-ttu-id="180fd-123">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez un modèle, puis, sous **Nom de la page**, entrez un nom pour la page de réponse d’erreur du code statut.</span><span class="sxs-lookup"><span data-stu-id="180fd-123">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="180fd-124">Laissez le champ **URL de la page** vide.</span><span class="sxs-lookup"><span data-stu-id="180fd-124">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="180fd-125">Générez la page.</span><span class="sxs-lookup"><span data-stu-id="180fd-125">Build the page.</span></span>
1. <span data-ttu-id="180fd-126">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="180fd-126">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="180fd-127">Vous pouvez créer des pages séparées de réponse d’erreur du code statut pour les erreurs du code statut 4xx et 5xx.</span><span class="sxs-lookup"><span data-stu-id="180fd-127">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="180fd-128">Sinon, vous pouvez utiliser la même page générale de réponse d’erreur du code statut pour les deux catégories d’erreur.</span><span class="sxs-lookup"><span data-stu-id="180fd-128">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="180fd-129">Paramétrer une redirection pour la page de réponse d’erreur du code statut</span><span class="sxs-lookup"><span data-stu-id="180fd-129">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="180fd-130">Pour configurer une redirection de la page de réponse d’erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="180fd-130">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="180fd-131">Accédez à **URL \> Nouveau \> Nouvel alias**, puis sélectionnez la page de réponse d’erreur du code statut que vous avez paramétrée auparavant.</span><span class="sxs-lookup"><span data-stu-id="180fd-131">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="180fd-132">Dans le champ **Alias**, entrez **default-4xx** ou **default-5xx**, en fonction de la page de réponse d’erreur du code statut pour laquelle vous paramétrez une redirection.</span><span class="sxs-lookup"><span data-stu-id="180fd-132">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="180fd-133">Ces alias doivent être publiés.</span><span class="sxs-lookup"><span data-stu-id="180fd-133">These aliases must be published.</span></span> <span data-ttu-id="180fd-134">Sinon, la redirection ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="180fd-134">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="180fd-135">Sélectionnez **OK** pour valider la liaison.</span><span class="sxs-lookup"><span data-stu-id="180fd-135">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="180fd-136">Si vous utilisez une seule page de réponse d’erreur du code statut pour les deux catégories d’erreur, répétez la procédure pour lier un alias pour l’autre catégorie d’erreur à la même page.</span><span class="sxs-lookup"><span data-stu-id="180fd-136">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="180fd-137">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="180fd-137">Additional resources</span></span>

[<span data-ttu-id="180fd-138">Utiliser des modèles</span><span class="sxs-lookup"><span data-stu-id="180fd-138">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="180fd-139">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="180fd-139">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="180fd-140">Créer une URL de page</span><span class="sxs-lookup"><span data-stu-id="180fd-140">Create a page URL</span></span>](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
