---
title: "Comptes de contrepartie par défaut pour les journaux de facture fournisseur et les journaux d'approbation de facture"
description: "Cette rubrique vous aide à décider où affecter les comptes par défaut pour les journaux des factures."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 45a066ff5b884e8cc78b0fc16d1f1eab9cb0f5f3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="cc11c-103">Comptes de contrepartie par défaut pour les journaux de facture fournisseur et les journaux d'approbation de facture</span><span class="sxs-lookup"><span data-stu-id="cc11c-103">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc11c-104">Les comptes de contrepartie par défaut sont utilisés dans les pages suivantes de journal des factures fournisseur :</span><span class="sxs-lookup"><span data-stu-id="cc11c-104">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="cc11c-105">Journal des factures</span><span class="sxs-lookup"><span data-stu-id="cc11c-105">Invoice journal</span></span>
-   <span data-ttu-id="cc11c-106">Journal des approbations de facture</span><span class="sxs-lookup"><span data-stu-id="cc11c-106">Invoice approval journal</span></span>

<span data-ttu-id="cc11c-107">Utilisez le tableau suivant pour vous aider à décider où affecter les comptes par défaut pour les journaux des factures.</span><span class="sxs-lookup"><span data-stu-id="cc11c-107">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc11c-108">Paramétrez des comptes par défaut ici...</span><span class="sxs-lookup"><span data-stu-id="cc11c-108">Set up default accounts here</span></span></th>
<th><span data-ttu-id="cc11c-109">... pour fournir les comptes par défaut ici</span><span class="sxs-lookup"><span data-stu-id="cc11c-109">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="cc11c-110">Comment cette option affecte le traitement</span><span class="sxs-lookup"><span data-stu-id="cc11c-110">How this option affects processing</span></span></th>
<th><span data-ttu-id="cc11c-111">Quand utiliser cette option</span><span class="sxs-lookup"><span data-stu-id="cc11c-111">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cc11c-112"><strong>Groupe de fournisseurs</strong> – Paramétrez des comptes de contrepartie par défaut pour des groupes de fournisseurs sur la page <strong>Paramétrage du compte par défaut</strong>, que vous pouvez ouvrir depuis la page <strong>Groupes de fournisseurs</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-112"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="cc11c-113">Compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="cc11c-113">Vendor account</span></span></li>
<li><span data-ttu-id="cc11c-114">Entrées de journal pour les comptes fournisseur dans le groupe de fournisseurs, si des comptes par défaut ne sont pas spécifiés pour les comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="cc11c-114">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="cc11c-115">Les comptes de contrepartie par défaut pour les groupes de fournisseurs sont affichés comme des comptes de contrepartie par défaut pour les fournisseurs sur la page <strong>Paramétrage du compte par défaut</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-115">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="cc11c-116">Vous pouvez ouvrir cette page depuis la page de la liste <strong>Tous les fournisseurs</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-116">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="cc11c-117">Utilisez cette option si vous payez généralement le même type de choses auprès des mêmes groupes de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="cc11c-117">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cc11c-118"><strong>Compte fournisseur</strong> – Paramétrez les comptes par défaut pour les comptes fournisseur sur la page <strong>Paramétrage du compte par défaut</strong>, que vous pouvez ouvrir depuis la page <strong>Fournisseurs</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-118"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="cc11c-119">Entrées de journal pour le compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="cc11c-119">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="cc11c-120">Les comptes de contrepartie par défaut pour les comptes fournisseur sont affichés comme des comptes de contrepartie par défaut pour les entrées de journal du compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="cc11c-120">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="cc11c-121">Utilisez cette option si vous payez généralement le même type de choses auprès des mêmes fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="cc11c-121">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cc11c-122"><strong>Noms de journal</strong> – Paramétrez des comptes de contrepartie par défaut pour les journaux sur la page <strong>Noms de journal</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-122"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="cc11c-123">Sélectionnez l'option <strong>Compte de contrepartie fixe</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-123">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="cc11c-124">Notez que vous ne pouvez pas spécifier de comptes de contrepartie par défaut dans les noms de journal si le type de journal des noms de journal est <strong>Registre des factures</strong> ou <strong>Approbation</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-124">Note that you can&#39;t specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="cc11c-125">En-tête de journal utilisant le nom de journal</span><span class="sxs-lookup"><span data-stu-id="cc11c-125">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="cc11c-126">Entrées de journal dans les journaux qui utilisent le nom de journal</span><span class="sxs-lookup"><span data-stu-id="cc11c-126">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="cc11c-127">Si l'option <strong>Compte de contrepartie fixe</strong> de la page <strong>Noms de journal</strong> est sélectionnée, le compte de contrepartie pour le nom de journal remplace le compte de contrepartie par défaut pour le fournisseur ou le groupe de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="cc11c-127">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="cc11c-128">Utilisez cette option pour paramétrer des journaux pour les coûts spécifiques et les dépenses facturées sur des comptes spécifiques, indépendamment du fournisseur ou du groupe de fournisseurs dont le fournisseur fait partie.</span><span class="sxs-lookup"><span data-stu-id="cc11c-128">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cc11c-129"><strong>Noms de journal</strong> – Paramétrez des comptes de contrepartie par défaut pour les journaux sur la page <strong>Noms de journal</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-129"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="cc11c-130">Désactivez l'option <strong>Compte de contrepartie fixe</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-130">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="cc11c-131">Notez que vous ne pouvez pas spécifier de comptes de contrepartie par défaut dans les noms de journal si le type de journal des noms de journal est <strong>Registre des factures</strong> ou <strong>Approbation</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-131">Note that you can&#39;t specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="cc11c-132">En-tête de journal</span><span class="sxs-lookup"><span data-stu-id="cc11c-132">Journal header</span></span></li>
<li><span data-ttu-id="cc11c-133">Entrées de journal dans les journaux qui utilisent le nom de journal</span><span class="sxs-lookup"><span data-stu-id="cc11c-133">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="cc11c-134">Ces entrées par défaut sont utilisées dans des écrans d'en-tête de journal, et le compte de contrepartie dans l'écran d'en-tête de journal est utilisé comme entrée par défaut sur la pages de N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="cc11c-134">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="cc11c-135">Les comptes par défaut de la page <strong>Noms de journal </strong>sont utilisés uniquement si les comptes par défaut ne sont pas paramétrés pour le compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="cc11c-135">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="cc11c-136">Utilisez cette option pour paramétrer des comptes par défaut à utiliser lorsqu'un compte de contrepartie par défaut du fournisseur n'est pas affecté.</span><span class="sxs-lookup"><span data-stu-id="cc11c-136">Use this option to set up default accounts that are used when a default vendor offset account isn&#39;t assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cc11c-137"><strong>En-tête de journal</strong> – Paramétrez un compte de contrepartie par défaut pour un journal à utiliser comme entrée par défaut dans les pages de N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="cc11c-137"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="cc11c-138">Notez que vous ne pouvez pas spécifier de comptes de contrepartie par défaut sur l'en-tête de journal si le type de journal des noms de journal est <strong>Registre des factures</strong> ou <strong>Approbation</strong>.</span><span class="sxs-lookup"><span data-stu-id="cc11c-138">Note that you can&#39;t specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="cc11c-139">Entrées de journal dans le journal</span><span class="sxs-lookup"><span data-stu-id="cc11c-139">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="cc11c-140">Le compte de contrepartie par défaut pour un journal est utilisé comme entrée par défaut sur les pages de N° document de journal.</span><span class="sxs-lookup"><span data-stu-id="cc11c-140">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="cc11c-141">Utilisez cette option pour accélérer la saisie des données si la plupart des entrées d'un journal ont le même compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="cc11c-141">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>






