---
title: Établir des pages personnalisées de réponse pour les erreurs de code statut 4xx/5xx
description: Cette rubrique décrit la procédure de création de pages de réponse personnalisées pour les erreurs de code statut 4xx et 5xx à l’aide des outils de création dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ee2f74581ded6020d075377f931c465d7c89f9e5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211103"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="88c70-103">Établir des pages personnalisées de réponse pour les erreurs de code statut 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="88c70-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="88c70-104">Cette rubrique décrit la procédure de création de pages de réponse personnalisées pour les erreurs de code statut 4xx et 5xx à l’aide des outils de création dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="88c70-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="88c70-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="88c70-105">Overview</span></span>

<span data-ttu-id="88c70-106">Si une demande échoue, le serveur publie des réponses d'erreur du code statut HTTP.</span><span class="sxs-lookup"><span data-stu-id="88c70-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="88c70-107">Le code statut 404 est capturé et renvoyé si une page est introuvable, et le code statut 500 est capturé et renvoyé si une erreur de serveur est produit.</span><span class="sxs-lookup"><span data-stu-id="88c70-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="88c70-108">Dans Dynamics 365 Commerce, les utilisateurs de l'application peuvent générer les pages de réponse d'erreur du code statut personnalisées affichées aux utilisateurs pour ces réponses d'erreur du code statut.</span><span class="sxs-lookup"><span data-stu-id="88c70-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="88c70-109">Générer une page de réponse d'erreur du code statut</span><span class="sxs-lookup"><span data-stu-id="88c70-109">Build a status code error response page</span></span>

<span data-ttu-id="88c70-110">Pour commencer à générer une page de réponse d'erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="88c70-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="88c70-111">Dans votre navigateur web préféré, connectez-vous à Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="88c70-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="88c70-112">Sélectionnez le site pour lequel vous souhaitez créer une page de réponse d'erreur du code statut 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="88c70-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="88c70-113">Générer le modèle</span><span class="sxs-lookup"><span data-stu-id="88c70-113">Build the template</span></span>

<span data-ttu-id="88c70-114">Pour générer le modèle pour une page de réponse d'erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="88c70-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="88c70-115">Accédez à **Modèles**.</span><span class="sxs-lookup"><span data-stu-id="88c70-115">Go to **Templates**.</span></span>
1. <span data-ttu-id="88c70-116">Sélectionnez **Nouveau** pour créer un modèle de page.</span><span class="sxs-lookup"><span data-stu-id="88c70-116">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="88c70-117">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le nouveau modèle, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="88c70-117">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="88c70-118">Paramétrez le modèle, selon la structure de votre choix que vous voulez que la page de réponse d'erreur du code statut ait.</span><span class="sxs-lookup"><span data-stu-id="88c70-118">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="88c70-119">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="88c70-119">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="88c70-120">Générer la page de réponse d'erreur du code statut</span><span class="sxs-lookup"><span data-stu-id="88c70-120">Build the status code error response page</span></span>

<span data-ttu-id="88c70-121">Pour générer la page de réponse d'erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="88c70-121">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="88c70-122">Accédez à **Pages**.</span><span class="sxs-lookup"><span data-stu-id="88c70-122">Go to **Pages**.</span></span>
1. <span data-ttu-id="88c70-123">Sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="88c70-123">Select **New** to create a page.</span></span>
1. <span data-ttu-id="88c70-124">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez un modèle, puis, sous **Nom de la page**, entrez un nom pour la page de réponse d'erreur du code statut.</span><span class="sxs-lookup"><span data-stu-id="88c70-124">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="88c70-125">Laissez le champ **URL de la page** vide.</span><span class="sxs-lookup"><span data-stu-id="88c70-125">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="88c70-126">Générez la page.</span><span class="sxs-lookup"><span data-stu-id="88c70-126">Build the page.</span></span>
1. <span data-ttu-id="88c70-127">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="88c70-127">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="88c70-128">Vous pouvez créer des pages séparées de réponse d'erreur du code statut pour les erreurs du code statut 4xx et 5xx.</span><span class="sxs-lookup"><span data-stu-id="88c70-128">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="88c70-129">Sinon, vous pouvez utiliser la même page générale de réponse d'erreur du code statut pour les deux catégories d'erreur.</span><span class="sxs-lookup"><span data-stu-id="88c70-129">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="88c70-130">Paramétrer une redirection pour la page de réponse d'erreur du code statut</span><span class="sxs-lookup"><span data-stu-id="88c70-130">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="88c70-131">Pour configurer une redirection de la page de réponse d'erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="88c70-131">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="88c70-132">Accédez à **URL \> Nouveau \> Nouvel alias**, puis sélectionnez la page de réponse d'erreur du code statut que vous avez paramétrée auparavant.</span><span class="sxs-lookup"><span data-stu-id="88c70-132">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="88c70-133">Dans le champ **Alias**, entrez **default-4xx** ou **default-5xx**, en fonction de la page de réponse d'erreur du code statut pour laquelle vous paramétrez une redirection.</span><span class="sxs-lookup"><span data-stu-id="88c70-133">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="88c70-134">Ces alias doivent être publiés.</span><span class="sxs-lookup"><span data-stu-id="88c70-134">These aliases must be published.</span></span> <span data-ttu-id="88c70-135">Sinon, la redirection ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="88c70-135">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="88c70-136">Sélectionnez **OK** pour valider la liaison.</span><span class="sxs-lookup"><span data-stu-id="88c70-136">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="88c70-137">Si vous utilisez une seule page de réponse d'erreur du code statut pour les deux catégories d'erreur, répétez la procédure pour lier un alias pour l'autre catégorie d'erreur à la même page.</span><span class="sxs-lookup"><span data-stu-id="88c70-137">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88c70-138">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="88c70-138">Additional resources</span></span>

[<span data-ttu-id="88c70-139">Utiliser des modèles</span><span class="sxs-lookup"><span data-stu-id="88c70-139">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="88c70-140">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="88c70-140">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="88c70-141">Créer une URL de page</span><span class="sxs-lookup"><span data-stu-id="88c70-141">Create a page URL</span></span>](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]