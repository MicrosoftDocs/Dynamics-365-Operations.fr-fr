---
title: Publication d'emplois sur des sites de carrière externes à partir d'Attract
description: Cette rubrique explique comment utiliser Dynamics 365 for Talent - Attract pour publier des offres d'emploi sur des sites de recrutement externes
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 9c27d1810a89ed7d7a7745e41c5f118dbdfe5dda
ms.sourcegitcommit: cadce85ca3004d53caf6bc49147a524c1bfd421f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2019
ms.locfileid: "1590480"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a><span data-ttu-id="b0d5a-103">Publication d'emplois sur des sites de carrière externes à partir d'Attract</span><span class="sxs-lookup"><span data-stu-id="b0d5a-103">Post jobs to external career sites from Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0d5a-104">Vous souhaitez présenter vos postes vacants à autant de candidats qualifiés que possible.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="b0d5a-105">Les sites de recrutement comme Broadbean vous aident à y parvenir.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="b0d5a-106">Microsoft Dynamics 365 Talent - Attract vous permet désormais de publier des offres sur Broadbean, et Microsoft propose continuellement de nouvelles options dans ce domaine.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="b0d5a-107">Publier des offres sur Broadbean</span><span class="sxs-lookup"><span data-stu-id="b0d5a-107">Post jobs to Broadbean</span></span>

<span data-ttu-id="b0d5a-108">Avant de publier des offres sur Broadbean, vous devez configurer l'intégration de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-108">Before you can post jobs to Broadbean, you must configure the Broadbean integration.</span></span>

> [!NOTE]
> - <span data-ttu-id="b0d5a-109">Pour publier des offres sur des sites externes, vous devez avoir le [Module complémentaire Recrutement complet](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="b0d5a-109">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="b0d5a-110">Pour afficher des missions dans Broadbean via Attract, vous devez avoir un abonnement à Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-110">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="b0d5a-111">Cette fonctionnalité est actuellement en mode aperçu.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-111">This feature is currently in preview.</span></span> <span data-ttu-id="b0d5a-112">Si vous souhaitez l'essayer, vous devez [l'activer dans les paramètres administrateur d'Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="b0d5a-112">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

### <a name="configure-broadbean-integration"></a><span data-ttu-id="b0d5a-113">Configurer l'intégration de Broadbean</span><span class="sxs-lookup"><span data-stu-id="b0d5a-113">Configure Broadbean integration</span></span>

1. <span data-ttu-id="b0d5a-114">Connectez-vous à Attract en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-114">Sign in to Attract as an admin.</span></span>
2. <span data-ttu-id="b0d5a-115">Sélectionnez le bouton **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit de la page, puis sélectionnez **Centre d'administration**.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-115">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>
3. <span data-ttu-id="b0d5a-116">Dans l'onglet **Paramètres des offres d'emploi**, dans la section **Activer l'intégration de Broadbean**, activez l'intégration.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-116">On the **Job board settings** tab, in the **Enable Broadbean integration** section, turn on the integration.</span></span>
4. <span data-ttu-id="b0d5a-117">Contactez Broadbean, puis entrez vos informations dans **Nom d'utilisateur, ID client, jeton de chiffrement**.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-117">Contact Broadbean, and enter your information in **Username, Client ID, Encryption Token**.</span></span>

> [!WARNING]
> <span data-ttu-id="b0d5a-118">Les informations d'identification Broadbean sont précieuses et confidentielles.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-118">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="b0d5a-119">Conservez-les et partagez-les de manière responsable en conséquence.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-119">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="b0d5a-120">Toute personne disposant du rôle Administrateur dans Attract peut afficher ces informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-120">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="b0d5a-121">Microsoft et Attract ne sont pas impliqués dans la création et la conservation de ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-121">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="b0d5a-122">Il est de votre responsabilité de les garder à jour dans Attract et de faire appel à Broadbean pour résoudre éventuels les problèmes impliquant vos informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-122">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>

### <a name="post-a-job-to-broadbean"></a><span data-ttu-id="b0d5a-123">Publication d'une offre sur Broadbean</span><span class="sxs-lookup"><span data-stu-id="b0d5a-123">Post a job to Broadbean</span></span>

<span data-ttu-id="b0d5a-124">Une fois Broadbean activé, les recruteurs et les administrateurs peuvent y publier une offre d'emploi.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-124">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="b0d5a-125">Vous devez posséder une URL de candidature pour l'emploi.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-125">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="b0d5a-126">Dans Attract, ouvrez l'emploi que vous souhaitez publier dans Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-126">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="b0d5a-127">Dans la section **Publications**, sélectionnez le bouton **Publier maintenant** correspondant à Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-127">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="b0d5a-128">Suivez les instructions de la fenêtre Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-128">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="b0d5a-129">Attract transmet les informations suivantes à Broadbean :</span><span class="sxs-lookup"><span data-stu-id="b0d5a-129">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="b0d5a-130">ID demande</span><span class="sxs-lookup"><span data-stu-id="b0d5a-130">Request ID</span></span>
- <span data-ttu-id="b0d5a-131">Titre du poste</span><span class="sxs-lookup"><span data-stu-id="b0d5a-131">Job title</span></span>
- <span data-ttu-id="b0d5a-132">Description du poste</span><span class="sxs-lookup"><span data-stu-id="b0d5a-132">Job description</span></span>
- <span data-ttu-id="b0d5a-133">Emplacement du poste</span><span class="sxs-lookup"><span data-stu-id="b0d5a-133">Job location</span></span>
- <span data-ttu-id="b0d5a-134">URL de candidature</span><span class="sxs-lookup"><span data-stu-id="b0d5a-134">Apply URL</span></span>
- <span data-ttu-id="b0d5a-135">Informations sur le recruteur</span><span class="sxs-lookup"><span data-stu-id="b0d5a-135">Recruiter information</span></span>

<span data-ttu-id="b0d5a-136">Une fois la publication terminée avec succès dans Broadbean, la section **Validations** de l'emploi dans Attract affiche le statut de Broadbean comme **Publié**.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-136">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="b0d5a-137">Broadbean nécessite le champ **Secteur**.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-137">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="b0d5a-138">Actuellement, ce champ est défini sur **IT** par défaut.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-138">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="b0d5a-139">Toutefois, vous pouvez modifier la valeur sur le secteur approprié dans la fenêtre de publication d'emploi dans Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-139">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="b0d5a-140">Il faut un certain temps pour que Broadbean mène à bien la publication de votre offre sur tous les sites d'emplois que vous avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-140">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="b0d5a-141">Par conséquent, il peut y avoir un léger délai avant qu'Attract ne mette à jour le statut de l'offre d'emploi.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-141">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="b0d5a-142">Afficher une publication d'offre d'emploi Broadbean</span><span class="sxs-lookup"><span data-stu-id="b0d5a-142">View a Broadbean job posting</span></span>

<span data-ttu-id="b0d5a-143">Après avoir publié une offre dans Broadbean, vous pouvez la voir depuis Attract.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-143">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="b0d5a-144">Dans Attract, ouvrez l'emploi que vous souhaitez afficher dans Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-144">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="b0d5a-145">Dans la section **Publications**, sélectionnez le bouton représentant des points de suspension (**...**) qui correspond Broadbean, puis sélectionnez **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-145">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="b0d5a-146">La publication d'offre d'emploi Broadbean apparaît dans une nouvelle fenêtre.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-146">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="b0d5a-147">Mise à jour d'une publication d'offre d'emploi Broadbean</span><span class="sxs-lookup"><span data-stu-id="b0d5a-147">Update a Broadbean job posting</span></span>

<span data-ttu-id="b0d5a-148">Vous pouvez mettre à jour une publication d'offre d'emploi Broadbean de deux manières.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-148">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="b0d5a-149">Dans Attract, ouvrez l'emploi que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-149">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="b0d5a-150">Dans la section **Publications**, sélectionnez le bouton **Mettre à jour la publication** correspondant à Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-150">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="b0d5a-151">Modifiez la publication dans la fenêtre Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-151">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="b0d5a-152">- ou -</span><span class="sxs-lookup"><span data-stu-id="b0d5a-152">–or–</span></span>

1. <span data-ttu-id="b0d5a-153">Dans Attract, ouvrez l'emploi que vous souhaitez afficher dans Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-153">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="b0d5a-154">Dans la section **Publications**, sélectionnez le bouton représentant des points de suspension (**...**) qui correspond Broadbean, puis sélectionnez **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-154">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="b0d5a-155">Dans la fenêtre Broadbean, modifiez les détails de l'emploi, puis publiez à nouveau l'offre d'emploi.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-155">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="b0d5a-156">Les détails de l'emploi dans Attract ne sont pas modifiés.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-156">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="b0d5a-157">Supprimer une publication d'offre d'emploi Broadbean</span><span class="sxs-lookup"><span data-stu-id="b0d5a-157">Remove a Broadbean job posting</span></span>

<span data-ttu-id="b0d5a-158">Vous pouvez supprimer une publication d'offre d'emploi de Broadbean comme bon vous semble.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-158">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="b0d5a-159">Dans Attract, ouvrez l'emploi que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-159">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="b0d5a-160">Dans la section **Publications**, sélectionnez le bouton représentant des points de suspension (**...**) qui correspond Broadbean, puis sélectionnez **Supprimer la publication**.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-160">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="b0d5a-161">Une fois que Broadbean a supprimé l'offre d'emploi, l'article Broadbean dans Attract a un bouton **Publier maintenant**.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-161">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="b0d5a-162">La présence de ce bouton indique que l'offre d'emploi a été supprimée et peut être publiée de nouveau.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-162">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-the-broadbean-integration"></a><span data-ttu-id="b0d5a-163">Résoudre les problèmes d'intégration de Broadbean</span><span class="sxs-lookup"><span data-stu-id="b0d5a-163">Troubleshoot the Broadbean integration</span></span>

<span data-ttu-id="b0d5a-164">Si vous avez des problèmes pour publier une offre d'emploi sur Broadbean, essayez ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-164">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="b0d5a-165">Vérifiez que les informations d'identification Broadbean entrées dans Attract sont valides et correctes.</span><span class="sxs-lookup"><span data-stu-id="b0d5a-165">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="b0d5a-166">Si les informations d'identification sont valides et cerrectes, contactez le [Support Broadbean](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="b0d5a-166">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="b0d5a-167">Si le problème persiste, contactez le [Support Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="b0d5a-167">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>
