---
title: Marquage du stock avec optimisation de la planification
description: Cette rubrique fournit des informations sur les options disponibles pour marquer le stock dans les commandes confirmées lorsque vous utilisez l’optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 236e1955dd80564e748aab1c595b017cb78e9418
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983489"
---
# <a name="inventory-marking-with-planning-optimization"></a><span data-ttu-id="5dab8-103">Marquage du stock avec optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="5dab8-103">Inventory marking with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5dab8-104">Cette rubrique fournit des informations sur les options disponibles pour marquer le stock dans les commandes confirmées lorsque vous utilisez l’optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="5dab8-104">This topic provides information about the options that are available for marking inventory in firmed orders when you use Planning Optimization.</span></span>

<span data-ttu-id="5dab8-105">Le *Marquage* est utilisé pour relier l'offre et la demande.</span><span class="sxs-lookup"><span data-stu-id="5dab8-105">*Marking* is used to link supply and demand.</span></span> <span data-ttu-id="5dab8-106">Il ressemble à l'*origine des besoins*, qui indique comment la planification prévoit de couvrir la demande.</span><span class="sxs-lookup"><span data-stu-id="5dab8-106">It resembles *pegging*, which indicates how master planning expects to cover demand.</span></span> <span data-ttu-id="5dab8-107">Du point de vue de la planification, la principale différence est que le marquage est plus permanent que l'origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="5dab8-107">From a planning point of view, the main difference is that marking is more permanent than pegging.</span></span>

<span data-ttu-id="5dab8-108">Le marquage a été introduit pour prendre en charge des scénarios de coûts spéciaux pour le premier entré, premier sorti (FIFO) et le dernier entré, premier sorti (LIFO).</span><span class="sxs-lookup"><span data-stu-id="5dab8-108">Marking was introduced to support special costing scenarios for first in, first out (FIFO) and last in, first out (LIFO).</span></span> <span data-ttu-id="5dab8-109">Cependant, il est maintenant également utilisé pour certains scénarios sans coût.</span><span class="sxs-lookup"><span data-stu-id="5dab8-109">However, it's now also used for some non-costing scenarios.</span></span> <span data-ttu-id="5dab8-110">Le marquage entre l'offre et la demande est facultatif et presque permanent.</span><span class="sxs-lookup"><span data-stu-id="5dab8-110">Marking between supply and demand is optional and almost permanent.</span></span> <span data-ttu-id="5dab8-111">Le marquage peut être supprimé manuellement par un utilisateur, ou il peut être supprimé en exécutant une explosion de ligne de commande client où l'option **Supprimer le marquage** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5dab8-111">Marking can be removed manually by a user, or it can be removed by running a sales order line explosion where the **Remove marking** option is selected.</span></span>

<span data-ttu-id="5dab8-112">L'origine des besoins est contrôlé par la planification pendant la couverture pour lier la demande à l'offre requise.</span><span class="sxs-lookup"><span data-stu-id="5dab8-112">Pegging is controlled by master planning during coverage to link demand with the required supply.</span></span> <span data-ttu-id="5dab8-113">L'origine des besoins peut être mis à jour pour chaque cycle de planification afin d'optimiser l'approvisionnement nécessaire pour couvrir la demande.</span><span class="sxs-lookup"><span data-stu-id="5dab8-113">Pegging can be updated for each planning run to optimize the supply that is required to cover demand.</span></span> <span data-ttu-id="5dab8-114">Lorsque la planification met à jour les informations d'origine des besoins, elle respecte tout marquage existant.</span><span class="sxs-lookup"><span data-stu-id="5dab8-114">When master planning updates pegging information, it respects any existing marking.</span></span>

<span data-ttu-id="5dab8-115">L'origine des besoins commence par inclure le marquage pertinent, les réservations disponibles et les réservations sur commande, dans l'ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="5dab8-115">Pegging starts by including relevant marking, on-hand reservations, and on-order reservations, in the following sequence:</span></span>

1. <span data-ttu-id="5dab8-116">Marquage entre demande et offre</span><span class="sxs-lookup"><span data-stu-id="5dab8-116">Marking between demand and supply</span></span>
1. <span data-ttu-id="5dab8-117">Réservations disponibles</span><span class="sxs-lookup"><span data-stu-id="5dab8-117">On-hand reservations</span></span>
1. <span data-ttu-id="5dab8-118">Réservation sur commande</span><span class="sxs-lookup"><span data-stu-id="5dab8-118">On-order reservations</span></span>

<span data-ttu-id="5dab8-119">Lorsque vous confirmez une commande planifiée, la boîte de dialogue **Confirmation** fournit un champ **Mettre à jour le marquage** que vous utilisez pour définir les options de marquage des commandes créées lors de la confirmation.</span><span class="sxs-lookup"><span data-stu-id="5dab8-119">When you firm a planned order, the **Firming** dialog box provides an **Update marking** field that you use to set marking options for the orders that are created during firming.</span></span> <span data-ttu-id="5dab8-120">Vous devez sélectionner l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="5dab8-120">Select one of the following values:</span></span>

- <span data-ttu-id="5dab8-121">**Non** – Aucun marquage de stock n'est appliqué.</span><span class="sxs-lookup"><span data-stu-id="5dab8-121">**No** – No inventory marking is applied.</span></span>
- <span data-ttu-id="5dab8-122">**Standard** – Le marquage du stock est mis à jour en fonction de l'origine des demandes.</span><span class="sxs-lookup"><span data-stu-id="5dab8-122">**Standard** – Inventory marking is updated according to the pegging.</span></span> <span data-ttu-id="5dab8-123">Un ordre de besoins (demande) est marqué par rapport à un ordre d'exécution de commande (offre).</span><span class="sxs-lookup"><span data-stu-id="5dab8-123">A requirement order (demand) is marked against a fulfillment order (supply).</span></span> <span data-ttu-id="5dab8-124">S'il reste une quantité sur l'ordre d'exécution, elle n'est pas marquée et les informations de référence sont laissées vides.</span><span class="sxs-lookup"><span data-stu-id="5dab8-124">If some quantity remains on the fulfillment order, it isn't marked, and the reference information is left blank.</span></span> <span data-ttu-id="5dab8-125">Par exemple, si une commande client de 100 unités est liée à une commande d'achat de 150 unités, les informations de référence ne seront affectées qu'à la commande client.</span><span class="sxs-lookup"><span data-stu-id="5dab8-125">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned only to the sales order.</span></span>
- <span data-ttu-id="5dab8-126">**Développé** - L'ordre de besoins (demande) et l'ordre d'exécution de commande (offre) sont marqués, indépendamment de la quantité restant dans l'ordre d'exécution de commande.</span><span class="sxs-lookup"><span data-stu-id="5dab8-126">**Extended** – Both the requirement order (demand) and the fulfillment order (supply) are marked, regardless of any quantity that remains on the fulfillment order.</span></span> <span data-ttu-id="5dab8-127">Par exemple, si une commande client de 100 unités est liée à une commande d'achat de 150 unités, les informations de référence ne seront affectées qu'à la commande client et à la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5dab8-127">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned to both the sales order and the purchase order.</span></span>
