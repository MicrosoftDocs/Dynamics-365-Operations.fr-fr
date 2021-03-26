---
title: Vue d’ensemble de la fonctionnalité de prise en compte de revenu
description: Cette rubrique fournit des informations sur la fonctionnalité de prise en compte de revenu. Elle offre un cadre flexible qui vous permet de définir des règles spécifiques pour identifier le prix et l’échéancier de produit pour les commandes comportant plusieurs éléments.
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
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: b21cf04674d01df31dc3304886e7cda035bdcce2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238254"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="35919-104">Vue d’ensemble de la fonctionnalité de prise en compte de revenu</span><span class="sxs-lookup"><span data-stu-id="35919-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35919-105">Les sociétés qui ont de multiples prestations (comme des produits, des services, des abonnements, etc.), doivent pouvoir éclater les commandes comportant plusieurs éléments afin que le produit puisse être identifié selon un ensemble d’instructions spécifiques et propres au secteur.</span><span class="sxs-lookup"><span data-stu-id="35919-105">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

> [!NOTE]
> <span data-ttu-id="35919-106">La fonctionnalité de prise en compte de revenu ne peut pas être activée via la gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="35919-106">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="35919-107">Vous devez pour l’instant utiliser les clés de configuration pour l’activer.</span><span class="sxs-lookup"><span data-stu-id="35919-107">Currently, you must use configuration keys to turn it on.</span></span>

> <span data-ttu-id="35919-108">La fonctionnalité de prise en compte de revenu (y compris la fonctionnalité groupée), n’est pas prise en charge pour une utilisation dans les canaux commerciaux (commerce électronique, PDV, centre d’appels).</span><span class="sxs-lookup"><span data-stu-id="35919-108">Revenue recognition, including bundle functionality, isn't supported for use in Commerce channels (e-commerce, POS, call center).</span></span> <span data-ttu-id="35919-109">Les articles configurés avec la fonctionnalité de prise en compte de revenu ne doivent pas être ajoutés aux commandes ou aux transactions créées dans les canaux commerciaux.</span><span class="sxs-lookup"><span data-stu-id="35919-109">Items configured with revenue recognition should not be added to orders or transactions created in Commerce channels.</span></span>

<span data-ttu-id="35919-110">En général le processus de prise en compte de revenu peut être utilisé pour réaliser les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="35919-110">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="35919-111">Répartir le produit, pour aider à garantir que le prix approprié est bien constaté en fonction de la valeur des composants sur les commandes à plusieurs éléments.</span><span class="sxs-lookup"><span data-stu-id="35919-111">Allocate revenue, to help ensure that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="35919-112">Différer le produit, selon un échéancier de produit qui représente le calendrier et les pourcentages contractuels pour constater le produit au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="35919-112">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

<span data-ttu-id="35919-113">La vidéo [Utilisation de la prise en compte de revenu dans Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (affichée ci-dessus) est incluse dans la liste de lecture [Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.</span><span class="sxs-lookup"><span data-stu-id="35919-113">The [How to use revenue recognition in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

<span data-ttu-id="35919-114">La fonctionnalité de prise en compte de revenu offre un cadre flexible qui vous permet de définir des règles spécifiques pour identifier le prix et l’échéancier de produit.</span><span class="sxs-lookup"><span data-stu-id="35919-114">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="35919-115">Les produits lancés permettent de prendre en charge la prise en compte de revenu dans les documents de commande client.</span><span class="sxs-lookup"><span data-stu-id="35919-115">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="35919-116">Les produits lancés contiennent le paramétrage requis pour déterminer le prix et l’échéancier de produit.</span><span class="sxs-lookup"><span data-stu-id="35919-116">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="35919-117">La commande client peut provenir d’un projet en régie.</span><span class="sxs-lookup"><span data-stu-id="35919-117">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="35919-118">Les sociétés peuvent utiliser la fonctionnalité d’échéancier de produit sans utiliser la fonctionnalité de prix du produit.</span><span class="sxs-lookup"><span data-stu-id="35919-118">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="35919-119">Par conséquent, le prix sur les lignes de commande client est utilisé comme produit ou comme produit différé.</span><span class="sxs-lookup"><span data-stu-id="35919-119">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="35919-120">Si un échéancier de produit existe sur la ligne de commande client, le prix sur la ligne de commande client est différé.</span><span class="sxs-lookup"><span data-stu-id="35919-120">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="35919-121">S’il n’existe pas d’échéancier de produit dans la ligne de commande client, le prix est validé dans un compte de produit au moment de la facturation.</span><span class="sxs-lookup"><span data-stu-id="35919-121">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="35919-122">Le prix du produit est calculé lors de la confirmation de la commande client ou lors de la validation de la facture.</span><span class="sxs-lookup"><span data-stu-id="35919-122">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="35919-123">Pour afficher un aperçu du prix du produit avant la validation de la facture, vous devez confirmer la commande client.</span><span class="sxs-lookup"><span data-stu-id="35919-123">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="35919-124">Lorsque la commande client est confirmée, un échéancier de produit prévu est également créé si une ligne de commande comporte un échéancier de produit.</span><span class="sxs-lookup"><span data-stu-id="35919-124">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="35919-125">Lorsque la commande client est facturée, l’échéancier de produit prévu est supprimé et remplacé par l’échéancier de prise en compte de revenu réels.</span><span class="sxs-lookup"><span data-stu-id="35919-125">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="35919-126">Les détails de l’échéancier de prise en compte de revenu sont conservés pour chaque ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="35919-126">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="35919-127">Par conséquent, le responsable de prise en compte de revenu peut afficher les détails et peut libérer des lignes du produit une fois l’obligation contractuelle accomplie.</span><span class="sxs-lookup"><span data-stu-id="35919-127">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="35919-128">À la fin de chaque période, le responsable de prise en compte de revenu peut créer un journal de produit pour débloquer toutes les lignes de l’échéancier qui arrivent à échéance à cette date ou avant une date qu’il a définie.</span><span class="sxs-lookup"><span data-stu-id="35919-128">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date they define.</span></span> <span data-ttu-id="35919-129">Ce journal de produit n’est pas validé immédiatement.</span><span class="sxs-lookup"><span data-stu-id="35919-129">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="35919-130">Par conséquent, le responsable de prise en compte de revenu peut vérifier que des montants corrects sont bien émis entre le produit différé et le produit réel.</span><span class="sxs-lookup"><span data-stu-id="35919-130">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="35919-131">Si une modification contractuelle entraîne l’ajout d’une nouvelle ligne de commande client à la commande client existante ou à une nouvelle commande client, un processus de redistribution peut être exécuté pour corriger le prix du produit dans toutes les lignes des commandes client.</span><span class="sxs-lookup"><span data-stu-id="35919-131">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]