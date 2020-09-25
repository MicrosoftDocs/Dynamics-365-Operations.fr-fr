---
title: Synchronisation des évaluations de produit dans Dynamics 365 Commerce
description: Cette rubrique décrit comment synchroniser les classements de produit dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: dec87b548f3a218e1f833b752305f373e893b14c
ms.sourcegitcommit: 58d7133ae9909fa205730e3cf4c7fd5a1d5d0b75
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2020
ms.locfileid: "3793585"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a><span data-ttu-id="b47cc-103">Synchronisation des évaluations de produit dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b47cc-103">Sync product ratings in Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b47cc-104">Cette rubrique décrit comment synchroniser les classements de produit dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b47cc-104">This topic describes how to sync product ratings in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b47cc-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="b47cc-105">Overview</span></span>

<span data-ttu-id="b47cc-106">Pour consommer des classements de produit dans les omnicanaux, par exemple au point de vente (PDV) et dans les centres d’appels, les classements de produit du service de classements et d’évaluations doivent être importés dans la base de données du canal de commerce.</span><span class="sxs-lookup"><span data-stu-id="b47cc-106">To consume product ratings in omnichannels, such as at the point of sale (POS) and in call centers, product ratings from the ratings and reviews service must be imported into the Commerce channel database.</span></span> <span data-ttu-id="b47cc-107">Lorsque les classements de produit sont disponibles dans les omnicanaux, ils peuvent aider les clients indirectement lors de leurs interactions avec des vendeurs.</span><span class="sxs-lookup"><span data-stu-id="b47cc-107">When product ratings are made available in omnichannels, they can help customers indirectly during their interactions with sales associates.</span></span>

<span data-ttu-id="b47cc-108">Cette rubrique décrit les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="b47cc-108">This topic describes following tasks:</span></span>

1. <span data-ttu-id="b47cc-109">Configurez **Synchronisation les classements de produits** comme un traitement par lots pour synchroniser les classements de produits à partir de **Service de classements et d’évaluations**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-109">Configure **Product ratings sync job** as a batch job to synchronize product ratings from the **Ratings and Reviews service**.</span></span>
1. <span data-ttu-id="b47cc-110">Vérifiez que le traitement par lots de la synchronisation de classement de produit a abouti.</span><span class="sxs-lookup"><span data-stu-id="b47cc-110">Verify that the batch job for product rating synchronization was successful.</span></span>
1. <span data-ttu-id="b47cc-111">Rendez les classements de produit disponibles dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="b47cc-111">Make product ratings available at the POS.</span></span>

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a><span data-ttu-id="b47cc-112">Configurer un traitement par lots pour synchroniser les classements de produit</span><span class="sxs-lookup"><span data-stu-id="b47cc-112">Configure a batch job to synchronize product ratings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b47cc-113">Avant de démarrer, vérifiez que la version 10.0.6 ou ultérieure de Dynamics 365 Commerce est installée.</span><span class="sxs-lookup"><span data-stu-id="b47cc-113">Before you start, make sure that version 10.0.6 or later of Dynamics 365 Commerce is installed.</span></span>

### <a name="initialize-the-commerce-scheduler"></a><span data-ttu-id="b47cc-114">Initialiser le planificateur de commerce</span><span class="sxs-lookup"><span data-stu-id="b47cc-114">Initialize the commerce scheduler</span></span>

<span data-ttu-id="b47cc-115">Pour initialiser le planificateur de commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b47cc-115">To initialize the commerce scheduler, follow these steps.</span></span>

1. <span data-ttu-id="b47cc-116">Accédez à **Retail et Commerce \> Configuration du siège \> Planificateur de commerce \> Initialiser le planificateur de commerce**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-116">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Initialize commerce scheduler**.</span></span> <span data-ttu-id="b47cc-117">Sinon, faites une recherche sur « Initialiser le planificateur de commerce ».</span><span class="sxs-lookup"><span data-stu-id="b47cc-117">Alternatively, search for "Initialize commerce scheduler."</span></span>
1. <span data-ttu-id="b47cc-118">Dans la boîte de dialogue **Initialiser le planificateur de commerce**, vérifiez que l’option **Supprimer la configuration existante** est définie sur **Non**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-118">In the **Initialize commerce scheduler** dialog box, make sure that the **Delete existing configuration** option is set to **No**, and then select **OK**.</span></span>

### <a name="verify-the-retailproductrating-subjob"></a><span data-ttu-id="b47cc-119">Vérifiez la sous-tâche RetailProductRating</span><span class="sxs-lookup"><span data-stu-id="b47cc-119">Verify the RetailProductRating subjob</span></span>

<span data-ttu-id="b47cc-120">Pour vérifier que la sous-tâche **RetailProductRating** existe, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b47cc-120">To verify that the **RetailProductRating** subjob exists, follow these steps.</span></span>

1. <span data-ttu-id="b47cc-121">Accédez à **Retail et Commerce \> Configuration du siège \> Planificateur de commerce \> Sous-tâches du planificateur**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-121">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Scheduler subjobs**.</span></span> <span data-ttu-id="b47cc-122">Sinon, recherchez des « Sous-tâches Planification. »</span><span class="sxs-lookup"><span data-stu-id="b47cc-122">Alternatively, search for "Scheduler subjobs."</span></span>
1. <span data-ttu-id="b47cc-123">Dans la liste des sous-tâches, recherchez la sous-tâche **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-123">In the subjob list, find or search for the **RetailProductRating** subjob.</span></span>

<span data-ttu-id="b47cc-124">L’illustration suivante présente un exemple de détails de sous-tâche dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="b47cc-124">The following illustration shows an example of the subjob details in Commerce.</span></span>

![Détails la sous-tâche RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> <span data-ttu-id="b47cc-126">Si vous ne trouvez pas la sous-tâche **RetailProductRating**, il est possible que vous ayez déjà exécuté la tâche **Synchroniser les classements de produits** et la tâche **1040 CDX** avant d’initialiser le planificateur de commerce.</span><span class="sxs-lookup"><span data-stu-id="b47cc-126">If you don't find the **RetailProductRating** subjob, you might already have run the **Sync product ratings** job and the **1040 CDX** job before you initialized the Commerce scheduler.</span></span> <span data-ttu-id="b47cc-127">Dans ce cas, procédez comme suit pour exécuter la tâche **Synchronisation de données complète**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-127">In this case, follow these steps to run the **Full data sync** job.</span></span>

> 1. <span data-ttu-id="b47cc-128">Accédez à **Retail et Commerce \> Configuration du siège \> Planificateur de commerce \> Base de données des canaux**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-128">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span> <span data-ttu-id="b47cc-129">Sinon, recherchez la « Base de données du canal. »</span><span class="sxs-lookup"><span data-stu-id="b47cc-129">Alternatively, search for "Channel database."</span></span>
> 1. <span data-ttu-id="b47cc-130">Sélectionnez la base de données du canal à synchroniser.</span><span class="sxs-lookup"><span data-stu-id="b47cc-130">Select the channel database to sync.</span></span>
> 1. <span data-ttu-id="b47cc-131">Sur le volet d’action, sélectionnez **Synchronisation complète des données**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-131">On the action pane, select **Full data sync**.</span></span>
> 1. <span data-ttu-id="b47cc-132">Dans la boîte de dialogue de menu déroulant **Sélectionner un programme de distribution**, sélectionnez **1040 - produits**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-132">In the **Select a distribution schedule** drop-down dialog box, select **1040 - products**, and then select **OK**.</span></span>
> 1. <span data-ttu-id="b47cc-133">Répétez les étapes de la procédure précédente pour vérifier que la sous-tâche **RetailProductRating** a été créée.</span><span class="sxs-lookup"><span data-stu-id="b47cc-133">Repeat the steps of the previous procedure to verify that the **RetailProductRating** subjob has been created.</span></span>

### <a name="import-product-ratings"></a><span data-ttu-id="b47cc-134">Importer des classements de produits</span><span class="sxs-lookup"><span data-stu-id="b47cc-134">Import product ratings</span></span>

<span data-ttu-id="b47cc-135">Pour importer les classements de produits dans Commerce à partir du service de classements et d’évaluations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b47cc-135">To import product ratings into Commerce from the ratings and reviews service, follow these steps.</span></span>

1. <span data-ttu-id="b47cc-136">Accédez à **Retail et Commerce \> Paramétrage de Siège \> Planificateur de commerce \> Synchroniser les classements de produits**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-136">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Sync product ratings job**.</span></span> <span data-ttu-id="b47cc-137">Sinon, recherchez « Synchroniser les classements de produits. »</span><span class="sxs-lookup"><span data-stu-id="b47cc-137">Alternatively, search for "Sync product ratings job."</span></span>
1. <span data-ttu-id="b47cc-138">Dans la boîte de dialogue **Extraire les classements de produits**, sous l’organisateur **Exécuter en arrière-plan**, sélectionnez **Récurrence**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-138">In the **Pull product ratings** dialog box, on the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="b47cc-139">Dans la boîte de dialogue **Définissez la récurrence**, paramétrez un modèle de répétition.</span><span class="sxs-lookup"><span data-stu-id="b47cc-139">In the **Define recurrence** dialog box, set up a recurrence pattern.</span></span> <span data-ttu-id="b47cc-140">(La valeur suggérée est de deux heures.) Ne planifiez pas une récurrence inférieure à une heure.</span><span class="sxs-lookup"><span data-stu-id="b47cc-140">(The suggested value is two hours.) Don't schedule a recurrence that is less than one hour.</span></span>
1. <span data-ttu-id="b47cc-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-141">Select **OK**.</span></span>
1. <span data-ttu-id="b47cc-142">Définissez l’option **Traitement par lots** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-142">Set the **Batch process** option to **Yes**.</span></span> <span data-ttu-id="b47cc-143">Ce paramètre permet de garantir que vous pouvez auditer les journaux et vérifier le statut des exécutions de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="b47cc-143">This setting helps guarantee that you will be able to audit the logs and verify the status of batch job runs.</span></span>
1. <span data-ttu-id="b47cc-144">Sélectionnez **OK** pour planifier le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="b47cc-144">Select **OK** to schedule the batch job.</span></span>

<span data-ttu-id="b47cc-145">L’illustration suivante présente un exemple de configuration de traitement par lots dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="b47cc-145">The following illustration shows an example of batch job configuration in Commerce.</span></span>

![Configuration du traitement par lots de synchronisation des évaluations de produits](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a><span data-ttu-id="b47cc-147">Vérifiez que le traitement par lots de la synchronisation de classement de produit a abouti</span><span class="sxs-lookup"><span data-stu-id="b47cc-147">Verify that the batch job for product rating synchronization was successful</span></span>

<span data-ttu-id="b47cc-148">Pour vérifier que le traitement par lots **Synchroniser les classements de produits** a abouti, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b47cc-148">To verify that the **Sync product ratings** batch job was successful, follow these steps.</span></span>

1. <span data-ttu-id="b47cc-149">Accédez à **Retail et Commerce \> Administrateur système \> Recherches \> Traitements par lots** ou, si vous utilisez à une unité de gestion de stock (SKU) réservée à Commerce, accédez plutôt à **Retail et Commerce \> Recherches et états \> Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-149">Go to **Retail and Commerce \> System administrator \> Inquiries \> Batch jobs** or, if you're using a Commerce-only stock keeping unit (SKU), **Retail and Commerce \> Inquiries and reports \> Batch jobs** instead.</span></span> <span data-ttu-id="b47cc-150">Sinon, recherchez des « Traitements par lots ».</span><span class="sxs-lookup"><span data-stu-id="b47cc-150">Alternatively, search for "Batch jobs."</span></span>
1. <span data-ttu-id="b47cc-151">Pour afficher les détails du traitement par lots, dans la liste de traitement par lots, dans la colonne **Description de la tâche**, recherchez une description qui contient « Extraire les classements de produits ».</span><span class="sxs-lookup"><span data-stu-id="b47cc-151">To view the details of the batch job, in the batch job list, in the **Job description** column, search for a description that contains "Pull product ratings."</span></span>
1. <span data-ttu-id="b47cc-152">Sélectionnez l’ID tâche pour afficher les détails du traitement par lots, tels que la date et l’heure prévues de début et le texte de récurrence.</span><span class="sxs-lookup"><span data-stu-id="b47cc-152">Select the job ID to view the batch job details, such as the scheduled start date/time and the recurrence text.</span></span>

<span data-ttu-id="b47cc-153">L’illustration suivante donne un exemple de détails de traitement par lots dans Commerce lorsque le traitement par lots est programmé pour une exécution à des intervalles de deux heures.</span><span class="sxs-lookup"><span data-stu-id="b47cc-153">The following illustration shows an example of the batch job details in Commerce when the batch job is scheduled to run at two-hour intervals.</span></span>

![Détails du traitement par lots de synchronisation des évaluations de produits](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a><span data-ttu-id="b47cc-155">Rendez les classements de produit disponibles dans le PDV</span><span class="sxs-lookup"><span data-stu-id="b47cc-155">Make product ratings available at the POS</span></span>

<span data-ttu-id="b47cc-156">La solution de classements et d’évaluations dans Dynamics 365 Commerce est une solution omnicanale.</span><span class="sxs-lookup"><span data-stu-id="b47cc-156">The ratings and reviews solution in Dynamics 365 Commerce is an omnichannel solution.</span></span> <span data-ttu-id="b47cc-157">Toutefois, les classements de produits ne sont pas affichés au niveau du PDV par défaut.</span><span class="sxs-lookup"><span data-stu-id="b47cc-157">However, products ratings aren't shown at the POS by default.</span></span> <span data-ttu-id="b47cc-158">Pour aider les clients dans les magasins à afficher les classements et les évaluations lorsqu’ils sont aidés par des vendeurs, vous devez activer les classements de produits dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="b47cc-158">To help customers in stores see ratings and reviews when they are being helped by sales associates, you must turn on product ratings at the POS.</span></span>

<span data-ttu-id="b47cc-159">Pour activer les classements de produits dans le PDV, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b47cc-159">To turn on product ratings at the POS, follow these steps.</span></span>

1. <span data-ttu-id="b47cc-160">Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres de commerce**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-160">Go to **Retail and Commerce \> Commerce setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="b47cc-161">Sinon, faites une recherche sur « Paramètres de commerce ».</span><span class="sxs-lookup"><span data-stu-id="b47cc-161">Alternatively, search for "Commerce parameters."</span></span>
1. <span data-ttu-id="b47cc-162">Dans l’onglet **Paramètres de configuration**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-162">On the **Configuration parameters** tab, select **New**.</span></span>
1. <span data-ttu-id="b47cc-163">Entrez un nom tel que **RatingsAndReviews.EnableProductRatingsForRetailStores**, et définissez la valeur sur **vrai**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-163">Enter a name such as **RatingsAndReviews.EnableProductRatingsForRetailStores**, and set the value to **true**.</span></span>
1. <span data-ttu-id="b47cc-164">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-164">Select **Save**.</span></span>
1. <span data-ttu-id="b47cc-165">Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-165">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span> <span data-ttu-id="b47cc-166">Sinon, recherchez « Programme de distribution ».</span><span class="sxs-lookup"><span data-stu-id="b47cc-166">Alternatively, search for "Distribution schedule."</span></span>
1. <span data-ttu-id="b47cc-167">Dans la liste de tâches, sélectionnez **1110** (**Configuration globale**), puis sélectionnez **Exécution maintenant**.</span><span class="sxs-lookup"><span data-stu-id="b47cc-167">In the job list, select **1110** (**Global configuration**), and then select **Run now**.</span></span>
1. <span data-ttu-id="b47cc-168">Lorsque la tâche correctement exécuté, vérifiez que les classements de produits s’affichent dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="b47cc-168">After the job has successfully run, verify that products ratings are now shown at the POS.</span></span>

<span data-ttu-id="b47cc-169">L’illustration suivante donne un exemple de la configuration des paramètres de commerce pour activer les classements de produits au PDV.</span><span class="sxs-lookup"><span data-stu-id="b47cc-169">The following illustration shows an example of the configuration of the Commerce parameters to turn on product ratings at the POS.</span></span>

![Configuration des paramètres de commerce pour les évaluations de produit au PDV](media/rnr-hq-enable-ratings-in-pos.png)

<span data-ttu-id="b47cc-171">L’illustration suivante montre un exemple de classements de produits dans PDV.</span><span class="sxs-lookup"><span data-stu-id="b47cc-171">The following illustration shows an example of product ratings at the POS.</span></span>

![Classements de produits dans le PDV](media/rnr-pos-catalog-ratings.png)

<span data-ttu-id="b47cc-173">L’illustration suivante montre un exemple de classements de produits dans les canaux de centres d’appels.</span><span class="sxs-lookup"><span data-stu-id="b47cc-173">The following illustration shows an example of product ratings in call center channels.</span></span>

![Classements de produits dans un canal de centre d’appels](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a><span data-ttu-id="b47cc-175">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b47cc-175">Additional resources</span></span>

[<span data-ttu-id="b47cc-176">Vue d’ensemble des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="b47cc-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="b47cc-177">Choix d’utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="b47cc-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="b47cc-178">Gestion des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="b47cc-178">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="b47cc-179">Configuration des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="b47cc-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)
