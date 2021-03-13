---
title: Références aux factures d'origine dans les notes de crédit
description: Cette rubrique explique comment configurer et imprimer les numéros de facture d'origine dans les notes de crédit associées.
author: ilkond
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 673288f04b33aa2a578f9e2e7913dbe7ac309644
ms.sourcegitcommit: 7cdec5469ff0da145ac4e01caf3287d0627ae2dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5100000"
---
# <a name="references-to-original-invoices-in-credit-notes"></a><span data-ttu-id="49048-103">Références aux factures d'origine dans les notes de crédit</span><span class="sxs-lookup"><span data-stu-id="49048-103">References to original invoices in credit notes</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="49048-104">Dans certains pays et certaines régions, il existe une obligation légale selon laquelle les notes de crédit imprimées incluent des références aux factures originales.</span><span class="sxs-lookup"><span data-stu-id="49048-104">In some countries and regions, there is a legal requirement that printed credit notes include references to the original invoices.</span></span> <span data-ttu-id="49048-105">Cette rubrique explique comment configurer et imprimer les numéros de facture d'origine dans les notes de crédit associées.</span><span class="sxs-lookup"><span data-stu-id="49048-105">This topic explains how to set up and print the original invoice numbers in related credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="49048-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="49048-106">Prerequisites</span></span>

- <span data-ttu-id="49048-107">Dans l'espace de travail **Gestion des fonctionnalités**, activez la fonction **Mise en page de la facturation de crédit aux états des facture client et de projet**.</span><span class="sxs-lookup"><span data-stu-id="49048-107">In the **Feature management** workspace, turn on the **Credit invoicing layout for sales and project invoice reports** feature.</span></span> <span data-ttu-id="49048-108">Pour plus d'informations, voir [Vue d'ensemble de la gestion des fonctionnalités](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="49048-108">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="49048-109">Les formats imprimables des documents requis doivent être configurés dans Gestion de l'impression.</span><span class="sxs-lookup"><span data-stu-id="49048-109">The printable formats of the required documents must be configured in Print management.</span></span>

<span data-ttu-id="49048-110">La fonctionnalité décrite dans cette rubrique s'applique aux documents suivants :</span><span class="sxs-lookup"><span data-stu-id="49048-110">The functionality that is described in this topic applies to the following documents:</span></span>

<span data-ttu-id="49048-111">**Comptabilité client**</span><span class="sxs-lookup"><span data-stu-id="49048-111">**Accounts receivable**</span></span>

- <span data-ttu-id="49048-112">Avoir financier</span><span class="sxs-lookup"><span data-stu-id="49048-112">Free text credit note</span></span>
- <span data-ttu-id="49048-113">Avoir du client</span><span class="sxs-lookup"><span data-stu-id="49048-113">Customer credit note</span></span>

<span data-ttu-id="49048-114">**Gestion et comptabilité des projets**</span><span class="sxs-lookup"><span data-stu-id="49048-114">**Project management and accounting**</span></span>

- <span data-ttu-id="49048-115">Avoir de projet</span><span class="sxs-lookup"><span data-stu-id="49048-115">Project credit note</span></span>

## <a name="configure-accounts-receivable-parameters"></a><span data-ttu-id="49048-116">Configurer les paramètres de la comptabilité client</span><span class="sxs-lookup"><span data-stu-id="49048-116">Configure Accounts receivable parameters</span></span>

<span data-ttu-id="49048-117">Suivez ces étapes pour définir le paramètre qui contrôle si les références aux factures d'origine sont imprimées dans les notes de crédit associées.</span><span class="sxs-lookup"><span data-stu-id="49048-117">Follow these steps to set the parameter that controls whether references to the original invoices are printed in related credit notes.</span></span>

1. <span data-ttu-id="49048-118">Accédez à **Comptabilité client** \> **Configuration** \> **Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="49048-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="49048-119">Sur l'onglet **Mises à jour**, sur le raccourci **Facture**, définissez l'option **Appliquer la mise en page de la facturation de crédit aux états des facture client et de projet** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="49048-119">On the **Updates** tab, on the **Invoice** FastTab, set the **Apply the credit invoicing layout into sales and project invoice reports** option to **Yes**.</span></span>

![Configuration des paramètres de la comptabilité client](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a><span data-ttu-id="49048-121">Définir des références aux factures originales</span><span class="sxs-lookup"><span data-stu-id="49048-121">Define references to original invoices</span></span>

<span data-ttu-id="49048-122">Utilisez les procédures suivantes pour définir des références aux factures originales, en fonction du type de document.</span><span class="sxs-lookup"><span data-stu-id="49048-122">Use the following procedures to define references to original invoices, based on the document type.</span></span>

### <a name="free-text-credit-note"></a><span data-ttu-id="49048-123">Avoir financier</span><span class="sxs-lookup"><span data-stu-id="49048-123">Free text credit note</span></span>

1. <span data-ttu-id="49048-124">Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.</span><span class="sxs-lookup"><span data-stu-id="49048-124">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
2. <span data-ttu-id="49048-125">Créez une nouvelle note de crédit ou sélectionnez une note de crédit existante.</span><span class="sxs-lookup"><span data-stu-id="49048-125">Create a new credit note, or select an existing credit note.</span></span>
3. <span data-ttu-id="49048-126">Ouvrez la facture.</span><span class="sxs-lookup"><span data-stu-id="49048-126">Open the invoice.</span></span>
4. <span data-ttu-id="49048-127">Dans le volet Actions, sous l'onglet **Facture**, dans le groupe **Fonctions**, sélectionnez **Facturation de crédit**.</span><span class="sxs-lookup"><span data-stu-id="49048-127">On the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>
5. <span data-ttu-id="49048-128">Saisissez la référence à la facture d'origine et sélectionnez le motif de la correction.</span><span class="sxs-lookup"><span data-stu-id="49048-128">Enter the reference to the original invoice, and select the reason for the correction.</span></span>

![Définition de la référence pour une facture en texte libre](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a><span data-ttu-id="49048-130">Avoir du client</span><span class="sxs-lookup"><span data-stu-id="49048-130">Customer credit note</span></span>

1. <span data-ttu-id="49048-131">Allez dans **Comptabilité client** \> **Commandes** \> **Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="49048-131">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="49048-132">Sélectionnez et ouvrez la commande client facturée qui doit être corrigée.</span><span class="sxs-lookup"><span data-stu-id="49048-132">Select and open the invoiced sales order that must be corrected.</span></span>
3. <span data-ttu-id="49048-133">Dans le volet Actions, sous l'onglet **Vendre**, dans le groupe **Avoir**, sélectionnez **Avoir**.</span><span class="sxs-lookup"><span data-stu-id="49048-133">On the Action Pane, on the **Sell** tab, in the **Credit note** group, select **Credit note**.</span></span>
4. <span data-ttu-id="49048-134">Entrez le motif de la correction.</span><span class="sxs-lookup"><span data-stu-id="49048-134">Enter the reason for the correction.</span></span> <span data-ttu-id="49048-135">La référence à la facture originale est automatiquement établie.</span><span class="sxs-lookup"><span data-stu-id="49048-135">The reference to the original invoice is automatically established.</span></span>

![Définition de la référence d'une commande client](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a><span data-ttu-id="49048-137">Avoir de projet</span><span class="sxs-lookup"><span data-stu-id="49048-137">Project credit note</span></span>

1. <span data-ttu-id="49048-138">Accédez à **Gestion et comptabilité des projets** \> **Factures de projets** \> **Factures de projet**.</span><span class="sxs-lookup"><span data-stu-id="49048-138">Go to **Project management and accounting** \> **Project invoices** \> **Project invoices**.</span></span>
2. <span data-ttu-id="49048-139">Sélectionnez et ouvrez la facture de projet qui doit être corrigée.</span><span class="sxs-lookup"><span data-stu-id="49048-139">Select and open the project invoice that must be corrected.</span></span>
3. <span data-ttu-id="49048-140">Dans le volet Actions, sous l'onglet **Facture de projet**, dans le groupe **Fonctions**, sélectionnez **Sélectionner pour l'avoir**.</span><span class="sxs-lookup"><span data-stu-id="49048-140">On the Action Pane, on the **Project invoice** tab, in the **Functions** group, select **Select for credit note**.</span></span>
4. <span data-ttu-id="49048-141">Sélectionnez **Facturation de crédit**.</span><span class="sxs-lookup"><span data-stu-id="49048-141">Select **Credit invoicing**.</span></span>
5. <span data-ttu-id="49048-142">Entrez le motif de la correction.</span><span class="sxs-lookup"><span data-stu-id="49048-142">Enter the reason for the correction.</span></span> <span data-ttu-id="49048-143">La référence à la facture originale est automatiquement établie.</span><span class="sxs-lookup"><span data-stu-id="49048-143">The reference to the original invoice is automatically established.</span></span>

![Définition de la référence pour une facture de projet](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a><span data-ttu-id="49048-145">Impression d'avoirs</span><span class="sxs-lookup"><span data-stu-id="49048-145">Printing credit notes</span></span>

<span data-ttu-id="49048-146">Lorsque vous imprimez du texte libre, des notes de crédit client et projet, elles incluront la référence à la facture d'origine et le motif de la correction.</span><span class="sxs-lookup"><span data-stu-id="49048-146">When you print free text, customer, and project credit notes, they will include the reference to the original invoice and the correction reason.</span></span>

![Note de crédit imprimée](media/credit-note-FTI.jpg)

> [!NOTE]
> <span data-ttu-id="49048-148">Assurez-vous que les formats imprimables des documents sont correctement configurés, en supposant que les références aux factures d'origine soient imprimées.</span><span class="sxs-lookup"><span data-stu-id="49048-148">Make sure that the printable formats of the documents are correctly configured, on the assumption that references to original invoices will be printed.</span></span>
