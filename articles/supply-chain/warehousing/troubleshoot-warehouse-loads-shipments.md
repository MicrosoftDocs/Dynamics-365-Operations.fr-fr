---
title: Résoudre des problèmes de création de chargement et expéditions
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de création et d’expéditions de charges dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e9964376a794661058da78152879d2142dd7ec51
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828200"
---
# <a name="troubleshoot-load-building-and-shipments"></a><span data-ttu-id="2de26-103">Résoudre des problèmes de création de chargement et expéditions</span><span class="sxs-lookup"><span data-stu-id="2de26-103">Troubleshoot load building and shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2de26-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de création et d’expéditions de charges dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2de26-104">This topic describes how to fix common issues that you might encounter while you work with load building and shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a><span data-ttu-id="2de26-105">Je reçois le message d’erreur suivant : "Vous ne pouvez pas créer une ligne de chargement pour cette ligne de commande car elle contient des dimensions de stock qui ne sont pas valides..."</span><span class="sxs-lookup"><span data-stu-id="2de26-105">I receive the following error message: "You can't create a load line for this order line because it contains inventory dimensions that are invalid..."</span></span>

### <a name="issue-description"></a><span data-ttu-id="2de26-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-106">Issue description</span></span>

<span data-ttu-id="2de26-107">Le message d’erreur suivant s’affiche lorsque vous essayez de lancer une commande client de retour à l’entrepôt :</span><span class="sxs-lookup"><span data-stu-id="2de26-107">You receive the following error message when you try to release a return sales order to the warehouse:</span></span>

> <span data-ttu-id="2de26-108">Vous ne pouvez pas créer une ligne de chargement pour cette ligne de commande car elle contient des dimensions de stock qui ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="2de26-108">You can't create a load line for this order line because it contains inventory dimensions that are invalid.</span></span> <span data-ttu-id="2de26-109">Vous ne pouvez pas référencer les dimensions de stock situées sous la dimension d’emplacement dans la hiérarchie de réservation.</span><span class="sxs-lookup"><span data-stu-id="2de26-109">You can't reference inventory dimensions that are located below the location dimension in the reservation hierarchy.</span></span> <span data-ttu-id="2de26-110">Supprimez les dimensions non valides de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="2de26-110">Remove the invalid dimensions from the order line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2de26-111">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-111">Issue resolution</span></span>

<span data-ttu-id="2de26-112">Malheureusement, le produit ne prend pas en charge le traitement de la charge pour un processus de retour des ventes.</span><span class="sxs-lookup"><span data-stu-id="2de26-112">Unfortunately, the product doesn't support load processing for a sales return process.</span></span> <span data-ttu-id="2de26-113">Par conséquent, vous ne pouvez pas valider le retour de la commande client à l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="2de26-113">Therefore, you can't release the return sales order to the warehouse.</span></span>

<span data-ttu-id="2de26-114">Sur les transactions de commande client, vous ne pouvez pas référencer les dimensions de stock situées sous la dimension d’**emplacement** dans la hiérarchie de réservation.</span><span class="sxs-lookup"><span data-stu-id="2de26-114">On sales order transactions, you can't reference inventory dimensions that are located below the **Location** dimension in the reservation hierarchy.</span></span> <span data-ttu-id="2de26-115">La résolution consiste à supprimer les dimensions non valides de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="2de26-115">The resolution is to remove the invalid dimensions from the order line.</span></span>

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a><span data-ttu-id="2de26-116">Je reçois le message d’erreur suivant : "Une des lignes est déjà sur une charge.</span><span class="sxs-lookup"><span data-stu-id="2de26-116">I receive the following error message: "One of the lines is already on a load.</span></span> <span data-ttu-id="2de26-117">Impossible de libérer dans l’entrepôt."</span><span class="sxs-lookup"><span data-stu-id="2de26-117">Unable to release to warehouse."</span></span>

### <a name="issue-description"></a><span data-ttu-id="2de26-118">Description du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-118">Issue description</span></span>

<span data-ttu-id="2de26-119">Si vous créez manuellement des chargements, ou si vous configurez le processus de sorte que les chargements soient déjà créés avant la saisie de la ligne de commande client, on suppose que la publication suivante sera effectuée manuellement et que l’itinéraire et le classement du chargement seront utilisés.</span><span class="sxs-lookup"><span data-stu-id="2de26-119">If you manually create loads, or if you set up the process so that loads are already created before sales order line entry occurs, the assumption is that the subsequent release will be done manually, and that the route and rating from the load will be used.</span></span>

<span data-ttu-id="2de26-120">Dans un autre scénario possible, vous essayez d’effectuer une libération automatique dans l’entrepôt, mais le processus de vague n’a pas réussi à créer du travail.</span><span class="sxs-lookup"><span data-stu-id="2de26-120">In another possible scenario, you're trying to do an automatic release to the warehouse, but the wave process failed to create work.</span></span> <span data-ttu-id="2de26-121">Par conséquent, une expédition ou un chargement en cours est toujours créé.</span><span class="sxs-lookup"><span data-stu-id="2de26-121">Therefore, an open shipment or load is still created.</span></span> <span data-ttu-id="2de26-122">Cet envoi ou chargement en cours bloque ensuite les tentatives ultérieures de validation automatique de la commande jusqu’à ce que vous supprimiez l’envoi ou le chargement en cours, ou que vous retraitez manuellement la vague.</span><span class="sxs-lookup"><span data-stu-id="2de26-122">This open shipment or load then blocks subsequent attempts to automatically release the order until you either delete the open shipment or load, or manually reprocess the wave.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2de26-123">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-123">Issue resolution</span></span>

<span data-ttu-id="2de26-124">Vous pouvez valider à partir de la page de commande client, ou la validation automatique peut être effectuée à partir de la page de validation de commande client, uniquement s’il n’y a pas de chargement avant la validation vers l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="2de26-124">You can release from the sales order page, or automatic release can be done from the release sales order page, only if no load exists before the release to the warehouse.</span></span> <span data-ttu-id="2de26-125">Le chargement sera automatiquement créé après le traitement de la vague.</span><span class="sxs-lookup"><span data-stu-id="2de26-125">The load will automatically be created after the wave is processed.</span></span>

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a><span data-ttu-id="2de26-126">Je reçois le message d’erreur suivant : "La correction de la note de livraison ne peut pas être traitée.</span><span class="sxs-lookup"><span data-stu-id="2de26-126">I receive the following error message: "The delivery note correction can't be processed.</span></span> <span data-ttu-id="2de26-127">La note de livraison ne contient que les articles soumis aux processus de gestion de l’entrepôt, car ils ne sont pas pris en charge par la correction de la note de livraison. »</span><span class="sxs-lookup"><span data-stu-id="2de26-127">The delivery note only contains items that are subject to warehouse management processes, as these are not supported by Delivery Note correction."</span></span>

### <a name="issue-description"></a><span data-ttu-id="2de26-128">Description du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-128">Issue description</span></span>

<span data-ttu-id="2de26-129">Après avoir publié une note de livraison, vous ne pouvez pas l’annuler, car le bouton **Annuler** n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="2de26-129">After you post a delivery note, you can't cancel it, because the **Cancel** button is unavailable.</span></span> <span data-ttu-id="2de26-130">Vous ne pouvez pas non plus corriger la note de livraison.</span><span class="sxs-lookup"><span data-stu-id="2de26-130">You also can't correct the delivery note.</span></span> <span data-ttu-id="2de26-131">Si vous essayez, vous recevez ce message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="2de26-131">If you try, you receive this error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2de26-132">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-132">Issue resolution</span></span>

<span data-ttu-id="2de26-133">Pour corriger les bons de livraison validés pour les articles qui sont activés pour la gestion des entrepôts avancées (WMS), vous devez effectuer la validation à partir du chargement et non directement à partir de la commande.</span><span class="sxs-lookup"><span data-stu-id="2de26-133">To correct posted packing slips for items that are enabled for advanced warehouse management (WMS), you must do the posting from the load, not directly from the order.</span></span>

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a><span data-ttu-id="2de26-134">Comment puis-je créer du travail à partir de chargements sortantes au lieu de vagues ?</span><span class="sxs-lookup"><span data-stu-id="2de26-134">How can I create work from outbound loads instead of waves?</span></span>

### <a name="issue-description"></a><span data-ttu-id="2de26-135">Description du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-135">Issue description</span></span>

<span data-ttu-id="2de26-136">Voici une façon de reproduire ce problème.</span><span class="sxs-lookup"><span data-stu-id="2de26-136">Here is one way to reproduce this issue.</span></span>

1. <span data-ttu-id="2de26-137">Créer un chargement sortant à l’aide d’une commande client ou d’un ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="2de26-137">Create an outbound load by using a sales order or transfer order.</span></span>
2. <span data-ttu-id="2de26-138">Libérez la charge dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="2de26-138">Release the load to the warehouse.</span></span>
3. <span data-ttu-id="2de26-139">Notez qu’aucun travail de prélèvement n’a encore été généré.</span><span class="sxs-lookup"><span data-stu-id="2de26-139">Notice that no picking work has yet been generated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2de26-140">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-140">Issue resolution</span></span>

<span data-ttu-id="2de26-141">Si le travail doit être généré immédiatement lorsque la charge est libérée, vous devez configurer le modèle de vague en conséquence.</span><span class="sxs-lookup"><span data-stu-id="2de26-141">If work must be generated immediately when the load is released, you must configure the wave template accordingly.</span></span> <span data-ttu-id="2de26-142">Sur le modèle de vague, définissez les options suivantes sur *Oui* :</span><span class="sxs-lookup"><span data-stu-id="2de26-142">On the wave template, set the following options to *Yes*:</span></span>

- <span data-ttu-id="2de26-143">Création automatique de vagues</span><span class="sxs-lookup"><span data-stu-id="2de26-143">Automate wave creation</span></span>
- <span data-ttu-id="2de26-144">Traiter la vague à la sortie dans l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="2de26-144">Process wave at release to warehouse</span></span>
- <span data-ttu-id="2de26-145">Sortie automatique de vagues</span><span class="sxs-lookup"><span data-stu-id="2de26-145">Automate wave release</span></span>

## <a name="i-cant-re-release-a-partially-shipped-load"></a><span data-ttu-id="2de26-146">Je ne peux pas libérer une charge partiellement expédiée.</span><span class="sxs-lookup"><span data-stu-id="2de26-146">I can't re-release a partially shipped load.</span></span>

### <a name="issue-description"></a><span data-ttu-id="2de26-147">Description du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-147">Issue description</span></span>

<span data-ttu-id="2de26-148">Vous ne pouvez pas libérer une charge partiellement libérée vers l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="2de26-148">You can't release a partially shipped load to the warehouse.</span></span> <span data-ttu-id="2de26-149">Lorsque vous effectuez le lancement dans l’entrepôt, un message "Opération terminée" apparaît, mais rien ne se passe et aucun travail n’est créé pour la quantité restante.</span><span class="sxs-lookup"><span data-stu-id="2de26-149">When you do the release to the warehouse, an "Operation complete" message appears, but nothing happens, and no work is created for the remaining quantity.</span></span> <span data-ttu-id="2de26-150">Ce problème se produit lorsque vous utilisez la fonctionnalité de chargement de transport et qu’il y a une réservation incomplète.</span><span class="sxs-lookup"><span data-stu-id="2de26-150">This issue occurs when you use transport load functionality and there is an incomplete reservation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2de26-151">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="2de26-151">Issue resolution</span></span>

<span data-ttu-id="2de26-152">Le [problème KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Les chargements partiellement expédiés peuvent être relancés et retraités") est corrigé dans la [version 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span><span class="sxs-lookup"><span data-stu-id="2de26-152">[KB issue 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Partially shipped loads can be re-waved and re-processed") is fixed in [release 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]