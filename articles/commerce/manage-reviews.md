---
title: Gestion des évaluations et avis
description: Cette rubrique explique comment gérer les classements et les évaluations à l'aide de l'outil de modération des classements et des évaluations de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a7fa2ae3124a0a68b3890987c5dce2730e5c2183
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027240"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="d0f8a-103">Gestion des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="d0f8a-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d0f8a-104">Cette rubrique explique comment gérer les classements et les évaluations à l'aide de l'outil de modération des classements et des évaluations de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-104">This topic explains how to manage ratings and reviews by using the Microsoft Dynamics 365 Commerce ratings and reviews moderation tool.</span></span>

## <a name="overview"></a><span data-ttu-id="d0f8a-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="d0f8a-105">Overview</span></span>

<span data-ttu-id="d0f8a-106">Dynamics 365 Commerce utilise le service cognitif de Microsoft Azure pour modérer automatiquement du texte d'évaluation en effaçant les mots grossiers.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="d0f8a-107">En outre, les modérateurs peuvent utiliser l'outil de modération des classements et des évaluations pour les tâches manuelles suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0f8a-107">In addition, moderators can use the ratings and reviews moderation tool for the following manual tasks:</span></span>

- <span data-ttu-id="d0f8a-108">Modérez les évaluations en y répondant ou en les supprimant.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="d0f8a-109">Supprimez les évaluations d'un client à la demande du client.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="d0f8a-110">Importez en bloc les données des classements et des évaluations pour tous les produits dans un modèle Microsoft Power BI, afin que les tendances des classements et des évaluations puissent être analysées.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="access-ratings-and-reviews-moderation-features"></a><span data-ttu-id="d0f8a-111">Accéder aux fonctionnalités de modération des classements et des révisions</span><span class="sxs-lookup"><span data-stu-id="d0f8a-111">Access ratings and reviews moderation features</span></span>

<span data-ttu-id="d0f8a-112">Pour accéder aux fonctionnalités de modération des classements et des révisions dans l'outil de gestion du site de commerce électronique, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-112">To access ratings and reviews moderation features in the e-Commerce site management tool, follow these steps.</span></span>

1. <span data-ttu-id="d0f8a-113">Connectez-vous à [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="d0f8a-113">Sign in to [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="d0f8a-114">Ouvrir le projet contenant l'environnement dans lequel vous souhaitez initialiser le commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-114">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="d0f8a-115">Dans la section **Environnements**, sélectionnez l'environnement.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-115">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="d0f8a-116">Sous **Fonctions d'environnement**, sélectionnez **Gestion de la vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-116">Under **Environment features**, select **Retail manage**.</span></span>
1. <span data-ttu-id="d0f8a-117">Dans l'onglet **Commerce électronique**, sous **Liens**, sélectionnez **Outil de gestion du site de commerce électronique**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-117">On the **e-Commerce** tab under **Links**, select **e-Commerce Site management tool**.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="d0f8a-118">Lecture d'une évaluation</span><span class="sxs-lookup"><span data-stu-id="d0f8a-118">Read a review</span></span> 

1. <span data-ttu-id="d0f8a-119">Accédez à **Accueil \> Évaluations \> Modération**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-119">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="d0f8a-120">Utilisez le champ de recherche en haut à droite de la page pour filtrer les évaluations affichées par ID produit, nom du produit, ou texte de l'évaluation.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-120">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="d0f8a-121">Des filtres supplémentaires vous permettent de limiter les évaluations par période, classement, canal ou statut des problèmes (retirée, répondue ou signalée).</span><span class="sxs-lookup"><span data-stu-id="d0f8a-121">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Page d'accueil Modération](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="d0f8a-123">Réponse à une évaluation</span><span class="sxs-lookup"><span data-stu-id="d0f8a-123">Respond to a review</span></span> 

<span data-ttu-id="d0f8a-124">Parfois, les clients qui ont acheté un produit expriment leur satisfaction ou mécontentement, ou ne comprennent pas comment utiliser le produit.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-124">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="d0f8a-125">Comme modérateur, vous pouvez publier une réponse à une évaluation.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-125">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="d0f8a-126">Cette réponse apparaît avec l'évaluation sur le site.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-126">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="d0f8a-127">Pour répondre à une évaluation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-127">To respond to a review, follow these steps.</span></span>

1. <span data-ttu-id="d0f8a-128">Accédez à **Accueil \> Évaluations \> Modération**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-128">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="d0f8a-129">Recherchez et sélectionnez l'évaluation nécessitant une réponse.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-129">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="d0f8a-130">Dans le volet de propriétés de droite, sélectionnez **Ajouter une réponse**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-130">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="d0f8a-131">Entrez le texte de réponse et le nom qui doivent être affichés pour le répondeur.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-131">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="d0f8a-132">Le nom par défaut du répondeur est **Modérateur**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-132">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="d0f8a-133">Lorsque vous avez terminé, sélectionnez **Publier la réponse**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-133">When you've finished, select **Post response**.</span></span>

![Répondre à une évaluation](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="d0f8a-135">Retirer une révision</span><span class="sxs-lookup"><span data-stu-id="d0f8a-135">Take down a review</span></span> 

<span data-ttu-id="d0f8a-136">Parfois, il existe une justification commerciale pour les modérateurs de retirer des évaluations de clients.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-136">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="d0f8a-137">Pour retirer une évaluation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-137">To take down a review, follow these steps.</span></span>

1. <span data-ttu-id="d0f8a-138">Accédez à **Accueil \> Évaluations \> Modération**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-138">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="d0f8a-139">Recherchez et sélectionnez l'évaluation qui doit être retirée.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-139">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="d0f8a-140">Dans le volet de propriétés de droite, sélectionnez un motif de retrait, puis sélectionnez **Retirer**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-140">In the properties pane on the right, select a takedown reason, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="d0f8a-141">Supprimer les évaluations d'un client à la demande du client</span><span class="sxs-lookup"><span data-stu-id="d0f8a-141">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="d0f8a-142">Parfois, les clients souhaitent que les données de leurs classements et évaluations soient supprimées définitivement d'un site web du commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-142">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="d0f8a-143">Un modérateur qui reçoit une demande de suppression d'un client peut supprimer les données du client à l'aide de la fonctionnalité de suppression d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-143">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="d0f8a-144">Pour rechercher et supprimer les données d'un client, le modérateur nécessite l'adresse e-mail que ce client a utilisée pour se connecter et fournir les évaluations.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-144">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="d0f8a-145">Pour rechercher et supprimer des données client, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-145">To find and delete customer data, follow these steps.</span></span>

1. <span data-ttu-id="d0f8a-146">Accédez à **Accueil \> Évaluations \> Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-146">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="d0f8a-147">Dans le champ **Rechercher des utilisateurs par adresse e-mail**, entrez l'adresse e-mail du client, puis sélectionnez **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-147">In the **Search for users by email address** field, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="d0f8a-148">Si le client a une activité d'évaluation (par exemple, des soumissions d'évaluation, des votes sur l'utilité des évaluations d'un autre client, ou des commentaires sur l'évaluation d'un autre client), les résultats s'affichent.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-148">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="d0f8a-149">Pour chaque article, il existe un bouton **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-149">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="d0f8a-150">Pour chaque article qui doit être supprimé, sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-150">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="d0f8a-151">Lorsque vous êtes invité à confirmer, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-151">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Suppression de données client](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="d0f8a-153">La suppression totale des données du système peut prendre jusqu'à sept jours.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-153">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="d0f8a-154">Les modérateurs doivent informer les clients de ce délai.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-154">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="d0f8a-155">Si les clients ont modifié leur nom dans leurs paramètres de compte, plusieurs articles peuvent apparaître dans les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-155">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="d0f8a-156">Dans ce cas, pour supprimer complètement les données client, le modérateur doit sélectionner **Supprimer** pour chaque article.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-156">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="d0f8a-157">Téléchargement des données de classement et d'évaluation</span><span class="sxs-lookup"><span data-stu-id="d0f8a-157">Download ratings and reviews data</span></span>

<span data-ttu-id="d0f8a-158">L'outil de modération des classements et des évaluations permet aux modérateurs d'importer des classements et des évaluations afin d'analyser les tendances.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-158">The ratings and reviews moderation tool lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="d0f8a-159">Un modèle Power BI qui inclut les mesures de base est disponible.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-159">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="d0f8a-160">Les modérateurs peuvent utiliser ce modèle pour connecter les données importées en bloc et afficher un tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-160">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="d0f8a-161">Ils n'ont pas besoin de créer un tableau de bord personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-161">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="d0f8a-162">Les modérateurs peuvent également personnaliser le modèle Power BI en fonction de leurs besoins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-162">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="d0f8a-163">Pour télécharger des données de classements et d'évaluations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-163">To download ratings and reviews data, follow these steps.</span></span>

1. <span data-ttu-id="d0f8a-164">Accédez à **Accueil \> Évaluations \> Génération d'états**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-164">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="d0f8a-165">Sélectionnez **Télécharger les données d'évaluations** pour télécharger les données de classement et d'évaluation en vrac dans le format avec séparation par une virgule de valeurs (CSV).</span><span class="sxs-lookup"><span data-stu-id="d0f8a-165">Select **Download reviews data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="d0f8a-166">Afficher les tendances des classements et des évaluations</span><span class="sxs-lookup"><span data-stu-id="d0f8a-166">View ratings and reviews trends</span></span>

<span data-ttu-id="d0f8a-167">Les modérateurs peuvent télécharger le modèle Power BI afin d'afficher les tendances dans un tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-167">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="d0f8a-168">Pour afficher les tendances des classements et des évaluations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-168">To view ratings and reviews trends, follow these steps.</span></span>

1. <span data-ttu-id="d0f8a-169">Accédez à **Accueil \> Évaluations \> Génération d'états**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-169">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="d0f8a-170">Sélectionnez **Modèle PowerBI** pour télécharger le modèle.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-170">Select **PowerBI template** to download the template.</span></span>

    ![Téléchargement du modèle Power BI](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="d0f8a-172">Ouvrez le modèle téléchargé à l'aide de l'application Power BI.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-172">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="d0f8a-173">Fermez la boîte de dialogue **Accès au contenu web** qui apparaît, puis fermez le message d'erreur « Actualisation » qui s'affiche.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-173">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="d0f8a-174">Accédez à **Accueil**, sélectionnez **Modifier les requêtes**, puis sélectionnez **Paramètres de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-174">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="d0f8a-175">Dans la boîte de dialogue **Paramètres de la source de données**, sélectionnez **Modifier la source**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-175">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="d0f8a-176">Dans le champ **URL**, entrez le chemin des données d'évaluations que vous avez téléchargées dans la procédure précédente (par exemple, **c :\\évaluations\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="d0f8a-176">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![Champ de l'URL dans la boîte de dialogue Valeurs séparées par une virgule](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="d0f8a-178">Sélectionnez **OK**, puis **Appliquer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-178">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="d0f8a-179">Une à deux minutes sont nécessaires pour appliquer les modifications à la source de données.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-179">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="d0f8a-180">Sélectionnez **Feuille de tendances** pour afficher les tendances des classements et des évaluations.</span><span class="sxs-lookup"><span data-stu-id="d0f8a-180">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Tendances des classements et des évaluations](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="d0f8a-182">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d0f8a-182">Additional resources</span></span>

[<span data-ttu-id="d0f8a-183">Vue d'ensemble des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="d0f8a-183">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="d0f8a-184">Choix d'utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="d0f8a-184">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="d0f8a-185">Configuration des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="d0f8a-185">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="d0f8a-186">Synchronisation des évaluations de produit dans Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="d0f8a-186">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
