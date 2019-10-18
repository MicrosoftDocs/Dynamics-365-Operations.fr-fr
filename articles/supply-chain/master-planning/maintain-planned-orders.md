---
title: Tenir à jour les ordres prévisionnels
description: Cette rubrique fournit des informations sur la gestion des ordres prévisionnels. Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu'un ordre prévisionnel sélectionné.
author: roxanadiaconu
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ddf2c7b4c67bec6c29387c78d1fdb021d85d702
ms.sourcegitcommit: 620e15555d176eec3905b48d5001af1c50107ce6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2019
ms.locfileid: "1993438"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="21962-104">Tenir à jour les ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="21962-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21962-105">Cette rubrique fournit des informations sur la gestion des ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="21962-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="21962-106">Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu'un ordre prévisionnel sélectionné.</span><span class="sxs-lookup"><span data-stu-id="21962-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="21962-107">Vous pouvez gérer les ordres prévisionnels à partir de l'espace de travail **Planification**, de la liste **Ordre prévisionnel** ou des listes **Ordres de fabrication prévisionnels**, **Commandes fournisseur prévisionnelles** et **Transfert prévisionnel**.</span><span class="sxs-lookup"><span data-stu-id="21962-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="21962-108">Statut de la commande prévisionnelle</span><span class="sxs-lookup"><span data-stu-id="21962-108">Planned order status</span></span>
<span data-ttu-id="21962-109">Vous pouvez utiliser le champ **Statut** pour aider à suivre la progression.</span><span class="sxs-lookup"><span data-stu-id="21962-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="21962-110">Les valeurs suivantes sont utilisées :</span><span class="sxs-lookup"><span data-stu-id="21962-110">The following values are used:</span></span>

-   <span data-ttu-id="21962-111">Lorsque la planification génère des ordres prévisionnels, leur statut est **Non traité**.</span><span class="sxs-lookup"><span data-stu-id="21962-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="21962-112">Si vous décidez de ne pas confirmer un ordre prévisionnel, vous pouvez lui attribuer le statut **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="21962-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="21962-113">Si vous souhaitez confirmer une commande prévisionnelle, vous pouvez définir son statut sur **Approuvée**.</span><span class="sxs-lookup"><span data-stu-id="21962-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="21962-114">Les commandes prévisionnelles définies sur **Approuvée** suivent la planification principale, de sorte qu'elles ne sont pas modifiées ou supprimées.</span><span class="sxs-lookup"><span data-stu-id="21962-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted.</span></span> 

## <a name="firming-planned-orders"></a><span data-ttu-id="21962-115">Confirmation des commandes prévisionnelles</span><span class="sxs-lookup"><span data-stu-id="21962-115">Firming planned orders</span></span> 
<span data-ttu-id="21962-116">La confirmation des commandes prévisionnelles entraîne la création de vraies commandes.</span><span class="sxs-lookup"><span data-stu-id="21962-116">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="21962-117">Elles sont également mentionnées par les appellations *lancées* ou *commandes en cours*.</span><span class="sxs-lookup"><span data-stu-id="21962-117">These are also know as *released* or *open orders*.</span></span> <span data-ttu-id="21962-118">Après confirmation, l'ordre prévisionnel est déplacé vers la section Commandes du module approprié.</span><span class="sxs-lookup"><span data-stu-id="21962-118">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="21962-119">Vous pouvez activer deux options de confirmation de la page **Commandes prévisionnelles** :</span><span class="sxs-lookup"><span data-stu-id="21962-119">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="21962-120">**Confirmer** : cette option permet de confirmer une ou plusieurs commandes prévisionnelles sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="21962-120">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="21962-121">**Confirmer tout** : cette option confirme toutes les commandes planifiées dans le filtre.</span><span class="sxs-lookup"><span data-stu-id="21962-121">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="21962-122">Avec l'option **Confirmer tout**, vous n'avez pas à sélectionner la commande planifiée, toutes les commandes planifiées dans le filtre seront confirmées.</span><span class="sxs-lookup"><span data-stu-id="21962-122">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="21962-123">Cette option peut être utile si vous confirmez un grand nombre de commandes prévisionnelles.</span><span class="sxs-lookup"><span data-stu-id="21962-123">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="21962-124">Vous pouvez suivre une commande prévisionnelle qui a été confirmée depuis **Confirmation de l'historique** sous **Écran des commandes planifiées > Affichage > Confirmation de l'historique**.</span><span class="sxs-lookup"><span data-stu-id="21962-124">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="21962-125">Confirmation de la mise en parallèle</span><span class="sxs-lookup"><span data-stu-id="21962-125">Parallelize firming</span></span>
<span data-ttu-id="21962-126">Si vous prévoyez de confirmer plusieurs commandes à la fois, la mise en parallèle de l'exécution peut améliorer le temps d'exécution ou la performance.</span><span class="sxs-lookup"><span data-stu-id="21962-126">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="21962-127">Cette option est disponible lors de la confirmation de plusieurs commandes prévisionnelles avec l'option **Confirmer** ou **Confirmer tout**.</span><span class="sxs-lookup"><span data-stu-id="21962-127">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="21962-128">Les paramètres disponibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="21962-128">The following parameters are available:</span></span>

-   <span data-ttu-id="21962-129">**Mettre la confirmation en parallèle** : si l'option est définie sur **Oui**, le processus de confirmation est parallélisé avec le nombre de threads définis dans **Nombre de threads**.</span><span class="sxs-lookup"><span data-stu-id="21962-129">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="21962-130">**Nombre de threads** : contrôle le nombre de threads utilisé pour mettre en parallèle le processus de confirmation.</span><span class="sxs-lookup"><span data-stu-id="21962-130">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="21962-131">Le paramètre n'est affiché que lorsque l'option **Mettre la confirmation en parallèle** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="21962-131">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>


<a name="additional-resources"></a><span data-ttu-id="21962-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="21962-132">Additional resources</span></span>
--------

[<span data-ttu-id="21962-133">Plans généraux</span><span class="sxs-lookup"><span data-stu-id="21962-133">Master plans</span></span>](master-plans.md)



