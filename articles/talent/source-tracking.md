---
title: Suivre les sources pour les profils de candidat et les candidatures
description: Cette rubrique fournit des informations sur la remontée à la source des profils et des candidatures des candidats.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 5b368e97a716cd1ce4f668c2a97326877a2d3dff
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551885"
---
# <a name="track-sources-for-candidate-profiles-and-applications"></a><span data-ttu-id="6f69e-103">Suivre les sources pour les profils de candidat et les candidatures</span><span class="sxs-lookup"><span data-stu-id="6f69e-103">Track sources for candidate profiles and applications</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE] 
> <span data-ttu-id="6f69e-104">La fonctionnalité décrite dans cette rubrique est accessible dans le cadre d'une version préliminaire.</span><span class="sxs-lookup"><span data-stu-id="6f69e-104">Functionality noted in this topic is available as part of a preview review release.</span></span> <span data-ttu-id="6f69e-105">Le contenu et la fonctionnalité peuvent faire l'objet de modifications.</span><span class="sxs-lookup"><span data-stu-id="6f69e-105">The content and the functionality are subject to change.</span></span> <span data-ttu-id="6f69e-106">Pour utiliser cette fonction, demandez à un administrateur de l'activer à l'aide des **Paramètres d'administrateur** dans Attract.</span><span class="sxs-lookup"><span data-stu-id="6f69e-106">To use this feature, ask an administrator to enable it using the **Admin settings** in Attract.</span></span> <span data-ttu-id="6f69e-107">Une version future fournira des états de suivi de la source.</span><span class="sxs-lookup"><span data-stu-id="6f69e-107">A future release will provide source tracking reports.</span></span> <span data-ttu-id="6f69e-108">Pour plus d'informations, voir [Accéder aux fonctions d'aperçu de Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="6f69e-108">For more information, see [Access preview features in Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

<span data-ttu-id="6f69e-109">Lorsque des candidats postulent à un emploi, Attract remonte automatiquement à la source de leur candidature. Cela vous donne des informations précieuses pour cibler vos initiatives de recrutement.</span><span class="sxs-lookup"><span data-stu-id="6f69e-109">When candidates apply for a job, Attract automatically tracks the source of their applications, providing you with valuable information to help you target your recruiting efforts.</span></span> <span data-ttu-id="6f69e-110">Les recruteurs et les responsables du recrutement peuvent également sélectionner une source de candidature lorsqu'ils ajoutent manuellement un candidat à un emploi ou à un vivier de talents.</span><span class="sxs-lookup"><span data-stu-id="6f69e-110">Recruiters and hiring managers can also select an application source while manually adding a candidate to a job or talent pool.</span></span>

<span data-ttu-id="6f69e-111">Vous pouvez afficher la source de la candidature dans les détails des activités de candidature sous l'onglet **Activité**, ainsi que dans l'historique de candidature disponible sous **Profil** dans les viviers de talents.</span><span class="sxs-lookup"><span data-stu-id="6f69e-111">You can view the application source in the application activity details under the **Activity** tab, as well as in the application history available under **Profile** in talent pools.</span></span> <span data-ttu-id="6f69e-112">Vous pouvez trouver la source du profil d'un candidat dans les détails du candidat sous l'onglet **Profil** dans les candidatures et les viviers de talents.</span><span class="sxs-lookup"><span data-stu-id="6f69e-112">You can find a candidate's profile source in the candidate details under the **Profile** tab in both applications and talent pools.</span></span>

> [!NOTE] 
> <span data-ttu-id="6f69e-113">Vous pouvez trouver des modèles de traitement dans le [Module complémentaire Recrutement complet](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="6f69e-113">You can find process templates in the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>

## <a name="pre-configured-sources"></a><span data-ttu-id="6f69e-114">Sources préconfigurées</span><span class="sxs-lookup"><span data-stu-id="6f69e-114">Pre-configured sources</span></span>

<span data-ttu-id="6f69e-115">La liste de sources par défaut contient les sources de candidature courantes.</span><span class="sxs-lookup"><span data-stu-id="6f69e-115">The default source list contains common application sources.</span></span> <span data-ttu-id="6f69e-116">Certains types de sources, tels que **Site d'emplois** et **Réseau social**, comportent des détails de source supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="6f69e-116">Some source types, like **Job board** and **Social Network**, have additional source details.</span></span> <span data-ttu-id="6f69e-117">Par exemple, **Réseau social** inclut Facebook et Twitter.</span><span class="sxs-lookup"><span data-stu-id="6f69e-117">For example, **Social Network** includes Facebook and Twitter.</span></span> <span data-ttu-id="6f69e-118">Le type de source **Recommandation** permet de spécifier un employé interne comme parrain.</span><span class="sxs-lookup"><span data-stu-id="6f69e-118">The **Referral** source type allows you to specify an internal employee as the referrer.</span></span> <span data-ttu-id="6f69e-119">La liste de sources par défaut comprend les sources préconfigurées suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f69e-119">The default source list includes the following pre-configured sources:</span></span>

-   <span data-ttu-id="6f69e-120">Site de carrière Attract</span><span class="sxs-lookup"><span data-stu-id="6f69e-120">Attract career site</span></span>

-   <span data-ttu-id="6f69e-121">Agence</span><span class="sxs-lookup"><span data-stu-id="6f69e-121">Agency</span></span>

-   <span data-ttu-id="6f69e-122">Salon de l'emploi</span><span class="sxs-lookup"><span data-stu-id="6f69e-122">Career Fair</span></span>

-   <span data-ttu-id="6f69e-123">Marketing de la société</span><span class="sxs-lookup"><span data-stu-id="6f69e-123">Company Marketing</span></span>

-   <span data-ttu-id="6f69e-124">Conférences et salons commerciaux</span><span class="sxs-lookup"><span data-stu-id="6f69e-124">Conferences & Trade shows</span></span>

-   <span data-ttu-id="6f69e-125">Association professionnelle</span><span class="sxs-lookup"><span data-stu-id="6f69e-125">Professional Association</span></span>

-   <span data-ttu-id="6f69e-126">Site d'emploi</span><span class="sxs-lookup"><span data-stu-id="6f69e-126">Job board</span></span>

    -   <span data-ttu-id="6f69e-127">Indeed</span><span class="sxs-lookup"><span data-stu-id="6f69e-127">Indeed</span></span>

    -   <span data-ttu-id="6f69e-128">Seek</span><span class="sxs-lookup"><span data-stu-id="6f69e-128">Seek</span></span>

    -   <span data-ttu-id="6f69e-129">CareerBuilder</span><span class="sxs-lookup"><span data-stu-id="6f69e-129">CareerBuilder</span></span>

    -   <span data-ttu-id="6f69e-130">Google Jobs</span><span class="sxs-lookup"><span data-stu-id="6f69e-130">Google Jobs</span></span>

    -   <span data-ttu-id="6f69e-131">Xing</span><span class="sxs-lookup"><span data-stu-id="6f69e-131">Xing</span></span>

    -   <span data-ttu-id="6f69e-132">Glassdoor</span><span class="sxs-lookup"><span data-stu-id="6f69e-132">Glassdoor</span></span>

    -   <span data-ttu-id="6f69e-133">Monster</span><span class="sxs-lookup"><span data-stu-id="6f69e-133">Monster Jobs</span></span>

-   <span data-ttu-id="6f69e-134">Magazines et publications</span><span class="sxs-lookup"><span data-stu-id="6f69e-134">Magazines & Publications</span></span>

-   <span data-ttu-id="6f69e-135">Réseau social</span><span class="sxs-lookup"><span data-stu-id="6f69e-135">Social Network</span></span>

    -   <span data-ttu-id="6f69e-136">Facebook</span><span class="sxs-lookup"><span data-stu-id="6f69e-136">Facebook</span></span>

    -   <span data-ttu-id="6f69e-137">Twitter</span><span class="sxs-lookup"><span data-stu-id="6f69e-137">Twitter</span></span>

-   <span data-ttu-id="6f69e-138">Recrutement universitaire</span><span class="sxs-lookup"><span data-stu-id="6f69e-138">University Recruiting</span></span>

-   <span data-ttu-id="6f69e-139">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="6f69e-139">LinkedIn</span></span>

-   <span data-ttu-id="6f69e-140">Petites annonces</span><span class="sxs-lookup"><span data-stu-id="6f69e-140">Classifieds</span></span>

-   <span data-ttu-id="6f69e-141">Renvoi</span><span class="sxs-lookup"><span data-stu-id="6f69e-141">Referral</span></span>

-   <span data-ttu-id="6f69e-142">Ajouté par le recruteur</span><span class="sxs-lookup"><span data-stu-id="6f69e-142">Added by Recruiter</span></span>

-   <span data-ttu-id="6f69e-143">Autre/s</span><span class="sxs-lookup"><span data-stu-id="6f69e-143">Other</span></span>

## <a name="customize-the-source-list"></a><span data-ttu-id="6f69e-144">Personnaliser la liste des sources</span><span class="sxs-lookup"><span data-stu-id="6f69e-144">Customize the source list</span></span> 

<span data-ttu-id="6f69e-145">Vous pouvez étendre la liste des sources pour inclure des sources de candidature supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="6f69e-145">You can extend the source list to include additional application sources.</span></span> <span data-ttu-id="6f69e-146">Pour personnaliser cette liste, suivez les instructions de [Étendre les ensembles d'options dans Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span><span class="sxs-lookup"><span data-stu-id="6f69e-146">To customize this list, follow the instructions in [Extending Option Sets in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span></span> <span data-ttu-id="6f69e-147">Modifiez l'entité **TalentSource** pour inclure des sources supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="6f69e-147">Edit the **TalentSource** entity to include additional sources.</span></span> 

<span data-ttu-id="6f69e-148">Pour éviter d'affecter négativement l'interface utilisateur (IU), ne modifiez ni ne supprimez les valeurs d'énumération **TalentCategory** (pas les noms) pour :</span><span class="sxs-lookup"><span data-stu-id="6f69e-148">To avoid negatively impacting the user interface (UI), don't edit or delete the **TalentCategory** enum values (not names) for the following:</span></span>

- <span data-ttu-id="6f69e-149">**Renvoi**</span><span class="sxs-lookup"><span data-stu-id="6f69e-149">**Referral**</span></span>
- <span data-ttu-id="6f69e-150">**LinkedIn**</span><span class="sxs-lookup"><span data-stu-id="6f69e-150">**LinkedIn**</span></span>
- <span data-ttu-id="6f69e-151">**Autre/s**</span><span class="sxs-lookup"><span data-stu-id="6f69e-151">**Other**</span></span>

<span data-ttu-id="6f69e-152">Au lieu de cela, vous pouvez étendre l'énumération **TalentSource** pour ajouter d'autres types de sources.</span><span class="sxs-lookup"><span data-stu-id="6f69e-152">Instead, you can extend the **TalentSource** enum to add other types of sources.</span></span>
