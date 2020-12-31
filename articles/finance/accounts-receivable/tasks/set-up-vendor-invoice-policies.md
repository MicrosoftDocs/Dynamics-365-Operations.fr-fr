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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58518f5291b70c63506c20717034daff0268901b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443190"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="6d033-103">Paramétrer des stratégies de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="6d033-103">Set up vendor invoice policies</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6d033-104">Cette rubrique explique comment paramétrer des politiques de facturation fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6d033-104">This topic explains how to set up vendor invoice policies.</span></span> <span data-ttu-id="6d033-105">Les stratégies de facture fournisseur sont exécutées lorsque vous validez une facture fournisseur à l’aide de la page Facture fournisseur et lorsque vous ouvrez la page Violations de stratégie de la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6d033-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="6d033-106">Vous pouvez également configurer le workflow de facture fournisseur de manière à exécuter des stratégies de facture fournisseur chaque fois que vous envoyez une facture dans le workflow.</span><span class="sxs-lookup"><span data-stu-id="6d033-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="6d033-107">Les stratégies de facture fournisseur ne s’appliquent pas aux factures créées dans le registre des factures ou dans le journal des factures.</span><span class="sxs-lookup"><span data-stu-id="6d033-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="6d033-108">Le contrôle du rapprochement de factures ne fait pas appel aux stratégies de facture fournisseur. Au lieu de cela, il est paramétré sur la page Paramètres de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6d033-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="6d033-109">La société fictive USMF sert d’exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="6d033-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="6d033-110">Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.</span><span class="sxs-lookup"><span data-stu-id="6d033-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="6d033-111">Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6d033-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="6d033-112">Préparation de la création des stratégies de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="6d033-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="6d033-113">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage > Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="6d033-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="6d033-114">Sélectionnez l’onglet **Contrôle de la facture**.</span><span class="sxs-lookup"><span data-stu-id="6d033-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="6d033-115">Activez ou désactivez la case à cocher **Mettre à jour automatiquement le statut d’en-tête des factures**.</span><span class="sxs-lookup"><span data-stu-id="6d033-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="6d033-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d033-116">Select **OK**.</span></span>
5. <span data-ttu-id="6d033-117">Sélectionnez une option dans le champ **Valider la facture avec les non-correspondances**.</span><span class="sxs-lookup"><span data-stu-id="6d033-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="6d033-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6d033-118">Close the page.</span></span>
7. <span data-ttu-id="6d033-119">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="6d033-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="6d033-120">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="6d033-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="6d033-121">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6d033-121">Select **Add**.</span></span>
10. <span data-ttu-id="6d033-122">Fermez la page pour revenir à la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="6d033-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="6d033-123">Création de types de règles de stratégie pour les factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="6d033-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="6d033-124">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Types de règles de stratégies de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="6d033-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="6d033-125">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6d033-125">Select **New**.</span></span>
3. <span data-ttu-id="6d033-126">Tapez des valeurs dans les champs **Nom de la règle** et **Description**.</span><span class="sxs-lookup"><span data-stu-id="6d033-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="6d033-127">Dans le champ **Nom de la requête**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche, puis sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6d033-127">In the **Query name** field, select the drop-down button to open the lookup, then select the desired record.</span></span>
5. <span data-ttu-id="6d033-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6d033-128">Select **Save**.</span></span>
6. <span data-ttu-id="6d033-129">Fermez la page pour revenir à la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="6d033-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="6d033-130">Définition d’une stratégie de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="6d033-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="6d033-131">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="6d033-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="6d033-132">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6d033-132">Select **New**.</span></span>
3. <span data-ttu-id="6d033-133">Tapez des valeurs dans les champs **Nom** et **Description**.</span><span class="sxs-lookup"><span data-stu-id="6d033-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="6d033-134">Développez ou réduisez la section **Organisations de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="6d033-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="6d033-135">Dans l’arborescence, sélectionnez **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="6d033-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="6d033-136">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6d033-136">Select **Add**.</span></span>
7. <span data-ttu-id="6d033-137">Développez ou réduisez la section **Règles de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="6d033-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="6d033-138">Sélectionnez **Créer une règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="6d033-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="6d033-139">Tapez une valeur dans le champ **Description de la règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="6d033-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="6d033-140">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="6d033-140">Select **Filter**.</span></span>
11. <span data-ttu-id="6d033-141">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6d033-141">Select **Add**.</span></span> <span data-ttu-id="6d033-142">Sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6d033-142">Select the desired record.</span></span>
12. <span data-ttu-id="6d033-143">Dans les champs **Table**, **Table dérivée** et **Champ**, sélectionnez ou entrez des options dans les menus déroulants.</span><span class="sxs-lookup"><span data-stu-id="6d033-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="6d033-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6d033-144">Close the page.</span></span>
14. <span data-ttu-id="6d033-145">Tapez une valeur dans le champ **Critères**.</span><span class="sxs-lookup"><span data-stu-id="6d033-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="6d033-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d033-146">Select **OK**.</span></span>
16. <span data-ttu-id="6d033-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d033-147">Select **OK**.</span></span>
17. <span data-ttu-id="6d033-148">Fermez les pages pour revenir à la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="6d033-148">Close the pages to return to the home page.</span></span>

