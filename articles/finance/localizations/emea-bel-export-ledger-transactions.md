---
title: Exporter les écritures comptables
description: Cette rubrique donne des informations sur l'exportation des soldes de compte général dans un fichier texte brut (ASCII) au format .CED pour la Belgique.
author: anasyash
manager: AnnBe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportExtraFieldsBE
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 273103
ms.search.region: Belgium
ms.author: roschlom
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.openlocfilehash: 032677d434e847920fa837287df11df036ab5aa9
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981856"
---
# <a name="export-ledger-transactions"></a><span data-ttu-id="398fd-103">Exporter les écritures comptables</span><span class="sxs-lookup"><span data-stu-id="398fd-103">Export ledger transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="398fd-104">La fonctionnalité décrite dans cette rubrique permet d'exporter le solde total de chaque compte général pour une période spécifique dans un fichier texte brut (ASCII) au format .CED.</span><span class="sxs-lookup"><span data-stu-id="398fd-104">The feature described in this topic is used to export the total balance of each ledger account for a specific period to a plain text (ASCII) file in .CED format.</span></span> <span data-ttu-id="398fd-105">Vous pouvez ensuite importer le fichier généré dans un logiciel tiers pour créer un état comptable en fonction des exigences spécifiques au pays/à la région.</span><span class="sxs-lookup"><span data-stu-id="398fd-105">You can then import the generated file into third-party software to create an accounting report according to country/region-specific requirements.</span></span>

<span data-ttu-id="398fd-106">Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en Belgique.</span><span class="sxs-lookup"><span data-stu-id="398fd-106">This functionality is available for legal entities that have their primary address in Belgium.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="398fd-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="398fd-107">Prerequisites</span></span>

### <a name="create-posting-journals"></a><span data-ttu-id="398fd-108">Créer des journaux de validation</span><span class="sxs-lookup"><span data-stu-id="398fd-108">Create posting journals</span></span>

1. <span data-ttu-id="398fd-109">Allez dans **Comptabilité** \> **Paramétrage du journal** \> **Journaux de validation**.</span><span class="sxs-lookup"><span data-stu-id="398fd-109">Go to **General ledger** \> **Journal setup** \> **Posting journals**.</span></span>
2. <span data-ttu-id="398fd-110">Sur la page **Paramétrage du journal**, sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="398fd-110">On the **Journal setup** page, select **Create**.</span></span> <span data-ttu-id="398fd-111">Les journaux de validation et les souches de numéros correspondantes sont créés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="398fd-111">Posting journals and corresponding number sequences are automatically created.</span></span>

## <a name="export-ledger-transactions-to-a-plain-text-file-in-ced-format"></a><span data-ttu-id="398fd-112">Exporter les écritures comptables dans un fichier texte brut ASCII au format CED</span><span class="sxs-lookup"><span data-stu-id="398fd-112">Export ledger transactions to a plain text file in CED format</span></span>

1. <span data-ttu-id="398fd-113">Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), dans la bibliothèque d'actifs partagés, téléchargez les dernières versions des configurations d'états électroniques pour le format d'état suivant :</span><span class="sxs-lookup"><span data-stu-id="398fd-113">In [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), in the Shared asset library, download the latest versions of the Electronic reporting (ER) configurations for the following report format:</span></span>

    - <span data-ttu-id="398fd-114">Format d'exportation des écritures comptables (BE)</span><span class="sxs-lookup"><span data-stu-id="398fd-114">Ledger transaction export format (BE)</span></span>

    <span data-ttu-id="398fd-115">Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](https://docs.microsoft.com/dynamics365/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)</span><span class="sxs-lookup"><span data-stu-id="398fd-115">For more information, see [Download Electronic reporting configurations from Lifecycle Services](https://docs.microsoft.com/dynamics365/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span></span>

2. <span data-ttu-id="398fd-116">Dans Dynamics 365 Finance, allez dans **Comptabilité** \> **Tâches périodiques** \> **Exporter les écritures comptables**.</span><span class="sxs-lookup"><span data-stu-id="398fd-116">In Dynamics 365 Finance, go to **General ledger** \> **Periodic tasks** \> **Export ledger transactions**.</span></span>
3. <span data-ttu-id="398fd-117">Dans la boîte de dialogue **Exporter les écritures comptables dans un fichier ASCII au format CED**, dans le champ **Mappage de format**, sélectionnez le format **Format d'exportation des écritures comptables (BE)** que vous venez de télécharger, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="398fd-117">In the **Export ledger transactions to an ASCII file in CED format** dialog box, in the **Format mapping** field, select the **Ledger transaction export format (BE)** format that you just downloaded, and then select **OK**.</span></span>
4. <span data-ttu-id="398fd-118">Dans la boîte de dialogue **Paramètres des états électroniques**, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="398fd-118">In the **Electronic report parameters** dialog box, set the following fields.</span></span>

| <span data-ttu-id="398fd-119">**Champ**</span><span class="sxs-lookup"><span data-stu-id="398fd-119">**Field**</span></span>          | <span data-ttu-id="398fd-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="398fd-120">**Description**</span></span>                                                             |
|--------------------|-----------------------------------------------------------------------------|
| <span data-ttu-id="398fd-121">Date de début</span><span class="sxs-lookup"><span data-stu-id="398fd-121">From date</span></span>          | <span data-ttu-id="398fd-122">Entrez le premier jour de la période de déclaration.</span><span class="sxs-lookup"><span data-stu-id="398fd-122">Enter the first day of the reporting period.</span></span>                                |
| <span data-ttu-id="398fd-123">Au</span><span class="sxs-lookup"><span data-stu-id="398fd-123">To date</span></span>            | <span data-ttu-id="398fd-124">Entrez le dernier jour de la période de déclaration.</span><span class="sxs-lookup"><span data-stu-id="398fd-124">Enter the last day of the reporting period.</span></span>                                 |
| <span data-ttu-id="398fd-125">Déclaration en euros</span><span class="sxs-lookup"><span data-stu-id="398fd-125">Reporting in euros</span></span> | <span data-ttu-id="398fd-126">Définissez cette option sur **Oui** si la société utilise une devise autre que l'euro.</span><span class="sxs-lookup"><span data-stu-id="398fd-126">Set this option to **Yes** if the company uses a currency other than euros.</span></span> |

5. <span data-ttu-id="398fd-127">Cliquez sur **OK** pour générer et télécharger le fichier .txt.</span><span class="sxs-lookup"><span data-stu-id="398fd-127">Select **OK** to generate and download the .txt file.</span></span>

    <span data-ttu-id="398fd-128">Par exemple, vous validez les écritures comptables suivantes dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="398fd-128">For example, you post the following ledger transactions in the DEMF company.</span></span>

| <span data-ttu-id="398fd-129">**Date**</span><span class="sxs-lookup"><span data-stu-id="398fd-129">**Date**</span></span>        | <span data-ttu-id="398fd-130">**Type de transaction**</span><span class="sxs-lookup"><span data-stu-id="398fd-130">**Transaction type**</span></span> | <span data-ttu-id="398fd-131">**Compte principal**</span><span class="sxs-lookup"><span data-stu-id="398fd-131">**Main account**</span></span>          | <span data-ttu-id="398fd-132">**Compte de contrepartie**</span><span class="sxs-lookup"><span data-stu-id="398fd-132">**Offset account**</span></span>        | <span data-ttu-id="398fd-133">**Montant net**</span><span class="sxs-lookup"><span data-stu-id="398fd-133">**Amount net**</span></span> | <span data-ttu-id="398fd-134">**Montant de la TVA**</span><span class="sxs-lookup"><span data-stu-id="398fd-134">**VAT amount**</span></span> | <span data-ttu-id="398fd-135">**Code taxe**</span><span class="sxs-lookup"><span data-stu-id="398fd-135">**Sales tax code**</span></span> |
|-----------------|----------------------|---------------------------|---------------------------|----------------|----------------|--------------------|
| <span data-ttu-id="398fd-136">1 janvier 2020</span><span class="sxs-lookup"><span data-stu-id="398fd-136">January 1, 2020</span></span> | <span data-ttu-id="398fd-137">Facture client</span><span class="sxs-lookup"><span data-stu-id="398fd-137">Customer invoice</span></span>     | <span data-ttu-id="398fd-138">110110 – Compte bancaire en USD</span><span class="sxs-lookup"><span data-stu-id="398fd-138">110110 – Bank account USD</span></span> |                           | <span data-ttu-id="398fd-139">1 000</span><span class="sxs-lookup"><span data-stu-id="398fd-139">1,000</span></span>          | <span data-ttu-id="398fd-140">190</span><span class="sxs-lookup"><span data-stu-id="398fd-140">190</span></span>            | <span data-ttu-id="398fd-141">TVA19</span><span class="sxs-lookup"><span data-stu-id="398fd-141">VAT19</span></span>              |
| <span data-ttu-id="398fd-142">1 janvier 2020</span><span class="sxs-lookup"><span data-stu-id="398fd-142">January 1, 2020</span></span> | <span data-ttu-id="398fd-143">Facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="398fd-143">Vendor invoice</span></span>       |                           | <span data-ttu-id="398fd-144">110120 – Compte bancaire en CNY</span><span class="sxs-lookup"><span data-stu-id="398fd-144">110120 – Bank account CNY</span></span> | <span data-ttu-id="398fd-145">1,095</span><span class="sxs-lookup"><span data-stu-id="398fd-145">1,095</span></span>          | <span data-ttu-id="398fd-146">76.65</span><span class="sxs-lookup"><span data-stu-id="398fd-146">76.65</span></span>          | <span data-ttu-id="398fd-147">EU7</span><span class="sxs-lookup"><span data-stu-id="398fd-147">EU7</span></span>                |
| <span data-ttu-id="398fd-148">1 janvier 2020</span><span class="sxs-lookup"><span data-stu-id="398fd-148">January 1, 2020</span></span> | <span data-ttu-id="398fd-149">Facture client</span><span class="sxs-lookup"><span data-stu-id="398fd-149">Customer invoice</span></span>     | <span data-ttu-id="398fd-150">110115 – Compte bancaire en CAD</span><span class="sxs-lookup"><span data-stu-id="398fd-150">110115 – Bank account CAD</span></span> |                           | <span data-ttu-id="398fd-151">800</span><span class="sxs-lookup"><span data-stu-id="398fd-151">800</span></span>            | <span data-ttu-id="398fd-152">0</span><span class="sxs-lookup"><span data-stu-id="398fd-152">0</span></span>              | <span data-ttu-id="398fd-153">EUS</span><span class="sxs-lookup"><span data-stu-id="398fd-153">EUS</span></span>                |

<span data-ttu-id="398fd-154">Dans ce cas, le fichier généré contient les données suivantes.</span><span class="sxs-lookup"><span data-stu-id="398fd-154">In this case, the file that is generated contains the following data.</span></span>

![Données des écritures comptables](media/1_Export_ledger_transactions.png)

<span data-ttu-id="398fd-156">Voici une explication des colonnes de ce fichier :</span><span class="sxs-lookup"><span data-stu-id="398fd-156">Here is an explanation of the columns in this file:</span></span>

- <span data-ttu-id="398fd-157">La première colonne affiche le code compte général.</span><span class="sxs-lookup"><span data-stu-id="398fd-157">The first column shows the ledger account code.</span></span>
- <span data-ttu-id="398fd-158">La deuxième colonne affiche le solde débiteur du compte général.</span><span class="sxs-lookup"><span data-stu-id="398fd-158">The second column shows the debit balance on the ledger account.</span></span>
- <span data-ttu-id="398fd-159">La troisième colonne affiche le solde créditeur du compte général.</span><span class="sxs-lookup"><span data-stu-id="398fd-159">The third column shows the credit balance on the ledger account.</span></span>
- <span data-ttu-id="398fd-160">La quatrième colonne affiche le nom du compte général.</span><span class="sxs-lookup"><span data-stu-id="398fd-160">The fourth column shows the name of the ledger account.</span></span>

> [!NOTE]
> <span data-ttu-id="398fd-161">Pour valider les écritures comptables pour les factures client, allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.</span><span class="sxs-lookup"><span data-stu-id="398fd-161">To post ledger transactions for customer invoices, go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span> <span data-ttu-id="398fd-162">Pour les factures fournisseur, allez dans **Comptabilité fournisseur** \> **Factures** \> **Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="398fd-162">For vendor invoices, go to **Accounts payable** \> **Invoices** \> **Invoice journal**.</span></span>
