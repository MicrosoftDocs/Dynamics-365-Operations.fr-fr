---
title: Confirmation automatique avec l’optimisation de la planification
description: Cette rubrique explique comment utiliser la confirmation automatique avec la fonction d’Optimisation de la planification.
author: ChristianRytt
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 3542e343de29c9fd9d19ed99cab4b4eebacd2899
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813001"
---
# <a name="autofirming-with-planning-optimization"></a><span data-ttu-id="b8cee-103">Confirmation automatique avec l’optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="b8cee-103">Autofirming with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b8cee-104">La confirmation automatique vous permet de confirmer les ordres prévisionnels dans le cadre du processus de planification.</span><span class="sxs-lookup"><span data-stu-id="b8cee-104">Automatic firming lets you firm (that is, release) planned orders as part of the master planning process.</span></span> <span data-ttu-id="b8cee-105">Lorsque des ordres prévisionnels sont confirmés, ils deviennent des commandes fournisseur, ordres de transfert ou ordres de fabrication réels.</span><span class="sxs-lookup"><span data-stu-id="b8cee-105">When planned orders are firmed, they are transformed into actual purchase orders, transfer orders, or production orders.</span></span> <span data-ttu-id="b8cee-106">Lorsque la fonction d’Optimisation de la planification est utilisée, les ordres prévisionnels sont confirmés pendant l’exécution d’une planification lorsque la date de commande (c’est-à-dire, la date de début) est comprise dans la plage de confirmation.</span><span class="sxs-lookup"><span data-stu-id="b8cee-106">When Planning Optimization is used, planned orders are firmed during a master planning run when the order date (that is, the start date) is within the time fence for firming.</span></span>

> [!NOTE]
> <span data-ttu-id="b8cee-107">La confirmation automatique d’une commande fournisseur prévisionnelle n’est possible que si l’article est associé à un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b8cee-107">Auto-firming of a planned purchase order can occur only if the item is associated with a vendor.</span></span>
> 
> <span data-ttu-id="b8cee-108">Les commandes dérivées confirmées (commandes d’achat de sous-traitance) afficheront un statut *En cours de révision* lorsque le suivi des modifications de dossier est activé.</span><span class="sxs-lookup"><span data-stu-id="b8cee-108">Firmed derived orders (subcontract purchase orders) will show a status of *In-review* when case change tracking is enabled.</span></span>

## <a name="turn-on-autofirming"></a><span data-ttu-id="b8cee-109">Activer la confirmation automatique</span><span class="sxs-lookup"><span data-stu-id="b8cee-109">Turn on autofirming</span></span>

<span data-ttu-id="b8cee-110">Pour activer la confirmation automatique, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b8cee-110">To turn on autofirming, follow these steps.</span></span>

1. <span data-ttu-id="b8cee-111">Dans l’espace de travail **Gestion des fonctionnalités**, sous l’onglet **Nouveau**, sélectionnez **Confirmation automatique de l’Optimisation de la planification** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b8cee-111">In the **Feature management** workspace, on the **New** tab, select **Auto-firming for Planning Optimization** in the list.</span></span> <span data-ttu-id="b8cee-112">Si la fonctionnalité ne s’affiche pas sur l’onglet **Nouveau**, examinez les onglets **Non activé** et **Tous**.</span><span class="sxs-lookup"><span data-stu-id="b8cee-112">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="b8cee-113">Sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="b8cee-113">Select **Enable now**.</span></span> <span data-ttu-id="b8cee-114">Sinon, sélectionnez **Programme**, puis sélectionnez l’heure à laquelle vous souhaitez activer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="b8cee-114">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

## <a name="set-up-the-firming-time-fence"></a><span data-ttu-id="b8cee-115">Définissez la plage de gestion de la confirmation.</span><span class="sxs-lookup"><span data-stu-id="b8cee-115">Set up the firming time fence</span></span>

<span data-ttu-id="b8cee-116">La plage de gestion de confirmation est calculée en avant à partir de la date d’exécution de la planification.</span><span class="sxs-lookup"><span data-stu-id="b8cee-116">The firming time fence is calculated forward from the master planning run date.</span></span> <span data-ttu-id="b8cee-117">Elle est définie par le nombre de jours que vous saisissez.</span><span class="sxs-lookup"><span data-stu-id="b8cee-117">It's defined by the number of days that you enter.</span></span> <span data-ttu-id="b8cee-118">Vous pouvez contrôler la plage de gestion de confirmation comme suit :</span><span class="sxs-lookup"><span data-stu-id="b8cee-118">You can control the firming time fence in the following ways:</span></span>

- <span data-ttu-id="b8cee-119">Pour définir la plage de gestion de confirmation par défaut pour un groupe de couverture, accédez à **Planification** \> **Paramétrage** \> **Couverture** \> **Groupes de couverture**, puis sélectionnez un groupe de couverture.</span><span class="sxs-lookup"><span data-stu-id="b8cee-119">To define the default firming time fence for a coverage group, go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**, and select a coverage group.</span></span> <span data-ttu-id="b8cee-120">Puis, dans l’organisateur **Autre**, dans le champ **Plage de gestion de confirmation automatique (jours)**, entrez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="b8cee-120">Then, on the **Other** FastTab, in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="b8cee-121">Pour remplacer la plage de gestion de confirmation définie pour le groupe de couverture pour un article spécifique, accédez à **Gestion des informations sur les produits** \> **Produits lancés**, puis dans le volet Actions, sélectionnez **Plan**, puis sélectionnez **Couverture de l’article**.</span><span class="sxs-lookup"><span data-stu-id="b8cee-121">To overwrite the firming time fence that is defined for the coverage group for a specific item, go to **Product information management** \> **Released products**, then from the Action Pane select **Plan** and then select **Item coverage**.</span></span> <span data-ttu-id="b8cee-122">Puis, dans l’onglet **Général**, sélectionnez **Remplacer les plages de gestion** et dans le champ **Plage de gestion de confirmation automatique (jours)**, entrez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="b8cee-122">Then, on the **General** tab, select **Override time fence** and in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="b8cee-123">Pour remplacer la plage de confirmation définie pour le groupe de couverture et la couverture d’article pour un plan général spécifique, accédez à **Planification** \> **Paramétrage** \> **Plans généraux**, puis sélectionnez un plan général.</span><span class="sxs-lookup"><span data-stu-id="b8cee-123">To overwrite the firming time fence that is defined for the coverage group and item coverage for a specific master plan, go to **Master planning** \> **Setup** \> **Master plans**, and select a Master plan.</span></span> <span data-ttu-id="b8cee-124">Puis, dans l’organisateur **Plage de gestion en jours**, définissez **Confirmer** sur **Oui**, et saisissez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="b8cee-124">Then, on the **Time fence in days** FastTab, set **Firming** to **Yes**, and enter the number of days.</span></span>

<span data-ttu-id="b8cee-125">Si la confirmation automatique est activée pour l’exécution d’une planification avec l’option Optimisation de la planification, le processus de confirmation automatique a lieu selon la configuration de la confirmation automatique.</span><span class="sxs-lookup"><span data-stu-id="b8cee-125">If autofirming is turned on for a master planning run that uses Planning Optimization, the autofirming process is done according to the autofirming setup.</span></span> <span data-ttu-id="b8cee-126">Si la confirmation automatique n’est pas activée, ou si la planification a commencé depuis la page **Besoins nets**, le processus de confirmation automatique est ignoré.</span><span class="sxs-lookup"><span data-stu-id="b8cee-126">If autofirming isn't turned on, or if planning is started from the **Net requirements** page, the autofirming process is skipped.</span></span>

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a><span data-ttu-id="b8cee-127">Optimisation de la planification vs moteur de planification intégré dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="b8cee-127">Planning Optimization vs. the built-in Supply Chain Management planning engine</span></span>

<span data-ttu-id="b8cee-128">L’option Optimisation de planification et le moteur de planification qui est intégré à Microsoft Dynamics 365 Supply Chain Management peuvent être utilisés pour confirmer automatiquement les ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="b8cee-128">Both Planning Optimization and the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management can be used to autofirm planned orders.</span></span> <span data-ttu-id="b8cee-129">Toutefois, il existe des différences importantes.</span><span class="sxs-lookup"><span data-stu-id="b8cee-129">However, there are some important differences.</span></span> <span data-ttu-id="b8cee-130">Par exemple, tandis que l’Optimisation de la planification utilise la date de commande (à savoir la date de début) pour déterminer les ordres prévisionnels à confirmer, le moteur de planification intégré à Supply Chain Management utilise la date de besoin (à savoir la date de fin).</span><span class="sxs-lookup"><span data-stu-id="b8cee-130">For example, whereas Planning Optimization uses the order date (that is, the start date) to determine which planned orders to firm, the built-in Supply Chain Management planning engine uses the requirement date (that is, the end date).</span></span> <span data-ttu-id="b8cee-131">Voici un résumé des différences.</span><span class="sxs-lookup"><span data-stu-id="b8cee-131">Here is a summary of the differences.</span></span>

<span data-ttu-id="b8cee-132">**Service Optimisation de la planification**</span><span class="sxs-lookup"><span data-stu-id="b8cee-132">**Planning Optimization**</span></span>

- <span data-ttu-id="b8cee-133">La confirmation automatique est basée sur la date de commande (date de début).</span><span class="sxs-lookup"><span data-stu-id="b8cee-133">Autofirming is based on the order date (start date).</span></span>
- <span data-ttu-id="b8cee-134">Puisque la date de commande (date de début) déclenche la confirmation, vous n’avez pas à tenir compte du délai d’exécution dans le cadre de la plage de confirmation.</span><span class="sxs-lookup"><span data-stu-id="b8cee-134">Because the order date (start date) triggers the firming, you don't have to consider the lead time as part of the firming time fence.</span></span>
- <span data-ttu-id="b8cee-135">Si vous souhaitez confirmer tous les ordres qui doivent commencer pendant la semaine en cours, la plage de confirmation doit être d’une semaine.</span><span class="sxs-lookup"><span data-stu-id="b8cee-135">If you want to firm all orders that must start during the current week, the firming time fence must be one week.</span></span>

<span data-ttu-id="b8cee-136">**Moteur de planification intégré à Supply Chain Management**</span><span class="sxs-lookup"><span data-stu-id="b8cee-136">**Built-in Supply Chain Management planning engine**</span></span>

- <span data-ttu-id="b8cee-137">La confirmation automatique est basée sur la date de besoin (date de fin).</span><span class="sxs-lookup"><span data-stu-id="b8cee-137">Autofirming is based on the requirement date (end date).</span></span>
- <span data-ttu-id="b8cee-138">Pour assurer que les ordres sont confirmés en temps voulu, la plage de confirmation doit être plus longue que le délai d’exécution.</span><span class="sxs-lookup"><span data-stu-id="b8cee-138">To help guarantee that orders are firmed in due time, the firming time fence must be longer than the lead time.</span></span>
- <span data-ttu-id="b8cee-139">Si vous souhaitez confirmer tous les ordres qui doivent commencer pendant la semaine en cours, la plage de confirmation doit être le délai d’exécution plus une semaine.</span><span class="sxs-lookup"><span data-stu-id="b8cee-139">If you want to firm all orders that must start during the current week, the firming time fence must be the lead time plus one week.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
