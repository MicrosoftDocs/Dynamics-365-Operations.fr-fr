---
title: "Comptes de contrepartie par défaut pour les journaux de facture fournisseur et les journaux d'approbation de facture"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b62eafc71b5d1ad4eaaf252efd1dcbb97b86f3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="093b3-102">Comptes de contrepartie par défaut pour les journaux de facture fournisseur et les journaux d'approbation de facture</span><span class="sxs-lookup"><span data-stu-id="093b3-102">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="093b3-103">Les comptes de contrepartie par défaut sont utilisés dans les pages suivantes de journal des factures fournisseur :</span><span class="sxs-lookup"><span data-stu-id="093b3-103">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="093b3-104">Journal des factures</span><span class="sxs-lookup"><span data-stu-id="093b3-104">Invoice journal</span></span>
-   <span data-ttu-id="093b3-105">Journal des approbations de facture</span><span class="sxs-lookup"><span data-stu-id="093b3-105">Invoice approval journal</span></span>

<span data-ttu-id="093b3-106">Utilisez le tableau suivant pour vous aider à décider où affecter les comptes par défaut pour les journaux des factures.</span><span class="sxs-lookup"><span data-stu-id="093b3-106">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="093b3-107">Paramétrez des comptes par défaut ici...</span><span class="sxs-lookup"><span data-stu-id="093b3-107">Set up default accounts here</span></span></th>
<th><span data-ttu-id="093b3-108">... pour fournir les comptes par défaut ici</span><span class="sxs-lookup"><span data-stu-id="093b3-108">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="093b3-109">Comment cette option affecte le traitement</span><span class="sxs-lookup"><span data-stu-id="093b3-109">How this option affects processing</span></span></th>
<th><span data-ttu-id="093b3-110">Quand utiliser cette option</span><span class="sxs-lookup"><span data-stu-id="093b3-110">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="093b3-111"><strong>Groupe de fournisseurs</strong> – Paramétrez des comptes de contrepartie par défaut pour des groupes de fournisseurs sur la page <strong>Paramétrage du compte par défaut</strong>, que vous pouvez ouvrir depuis la page <strong>Groupes de fournisseurs</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-111"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="093b3-112">Compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="093b3-112">Vendor account</span></span></li>
<li><span data-ttu-id="093b3-113">Entrées de journal pour les comptes fournisseur dans le groupe de fournisseurs, si des comptes par défaut ne sont pas spécifiés pour les comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="093b3-113">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="093b3-114">Les comptes de contrepartie par défaut pour les groupes de fournisseurs sont affichés comme des comptes de contrepartie par défaut pour les fournisseurs sur la page <strong>Paramétrage du compte par défaut</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-114">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="093b3-115">Vous pouvez ouvrir cette page depuis la page de la liste <strong>Tous les fournisseurs</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-115">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="093b3-116">Utilisez cette option si vous payez généralement le même type de choses auprès des mêmes groupes de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="093b3-116">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="093b3-117"><strong>Compte fournisseur</strong> – Paramétrez les comptes par défaut pour les comptes fournisseur sur la page <strong>Paramétrage du compte par défaut</strong>, que vous pouvez ouvrir depuis la page <strong>Fournisseurs</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-117"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="093b3-118">Entrées de journal pour le compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="093b3-118">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="093b3-119">Les comptes de contrepartie par défaut pour les comptes fournisseur sont affichés comme des comptes de contrepartie par défaut pour les entrées de journal du compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="093b3-119">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="093b3-120">Utilisez cette option si vous payez généralement le même type de choses auprès des mêmes fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="093b3-120">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="093b3-121"><strong>Noms de journal</strong> – Paramétrez des comptes de contrepartie par défaut pour les journaux sur la page <strong>Noms de journal</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-121"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="093b3-122">Sélectionnez l'option <strong>Compte de contrepartie fixe</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-122">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="093b3-123">Notez que vous ne pouvez pas spécifier de comptes de contrepartie par défaut dans les noms de journal si le type de journal des noms de journal est <strong>Registre des factures</strong> ou <strong>Approbation</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-123">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="093b3-124">En-tête de journal utilisant le nom de journal</span><span class="sxs-lookup"><span data-stu-id="093b3-124">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="093b3-125">Entrées de journal dans les journaux qui utilisent le nom de journal</span><span class="sxs-lookup"><span data-stu-id="093b3-125">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="093b3-126">Si l'option <strong>Compte de contrepartie fixe</strong> de la page <strong>Noms de journal</strong> est sélectionnée, le compte de contrepartie pour le nom de journal remplace le compte de contrepartie par défaut pour le fournisseur ou le groupe de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="093b3-126">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="093b3-127">Utilisez cette option pour paramétrer des journaux pour les coûts spécifiques et les dépenses facturées sur des comptes spécifiques, indépendamment du fournisseur ou du groupe de fournisseurs dont le fournisseur fait partie.</span><span class="sxs-lookup"><span data-stu-id="093b3-127">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="093b3-128"><strong>Noms de journal</strong> – Paramétrez des comptes de contrepartie par défaut pour les journaux sur la page <strong>Noms de journal</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-128"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="093b3-129">Désactivez l'option <strong>Compte de contrepartie fixe</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-129">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="093b3-130">Notez que vous ne pouvez pas spécifier de comptes de contrepartie par défaut dans les noms de journal si le type de journal des noms de journal est <strong>Registre des factures</strong> ou <strong>Approbation</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-130">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="093b3-131">En-tête de journal</span><span class="sxs-lookup"><span data-stu-id="093b3-131">Journal header</span></span></li>
<li><span data-ttu-id="093b3-132">Entrées de journal dans les journaux qui utilisent le nom de journal</span><span class="sxs-lookup"><span data-stu-id="093b3-132">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="093b3-133">Ces entrées par défaut sont utilisées dans des écrans d'en-tête de journal, et le compte de contrepartie dans l'écran d'en-tête de journal est utilisé comme entrée par défaut sur la pages de N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="093b3-133">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="093b3-134">Les comptes par défaut de la page <strong>Noms de journal </strong>sont utilisés uniquement si les comptes par défaut ne sont pas paramétrés pour le compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="093b3-134">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="093b3-135">Utilisez cette option pour paramétrer des comptes par défaut à utiliser lorsqu'un compte de contrepartie par défaut du fournisseur n'est pas affecté.</span><span class="sxs-lookup"><span data-stu-id="093b3-135">Use this option to set up default accounts that are used when a default vendor offset account isn't assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="093b3-136"><strong>En-tête de journal</strong> – Paramétrez un compte de contrepartie par défaut pour un journal à utiliser comme entrée par défaut dans les pages de N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="093b3-136"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="093b3-137">Notez que vous ne pouvez pas spécifier de comptes de contrepartie par défaut sur l'en-tête de journal si le type de journal des noms de journal est <strong>Registre des factures</strong> ou <strong>Approbation</strong>.</span><span class="sxs-lookup"><span data-stu-id="093b3-137">Note that you can't specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="093b3-138">Entrées de journal dans le journal</span><span class="sxs-lookup"><span data-stu-id="093b3-138">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="093b3-139">Le compte de contrepartie par défaut pour un journal est utilisé comme entrée par défaut sur les pages de N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="093b3-139">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="093b3-140">Utilisez cette option pour accélérer la saisie des données si la plupart des entrées d'un journal ont le même compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="093b3-140">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>






