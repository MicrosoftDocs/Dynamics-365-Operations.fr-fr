---
title: Vue d'ensemble de la constatation du produit
description: Cette rubrique fournit des informations sur la fonctionnalité de constatation du produit. Elle offre un cadre flexible qui vous permet de définir des règles spécifiques pour identifier le prix et l'échéancier de produit pour les commandes comportant plusieurs éléments.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 0681636853b38895e4b8875150ea42baadd7b951
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570377"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="676a0-104">Vue d'ensemble de la constatation du produit</span><span class="sxs-lookup"><span data-stu-id="676a0-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="676a0-105">La fonctionnalité de constatation du produit ne peut pas être activée via la gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="676a0-105">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="676a0-106">Vous devez pour l'instant utiliser les clés de configuration pour l'activer.</span><span class="sxs-lookup"><span data-stu-id="676a0-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="676a0-107">Les sociétés du secteur qui vendent plusieurs éléments, tels que des produits, des services, des abonnements, etc., doivent pouvoir éclater les commandes comportant plusieurs éléments afin que le produit puisse être identifié selon un ensemble d'instructions spécifiques et propres au secteur.</span><span class="sxs-lookup"><span data-stu-id="676a0-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="676a0-108">En général le processus de constatation du produit peut être utilisé pour réaliser les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="676a0-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="676a0-109">Répartir le produit, pour garantir que le prix approprié est bien constaté en fonction de la valeur des composants sur les commandes à plusieurs éléments.</span><span class="sxs-lookup"><span data-stu-id="676a0-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="676a0-110">Différer le produit, selon un échéancier de produit qui représente le calendrier et les pourcentages contractuels pour constater le produit au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="676a0-110">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

<span data-ttu-id="676a0-111">La fonctionnalité de constatation du produit offre un cadre flexible qui vous permet de définir des règles spécifiques pour identifier le prix et l'échéancier de produit.</span><span class="sxs-lookup"><span data-stu-id="676a0-111">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="676a0-112">Les produits lancés permettent de prendre en charge la constatation du produit dans les documents de commande client.</span><span class="sxs-lookup"><span data-stu-id="676a0-112">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="676a0-113">Les produits lancés contiennent le paramétrage requis pour déterminer le prix et l'échéancier de produit.</span><span class="sxs-lookup"><span data-stu-id="676a0-113">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="676a0-114">La commande client peut provenir d'un projet en régie.</span><span class="sxs-lookup"><span data-stu-id="676a0-114">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="676a0-115">Les sociétés peuvent utiliser la fonctionnalité d'échéancier de produit sans utiliser la fonctionnalité de prix du produit.</span><span class="sxs-lookup"><span data-stu-id="676a0-115">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="676a0-116">Par conséquent, le prix sur les lignes de commande client est utilisé comme produit ou comme produit différé.</span><span class="sxs-lookup"><span data-stu-id="676a0-116">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="676a0-117">Si un échéancier de produit existe sur la ligne de commande client, le prix sur la ligne de commande client est différé.</span><span class="sxs-lookup"><span data-stu-id="676a0-117">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="676a0-118">S'il n'existe pas d'échéancier de produit dans la ligne de commande client, le prix est validé dans un compte de produit au moment de la facturation.</span><span class="sxs-lookup"><span data-stu-id="676a0-118">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="676a0-119">Le prix du produit est calculé lors de la confirmation de la commande client ou lors de la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="676a0-119">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="676a0-120">Pour afficher un aperçu du prix du produit avant la validation de la facture, vous devez confirmer la commande client.</span><span class="sxs-lookup"><span data-stu-id="676a0-120">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="676a0-121">Lorsque la commande client est confirmée, un échéancier de produit prévu est également créé si une ligne de commande comporte un échéancier de produit.</span><span class="sxs-lookup"><span data-stu-id="676a0-121">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="676a0-122">Lorsque la commande client est facturée, l'échéancier de produit prévu est supprimé et remplacé par l'échéancier de constatation du produit réel.</span><span class="sxs-lookup"><span data-stu-id="676a0-122">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="676a0-123">Les détails de l'échéancier de constatation du produit sont conservés pour chaque ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="676a0-123">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="676a0-124">Par conséquent, le responsable de constatation du produit peut afficher les détails et peut libérer des lignes du produit une fois l'obligation contractuelle accomplie.</span><span class="sxs-lookup"><span data-stu-id="676a0-124">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="676a0-125">À la fin de chaque période, le responsable de constatation du produit peut créer un journal de produit pour libérer toutes les lignes de l'échéancier qui arrivent à échéance à cette date ou avant une date qu'il a définie.</span><span class="sxs-lookup"><span data-stu-id="676a0-125">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="676a0-126">Ce journal de produit n'est pas validé immédiatement.</span><span class="sxs-lookup"><span data-stu-id="676a0-126">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="676a0-127">Par conséquent, le responsable de constatation du produit peut vérifier que des montants corrects sont bien émis entre le produit différé et le produit réel.</span><span class="sxs-lookup"><span data-stu-id="676a0-127">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="676a0-128">Si une modification contractuelle entraîne l'ajout d'une nouvelle ligne de commande client à la commande client existante ou à une nouvelle commande client, un processus de redistribution peut être exécuté pour corriger le prix du produit dans toutes les lignes des commandes client.</span><span class="sxs-lookup"><span data-stu-id="676a0-128">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>
