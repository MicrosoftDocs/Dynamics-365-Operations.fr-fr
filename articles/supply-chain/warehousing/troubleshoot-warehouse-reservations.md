---
title: Résoudre des problèmes de réservations dans la gestion des entrepôts
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a9a5d20732a802fc58c392853af8334bbc07de73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248713"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="e99bd-103">Résoudre des problèmes de réservations dans la gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="e99bd-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e99bd-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e99bd-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="e99bd-105">Je reçois le message d’erreur suivant : "Impossible de supprimer les réservations, car un travail qui a été créé repose sur ces réservations."</span><span class="sxs-lookup"><span data-stu-id="e99bd-105">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e99bd-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="e99bd-106">Issue description</span></span>

<span data-ttu-id="e99bd-107">Vous ne pouvez pas annuler la réservation d’un stock sur une ligne de vente, car il y a un travail en cours sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="e99bd-107">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e99bd-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="e99bd-108">Issue resolution</span></span>

<span data-ttu-id="e99bd-109">Vérifiez s’il existe un travail de groupe d’emballage ouvert pour amener l’article d’une station d’emballage à un autre emplacement (tel que *Baydoor*).</span><span class="sxs-lookup"><span data-stu-id="e99bd-109">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="e99bd-110">Passez en revue les enregistrements sur les pages **Journal de l’historique de création de travail** et **Détails du travail** pour déterminer ce qui réserve physiquement le stock, puis terminer ou supprimer le travail pour libérer la réservation.</span><span class="sxs-lookup"><span data-stu-id="e99bd-110">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="e99bd-111">Je reçois le message d’erreur suivant : "Quantité de stock -%1 n’a pas pu être mis à jour en raison de transactions de stock insuffisantes pour l’article %2..."</span><span class="sxs-lookup"><span data-stu-id="e99bd-111">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e99bd-112">Description du problème</span><span class="sxs-lookup"><span data-stu-id="e99bd-112">Issue description</span></span>

<span data-ttu-id="e99bd-113">Ce problème peut se produire si le système ne peut pas mettre à jour une quantité de stock car il n’y a pas suffisamment de transactions de stock qui ont les dimensions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="e99bd-113">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="e99bd-114">Voici l’intégralité du message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="e99bd-114">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="e99bd-115">Quantité de stock -%1 n’a pas pu être mis à jour en raison de transactions de stock insuffisantes pour l’article %2 avec dimensions Taille=%3, Couleur=%4, Ajouts=%5, Site=%6, Entrepôt=%7, Emplacement=%8, Statut du stock=Disponible, Contenant=%9, Numéro de lot=%10 pour l’ID de référence %11 sur l’ID de lot %12.</span><span class="sxs-lookup"><span data-stu-id="e99bd-115">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e99bd-116">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="e99bd-116">Issue resolution</span></span>

<span data-ttu-id="e99bd-117">Assurez-vous qu’aucune transaction de stock ne réserve physiquement la quantité.</span><span class="sxs-lookup"><span data-stu-id="e99bd-117">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="e99bd-118">Par exemple, ces transactions peuvent ouvrir des commandes de qualité, des enregistrements de blocage des stocks ou des commandes de sortie.</span><span class="sxs-lookup"><span data-stu-id="e99bd-118">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="e99bd-119">Je reçois le message d’erreur suivant : "Physique disponible... ne peut pas être réservé car seuls 0,00 sont disponibles dans le stock. »</span><span class="sxs-lookup"><span data-stu-id="e99bd-119">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e99bd-120">Description du problème</span><span class="sxs-lookup"><span data-stu-id="e99bd-120">Issue description</span></span>

<span data-ttu-id="e99bd-121">Ce problème peut se produire si le système ne peut pas mettre à jour une quantité de stock car il n’y a pas suffisamment de transactions de stock qui ont les dimensions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="e99bd-121">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="e99bd-122">Voici l’intégralité du message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="e99bd-122">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="e99bd-123">Site physique disponible=%1, Entrepôt=%2, Statut du stock=Disponible, Numéro de lot=%3, Propriétaire=%4 :%5 ne peut pas être réservé car seuls 0,00 sont disponibles dans le stock.</span><span class="sxs-lookup"><span data-stu-id="e99bd-123">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e99bd-124">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="e99bd-124">Issue resolution</span></span>

<span data-ttu-id="e99bd-125">Ce problème est probablement dû à un travail ouvert.</span><span class="sxs-lookup"><span data-stu-id="e99bd-125">This issue is probably caused by open work.</span></span> <span data-ttu-id="e99bd-126">Soit terminer le travail, soit recevez sans création de travail.</span><span class="sxs-lookup"><span data-stu-id="e99bd-126">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="e99bd-127">Assurez-vous qu’aucune transaction de stock ne réserve physiquement la quantité.</span><span class="sxs-lookup"><span data-stu-id="e99bd-127">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="e99bd-128">Par exemple, ces transactions peuvent être des commandes de qualité ouvertes, des enregistrements de blocage des stocks ou des commandes de sortie.</span><span class="sxs-lookup"><span data-stu-id="e99bd-128">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a><span data-ttu-id="e99bd-129">Je reçois le message d’erreur suivant : "Pour être affectés à la vague, les lignes de charge doivent spécifier les dimensions au-dessus de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="e99bd-129">I receive the following error message: "To be assigned to wave, load lines must specify the dimensions above the location.</span></span> <span data-ttu-id="e99bd-130">Pour attribuer ces dimensions, réservez et recréez la ligne de charge. »</span><span class="sxs-lookup"><span data-stu-id="e99bd-130">To assign these dimensions, reserve and recreate the load line."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e99bd-131">Description du problème</span><span class="sxs-lookup"><span data-stu-id="e99bd-131">Issue description</span></span>

<span data-ttu-id="e99bd-132">Lorsque vous utilisez un article qui a une hiérarchie de réservation "lot au-dessus" (avec la dimension **Numéro de lot** placée *au dessus* de la dimension **Emplacement**), l’ordre **Lancement dans l’entrepôt** sur la page **Atelier de planification de charge** pour une quantité partielle ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="e99bd-132">When you use an item that has a "batch above" reservation hierarchy (with the **Batch number** dimension placed *above* the **Location** dimension), the **Release to warehouse** command on the **Load planning workbench** page for a partial quantity doesn't work.</span></span> <span data-ttu-id="e99bd-133">Vous recevez ce message d’erreur et aucun travail n’est créé pour la quantité partielle.</span><span class="sxs-lookup"><span data-stu-id="e99bd-133">You receive this error message, and no work is created for the partial quantity.</span></span>

<span data-ttu-id="e99bd-134">Toutefois, lorsque vous utilisez un article qui a une hiérarchie de réservation "lot en dessous" (avec la dimension **Numéro de lot** placée *en dessous* de la dimension **Emplacement**), vous pouvez lancer une charge sur la page **Atelier de planification de charge** pour une quantité partielle.</span><span class="sxs-lookup"><span data-stu-id="e99bd-134">However, if you use an item that has a "batch below" reservation hierarchy (with the **Batch number** dimension placed *below* the **Location** dimension), you can release a load from the **Load planning workbench** page for a partial quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e99bd-135">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="e99bd-135">Issue resolution</span></span>

<span data-ttu-id="e99bd-136">Ce comportement est fait exprès.</span><span class="sxs-lookup"><span data-stu-id="e99bd-136">This behavior is by design.</span></span> <span data-ttu-id="e99bd-137">Si vous mettez une dimension au-dessus de la dimension **Emplacement** dans la hiérarchie de réservation, elle doit être spécifiée avant le lancement vers l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e99bd-137">If you put a dimension above the **Location** dimension in the reservation hierarchy, it must be specified before the release to the warehouse.</span></span> <span data-ttu-id="e99bd-138">Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité lors des versions vers l’entrepôt à partir de l’atelier de planification de la charge.</span><span class="sxs-lookup"><span data-stu-id="e99bd-138">Microsoft has evaluated this issue and has determined that it's a feature limitation during releases to the warehouse from the load planning workbench.</span></span> <span data-ttu-id="e99bd-139">Les quantités partielles ne peuvent pas être libérées si une ou plusieurs dimensions au-dessus de **Emplacement** ne sont pas spécifiés.</span><span class="sxs-lookup"><span data-stu-id="e99bd-139">Partial quantities can't be released if one or more dimensions above **Location** aren't specified.</span></span>

<span data-ttu-id="e99bd-140">Pour plus d’informations, voir [Stratégie flexible de réservation de dimension au niveau de l’entrepôt](flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="e99bd-140">For more information, see [Flexible warehouse-level dimension reservation policy](flexible-warehouse-level-dimension-reservation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]