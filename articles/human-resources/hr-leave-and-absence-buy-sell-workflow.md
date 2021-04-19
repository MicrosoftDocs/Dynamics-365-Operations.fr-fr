---
title: Créer un workflow de demande d’achat et de vente de congés
description: Créez un workflow de demande d’achat et de vente de congés pour gérer les demandes d’achat et de vente de congés de manière cohérente dans Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a0ddb3ea3aa7f1941ff486d7a3e1db5846fac3eb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790546"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="3c76d-103">Créer un workflow de demande d’achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="3c76d-103">Create a buy and sell leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3c76d-104">Vous créez un workflow dans Dynamics 365 Human Resources pour gérer de manière cohérente les demandes d’achat et de vente de congés.</span><span class="sxs-lookup"><span data-stu-id="3c76d-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your buy and sell leave requests.</span></span> <span data-ttu-id="3c76d-105">Un workflow **Achat et vente de congés** vous permet de :</span><span class="sxs-lookup"><span data-stu-id="3c76d-105">A **Buy and sell leave** workflow lets you:</span></span>

- <span data-ttu-id="3c76d-106">Définir des tâches</span><span class="sxs-lookup"><span data-stu-id="3c76d-106">Define tasks</span></span>
- <span data-ttu-id="3c76d-107">Déterminer qui doit effectuer les tâches</span><span class="sxs-lookup"><span data-stu-id="3c76d-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="3c76d-108">Spécifier qui peut approuver ou rejeter les demandes</span><span class="sxs-lookup"><span data-stu-id="3c76d-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="3c76d-109">Créer un workflow de demande d’achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="3c76d-109">Create a buy and sell leave request workflow</span></span>

1. <span data-ttu-id="3c76d-110">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="3c76d-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="3c76d-111">Sous **Configuration**, sélectionnez **Workflows des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="3c76d-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="3c76d-112">Sélectionnez **Nouveau**, puis sélectionnez **Demandes d’achat et de vente de congés**.</span><span class="sxs-lookup"><span data-stu-id="3c76d-112">Select **New**, and then select **Buy and sell leave request**.</span></span> 

4. <span data-ttu-id="3c76d-113">Quand la boîte de dialogue **Ouvrir ce fichier ?** apparaît, sélectionnez **Ouvrir** et connectez-vous avec les informations d’identification de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="3c76d-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="3c76d-114">Utilisez l’éditeur de workflow pour créer un workflow pour vos demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="3c76d-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="3c76d-115">Pour plus d’informations sur l’utilisation des workflows, consultez [Créer une vue d’ensemble des workflows](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="3c76d-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="3c76d-116">Éléments de données liés au workflow de demande de congé ou d’absence</span><span class="sxs-lookup"><span data-stu-id="3c76d-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="3c76d-117">Vous pouvez utiliser les éléments de données suivants pour créer des approbations conditionnelles ou automatiques dans les workflows de demandes d’achat et de vente de congés :</span><span class="sxs-lookup"><span data-stu-id="3c76d-117">You can use the following data elements to create conditional or automatic approvals in workflows for buy and sell leave requests:</span></span>

- <span data-ttu-id="3c76d-118">**Montant**</span><span class="sxs-lookup"><span data-stu-id="3c76d-118">**Amount**</span></span>
- <span data-ttu-id="3c76d-119">**Stratégie d’achat et de vente de congés**</span><span class="sxs-lookup"><span data-stu-id="3c76d-119">**Buy and sell leave policy**</span></span>
- <span data-ttu-id="3c76d-120">**Société**</span><span class="sxs-lookup"><span data-stu-id="3c76d-120">**Company**</span></span>
- <span data-ttu-id="3c76d-121">**Créé(e) par**</span><span class="sxs-lookup"><span data-stu-id="3c76d-121">**Created by**</span></span>
- <span data-ttu-id="3c76d-122">**Date et heure de création**</span><span class="sxs-lookup"><span data-stu-id="3c76d-122">**Created date and time**</span></span>
- <span data-ttu-id="3c76d-123">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="3c76d-123">**End date**</span></span>
- <span data-ttu-id="3c76d-124">**Type de congé**</span><span class="sxs-lookup"><span data-stu-id="3c76d-124">**Leave type**</span></span>
- <span data-ttu-id="3c76d-125">**Modifié(e) par**</span><span class="sxs-lookup"><span data-stu-id="3c76d-125">**Modified by**</span></span>
- <span data-ttu-id="3c76d-126">**Date et heure de modification**</span><span class="sxs-lookup"><span data-stu-id="3c76d-126">**Modified date and time**</span></span>
- <span data-ttu-id="3c76d-127">**ID demande**</span><span class="sxs-lookup"><span data-stu-id="3c76d-127">**Request ID**</span></span>
- <span data-ttu-id="3c76d-128">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="3c76d-128">**Start date**</span></span>
- <span data-ttu-id="3c76d-129">**État**</span><span class="sxs-lookup"><span data-stu-id="3c76d-129">**Status**</span></span> 
- <span data-ttu-id="3c76d-130">**Date de soumission**</span><span class="sxs-lookup"><span data-stu-id="3c76d-130">**Submission date**</span></span>
- <span data-ttu-id="3c76d-131">**Soumis par**</span><span class="sxs-lookup"><span data-stu-id="3c76d-131">**Submitted by**</span></span>
- <span data-ttu-id="3c76d-132">**Soumis par les Ressources humaines**</span><span class="sxs-lookup"><span data-stu-id="3c76d-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="3c76d-133">**Soumis par le Responsable**</span><span class="sxs-lookup"><span data-stu-id="3c76d-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="3c76d-134">**Soumis au nom de**</span><span class="sxs-lookup"><span data-stu-id="3c76d-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="3c76d-135">**Collaborateur**</span><span class="sxs-lookup"><span data-stu-id="3c76d-135">**Worker**</span></span>

## <a name="workflow-examples"></a><span data-ttu-id="3c76d-136">Exemples de workflow</span><span class="sxs-lookup"><span data-stu-id="3c76d-136">Workflow examples</span></span>

<span data-ttu-id="3c76d-137">Ces exemples montrent comment créer différents types de conditions de workflow à l’aide de ces éléments de données :</span><span class="sxs-lookup"><span data-stu-id="3c76d-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="3c76d-138">Utilisez **Soumis par les Ressources humaines** et **Soumis par le Responsable** dans une action automatique pour approuver automatiquement les demandes d’achat et de vente de congés que ces rôles soumettent au nom des employés.</span><span class="sxs-lookup"><span data-stu-id="3c76d-138">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve buy and sell leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="3c76d-139">Pour plus d’informations sur les actions automatiques, consultez [Configurer des processus d’approbation dans un workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="3c76d-139">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="3c76d-140">Utilisez **Type de congé** dans une instruction conditionnelle ou une action automatique pour contrôler la façon dont le workflow achemine les demandes avec certains types de congés.</span><span class="sxs-lookup"><span data-stu-id="3c76d-140">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c76d-141">Voir également :</span><span class="sxs-lookup"><span data-stu-id="3c76d-141">See also</span></span>

[<span data-ttu-id="3c76d-142">Vue d’ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="3c76d-142">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)<br>
[<span data-ttu-id="3c76d-143">Gérer les stratégies d’achat et de vente de congés</span><span class="sxs-lookup"><span data-stu-id="3c76d-143">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]