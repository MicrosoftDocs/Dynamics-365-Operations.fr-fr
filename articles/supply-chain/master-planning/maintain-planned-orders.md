---
title: Tenir à jour les ordres prévisionnels
description: Cette rubrique fournit des informations sur la gestion des ordres prévisionnels. Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu’un ordre prévisionnel sélectionné.
author: roxanadiaconu
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f16a666cef5625fb159265ddc7237ad0eb45927
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187648"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="1a5dc-104">Tenir à jour les ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="1a5dc-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a5dc-105">Cette rubrique fournit des informations sur la gestion des ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="1a5dc-106">Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu’un ordre prévisionnel sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="1a5dc-107">Vous pouvez gérer les ordres prévisionnels à partir de l’espace de travail **Planification**, de la liste **Ordre prévisionnel** ou des listes **Ordres de fabrication prévisionnels**, **Commandes fournisseur prévisionnelles** et **Transfert prévisionnel**.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="1a5dc-108">Statut de la commande prévisionnelle</span><span class="sxs-lookup"><span data-stu-id="1a5dc-108">Planned order status</span></span>
<span data-ttu-id="1a5dc-109">Vous pouvez utiliser le champ **Statut** pour aider à suivre la progression.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="1a5dc-110">Les valeurs suivantes sont utilisées :</span><span class="sxs-lookup"><span data-stu-id="1a5dc-110">The following values are used:</span></span>

-   <span data-ttu-id="1a5dc-111">Lorsque la planification génère des ordres prévisionnels, leur statut est **Non traité**.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="1a5dc-112">Si vous décidez de ne pas confirmer un ordre prévisionnel, vous pouvez lui attribuer le statut **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="1a5dc-113">Si vous souhaitez confirmer une commande prévisionnelle, vous pouvez définir son statut sur **Approuvée**.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="1a5dc-114">Les commandes prévisionnelles définies sur **Approuvée** suivent la planification principale, de sorte qu’elles ne sont pas modifiées ou supprimées pendant une exécution ultérieure de la planification principale.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted during a later master planning run.</span></span> <span data-ttu-id="1a5dc-115">Pour ce faire, la logique de planification copie les ordres prévisionnels **Approuvés** de l’ancienne version de plan vers la nouvelle version de plan lors de la planification.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-115">To achieve this, the planning logic copies the **Approved** planned orders from the old plan version to the new plan version during master planning.</span></span>

## <a name="firming-planned-orders"></a><span data-ttu-id="1a5dc-116">Confirmation des commandes prévisionnelles</span><span class="sxs-lookup"><span data-stu-id="1a5dc-116">Firming planned orders</span></span> 
<span data-ttu-id="1a5dc-117">La confirmation des commandes prévisionnelles entraîne la création de vraies commandes.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-117">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="1a5dc-118">Elles sont également mentionnées par les appellations *lancées* ou *commandes en cours*.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-118">These are also known as *released* or *open orders*.</span></span> <span data-ttu-id="1a5dc-119">Après confirmation, l’ordre prévisionnel est déplacé vers la section Commandes du module approprié.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-119">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="1a5dc-120">Vous pouvez activer deux options de confirmation de la page **Commandes prévisionnelles** :</span><span class="sxs-lookup"><span data-stu-id="1a5dc-120">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="1a5dc-121">**Confirmer** : cette option permet de confirmer une ou plusieurs commandes prévisionnelles sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-121">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="1a5dc-122">**Confirmer tout** : cette option confirme toutes les commandes planifiées dans le filtre.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-122">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="1a5dc-123">Avec l’option **Confirmer tout**, vous n’avez pas à sélectionner la commande planifiée, toutes les commandes planifiées dans le filtre seront confirmées.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-123">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="1a5dc-124">Cette option peut être utile si vous confirmez un grand nombre de commandes prévisionnelles.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-124">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="1a5dc-125">Vous pouvez suivre une commande prévisionnelle qui a été confirmée depuis **Confirmation de l’historique** sous **Écran des commandes planifiées > Affichage > Confirmation de l’historique**.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-125">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="1a5dc-126">Confirmation de la mise en parallèle</span><span class="sxs-lookup"><span data-stu-id="1a5dc-126">Parallelize firming</span></span>
<span data-ttu-id="1a5dc-127">Si vous prévoyez de confirmer plusieurs commandes à la fois, la mise en parallèle de l’exécution peut améliorer le temps d’exécution ou la performance.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-127">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="1a5dc-128">Cette option est disponible lors de la confirmation de plusieurs commandes prévisionnelles avec l’option **Confirmer** ou **Confirmer tout**.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-128">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="1a5dc-129">Les paramètres disponibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="1a5dc-129">The following parameters are available:</span></span>

-   <span data-ttu-id="1a5dc-130">**Mettre la confirmation en parallèle** : si l’option est définie sur **Oui**, le processus de confirmation est parallélisé avec le nombre de threads définis dans **Nombre de threads**.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-130">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="1a5dc-131">**Nombre de threads** : contrôle le nombre de threads utilisé pour mettre en parallèle le processus de confirmation.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-131">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="1a5dc-132">Le paramètre n’est affiché que lorsque l’option **Mettre la confirmation en parallèle** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-132">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>

> [!NOTE]
> <span data-ttu-id="1a5dc-133">L’option pour la **Confirmation de la mise en parallèle** s’affiche uniquement lorsque vous avez sélectionné plusieurs ordres prévisionnels pour la confirmation.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-133">The option for **Parallelize firming** is only shown when you have more than one planned order selected for firming.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a5dc-134">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1a5dc-134">Additional resources</span></span>

[<span data-ttu-id="1a5dc-135">Vue d’ensemble des plans généraux</span><span class="sxs-lookup"><span data-stu-id="1a5dc-135">Master plans overview</span></span>](master-plans.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]