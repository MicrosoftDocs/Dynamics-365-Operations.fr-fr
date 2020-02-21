---
title: Vue d'ensemble de la constatation du produit
description: Cette rubrique fournit des informations sur la fonctionnalité de constatation du produit. Elle offre un cadre flexible qui vous permet de définir des règles spécifiques pour identifier le prix et l'échéancier de produit pour les commandes comportant plusieurs éléments.
author: kweekley
manager: aolson
ms.date: 11/11/2019
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
ms.openlocfilehash: c5a3a90b0065f8cd076117818df810cf10202d29
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2020
ms.locfileid: "3030966"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="24b27-104">Vue d'ensemble de la constatation du produit</span><span class="sxs-lookup"><span data-stu-id="24b27-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="24b27-105">La fonctionnalité de constatation du produit ne peut pas être activée via la gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="24b27-105">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="24b27-106">Vous devez pour l'instant utiliser les clés de configuration pour l'activer.</span><span class="sxs-lookup"><span data-stu-id="24b27-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="24b27-107">Les sociétés du secteur qui vendent plusieurs éléments, tels que des produits, des services, des abonnements, etc., doivent pouvoir éclater les commandes comportant plusieurs éléments afin que le produit puisse être identifié selon un ensemble d'instructions spécifiques et propres au secteur.</span><span class="sxs-lookup"><span data-stu-id="24b27-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="24b27-108">En général le processus de constatation du produit peut être utilisé pour réaliser les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="24b27-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="24b27-109">Répartir le produit, pour garantir que le prix approprié est bien constaté en fonction de la valeur des composants sur les commandes à plusieurs éléments.</span><span class="sxs-lookup"><span data-stu-id="24b27-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="24b27-110">Différer le produit, selon un échéancier de produit qui représente le calendrier et les pourcentages contractuels pour constater le produit au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="24b27-110">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

<span data-ttu-id="24b27-111">La vidéo [Utilisation de la constatation du produit dans Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (affichée ci-dessus) est incluse dans la liste de lecture [Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.</span><span class="sxs-lookup"><span data-stu-id="24b27-111">The [How to use revenue recognition in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

<span data-ttu-id="24b27-112">La fonctionnalité de constatation du produit offre un cadre flexible qui vous permet de définir des règles spécifiques pour identifier le prix et l'échéancier de produit.</span><span class="sxs-lookup"><span data-stu-id="24b27-112">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="24b27-113">Les produits lancés permettent de prendre en charge la constatation du produit dans les documents de commande client.</span><span class="sxs-lookup"><span data-stu-id="24b27-113">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="24b27-114">Les produits lancés contiennent le paramétrage requis pour déterminer le prix et l'échéancier de produit.</span><span class="sxs-lookup"><span data-stu-id="24b27-114">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="24b27-115">La commande client peut provenir d'un projet en régie.</span><span class="sxs-lookup"><span data-stu-id="24b27-115">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="24b27-116">Les sociétés peuvent utiliser la fonctionnalité d'échéancier de produit sans utiliser la fonctionnalité de prix du produit.</span><span class="sxs-lookup"><span data-stu-id="24b27-116">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="24b27-117">Par conséquent, le prix sur les lignes de commande client est utilisé comme produit ou comme produit différé.</span><span class="sxs-lookup"><span data-stu-id="24b27-117">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="24b27-118">Si un échéancier de produit existe sur la ligne de commande client, le prix sur la ligne de commande client est différé.</span><span class="sxs-lookup"><span data-stu-id="24b27-118">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="24b27-119">S'il n'existe pas d'échéancier de produit dans la ligne de commande client, le prix est validé dans un compte de produit au moment de la facturation.</span><span class="sxs-lookup"><span data-stu-id="24b27-119">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="24b27-120">Le prix du produit est calculé lors de la confirmation de la commande client ou lors de la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="24b27-120">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="24b27-121">Pour afficher un aperçu du prix du produit avant la validation de la facture, vous devez confirmer la commande client.</span><span class="sxs-lookup"><span data-stu-id="24b27-121">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="24b27-122">Lorsque la commande client est confirmée, un échéancier de produit prévu est également créé si une ligne de commande comporte un échéancier de produit.</span><span class="sxs-lookup"><span data-stu-id="24b27-122">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="24b27-123">Lorsque la commande client est facturée, l'échéancier de produit prévu est supprimé et remplacé par l'échéancier de constatation du produit réel.</span><span class="sxs-lookup"><span data-stu-id="24b27-123">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="24b27-124">Les détails de l'échéancier de constatation du produit sont conservés pour chaque ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="24b27-124">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="24b27-125">Par conséquent, le responsable de constatation du produit peut afficher les détails et peut libérer des lignes du produit une fois l'obligation contractuelle accomplie.</span><span class="sxs-lookup"><span data-stu-id="24b27-125">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="24b27-126">À la fin de chaque période, le responsable de constatation du produit peut créer un journal de produit pour libérer toutes les lignes de l'échéancier qui arrivent à échéance à cette date ou avant une date qu'il a définie.</span><span class="sxs-lookup"><span data-stu-id="24b27-126">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="24b27-127">Ce journal de produit n'est pas validé immédiatement.</span><span class="sxs-lookup"><span data-stu-id="24b27-127">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="24b27-128">Par conséquent, le responsable de constatation du produit peut vérifier que des montants corrects sont bien émis entre le produit différé et le produit réel.</span><span class="sxs-lookup"><span data-stu-id="24b27-128">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="24b27-129">Si une modification contractuelle entraîne l'ajout d'une nouvelle ligne de commande client à la commande client existante ou à une nouvelle commande client, un processus de redistribution peut être exécuté pour corriger le prix du produit dans toutes les lignes des commandes client.</span><span class="sxs-lookup"><span data-stu-id="24b27-129">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>
