---
title: Vue d'esemble des crédits et relances
description: Cette rubrique fournit un aperçu des fonctionnalités des crédits et des relances.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 67e0b3d1058e5fc085f51577ccf0b79e51546de0
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976593"
---
# <a name="credit-and-collections-overview"></a><span data-ttu-id="24000-103">Vue d'esemble des crédits et relances</span><span class="sxs-lookup"><span data-stu-id="24000-103">Credit and collections overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24000-104">Vous pouvez gérer les limites de crédit pour vos clients et effectuer des activités de collecte lorsqu'elles deviennent nécessaires.</span><span class="sxs-lookup"><span data-stu-id="24000-104">You can manage credit limits for your customers and perform collection activities when they become necessary.</span></span>

## <a name="credit-management"></a><span data-ttu-id="24000-105">Gestion du crédit</span><span class="sxs-lookup"><span data-stu-id="24000-105">Credit management</span></span>

<span data-ttu-id="24000-106">La gestion du crédit client vous permet de gérer les limites de crédit et de contrôler le flux des commandes client via le processus de validation en fonction des règles de crédit que vous créez.</span><span class="sxs-lookup"><span data-stu-id="24000-106">Customer credit management lets you manage credit limits and control the flow of sales orders through the posting process, based on credit rules that you create.</span></span>

<span data-ttu-id="24000-107">Le processus de gestion des crédits peut inclure n'importe laquelle des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="24000-107">The credit management process can include any of the following steps:</span></span>

- <span data-ttu-id="24000-108">Mettre à jour des attributs de crédit pour des clients afin de fournir des informations supplémentaires sur leur solvabilité.</span><span class="sxs-lookup"><span data-stu-id="24000-108">Update credit attributes for customers to provide additional information about their credit worthiness.</span></span>
- <span data-ttu-id="24000-109">Créer des limites de crédit pour les clients à l'aide d'ajustements de limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="24000-109">Create credit limits for customers by using credit limit adjustments.</span></span>
- <span data-ttu-id="24000-110">Créer des limites de crédit temporaires pour les clients à l'aide d'ajustements de limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="24000-110">Create temporary credit limits for customers by using credit limit adjustments.</span></span> <span data-ttu-id="24000-111">De cette façon, vous pouvez augmenter ou diminuer temporairement les limites de crédit client, en fonction des besoins de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="24000-111">In this way, you can temporarily increase or decrease customer credit limits, based on business requirements.</span></span>
- <span data-ttu-id="24000-112">Ajouter des informations qui peuvent affecter la limite de crédit, telles que des informations sur les assurances et les garanties.</span><span class="sxs-lookup"><span data-stu-id="24000-112">Add information that can affect the credit limit, such as information about insurance and guarantees.</span></span>
- <span data-ttu-id="24000-113">Créer des groupes de crédit client qui relient les clients afin qu'ils puissent partager une seule limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="24000-113">Create customer credit groups that link customers together so that they share a single credit limit.</span></span>
- <span data-ttu-id="24000-114">Attribuer des scores de risque aux clients, puis utiliser les scores pour générer automatiquement des limites de crédit pour ces clients via des ajustements de limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="24000-114">Assign risk scores to customers, and then use the scores to automatically generate credit limits for those customers through credit limit adjustments.</span></span>
- <span data-ttu-id="24000-115">Créer des règles de blocage qui mettent une commande en attente pendant un ou plusieurs processus de validation en fonction de facteurs tels que le risque, les modalités de paiement, les limites de crédit, les montants en souffrance et le pourcentage de la limite de crédit utilisée.</span><span class="sxs-lookup"><span data-stu-id="24000-115">Create blocking rules that put an order on hold during one or more posting processes, based on factors such as risk, payment terms, credit limits, overdue amounts, and the percentage of the credit limit that has been used.</span></span>
- <span data-ttu-id="24000-116">Gérer une liste des commandes client en attente, examiner les motifs de la suspension et atténuer les problèmes.</span><span class="sxs-lookup"><span data-stu-id="24000-116">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate issues.</span></span>
- <span data-ttu-id="24000-117">Libérer des commandes client afin qu'elle poursuivent le processus de validation.</span><span class="sxs-lookup"><span data-stu-id="24000-117">Release sales orders so that they continue through the posting process.</span></span>
- <span data-ttu-id="24000-118">Paramétrer un workflow pour gérer l'approbation des modifications de limites de crédit et des validations de commandes client.</span><span class="sxs-lookup"><span data-stu-id="24000-118">Set up a workflow to manage the approval of credit limit changes and sales order releases.</span></span>

## <a name="collections-management"></a><span data-ttu-id="24000-119">Gestion des recouvrements</span><span class="sxs-lookup"><span data-stu-id="24000-119">Collections management</span></span>

<span data-ttu-id="24000-120">La page **Recouvrements** fournit une vue centralisée de l'emplacement où sont gérées les informations de recouvrements des comptes clients.</span><span class="sxs-lookup"><span data-stu-id="24000-120">The **Collections** page provides a centralized view where accounts receivable collections information is managed.</span></span> <span data-ttu-id="24000-121">Les directeurs des recouvrements peuvent utiliser cette vue centralisée pour gérer les recouvrements.</span><span class="sxs-lookup"><span data-stu-id="24000-121">Collections managers can use this centralized view to manage collections.</span></span> <span data-ttu-id="24000-122">Les agents de recouvrement peuvent lancer le processus de recouvrement soit à partir des listes de clients générées à l'aide de critères de recouvrement prédéfinis, soit à partir de la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="24000-122">Collections agents can begin the collections process either from customer lists that are generated by using predefined collection criteria or from the **Customers** page.</span></span>

<span data-ttu-id="24000-123">Avant de commencer à paramétrer ou utiliser des recouvrements, vous devez comprendre les concepts suivants :</span><span class="sxs-lookup"><span data-stu-id="24000-123">Before you start to set up or work with collections, you should understand the following concepts:</span></span>

- <span data-ttu-id="24000-124">Les instantanés de balance âgée des clients contiennent des informations sur les balances âgées à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="24000-124">Customer aging snapshots contain aged balance information at a specific point in time.</span></span>
- <span data-ttu-id="24000-125">Les regroupements de clients de recouvrement vous aident à organiser votre travail.</span><span class="sxs-lookup"><span data-stu-id="24000-125">Collections customer pools help you organize your work.</span></span>
- <span data-ttu-id="24000-126">Les agents de recouvrement peuvent avoir leurs propres regroupements de clients.</span><span class="sxs-lookup"><span data-stu-id="24000-126">Collections agents can have their own customer pools.</span></span>
- <span data-ttu-id="24000-127">Les pages de liste permettent d'organiser les clients, les activités et les demandes de devis de recouvrement.</span><span class="sxs-lookup"><span data-stu-id="24000-127">List pages organize collections customers, activities, and cases.</span></span>
- <span data-ttu-id="24000-128">Toutes les informations de recouvrement d'un client sont indiquées sur une seule page qui vous permet d'effectuer diverses opérations.</span><span class="sxs-lookup"><span data-stu-id="24000-128">All collections information for a customer is on one page, and you can take action from that page.</span></span>
- <span data-ttu-id="24000-129">Les intérêts et commissions peuvent être exonérés, rétablis ou contrepassés en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="24000-129">Interest and fees can be waived, reinstated, or reversed in one step.</span></span>
- <span data-ttu-id="24000-130">Des transactions d'annulation peuvent être créées en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="24000-130">Write-off transactions can be created in one step.</span></span>
- <span data-ttu-id="24000-131">Les paiements de fonds insuffisants peuvent être traités en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="24000-131">Not sufficient funds (NSF) payments can be processed in one step.</span></span>

<span data-ttu-id="24000-132">Pour une description de ces concepts, voir [Concepts clés de la gestion des recouvrements](./cm-collections-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="24000-132">For descriptions of these concepts, see [Collections management key concepts](./cm-collections-concepts.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="24000-133">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="24000-133">Additional resources</span></span>

[<span data-ttu-id="24000-134">Paramétrage de la gestion du crédit client</span><span class="sxs-lookup"><span data-stu-id="24000-134">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="24000-135">Informations sur le paramétrage de la gestion du crédit client</span><span class="sxs-lookup"><span data-stu-id="24000-135">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="24000-136">Ajout d'informations sur la gestion du crédit pour un client</span><span class="sxs-lookup"><span data-stu-id="24000-136">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="24000-137">Groupes de créditer du client</span><span class="sxs-lookup"><span data-stu-id="24000-137">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="24000-138">Ajustements de limite de crédit client</span><span class="sxs-lookup"><span data-stu-id="24000-138">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="24000-139">Blocages pour les commandes client</span><span class="sxs-lookup"><span data-stu-id="24000-139">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="24000-140">Tâches périodiques de gestion des crédits client</span><span class="sxs-lookup"><span data-stu-id="24000-140">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)
