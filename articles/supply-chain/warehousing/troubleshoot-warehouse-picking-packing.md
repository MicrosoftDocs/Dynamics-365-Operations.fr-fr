---
title: Corriger les problèmes liés aux prélèvements et au conditionnement
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du prélèvement et du conditionnement dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 74854fa95837dd8a133860e2a017be4c92ff84a3
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645475"
---
# <a name="troubleshoot-picking-and-packing"></a><span data-ttu-id="97d53-103">Corriger les problèmes liés aux prélèvements et au conditionnement</span><span class="sxs-lookup"><span data-stu-id="97d53-103">Troubleshoot picking and packing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97d53-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du prélèvement et du conditionnement dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="97d53-104">This topic describes how to fix common issues that you might encounter while you pick and pack in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a><span data-ttu-id="97d53-105">Je reçois le message d'erreur suivant : "L'emplacement de dimension ne peut pas être laissé vide si le numéro de série de dimension est défini".</span><span class="sxs-lookup"><span data-stu-id="97d53-105">I receive the following error message: "Dimension location can't be left blank if dimension serial number is set."</span></span>

### <a name="issue-description"></a><span data-ttu-id="97d53-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-106">Issue description</span></span>

<span data-ttu-id="97d53-107">Vous recevez ce message d'erreur si vous créez un ordre de transfert pour un article de série à l'aide d'un entrepôt activé pour la gestion avancée des entrepôts (WMS), puis, une fois le travail terminé, vous essayez de confirmer l'expédition.</span><span class="sxs-lookup"><span data-stu-id="97d53-107">You receive this error message if you create a transfer order for a serial item by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="97d53-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-108">Issue resolution</span></span>

<span data-ttu-id="97d53-109">Le champ **Emplacement de réception par défaut** est vide pour un entrepôt de transit de l'entrepôt "Expéditeur".</span><span class="sxs-lookup"><span data-stu-id="97d53-109">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="97d53-110">Pour résoudre ce problème, spécifiez un emplacement de réception par défaut dans l'entrepôt de transit.</span><span class="sxs-lookup"><span data-stu-id="97d53-110">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="97d53-111">Assurez-vous que cet emplacement est contrôlé par conteneur.</span><span class="sxs-lookup"><span data-stu-id="97d53-111">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a><span data-ttu-id="97d53-112">Je reçois le message d'erreur suivant : "Contenant non valide".</span><span class="sxs-lookup"><span data-stu-id="97d53-112">I receive the following error message: "Invalid license plate."</span></span>

### <a name="issue-description"></a><span data-ttu-id="97d53-113">Description du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-113">Issue description</span></span>

<span data-ttu-id="97d53-114">Vous recevez ce message d'erreur dans l'application d'entrepôt lorsque vous numérisez un ID de contenant.</span><span class="sxs-lookup"><span data-stu-id="97d53-114">You receive this error message in the warehouse app when you scan a license plate ID.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="97d53-115">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-115">Issue resolution</span></span>

<span data-ttu-id="97d53-116">Assurez-vous que l'ID de contenant existe dans le tableau des contenants, et que les articles et les quantités sur le contenant sont disponibles (en d'autres termes, ils ne sont pas bloqués).</span><span class="sxs-lookup"><span data-stu-id="97d53-116">Make sure that the license plate ID exists in the license plates table, and that the items and quantities on the license plate are available (in other words, they aren't blocked).</span></span>

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a><span data-ttu-id="97d53-117">Je reçois le message d'erreur suivant : "Le champ 'Poids de charge' (=-%1) ne peut contenir que des nombres positifs.</span><span class="sxs-lookup"><span data-stu-id="97d53-117">I receive the following error message: "Field 'Load weight'(=-%1) can only contain positive numbers.</span></span> <span data-ttu-id="97d53-118">La mise à jour a été annulée."</span><span class="sxs-lookup"><span data-stu-id="97d53-118">Update has been canceled."</span></span>

### <a name="issue-description"></a><span data-ttu-id="97d53-119">Description du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-119">Issue description</span></span>

<span data-ttu-id="97d53-120">Vous recevez ce message d'erreur s'il y a du travail en cours lorsque vous traitez le travail des emplacements d'emballage aux emplacements de préparation, ou des emplacements de préparation aux emplacements de quai.</span><span class="sxs-lookup"><span data-stu-id="97d53-120">You receive this error message if there is open work when you process work from packing locations to staging locations, or from staging locations to dock locations.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="97d53-121">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-121">Issue resolution</span></span>

<span data-ttu-id="97d53-122">Pour résoudre ce problème, accédez à **Administration système \> Tâches périodiques \> Base de données \> Contrôle de cohérence** et exécutez le processus pour **Vérification de la cohérence du poids de la charge de l'entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="97d53-122">To fix this issue, go to **System administration \> Periodic tasks \> Database \> Consistency check**, and run the process for **Warehouse load weight consistency check**.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="97d53-123">Je reçois le message d'erreur suivant : "La quantité n'est pas valide pour l'unité %1."</span><span class="sxs-lookup"><span data-stu-id="97d53-123">I receive the following error message: "The quantity is not valid for unit %1."</span></span>

### <a name="issue-description"></a><span data-ttu-id="97d53-124">Description du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-124">Issue description</span></span>

<span data-ttu-id="97d53-125">Vous recevez ce message d'erreur lorsque vous essayez d'effectuer un *prélèvement partagé* sur plusieurs lots.</span><span class="sxs-lookup"><span data-stu-id="97d53-125">You receive this error message when you try to perform a *split pick* across multiple batches.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="97d53-126">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-126">Issue resolution</span></span>

<span data-ttu-id="97d53-127">Le magasinier doit utiliser le processus *Prélèvement court* dans l'application d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="97d53-127">The warehouse worker must use the *Short picking* process in the warehouse app.</span></span> <span data-ttu-id="97d53-128">Si vous essayez de sélectionner plusieurs lots au même endroit, vous pouvez également utiliser l'option **Complet** dans l'application d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="97d53-128">If you're trying to pick multiple batches from the same location, you can also use the **Full** option in the warehouse app.</span></span>

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a><span data-ttu-id="97d53-129">Je ne peux pas déplacer le stock vers un emplacement contrôlé par le contenant.</span><span class="sxs-lookup"><span data-stu-id="97d53-129">I can't move inventory to a location that is license plate–controlled.</span></span>

### <a name="issue-description"></a><span data-ttu-id="97d53-130">Description du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-130">Issue description</span></span>

<span data-ttu-id="97d53-131">Vous ne pouvez pas réduire les quantités prélevées sur un chargement.</span><span class="sxs-lookup"><span data-stu-id="97d53-131">You can't reduce picked quantities on a load.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="97d53-132">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-132">Issue resolution</span></span>

<span data-ttu-id="97d53-133">Dans les versions précédentes, vous ne pouvez pas réduire les quantités prélevées sur un chargement.</span><span class="sxs-lookup"><span data-stu-id="97d53-133">In earlier versions, you can't reduce picked quantities on a load.</span></span> <span data-ttu-id="97d53-134">Cependant, vous pouvez désormais annuler le prélèvement à un emplacement contrôlé par le contenant.</span><span class="sxs-lookup"><span data-stu-id="97d53-134">However, you can now unpick to a license plate–controlled location.</span></span> <span data-ttu-id="97d53-135">Vous devez spécifier à la fois une valeur **Emplacement** et une valeur **Contenant** de la ligne de charge sur la page **Réduire la quantité prélevée**.</span><span class="sxs-lookup"><span data-stu-id="97d53-135">You must specify both a **Location** value and a **License plate** value for the load line on the **Reduce picked quantity** page.</span></span>

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a><span data-ttu-id="97d53-136">Puis-je imprimer une note de livraison ou un contenu d'emballage par entrepôt ?</span><span class="sxs-lookup"><span data-stu-id="97d53-136">Can I print a delivery note or packing content by warehouse?</span></span>

### <a name="issue-description"></a><span data-ttu-id="97d53-137">Description du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-137">Issue description</span></span>

<span data-ttu-id="97d53-138">Vous souhaitez imprimer une note de livraison ou un contenu d'emballage par entrepôt ou site sur la page **Mise à jour de la ligne de modèle d'audit de travail**.</span><span class="sxs-lookup"><span data-stu-id="97d53-138">You want to print a delivery note or packing content by warehouse or site on the **Work audit template line update** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="97d53-139">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-139">Issue resolution</span></span>

<span data-ttu-id="97d53-140">Lorsque vous imprimez un document à l'aide des paramètres de gestion de l'impression, limitez la portée (site/entrepôt) via la gestion de l'impression au lieu de sélectionner **Modifier les paramètres d'impression** sur la page **Mise à jour de la ligne de modèle d'audit de travail**.</span><span class="sxs-lookup"><span data-stu-id="97d53-140">When you print a document by using Print management settings, limit the scope (site/warehouse) through Print management instead of by selecting **Edit print settings** on the **Work audit template line update** page.</span></span>

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a><span data-ttu-id="97d53-141">Je ne peux pas annuler un bon de livraison après l'avoir publié à partir d'une commande client.</span><span class="sxs-lookup"><span data-stu-id="97d53-141">I can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="97d53-142">Description du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-142">Issue description</span></span>

<span data-ttu-id="97d53-143">Lorsque les processus de prélèvement et d'expédition sont activés pour WMS, vous ne pouvez pas annuler un bon de livraison après l'avoir validé à partir d'une commande client.</span><span class="sxs-lookup"><span data-stu-id="97d53-143">When picking and shipping processes are enabled for WMS, you can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="97d53-144">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-144">Issue resolution</span></span>

<span data-ttu-id="97d53-145">Pour corriger les bons de livraison validés pour les articles qui sont activés pour WMS, l'enregistrement doit se faire à partir du chargement et non de la commande.</span><span class="sxs-lookup"><span data-stu-id="97d53-145">To correct posted packing slips for items that are enabled for WMS, the posting must occur from the load, not from the order.</span></span> <span data-ttu-id="97d53-146">Microsoft a évalué ce problème et a déterminé qu'il s'agissait d'une limitation de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="97d53-146">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="97d53-147">En général, une commande client qui a été prélevée et expédiée via des processus de gestion d'entrepôt peut être mise à jour selon le bon de livraison à partir du chargement ou de l'expédition et du document de commande client lui-même.</span><span class="sxs-lookup"><span data-stu-id="97d53-147">In general, a sales order that has been picked and shipped through warehouse management processes can be packing slip–updated from the load or shipment and the sales order document itself.</span></span> <span data-ttu-id="97d53-148">Cependant, si vous mettez à jour la commande client selon le bon de livraison à partir du document de commande client, l'annulation du bon de livraison ne peut toujours pas être effectuée à partir du chargement ou de la commande client.</span><span class="sxs-lookup"><span data-stu-id="97d53-148">However, if you packing slip–update the sales order from the sales order document, packing slip reversal still can't be done from the load or sales order.</span></span> <span data-ttu-id="97d53-149">Par conséquent, nous vous recommandons d'utiliser l'enregistrement du bon de livraison à partir du chargement.</span><span class="sxs-lookup"><span data-stu-id="97d53-149">Therefore, we recommend that you use the packing slip posting from the load.</span></span> <span data-ttu-id="97d53-150">Dans ce cas, l'inversion qui doit être effectuée à partir de la charge sera activée.</span><span class="sxs-lookup"><span data-stu-id="97d53-150">In this case, the reversal that must be done from the load will be enabled.</span></span>

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a><span data-ttu-id="97d53-151">Je reçois le message d'erreur suivant : « Le groupement contient un nombre insuffisant de tâches. »</span><span class="sxs-lookup"><span data-stu-id="97d53-151">I receive the following error message: "Not enough work can be found for cluster."</span></span>

### <a name="issue-description"></a><span data-ttu-id="97d53-152">Description du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-152">Issue description</span></span>

<span data-ttu-id="97d53-153">Lorsque vous utilisez le processus *Sélection de cluster dirigée par le système*, si vous configurez un profil de cluster où, par exemple, 10 positions peuvent être sélectionnées, le processus fonctionne comme prévu lorsqu'il y a suffisamment de travail pour sélectionner 10 positions.</span><span class="sxs-lookup"><span data-stu-id="97d53-153">When you use the *System directed cluster picking* process, if you configure a cluster profile where, for example, 10 positions can be picked, the process works as planned when there is enough work to pick to 10 positions.</span></span> <span data-ttu-id="97d53-154">Toutefois, s'il n'y a que huit positions à sélectionner, vous recevez ce message d'erreur, car il n'y a pas assez de travail pour un cluster.</span><span class="sxs-lookup"><span data-stu-id="97d53-154">However, if there are only eight positions to pick, you receive this error message, because there isn't enough work for one cluster.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="97d53-155">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="97d53-155">Issue resolution</span></span>

<span data-ttu-id="97d53-156">Pour résoudre ce problème, modifiez le profil du cluster et définissez l'option **Activer les positions** sur *Non*.</span><span class="sxs-lookup"><span data-stu-id="97d53-156">To fix this issue, edit the cluster profile, and set the **Activate positions** option to *No*.</span></span>
