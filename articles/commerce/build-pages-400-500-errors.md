---
title: Établir des pages personnalisées de réponse pour les erreurs de code statut 4xx/5xx
description: Cette rubrique décrit la procédure d'établir les pages de réponse personnalisées pour les erreurs de code statut 4xx et 5xx à l'aide des outils de création dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bcceeb1bc68c6432442c863ca06b7ba81d0abed8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697104"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="9c8bc-103">Établir des pages personnalisées de réponse pour les erreurs de code statut 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="9c8bc-103">Build custom response pages for 4xx/5xx status code errors</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="9c8bc-104">Cette rubrique décrit la procédure d'établir les pages de réponse personnalisées pour les erreurs de code statut 4xx et 5xx à l'aide des outils de création dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9c8bc-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="9c8bc-105">Overview</span></span>

<span data-ttu-id="9c8bc-106">Si une demande échoue, le serveur publie des réponses d'erreur du code statut HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="9c8bc-107">Le code statut 404 est capturé et renvoyé si une page est introuvable, et le code statut 500 est capturé et renvoyé si une erreur de serveur est produit.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="9c8bc-108">Dans Dynamics 365 Commerce, les utilisateurs de l'application peuvent générer les pages de réponse d'erreur du code statut personnalisées affichées aux utilisateurs pour ces réponses d'erreur du code statut.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="9c8bc-109">Générer une page de réponse d'erreur du code statut</span><span class="sxs-lookup"><span data-stu-id="9c8bc-109">Build a status code error response page</span></span>

<span data-ttu-id="9c8bc-110">Pour commencer à générer une page de réponse d'erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="9c8bc-111">Dans votre navigateur web préféré, connectez-vous à Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="9c8bc-112">Sélectionnez le site pour lequel vous souhaitez créer une page de réponse d'erreur du code statut 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="9c8bc-113">Générer le modèle</span><span class="sxs-lookup"><span data-stu-id="9c8bc-113">Build the template</span></span>

<span data-ttu-id="9c8bc-114">Pour générer le modèle pour une page de réponse d'erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="9c8bc-115">Accédez à **Modèles \> Nouveau modèle**.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-115">Go to **Templates \> New template**.</span></span>
1. <span data-ttu-id="9c8bc-116">Nommez le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-116">Name the new template.</span></span>
1. <span data-ttu-id="9c8bc-117">Paramétrez le modèle, selon la structure de votre choix que vous voulez que la page de réponse d'erreur du code statut ait.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="9c8bc-118">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-118">Check the template in, and publish it.</span></span>

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="9c8bc-119">Générer la page de réponse d'erreur du code statut</span><span class="sxs-lookup"><span data-stu-id="9c8bc-119">Build the status code error response page</span></span>

<span data-ttu-id="9c8bc-120">Pour générer la page de réponse d'erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="9c8bc-121">Accédez à **Pages \> Nouvelle page**.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-121">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="9c8bc-122">Nommez la page de réponse d'erreur du code statut, mais ne définissez **pas** le champ **URL**.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-122">Name the status code error response page, but do **not** set the **URL** field.</span></span>
1. <span data-ttu-id="9c8bc-123">Générez la page.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-123">Build the page.</span></span>
1. <span data-ttu-id="9c8bc-124">Archivez la page, et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-124">Check the page in, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="9c8bc-125">Vous pouvez créer des pages séparées de réponse d'erreur du code statut pour les erreurs du code statut 4xx et 5xx.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-125">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="9c8bc-126">Sinon, vous pouvez utiliser la même page générale de réponse d'erreur du code statut pour les deux catégories d'erreur.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-126">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="9c8bc-127">Paramétrer une redirection pour la page de réponse d'erreur du code statut</span><span class="sxs-lookup"><span data-stu-id="9c8bc-127">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="9c8bc-128">Pour configurer une redirection de la page de réponse d'erreur du code statut, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-128">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="9c8bc-129">Accédez à **URL \> Nouveau \> Nouvel alias**, puis sélectionnez la page de réponse d'erreur du code statut que vous avez paramétrée auparavant.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-129">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="9c8bc-130">Dans le champ **Alias**, entrez **default-4xx** ou **default-5xx**, en fonction de la page de réponse d'erreur du code statut pour laquelle vous paramétrez une redirection.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-130">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="9c8bc-131">Ces alias doivent être publiés.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-131">These aliases must be published.</span></span> <span data-ttu-id="9c8bc-132">Sinon, la redirection ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-132">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="9c8bc-133">Sélectionnez **OK** pour valider la liaison.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-133">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="9c8bc-134">Si vous utilisez une seule page de réponse d'erreur du code statut pour les deux catégories d'erreur, répétez la procédure pour lier un alias pour l'autre catégorie d'erreur à la même page.</span><span class="sxs-lookup"><span data-stu-id="9c8bc-134">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c8bc-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9c8bc-135">Additional resources</span></span>

[<span data-ttu-id="9c8bc-136">Utiliser des modèles</span><span class="sxs-lookup"><span data-stu-id="9c8bc-136">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="9c8bc-137">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="9c8bc-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="9c8bc-138">Créer une URL de page</span><span class="sxs-lookup"><span data-stu-id="9c8bc-138">Create a page URL</span></span>](create-page-url.md)
