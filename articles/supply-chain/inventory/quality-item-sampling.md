---
title: Échantillonnage des éléments de gestion de la qualité
description: Cette rubrique décrit comment configurer l’échantillonnage d’article.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 495bef32d63738e367167ee69f2028bc77945cc4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956647"
---
# <a name="quality-management-item-sampling"></a><span data-ttu-id="f8925-103">Échantillonnage des éléments de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="f8925-103">Quality management item sampling</span></span>

<span data-ttu-id="f8925-104">L'échantillonnage d’article est utilisé dans le cadre d'une association de qualité.</span><span class="sxs-lookup"><span data-stu-id="f8925-104">Item sampling is used as part of a quality association.</span></span> <span data-ttu-id="f8925-105">Il définit le montant de l'inventaire physique actuel qui doit être inspecté.</span><span class="sxs-lookup"><span data-stu-id="f8925-105">It defines the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="f8925-106">L’échantillonnage peut être basé sur des quantités fixes, un pourcentage ou un contenant complet.</span><span class="sxs-lookup"><span data-stu-id="f8925-106">Sampling can be based on fixed quantities, a percentage, or a full license plate.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="f8925-107">Paramétrer l’échantillonnage d’article</span><span class="sxs-lookup"><span data-stu-id="f8925-107">Set up item sampling</span></span>

<span data-ttu-id="f8925-108">Procédez comme suit pour configurer l’échantillonnage d’article :</span><span class="sxs-lookup"><span data-stu-id="f8925-108">Follow these steps to set up item sampling.</span></span>

1. <span data-ttu-id="f8925-109">Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Échantillonnage d’article**.</span><span class="sxs-lookup"><span data-stu-id="f8925-109">Go to **Inventory management \> Setup \> Quality control \> Item sampling**.</span></span>
1. <span data-ttu-id="f8925-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f8925-110">Select **New**.</span></span>
1. <span data-ttu-id="f8925-111">Entrez une valeur dans le champ **Échantillonnage d’article**.</span><span class="sxs-lookup"><span data-stu-id="f8925-111">In the **Item sampling** field, enter a value.</span></span>
1. <span data-ttu-id="f8925-112">Dans le champ **Description**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f8925-112">In the **Description** field, enter a value.</span></span>
1. <span data-ttu-id="f8925-113">Entrez un nombre dans le champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="f8925-113">In the **Value** field, enter a number.</span></span> <span data-ttu-id="f8925-114">Cette valeur fait référence à la valeur de spécification de quantité sélectionnée dans le champ adjacent.</span><span class="sxs-lookup"><span data-stu-id="f8925-114">This value is related to the quantity specification value that is selected in the adjacent field.</span></span>
1. <span data-ttu-id="f8925-115">Dans la section **Processus**, cochez la case **Blocage total** si la quantité totale du lot ou de la ligne de commande doit être bloquée en cas d'échec d'un test.</span><span class="sxs-lookup"><span data-stu-id="f8925-115">In the **Process** section, select the **Full blocking** check box if the whole lot or order line quantity should be blocked if a test is failed.</span></span> <span data-ttu-id="f8925-116">Si cette case à cocher est désactivée, seuls les éléments de l'ordre de qualité seront bloqués en cas d'échec d'un test.</span><span class="sxs-lookup"><span data-stu-id="f8925-116">If this check box is cleared, only the items in the quality order will be blocked if a test is failed.</span></span>
1. <span data-ttu-id="f8925-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f8925-117">Select **Save**.</span></span>
1. <span data-ttu-id="f8925-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f8925-118">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="f8925-119">La fonctionnalité *Gestion de la qualité pour les processus d’entrepôt* fournit des capacités d’échantillonnage d’articles supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f8925-119">The *Quality management for warehouse processes* feature provides additional item sampling capabilities.</span></span> <span data-ttu-id="f8925-120">Elle ajoute le concept de *portée d’échantillonnage de l’article* et permet de définir un contenant complet comme spécification de quantité.</span><span class="sxs-lookup"><span data-stu-id="f8925-120">It adds the concept of *item sampling scope* and lets you define a full license plate as the quantity specification.</span></span> <span data-ttu-id="f8925-121">Si vous avez activé cette fonctionnalité, consultez [Gestion de la qualité pour les processus d’entrepôt](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="f8925-121">If you've turned on this feature, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
