---
title: Workflows d’accord de gestion des remises
description: Cette rubrique explique comment configurer un workflow d’accord de gestion des remises pour approuver et activer les accords.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ee342de6d069131e230120c5d65aef58da8e632a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020384"
---
# <a name="rebate-management-deal-workflows"></a><span data-ttu-id="f6d46-103">Workflows d’accord de gestion des remises</span><span class="sxs-lookup"><span data-stu-id="f6d46-103">Rebate management deal workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f6d46-104">Pour approuver les accords de remise, la gestion des remises utilise la même plateforme de workflow que les autres applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f6d46-104">To approve rebate deals, Rebate management uses the same workflow platform as other Finance and Operations apps.</span></span> <span data-ttu-id="f6d46-105">Deux processus de travail sont associés à chaque workflow :</span><span class="sxs-lookup"><span data-stu-id="f6d46-105">Two job processes are associated with every workflow:</span></span>

- <span data-ttu-id="f6d46-106">Un élément du workflow active l’accord afin que l’utilisateur ou le processus de workflow puisse approuver les transactions.</span><span class="sxs-lookup"><span data-stu-id="f6d46-106">One element of the workflow activates the deal so that the user or workflow process can approve the transactions.</span></span>
- <span data-ttu-id="f6d46-107">Un élément du workflow approuve l’accord.</span><span class="sxs-lookup"><span data-stu-id="f6d46-107">One element of the workflow approves the deal.</span></span>

<span data-ttu-id="f6d46-108">Avant de pouvoir utiliser un accord de remise, celui-ci doit être activé dans le module **Gestion des remises**.</span><span class="sxs-lookup"><span data-stu-id="f6d46-108">Before you can use a rebate deal, it must be active in the **Rebate management** module.</span></span> <span data-ttu-id="f6d46-109">Pour activer un accord, vous devez d’abord créer et configurer un *Workflow d’accord de gestion des remises*.</span><span class="sxs-lookup"><span data-stu-id="f6d46-109">To activate a deal, you must first create and configure a *Rebate management deal workflow*.</span></span>

<span data-ttu-id="f6d46-110">Une fois qu’un workflow a été activé pour la gestion des remises, les utilisateurs ne peuvent pas approuver manuellement les accords.</span><span class="sxs-lookup"><span data-stu-id="f6d46-110">After a workflow is activated for Rebate management, users can't manually approve deals.</span></span> <span data-ttu-id="f6d46-111">Le workflow doit toujours être utilisé.</span><span class="sxs-lookup"><span data-stu-id="f6d46-111">The workflow must be always used.</span></span>

## <a name="create-and-manage-rebate-management-deal-workflows"></a><span data-ttu-id="f6d46-112">Créer et gérer des workflows d’accord de gestion des remises</span><span class="sxs-lookup"><span data-stu-id="f6d46-112">Create and manage Rebate management deal workflows</span></span>

<span data-ttu-id="f6d46-113">Pour utiliser vos workflows d’accord de gestion des remises, accédez à **Gestion des remises \> Paramétrage \> Workflows de gestion des remises**.</span><span class="sxs-lookup"><span data-stu-id="f6d46-113">To work with your Rebate management deal workflows, go to **Rebate management \> Setup \> Rebate management workflows**.</span></span> <span data-ttu-id="f6d46-114">Là, vous pouvez afficher, créer et mettre à jour les workflows selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="f6d46-114">There, you can view, create, and update workflows as required.</span></span> <span data-ttu-id="f6d46-115">Un seul workflow de ce type peut être actif à la fois.</span><span class="sxs-lookup"><span data-stu-id="f6d46-115">Only one workflow of this type can be active at a time.</span></span> <span data-ttu-id="f6d46-116">Pour plus d’informations sur les workflows, savoir comment utiliser la page **Workflows de gestion des remises** et comment créer des workflows, reportez-vous à la rubrique [Vue d’ensemble du système de workflow](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) et ses rubriques connexes.</span><span class="sxs-lookup"><span data-stu-id="f6d46-116">For more information about workflows, how to work with the **Rebate management workflows** page, and how to create workflows, see [Workflow system overview](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) and its related topics.</span></span>

## <a name="use-a-workflow-to-activate-a-deal"></a><span data-ttu-id="f6d46-117">Utilisez un workflow pour activer un accord</span><span class="sxs-lookup"><span data-stu-id="f6d46-117">Use a workflow to activate a deal</span></span>

<span data-ttu-id="f6d46-118">Pour activer un accord via un workflow, ouvrez l’accord (par exemple, sur la page **Tous les accords de gestion des remises**).</span><span class="sxs-lookup"><span data-stu-id="f6d46-118">To activate a deal through a workflow, open the deal (for example, on the **All rebate management deals** page).</span></span> <span data-ttu-id="f6d46-119">Ensuite, dans le volet Actions, sélectionnez **Workflow \> Envoyer**.</span><span class="sxs-lookup"><span data-stu-id="f6d46-119">Then, on the Action Pane, select **Workflow \> Submit**.</span></span> <span data-ttu-id="f6d46-120">Une fois le nouvel accord traité et approuvé via le workflow, il sera actif et prêt à être utilisé.</span><span class="sxs-lookup"><span data-stu-id="f6d46-120">After the new deal has been processed and approved through the workflow, it will be active and ready to use.</span></span>

<span data-ttu-id="f6d46-121">Une fois qu’un accord a été activé, vous ne pouvez pas modifier sa configuration.</span><span class="sxs-lookup"><span data-stu-id="f6d46-121">After a deal has been activated, you can't change its setup.</span></span> <span data-ttu-id="f6d46-122">Si vous devez modifier un accord actif, désactivez-le, puis créez-en un nouveau.</span><span class="sxs-lookup"><span data-stu-id="f6d46-122">If you must change an active deal, inactivate it, and then create a new deal.</span></span> <span data-ttu-id="f6d46-123">Si le nouvel accord ressemble à l’ancien, vous pouvez le créer en copiant l’ancien.</span><span class="sxs-lookup"><span data-stu-id="f6d46-123">If the new deal will resemble the old deal, you can create it by copying the old deal.</span></span>
