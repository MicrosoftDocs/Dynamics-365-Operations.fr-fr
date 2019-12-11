---
title: Synchronisation des évaluations de produit dans Dynamics 365 Retail
description: Cette rubrique décrit comment synchroniser les classements de produit dans Microsoft Dynamics 365 Retail.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: db5a4e1f78797d20ded2274cc99bef422fd50acc
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698163"
---
# <a name="sync-product-ratings-in-dynamics-365-retail"></a><span data-ttu-id="0bf23-103">Synchronisation des évaluations de produit dans Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="0bf23-103">Sync product ratings in Dynamics 365 Retail</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="0bf23-104">Cette rubrique décrit comment synchroniser les classements de produit dans Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="0bf23-104">This topic describes how to sync product ratings in Microsoft Dynamics 365 Retail.</span></span>

## <a name="overview"></a><span data-ttu-id="0bf23-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="0bf23-105">Overview</span></span>

<span data-ttu-id="0bf23-106">Pour consommer des classements de produit dans les omnicanaux, par exemple au point de vente (PDV) et dans les centres d'appels, les classements de produit du service de classements et d'évaluations doivent être importés dans la base de données du canal de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="0bf23-106">To consume product ratings in omnichannels, such as at the point of sale (POS) and in call centers, product ratings from the ratings and reviews service must be imported into the Retail channel database.</span></span> <span data-ttu-id="0bf23-107">Lorsque les classements de produit sont disponibles dans les omnicanaux, ils peuvent aider les clients indirectement lors de leurs interactions avec des vendeurs.</span><span class="sxs-lookup"><span data-stu-id="0bf23-107">When product ratings are made available in omnichannels, they can help customers indirectly during their interactions with sales associates.</span></span>

<span data-ttu-id="0bf23-108">Cette rubrique décrit les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bf23-108">This topic describes following tasks:</span></span>

1. <span data-ttu-id="0bf23-109">Configurez un traitement par lots de vente au détail pour importer des classements de produit.</span><span class="sxs-lookup"><span data-stu-id="0bf23-109">Configure a Retail batch job to import product ratings.</span></span>
1. <span data-ttu-id="0bf23-110">Vérifiez que le traitement par lots de la synchronisation de classement de produit a abouti.</span><span class="sxs-lookup"><span data-stu-id="0bf23-110">Verify that the batch job for product rating synchronization was successful.</span></span>
1. <span data-ttu-id="0bf23-111">Rendez les classements de produit disponibles dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="0bf23-111">Make product ratings available at the POS.</span></span>

## <a name="configure-a-retail-batch-job-to-import-product-ratings"></a><span data-ttu-id="0bf23-112">Configurez un traitement par lots de vente au détail pour importer des classements de produit</span><span class="sxs-lookup"><span data-stu-id="0bf23-112">Configure a Retail batch job to import product ratings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bf23-113">Avant de commencer, vérifiez que la version 10.0.6 ou ultérieure de Retail est installé.</span><span class="sxs-lookup"><span data-stu-id="0bf23-113">Before you start, make sure that version 10.0.6 or later of Retail is installed.</span></span>

### <a name="initialize-the-retail-scheduler"></a><span data-ttu-id="0bf23-114">Initialiser Retail Planification</span><span class="sxs-lookup"><span data-stu-id="0bf23-114">Initialize the retail scheduler</span></span>

<span data-ttu-id="0bf23-115">Pour initialiser Retail Planification, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0bf23-115">To initialize the retail scheduler, follow these steps.</span></span>

1. <span data-ttu-id="0bf23-116">Aller à **Vente au détail \> Paramétrage de Siège \> Retail Planification \> Initialiser Retail Planification**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-116">Go to **Retail \> Headquarters setup \> Retail scheduler \> Initialize retail scheduler**.</span></span> <span data-ttu-id="0bf23-117">Sinon, recherchez « Initialiser Retail Planification. »</span><span class="sxs-lookup"><span data-stu-id="0bf23-117">Alternatively, search for "Initialize retail scheduler."</span></span>
1. <span data-ttu-id="0bf23-118">Dans la boîte de dialogue **Initialiser Retail Planification**, assurez-vous que l'option **Supprimer la configuration existante** est définie sur **Non**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-118">In the **Initialize retail scheduler** dialog box, make sure that the **Delete existing configuration** option is set to **No**, and then select **OK**.</span></span>

### <a name="verify-the-retailproductrating-subjob"></a><span data-ttu-id="0bf23-119">Vérifiez la sous-tâche RetailProductRating</span><span class="sxs-lookup"><span data-stu-id="0bf23-119">Verify the RetailProductRating subjob</span></span>

<span data-ttu-id="0bf23-120">Pour vérifier que la sous-tâche **RetailProductRating** existe, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0bf23-120">To verify that the **RetailProductRating** subjob exists, follow these steps.</span></span>

1. <span data-ttu-id="0bf23-121">Aller à **Vente au détail \> Paramétrage de Siège \> Retail Planification \> Sous-tâche Planification**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-121">Go to **Retail \> Headquarters setup \> Retail scheduler \> Scheduler subjobs**.</span></span> <span data-ttu-id="0bf23-122">Sinon, recherchez des « Sous-tâches Planification. »</span><span class="sxs-lookup"><span data-stu-id="0bf23-122">Alternatively, search for "Scheduler subjobs."</span></span>
1. <span data-ttu-id="0bf23-123">Dans la liste des sous-tâches, recherchez la sous-tâche **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-123">In the subjob list, find or search for the **RetailProductRating** subjob.</span></span>

<span data-ttu-id="0bf23-124">L'illustration suivante présente un exemple de la page Détails de la sous-tâche dans Retail.</span><span class="sxs-lookup"><span data-stu-id="0bf23-124">The following illustration shows an example of the subjob details in Retail.</span></span>

![Détails la sous-tâche RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> <span data-ttu-id="0bf23-126">Si vous ne trouvez pas la sous-tâche **RetailProductRating**, vous pouvez avoir déjà effectué la tâche **Synchroniser les classements de produits** et la tâche **1040 CDX** avant d'initialiser Retail Planification.</span><span class="sxs-lookup"><span data-stu-id="0bf23-126">If you don't find the **RetailProductRating** subjob, you might already have run the **Sync product ratings** job and the **1040 CDX** job before you initialized the retail scheduler.</span></span> <span data-ttu-id="0bf23-127">Dans ce cas, procédez comme suit pour exécuter la tâche **Synchronisation de données complète**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-127">In this case, follow these steps to run the **Full data sync** job.</span></span>
>
> 1. <span data-ttu-id="0bf23-128">Aller à **Vente au détail \> Paramétrage de Siège \> Retail Planification \> Base de données du canal**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-128">Go to **Retail \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span> <span data-ttu-id="0bf23-129">Sinon, recherchez la « Base de données du canal. »</span><span class="sxs-lookup"><span data-stu-id="0bf23-129">Alternatively, search for "Channel database."</span></span>
> 1. <span data-ttu-id="0bf23-130">Sélectionnez la base de données du canal à synchroniser.</span><span class="sxs-lookup"><span data-stu-id="0bf23-130">Select the channel database to sync.</span></span>
> 1. <span data-ttu-id="0bf23-131">Sur le volet Action, sélectionnez **Synchronisation de données complète**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-131">On the Action Pane, select **Full data sync**.</span></span>
> 1. <span data-ttu-id="0bf23-132">Dans la boîte de dialogue de menu déroulant **Sélectionner un programme de distribution**, sélectionnez **1040 - produits**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-132">In the **Select a distribution schedule** drop-down dialog box, select **1040 - products**, and then select **OK**.</span></span>
> 1. <span data-ttu-id="0bf23-133">Répétez les étapes de la procédure précédente pour vérifier que la sous-tâche **RetailProductRating** a été créée.</span><span class="sxs-lookup"><span data-stu-id="0bf23-133">Repeat the steps of the previous procedure to verify that the **RetailProductRating** subjob has been created.</span></span>

### <a name="import-product-ratings"></a><span data-ttu-id="0bf23-134">Importer des classements de produits</span><span class="sxs-lookup"><span data-stu-id="0bf23-134">Import product ratings</span></span>

<span data-ttu-id="0bf23-135">Pour importer des classements de produits dans Retail à partir du service de classements et d'évaluations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0bf23-135">To import product ratings into Retail from the ratings and reviews service, follow these steps.</span></span>

1. <span data-ttu-id="0bf23-136">Aller à **Vente au détail \> Paramétrage de Siège \> Retail Planification \> Synchroniser les classements de produits**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-136">Go to **Retail \> Headquarters setup \> Retail scheduler \> Sync product ratings job**.</span></span> <span data-ttu-id="0bf23-137">Sinon, recherchez « Synchroniser les classements de produits. »</span><span class="sxs-lookup"><span data-stu-id="0bf23-137">Alternatively, search for "Sync product ratings job."</span></span>
1. <span data-ttu-id="0bf23-138">Dans la boîte de dialogue **Extraire les classements de produits**, sous l'organisateur **Exécuter en arrière-plan**, sélectionnez **Récurrence**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-138">In the **Pull product ratings** dialog box, on the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="0bf23-139">Dans la boîte de dialogue **Définissez la récurrence**, paramétrez un modèle de répétition.</span><span class="sxs-lookup"><span data-stu-id="0bf23-139">In the **Define recurrence** dialog box, set up a recurrence pattern.</span></span> <span data-ttu-id="0bf23-140">(La valeur suggérée est de deux heures.) Ne planifiez pas une récurrence inférieure à une heure.</span><span class="sxs-lookup"><span data-stu-id="0bf23-140">(The suggested value is two hours.) Don't schedule a recurrence that is less than one hour.</span></span>
1. <span data-ttu-id="0bf23-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-141">Select **OK**.</span></span>
1. <span data-ttu-id="0bf23-142">Définissez l'option **Traitement par lots** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-142">Set the **Batch process** option to **Yes**.</span></span> <span data-ttu-id="0bf23-143">Ce paramètre permet de garantir que vous pouvez auditer les journaux et vérifier le statut des exécutions de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="0bf23-143">This setting helps guarantee that you will be able to audit the logs and verify the status of batch job runs.</span></span>
1. <span data-ttu-id="0bf23-144">Sélectionnez **OK** pour planifier le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="0bf23-144">Select **OK** to schedule the batch job.</span></span>

<span data-ttu-id="0bf23-145">L'illustration suivante présente un exemple de configuration de traitement par lots dans Retail.</span><span class="sxs-lookup"><span data-stu-id="0bf23-145">The following illustration shows an example of batch job configuration in Retail.</span></span>

![Configuration du traitement par lots de synchronisation des évaluations de produits](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a><span data-ttu-id="0bf23-147">Vérifiez que le traitement par lots de la synchronisation de classement de produit a abouti</span><span class="sxs-lookup"><span data-stu-id="0bf23-147">Verify that the batch job for product rating synchronization was successful</span></span>

<span data-ttu-id="0bf23-148">Pour vérifier que le traitement par lots **Synchroniser les classements de produits** a abouti, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0bf23-148">To verify that the **Sync product ratings** batch job was successful, follow these steps.</span></span>

1. <span data-ttu-id="0bf23-149">Aller **Vente au détail \> Administrateur système \> Recherches \> Traitements par lots** ou, si vous utilisez à une unité de gestion de stock (SKU) réservée à la vente au détail, **Vente au détail \> Recherches et états \> Traitements par lots** à la place.</span><span class="sxs-lookup"><span data-stu-id="0bf23-149">Go to **Retail \> System administrator \> Inquiries \> Batch jobs** or, if you're using a Retail-only stock keeping unit (SKU), **Retail \> Inquiries and reports \> Batch jobs** instead.</span></span> <span data-ttu-id="0bf23-150">Sinon, recherchez des « Traitements par lots ».</span><span class="sxs-lookup"><span data-stu-id="0bf23-150">Alternatively, search for "Batch jobs."</span></span>
1. <span data-ttu-id="0bf23-151">Pour afficher les détails du traitement par lots, dans la liste de traitement par lots, dans la colonne **Description de la tâche**, recherchez une description qui contient « Extraire les classements de produits ».</span><span class="sxs-lookup"><span data-stu-id="0bf23-151">To view the details of the batch job, in the batch job list, in the **Job description** column, search for a description that contains "Pull product ratings."</span></span>
1. <span data-ttu-id="0bf23-152">Sélectionnez l'ID tâche pour afficher les détails du traitement par lots, tels que la date et l'heure prévues de début et le texte de récurrence.</span><span class="sxs-lookup"><span data-stu-id="0bf23-152">Select the job ID to view the batch job details, such as the scheduled start date/time and the recurrence text.</span></span>

<span data-ttu-id="0bf23-153">L'illustration suivante indique qu'un exemple de détails de traitement par lots dans Retail lorsque le traitement par lots est planifié à s'exécuter à des intervalles de deux heures.</span><span class="sxs-lookup"><span data-stu-id="0bf23-153">The following illustration shows an example of the batch job details in Retail when the batch job is scheduled to run at two-hour intervals.</span></span>

![Détails du traitement par lots de synchronisation des évaluations de produits](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a><span data-ttu-id="0bf23-155">Rendez les classements de produit disponibles dans le PDV</span><span class="sxs-lookup"><span data-stu-id="0bf23-155">Make product ratings available at the POS</span></span>

<span data-ttu-id="0bf23-156">La solution de classements et d'évaluations dans Dynamics 365 Commerce est une solution omnicanale.</span><span class="sxs-lookup"><span data-stu-id="0bf23-156">The ratings and reviews solution in Dynamics 365 Commerce is an omnichannel solution.</span></span> <span data-ttu-id="0bf23-157">Toutefois, les classements de produits ne sont pas affichés au niveau du PDV par défaut.</span><span class="sxs-lookup"><span data-stu-id="0bf23-157">However, products ratings aren't shown at the POS by default.</span></span> <span data-ttu-id="0bf23-158">Pour aider les clients dans les magasins à afficher les classements et les évaluations lorsqu'ils sont aidés par des vendeurs, vous devez activer les classements de produits dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="0bf23-158">To help customers in stores see ratings and reviews when they are being helped by sales associates, you must turn on product ratings at the POS.</span></span>

<span data-ttu-id="0bf23-159">Pour activer les classements de produits dans le PDV, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0bf23-159">To turn on product ratings at the POS, follow these steps.</span></span>

1. <span data-ttu-id="0bf23-160">Accédez à **Vente au détail \> Configuration de Retail \> Paramètres \> Paramètres des ventes au détail**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-160">Go to **Retail \> Retail setup \> Parameters \> Retail parameters**.</span></span> <span data-ttu-id="0bf23-161">Sinon, recherchez « Paramètres des ventes au détail ».</span><span class="sxs-lookup"><span data-stu-id="0bf23-161">Alternatively, search for "Retail parameters."</span></span>
1. <span data-ttu-id="0bf23-162">Dans l'onglet **Paramètres de configuration**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-162">On the **Configuration parameters** tab, select **New**.</span></span>
1. <span data-ttu-id="0bf23-163">Entrez un nom tel que **RatingsAndReviews.EnableProductRatingsForRetailStores**, et définissez la valeur sur **vrai**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-163">Enter a name such as **RatingsAndReviews.EnableProductRatingsForRetailStores**, and set the value to **true**.</span></span>
1. <span data-ttu-id="0bf23-164">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-164">Select **Save**.</span></span>
1. <span data-ttu-id="0bf23-165">Accédez à **Vente au détail \> Informatique de vente au détail \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-165">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span> <span data-ttu-id="0bf23-166">Sinon, recherchez « Programme de distribution ».</span><span class="sxs-lookup"><span data-stu-id="0bf23-166">Alternatively, search for "Distribution schedule."</span></span>
1. <span data-ttu-id="0bf23-167">Dans la liste de tâches, sélectionnez **1110** (**Configuration globale**), puis sélectionnez **Exécution maintenant**.</span><span class="sxs-lookup"><span data-stu-id="0bf23-167">In the job list, select **1110** (**Global configuration**), and then select **Run now**.</span></span>
1. <span data-ttu-id="0bf23-168">Lorsque la tâche correctement exécuté, vérifiez que les classements de produits s'affichent dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="0bf23-168">After the job has successfully run, verify that products ratings are now shown at the POS.</span></span>

<span data-ttu-id="0bf23-169">L'illustration suivante présente un exemple de la configuration des paramètres des ventes au détail pour activer les classements de produit dans PDV.</span><span class="sxs-lookup"><span data-stu-id="0bf23-169">The following illustration shows an example of the configuration of the Retail parameters to turn on product ratings at the POS.</span></span>

![Configuration des paramètres des ventes au détail pour les évaluations de produit dans le PDV](media/rnr-hq-enable-ratings-in-pos.png)

<span data-ttu-id="0bf23-171">L'illustration suivante montre un exemple de classements de produits dans PDV.</span><span class="sxs-lookup"><span data-stu-id="0bf23-171">The following illustration shows an example of product ratings at the POS.</span></span>

![Classements de produits dans le PDV](media/rnr-pos-catalog-ratings.png)

<span data-ttu-id="0bf23-173">L'illustration suivante montre un exemple de classements de produits dans les canaux de centres d'appels.</span><span class="sxs-lookup"><span data-stu-id="0bf23-173">The following illustration shows an example of product ratings in call center channels.</span></span>

![Classements de produits dans un canal de centre d'appels](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a><span data-ttu-id="0bf23-175">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0bf23-175">Additional resources</span></span>

[<span data-ttu-id="0bf23-176">Vue d'ensemble des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="0bf23-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="0bf23-177">Choix d'utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="0bf23-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="0bf23-178">Gestion des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="0bf23-178">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="0bf23-179">Configuration des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="0bf23-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)
