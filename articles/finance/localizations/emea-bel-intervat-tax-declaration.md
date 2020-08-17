---
title: Déclaration de taxe INTERVAT
description: Cette rubrique fournit les informations spécifiques au pays/à la région pour la configuration et la création de la déclaration de taxe INTERVAT pour les entités juridiques en Belgique uniquement.
author: anasyash
manager: AnnBe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxIntervat
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 273023
ms.search.region: Belgium
ms.author: v-oloski
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.openlocfilehash: ac59959451bf4267d1347db29d3326605c9121e6
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621339"
---
# <a name="intervat-tax-declaration"></a><span data-ttu-id="366ed-103">Déclaration de taxe INTERVAT</span><span class="sxs-lookup"><span data-stu-id="366ed-103">INTERVAT tax declaration</span></span>

[!include [banner](../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="366ed-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="366ed-104">Overview</span></span>

<span data-ttu-id="366ed-105">Cette rubrique fournit les informations spécifiques au pays/à la région pour la configuration et la création de la déclaration de taxe INTERVAT pour les entités juridiques en Belgique.</span><span class="sxs-lookup"><span data-stu-id="366ed-105">This topic provides country/region-specific information about how to set up and create the INTERVAT tax declaration for legal entities in Belgium.</span></span>

<span data-ttu-id="366ed-106">Vous pouvez créer la déclaration de taxe INTERVAT sous la forme d’un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="366ed-106">You can create the INTERVAT tax declaration as an XML file.</span></span> <span data-ttu-id="366ed-107">Vous pouvez également prévisualiser les montants de la déclaration de taxe sur la valeur ajoutée (TVA) dans un format imprimable.</span><span class="sxs-lookup"><span data-stu-id="366ed-107">You can also preview the amounts of the value-added tax (VAT) declaration in a printable format.</span></span>

<span data-ttu-id="366ed-108">La déclaration INTERVAT que vous créez comprend les transactions fiscales de la période en cours.</span><span class="sxs-lookup"><span data-stu-id="366ed-108">The INTERVAT declaration that you create includes tax transactions from the current period.</span></span> <span data-ttu-id="366ed-109">Elle peut également comprendre des corrections de la période précédente, si une transaction a été validée dans la période précédente après la clôture de cette période.</span><span class="sxs-lookup"><span data-stu-id="366ed-109">It can also include corrections from the previous period, if a transaction was posted in the previous period after that period was closed.</span></span>

<span data-ttu-id="366ed-110">Vous pouvez entrer des informations supplémentaires pour la déclaration et corriger manuellement les données sur la page **Zones de déclaration de taxe supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="366ed-110">You can enter additional information for the declaration and manually correct data on the **Additional sales tax report boxes** page.</span></span> <span data-ttu-id="366ed-111">La correction manuelle peut être nécessaire si, par exemple, vous ne pouvez pas imprimer le montant du code de déclaration dans la déclaration INTERVAT, car le montant est négatif.</span><span class="sxs-lookup"><span data-stu-id="366ed-111">Manual correction might be required if, for example, you can't print the amount of the reporting code in the INTERVAT declaration because the amount is negative.</span></span> <span data-ttu-id="366ed-112">Les montants négatifs doivent être déduits de la prochaine déclaration de TVA et cette tâche doit être effectuée manuellement à l’aide de corrections.</span><span class="sxs-lookup"><span data-stu-id="366ed-112">Negative amounts must be deducted from the next VAT declaration, and this task must be completed manually by using corrections.</span></span> <span data-ttu-id="366ed-113">Avant de pouvoir indiquer le montant corrigé, vous devez indiquer quels codes de déclaration de taxe autorisent les corrections.</span><span class="sxs-lookup"><span data-stu-id="366ed-113">Before you can indicate the corrected amount, you must indicate which sales tax reporting codes allow for corrections.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="366ed-114">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="366ed-114">Prerequisites</span></span>
<span data-ttu-id="366ed-115">Les conditions préalables suivantes doivent être configurées avant de commencer à utiliser la déclaration de taxe INTERVAT :</span><span class="sxs-lookup"><span data-stu-id="366ed-115">The following prerequisites must be set up before you begin to work with the INTERVAT tax declaration:</span></span>

-   <span data-ttu-id="366ed-116">Entité juridique</span><span class="sxs-lookup"><span data-stu-id="366ed-116">Legal entity</span></span>
-   <span data-ttu-id="366ed-117">Numéro d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="366ed-117">Registration number</span></span>
-   <span data-ttu-id="366ed-118">Informations sur le contact</span><span class="sxs-lookup"><span data-stu-id="366ed-118">Contact information</span></span>
-   <span data-ttu-id="366ed-119">Souches de numéros</span><span class="sxs-lookup"><span data-stu-id="366ed-119">Number sequences</span></span>
-   <span data-ttu-id="366ed-120">Journal de validation</span><span class="sxs-lookup"><span data-stu-id="366ed-120">Posting journal</span></span>
-   <span data-ttu-id="366ed-121">Administrations fiscales</span><span class="sxs-lookup"><span data-stu-id="366ed-121">Sales tax authorities</span></span>
-   <span data-ttu-id="366ed-122">Codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="366ed-122">Sales tax reporting codes</span></span>
-   <span data-ttu-id="366ed-123">Codes taxe</span><span class="sxs-lookup"><span data-stu-id="366ed-123">Sales tax codes</span></span>
-   <span data-ttu-id="366ed-124">Numéro identifiant TVA</span><span class="sxs-lookup"><span data-stu-id="366ed-124">Tax exempt number</span></span>

### <a name="legal-entity"></a><span data-ttu-id="366ed-125">Entité juridique</span><span class="sxs-lookup"><span data-stu-id="366ed-125">Legal entity</span></span>

1.  <span data-ttu-id="366ed-126">Allez dans **Administration d’organisation** \> **Organisations** \> **Entités juridiques**, puis sélectionnez votre entité juridique.</span><span class="sxs-lookup"><span data-stu-id="366ed-126">Go to **Organization administration** \> **Organizations** \> **Legal entities**, and select your legal entity.</span></span>
2.  <span data-ttu-id="366ed-127">Dans l’organisateur **Adresses**, créez une adresse.</span><span class="sxs-lookup"><span data-stu-id="366ed-127">On the **Addresses** FastTab, create an address.</span></span>
3.  <span data-ttu-id="366ed-128">Dans le champ **Pays/région**, sélectionnez **Belgique**.</span><span class="sxs-lookup"><span data-stu-id="366ed-128">In the **Country/region** field, select **Belgium**.</span></span>
4.  <span data-ttu-id="366ed-129">Renseignez les autres composants d’adresse et marquez l’adresse comme **Principale**.</span><span class="sxs-lookup"><span data-stu-id="366ed-129">Fill in other address components, and mark the address as **Primary**.</span></span>
5.  <span data-ttu-id="366ed-130">Dans l’organisateur **Immatriculation fiscale**, dans le champ **Numéro d’identification fiscale**, spécifiez le numéro identifiant TVA de votre société.</span><span class="sxs-lookup"><span data-stu-id="366ed-130">On the **Tax registration** FastTab, in the **Tax registration number** field, specify the tax registration number for your company.</span></span>

### <a name="registration-number"></a><span data-ttu-id="366ed-131">Numéro d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="366ed-131">Registration number</span></span>

1.  <span data-ttu-id="366ed-132">Allez dans **Administration d’organisation** \> **Organisations** \> **Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="366ed-132">Go to **Organization administration** \> **Organizations** \> **Legal entities**.</span></span>
2.  <span data-ttu-id="366ed-133">Sélectionnez **ID enregistrement**, puis, dans l’onglet **ID enregistrement**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="366ed-133">Select **Registration IDs**, and then, on the **Registration ID** tab, select **Add**.</span></span>
3.  <span data-ttu-id="366ed-134">Dans le champ **Type d’enregistrement**, sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="366ed-134">In the **Registration type** field, select a value.</span></span>
4.  <span data-ttu-id="366ed-135">Dans le champ **Numéro d’enregistrement**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="366ed-135">In the **Registration number** field, enter a value.</span></span>
5.  <span data-ttu-id="366ed-136">Dans l’onglet **Général**, entrez une date d’effet.</span><span class="sxs-lookup"><span data-stu-id="366ed-136">On the **General** tab, enter an effective date.</span></span> <span data-ttu-id="366ed-137">Pour plus d’informations, voir [Numéro d’enregistrement](emea-registration-ids.md).</span><span class="sxs-lookup"><span data-stu-id="366ed-137">For more information, see [Registration number](emea-registration-ids.md).</span></span>

### <a name="contact-information"></a><span data-ttu-id="366ed-138">Informations sur le contact</span><span class="sxs-lookup"><span data-stu-id="366ed-138">Contact information</span></span>

1.  <span data-ttu-id="366ed-139">Allez dans **Administration d’organisation** \> **Organisations** \> **Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="366ed-139">Go to **Organization administration** \> **Organizations** \> **Legal entities**.</span></span>
2.  <span data-ttu-id="366ed-140">Dans l’onglet **Informations sur le contact**, ajoutez des lignes pour le numéro de téléphone et l’adresse e-mail et définissez-les sur **Principal**.</span><span class="sxs-lookup"><span data-stu-id="366ed-140">On the **Contact information** tab, add lines for the phone number and email address, and set them to **Primary**.</span></span>

### <a name="number-sequences"></a><span data-ttu-id="366ed-141">Souches de numéros</span><span class="sxs-lookup"><span data-stu-id="366ed-141">Number sequences</span></span>

1.  <span data-ttu-id="366ed-142">Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="366ed-142">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2.  <span data-ttu-id="366ed-143">Dans l’onglet **Souches de numéros**, définissez des souches de numéros pour les références **ID liste des ventes annuelles** et **ID INTERVAT**.</span><span class="sxs-lookup"><span data-stu-id="366ed-143">On the **Number sequences** tab, set up number sequences for the **Annual sales list ID** and **INTERVAT ID** references.</span></span>

### <a name="posting-journal"></a><span data-ttu-id="366ed-144">Journal de validation</span><span class="sxs-lookup"><span data-stu-id="366ed-144">Posting journal</span></span>

1.  <span data-ttu-id="366ed-145">Allez dans **Comptabilité** \> **Paramétrage du journal** \> **Journaux de validation**.</span><span class="sxs-lookup"><span data-stu-id="366ed-145">Go to **General ledger** \> **Journal setup** \> **Posting journals**.</span></span>
2.  <span data-ttu-id="366ed-146">Sur la page **Paramétrage du journal**, sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="366ed-146">On the **Journal setup** page, select **Create**.</span></span> <span data-ttu-id="366ed-147">La souche de N° documents est créée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="366ed-147">The voucher series is automatically created.</span></span>

### <a name="sales-tax-authorities"></a><span data-ttu-id="366ed-148">Administrations fiscales</span><span class="sxs-lookup"><span data-stu-id="366ed-148">Sales tax authorities</span></span>

1.  <span data-ttu-id="366ed-149">Allez dans **Taxe** \> **Taxes indirectes** \> **Administrations fiscales**.</span><span class="sxs-lookup"><span data-stu-id="366ed-149">Go to **Tax** \> **Indirect taxes** \> **Sales tax authorities**.</span></span>
2.  <span data-ttu-id="366ed-150">Vérifiez que le champ **Présentation d’état** est défini sur **Présentation d’état belge**.</span><span class="sxs-lookup"><span data-stu-id="366ed-150">Verify that the **Report layout** field is set to **Belgium report layout**.</span></span>

### <a name="sales-tax-reporting-codes"></a><span data-ttu-id="366ed-151">Codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="366ed-151">Sales tax reporting codes</span></span>

-   <span data-ttu-id="366ed-152">Allez dans **Taxe** \> **Paramétrage** \> **Taxe** \> **Codes déclaration de taxe** et créez des codes déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-152">Go to **Tax** \> **Setup** \> **Sales tax** \> **Sales tax reporting codes**, and create new sales tax reporting codes.</span></span>

<span data-ttu-id="366ed-153">Si la case à cocher **Correction de taxe** est activée pour un code déclaration de taxe, ce code est disponible à la sélection dans la page **Zones de déclaration de taxe supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="366ed-153">If the **Sales tax correction** check box is selected for a sales tax reporting code, that code is available for selection on the **Additional sales tax report boxes** page.</span></span>

<span data-ttu-id="366ed-154">Des exemples de code déclaration de taxe sont fournis dans la section [Paramétrer des codes déclaration de taxe](#set-up-sales-tax-reporting-codes) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="366ed-154">Examples of sales tax reporting code are provided in the [Set up sales tax reporting codes](#set-up-sales-tax-reporting-codes) section later in this topic.</span></span>

### <a name="sales-tax-codes"></a><span data-ttu-id="366ed-155">Codes taxe</span><span class="sxs-lookup"><span data-stu-id="366ed-155">Sales tax codes</span></span>

1.  <span data-ttu-id="366ed-156">Allez dans **Taxe** \> **Taxes indirectes** \> **Codes taxe**.</span><span class="sxs-lookup"><span data-stu-id="366ed-156">Go to **Tax** \> **Indirect taxes** \> **Sales tax codes**.</span></span>
2.  <span data-ttu-id="366ed-157">Ajoutez ou sélectionnez des informations dans les champs des onglets **État** et **État – avoir**.</span><span class="sxs-lookup"><span data-stu-id="366ed-157">Add or select information in the fields on the **Report** and **Report – credit note** tabs.</span></span>
3.  <span data-ttu-id="366ed-158">Sélectionnez les valeurs requises dans la grille **Codes déclaration de taxe**.</span><span class="sxs-lookup"><span data-stu-id="366ed-158">Select the required values in the **Sales tax reporting codes** grid.</span></span>

### <a name="tax-exempt-number"></a><span data-ttu-id="366ed-159">Numéro identifiant TVA</span><span class="sxs-lookup"><span data-stu-id="366ed-159">Tax exempt number</span></span>

1.  <span data-ttu-id="366ed-160">Allez dans **Taxe** \> **Paramétrage** \> **Taxe** \> **Numéros identifiant TVA**.</span><span class="sxs-lookup"><span data-stu-id="366ed-160">Go to **Tax** \> **Setup** \> **Sales tax** \> **Tax exempt numbers**.</span></span>
2.  <span data-ttu-id="366ed-161">Pour chaque numéro identifiant TVA, créez un enregistrement comprenant les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="366ed-161">For each tax-exempt number, create a record that includes the followinginformation:</span></span>

    -   <span data-ttu-id="366ed-162">Dans le champ **Pays/région**, sélectionnez l’enregistrement de taxe de la contrepartie.</span><span class="sxs-lookup"><span data-stu-id="366ed-162">In the **Country/region** field, select the tax registration of the counterparty.</span></span>
    -   <span data-ttu-id="366ed-163">Dans le champ **Numéro identifiant TVA**, entrez le numéro identifiant TVA de la contrepartie.</span><span class="sxs-lookup"><span data-stu-id="366ed-163">In the **Tax exempt number** field, enter the tax-exempt number of the counterparty.</span></span>
    -   <span data-ttu-id="366ed-164">Dans le champ **Nom de la société**, entrez le nom de la contrepartie.</span><span class="sxs-lookup"><span data-stu-id="366ed-164">In the **Company name** field, enter the name of the counterparty.</span></span>

<span data-ttu-id="366ed-165">Pour plus d’informations sur le paramétrage des déclarations de fin, voir [Déclarations de TVA pour l’Europe](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/localizations/emea-vat-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="366ed-165">For more information about how to set up the VAT statement, see [VAT reporting for Europe](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/localizations/emea-vat-reporting.md).</span></span>

## <a name="settings"></a><span data-ttu-id="366ed-166">Paramètres</span><span class="sxs-lookup"><span data-stu-id="366ed-166">Settings</span></span>

### <a name="set-up-intervat"></a><span data-ttu-id="366ed-167">Paramétrer INTERVAT</span><span class="sxs-lookup"><span data-stu-id="366ed-167">Set up INTERVAT</span></span>

<span data-ttu-id="366ed-168">Créez des lignes sur la page **Paramétrage INTERVAT** (**Taxe \> Paramétrage \> Taxe \> Paramétrage INTERVAT**).</span><span class="sxs-lookup"><span data-stu-id="366ed-168">Create lines on the **INTERVAT setup** page (**Tax \> Setup \> Sales tax \> INTERVAT setup**).</span></span> <span data-ttu-id="366ed-169">Les informations que vous entrez dans cette page sont utilisées lorsque vous sélectionnez **Ouvrir le site web** sur la page **Déclaration de taxe INTERVAT**.</span><span class="sxs-lookup"><span data-stu-id="366ed-169">The information that you enter on this page is used when you select **Open Web site** on the **INTERVAT tax declaration** page.</span></span> <span data-ttu-id="366ed-170">Vous devez créer un élément pour chaque langue.</span><span class="sxs-lookup"><span data-stu-id="366ed-170">You should create an element for each language.</span></span> <span data-ttu-id="366ed-171">Définissez les champs suivants : **Langue**, **Description** et **URL**.</span><span class="sxs-lookup"><span data-stu-id="366ed-171">Set the following fields: **Language**, **Description**, and **URL**.</span></span>

![Page Paramétrage INTERVAT](media/1_Intervat_setup.png)

### <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="366ed-173">Paramétrer des codes déclaration de taxe</span><span class="sxs-lookup"><span data-stu-id="366ed-173">Set up sales tax reporting codes</span></span>

<span data-ttu-id="366ed-174">Pour plus d’informations sur le paramétrage des codes déclaration de taxe, voir [Paramétrer des codes déclaration de taxe](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/general-ledger/tasks/set-up-sales-tax-reporting-codes.md).</span><span class="sxs-lookup"><span data-stu-id="366ed-174">For information about how to set up sales tax reporting codes, see [Set up sales tax reporting codes](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/general-ledger/tasks/set-up-sales-tax-reporting-codes.md).</span></span>

<span data-ttu-id="366ed-175">Si les utilisateurs sont autorisés à corriger manuellement un code déclaration, activez la case à cocher **Corrections de taxe**.</span><span class="sxs-lookup"><span data-stu-id="366ed-175">If users are allowed to manually correct a reporting code, select the **Tax corrections** check box.</span></span> <span data-ttu-id="366ed-176">Le tableau suivant fournit un exemple de codes déclaration de taxe pour la Belgique.</span><span class="sxs-lookup"><span data-stu-id="366ed-176">The following table provides an example of sales tax reporting codes for Belgium.</span></span>

<table width="100%">
<thead>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-177"><strong>Code et zone correspondante dans la déclaration de TVA</strong></span><span class="sxs-lookup"><span data-stu-id="366ed-177"><strong>Code and corresponding box in the VAT declaration</strong></span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-178"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="366ed-178"><strong>Description</strong></span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-179"><strong>Base/taxe</strong></span><span class="sxs-lookup"><span data-stu-id="366ed-179"><strong>Base/tax</strong></span></span></p>
</td>
</tr>
</thead>
<tbody>
<tr>
<td colspan="3" width="100%">
<p style="text-align: center;"><span data-ttu-id="366ed-180"><strong>Section II. Sorties</strong></span><span class="sxs-lookup"><span data-stu-id="366ed-180"><strong>Section II. Outputs</strong></span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-181">100 (Zone 00)</span><span class="sxs-lookup"><span data-stu-id="366ed-181">100 (Box 00)</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-182">Ventes soumises à une réglementation spéciale.</span><span class="sxs-lookup"><span data-stu-id="366ed-182">Sales that are subject to a special regulation.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-183">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-183">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-184">01</span><span class="sxs-lookup"><span data-stu-id="366ed-184">01</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-185">Fournitures et services soumis au taux de taxe de 6 %.</span><span class="sxs-lookup"><span data-stu-id="366ed-185">Taxable supplies and services at a sales tax rate of 6 percent.</span></span></p>
<p><span data-ttu-id="366ed-186">Livraison d'un produit ou de transactions de service soumis au taux de taxe de 6 %.</span><span class="sxs-lookup"><span data-stu-id="366ed-186">The delivery of a product or service transactions at a sales tax rate of 6 percent.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-187">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-187">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-188">02</span><span class="sxs-lookup"><span data-stu-id="366ed-188">02</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-189">Fournitures et services soumis au taux de taxe de 12 %.</span><span class="sxs-lookup"><span data-stu-id="366ed-189">Taxable supplies and services at a sales tax rate of 12 percent.</span></span></p>
<p><span data-ttu-id="366ed-190">Livraison d'un produit ou de transactions de service soumis au taux de taxe de 12 %.</span><span class="sxs-lookup"><span data-stu-id="366ed-190">The delivery of a product or service transactions at a sales tax rate of 12 percent.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-191">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-191">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-192">03</span><span class="sxs-lookup"><span data-stu-id="366ed-192">03</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-193">Fournitures et services soumis au taux de taxe de 21 %.</span><span class="sxs-lookup"><span data-stu-id="366ed-193">Taxable supplies and services at a sales tax rate of 21 percent.</span></span></p>
<p><span data-ttu-id="366ed-194">Livraison d'un produit ou de transactions de service soumis au taux de taxe de 21 %.</span><span class="sxs-lookup"><span data-stu-id="366ed-194">The delivery of a product or service transactions at a sales tax rate of 21 percent.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-195">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-195">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-196">44</span><span class="sxs-lookup"><span data-stu-id="366ed-196">44</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-197">Services pour lesquels le partenaire contractuel doit la TVA étrangère.</span><span class="sxs-lookup"><span data-stu-id="366ed-197">Services that the contractual partner owes foreign VAT for.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-198">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-198">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-199">45</span><span class="sxs-lookup"><span data-stu-id="366ed-199">45</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-200">Chiffre d’affaires pour lequel le partenaire contractuel doit la TVA.</span><span class="sxs-lookup"><span data-stu-id="366ed-200">Turnover that the contractual partner owes VAT for.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-201">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-201">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-202">46</span><span class="sxs-lookup"><span data-stu-id="366ed-202">46</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-203">Approvisionnement intracommunautaire de marchandises et transactions similaires (expéditions).</span><span class="sxs-lookup"><span data-stu-id="366ed-203">Intra-community supply of goods and similar transactions (shipments).</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-204">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-204">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-205">47</span><span class="sxs-lookup"><span data-stu-id="366ed-205">47</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-206">Autres ventes détaxées et autres ventes générées à l’étranger.</span><span class="sxs-lookup"><span data-stu-id="366ed-206">Other tax-free sales and other sales that are generated abroad.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-207">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-207">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-208">48</span><span class="sxs-lookup"><span data-stu-id="366ed-208">48</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-209">Montant des avoirs émis et corrections négatives liées aux ventes des zones 44 et 46.</span><span class="sxs-lookup"><span data-stu-id="366ed-209">Amount of the issued credit notes, and negative corrections that are related to sales from boxes 44 and 46.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-210">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-210">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-211">49</span><span class="sxs-lookup"><span data-stu-id="366ed-211">49</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-212">Montant des crédits émis et ajustements négatifs liés aux autres zones de la section II, « Sorties ».</span><span class="sxs-lookup"><span data-stu-id="366ed-212">Amount of issued credits, and negative adjustments that are related to other boxes from section II, "Outputs."</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-213">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-213">Base</span></span></p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p style="text-align: center;"><span data-ttu-id="366ed-214"><strong>Section III. Entrées</strong></span><span class="sxs-lookup"><span data-stu-id="366ed-214"><strong>Section III. Inputs</strong></span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-215">81</span><span class="sxs-lookup"><span data-stu-id="366ed-215">81</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-216">Montant de tous les achats de biens, matières premières et consommables, et coûts d’acquisition associés.</span><span class="sxs-lookup"><span data-stu-id="366ed-216">Amount of all purchases of goods, raw materials, and consumables, and related acquisition costs.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-217">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-217">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-218">82</span><span class="sxs-lookup"><span data-stu-id="366ed-218">82</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-219">Montant de marchandises diverses et de services, peu importe s’ils sont soumis à la TVA.</span><span class="sxs-lookup"><span data-stu-id="366ed-219">Amount of miscellaneous goods and services, regardless of whether they are subject to VAT.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-220">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-220">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-221">83</span><span class="sxs-lookup"><span data-stu-id="366ed-221">83</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-222">Montant des achats de biens d’équipement, peu importe s’ils sont soumis à la TVA.</span><span class="sxs-lookup"><span data-stu-id="366ed-222">Amount of purchases of capital goods, regardless of whether they are subject to VAT.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-223">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-223">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-224">84</span><span class="sxs-lookup"><span data-stu-id="366ed-224">84</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-225">Montant des crédits reçus et ajustements négatifs liés aux ventes des zones 86 et 88.</span><span class="sxs-lookup"><span data-stu-id="366ed-225">Amount of credits received, and negative adjustments that are related to sales from boxes 86 and 88.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-226">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-226">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-227">8684</span><span class="sxs-lookup"><span data-stu-id="366ed-227">8684</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-228">Code de déclaration technique pour indiquer les montants des avoirs dans les zones 86 et 84.</span><span class="sxs-lookup"><span data-stu-id="366ed-228">Technical reporting code for showing credit note amounts in boxes 86 and 84.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-229">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-229">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-230">8884</span><span class="sxs-lookup"><span data-stu-id="366ed-230">8884</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-231">Code de déclaration technique pour indiquer les montants des avoirs dans les zones 88 et 84.</span><span class="sxs-lookup"><span data-stu-id="366ed-231">Technical reporting code for showing credit note amounts in boxes 88 and 84.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-232">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-232">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-233">85</span><span class="sxs-lookup"><span data-stu-id="366ed-233">85</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-234">Montant des crédits reçus et ajustements négatifs liés aux autres zones de la section III, « Entrées ».</span><span class="sxs-lookup"><span data-stu-id="366ed-234">Amount of credits received, and negative adjustments that are related to other boxes from section III, "Inputs."</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-235">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-235">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-236">8185</span><span class="sxs-lookup"><span data-stu-id="366ed-236">8185</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-237">Code de déclaration technique pour indiquer les montants des avoirs dans les zones 81 et 85.</span><span class="sxs-lookup"><span data-stu-id="366ed-237">Technical reporting code for showing credit note amounts in boxes 81 and 85.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-238">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-238">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-239">8285</span><span class="sxs-lookup"><span data-stu-id="366ed-239">8285</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-240">Code de déclaration technique pour indiquer les montants des avoirs dans les zones 82 et 85.</span><span class="sxs-lookup"><span data-stu-id="366ed-240">Technical reporting code for showing credit note amounts in boxes 82 and 85.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-241">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-241">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-242">8385</span><span class="sxs-lookup"><span data-stu-id="366ed-242">8385</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-243">Code de déclaration technique pour indiquer les montants des avoirs dans les zones 83 et 85.</span><span class="sxs-lookup"><span data-stu-id="366ed-243">Technical reporting code for showing credit note amounts in boxes 83 and 85.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-244">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-244">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-245">8785</span><span class="sxs-lookup"><span data-stu-id="366ed-245">8785</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-246">Code de déclaration technique pour indiquer les montants des avoirs dans les zones 87 et 85.</span><span class="sxs-lookup"><span data-stu-id="366ed-246">Technical reporting code for showing credit note amounts in boxes 87 and 85.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-247">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-247">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-248">86</span><span class="sxs-lookup"><span data-stu-id="366ed-248">86</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-249">Acquisitions intracommunautaires et transactions similaires.</span><span class="sxs-lookup"><span data-stu-id="366ed-249">Intra-community acquisitions and similar transactions.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-250">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-250">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-251">87</span><span class="sxs-lookup"><span data-stu-id="366ed-251">87</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-252">Autres réceptions pour lesquelles la personne qui est tenue de s’enregistrer doit la TVA.</span><span class="sxs-lookup"><span data-stu-id="366ed-252">Other receipts that the person who is liable to register owes VAT for.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-253">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-253">Base</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-254">88</span><span class="sxs-lookup"><span data-stu-id="366ed-254">88</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-255">Services intra-communautaires avec transfert de l’enquête.</span><span class="sxs-lookup"><span data-stu-id="366ed-255">Intra-community services with transfer of the survey.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-256">Base</span><span class="sxs-lookup"><span data-stu-id="366ed-256">Base</span></span></p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p style="text-align: center;"><span data-ttu-id="366ed-257"><strong>Section IV. Taxes à payer</strong></span><span class="sxs-lookup"><span data-stu-id="366ed-257"><strong>Section IV. Taxes payable</strong></span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-258">54</span><span class="sxs-lookup"><span data-stu-id="366ed-258">54</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-259">TVA collectée sur le chiffre d’affaires inclus dans les codes <strong>01</strong>, <strong>02</strong> et <strong>03</strong>.</span><span class="sxs-lookup"><span data-stu-id="366ed-259">VAT that is payable on the turnover that is included in codes <strong>01</strong>, <strong>02</strong>, and <strong>03</strong>.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-260">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-260">Tax</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-261">55</span><span class="sxs-lookup"><span data-stu-id="366ed-261">55</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-262">TVA collectée sur le chiffre d’affaires inclus dans les codes <strong>86</strong> et <strong>88</strong>.</span><span class="sxs-lookup"><span data-stu-id="366ed-262">VAT that is payable on the turnover that is included in codes <strong>86</strong> and <strong>88</strong>.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-263">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-263">Tax</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-264">56</span><span class="sxs-lookup"><span data-stu-id="366ed-264">56</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-265">TVA sur les ventes déclarées dans la zone 87, hors importations impliquant le transfert de l’enquête.</span><span class="sxs-lookup"><span data-stu-id="366ed-265">VAT on sales that are declared in box 87, excluding imports that involve relocation of the survey.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-266">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-266">Tax</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-267">57</span><span class="sxs-lookup"><span data-stu-id="366ed-267">57</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-268">TVA sur les importations impliquant le transfert de l’enquête.</span><span class="sxs-lookup"><span data-stu-id="366ed-268">VAT on imports that involve transfer of the survey.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-269">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-269">Tax</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-270">61</span><span class="sxs-lookup"><span data-stu-id="366ed-270">61</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-271">Divers ajustements de TVA en faveur de l’État.</span><span class="sxs-lookup"><span data-stu-id="366ed-271">Various VAT adjustments in favor of the state.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-272">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-272">Tax</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-273">63</span><span class="sxs-lookup"><span data-stu-id="366ed-273">63</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-274">TVA devant être retournée, comme indiqué sur les crédits reçus.</span><span class="sxs-lookup"><span data-stu-id="366ed-274">VAT that must be returned, as shown on the credits that are received.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-275">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-275">Tax</span></span></p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p style="text-align: center;"><span data-ttu-id="366ed-276"><strong>Section V. Taxes déductibles</strong></span><span class="sxs-lookup"><span data-stu-id="366ed-276"><strong>Section V. Taxes deductible</strong></span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-277">59</span><span class="sxs-lookup"><span data-stu-id="366ed-277">59</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-278">Montant de la TVA déductible.</span><span class="sxs-lookup"><span data-stu-id="366ed-278">Amount of deductible VAT.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-279">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-279">Tax</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-280">62</span><span class="sxs-lookup"><span data-stu-id="366ed-280">62</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-281">Diverses corrections de TVA en faveur du déclarant.</span><span class="sxs-lookup"><span data-stu-id="366ed-281">Various VAT corrections in favor of the declarant.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-282">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-282">Tax</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-283">64</span><span class="sxs-lookup"><span data-stu-id="366ed-283">64</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-284">TVA devant être récupérée en raison des crédits accordés.</span><span class="sxs-lookup"><span data-stu-id="366ed-284">VAT that must be recovered because of credits that are granted.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-285">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-285">Tax</span></span></p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p style="text-align: center;"><span data-ttu-id="366ed-286"><strong>Section VI. Solde</strong></span><span class="sxs-lookup"><span data-stu-id="366ed-286"><strong>Section VI. Balance</strong></span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-287">71</span><span class="sxs-lookup"><span data-stu-id="366ed-287">71</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-288">Taxe devant être payée.</span><span class="sxs-lookup"><span data-stu-id="366ed-288">Tax that must be paid.</span></span> <span data-ttu-id="366ed-289">Sur l’état INTERVAT, la valeur de cette zone est automatiquement calculée comme la somme des codes de déclaration <strong>54</strong>, <strong>55</strong>, <strong>56</strong>, <strong>57</strong>, <strong>61</strong> et <strong>63</strong>, moins les codes de déclaration <strong>59</strong>, <strong>62</strong> et <strong>64</strong>.</span><span class="sxs-lookup"><span data-stu-id="366ed-289">On the INTERVAT report, the value in this box is automatically calculated as the sum of reporting codes <strong>54</strong>, <strong>55</strong>, <strong>56</strong>, <strong>57</strong>, <strong>61</strong>, and <strong>63</strong>, minus reporting codes <strong>59</strong>, <strong>62</strong>, and <strong>64</strong>.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-290">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-290">Tax</span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-291">72</span><span class="sxs-lookup"><span data-stu-id="366ed-291">72</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-292">Taxe devant être récupérée.</span><span class="sxs-lookup"><span data-stu-id="366ed-292">Tax that must be recovered.</span></span> <span data-ttu-id="366ed-293">Sur l’état INTERVAT, la valeur de cette zone est automatiquement calculée comme la somme des codes de déclaration <strong>59</strong>, <strong>62</strong> et <strong>64</strong>, moins les codes de déclaration <strong>54</strong>, <strong>55</strong>, <strong>56</strong>, <strong>57</strong>, <strong>61</strong> et <strong>63</strong>.</span><span class="sxs-lookup"><span data-stu-id="366ed-293">On the INTERVAT report, the value in this box is automatically calculated as the sum of reporting codes <strong>59</strong>, <strong>62</strong>, and <strong>64</strong>, minus reporting codes <strong>54</strong>, <strong>55</strong>, <strong>56</strong>, <strong>57</strong>, <strong>61</strong>, and <strong>63</strong>.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-294">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-294">Tax</span></span></p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p style="text-align: center;"><span data-ttu-id="366ed-295"><strong>Section VII. Dépôt</strong></span><span class="sxs-lookup"><span data-stu-id="366ed-295"><strong>Section VII. Deposit</strong></span></span></p>
</td>
</tr>
<tr>
<td width="17%">
<p><span data-ttu-id="366ed-296">91</span><span class="sxs-lookup"><span data-stu-id="366ed-296">91</span></span></p>
</td>
<td width="71%">
<p><span data-ttu-id="366ed-297">TVA réellement due pour la période allant du 1er décembre au 20 décembre.</span><span class="sxs-lookup"><span data-stu-id="366ed-297">VAT that is actually owed for the period from December 1 through December 20.</span></span> <span data-ttu-id="366ed-298">Ce code s’applique à la déclaration mensuelle de décembre.</span><span class="sxs-lookup"><span data-stu-id="366ed-298">This code applies to the monthly declaration for December.</span></span></p>
</td>
<td width="10%">
<p><span data-ttu-id="366ed-299">Taxes</span><span class="sxs-lookup"><span data-stu-id="366ed-299">Tax</span></span></p>
</td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="366ed-300">Il n’est pas nécessaire d’entrer les codes **71**, **72** et **91**, car ils sont générés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="366ed-300">You don't have to enter codes **71**, **72**, and **91**, because they will be generated automatically.</span></span>

<span data-ttu-id="366ed-301">Pour paramétrer l’affectation de codes déclaration de taxe aux codes taxe, allez dans **Codes taxe \> Paramétrage d’état/Paramétrage d’état - Avoir**.</span><span class="sxs-lookup"><span data-stu-id="366ed-301">To set up an assignment of sales tax reporting codes to sales tax codes, go to **Sales tax codes \> Report setup/Report setup - Credit note**.</span></span> <span data-ttu-id="366ed-302">Tenez compte des relations suivantes entre les codes déclaration de taxe :</span><span class="sxs-lookup"><span data-stu-id="366ed-302">Consider the following relations between sales tax reporting codes:</span></span>

-   <span data-ttu-id="366ed-303">S’il y a un montant dans le code **01**, **02** ou **03**, il devrait également y avoir un montant dans le code **54**.</span><span class="sxs-lookup"><span data-stu-id="366ed-303">If there is an amount in code **01**, **02**, or **03**, there should also be an amount in code **54**.</span></span>
-   <span data-ttu-id="366ed-304">S’il y a un montant dans le code **54**, il devrait également y avoir un montant dans le code **01**, **02** ou **03**.</span><span class="sxs-lookup"><span data-stu-id="366ed-304">If there is an amount in code **54**, there should also be an amount in code **01**, **02**, or **03**.</span></span>
-   <span data-ttu-id="366ed-305">S’il y a un montant dans le code **86**, il devrait également y avoir un montant dans le code **55**.</span><span class="sxs-lookup"><span data-stu-id="366ed-305">If there is an amount in code **86**, there should also be an amount in code **55**.</span></span>
-   <span data-ttu-id="366ed-306">S’il y a un montant dans le code **87**, il devrait également y avoir un montant dans le code **56** ou **57**.</span><span class="sxs-lookup"><span data-stu-id="366ed-306">If there is an amount in code **87**, there should also be an amount in code **56** or **57**.</span></span>
-   <span data-ttu-id="366ed-307">La différence entre le montant du code **54** et la somme des codes **01**, **02** et **03** multipliée par les taux de TVA correspondants ne peut pas être supérieure à 61,97 EUR.</span><span class="sxs-lookup"><span data-stu-id="366ed-307">The difference between the amount in code **54** and the sum of codes **01**, **02**, and **03** multiplied by the corresponding VAT rates can't be more than 61.97 EUR.</span></span>
-   <span data-ttu-id="366ed-308">La différence entre le montant du code **55** et la somme des codes **84** et **86** multipliée par les taux de TVA correspondants ne peut pas être supérieure à 610,97 EUR.</span><span class="sxs-lookup"><span data-stu-id="366ed-308">The difference between the amount in code **55** and the sum of codes **84** and **86** multiplied by the corresponding VAT rates can't be more than 610.97 EUR.</span></span>
-   <span data-ttu-id="366ed-309">La différence entre la somme des montants des codes **56** et **57** et la somme des codes **85** et **87** multipliée par les taux de TVA correspondants ne peut pas être supérieure à 61,97 EUR.</span><span class="sxs-lookup"><span data-stu-id="366ed-309">The difference between the sum of the amounts in codes **56** and **57** and the sum of codes **85** and **87** multiplied by the corresponding VAT rates can't be more than 61.97 EUR.</span></span>
-   <span data-ttu-id="366ed-310">Le montant du code **59** doit être supérieur à la somme des codes **81**, **82**, **83**, **84** et **85**.</span><span class="sxs-lookup"><span data-stu-id="366ed-310">The amount in code **59** should be more than the sum of codes **81**, **82**, **83**, **84**, and **85**.</span></span>
-   <span data-ttu-id="366ed-311">Le montant du code **63** et du code **85** multiplié par les taux de TVA correspondants ne peut pas être supérieur à 61,97 EUR.</span><span class="sxs-lookup"><span data-stu-id="366ed-311">The amount in code **63** and code **85** multiplied by the corresponding VAT rates can't be more than 61.97 EUR.</span></span>
-   <span data-ttu-id="366ed-312">Le montant du code **64** et du code **49** multiplié par les taux de TVA correspondants ne peut pas être supérieur à 61,97 EUR.</span><span class="sxs-lookup"><span data-stu-id="366ed-312">The amount in code **64** and code **49** multiplied by the corresponding VAT rates can't be more than 61.97 EUR.</span></span>


### <a name="download-the-format-for-the-report"></a><span data-ttu-id="366ed-313">Télécharger le format de l’état</span><span class="sxs-lookup"><span data-stu-id="366ed-313">Download the format for the report</span></span>

<span data-ttu-id="366ed-314">Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), dans la bibliothèque d’actifs partagés, téléchargez les dernières versions des configurations d’états électroniques pour le format de déclaration de TVA suivant :</span><span class="sxs-lookup"><span data-stu-id="366ed-314">In [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), in the Shared asset library, download the latest versions of the Electronic reporting (ER) configurations for the following VAT declaration format:</span></span>

-   <span data-ttu-id="366ed-315">Format INTERVAT (BE)</span><span class="sxs-lookup"><span data-stu-id="366ed-315">INTERVAT format (BE)</span></span>

<span data-ttu-id="366ed-316">Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](https://docs.microsoft.com/dynamics365/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)</span><span class="sxs-lookup"><span data-stu-id="366ed-316">For more information, see [Download Electronic reporting configurations from Lifecycle Services](https://docs.microsoft.com/dynamics365/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span></span>

## <a name="additional-sales-tax-report-boxes"></a><span data-ttu-id="366ed-317">Zones d’état de taxes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="366ed-317">Additional sales tax report boxes</span></span>

1.  <span data-ttu-id="366ed-318">Allez dans **Taxe** \> **Déclarations** \> **Taxe** \> **Zones de déclaration de taxe supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="366ed-318">Go to **Tax** \> **Declarations** \> **Sales tax** \> **Additional sales tax report boxes**.</span></span>
2.  <span data-ttu-id="366ed-319">Sélectionnez **Nouveau** pour créer des lignes contenant des informations supplémentaires sur les codes de déclaration, y compris les corrections manuelles de la déclaration de taxe INTERVAT.</span><span class="sxs-lookup"><span data-stu-id="366ed-319">Select **New** to create lines that have additional information about reporting codes, including manual corrections of the INTERVAT tax declaration.</span></span> <span data-ttu-id="366ed-320">Avant de clôturer une période de règlement, vous devez créer la ligne correspondante, en validant le paiement de la taxe ou en créant une déclaration INTERVAT marquée comme **Mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="366ed-320">Before you close a settlement period, you should create the line for it, either by posting the sales tax payment or by creating an INTERVAT declaration that is marked as **Update**.</span></span> <span data-ttu-id="366ed-321">Le tableau suivant décrit les champs que vous devez définir pour une nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="366ed-321">The following table describes the fields that you must set for a new line.</span></span>

| <span data-ttu-id="366ed-322">**Champ**</span><span class="sxs-lookup"><span data-stu-id="366ed-322">**Field**</span></span>         | <span data-ttu-id="366ed-323">**Description**</span><span class="sxs-lookup"><span data-stu-id="366ed-323">**Description**</span></span>                                                                                                                                                                           |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="366ed-324">Période de règlement</span><span class="sxs-lookup"><span data-stu-id="366ed-324">Settlement period</span></span> | <span data-ttu-id="366ed-325">Sélectionnez la période de déclaration applicable.</span><span class="sxs-lookup"><span data-stu-id="366ed-325">Select the applicable reporting period.</span></span>                                                                                                                                                   |
| <span data-ttu-id="366ed-326">Date de début</span><span class="sxs-lookup"><span data-stu-id="366ed-326">From date</span></span>         | <span data-ttu-id="366ed-327">Indiquez le premier jour de la période du règlement de taxe à calculer.</span><span class="sxs-lookup"><span data-stu-id="366ed-327">Enter the first day of the sales tax settlement period to calculate sales tax for.</span></span> <span data-ttu-id="366ed-328">Cette valeur correspond à la date dans le champ **Début** sur la page **Périodes de règlement fiscal**.</span><span class="sxs-lookup"><span data-stu-id="366ed-328">This value corresponds to the date in the **From** field on the **Sales tax settlement periods** page.</span></span> |
| <span data-ttu-id="366ed-329">Au</span><span class="sxs-lookup"><span data-stu-id="366ed-329">To date</span></span>           | <span data-ttu-id="366ed-330">Entrez la dernière date de la période de règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-330">Enter the last date of the sales tax settlement period.</span></span>                                                                                                                                   |

3.  <span data-ttu-id="366ed-331">Dans l’onglet **Général**, vous pouvez définir les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="366ed-331">On **General** tab, you can set the following fields:</span></span>

-   <span data-ttu-id="366ed-332">Section **Commandes**</span><span class="sxs-lookup"><span data-stu-id="366ed-332">**Orders** section</span></span>

| <span data-ttu-id="366ed-333">**Champ**</span><span class="sxs-lookup"><span data-stu-id="366ed-333">**Field**</span></span>                                 | <span data-ttu-id="366ed-334">**Description**</span><span class="sxs-lookup"><span data-stu-id="366ed-334">**Description**</span></span>                                                                                                                                                                                                                                              |
|-------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="366ed-335">Demande le remboursement de la taxe réclamée</span><span class="sxs-lookup"><span data-stu-id="366ed-335">Requests repayment of sales tax reclaimed</span></span> | <span data-ttu-id="366ed-336">Sélectionnez cette option pour demander le remboursement de toute taxe réclamée.</span><span class="sxs-lookup"><span data-stu-id="366ed-336">Select this option to request the repayment of any reclaimed sales tax.</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="366ed-337">Décaissement</span><span class="sxs-lookup"><span data-stu-id="366ed-337">Disbursement</span></span>                              | <span data-ttu-id="366ed-338">Entrez le montant du décaissement.</span><span class="sxs-lookup"><span data-stu-id="366ed-338">Enter the amount of disbursement.</span></span> <span data-ttu-id="366ed-339">Un décaissement ne peut être effectué que pour le mois de décembre (déclaration mensuelle).</span><span class="sxs-lookup"><span data-stu-id="366ed-339">A disbursement can be paid only for the month of December (monthly declaration).</span></span> <span data-ttu-id="366ed-340">Le décaissement correspond à la zone 91 de la déclaration de TVA belge.</span><span class="sxs-lookup"><span data-stu-id="366ed-340">The disbursement corresponds to box 91 in the Belgian VAT declaration.</span></span> <span data-ttu-id="366ed-341">Vous ne pouvez définir ce champ que si le mois est égal à décembre (**12**).</span><span class="sxs-lookup"><span data-stu-id="366ed-341">You can set this field only if the month equals December (**12**).</span></span> |
| <span data-ttu-id="366ed-342">Commande d’avis de dépôt</span><span class="sxs-lookup"><span data-stu-id="366ed-342">Order deposit form</span></span>                        | <span data-ttu-id="366ed-343">Sélectionnez cette option pour demander des pages de dépôt dans le cadre de la déclaration de taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-343">Select this option to order deposit pages for tax reporting purposes.</span></span>                                                                                                                                                                                        |
| <span data-ttu-id="366ed-344">Liste annuelle nulle</span><span class="sxs-lookup"><span data-stu-id="366ed-344">Nil annual listing</span></span>                        | <span data-ttu-id="366ed-345">Sélectionnez cette option pour indiquer qu’il n’y a aucune transaction à déclarer et que la société n’a pas d’obligation envers le gouvernement belge de déclarer la vente annuelle de l’année précédente.</span><span class="sxs-lookup"><span data-stu-id="366ed-345">Select this option to indicate that there are no transactions to report, and that the company has no obligation to the Belgian government to declare the annual sales from the previous year.</span></span>                                                                |

-   <span data-ttu-id="366ed-346">Section **Pourcentages au prorata**</span><span class="sxs-lookup"><span data-stu-id="366ed-346">**Pro-rata percentages** section</span></span>

| <span data-ttu-id="366ed-347">**Champ**</span><span class="sxs-lookup"><span data-stu-id="366ed-347">**Field**</span></span>           | <span data-ttu-id="366ed-348">**Description**</span><span class="sxs-lookup"><span data-stu-id="366ed-348">**Description**</span></span>                                                                                                                                                                                                                 |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="366ed-349">Pourcentage prorata</span><span class="sxs-lookup"><span data-stu-id="366ed-349">Pro-rata percentage</span></span> | <span data-ttu-id="366ed-350">Entrez la valeur du pourcentage au prorata qui est exportée dans la balise **\<AdjustedValue\>** du fichier XML.</span><span class="sxs-lookup"><span data-stu-id="366ed-350">Enter the value of the pro-rata percentage that will be exported in the **\<AdjustedValue\>** tag in the XML file.</span></span>                                                                                                              |
| <span data-ttu-id="366ed-351">B1, B2, B3, B4, B5</span><span class="sxs-lookup"><span data-stu-id="366ed-351">B1, B2, B3, B4, B5</span></span>  | <span data-ttu-id="366ed-352">Entrez les montants des valeurs de B1, B2, B3, B4 et B5, qui sont exportées dans la balise **\<SpecialProRataPercentage\>** du fichier XML, où **\<SpecialProRataGridNumber\>**=**"1"**, **"2"**, **"3"**, **"4"**, **"5"**.</span><span class="sxs-lookup"><span data-stu-id="366ed-352">Enter amounts for the values of B1, B2, B3, B4, and B5, which will be exported in the **\<SpecialProRataPercentage\>** tag in the XML file, where **\<SpecialProRataGridNumber\>**=**"1"**, **"2"**, **"3"**, **"4"**, **"5"**.</span></span> |

### <a name="tax-corrections"></a><span data-ttu-id="366ed-353">Corrections de taxe</span><span class="sxs-lookup"><span data-stu-id="366ed-353">Tax corrections</span></span>

<span data-ttu-id="366ed-354">Suivez ces étapes pour entrer les montants de correction manuelle.</span><span class="sxs-lookup"><span data-stu-id="366ed-354">Follow these steps to enter manual correction amounts.</span></span>

1.  <span data-ttu-id="366ed-355">Allez dans **Taxe** \> **Déclarations** \> **Taxe** \> **Zones de déclaration de taxe supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="366ed-355">Go to **Tax** \> **Declarations** \> **Sales tax** \> **Additional sales tax report boxes**.</span></span>
2.  <span data-ttu-id="366ed-356">Sélectionnez **Corrections de taxe** \> **Ajustements** et définissez les champs suivants.</span><span class="sxs-lookup"><span data-stu-id="366ed-356">Select **Tax corrections** \> **Adjustments** and set the following fields.</span></span>

| <span data-ttu-id="366ed-357">**Champ**</span><span class="sxs-lookup"><span data-stu-id="366ed-357">**Field**</span></span>         | <span data-ttu-id="366ed-358">**Description**</span><span class="sxs-lookup"><span data-stu-id="366ed-358">**Description**</span></span>                                                                                                                                                                           |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="366ed-359">Période de règlement</span><span class="sxs-lookup"><span data-stu-id="366ed-359">Settlement period</span></span> | <span data-ttu-id="366ed-360">Sélectionnez la période de déclaration applicable.</span><span class="sxs-lookup"><span data-stu-id="366ed-360">Select the applicable reporting period.</span></span>                                                                                                                                                   |
| <span data-ttu-id="366ed-361">Date de début</span><span class="sxs-lookup"><span data-stu-id="366ed-361">From date</span></span>         | <span data-ttu-id="366ed-362">Indiquez le premier jour de la période du règlement de taxe à calculer.</span><span class="sxs-lookup"><span data-stu-id="366ed-362">Enter the first day of the sales tax settlement period to calculate sales tax for.</span></span> <span data-ttu-id="366ed-363">Cette valeur correspond à la date dans le champ **Début** sur la page **Périodes de règlement fiscal**.</span><span class="sxs-lookup"><span data-stu-id="366ed-363">This value corresponds to the date in the **From** field on the **Sales tax settlement periods** page.</span></span> |
| <span data-ttu-id="366ed-364">Au</span><span class="sxs-lookup"><span data-stu-id="366ed-364">To date</span></span>           | <span data-ttu-id="366ed-365">Entrez le dernier jour de la période de règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-365">Enter the last day of the sales tax settlement period.</span></span>                                                                                                                                    |
| <span data-ttu-id="366ed-366">Code de déclaration</span><span class="sxs-lookup"><span data-stu-id="366ed-366">Reporting code</span></span>    | <span data-ttu-id="366ed-367">Sélectionnez le code de déclaration.</span><span class="sxs-lookup"><span data-stu-id="366ed-367">Select the reporting code.</span></span> <span data-ttu-id="366ed-368">Seuls les codes de déclaration pour lesquels la case à cocher **Corrections de taxe** est activée sont disponibles lors de l’entrée d’une correction de taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-368">Only the reporting codes that the **Tax corrections** check box is selected for will be available during tax correction entry.</span></span>                                 |
| <span data-ttu-id="366ed-369">Montant</span><span class="sxs-lookup"><span data-stu-id="366ed-369">Amount</span></span>            | <span data-ttu-id="366ed-370">Entrez le montant de la correction.</span><span class="sxs-lookup"><span data-stu-id="366ed-370">Enter the correction amount.</span></span>                                                                                                                                                              |

> [!NOTE]
> <span data-ttu-id="366ed-371">Les codes de déclaration composés qui sont utilisés pour les avoirs,</span><span class="sxs-lookup"><span data-stu-id="366ed-371">Composed reporting codes that are used for credit notes.</span></span> <span data-ttu-id="366ed-372">comme le code **8185**, ne sont pas disponibles à la sélection.</span><span class="sxs-lookup"><span data-stu-id="366ed-372">such as code **8185**, aren't available for selection.</span></span> <span data-ttu-id="366ed-373">Il en va de même pour les codes **71**, **72** et **91**.</span><span class="sxs-lookup"><span data-stu-id="366ed-373">Nor are codes **71**, **72**, and **91**.</span></span> <span data-ttu-id="366ed-374">Les codes **71** et **72** sont calculés automatiquement lorsque la déclaration de taxe belge est exécutée.</span><span class="sxs-lookup"><span data-stu-id="366ed-374">Codes **71** and **72** are calculated automatically when Belgian sales tax reporting is run.</span></span> <span data-ttu-id="366ed-375">Le code **91** est entré d’une autre manière (voir la description du champ **Décaissement** ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="366ed-375">Code **91** is entered in another way (see description of **Disbursement** field above).</span></span>
>
> <span data-ttu-id="366ed-376">Si une période fiscale est mise à jour, un N° document et une date s’affichent.</span><span class="sxs-lookup"><span data-stu-id="366ed-376">If a tax period is updated, a voucher number and a date will be shown.</span></span> <span data-ttu-id="366ed-377">(Pour plus d’informations, consultez la description de la case à cocher **Mettre à jour** dans la section [Générer une déclaration de taxe INTERVAT](#generate-an-intervat-tax-declaration) plus loin dans cette rubrique.) La période comportant un N° document et une date est une période de TVA clôturée pour la Belgique.</span><span class="sxs-lookup"><span data-stu-id="366ed-377">(For more information, see the description of the **Update** check box in the [Generate an INTERVAT tax declaration](#generate-an-intervat-tax-declaration) section later in this topic.) The period that has a voucher number and a date is a closed VAT period for Belgium.</span></span> <span data-ttu-id="366ed-378">Par conséquent, toutes les valeurs de l’onglet **Général** de la page **Corrections de taxe** sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="366ed-378">Therefore, all values on the **General** tab of the **Tax corrections** page are read-only.</span></span> <span data-ttu-id="366ed-379">Lorsque de nouvelles transactions avec taxes sont entrées pour la période de TVA clôturée, les taxes sont transférées vers la prochaine période fiscale ouverte disponible.</span><span class="sxs-lookup"><span data-stu-id="366ed-379">When new transactions that have taxes are entered for the closed VAT period, the taxes will be forwarded to the next available open tax period.</span></span>


## <a name="generate-an-intervat-tax-declaration"></a><span data-ttu-id="366ed-380">Générer une déclaration de taxe INTERVAT</span><span class="sxs-lookup"><span data-stu-id="366ed-380">Generate an INTERVAT tax declaration</span></span>
1.  <span data-ttu-id="366ed-381">Allez dans **Taxe** \>**Déclarations \> Taxe \> Déclaration de taxe INTERVAT**.</span><span class="sxs-lookup"><span data-stu-id="366ed-381">Go to **Tax** \>**Declarations \> Sales tax \> INTERVAT tax declaration**.</span></span>
2.  <span data-ttu-id="366ed-382">Sélectionnez **Nouvelle déclaration** pour générer une déclaration de taxe INTERVAT.</span><span class="sxs-lookup"><span data-stu-id="366ed-382">Select **New declaration** to generate an INTERVAT tax declaration.</span></span>
3.  <span data-ttu-id="366ed-383">Dans la boîte de dialogue **INTERVAT : Déclaration de taxe belge**, définissez les champs suivants.</span><span class="sxs-lookup"><span data-stu-id="366ed-383">In the **INTERVAT: Belgian sales tax reporting** dialog box, set the following fields.</span></span>

| <span data-ttu-id="366ed-384">**Champ**</span><span class="sxs-lookup"><span data-stu-id="366ed-384">**Field**</span></span>                | <span data-ttu-id="366ed-385">**Description**</span><span class="sxs-lookup"><span data-stu-id="366ed-385">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                            |
|--------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="366ed-386">Période de règlement</span><span class="sxs-lookup"><span data-stu-id="366ed-386">Settlement period</span></span>        | <span data-ttu-id="366ed-387">Sélectionnez la période de déclaration applicable.</span><span class="sxs-lookup"><span data-stu-id="366ed-387">Select the applicable reporting period.</span></span>                                                                                                                                                                                                                                                                                                                                                                                    |
| <span data-ttu-id="366ed-388">Date de début</span><span class="sxs-lookup"><span data-stu-id="366ed-388">From date</span></span>                | <span data-ttu-id="366ed-389">Indiquez le premier jour de la période du règlement de taxe à calculer.</span><span class="sxs-lookup"><span data-stu-id="366ed-389">Enter the first day of the sales tax settlement period to calculate sales tax for.</span></span> <span data-ttu-id="366ed-390">Cette valeur correspond à la date dans le champ **Début** sur la page **Périodes de règlement fiscal**.</span><span class="sxs-lookup"><span data-stu-id="366ed-390">This value corresponds to the date in the **From** field on the **Sales tax settlement periods** page.</span></span>                                                                                                                                                                                                                                  |
| <span data-ttu-id="366ed-391">Date de transaction</span><span class="sxs-lookup"><span data-stu-id="366ed-391">Transaction date</span></span>         | <span data-ttu-id="366ed-392">Indiquez la date à laquelle la déclaration de taxe est calculée.</span><span class="sxs-lookup"><span data-stu-id="366ed-392">Enter the date when the sales tax report is calculated.</span></span> <span data-ttu-id="366ed-393">La valeur par défaut est la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="366ed-393">The default value is the current date.</span></span> <span data-ttu-id="366ed-394">Le paiement de la taxe est calculé pour toutes les transactions validées pendant la période de règlement.</span><span class="sxs-lookup"><span data-stu-id="366ed-394">The sales tax payment is calculated for all transactions that were posted during the settlement period.</span></span>                                                                                                                                                                                                                     |
| <span data-ttu-id="366ed-395">Mise à jour</span><span class="sxs-lookup"><span data-stu-id="366ed-395">Update</span></span>                   | <span data-ttu-id="366ed-396">Une case cochée clôture la période et crée un paiement de taxe, s’il n’a pas déjà été créé.</span><span class="sxs-lookup"><span data-stu-id="366ed-396">A selected check box closes the period and creates a sales tax payment, if it wasn't already created.</span></span> <span data-ttu-id="366ed-397">Par conséquent, toutes les transactions de TVA entrées dans cette période après la mise à jour sont transférées vers la prochaine période ouverte disponible.</span><span class="sxs-lookup"><span data-stu-id="366ed-397">Therefore, all VAT transactions that are entered in this period after the update will be forwarded to the next available open period.</span></span> <span data-ttu-id="366ed-398">Une case cochée crée également la ligne sur la page **Zones de déclaration de taxe supplémentaires**, si elle n’a pas déjà été créée.</span><span class="sxs-lookup"><span data-stu-id="366ed-398">A selected check box also creates the line on the **Additional sales tax report boxes** page, if it wasn't already created.</span></span> <span data-ttu-id="366ed-399">Aucune des valeurs sur cette nouvelle ligne ne peut être modifiée.</span><span class="sxs-lookup"><span data-stu-id="366ed-399">None of the values on this new line can be edited.</span></span> |
| <span data-ttu-id="366ed-400">Remplacement de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="366ed-400">Replaced VAT declaration</span></span> | <span data-ttu-id="366ed-401">Entrez le numéro d’identification de la déclaration à remplacer.</span><span class="sxs-lookup"><span data-stu-id="366ed-401">Enter the identification number of the declaration to replace.</span></span>                                                                                                                                                                                                                                                                                                                                                             |
| <span data-ttu-id="366ed-402">Fichier</span><span class="sxs-lookup"><span data-stu-id="366ed-402">File</span></span>                     | <span data-ttu-id="366ed-403">Entrez le nom du fichier vers lequel la déclaration de taxe INTERVAT sera exportée.</span><span class="sxs-lookup"><span data-stu-id="366ed-403">Enter the file name that the INTERVAT tax declaration will be exported to.</span></span>                                                                                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="366ed-404">Mise en correspondance des formats</span><span class="sxs-lookup"><span data-stu-id="366ed-404">Format mapping</span></span>           | <span data-ttu-id="366ed-405">Sélectionnez le format **Format INTERVAT (BE)** que vous avez téléchargé précédemment.</span><span class="sxs-lookup"><span data-stu-id="366ed-405">Select the **INTERVAT format (BE)** ER format that you downloaded earlier.</span></span>                                                                                                                                                                                                                                                                                                                                                 |

<span data-ttu-id="366ed-406">Vous pouvez également clôturer la période fiscale en générant un paiement de taxe (**Taxe \> Déclarations \> Taxe \> Régler et valider la taxe**).</span><span class="sxs-lookup"><span data-stu-id="366ed-406">You can also close the tax period by generating a sales tax payment (**Tax \> Declarations \> Sales tax \> Settle and post sales tax**).</span></span>

4.  <span data-ttu-id="366ed-407">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="366ed-407">Select **OK**.</span></span> <span data-ttu-id="366ed-408">Le système génère la ligne de déclaration de taxe INTERVAT et un fichier XML INTERVAT.</span><span class="sxs-lookup"><span data-stu-id="366ed-408">The system generates the INTERVAT tax declaration line and an INTERVAT XML file.</span></span>
5.  <span data-ttu-id="366ed-409">Passez en revue les informations de la déclaration.</span><span class="sxs-lookup"><span data-stu-id="366ed-409">Review the information in the declaration.</span></span>

![](media/2_Intervat_tax declaration.png)

6.  <span data-ttu-id="366ed-410">Dans l’onglet **Général**, vérifiez les champs suivants : **ID INTERVAT**, **Date**, **Période**, **Date de début**, **Date de fin**, **Fréquence**, **Statut** et **Nom du fichier**.</span><span class="sxs-lookup"><span data-stu-id="366ed-410">On the **General** tab, review the following fields: **INTERVAT ID**, **Date**, **Period**, **Start date**, **End date**, **Period frequency**, **Status**, and **File name**.</span></span>
7.  <span data-ttu-id="366ed-411">Dans l’onglet **Cadre I : Informations générales**, vérifiez les champs suivants.</span><span class="sxs-lookup"><span data-stu-id="366ed-411">On the **Frame I: General information** tab, review the following fields.</span></span> <span data-ttu-id="366ed-412">Vous pouvez modifier ces champs, même si la période a été clôturée.</span><span class="sxs-lookup"><span data-stu-id="366ed-412">You can edit these fields, even if the period was closed.</span></span> <span data-ttu-id="366ed-413">Les exceptions sont les champs de la section **Pourcentages au prorata**.</span><span class="sxs-lookup"><span data-stu-id="366ed-413">The exceptions are the fields in the **Pro-rata percentages** section.</span></span> <span data-ttu-id="366ed-414">Ces champs sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="366ed-414">Those fields are read-only.</span></span>

| <span data-ttu-id="366ed-415">**Champ**</span><span class="sxs-lookup"><span data-stu-id="366ed-415">**Field**</span></span>                        | <span data-ttu-id="366ed-416">**Description**</span><span class="sxs-lookup"><span data-stu-id="366ed-416">**Description**</span></span>                                                                                                                                                                                                                                                                           |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="366ed-417">Nom de la société</span><span class="sxs-lookup"><span data-stu-id="366ed-417">Company name</span></span>                     | <span data-ttu-id="366ed-418">Nom de la société.</span><span class="sxs-lookup"><span data-stu-id="366ed-418">The company name.</span></span>                                                                                                                                                                                                                                                                         |
| <span data-ttu-id="366ed-419">Numéro de taxe</span><span class="sxs-lookup"><span data-stu-id="366ed-419">Sales tax number</span></span>                 | <span data-ttu-id="366ed-420">Numéro d’identification fiscale transféré à partir du paramètre que vous avez défini dans la section [Conditions préalables](#prerequisites) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="366ed-420">The tax registration number that is transferred from the setting that you defined in the [Prerequisites](#prerequisites) section earlier in this topic.</span></span>                                                                                                                                   |
| <span data-ttu-id="366ed-421">Numéro de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="366ed-421">Enterprise number</span></span>                | <span data-ttu-id="366ed-422">Numéro d’entreprise transféré à partir du paramètre que vous avez défini dans la section [Conditions préalables](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="366ed-422">The enterprise number that is transferred from the setting that you defined in the [Prerequisites](#prerequisites) section.</span></span>                                                                                                                                                               |
| <span data-ttu-id="366ed-423">Téléphone, E-mail</span><span class="sxs-lookup"><span data-stu-id="366ed-423">Telephone, Email</span></span>                 | <span data-ttu-id="366ed-424">Informations sur le contact transférées à partir du paramètre que vous avez défini dans la section [Conditions préalables](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="366ed-424">Contact information that is transferred from the setting that you defined in the [Prerequisites](#prerequisites) section.</span></span>                                                                                                                                                                 |
| <span data-ttu-id="366ed-425">Demande de remboursement</span><span class="sxs-lookup"><span data-stu-id="366ed-425">Request for reimbursement</span></span>        | <span data-ttu-id="366ed-426">Cochez cette case pour demander un remboursement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-426">Select this check box to request a reimbursement of tax.</span></span>                                                                                                                                                                                                                                  |
| <span data-ttu-id="366ed-427">Demande de formulaires de paiement</span><span class="sxs-lookup"><span data-stu-id="366ed-427">Request for payment forms</span></span>        | <span data-ttu-id="366ed-428">Cochez cette case pour demander des pages de paiement pour les déclarations de taxe INTERVAT.</span><span class="sxs-lookup"><span data-stu-id="366ed-428">Select this check box to request payment pages for the INTERVAT tax declarations.</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="366ed-429">Liste annuelle nulle</span><span class="sxs-lookup"><span data-stu-id="366ed-429">Nil annual listing</span></span>               | <span data-ttu-id="366ed-430">Une case cochée indique que cette déclaration est une déclaration vide.</span><span class="sxs-lookup"><span data-stu-id="366ed-430">A selected check box indicates that this declaration is an empty declaration.</span></span> <span data-ttu-id="366ed-431">La valeur est transférée à partir de la page **Zones de déclaration de taxe supplémentaires** décrite dans la section [Zones de déclaration de taxe supplémentaires](#additional-sales-tax-report-boxes) plus haut dans cette rubrique</span><span class="sxs-lookup"><span data-stu-id="366ed-431">The value is transferred from the **Additional sales tax report boxes** page that is described in the [Additional sales tax report boxes](#additional-sales-tax-report-boxes) section earlier in this topic</span></span> |
| <span data-ttu-id="366ed-432">Remplacement de la déclaration de TVA</span><span class="sxs-lookup"><span data-stu-id="366ed-432">Replaced VAT declaration</span></span>         | <span data-ttu-id="366ed-433">Numéro d’identification de la déclaration, pour remplacer ce que vous avez défini dans la boîte de dialogue **INTERVAT : Déclaration de taxe belge** décrite plus haut dans cette section.</span><span class="sxs-lookup"><span data-stu-id="366ed-433">The identification number of the declaration, to replace what you defined in the **INTERVAT: Belgian sales tax reporting** dialog box that is described earlier in this section.</span></span>                                                                                                          |
| <span data-ttu-id="366ed-434">Section **Pourcentages au prorata**</span><span class="sxs-lookup"><span data-stu-id="366ed-434">**Pro-rata percentages** section</span></span> | <span data-ttu-id="366ed-435">Vérifiez les montants des champs **Pourcentage au prorata**, **B1**, **B2**, **B3**, **B4** et **B5** que vous avez définis sur la page **Zones de déclaration de taxe supplémentaires** décrite dans la section [Zones de déclaration de taxe supplémentaires](#additional-sales-tax-report-boxes).</span><span class="sxs-lookup"><span data-stu-id="366ed-435">Review the amounts in the **Pro-rata percentage**, **B1**, **B2**, **B3**, **B4**, and **B5** fields that you defined on the **Additional sales tax report boxes** page that is described in the [Additional sales tax report boxes](#additional-sales-tax-report-boxes) section.</span></span>         |

<span data-ttu-id="366ed-436">Sur la page **Déclaration de taxe INTERVAT**, vous pouvez effectuer les actions suivantes à l’aide des boutons du volet Actions.</span><span class="sxs-lookup"><span data-stu-id="366ed-436">On the **INTERVAT tax declaration** page, you can perform the following actions by using the buttons on the Action Pane.</span></span>

| <span data-ttu-id="366ed-437">**Bouton**</span><span class="sxs-lookup"><span data-stu-id="366ed-437">**Button**</span></span>     | <span data-ttu-id="366ed-438">**Description**</span><span class="sxs-lookup"><span data-stu-id="366ed-438">**Description**</span></span>                                                                                                                                                                                                                                                   |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="366ed-439">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="366ed-439">Setup</span></span>          | <span data-ttu-id="366ed-440">Ouvrez la page **Zones de déclaration de taxe supplémentaires** décrite dans la section [Zones de déclaration de taxe supplémentaires](#additional-sales-tax-report-boxes).</span><span class="sxs-lookup"><span data-stu-id="366ed-440">Open the **Additional sales tax report boxes** page that is described in the [Additional sales tax report boxes](#additional-sales-tax-report-boxes) section.</span></span>                                                                                                     |
| <span data-ttu-id="366ed-441">Recréer le fichier</span><span class="sxs-lookup"><span data-stu-id="366ed-441">Re-create file</span></span> | <span data-ttu-id="366ed-442">Recréez le fichier INTERVAT si la période n’a pas été clôturée.</span><span class="sxs-lookup"><span data-stu-id="366ed-442">Recreate the INTERVAT file if the period wasn't closed.</span></span>                                                                                                                                                                                                           |
| <span data-ttu-id="366ed-443">Ouvrir le fichier</span><span class="sxs-lookup"><span data-stu-id="366ed-443">Open file</span></span>      | <span data-ttu-id="366ed-444">Ouvrez le fichier XML généré.</span><span class="sxs-lookup"><span data-stu-id="366ed-444">Open the generated XML file.</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="366ed-445">Site Web ouvert</span><span class="sxs-lookup"><span data-stu-id="366ed-445">Open Web site</span></span>  | <span data-ttu-id="366ed-446">Ouvrez le site web (URL) que vous avez défini sur la page **Paramétrage INTERVAT**.</span><span class="sxs-lookup"><span data-stu-id="366ed-446">Open the website (URL) that you defined on the **INTERVAT setup** page.</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="366ed-447">Modifier le statut</span><span class="sxs-lookup"><span data-stu-id="366ed-447">Change status</span></span>  | <span data-ttu-id="366ed-448">Modifiez le statut en **Envoyé**.</span><span class="sxs-lookup"><span data-stu-id="366ed-448">Change the status to **Sent**.</span></span> <span data-ttu-id="366ed-449">Lorsqu’une déclaration est créée, son statut est **Créé**.</span><span class="sxs-lookup"><span data-stu-id="366ed-449">When a declaration is created, it has a status of **Created**.</span></span> <span data-ttu-id="366ed-450">Après avoir importé manuellement le fichier généré contenant la déclaration INTERVAT sur le site INTERVAT, vous pouvez utiliser ce bouton pour modifier le statut en **Envoyé**.</span><span class="sxs-lookup"><span data-stu-id="366ed-450">After you manually import the generated file that contains the INTERVAT declaration on the INTERVAT site, you can use this button to change the status to **Sent**.</span></span> |
| <span data-ttu-id="366ed-451">Détails</span><span class="sxs-lookup"><span data-stu-id="366ed-451">Details</span></span>        | <span data-ttu-id="366ed-452">Ouvrez la page **Détails INTERVAT**, où vous pouvez examiner les montants des codes de déclaration correspondants.</span><span class="sxs-lookup"><span data-stu-id="366ed-452">Open the **INTERVAT details** page, where you can review the amounts in the corresponding reporting codes.</span></span>                                                                                                                                                        |

## <a name="generate-an-intervat-summary-tax-declaration"></a><span data-ttu-id="366ed-453">Générer une déclaration de taxe de synthèse INTERVAT</span><span class="sxs-lookup"><span data-stu-id="366ed-453">Generate an INTERVAT summary tax declaration</span></span>
<span data-ttu-id="366ed-454">Pour imprimer une déclaration de taxe INTERVAT pour plusieurs périodes fiscales, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="366ed-454">To print an INTERVAT tax declaration for several tax periods, follow these steps.</span></span>

1.  <span data-ttu-id="366ed-455">Allez dans **Taxe** \> **Recherches et états** \> **États de taxe** \> **Déclaration de taxe de synthèse INTERVAT**.</span><span class="sxs-lookup"><span data-stu-id="366ed-455">Go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **INTERVAT summary tax declaration**.</span></span>
2.  <span data-ttu-id="366ed-456">Utilisez les filtres pour spécifier les critères de sélection des données, puis passez en revue les informations de l’état.</span><span class="sxs-lookup"><span data-stu-id="366ed-456">Use the filters to specify criteria for selecting data, and then review the information on the report.</span></span>

![État des déclarations de taxe de synthèse INTERVAT généré](media/3_Intervat_summary_tax_declarations.png)

## <a name="example"></a><span data-ttu-id="366ed-458">Exemple</span><span class="sxs-lookup"><span data-stu-id="366ed-458">Example</span></span>
<span data-ttu-id="366ed-459">L’exemple suivant montre comment paramétrer des codes taxe et des codes déclaration de taxe, valider des transactions et générer la déclaration de taxe INTERVAT.</span><span class="sxs-lookup"><span data-stu-id="366ed-459">The following example shows how you can set up sales tax codes and sales tax reporting codes, post transactions, and generate the INTERVAT tax declaration.</span></span>

1.  <span data-ttu-id="366ed-460">Accédez à **Administration d’organisation \> Organisations \> Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="366ed-460">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>
2.  <span data-ttu-id="366ed-461">Dans l’organisateur **Immatriculation fiscale**, dans le champ **Numéro d’identification fiscale**, entrez **0466.158.640**.</span><span class="sxs-lookup"><span data-stu-id="366ed-461">On the **Tax registration** FastTab, in the **Tax registration number** field, enter **0466.158.640**.</span></span>
3.  <span data-ttu-id="366ed-462">Sélectionnez **ID enregistrement**, ajoutez une nouvelle ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="366ed-462">Select **Registration IDs**, add a line, and set the following values:</span></span>

-   <span data-ttu-id="366ed-463">**Type d’enregistrement :** ENTNUM</span><span class="sxs-lookup"><span data-stu-id="366ed-463">**Registration type:** ENTNUM</span></span>
-   <span data-ttu-id="366ed-464">**Numéro d’enregistrement :** BTW BE 0466.158.640</span><span class="sxs-lookup"><span data-stu-id="366ed-464">**Registration number:** BTW BE 0466.158.640</span></span>

4.  <span data-ttu-id="366ed-465">Allez dans **Taxe \> Taxes indirectes \> Taxe \> Codes taxe** et configurez les codes taxe suivants.</span><span class="sxs-lookup"><span data-stu-id="366ed-465">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax codes**, and set up the following sales tax codes.</span></span>

| <span data-ttu-id="366ed-466">**Code taxe**</span><span class="sxs-lookup"><span data-stu-id="366ed-466">**Sales tax code**</span></span> | <span data-ttu-id="366ed-467">**Pourcentage**</span><span class="sxs-lookup"><span data-stu-id="366ed-467">**Percentage**</span></span> | <span data-ttu-id="366ed-468">**Description**</span><span class="sxs-lookup"><span data-stu-id="366ed-468">**Description**</span></span>                                                                      |
|--------------------|----------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="366ed-469">BE21</span><span class="sxs-lookup"><span data-stu-id="366ed-469">BE21</span></span>               | <span data-ttu-id="366ed-470">21</span><span class="sxs-lookup"><span data-stu-id="366ed-470">21</span></span>             | <span data-ttu-id="366ed-471">Ventes et achats nationaux à un taux de 21 %.</span><span class="sxs-lookup"><span data-stu-id="366ed-471">Domestic sales and purchases at a rate of 21 percent.</span></span>                                |
| <span data-ttu-id="366ed-472">BE12</span><span class="sxs-lookup"><span data-stu-id="366ed-472">BE12</span></span>               | <span data-ttu-id="366ed-473">12</span><span class="sxs-lookup"><span data-stu-id="366ed-473">12</span></span>             | <span data-ttu-id="366ed-474">Ventes et achats nationaux à un taux de 12 %.</span><span class="sxs-lookup"><span data-stu-id="366ed-474">Domestic sales and purchases at a rate of 12 percent.</span></span>                                |
| <span data-ttu-id="366ed-475">BE6</span><span class="sxs-lookup"><span data-stu-id="366ed-475">BE6</span></span>                | <span data-ttu-id="366ed-476">6</span><span class="sxs-lookup"><span data-stu-id="366ed-476">6</span></span>              | <span data-ttu-id="366ed-477">Ventes et achats nationaux à un taux de 6 %.</span><span class="sxs-lookup"><span data-stu-id="366ed-477">Domestic sales and purchases at a rate of 6 percent.</span></span>                                 |
| <span data-ttu-id="366ed-478">BEEU21</span><span class="sxs-lookup"><span data-stu-id="366ed-478">BEEU21</span></span>             | <span data-ttu-id="366ed-479">21</span><span class="sxs-lookup"><span data-stu-id="366ed-479">21</span></span>             | <span data-ttu-id="366ed-480">Achats dans l’UE à un taux de 21 % lorsque l’option **Taxe d’utilisation** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="366ed-480">EU purchases at a rate of 21 percent where the **Use tax** option is set to **Yes**.</span></span> |
| <span data-ttu-id="366ed-481">BEEU12</span><span class="sxs-lookup"><span data-stu-id="366ed-481">BEEU12</span></span>             | <span data-ttu-id="366ed-482">12</span><span class="sxs-lookup"><span data-stu-id="366ed-482">12</span></span>             | <span data-ttu-id="366ed-483">Achats dans l’UE à un taux de 12 % lorsque l’option **Taxe d’utilisation** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="366ed-483">EU purchases at a rate of 12 percent where the **Use tax** option is set to **Yes**.</span></span> |
| <span data-ttu-id="366ed-484">BEEU6</span><span class="sxs-lookup"><span data-stu-id="366ed-484">BEEU6</span></span>              | <span data-ttu-id="366ed-485">6</span><span class="sxs-lookup"><span data-stu-id="366ed-485">6</span></span>              | <span data-ttu-id="366ed-486">Achats dans l’UE à un taux de 6 % lorsque l’option **Taxe d’utilisation** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="366ed-486">EU purchases at a rate of 6 percent where the **Use tax** option is set to **Yes**.</span></span>  |
| <span data-ttu-id="366ed-487">BEEUS</span><span class="sxs-lookup"><span data-stu-id="366ed-487">BEEUS</span></span>              | <span data-ttu-id="366ed-488">21</span><span class="sxs-lookup"><span data-stu-id="366ed-488">21</span></span>             | <span data-ttu-id="366ed-489">Ventes dans l’UE où l’option **Exonéré** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="366ed-489">EU sales where the **Exempt** option is set to **Yes**.</span></span>                              |

5.  <span data-ttu-id="366ed-490">Sur la page **Codes taxe**, dans l’organisateur **Paramétrage d’état**, affectez des codes déclaration aux codes taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-490">On the **Sales tax codes** page, on the **Report setup** FastTab, assign reporting codes to sales tax codes.</span></span>

<span data-ttu-id="366ed-491">Le tableau suivant montre comment affecter les codes déclaration de taxe aux codes taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-491">The following table shows how to assign the sales tax reporting codes to sales tax codes.</span></span>

| <span data-ttu-id="366ed-492">**Code taxe**</span><span class="sxs-lookup"><span data-stu-id="366ed-492">**Sales tax code**</span></span> | <span data-ttu-id="366ed-493">**Ventes soumises à taxe**</span><span class="sxs-lookup"><span data-stu-id="366ed-493">**Taxable sales**</span></span> | <span data-ttu-id="366ed-494">**Vente détaxée**</span><span class="sxs-lookup"><span data-stu-id="366ed-494">**Tax-free sale**</span></span> | <span data-ttu-id="366ed-495">**Taxe due**</span><span class="sxs-lookup"><span data-stu-id="366ed-495">**Sales tax payable**</span></span> | <span data-ttu-id="366ed-496">**Achats soumis à taxe**</span><span class="sxs-lookup"><span data-stu-id="366ed-496">**Taxable purchases**</span></span> | <span data-ttu-id="366ed-497">**Taxe déductible**</span><span class="sxs-lookup"><span data-stu-id="366ed-497">**Sales tax receivable**</span></span> | <span data-ttu-id="366ed-498">**Importation soumise à taxe**</span><span class="sxs-lookup"><span data-stu-id="366ed-498">**Taxable import**</span></span> | <span data-ttu-id="366ed-499">**Taxe d’utilisation**</span><span class="sxs-lookup"><span data-stu-id="366ed-499">**Use tax**</span></span> | <span data-ttu-id="366ed-500">**Contrepartie taxe d’utilisation**</span><span class="sxs-lookup"><span data-stu-id="366ed-500">**Offset use tax**</span></span> |
|--------------------|-------------------|-------------------|-----------------------|-----------------------|--------------------------|--------------------|-------------|--------------------|
| <span data-ttu-id="366ed-501">BE21</span><span class="sxs-lookup"><span data-stu-id="366ed-501">BE21</span></span>               | <span data-ttu-id="366ed-502">03</span><span class="sxs-lookup"><span data-stu-id="366ed-502">03</span></span>                |                   | <span data-ttu-id="366ed-503">54</span><span class="sxs-lookup"><span data-stu-id="366ed-503">54</span></span>                    |                       |                          |                    |             |                    |
| <span data-ttu-id="366ed-504">BE12</span><span class="sxs-lookup"><span data-stu-id="366ed-504">BE12</span></span>               | <span data-ttu-id="366ed-505">02</span><span class="sxs-lookup"><span data-stu-id="366ed-505">02</span></span>                |                   | <span data-ttu-id="366ed-506">54</span><span class="sxs-lookup"><span data-stu-id="366ed-506">54</span></span>                    |                       |                          |                    |             |                    |
| <span data-ttu-id="366ed-507">BE6</span><span class="sxs-lookup"><span data-stu-id="366ed-507">BE6</span></span>                | <span data-ttu-id="366ed-508">01</span><span class="sxs-lookup"><span data-stu-id="366ed-508">01</span></span>                |                   | <span data-ttu-id="366ed-509">54</span><span class="sxs-lookup"><span data-stu-id="366ed-509">54</span></span>                    |                       |                          |                    |             |                    |
| <span data-ttu-id="366ed-510">BEEU21</span><span class="sxs-lookup"><span data-stu-id="366ed-510">BEEU21</span></span>             |                   |                   |                       |                       | <span data-ttu-id="366ed-511">81</span><span class="sxs-lookup"><span data-stu-id="366ed-511">81</span></span>                       | <span data-ttu-id="366ed-512">86</span><span class="sxs-lookup"><span data-stu-id="366ed-512">86</span></span>                 | <span data-ttu-id="366ed-513">59</span><span class="sxs-lookup"><span data-stu-id="366ed-513">59</span></span>          | <span data-ttu-id="366ed-514">55</span><span class="sxs-lookup"><span data-stu-id="366ed-514">55</span></span>                 |
| <span data-ttu-id="366ed-515">BEEU12</span><span class="sxs-lookup"><span data-stu-id="366ed-515">BEEU12</span></span>             |                   |                   |                       |                       | <span data-ttu-id="366ed-516">81</span><span class="sxs-lookup"><span data-stu-id="366ed-516">81</span></span>                       | <span data-ttu-id="366ed-517">86</span><span class="sxs-lookup"><span data-stu-id="366ed-517">86</span></span>                 | <span data-ttu-id="366ed-518">59</span><span class="sxs-lookup"><span data-stu-id="366ed-518">59</span></span>          | <span data-ttu-id="366ed-519">55</span><span class="sxs-lookup"><span data-stu-id="366ed-519">55</span></span>                 |
| <span data-ttu-id="366ed-520">BEEU6</span><span class="sxs-lookup"><span data-stu-id="366ed-520">BEEU6</span></span>              |                   |                   |                       |                       | <span data-ttu-id="366ed-521">81</span><span class="sxs-lookup"><span data-stu-id="366ed-521">81</span></span>                       | <span data-ttu-id="366ed-522">86</span><span class="sxs-lookup"><span data-stu-id="366ed-522">86</span></span>                 | <span data-ttu-id="366ed-523">59</span><span class="sxs-lookup"><span data-stu-id="366ed-523">59</span></span>          | <span data-ttu-id="366ed-524">55</span><span class="sxs-lookup"><span data-stu-id="366ed-524">55</span></span>                 |
| <span data-ttu-id="366ed-525">BEEUS</span><span class="sxs-lookup"><span data-stu-id="366ed-525">BEEUS</span></span>              |                   | <span data-ttu-id="366ed-526">46</span><span class="sxs-lookup"><span data-stu-id="366ed-526">46</span></span>                |                       |                       |                          |                    |             |                    |

6.  <span data-ttu-id="366ed-527">Sur la page **Codes taxe**, dans l’organisateur **Paramétrage d’état – avoir**, affectez des codes déclaration aux codes taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-527">On the **Sales tax codes** page, on the **Report setup – credit note** FastTab, assign reporting codes to sales tax codes.</span></span>

<span data-ttu-id="366ed-528">Le tableau suivant montre comment affecter les codes déclaration de taxe aux codes taxe.</span><span class="sxs-lookup"><span data-stu-id="366ed-528">The following table shows how to assign the sales tax reporting codes to sales tax codes.</span></span>

| <span data-ttu-id="366ed-529">**Code taxe**</span><span class="sxs-lookup"><span data-stu-id="366ed-529">**Sales tax code**</span></span> | <span data-ttu-id="366ed-530">**Ventes soumises à taxe CN**</span><span class="sxs-lookup"><span data-stu-id="366ed-530">**Taxable sales CN**</span></span> | <span data-ttu-id="366ed-531">**Vente détaxée CN**</span><span class="sxs-lookup"><span data-stu-id="366ed-531">**Tax-free sale CN**</span></span> | <span data-ttu-id="366ed-532">**Taxe collectée CN**</span><span class="sxs-lookup"><span data-stu-id="366ed-532">**Sales tax payable CN**</span></span> | <span data-ttu-id="366ed-533">**Achats soumis à taxe CN**</span><span class="sxs-lookup"><span data-stu-id="366ed-533">**Taxable purchases CN**</span></span> | <span data-ttu-id="366ed-534">**Taxe déductible CN**</span><span class="sxs-lookup"><span data-stu-id="366ed-534">**Sales tax receivable CN**</span></span> | <span data-ttu-id="366ed-535">**Importation soumise à taxe CN**</span><span class="sxs-lookup"><span data-stu-id="366ed-535">**Taxable import CN**</span></span> | <span data-ttu-id="366ed-536">**Taxe d’utilisation CN**</span><span class="sxs-lookup"><span data-stu-id="366ed-536">**Use tax CN**</span></span> | <span data-ttu-id="366ed-537">**Contrepartie taxe d’utilisation CN**</span><span class="sxs-lookup"><span data-stu-id="366ed-537">**Offset use tax CN**</span></span> |
|--------------------|----------------------|----------------------|--------------------------|--------------------------|-----------------------------|-----------------------|----------------|-----------------------|
| <span data-ttu-id="366ed-538">BEEU21</span><span class="sxs-lookup"><span data-stu-id="366ed-538">BEEU21</span></span>             |                      |                      |                          |                          | <span data-ttu-id="366ed-539">8184</span><span class="sxs-lookup"><span data-stu-id="366ed-539">8184</span></span>                        | <span data-ttu-id="366ed-540">86</span><span class="sxs-lookup"><span data-stu-id="366ed-540">86</span></span>                    | <span data-ttu-id="366ed-541">59</span><span class="sxs-lookup"><span data-stu-id="366ed-541">59</span></span>             | <span data-ttu-id="366ed-542">55</span><span class="sxs-lookup"><span data-stu-id="366ed-542">55</span></span>                    |
| <span data-ttu-id="366ed-543">BEEU12</span><span class="sxs-lookup"><span data-stu-id="366ed-543">BEEU12</span></span>             |                      |                      |                          |                          | <span data-ttu-id="366ed-544">8184</span><span class="sxs-lookup"><span data-stu-id="366ed-544">8184</span></span>                        | <span data-ttu-id="366ed-545">86</span><span class="sxs-lookup"><span data-stu-id="366ed-545">86</span></span>                    | <span data-ttu-id="366ed-546">59</span><span class="sxs-lookup"><span data-stu-id="366ed-546">59</span></span>             | <span data-ttu-id="366ed-547">55</span><span class="sxs-lookup"><span data-stu-id="366ed-547">55</span></span>                    |
| <span data-ttu-id="366ed-548">BEEU6</span><span class="sxs-lookup"><span data-stu-id="366ed-548">BEEU6</span></span>              |                      |                      |                          |                          | <span data-ttu-id="366ed-549">8184</span><span class="sxs-lookup"><span data-stu-id="366ed-549">8184</span></span>                        | <span data-ttu-id="366ed-550">86</span><span class="sxs-lookup"><span data-stu-id="366ed-550">86</span></span>                    | <span data-ttu-id="366ed-551">59</span><span class="sxs-lookup"><span data-stu-id="366ed-551">59</span></span>             | <span data-ttu-id="366ed-552">55</span><span class="sxs-lookup"><span data-stu-id="366ed-552">55</span></span>                    |

<span data-ttu-id="366ed-553">Au lieu des codes **55** et **59**, vous pouvez utiliser les codes correctifs **63** et **64**.</span><span class="sxs-lookup"><span data-stu-id="366ed-553">Instead of codes **55** and **59**, you can use corrective codes **63** and **64**.</span></span>

> [!NOTE]
> <span data-ttu-id="366ed-554">La configuration précédente n’est qu’un exemple et dépend de la structure des codes taxe utilisés.</span><span class="sxs-lookup"><span data-stu-id="366ed-554">The preceding configuration is just an example and depends on the structure of the sales tax codes that are used.</span></span> <span data-ttu-id="366ed-555">Si vous souhaitez que les valeurs soient calculées et transférées dans la déclaration de taxe, pour chaque code taxe utilisé dans le processus de paiement de la taxe, vous devez définir un code déclaration de taxe approprié dans un ou plusieurs champs de l’onglet **Paramétrage d’état**.</span><span class="sxs-lookup"><span data-stu-id="366ed-555">If you want values to be calculated and transferred to the sales tax report, for each tax code that is used in the sales tax payment process, you must set a relevant sales tax reporting code in one or more fields on the **Report setup** tab.</span></span>

7.  <span data-ttu-id="366ed-556">Validez les transactions suivantes.</span><span class="sxs-lookup"><span data-stu-id="366ed-556">Post the following transactions.</span></span> <span data-ttu-id="366ed-557">Par exemple, pour les factures client, allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.</span><span class="sxs-lookup"><span data-stu-id="366ed-557">For example, for customer invoices, go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span> <span data-ttu-id="366ed-558">Pour les factures fournisseur, allez dans **Comptabilité fournisseur** \> **Factures** \> **Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="366ed-558">For vendor invoices, go to **Accounts payable** \> **Invoices** \> **Invoice journal**.</span></span>

| <span data-ttu-id="366ed-559">**Date**</span><span class="sxs-lookup"><span data-stu-id="366ed-559">**Date**</span></span>         | <span data-ttu-id="366ed-560">**Type de transaction**</span><span class="sxs-lookup"><span data-stu-id="366ed-560">**Transaction type**</span></span>  | <span data-ttu-id="366ed-561">**Montant net**</span><span class="sxs-lookup"><span data-stu-id="366ed-561">**Amount net**</span></span> | <span data-ttu-id="366ed-562">**Montant de la TVA**</span><span class="sxs-lookup"><span data-stu-id="366ed-562">**VAT amount**</span></span> | <span data-ttu-id="366ed-563">**Code taxe**</span><span class="sxs-lookup"><span data-stu-id="366ed-563">**Sales tax code**</span></span> | <span data-ttu-id="366ed-564">**Base de taxe prévue – code de déclaration**</span><span class="sxs-lookup"><span data-stu-id="366ed-564">**Expected tax base – reporting code**</span></span>                 | <span data-ttu-id="366ed-565">**Montant de taxe prévu – code de déclaration**</span><span class="sxs-lookup"><span data-stu-id="366ed-565">**Expected tax amount – reporting code**</span></span> |
|------------------|-----------------------|----------------|----------------|--------------------|--------------------------------------------------------|------------------------------------------|
| <span data-ttu-id="366ed-566">1 février 2020</span><span class="sxs-lookup"><span data-stu-id="366ed-566">February 1, 2020</span></span> | <span data-ttu-id="366ed-567">Facture client</span><span class="sxs-lookup"><span data-stu-id="366ed-567">Customer invoice</span></span>      | <span data-ttu-id="366ed-568">1,100</span><span class="sxs-lookup"><span data-stu-id="366ed-568">1,100</span></span>          | <span data-ttu-id="366ed-569">132</span><span class="sxs-lookup"><span data-stu-id="366ed-569">132</span></span>            | <span data-ttu-id="366ed-570">BE12</span><span class="sxs-lookup"><span data-stu-id="366ed-570">BE12</span></span>               | <span data-ttu-id="366ed-571">02</span><span class="sxs-lookup"><span data-stu-id="366ed-571">02</span></span>                                                     | <span data-ttu-id="366ed-572">54</span><span class="sxs-lookup"><span data-stu-id="366ed-572">54</span></span>                                       |
| <span data-ttu-id="366ed-573">1 février 2020</span><span class="sxs-lookup"><span data-stu-id="366ed-573">February 1, 2020</span></span> | <span data-ttu-id="366ed-574">Facture fournisseur (UE)</span><span class="sxs-lookup"><span data-stu-id="366ed-574">Vendor invoice (EU)</span></span>   | <span data-ttu-id="366ed-575">1 000</span><span class="sxs-lookup"><span data-stu-id="366ed-575">1,000</span></span>          | <span data-ttu-id="366ed-576">210</span><span class="sxs-lookup"><span data-stu-id="366ed-576">210</span></span>            | <span data-ttu-id="366ed-577">BEEU21</span><span class="sxs-lookup"><span data-stu-id="366ed-577">BEEU21</span></span>             | <span data-ttu-id="366ed-578">86 - Base à payer 81 - Déduction de base</span><span class="sxs-lookup"><span data-stu-id="366ed-578">86 – Base payable 81 – Base deduction</span></span>                  | <span data-ttu-id="366ed-579">55 - Taxe à payer 59 - Déduction de taxe</span><span class="sxs-lookup"><span data-stu-id="366ed-579">55 – Tax payable 59 – Tax deduction</span></span>      |
| <span data-ttu-id="366ed-580">2 février 2020</span><span class="sxs-lookup"><span data-stu-id="366ed-580">February 2, 2020</span></span> | <span data-ttu-id="366ed-581">Facture fournisseur (UE)</span><span class="sxs-lookup"><span data-stu-id="366ed-581">Vendor invoice (EU)</span></span>   | <span data-ttu-id="366ed-582">\-200</span><span class="sxs-lookup"><span data-stu-id="366ed-582">\-200</span></span>          | <span data-ttu-id="366ed-583">\-42</span><span class="sxs-lookup"><span data-stu-id="366ed-583">\-42</span></span>           | <span data-ttu-id="366ed-584">BEEU21</span><span class="sxs-lookup"><span data-stu-id="366ed-584">BEEU21</span></span>             | <span data-ttu-id="366ed-585">86 - Base à payer 81 - Déduction de base 84 - Base de crédit</span><span class="sxs-lookup"><span data-stu-id="366ed-585">86 – Base payable 81 – Base deduction 84 – Credit base</span></span> | <span data-ttu-id="366ed-586">55 - Taxe à payer 59 - Déduction de taxe</span><span class="sxs-lookup"><span data-stu-id="366ed-586">55 – Tax payable 59 – Tax deduction</span></span>      |
| <span data-ttu-id="366ed-587">1 février 2020</span><span class="sxs-lookup"><span data-stu-id="366ed-587">February 1, 2020</span></span> | <span data-ttu-id="366ed-588">Facture client (UE)</span><span class="sxs-lookup"><span data-stu-id="366ed-588">Customer invoice (EU)</span></span> | <span data-ttu-id="366ed-589">100</span><span class="sxs-lookup"><span data-stu-id="366ed-589">100</span></span>            | <span data-ttu-id="366ed-590">0</span><span class="sxs-lookup"><span data-stu-id="366ed-590">0</span></span>              | <span data-ttu-id="366ed-591">BEEUS</span><span class="sxs-lookup"><span data-stu-id="366ed-591">BEEUS</span></span>              | <span data-ttu-id="366ed-592">46</span><span class="sxs-lookup"><span data-stu-id="366ed-592">46</span></span>                                                     | <span data-ttu-id="366ed-593">Non applicable</span><span class="sxs-lookup"><span data-stu-id="366ed-593">Not applicable</span></span>                           |

8.  <span data-ttu-id="366ed-594">Allez dans **Taxe \> Déclarations \> Taxe \> État de la taxe pour la période de règlement**.</span><span class="sxs-lookup"><span data-stu-id="366ed-594">Go to **Tax \> Declarations \> Sales tax \> Report sales tax for settlement period**.</span></span>
9.  <span data-ttu-id="366ed-595">Dans la boite de dialogue **État de la taxe pour la période de règlement**, dans le champ **Version de paiement de la taxe**, sélectionnez **Original**.</span><span class="sxs-lookup"><span data-stu-id="366ed-595">In the **Report sales tax for settlement period** dialog box, in the **Sales tax payment version** field, select **Original**.</span></span>
10.  <span data-ttu-id="366ed-596">Cliquez sur **OK** et passez en revue les données.</span><span class="sxs-lookup"><span data-stu-id="366ed-596">Select **OK**, and review the data.</span></span>

![Page Déclaration de taxe INTERVAT générée](media/4_Intervat_tax_declaration.png)

<span data-ttu-id="366ed-598">Notez que le montant de l’avoir est indiqué dans le code **84**.</span><span class="sxs-lookup"><span data-stu-id="366ed-598">Notice that the amount of the credit note is shown in code **84**.</span></span>

11.  <span data-ttu-id="366ed-599">Allez dans **Taxe \> Déclarations \> Taxe \> Zones de déclaration de taxe supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="366ed-599">Go to **Tax \> Declarations \> Sales tax \> Additional sales tax report boxes**.</span></span>
12.  <span data-ttu-id="366ed-600">Cliquez sur **Nouveau** pour créer une ligne pour février 2020.</span><span class="sxs-lookup"><span data-stu-id="366ed-600">Select **New** to create a line for February 2020.</span></span>
13.  <span data-ttu-id="366ed-601">Sélectionnez **Corrections de taxe \> Ajustements** et créez une ligne.</span><span class="sxs-lookup"><span data-stu-id="366ed-601">Select **Tax corrections \> Adjustments**, and create a line.</span></span>

![Page Ajustements](media/5_Adjustments.png)

14.  <span data-ttu-id="366ed-603">Allez dans **Taxe** \> **Déclarations** \> **Taxe** \> **Régler et valider la taxe**.</span><span class="sxs-lookup"><span data-stu-id="366ed-603">Go to **Tax** \> **Declarations** \> **Sales tax** \> **Settle and post sales tax**.</span></span>
15.  <span data-ttu-id="366ed-604">Dans la boite de dialogue **Régler et valider la taxe**, dans le champ **Version de paiement de la taxe**, sélectionnez **Original**.</span><span class="sxs-lookup"><span data-stu-id="366ed-604">In the **Settle and post sales tax** dialog box, in the **Sales tax payment version** field, select **Original**.</span></span>
16.  <span data-ttu-id="366ed-605">Allez dans **Taxe** \> **Déclarations** \> **Taxe** \> **Déclaration de taxe INTERVAT**.</span><span class="sxs-lookup"><span data-stu-id="366ed-605">Go to **Tax** \> **Declarations** \> **Sales tax** \> **INTERVAT tax declaration**.</span></span>
17.  <span data-ttu-id="366ed-606">Sélectionnez **Nouvelle déclaration**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="366ed-606">Select **New declaration**, set the following values:</span></span>

   -   <span data-ttu-id="366ed-607">**Période de règlement :** MEN</span><span class="sxs-lookup"><span data-stu-id="366ed-607">**Settlement period:** MEN</span></span>
   -   <span data-ttu-id="366ed-608">**Date de début :** 1/2/2020 (1 février 2020)</span><span class="sxs-lookup"><span data-stu-id="366ed-608">**From date:** 2/1/2020 (February 1, 2020)</span></span>
   -   <span data-ttu-id="366ed-609">**Date de la transaction :** 29/02/2020 (29 février 2020)</span><span class="sxs-lookup"><span data-stu-id="366ed-609">**Transaction date:** 2/29/2020 (February 29, 2020)</span></span>
   -   <span data-ttu-id="366ed-610">**Mettre à jour :** Non</span><span class="sxs-lookup"><span data-stu-id="366ed-610">**Update:** No</span></span>
   -   <span data-ttu-id="366ed-611">**Mise en correspondance des formats :** Format INTERVAT (BE)</span><span class="sxs-lookup"><span data-stu-id="366ed-611">**Format mapping:** INTERVAT format (BE)</span></span>

![Page Déclaration de taxe INTERVAT](media/6_Intervat.png)

18.  <span data-ttu-id="366ed-613">Cliquez sur **OK**, ouvrez le fichier et examinez le rapport.</span><span class="sxs-lookup"><span data-stu-id="366ed-613">Select **OK**, open the file, and review the report.</span></span>

![État de déclaration de taxe INTERVAT au format xml](media/7_Intervat_XML.png)

19.  <span data-ttu-id="366ed-615">Sélectionnez **Détails** et examinez les données.</span><span class="sxs-lookup"><span data-stu-id="366ed-615">Select **Details**, and review the data.</span></span>

![Page Détails INTERVAT](media/8_Intervat_details.png)

<span data-ttu-id="366ed-617">Notez que le montant du code **62** est égal à **200**.</span><span class="sxs-lookup"><span data-stu-id="366ed-617">Notice that the amount in **62** code equals **200**.</span></span>
    
## <a name="reconciliation-reports-for-belgium"></a><span data-ttu-id="366ed-618">États de rapprochement pour la Belgique</span><span class="sxs-lookup"><span data-stu-id="366ed-618">Reconciliation reports for Belgium</span></span>

<span data-ttu-id="366ed-619">Pour plus d’informations sur les états de rapprochement pour la Belgique, voir [États de rapprochement pour la Belgique](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/localizations/emea-bel-reconciliation-reports.md).</span><span class="sxs-lookup"><span data-stu-id="366ed-619">For information about reconciliation reports for Belgium, see [Reconciliation reports for Belgium](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/localizations/emea-bel-reconciliation-reports.md).</span></span>




