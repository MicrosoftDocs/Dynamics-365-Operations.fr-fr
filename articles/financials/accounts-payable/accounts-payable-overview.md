---
title: "Configuration du module Comptabilité fournisseur"
description: "Cet article décrit les pages que vous utilisez pour paramétrer les fonctionnalités de base et facultatives pour la Comptabilité fournisseur dans Microsoft Dynamics 365 for Finance and Operations. Il décrit également les étapes de paramétrage que vous devez effectuer avant de commencer à configurer la Comptabilité fournisseur."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 60313da23fdbd5a06b71c7c91a236165f8f189de
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="configure-accounts-payable"></a><span data-ttu-id="00120-104">Configuration du module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="00120-104">Configure Accounts payable</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="00120-105">Cet article décrit les pages que vous utilisez pour paramétrer les fonctionnalités de base et facultatives pour la Comptabilité fournisseur dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="00120-105">This article describes the pages that you use to set up basic and optional functionality for Accounts payable in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="00120-106">Il décrit également les étapes de paramétrage que vous devez effectuer avant de commencer à configurer la Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="00120-106">It also describes setup steps that you must complete before you start to set up Accounts payable.</span></span>

<a name="prerequisites-for-accounts-payable-setup"></a><span data-ttu-id="00120-107">Conditions préalables à la configuration du module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="00120-107">Prerequisites for Accounts payable setup</span></span>
----------------------------------------

<span data-ttu-id="00120-108">Avant d'être en mesure de configurer le module Comptabilité fournisseur, vous devez effectuer les procédures de paramétrage suivantes :</span><span class="sxs-lookup"><span data-stu-id="00120-108">Before you can set up Accounts payable, you must complete the following setup:</span></span>

-   <span data-ttu-id="00120-109">Dans le module Comptabilité :</span><span class="sxs-lookup"><span data-stu-id="00120-109">In General ledger:</span></span>
    -   <span data-ttu-id="00120-110">Pour utiliser des journaux des paiements, vous devez d'abord les paramétrer.</span><span class="sxs-lookup"><span data-stu-id="00120-110">If you plan to use payment journals, set up payment journals.</span></span>
    -   <span data-ttu-id="00120-111">Si vous prévoyez d'effectuer des ajustements du taux de change, paramétrez les codes devise sur la page Devises, paramétrez les types de taux de change sur la page Types de taux de change, et paramétrez les taux de change des devises sur la page Taux de change des devises.</span><span class="sxs-lookup"><span data-stu-id="00120-111">If you plan to run exchange rate adjustments, set up currency codes on the Currencies page, set up exchange rate types on the Exchange rate types page, and set up currency exchange rates on the Currency exchange rates page.</span></span>
-   <span data-ttu-id="00120-112">Dans le module Gestion de la trésorerie et de la banque, paramétrez les comptes bancaires à utiliser avec des modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="00120-112">In Cash and bank management, set up bank accounts to use with methods of payment.</span></span>

## <a name="setup-pages-for-accounts-payable"></a><span data-ttu-id="00120-113">Configuration des pages pour le module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="00120-113">Setup pages for Accounts payable</span></span>

<span data-ttu-id="00120-114">Les pages suivantes permettent de paramétrer les fonctionnalités de base du module Comptabilité fournisseur pour chaque entité juridique.</span><span class="sxs-lookup"><span data-stu-id="00120-114">Use the following pages to set up the basic functionality of Accounts payable for each legal entity.</span></span> <span data-ttu-id="00120-115">Elles sont répertoriées dans l'ordre de paramétrage recommandé.</span><span class="sxs-lookup"><span data-stu-id="00120-115">The pages are listed in the recommended order of setup.</span></span> <span data-ttu-id="00120-116">Pour simplifier le processus de paramétrage, vous pouvez créer des modèles à partir des premiers enregistrements que vous créez.</span><span class="sxs-lookup"><span data-stu-id="00120-116">To make the setup process easier, you can create templates from the first records that you create.</span></span> <span data-ttu-id="00120-117">Dans un modèle, les valeurs sont généralement entrées dans de nombreux champs de sorte à refléter les fonctionnalités que l'organisation veut mettre en œuvre pour un type de fournisseur particulier.</span><span class="sxs-lookup"><span data-stu-id="00120-117">In a template, values are typically entered in many fields to reflect the features that the organization wants to implement for a particular type of vendor.</span></span>
1.  <span data-ttu-id="00120-118">Sur la page Conditions de paiement, définissez les conditions de paiement à affecter aux commandes client, aux commandes fournisseur, aux clients et aux fournisseurs et qui déterminent les dates d'échéance des factures.</span><span class="sxs-lookup"><span data-stu-id="00120-118">On the Terms of payment page, define the terms of payment that you assign to sales orders, purchase orders, customers, and vendors, and that determine invoice due dates.</span></span> <span data-ttu-id="00120-119">Pour plus d'informations, voir [Définir les commissions de paiement fournisseur](tasks/define-vendor-payment-fees.md).</span><span class="sxs-lookup"><span data-stu-id="00120-119">For more information, see [Define vendor payment fees](tasks/define-vendor-payment-fees.md).</span></span>
2.  <span data-ttu-id="00120-120">Sur la page Modes de paiement - fournisseurs, créez et tenez à jour les informations sur la manière dont l'organisation paie ses fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="00120-120">On the Methods of payment - vendors page, create and maintain information about how the organization pays its vendors.</span></span>
3.  <span data-ttu-id="00120-121">Sur la page Groupes de fournisseurs, créez et tenez à jour les groupes de fournisseurs qui partagent des paramètres importants pour la validation, le règlement et le paiement, la génération d'états et les prévisions.</span><span class="sxs-lookup"><span data-stu-id="00120-121">On the Vendor groups page, create and maintain groups of vendors that share important parameters for posting, settlement and payment, reporting, and forecasting.</span></span>
4.  <span data-ttu-id="00120-122">Sur la page Profils de validation fournisseur, définissez comment les transactions fournisseur sont validés dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="00120-122">On the Vendor posting profiles page, define how vendor transactions are posted to the general ledger.</span></span>
5.  <span data-ttu-id="00120-123">Sur la page Paramètres de la comptabilité fournisseur, définissez des paramètres par défaut qui sont appliqués si aucun paramétrage plus spécifique n'est spécifié, des paramètres pour différents types de fonctionnalités et les diverses souches de numéros pour la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="00120-123">On the Accounts payable parameters page, set up default settings that are applied if a more specific setting isn't specified, parameters for various kinds of functionality, and the various number sequences for Accounts payable.</span></span>
6.  <span data-ttu-id="00120-124">Sur la page Paramétrage d'écran, définissez le format de différents documents liés aux fournisseurs et que l'organisation utilise pour le suivi des réceptions des fournisseurs et pour entrer les motifs du flux de paiements adressés aux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="00120-124">On the Form setup page, define the format of various documents that are related to vendors, and that the organization uses to keep track of receipts from vendors and enter reasons for the flow of payments to vendors.</span></span>
7.  <span data-ttu-id="00120-125">Sur la page Fournisseurs, créez et tenez à jour les comptes fournisseur, ainsi que les administrations fiscales auxquelles votre organisation déclare les taxes.</span><span class="sxs-lookup"><span data-stu-id="00120-125">On the Vendors page, create and maintain vendor accounts, and also the tax authorities that your organization reports sales taxes to.</span></span>

## <a name="optional-setup-pages-for-accounts-payable"></a><span data-ttu-id="00120-126">Paramétrage facultatif de pages pour le module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="00120-126">Optional setup pages for Accounts payable</span></span>
<span data-ttu-id="00120-127">Outre les fonctionnalités de base, le module Comptabilité fournisseur est doté d'autres fonctionnalités que vous pouvez paramétrer.</span><span class="sxs-lookup"><span data-stu-id="00120-127">In addition to the basic functionality, Accounts payable has other functionality that you can set up.</span></span>

<span data-ttu-id="00120-128">Les pages à paramétrer supplémentaires sont organisés selon leur fonction.</span><span class="sxs-lookup"><span data-stu-id="00120-128">The additional setup pages are organized by functionality.</span></span>

<span data-ttu-id="00120-129">**Stratégies**</span><span class="sxs-lookup"><span data-stu-id="00120-129">**Policies**</span></span>
-   <span data-ttu-id="00120-130">Sur la page Stratégie de facture fournisseur, paramétrez les stratégies de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="00120-130">On the Vendor invoice policy page, set up vendor invoice policies.</span></span>

<span data-ttu-id="00120-131">**Rapprochement de factures**</span><span class="sxs-lookup"><span data-stu-id="00120-131">**Invoice matching**</span></span>

-   <span data-ttu-id="00120-132">Sur la page Tolérances de totaux de facture, paramétrez les tolérances pour les totaux de facture.</span><span class="sxs-lookup"><span data-stu-id="00120-132">On the Invoice totals tolerances page, set up tolerances for invoice totals.</span></span>
-   <span data-ttu-id="00120-133">Sur la page Stratégie de rapprochement, paramétrez des stratégies de rapprochement à deux et à trois facteurs.</span><span class="sxs-lookup"><span data-stu-id="00120-133">On the Matching policy page, set up two-way and three-way matching policies.</span></span>
-   <span data-ttu-id="00120-134">Sur la page Tolérances de prix, paramétrez les tolérances pour les prix unitaires.</span><span class="sxs-lookup"><span data-stu-id="00120-134">On the Price tolerances page, set up tolerances for unit prices.</span></span>
-   <span data-ttu-id="00120-135">Sur la page Groupes de tolérance de prix d'article, paramétrez des groupes de tolérance pour le prix des articles.</span><span class="sxs-lookup"><span data-stu-id="00120-135">On the Item price tolerance groups page, set up tolerance groups for item prices.</span></span>
-   <span data-ttu-id="00120-136">Sur la page Groupes de tolérance de prix fournisseur, paramétrez des groupes de tolérance pour les prix fournisseur.</span><span class="sxs-lookup"><span data-stu-id="00120-136">On the Vendor price tolerance groups page, set up  tolerance groups for vendor prices.</span></span>
-   <span data-ttu-id="00120-137">Sur la page Tolérances en termes de frais, paramétrez les tolérances pour les frais.</span><span class="sxs-lookup"><span data-stu-id="00120-137">On the Charges tolerances page, set up tolerances for charges.</span></span>

<span data-ttu-id="00120-138">**Workflow**</span><span class="sxs-lookup"><span data-stu-id="00120-138">**Workflow**</span></span>

-   <span data-ttu-id="00120-139">Sur la page Workflows de la comptabilité fournisseur, paramétrez les configurations de workflow pour les approbations de journaux et les demandes d'achat.</span><span class="sxs-lookup"><span data-stu-id="00120-139">On the Accounts payable workflows page, set up workflow configurations for journal approvals and purchase requisitions.</span></span>

<span data-ttu-id="00120-140">**Motifs**</span><span class="sxs-lookup"><span data-stu-id="00120-140">**Reasons**</span></span>

-   <span data-ttu-id="00120-141">Sur la page Motifs de fournisseur, paramétrez les codes motif.</span><span class="sxs-lookup"><span data-stu-id="00120-141">On the Vendor reasons page, set up reason codes.</span></span>

<span data-ttu-id="00120-142">**Frais**</span><span class="sxs-lookup"><span data-stu-id="00120-142">**Charges**</span></span>

-   <span data-ttu-id="00120-143">Sur la page Code frais, paramétrez les codes pour les frais utilisés dans les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="00120-143">On the Charges code page, set up codes for the charges that are used in purchase orders.</span></span>
-   <span data-ttu-id="00120-144">Sur la page Groupe de frais fournisseur, créez et tenez à jour les groupes de frais pour les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="00120-144">On the Vendor charges group page, create and maintain charges groups for vendors.</span></span>
-   <span data-ttu-id="00120-145">Sur la page Groupes de frais sur article, créez et tenez à jour les groupes de frais pour les articles.</span><span class="sxs-lookup"><span data-stu-id="00120-145">On the Item charge groups page, create and maintain charges groups for items.</span></span>
-   <span data-ttu-id="00120-146">Sur la page Frais auto., définissez les frais qui sont automatiquement affectés à des commandes.</span><span class="sxs-lookup"><span data-stu-id="00120-146">On the Auto charges page, define the charges that are automatically assigned to orders.</span></span>

<span data-ttu-id="00120-147">**Articles supplémentaires**</span><span class="sxs-lookup"><span data-stu-id="00120-147">**Supplementary items**</span></span>

-   <span data-ttu-id="00120-148">Sur la page Groupes d'articles supplémentaires - Fournisseur , créez et tenez à jour des groupes d'articles supplémentaires pour les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="00120-148">On the Supplementary item groups - Vendor page, create and maintain supplementary item groups for vendors.</span></span>
-   <span data-ttu-id="00120-149">Sur la page Groupes d'articles supplémentaires - Stock, créez et tenez à jour des groupes d'articles supplémentaires pour les articles.</span><span class="sxs-lookup"><span data-stu-id="00120-149">On the Supplementary item groups - Inventory page, create and maintain supplementary item groups for items.</span></span>

<span data-ttu-id="00120-150">**Distribution**</span><span class="sxs-lookup"><span data-stu-id="00120-150">**Distribution**</span></span>

-   <span data-ttu-id="00120-151">Sur la page Conditions de livraison , créez et tenez à jour les conditions de transfert d'un article d'un vendeur vers un acheteur.</span><span class="sxs-lookup"><span data-stu-id="00120-151">On the Terms of delivery page, create and maintain the conditions for an item's transfer from seller to buyer.</span></span>
-   <span data-ttu-id="00120-152">Sur la page Modes de livraison, créez et tenez à jour les modes de transport utilisés pour la livraison d'une commande du vendeur à l'acheteur..</span><span class="sxs-lookup"><span data-stu-id="00120-152">On the Modes of delivery page, create and maintain the methods of transport that are used when an order is delivered from the seller to the buyer.</span></span>
-   <span data-ttu-id="00120-153">Sur la page Codes destination , créez et tenez à jour des identificateurs et des descriptions pour les destinations de livraison.</span><span class="sxs-lookup"><span data-stu-id="00120-153">On the Destination codes page, create and maintain identifiers and descriptions for delivery destinations.</span></span>

<span data-ttu-id="00120-154">**Écrans**</span><span class="sxs-lookup"><span data-stu-id="00120-154">**Forms**</span></span>

-   <span data-ttu-id="00120-155">Sur la page Textes standard, créez le texte standard qui s'affiche sur diverses pages.</span><span class="sxs-lookup"><span data-stu-id="00120-155">On the Form notes page, create the standard text that appears on various pages.</span></span>
-   <span data-ttu-id="00120-156">Sur la page Paramètres de tri d'écran, paramétrez l'ordre de tri pour les demandes, les listes de réception, les bons de livraison et les factures.</span><span class="sxs-lookup"><span data-stu-id="00120-156">On the Form sorting parameters page, set up the sorting order for requisitions, receipt lists, packing slips, and invoices.</span></span>
-   <span data-ttu-id="00120-157">Sur la page Paramétrage de la gestion de l'impression, paramétrez les informations de gestion d'impression pour les originaux et les copies des pages.</span><span class="sxs-lookup"><span data-stu-id="00120-157">On the Print management setup page, set up print management information for originals and copies of pages.</span></span>

<span data-ttu-id="00120-158">**Paiements**</span><span class="sxs-lookup"><span data-stu-id="00120-158">**Payments**</span></span>

-   <span data-ttu-id="00120-159">Sur la page Escomptes de règlement, paramétrez et gérez les conditions d'obtention d'escomptes de règlement.</span><span class="sxs-lookup"><span data-stu-id="00120-159">On the Cash discounts page, set up and manage the terms for obtaining cash discounts.</span></span> <span data-ttu-id="00120-160">Les codes escompte de règlement sont associés aux fournisseurs et appliqués aux commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="00120-160">The cash discount codes are linked to vendors and are applied to purchase orders.</span></span>
-   <span data-ttu-id="00120-161">Sur la page Echéanciers de paiement, paramétrez les échéanciers de paiement utilisés pour gérer les paiements par versement des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="00120-161">On the Payment schedules page, set up the payment schedules that are used to manage installment payments to vendors.</span></span>
-   <span data-ttu-id="00120-162">Sur la page Jours de paiement, définissez les jours de paiement utilisés pour le calcul des dates d'échéance et spécifiez les jours de paiement pour un jour spécifique de la semaine ou du mois.</span><span class="sxs-lookup"><span data-stu-id="00120-162">On the Payment days page, define the payment days that are used to calculate due dates, and specify payment days for a specific day of the week or month.</span></span>
-   <span data-ttu-id="00120-163">Sur la page Frais de paiement, créez et tenez à jour les frais de paiement associés aux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="00120-163">On the Payment fee page, create and maintain the payment fees that are associated with vendors.</span></span>
-   <span data-ttu-id="00120-164">Sur la page Instructions de paiement, créez et tenez à jour les instructions de paiement.</span><span class="sxs-lookup"><span data-stu-id="00120-164">On the Payment instruction page, create and maintain payment instructions.</span></span>

<span data-ttu-id="00120-165">**Statistiques**</span><span class="sxs-lookup"><span data-stu-id="00120-165">**Statistics**</span></span>

-   <span data-ttu-id="00120-166">Sur la page Définitions des plages âgées, paramétrez des intervalles définis par l'utilisateur, permettant d'analyser la distribution par exigibilité des comptes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="00120-166">On the Aging period definitions page, set up user-defined intervals that are used to analyze the maturity distribution of vendor accounts.</span></span>
-   <span data-ttu-id="00120-167">Sur la page Activité, créez les codes activité affectés aux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="00120-167">On the Line of business page, create the line of business (LOB) codes that are assigned to vendors.</span></span>

<span data-ttu-id="00120-168">**Taxe sur les honoraires**</span><span class="sxs-lookup"><span data-stu-id="00120-168">**Tax 1099**</span></span>

-   <span data-ttu-id="00120-169">Sur la page **Champs de déclaration des honoraires**, vérifiez et tenez à jour les montants minimaux à déclarer à l'IRS (Internal Revenue Service), selon les dernières recommandations de l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="00120-169">On the **1099 fields** page, verify and update the minimum amounts that must be reported to the Internal Revenue Service (IRS), based on the latest IRS requirements.</span></span>

## <a name="optional-setup-for-other-modules"></a><span data-ttu-id="00120-170">**Paramétrage facultatif pour d'autres modules**</span><span class="sxs-lookup"><span data-stu-id="00120-170">**Optional setup for other modules**</span></span>
<span data-ttu-id="00120-171">**Administration d'organisation**</span><span class="sxs-lookup"><span data-stu-id="00120-171">**Organization administration**</span></span>

-   <span data-ttu-id="00120-172">Sur la page Souches de numéros , paramétrez des groupes de souches de numéros pour les numéros de facture.</span><span class="sxs-lookup"><span data-stu-id="00120-172">On the Number sequences page, set up number sequence groups for invoice numbers.</span></span>
-   <span data-ttu-id="00120-173">Sur les pages suivantes, paramétrez les informations d'adresse :</span><span class="sxs-lookup"><span data-stu-id="00120-173">On the following pages, set up address information:</span></span>
    -   <span data-ttu-id="00120-174">Configuration de l'adresse</span><span class="sxs-lookup"><span data-stu-id="00120-174">Address setup</span></span>
    -   <span data-ttu-id="00120-175">Codes NAF</span><span class="sxs-lookup"><span data-stu-id="00120-175">NAF codes</span></span>
    -   <span data-ttu-id="00120-176">Importer des codes postaux</span><span class="sxs-lookup"><span data-stu-id="00120-176">Import ZIP/postal codes</span></span>

<span data-ttu-id="00120-177">**Comptabilité**</span><span class="sxs-lookup"><span data-stu-id="00120-177">**General ledger**</span></span>

-   <span data-ttu-id="00120-178">Sur la page Dimensions financières , paramétrez les dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="00120-178">On the Financial dimensions page, set up financial dimensions.</span></span>
-   <span data-ttu-id="00120-179">Sur les pages suivantes, paramétrez les informations fiscales :</span><span class="sxs-lookup"><span data-stu-id="00120-179">On the following pages, set up tax information:</span></span>
    -   <span data-ttu-id="00120-180">Codes taxe</span><span class="sxs-lookup"><span data-stu-id="00120-180">Sales tax codes</span></span>
    -   <span data-ttu-id="00120-181">Groupes de taxe</span><span class="sxs-lookup"><span data-stu-id="00120-181">Sales tax groups</span></span>
    -   <span data-ttu-id="00120-182">Groupes de taxe d'article</span><span class="sxs-lookup"><span data-stu-id="00120-182">Item sales tax groups</span></span>
    -   <span data-ttu-id="00120-183">Groupe de comptes</span><span class="sxs-lookup"><span data-stu-id="00120-183">Account group</span></span>
    -   <span data-ttu-id="00120-184">Codes d'exonération fiscale</span><span class="sxs-lookup"><span data-stu-id="00120-184">Sales tax exempt codes</span></span>
    -   <span data-ttu-id="00120-185">Juridictions fiscales</span><span class="sxs-lookup"><span data-stu-id="00120-185">Sales tax jurisdictions</span></span>
    -   <span data-ttu-id="00120-186">Administrations fiscales</span><span class="sxs-lookup"><span data-stu-id="00120-186">Sales tax authorities</span></span>
    -   <span data-ttu-id="00120-187">Périodes de règlement fiscal</span><span class="sxs-lookup"><span data-stu-id="00120-187">Sales tax settlement periods</span></span>

<span data-ttu-id="00120-188">**Gestion de la trésorerie et de la banque**</span><span class="sxs-lookup"><span data-stu-id="00120-188">**Cash and bank management**</span></span>

-   <span data-ttu-id="00120-189">Sur la page Codes objectif de paiement, paramétrez le code objet de la Banque centrale.</span><span class="sxs-lookup"><span data-stu-id="00120-189">On the Payment purpose codes page, set up the Central Bank purpose code.</span></span>






