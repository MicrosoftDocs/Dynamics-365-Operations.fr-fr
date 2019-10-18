---
title: Comptabilité de projet avec des réservations budgétaires générales
description: Cette rubrique fournit des informations sur la comptabilité de projet qui utilise les réservations budgétaires générales pour le secteur public.
author: AlexRenney
manager: AnnBe
ms.date: 04/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetReservation_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 3f376de75951e9468ce95a24e9393d9bdca66672
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183641"
---
# <a name="project-accounting-with-general-budget-reservations"></a><span data-ttu-id="d9579-103">Comptabilité de projet avec des réservations budgétaires générales</span><span class="sxs-lookup"><span data-stu-id="d9579-103">Project accounting with general budget reservations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9579-104">Si votre organisation utilise la comptabilité de projet, vous pouvez inclure dans votre projet des références aux réservations budgétaires générales.</span><span class="sxs-lookup"><span data-stu-id="d9579-104">If your organization uses project accounting, you can include references to your project in general budget reservations.</span></span> <span data-ttu-id="d9579-105">Ces références peuvent affecter la budgétisation, les coûts engagés, ainsi que la réservation et la consommation des sources de financement.</span><span class="sxs-lookup"><span data-stu-id="d9579-105">These references can affect budgeting, committed costs, and the reservation and consumption of funding sources.</span></span>

<span data-ttu-id="d9579-106">Certaines dépenses sont planifiées pour être imputées aux projets.</span><span class="sxs-lookup"><span data-stu-id="d9579-106">Some expenditures are planned to be charged to projects.</span></span> <span data-ttu-id="d9579-107">Lorsque vous créez une réservation budgétaire générale, vous pouvez spécifier le projet et la catégorie de projet pour lesquels un achat est prévu.</span><span class="sxs-lookup"><span data-stu-id="d9579-107">When you create a general budget reservation, you can specify the project and project category that a planned purchase is for.</span></span> <span data-ttu-id="d9579-108">Vous pouvez également spécifier d'autres informations relatives au projet, telles que le prix de vente attendu.</span><span class="sxs-lookup"><span data-stu-id="d9579-108">You can also specify other project-related information, such as the expected sales price.</span></span> <span data-ttu-id="d9579-109">(Pour les entités du secteur public, le prix de vente attendu est généralement le prix de revient.) Toutes ces informations sont incluses dans les documents d'achat qui sont générés pour les projets ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="d9579-109">(For public sector entities, the expected sales price is typically the cost price.) All this information is included on the purchasing documents that are generated for projects later.</span></span>

<span data-ttu-id="d9579-110">Si la réservation budgétaire générale contient une répartition de projet, la commande fournisseur, la demande d'achat, ou la facture fournisseur qui référence la réservation doivent inclure la répartition de projet et toutes les informations de projet.</span><span class="sxs-lookup"><span data-stu-id="d9579-110">If the general budget reservation contains a project distribution, the purchase order, purchase requisition, or vendor invoice that references the reservation must include the project distribution and all project information.</span></span> <span data-ttu-id="d9579-111">Ces informations sont automatiquement copiées sur le document source de la réservation budgétaire générale.</span><span class="sxs-lookup"><span data-stu-id="d9579-111">This information is automatically copied to the source document from the general budget reservation.</span></span>

## <a name="turn-on-tracking-of-committed-costs-for-general-budget-reservations"></a><span data-ttu-id="d9579-112">Activer le suivi des coûts engagés pour les réservations budgétaires générales</span><span class="sxs-lookup"><span data-stu-id="d9579-112">Turn on tracking of committed costs for general budget reservations</span></span>

<span data-ttu-id="d9579-113">Les coûts engagés du projet sont créés lorsque les documents d'achat sont approuvés, confirmées, ou validés.</span><span class="sxs-lookup"><span data-stu-id="d9579-113">Project committed costs are created when purchasing documents are approved, confirmed, or posted.</span></span> <span data-ttu-id="d9579-114">Les coûts représentent les montants qui seront dépensés sur un projet.</span><span class="sxs-lookup"><span data-stu-id="d9579-114">The costs represent amounts that will be spent on a project.</span></span> <span data-ttu-id="d9579-115">Les chefs de projet peuvent afficher les coûts en attente pour un projet afin de suivre précisément les coûts de leur projet.</span><span class="sxs-lookup"><span data-stu-id="d9579-115">Project managers can view pending costs for a project to track accurate information about their project's costs.</span></span>

1. <span data-ttu-id="d9579-116">Accédez à **Gestion de projets et comptabilité \> Paramétrage \> Paramètres de gestion de projets et de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="d9579-116">Go to **Project management and accounting \> Setup \> Project management and accounting parameters**.</span></span>
2. <span data-ttu-id="d9579-117">Dans l'onglet **Contrôle des coûts**, sous l'organisateur **Engagements en termes de coûts**, définissez l'option **Réservation budgétaire générale** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d9579-117">On the **Cost control** tab, on the **Cost commitments** FastTab, set the **General budget reservation** option to **Yes**.</span></span>

    - <span data-ttu-id="d9579-118">Les options **Demande d'achat**, **Commande fournisseur** et **Facture fournisseur** sont automatiquement définies sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d9579-118">The **Purchase requisition**, **Purchase order**, and **Vendor invoice** options will automatically be set to **Yes**.</span></span>
    - <span data-ttu-id="d9579-119">Lorsque la réservation budgétaire générale est validée, elle est comptabilisée dans les coûts engagés du projet.</span><span class="sxs-lookup"><span data-stu-id="d9579-119">When the general budget reservation is posted, it will be counted in the project's committed costs.</span></span>

## <a name="specify-project-information-in-a-general-budget-reservation"></a><span data-ttu-id="d9579-120">Spécifier les informations de projet dans une réservation budgétaire générale</span><span class="sxs-lookup"><span data-stu-id="d9579-120">Specify project information in a general budget reservation</span></span>

1. <span data-ttu-id="d9579-121">Accédez à **Budgétisation \> Réservations budgétaires générales**.</span><span class="sxs-lookup"><span data-stu-id="d9579-121">Go to **Budgeting \> General budget reservations**.</span></span>
2. <span data-ttu-id="d9579-122">Créez une réservation budgétaire générale.</span><span class="sxs-lookup"><span data-stu-id="d9579-122">Create a general budget reservation.</span></span>
3. <span data-ttu-id="d9579-123">Dans l'organisateur **Lignes de réservation budgétaire générale**, ajoutez un ID projet et une catégorie de projet pour chaque ligne de réservation applicable.</span><span class="sxs-lookup"><span data-stu-id="d9579-123">On the **General budget reservation lines** FastTab, add a project ID and project category for each applicable reservation line.</span></span> <span data-ttu-id="d9579-124">Les informations du projet sont automatiquement copiées dans la réservation.</span><span class="sxs-lookup"><span data-stu-id="d9579-124">Information from the project will automatically be copied to the reservation.</span></span>
4. <span data-ttu-id="d9579-125">Facultatif : Pour afficher les détails du projet, dans l'organisateur **Détails de la ligne**, sélectionnez l'onglet **Projet**.</span><span class="sxs-lookup"><span data-stu-id="d9579-125">Optional: To view the project details, on the **Line details** FastTab, select the **Project** tab.</span></span>

## <a name="view-project-committed-costs-for-a-general-budget-reservation"></a><span data-ttu-id="d9579-126">Afficher les coûts engagés du projet pour une réservation budgétaire générale</span><span class="sxs-lookup"><span data-stu-id="d9579-126">View project committed costs for a general budget reservation</span></span>

<span data-ttu-id="d9579-127">Lorsque vous validez une réservation budgétaire générale pour un projet, un coût engagé est créé pour le montant de réservation par rapport à ce projet.</span><span class="sxs-lookup"><span data-stu-id="d9579-127">When you post a general budget reservation for a project, a committed cost is created for the reservation amount against that project.</span></span> <span data-ttu-id="d9579-128">Le coût engagé représente le montant total des distributions de ce projet.</span><span class="sxs-lookup"><span data-stu-id="d9579-128">The committed cost represents the total amount of the distributions to that project.</span></span>

1. <span data-ttu-id="d9579-129">Accédez à **Budgétisation \> Réservations budgétaires générales**.</span><span class="sxs-lookup"><span data-stu-id="d9579-129">Go to **Budgeting \> General budget reservations**.</span></span>
2. <span data-ttu-id="d9579-130">Ouvrez la réservation budgétaire générale validée, et sélectionnez une ligne de réservation.</span><span class="sxs-lookup"><span data-stu-id="d9579-130">Open the posted general budget reservation that you want, and select a reservation line.</span></span>
3. <span data-ttu-id="d9579-131">Sélectionnez **Coûts engagés**.</span><span class="sxs-lookup"><span data-stu-id="d9579-131">Select **Committed costs**.</span></span> <span data-ttu-id="d9579-132">La page **Coûts engagés** s'affiche et indique les coûts engagés associés à la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d9579-132">The **Committed costs** page appears and shows the committed costs that are related to the selected line.</span></span>

    <span data-ttu-id="d9579-133">Les coûts engagés pour les réservations budgétaires générales sont basés sur le montant, peu importe si le coût engagé inclut une quantité et un coût unitaire distincts.</span><span class="sxs-lookup"><span data-stu-id="d9579-133">Committed costs for general budget reservations are based on amount, regardless of whether the committed cost includes a discrete quantity and unit cost.</span></span> <span data-ttu-id="d9579-134">La quantité du coût engagé est toujours 1.</span><span class="sxs-lookup"><span data-stu-id="d9579-134">The committed cost quantity will always be 1.</span></span>
