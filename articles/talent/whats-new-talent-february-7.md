---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (7 février 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b89fc15130755a80b56f26cf7c61674a26f43e36
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "858926"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-7-2019"></a><span data-ttu-id="c9521-103">Nouveautés ou modifications dans Dynamics 365 for Talent (7 février 2019)</span><span class="sxs-lookup"><span data-stu-id="c9521-103">What's new or changed in Dynamics 365 for Talent (February 7, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c9521-104">Cette rubrique décrit les fonctionnalités inédites ou ayant fait l'objet de modifications dans Talent.</span><span class="sxs-lookup"><span data-stu-id="c9521-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="c9521-105">Modifications apportées à Attract</span><span class="sxs-lookup"><span data-stu-id="c9521-105">Changes in Attract</span></span>

### <a name="interview-scheduling-enhancements"></a><span data-ttu-id="c9521-106">Améliorations de la planification des entretiens</span><span class="sxs-lookup"><span data-stu-id="c9521-106">Interview scheduling enhancements</span></span>
<span data-ttu-id="c9521-107">Des améliorations ont été apportées à l'expérience de planification des entretiens de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="c9521-107">Improvements have been made to the end-to-end interview scheduling experience.</span></span> <span data-ttu-id="c9521-108">Vous pouvez désormais voir la disponibilité du calendrier d'un candidat interne et utiliser le calendrier du candidat interne pour les recommandations du programme.</span><span class="sxs-lookup"><span data-stu-id="c9521-108">You can now see the calendar availability of an internal candidate and use the internal candidate’s calendar for schedule recommendations.</span></span> <span data-ttu-id="c9521-109">Pour en savoir plus, consultez la rubrique [Planification et commentaires sur les entretiens](interview-scheduling-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="c9521-109">For more information, see [Interview scheduling and feedback](interview-scheduling-feedback.md).</span></span>

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a><span data-ttu-id="c9521-110">Offre d'emploi sur LinkedIn : problème de société inappropriée corrigé</span><span class="sxs-lookup"><span data-stu-id="c9521-110">Job posting to LinkedIn – company mismatch issue fixed</span></span>
<span data-ttu-id="c9521-111">Un problème a été corrigé suite à la publication d'offres d'emploi sur LinkedIn depuis Attract sous un mauvais nom de société.</span><span class="sxs-lookup"><span data-stu-id="c9521-111">An issue has been fixed where jobs posted to LinkedIn from Attract were appearing under the wrong company name.</span></span> <span data-ttu-id="c9521-112">Pour plus d'informations, voir [Créer, approuver et publier des annonces dans Attract](creating-jobs-attract.md).</span><span class="sxs-lookup"><span data-stu-id="c9521-112">For more information, see [Create, approve, and post jobs in Attract](creating-jobs-attract.md).</span></span>

### <a name="career-site-url-displayed-in-admin-settings"></a><span data-ttu-id="c9521-113">URL du site de carrière affichée dans les paramètres d'administration</span><span class="sxs-lookup"><span data-stu-id="c9521-113">Career site URL displayed in Admin settings</span></span>
<span data-ttu-id="c9521-114">L'URL de la page d'accueil du site de carrière s'affiche désormais dans **Paramètres d'administration** sous **Gestion du site de carrière**.</span><span class="sxs-lookup"><span data-stu-id="c9521-114">The career site home page URL is now displayed in **Admin Settings** under **Career Site management**.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="c9521-115">Modifications apportées à Core HR</span><span class="sxs-lookup"><span data-stu-id="c9521-115">Changes in Core HR</span></span>

<span data-ttu-id="c9521-116">**Version 8.1.2134**</span><span class="sxs-lookup"><span data-stu-id="c9521-116">**Build 8.1.2134**</span></span>

### <a name="multiple-compensation-levels-supported-on-jobs"></a><span data-ttu-id="c9521-117">Plusieurs niveaux de rémunération pris en charge par les tâches</span><span class="sxs-lookup"><span data-stu-id="c9521-117">Multiple compensation levels supported on jobs</span></span>
<span data-ttu-id="c9521-118">Cette modification permet de définir plusieurs niveaux de rémunération pour une tâche, générant ainsi des plages de rémunération fixe des employés, qui peuvent différer d'un plan à l'autre pour une même tâche.</span><span class="sxs-lookup"><span data-stu-id="c9521-118">This change allows for more than one compensation level to be defined on a job, enabling employee fixed compensation ranges which may differ between plans when using the same job.</span></span> 

<span data-ttu-id="c9521-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c9521-119">For example:</span></span>    
<span data-ttu-id="c9521-120">*Tâche* - Gestionnaire de compte *Niveaux de rémunération associés :* B1 et B2 - Chaque niveau a une plage de valeurs définie.</span><span class="sxs-lookup"><span data-stu-id="c9521-120">*Job* - Account Manager *Associated compensation levels:* B1 and B2 - Each level has a defined range of values.</span></span> <span data-ttu-id="c9521-121">B1 = 50 000 min, 60 000 moyen, 75 000 max et B2 = 65 000 min, 74 000 moyen, 85 000 max.</span><span class="sxs-lookup"><span data-stu-id="c9521-121">B1 = Min 50,000, Mid 60,000, Max 75,000 and B2 = Min 65,000, Mid 74,000, Max 85,000.</span></span> <span data-ttu-id="c9521-122">En créant une rémunération fixe pour les employés, selon les règles d'éligibilité définies, chaque plan fixe peut désormais désigner la même tâche et différents niveaux de la tâche.</span><span class="sxs-lookup"><span data-stu-id="c9521-122">When creating fixed compensation for employees, based on the eligibility rules defined, each fixed plan can now point to the same job and to different levels on the job.</span></span> <span data-ttu-id="c9521-123">Cela permet de définir des plans dans différentes régions/sociétés et de désigner la même tâche, mais différentes plages sans dupliquer les tâches pour tenir compte de ces différences.</span><span class="sxs-lookup"><span data-stu-id="c9521-123">This allows for plans to be defined in different regions/companies and point to the same job but different ranges without duplicating jobs to account for these differences.</span></span>

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a><span data-ttu-id="c9521-124">Le champ du niveau de rémunération a été ajouté à l'entité de rémunération fixe des employés.</span><span class="sxs-lookup"><span data-stu-id="c9521-124">Compensation level field has been added to the Employee fixed compensation entity</span></span> 
<span data-ttu-id="c9521-125">Avec cette mise à jour, l'entité de rémunération fixe des employés a été mise à jour pour inclure le champ **Niveau de rémunération**.</span><span class="sxs-lookup"><span data-stu-id="c9521-125">With this update, the employee fixed compensation entity has been updated to include the **Compensation level** field.</span></span> <span data-ttu-id="c9521-126">Cet ajout facilite la mise à jour des plans de rémunération fixe des employés.</span><span class="sxs-lookup"><span data-stu-id="c9521-126">This addition makes it easier to update employee fixed compensation plans.</span></span> 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a><span data-ttu-id="c9521-127">Mettre à jour la famille de tâches lors de la mise à jour et de la création de postes</span><span class="sxs-lookup"><span data-stu-id="c9521-127">Update Job family when updating and creating new positions</span></span>
<span data-ttu-id="c9521-128">Lorsque vous modifiez la tâche sur un poste, l'option **Famille de tâches** est désormais définie par défaut sur la tâche sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9521-128">When changing the job on a position, **Job family** will now default based on the job selected.</span></span>

### <a name="performance-improvements-when-rendering-workspaces"></a><span data-ttu-id="c9521-129">Améliorations des performances lors du rendu des espaces de travail</span><span class="sxs-lookup"><span data-stu-id="c9521-129">Performance improvements when rendering workspaces</span></span>
<span data-ttu-id="c9521-130">Les onglets d'analyse des espaces de travail se chargent uniquement lors de l'accès à ces pages.</span><span class="sxs-lookup"><span data-stu-id="c9521-130">Analytics tabs on workspaces will now load only when accessing those pages.</span></span> <span data-ttu-id="c9521-131">Un indicateur s'affiche pendant le rendu initial de la page dans l'angle supérieur gauche de la page.</span><span class="sxs-lookup"><span data-stu-id="c9521-131">An indicator will display during the initial rendering of the page in the upper-left corner of the page.</span></span>
