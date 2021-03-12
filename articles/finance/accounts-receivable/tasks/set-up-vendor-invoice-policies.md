---
title: Paramétrer des stratégies de facture fournisseur
description: Cette rubrique explique comment paramétrer des politiques de facturation fournisseur.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 79cbabba74fdb76d8fcc0553d39e0f140aacf03e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995447"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="3b7b7-103">Paramétrer des stratégies de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="3b7b7-103">Set up vendor invoice policies</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3b7b7-104">Cette rubrique explique comment paramétrer des politiques de facturation fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-104">This topic explains how to set up vendor invoice policies.</span></span> <span data-ttu-id="3b7b7-105">Les stratégies de facture fournisseur sont exécutées lorsque vous validez une facture fournisseur à l’aide de la page Facture fournisseur et lorsque vous ouvrez la page Violations de stratégie de la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="3b7b7-106">Vous pouvez également configurer le workflow de facture fournisseur de manière à exécuter des stratégies de facture fournisseur chaque fois que vous envoyez une facture dans le workflow.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="3b7b7-107">Les stratégies de facture fournisseur ne s’appliquent pas aux factures créées dans le registre des factures ou dans le journal des factures.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="3b7b7-108">Le contrôle du rapprochement de factures ne fait pas appel aux stratégies de facture fournisseur. Au lieu de cela, il est paramétré sur la page Paramètres de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="3b7b7-109">La société fictive USMF sert d’exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="3b7b7-110">Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="3b7b7-111">Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="3b7b7-112">Préparation de la création des stratégies de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="3b7b7-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="3b7b7-113">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage > Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="3b7b7-114">Sélectionnez l’onglet **Contrôle de la facture**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="3b7b7-115">Activez ou désactivez la case à cocher **Mettre à jour automatiquement le statut d’en-tête des factures**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="3b7b7-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-116">Select **OK**.</span></span>
5. <span data-ttu-id="3b7b7-117">Sélectionnez une option dans le champ **Valider la facture avec les non-correspondances**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="3b7b7-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-118">Close the page.</span></span>
7. <span data-ttu-id="3b7b7-119">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="3b7b7-120">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="3b7b7-121">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-121">Select **Add**.</span></span>
10. <span data-ttu-id="3b7b7-122">Fermez la page pour revenir à la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="3b7b7-123">Création de types de règles de stratégie pour les factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="3b7b7-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="3b7b7-124">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Types de règles de stratégies de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="3b7b7-125">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-125">Select **New**.</span></span>
3. <span data-ttu-id="3b7b7-126">Tapez des valeurs dans les champs **Nom de la règle** et **Description**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="3b7b7-127">Dans le champ **Nom de la requête**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche, puis sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-127">In the **Query name** field, select the drop-down button to open the lookup, then select the desired record.</span></span>
5. <span data-ttu-id="3b7b7-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-128">Select **Save**.</span></span>
6. <span data-ttu-id="3b7b7-129">Fermez la page pour revenir à la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="3b7b7-130">Définition d’une stratégie de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="3b7b7-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="3b7b7-131">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="3b7b7-132">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-132">Select **New**.</span></span>
3. <span data-ttu-id="3b7b7-133">Tapez des valeurs dans les champs **Nom** et **Description**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="3b7b7-134">Développez ou réduisez la section **Organisations de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="3b7b7-135">Dans l’arborescence, sélectionnez **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="3b7b7-136">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-136">Select **Add**.</span></span>
7. <span data-ttu-id="3b7b7-137">Développez ou réduisez la section **Règles de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="3b7b7-138">Sélectionnez **Créer une règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="3b7b7-139">Tapez une valeur dans le champ **Description de la règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="3b7b7-140">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-140">Select **Filter**.</span></span>
11. <span data-ttu-id="3b7b7-141">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-141">Select **Add**.</span></span> <span data-ttu-id="3b7b7-142">Sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-142">Select the desired record.</span></span>
12. <span data-ttu-id="3b7b7-143">Dans les champs **Table**, **Table dérivée** et **Champ**, sélectionnez ou entrez des options dans les menus déroulants.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="3b7b7-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-144">Close the page.</span></span>
14. <span data-ttu-id="3b7b7-145">Tapez une valeur dans le champ **Critères**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="3b7b7-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-146">Select **OK**.</span></span>
16. <span data-ttu-id="3b7b7-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-147">Select **OK**.</span></span>
17. <span data-ttu-id="3b7b7-148">Fermez les pages pour revenir à la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="3b7b7-148">Close the pages to return to the home page.</span></span>

