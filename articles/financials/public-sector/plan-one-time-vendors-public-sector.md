---
title: Planifier pour les fournisseurs occasionnels dans le secteur public
description: "Cet article fournit des informations sur l'importation et la création de fournisseurs occasionnels et de factures."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerTransVoucher, SysConfiguration, Tax1099Summary, VendTableListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 27251
ms.assetid: 936570cb-932f-4027-b3c7-2235ad79bc1c
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 495f867385d4f842e9cdd2c78432ccdcd27919cd
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---

# <a name="plan-for-one-time-vendors-in-the-public-sector"></a><span data-ttu-id="87077-103">Planifier pour les fournisseurs occasionnels dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="87077-103">Plan for one-time vendors in the public sector</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="87077-104">Cet article fournit des informations sur l'importation et la création de fournisseurs occasionnels et de factures.</span><span class="sxs-lookup"><span data-stu-id="87077-104">This article explains how to prepare to import and create multiple one-time vendors and invoices.</span></span> 

<span data-ttu-id="87077-105">Généralement, si vous planifiez d'importer en masse des informations facturation et sur les fournisseurs, vous commencez par créer un fichier de données au format feuille de calcul et l'enregistrez au format CSV (valeurs séparées par des virgules).</span><span class="sxs-lookup"><span data-stu-id="87077-105">Typically, if you plan to mass-import vendor and invoice information, you first create a data file in spreadsheet format and save it in CSV (comma-separated values) format.</span></span>

-   <span data-ttu-id="87077-106">Étant donné que les virgules sont utilisées pour séparer les champs dans un fichier CSV, n'utilisez pas les virgules dans le texte d'une entrée.</span><span class="sxs-lookup"><span data-stu-id="87077-106">Because commas are used to separate the fields in a CSV file, don't use commas in the text of an entry.</span></span> <span data-ttu-id="87077-107">Par exemple, si vous souhaitez spécifier le nom de la société « Smith, Smith, and Jones », entrez-la le en tant que **Smith Smith and Jones**.</span><span class="sxs-lookup"><span data-stu-id="87077-107">For example, to specify a company name of “Smith, Smith, and Jones,” enter it as **Smith Smith and Jones**.</span></span>
-   <span data-ttu-id="87077-108">Si vous ne définissez pas de valeurs pour les champs de cette page, les comptes fournisseur nouvellement créés utilisent les valeurs du profil fournisseur occasionnel référencé dans la page **Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="87077-108">If you don't set values for fields on this page, the newly created vendor accounts use values from the one-time vendor profile that is referenced on the **Accounts payable parameters** page.</span></span> <span data-ttu-id="87077-109">Par exemple, si le mode de paiement est défini sur **Chèque** pour le profil du fournisseur occasionnel dans la page **Paramètres de la comptabilité fournisseur**, ce mode de paiement sera également défini pour les fournisseurs occasionnels que vous ajouterez.</span><span class="sxs-lookup"><span data-stu-id="87077-109">For example, if the method of payment is set to **Check** for the one-time vendor profile on the **Accounts payable parameters** page, that method of payment will also be set for the one-time vendors that you're adding.</span></span>
-   <span data-ttu-id="87077-110">La souche de numéros de la Comptabilité fournisseur **Fournisseur occasionnel** permet d'affecter les comptes des fournisseurs occasionnels et ne doit pas être défini sur **Continu** pour ce service.</span><span class="sxs-lookup"><span data-stu-id="87077-110">The **One-time supplier** Accounts payable number sequence is used to assign the one-time vendor accounts and must not be set to **Continuous** for this service.</span></span> <span data-ttu-id="87077-111">Les factures sont générées dans un état de brouillon.</span><span class="sxs-lookup"><span data-stu-id="87077-111">Invoices are generated in a draft state.</span></span> <span data-ttu-id="87077-112">Avant de créer des propositions de paiement, vous devez valider les factures.</span><span class="sxs-lookup"><span data-stu-id="87077-112">Before you create payment proposals for payment, you must post the invoices.</span></span>

<span data-ttu-id="87077-113">Le tableau suivant répertorie les champs que le fichier d'importation doit contenir.</span><span class="sxs-lookup"><span data-stu-id="87077-113">The following table show the fields that the import file must contain.</span></span> <span data-ttu-id="87077-114">Chaque nom de champ est équivalent à un en-tête de colonne dans une feuille de calcul, et chaque ligne de la feuille de calcul contient les données pour chaque colonne applicable.</span><span class="sxs-lookup"><span data-stu-id="87077-114">Each field label is equivalent to a column heading in a spreadsheet, and each spreadsheet row contains the data for each applicable column.</span></span>

<span data-ttu-id="87077-115">**Section du fournisseur**</span><span class="sxs-lookup"><span data-stu-id="87077-115">**Vendor section**</span></span>

| <span data-ttu-id="87077-116">Champ</span><span class="sxs-lookup"><span data-stu-id="87077-116">Field</span></span>                                          | <span data-ttu-id="87077-117">Détails</span><span class="sxs-lookup"><span data-stu-id="87077-117">Details</span></span>                                                 |
|------------------------------------------------|---------------------------------------------------------|
|<span data-ttu-id="87077-118">Type d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="87077-118">Record type</span></span>                                     | <span data-ttu-id="87077-119">**Personne** ou **Organisation**</span><span class="sxs-lookup"><span data-stu-id="87077-119">**Person** or **Organization**</span></span>                          |
| <span data-ttu-id="87077-120">Prénom</span><span class="sxs-lookup"><span data-stu-id="87077-120">First name</span></span>                                     | <span data-ttu-id="87077-121">(Si la valeur du type d'enregistrement est **Personne**)</span><span class="sxs-lookup"><span data-stu-id="87077-121">(If the record type value is **Person**)</span></span>                |
| <span data-ttu-id="87077-122">Deuxième prénom (facultatif)</span><span class="sxs-lookup"><span data-stu-id="87077-122">Middle name (Optional)</span></span>                         | <span data-ttu-id="87077-123">(Si le type d'enregistrement est **Personne**)</span><span class="sxs-lookup"><span data-stu-id="87077-123">(If the record type is **Person**)</span></span>                      |
| <span data-ttu-id="87077-124">Nom</span><span class="sxs-lookup"><span data-stu-id="87077-124">Last name</span></span>                                      | <span data-ttu-id="87077-125">(Si le type d'enregistrement est **Personne**)</span><span class="sxs-lookup"><span data-stu-id="87077-125">(If the record type is **Person**)</span></span>                      |
| <span data-ttu-id="87077-126">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="87077-126">Vendor name</span></span>                                    | <span data-ttu-id="87077-127">(Si le type d'enregistrement est **Organisation**)</span><span class="sxs-lookup"><span data-stu-id="87077-127">(If the record type is **Organization**)</span></span>                |
| <span data-ttu-id="87077-128">Groupe</span><span class="sxs-lookup"><span data-stu-id="87077-128">Group</span></span>                                          | <span data-ttu-id="87077-129">Limité à dix caractères</span><span class="sxs-lookup"><span data-stu-id="87077-129">Ten-character limit</span></span>                                     |
| <span data-ttu-id="87077-130">Pays/Région</span><span class="sxs-lookup"><span data-stu-id="87077-130">Country/region</span></span>                                 | <span data-ttu-id="87077-131">Limité à dix caractères</span><span class="sxs-lookup"><span data-stu-id="87077-131">Ten-character limit</span></span>                                     |
| <span data-ttu-id="87077-132">Code postal</span><span class="sxs-lookup"><span data-stu-id="87077-132">ZIP/postal code</span></span>                                |                                                         |
| <span data-ttu-id="87077-133">Rue</span><span class="sxs-lookup"><span data-stu-id="87077-133">Street</span></span>                                         |                                                         |
| <span data-ttu-id="87077-134">Ville</span><span class="sxs-lookup"><span data-stu-id="87077-134">City</span></span>                                           |                                                         |
| <span data-ttu-id="87077-135">Ville</span><span class="sxs-lookup"><span data-stu-id="87077-135">City</span></span>                                           |                                                         |
|<span data-ttu-id="87077-136">ID taxe fédérale (facultatif)</span><span class="sxs-lookup"><span data-stu-id="87077-136">Federal tax ID (Optional)</span></span>                       | <span data-ttu-id="87077-137">(États-Unis uniquement) nombre 1099</span><span class="sxs-lookup"><span data-stu-id="87077-137">(U.S. only) 1099 number</span></span>                                 |
| <span data-ttu-id="87077-138">Type d'ID taxe</span><span class="sxs-lookup"><span data-stu-id="87077-138">Tax ID type</span></span>                                    | <span data-ttu-id="87077-139">(États-unis uniquement). Les valeurs peuvent être **Inconnu**, **Numéro d'identification de l'employeur**, **Numéro de Sécurité sociale**, **Numéro d'identification du contribuable individuel** ou **Numéro d'identification du contribuable choisi**.</span><span class="sxs-lookup"><span data-stu-id="87077-139">(U.S. only) Values can be **Unknown**, **Employer Identification Number**, **Social Security Number**, **Individual Taxpayer Identification Number**, or **Adopted Tax Payer Identification Number**.</span></span>  <span data-ttu-id="87077-140">**Remarque :** si aucun ID taxe fédérale n'est indiqué, ce champ doit être défini sur **Inconnu**.</span><span class="sxs-lookup"><span data-stu-id="87077-140">**Note:** If no federal tax ID is provided, this field should be set to **Unknown**.</span></span>                                               |
| <span data-ttu-id="87077-141">Compte bancaire (facultatif)</span><span class="sxs-lookup"><span data-stu-id="87077-141">Bank account (Optional)</span></span>                        | <span data-ttu-id="87077-142">Nom du compte bancaire</span><span class="sxs-lookup"><span data-stu-id="87077-142">Bank account name</span></span>                                       |
| <span data-ttu-id="87077-143">Numéro de compte bancaire</span><span class="sxs-lookup"><span data-stu-id="87077-143">Bank account number</span></span>                            |                                                         |
| <span data-ttu-id="87077-144">Numéro d'acheminement (facultatif)</span><span class="sxs-lookup"><span data-stu-id="87077-144">Routing number (Optional)</span></span>                      |                                                         |
| <span data-ttu-id="87077-145">Code SWIFT (facultatif)</span><span class="sxs-lookup"><span data-stu-id="87077-145">SWIFT code (Optional)</span></span>                          | <span data-ttu-id="87077-146">Également appelé BIC (Bank Identifier Code)</span><span class="sxs-lookup"><span data-stu-id="87077-146">Also known as BIC (Bank identifier code)</span></span>                |
|<span data-ttu-id="87077-147">Code IBAN (facultatif)</span><span class="sxs-lookup"><span data-stu-id="87077-147">IBAN (Optional)</span></span>                                 | <span data-ttu-id="87077-148">Numéro de compte bancaire international, limité à 34 caractères.</span><span class="sxs-lookup"><span data-stu-id="87077-148">International bank account number, 34-character limit</span></span>   |



<span data-ttu-id="87077-149">**Section de facture**</span><span class="sxs-lookup"><span data-stu-id="87077-149">**Invoice section**</span></span>

| <span data-ttu-id="87077-150">Champ</span><span class="sxs-lookup"><span data-stu-id="87077-150">Field</span></span>                                                | <span data-ttu-id="87077-151">Détails</span><span class="sxs-lookup"><span data-stu-id="87077-151">Details</span></span>                                           |
|------------------------------------------------------|---------------------------------------------------|
| <span data-ttu-id="87077-152">Numéro de facture</span><span class="sxs-lookup"><span data-stu-id="87077-152">Invoice number</span></span>                                       | <span data-ttu-id="87077-153">Numéro de facture ; limité à 20 caractères</span><span class="sxs-lookup"><span data-stu-id="87077-153">Invoice number, 20-character limit</span></span>                |
| <span data-ttu-id="87077-154">Description de facture (facultative)</span><span class="sxs-lookup"><span data-stu-id="87077-154">Invoice description (Optional)</span></span>                       |                                                   |
| <span data-ttu-id="87077-155">Date de validation (facultative)</span><span class="sxs-lookup"><span data-stu-id="87077-155">Posting date (Optional)</span></span>                              | <span data-ttu-id="87077-156">Format de date</span><span class="sxs-lookup"><span data-stu-id="87077-156">Date format</span></span>                                       |
| <span data-ttu-id="87077-157">Date de facture</span><span class="sxs-lookup"><span data-stu-id="87077-157">Invoice date</span></span>                                         | <span data-ttu-id="87077-158">Format de date</span><span class="sxs-lookup"><span data-stu-id="87077-158">Date format</span></span>                                       |
| <span data-ttu-id="87077-159">Date d'échéance (facultative)</span><span class="sxs-lookup"><span data-stu-id="87077-159">Due date (Optional)</span></span>                                  | <span data-ttu-id="87077-160">Format de date</span><span class="sxs-lookup"><span data-stu-id="87077-160">Date format</span></span>                                       |
| <span data-ttu-id="87077-161">Numéro de ligne</span><span class="sxs-lookup"><span data-stu-id="87077-161">Line number</span></span>                                          |                                                   |
|<span data-ttu-id="87077-162">Numéro d'article (facultatif)</span><span class="sxs-lookup"><span data-stu-id="87077-162">Item number (Optional)</span></span>                                | <span data-ttu-id="87077-163">Limité à 20 caractères   **Remarque :** si aucun numéro d'article n'est fourni, vous devez indiquer des valeurs dans les champs **Catégorie d'approvisionnement** et **Hiérarchie des catégories d'approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="87077-163">20-character limit   **Note:** If no item number is provided, you must provide values in the **Procurement category** and **Procurement category hierarchy** fields.</span></span> <span data-ttu-id="87077-164">Si aucune valeur de catégorie d'approvisionnement ou de hiérarchie de catégorie d'approvisionnement n'est fournie, vous devez fournir une valeur dans le champ **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="87077-164">If no procurement category and procurement category hierarchy are provided, you must provide a value in the **Item number** field.</span></span>                    |
| <span data-ttu-id="87077-165">Nom de l'article (facultatif)</span><span class="sxs-lookup"><span data-stu-id="87077-165">Item name (Optional)</span></span>                                 |  <span data-ttu-id="87077-166">Limité à 60 caractères</span><span class="sxs-lookup"><span data-stu-id="87077-166">60-character limit</span></span>                               |
| <span data-ttu-id="87077-167">Hiérarchie de catégories d'approvisionnement (facultative)</span><span class="sxs-lookup"><span data-stu-id="87077-167">Procurement category hierarchy (Optional)</span></span>            |    <span data-ttu-id="87077-168">**Remarque :** si vous indiquez une valeur pour ce champ, le champ **Catégorie d'approvisionnement** est également obligatoire.</span><span class="sxs-lookup"><span data-stu-id="87077-168">**Note:** If you provide a value for this field, the **Procurement category** field is also required.</span></span>                                                                         |
| <span data-ttu-id="87077-169">Catégorie d'approvisionnement (facultative)</span><span class="sxs-lookup"><span data-stu-id="87077-169">Procurement category (Optional)</span></span>                      | <span data-ttu-id="87077-170">**Remarque :** si vous indiquez une valeur pour ce champ, le champ **Hiérarchie de catégories d'approvisionnement** est également obligatoire.</span><span class="sxs-lookup"><span data-stu-id="87077-170">**Note:** If you provide a value for this field, the **Procurement category hierarchy** field is also required.</span></span>                                                                        |
| <span data-ttu-id="87077-171">Quantité (facultative)</span><span class="sxs-lookup"><span data-stu-id="87077-171">Quantity (Optional)</span></span>                                  |                                                   |
| <span data-ttu-id="87077-172">Unité (facultative)</span><span class="sxs-lookup"><span data-stu-id="87077-172">Unit (Optional)</span></span>                                      | <span data-ttu-id="87077-173">Limité à dix caractères</span><span class="sxs-lookup"><span data-stu-id="87077-173">Ten-character limit</span></span>                               |
|<span data-ttu-id="87077-174">Montant net de ligne</span><span class="sxs-lookup"><span data-stu-id="87077-174">Line net amount</span></span>                                       | <span data-ttu-id="87077-175">Les valeurs décimales sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="87077-175">Decimal values are allowed.</span></span>                       |
| <span data-ttu-id="87077-176">Prix unitaire (facultatif)</span><span class="sxs-lookup"><span data-stu-id="87077-176">Unit price (Optional)</span></span>                                | <span data-ttu-id="87077-177">Les valeurs décimales sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="87077-177">Decimal values are allowed.</span></span>                       |


<span data-ttu-id="87077-178">**Section de distribution**</span><span class="sxs-lookup"><span data-stu-id="87077-178">**Distributions section**</span></span>
| <span data-ttu-id="87077-179">Champ</span><span class="sxs-lookup"><span data-stu-id="87077-179">Field</span></span>                                                | <span data-ttu-id="87077-180">Détails</span><span class="sxs-lookup"><span data-stu-id="87077-180">Details</span></span>                                  |
|------------------------------------------------------|------------------------------------------|
| <span data-ttu-id="87077-181">Nombre</span><span class="sxs-lookup"><span data-stu-id="87077-181">Number</span></span>                                               | <span data-ttu-id="87077-182">Numéro de ligne de répartition comptable</span><span class="sxs-lookup"><span data-stu-id="87077-182">Accounting distribution line number</span></span>      |
| <span data-ttu-id="87077-183">Compte général</span><span class="sxs-lookup"><span data-stu-id="87077-183">Ledger account</span></span>                                       |                                          |
| <span data-ttu-id="87077-184">Pourcentage</span><span class="sxs-lookup"><span data-stu-id="87077-184">Percent</span></span>                                              | <span data-ttu-id="87077-185">Les valeurs décimales sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="87077-185">Decimal values are allowed.</span></span>              |




## <a name="what-do-i-do-next"></a><span data-ttu-id="87077-186">Que faire ensuite ?</span><span class="sxs-lookup"><span data-stu-id="87077-186">What do I do next?</span></span>
<span data-ttu-id="87077-187">Après avoir paramétré les conditions préalables nécessaires, consultez [Fournisseurs occasionnels dans le secteur public](one-time-vendors-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="87077-187">After you’ve set up the prerequisites that you require, see [One time vendors in the public sector](one-time-vendors-public-sector.md).</span></span>

<a name="see-also"></a><span data-ttu-id="87077-188">Voir également :</span><span class="sxs-lookup"><span data-stu-id="87077-188">See also</span></span>
--------

[<span data-ttu-id="87077-189">Fournisseurs occasionnels dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="87077-189">One-time vendors in the public sector</span></span>](one-time-vendors-public-sector.md)

[<span data-ttu-id="87077-190">Comptabilité fournisseur dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="87077-190">Accounts payable in the public sector</span></span>](accounts-payable-public-sector.md)




