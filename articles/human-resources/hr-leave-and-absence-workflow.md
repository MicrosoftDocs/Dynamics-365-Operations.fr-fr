---
title: Créer un workflow de demande d'absence
description: Créez un workflow de demande de congé et d'absence pour gérer les demandes de congé de manière cohérente dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c2e994d11bbd45907a48c1f3955fa751a676a327
ms.sourcegitcommit: e69cfc74e9dbce64ae0e1ab7cd441e5ae6efd4c9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "3353686"
---
# <a name="create-a-leave-request-workflow"></a><span data-ttu-id="c0f54-103">Créer un workflow de demande d'absence</span><span class="sxs-lookup"><span data-stu-id="c0f54-103">Create a leave request workflow</span></span>

<span data-ttu-id="c0f54-104">Vous créez un workflow dans Dynamics 365 Human Resources pour gérer de manière cohérente les demandes de congé et d'absence.</span><span class="sxs-lookup"><span data-stu-id="c0f54-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your leave and absence requests.</span></span> <span data-ttu-id="c0f54-105">Un workflow **Congé et absence** vous permet de :</span><span class="sxs-lookup"><span data-stu-id="c0f54-105">A **Leave and absence** workflow lets you:</span></span>

- <span data-ttu-id="c0f54-106">Définir des tâches</span><span class="sxs-lookup"><span data-stu-id="c0f54-106">Define tasks</span></span>
- <span data-ttu-id="c0f54-107">Déterminer qui doit effectuer les tâches</span><span class="sxs-lookup"><span data-stu-id="c0f54-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="c0f54-108">Spécifier qui peut approuver ou rejeter les demandes</span><span class="sxs-lookup"><span data-stu-id="c0f54-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-leave-and-absence-request-workflow"></a><span data-ttu-id="c0f54-109">Créer un workflow de demande de congé ou d'absence</span><span class="sxs-lookup"><span data-stu-id="c0f54-109">Create a Leave and absence request workflow</span></span>

1. <span data-ttu-id="c0f54-110">Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="c0f54-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="c0f54-111">Sous **Configuration**, sélectionnez **Workflows des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="c0f54-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="c0f54-112">Sélectionnez **Nouveau**, puis sélectionnez **Demande de congé et d'absence**.</span><span class="sxs-lookup"><span data-stu-id="c0f54-112">Select **New**, and then select **Leave and absence request**.</span></span> 

4. <span data-ttu-id="c0f54-113">Quand la boîte de dialogue **Ouvrir ce fichier ?** apparaît, sélectionnez **Ouvrir** et connectez-vous avec les informations d'identification de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="c0f54-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="c0f54-114">Utilisez l'éditeur de workflow pour créer un workflow pour vos demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="c0f54-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="c0f54-115">Pour plus d'informations sur l'utilisation des workflows, consultez [Créer une vue d'ensemble des workflows](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="c0f54-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="c0f54-116">Éléments de données liés au workflow de demande de congé ou d'absence</span><span class="sxs-lookup"><span data-stu-id="c0f54-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="c0f54-117">Vous pouvez utiliser les éléments de données suivants pour créer des approbations conditionnelles ou automatiques dans les workflows pour les demandes de congé et d'absence :</span><span class="sxs-lookup"><span data-stu-id="c0f54-117">You can use the following data elements to create conditional or automatic approvals in workflows for leave and absence requests:</span></span>

- <span data-ttu-id="c0f54-118">**Commentaire**</span><span class="sxs-lookup"><span data-stu-id="c0f54-118">**Comment**</span></span>
- <span data-ttu-id="c0f54-119">**Société**</span><span class="sxs-lookup"><span data-stu-id="c0f54-119">**Company**</span></span>
- <span data-ttu-id="c0f54-120">**Créateur**</span><span class="sxs-lookup"><span data-stu-id="c0f54-120">**Created by**</span></span>
- <span data-ttu-id="c0f54-121">**Date et heure de création**</span><span class="sxs-lookup"><span data-stu-id="c0f54-121">**Created date and time**</span></span>
- <span data-ttu-id="c0f54-122">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="c0f54-122">**End date**</span></span>
- <span data-ttu-id="c0f54-123">**Type de congé**</span><span class="sxs-lookup"><span data-stu-id="c0f54-123">**Leave type**</span></span>
- <span data-ttu-id="c0f54-124">**Modifiées par**</span><span class="sxs-lookup"><span data-stu-id="c0f54-124">**Modified by**</span></span>
- <span data-ttu-id="c0f54-125">**Date et heure de modification**</span><span class="sxs-lookup"><span data-stu-id="c0f54-125">**Modified date and time**</span></span>
- <span data-ttu-id="c0f54-126">**Code motif**</span><span class="sxs-lookup"><span data-stu-id="c0f54-126">**Reason code**</span></span>
- <span data-ttu-id="c0f54-127">**ID demande**</span><span class="sxs-lookup"><span data-stu-id="c0f54-127">**Request ID**</span></span>
- <span data-ttu-id="c0f54-128">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="c0f54-128">**Start date**</span></span>
- <span data-ttu-id="c0f54-129">**État**</span><span class="sxs-lookup"><span data-stu-id="c0f54-129">**Status**</span></span> 
- <span data-ttu-id="c0f54-130">**Date de soumission**</span><span class="sxs-lookup"><span data-stu-id="c0f54-130">**Submission date**</span></span>
- <span data-ttu-id="c0f54-131">**Soumis par**</span><span class="sxs-lookup"><span data-stu-id="c0f54-131">**Submitted by**</span></span>
- <span data-ttu-id="c0f54-132">**Soumis par les Ressources humaines**</span><span class="sxs-lookup"><span data-stu-id="c0f54-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="c0f54-133">**Soumis par le Responsable**</span><span class="sxs-lookup"><span data-stu-id="c0f54-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="c0f54-134">**Soumis au nom de**</span><span class="sxs-lookup"><span data-stu-id="c0f54-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="c0f54-135">**Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="c0f54-135">**Worker**</span></span>
- <span data-ttu-id="c0f54-136">**Type de collaborateur**</span><span class="sxs-lookup"><span data-stu-id="c0f54-136">**Worker type**</span></span>

<span data-ttu-id="c0f54-137">Ces exemples montrent comment créer différents types de conditions de workflow à l'aide de ces éléments de données :</span><span class="sxs-lookup"><span data-stu-id="c0f54-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="c0f54-138">Utilisez **Code de raison** dans une instruction conditionnelle pour acheminer les demandes de congé maladie avec le code de motif **Chirurgie** aux RH pour approbation, tout en acheminant tous les autres codes de motif au responsable.</span><span class="sxs-lookup"><span data-stu-id="c0f54-138">Use **Reason code** in a conditional statement to route sick leave requests with the reason code **Surgery** to HR for approval, while routing all other reason codes to the manager.</span></span> <span data-ttu-id="c0f54-139">Pour plus d'informations sur les instructions conditionnelles, consultez [Configurer des décisions conditionnelles dans un workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span><span class="sxs-lookup"><span data-stu-id="c0f54-139">For more information about conditional statements, see [Configure conditional decisions in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span></span> 

- <span data-ttu-id="c0f54-140">Utilisez **Soumis par les Ressources humaines** et **Soumis par le Responsable** dans une action automatique pour approuver automatiquement les demandes de congé que ces rôles soumettent au nom des employés.</span><span class="sxs-lookup"><span data-stu-id="c0f54-140">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="c0f54-141">Pour plus d'informations sur les actions automatiques, consultez [Configurer des processus d'approbation dans un workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="c0f54-141">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="c0f54-142">Utilisez **Type de congé** dans une instruction conditionnelle ou une action automatique pour contrôler la façon dont le workflow achemine les demandes avec certains types de congés.</span><span class="sxs-lookup"><span data-stu-id="c0f54-142">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0f54-143">Voir également :</span><span class="sxs-lookup"><span data-stu-id="c0f54-143">See also</span></span>

- [<span data-ttu-id="c0f54-144">Vue d'ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="c0f54-144">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
