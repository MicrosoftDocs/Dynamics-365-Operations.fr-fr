---
title: Résoudre des problèmes de configuration de l’entrepôt
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la configuration dans Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 9bbe92627f53b3b4b04597be144d602b3cae7ed7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646105"
---
# <a name="troubleshoot-warehouse-configuration"></a><span data-ttu-id="79a0d-103">Résoudre des problèmes de configuration de l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="79a0d-103">Troubleshoot warehouse configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79a0d-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la configuration dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="79a0d-104">This topic describes how to fix common issues that you might encounter while you configure Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a><span data-ttu-id="79a0d-105">Je reçois le message d'erreur suivant : "Le contenant ou l'emplacement n'est pas valide pour l'unité."</span><span class="sxs-lookup"><span data-stu-id="79a0d-105">I receive the following error message: "The license plate or location is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="79a0d-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-106">Issue description</span></span>

<span data-ttu-id="79a0d-107">Vous recevez ce message d'erreur lorsque vous numérisez un ID de contenant ou un emplacement.</span><span class="sxs-lookup"><span data-stu-id="79a0d-107">You receive this error message when you scan a license plate ID or location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="79a0d-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-108">Issue resolution</span></span>

<span data-ttu-id="79a0d-109">Assurez-vous que l'ID de contenant n'est pas réservé par autre chose.</span><span class="sxs-lookup"><span data-stu-id="79a0d-109">Make sure that the license plate ID isn't reserved by something else.</span></span> <span data-ttu-id="79a0d-110">Ce problème se produisait lorsque la valeur numérisée par un utilisateur dans l'application d'entrepôt était à la fois un emplacement valide et un ID de contenant valide.</span><span class="sxs-lookup"><span data-stu-id="79a0d-110">This issue used to occur when the value that a user scanned in the warehouse app was both a valid location and a valid license plate ID.</span></span> <span data-ttu-id="79a0d-111">Cependant, ce problème a été résolu dans la version 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="79a0d-111">However, this issue was resolved in version 10.0.11.</span></span>

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a><span data-ttu-id="79a0d-112">Je reçois le message d'erreur suivant : "Le contenant doit être spécifié pour cet emplacement."</span><span class="sxs-lookup"><span data-stu-id="79a0d-112">I receive the following error message: "License plate must be specified for this location."</span></span>

### <a name="issue-description"></a><span data-ttu-id="79a0d-113">Description du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-113">Issue description</span></span>

<span data-ttu-id="79a0d-114">Vous recevez ce message d'erreur si vous créez un ordre de transfert à l'aide d'un entrepôt qui n'est pas activé pour la gestion avancée des entrepôts (WMS), puis, une fois le travail terminé, vous essayez de confirmer l'expédition.</span><span class="sxs-lookup"><span data-stu-id="79a0d-114">You receive this error message if you create a transfer order by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="79a0d-115">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-115">Issue resolution</span></span>

<span data-ttu-id="79a0d-116">Le champ **Emplacement de réception par défaut** est vide pour un entrepôt de transit de l'entrepôt "Expéditeur".</span><span class="sxs-lookup"><span data-stu-id="79a0d-116">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="79a0d-117">Pour résoudre ce problème, spécifiez un emplacement de réception par défaut dans l'entrepôt de transit.</span><span class="sxs-lookup"><span data-stu-id="79a0d-117">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="79a0d-118">Assurez-vous que cet emplacement est contrôlé par conteneur.</span><span class="sxs-lookup"><span data-stu-id="79a0d-118">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a><span data-ttu-id="79a0d-119">Je reçois le message d'erreur suivant : "Vous ne pouvez pas créer une ligne de modèle de travail pour la modification de l'état de stock car le type de travail n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="79a0d-119">I receive the following error message: "You can't create a work template line for Inventory status change because the work type is not valid.</span></span> <span data-ttu-id="79a0d-120">Sélectionnez un autre type de travail. »</span><span class="sxs-lookup"><span data-stu-id="79a0d-120">Select a different work type."</span></span>

### <a name="issue-description"></a><span data-ttu-id="79a0d-121">Description du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-121">Issue description</span></span>

<span data-ttu-id="79a0d-122">Pour un modèle de travail, vous ne pouvez pas sélectionner *Changement de l'état de stock* dans la colonne **Type de travail** de la section **Détails du modèle de travail**.</span><span class="sxs-lookup"><span data-stu-id="79a0d-122">For a work template, you can't select *Inventory status change* in the **Work type** column of the **Work template details** section.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="79a0d-123">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-123">Issue resolution</span></span>

<span data-ttu-id="79a0d-124">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="79a0d-124">This behavior is by design.</span></span> <span data-ttu-id="79a0d-125">Le type de travail *Changement du statut du stock* est utilisé uniquement par les processus système.</span><span class="sxs-lookup"><span data-stu-id="79a0d-125">The *Inventory status change* work type is used only by system processes.</span></span> <span data-ttu-id="79a0d-126">Cette valeur peut être configurée.</span><span class="sxs-lookup"><span data-stu-id="79a0d-126">It can't be configured.</span></span> <span data-ttu-id="79a0d-127">Étant donné que la liste des types de travail est fixée comme une énumération, les entrées supplémentaires ne peuvent pas être filtrées en dehors du menu déroulant **Type de travail**.</span><span class="sxs-lookup"><span data-stu-id="79a0d-127">Because the list of work types is fixed as an enumeration, the extra entries can't be filtered out of the **Work type** drop-down menu.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="79a0d-128">Je reçois le message d'erreur suivant : "La quantité n'est pas valide pour l'unité 1%."</span><span class="sxs-lookup"><span data-stu-id="79a0d-128">I receive the following error message: "The Quantity is not valid for unit 1%."</span></span>

### <a name="issue-description"></a><span data-ttu-id="79a0d-129">Description du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-129">Issue description</span></span>

<span data-ttu-id="79a0d-130">La quantité n'est pas valable pour l'unité *ea* lorsqu'il y a des travaux de prélèvement qui ont plusieurs contenants à un seul emplacement.</span><span class="sxs-lookup"><span data-stu-id="79a0d-130">The quantity isn't valid for the *ea* unit when there is picking work that has multiple license plates in one location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="79a0d-131">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-131">Issue resolution</span></span>

<span data-ttu-id="79a0d-132">Vérifiez que les champs **ID du groupe de séquences d'unités** et **Conversions d'unités** du produit lancé ou de la variante de produit sont correctement définis.</span><span class="sxs-lookup"><span data-stu-id="79a0d-132">Verify that the **Unit sequence group ID** and **Unit conversions** fields on the released product or product variant are set correctly.</span></span>

<span data-ttu-id="79a0d-133">Notez que le message d'erreur a été amélioré dans la version 10.0.15 (voir [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span><span class="sxs-lookup"><span data-stu-id="79a0d-133">Note that the error message has been improved in version 10.0.15 (see [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span></span> <span data-ttu-id="79a0d-134">Le nouveau message d'erreur est : "La quantité n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="79a0d-134">The new error message is, "The quantity is not valid.</span></span> <span data-ttu-id="79a0d-135">Prévu %1 %2."</span><span class="sxs-lookup"><span data-stu-id="79a0d-135">Expected %1 %2."</span></span>

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a><span data-ttu-id="79a0d-136">Dans les directives d'emplacement pour la mise en œuvre des commandes client, l'option de plusieurs SKU n'évalue pas plusieurs actions de directive d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="79a0d-136">In location directives for sales order put work, the multiple SKU option doesn't evaluate multiple location directive actions.</span></span>

### <a name="issue-description"></a><span data-ttu-id="79a0d-137">Description du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-137">Issue description</span></span>

<span data-ttu-id="79a0d-138">Les directives d'emplacement du type d'ordre de travail *Commandes client* et le type de travail *Ranger* n'évalue pas plusieurs actions de directive d'emplacement lorsque l'option **Plusieurs SKU** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="79a0d-138">Location directives of the *Sales orders* work order type and the *Put* work type don't evaluate multiple location directive actions when the **Multiple SKU** option is selected.</span></span> <span data-ttu-id="79a0d-139">Seule la première action de directive d'emplacement est évaluée.</span><span class="sxs-lookup"><span data-stu-id="79a0d-139">Only the first location directive action is evaluated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="79a0d-140">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-140">Issue resolution</span></span>

<span data-ttu-id="79a0d-141">Une nouvelle fonctionnalité, *Évaluer toutes les actions pour les directives d'emplacement à plusieurs SKU*, a été ajouté dans la version 10.0.15 (voir [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span><span class="sxs-lookup"><span data-stu-id="79a0d-141">A new feature, *Evaluate all actions for Multi SKU location directives*, has been added in version 10.0.15 (see [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span></span> <span data-ttu-id="79a0d-142">Cette fonctionnalité évalue toutes les actions pour les directives d'emplacement à plusieurs SKU.</span><span class="sxs-lookup"><span data-stu-id="79a0d-142">This feature evaluates all actions for multi-SKU location directives.</span></span> <span data-ttu-id="79a0d-143">Si vous avez besoin de cette fonctionnalité, utilisez [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour l'activer.</span><span class="sxs-lookup"><span data-stu-id="79a0d-143">If you require this feature, use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn it on.</span></span>

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a><span data-ttu-id="79a0d-144">Je ne peux pas utiliser l'application d'entrepôt pour effectuer un prélèvement partiel.</span><span class="sxs-lookup"><span data-stu-id="79a0d-144">I can't use the warehouse app to do partial picking.</span></span>

### <a name="issue-description"></a><span data-ttu-id="79a0d-145">Description du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-145">Issue description</span></span>

<span data-ttu-id="79a0d-146">Pour les commandes client et les ordres de transfert, vous ne pouvez pas ignorer des articles et effectuer un prélèvement partiel.</span><span class="sxs-lookup"><span data-stu-id="79a0d-146">For sales and transfer orders, you can't skip items and do partial picking.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="79a0d-147">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-147">Issue resolution</span></span>

<span data-ttu-id="79a0d-148">Sur la page **Éléments du menu de l'appareil mobile**, pour chaque élément de menu configuré pour traiter les commandes client ou transférer les commandes, définissez l'option **Autoriser le fractionnement du travail** sur le raccourci **Général** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="79a0d-148">On the **Mobile device menu items** page, for each menu item that is set up to process sales orders or transfer orders, set the **Allow splitting of work** option on the **General** FastTab to *Yes*.</span></span>

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a><span data-ttu-id="79a0d-149">Comment puis-je modifier le statut du stock pour un travail en quantité partielle ?</span><span class="sxs-lookup"><span data-stu-id="79a0d-149">How can I do an inventory status change for partial quantity work?</span></span>

### <a name="issue-description"></a><span data-ttu-id="79a0d-150">Description du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-150">Issue description</span></span>

<span data-ttu-id="79a0d-151">Vous souhaitez effectuer un changement de statut de stock pour une quantité partielle d'un lot.</span><span class="sxs-lookup"><span data-stu-id="79a0d-151">You want to do an inventory status change for a partial quantity of a batch.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="79a0d-152">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="79a0d-152">Issue resolution</span></span>

<span data-ttu-id="79a0d-153">Pour permettre aux employés d'effectuer cette modification, vous pouvez créer un élément de menu pour l'application d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="79a0d-153">To enable workers to make this change, you can create a menu item for the warehouse app.</span></span> <span data-ttu-id="79a0d-154">Sur la page **Options de menu d'appareil mobile**, créez (ou modifiez) une option de menu avec l'un des paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="79a0d-154">On the **Mobile device menu items** page, create (or edit) a menu item that has the following settings:</span></span>

- <span data-ttu-id="79a0d-155">**Mode :** *Travail*</span><span class="sxs-lookup"><span data-stu-id="79a0d-155">**Mode:** *Work*</span></span>
- <span data-ttu-id="79a0d-156">**Utiliser un travail existant :** *Non*</span><span class="sxs-lookup"><span data-stu-id="79a0d-156">**Use existing work:** *No*</span></span>
- <span data-ttu-id="79a0d-157">**Processus de création de travail :** *Mouvement*</span><span class="sxs-lookup"><span data-stu-id="79a0d-157">**Work creation process:** *Movement*</span></span>
- <span data-ttu-id="79a0d-158">**Afficher le statut de stock :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="79a0d-158">**Display inventory status:** *Yes*</span></span>

<span data-ttu-id="79a0d-159">Vous pouvez définir d'autres champs dans la page comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="79a0d-159">You can set other fields on the page as you require.</span></span>