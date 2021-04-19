---
title: Résoudre des problèmes de réservations dans la gestion des entrepôts
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: d0d73396772ed9e8397797d6685fb550d911303b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828104"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="d80c1-103">Résoudre des problèmes de réservations dans la gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="d80c1-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d80c1-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d80c1-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="d80c1-105">Pour les rubriques liées aux enregistrements de lots et de numéros de série, voir [Résoudre les problèmes liés aux hiérarchies de réservation de lots et de série en entrepôt](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="d80c1-105">For topics that are related to batch and serial number registrations, see [Troubleshoot warehouse batch and serial reservation hierarchies](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="d80c1-106">Je reçois le message d’erreur suivant : "Impossible de supprimer les réservations, car un travail qui a été créé repose sur ces réservations."</span><span class="sxs-lookup"><span data-stu-id="d80c1-106">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="d80c1-107">Description du problème</span><span class="sxs-lookup"><span data-stu-id="d80c1-107">Issue description</span></span>

<span data-ttu-id="d80c1-108">Vous ne pouvez pas annuler la réservation d’un stock sur une ligne de vente, car il y a un travail en cours sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="d80c1-108">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d80c1-109">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="d80c1-109">Issue resolution</span></span>

<span data-ttu-id="d80c1-110">Vérifiez s’il existe un travail de groupe d’emballage ouvert pour amener l’article d’une station d’emballage à un autre emplacement (tel que *Baydoor*).</span><span class="sxs-lookup"><span data-stu-id="d80c1-110">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="d80c1-111">Passez en revue les enregistrements sur les pages **Journal de l’historique de création de travail** et **Détails du travail** pour déterminer ce qui réserve physiquement le stock, puis terminer ou supprimer le travail pour libérer la réservation.</span><span class="sxs-lookup"><span data-stu-id="d80c1-111">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="d80c1-112">Je reçois le message d’erreur suivant : "Quantité de stock -%1 n’a pas pu être mis à jour en raison de transactions de stock insuffisantes pour l’article %2..."</span><span class="sxs-lookup"><span data-stu-id="d80c1-112">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="d80c1-113">Description du problème</span><span class="sxs-lookup"><span data-stu-id="d80c1-113">Issue description</span></span>

<span data-ttu-id="d80c1-114">Ce problème peut se produire si le système ne peut pas mettre à jour une quantité de stock car il n’y a pas suffisamment de transactions de stock qui ont les dimensions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="d80c1-114">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="d80c1-115">Voici l’intégralité du message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="d80c1-115">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="d80c1-116">Quantité de stock -%1 n’a pas pu être mis à jour en raison de transactions de stock insuffisantes pour l’article %2 avec dimensions Taille=%3, Couleur=%4, Ajouts=%5, Site=%6, Entrepôt=%7, Emplacement=%8, Statut du stock=Disponible, Contenant=%9, Numéro de lot=%10 pour l’ID de référence %11 sur l’ID de lot %12.</span><span class="sxs-lookup"><span data-stu-id="d80c1-116">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d80c1-117">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="d80c1-117">Issue resolution</span></span>

<span data-ttu-id="d80c1-118">Assurez-vous qu’aucune transaction de stock ne réserve physiquement la quantité.</span><span class="sxs-lookup"><span data-stu-id="d80c1-118">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="d80c1-119">Par exemple, ces transactions peuvent ouvrir des commandes de qualité, des enregistrements de blocage des stocks ou des commandes de sortie.</span><span class="sxs-lookup"><span data-stu-id="d80c1-119">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="d80c1-120">Je reçois le message d’erreur suivant : "Physique disponible... ne peut pas être réservé car seuls 0,00 sont disponibles dans le stock. »</span><span class="sxs-lookup"><span data-stu-id="d80c1-120">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="d80c1-121">Description du problème</span><span class="sxs-lookup"><span data-stu-id="d80c1-121">Issue description</span></span>

<span data-ttu-id="d80c1-122">Ce problème peut se produire si le système ne peut pas mettre à jour une quantité de stock car il n’y a pas suffisamment de transactions de stock qui ont les dimensions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="d80c1-122">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="d80c1-123">Voici l’intégralité du message d’erreur :</span><span class="sxs-lookup"><span data-stu-id="d80c1-123">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="d80c1-124">Site physique disponible=%1, Entrepôt=%2, Statut du stock=Disponible, Numéro de lot=%3, Propriétaire=%4 :%5 ne peut pas être réservé car seuls 0,00 sont disponibles dans le stock.</span><span class="sxs-lookup"><span data-stu-id="d80c1-124">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d80c1-125">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="d80c1-125">Issue resolution</span></span>

<span data-ttu-id="d80c1-126">Ce problème est probablement dû à un travail ouvert.</span><span class="sxs-lookup"><span data-stu-id="d80c1-126">This issue is probably caused by open work.</span></span> <span data-ttu-id="d80c1-127">Soit terminer le travail, soit recevez sans création de travail.</span><span class="sxs-lookup"><span data-stu-id="d80c1-127">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="d80c1-128">Assurez-vous qu’aucune transaction de stock ne réserve physiquement la quantité.</span><span class="sxs-lookup"><span data-stu-id="d80c1-128">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="d80c1-129">Par exemple, ces transactions peuvent être des commandes de qualité ouvertes, des enregistrements de blocage des stocks ou des commandes de sortie.</span><span class="sxs-lookup"><span data-stu-id="d80c1-129">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
