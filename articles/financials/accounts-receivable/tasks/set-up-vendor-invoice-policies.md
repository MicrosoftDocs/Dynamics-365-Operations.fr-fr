---
title: Paramétrer des stratégies de facture fournisseur
description: Cette rubrique explique comment paramétrer des stratégies de facture fournisseur dans Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: 328aafd16496fdbb963c9aa40a5c13005be7a382
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842807"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="a0198-103">Paramétrer des stratégies de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="a0198-103">Set up vendor invoice policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a0198-104">Cette rubrique explique comment paramétrer des stratégies de facture fournisseur dans Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a0198-104">This topic explains how to set up vendor invoice policies in Dynamics 365 for Finance and Operatoins.</span></span> <span data-ttu-id="a0198-105">Les stratégies de facture fournisseur sont exécutées lorsque vous validez une facture fournisseur à l'aide de la page Facture fournisseur et lorsque vous ouvrez la page Violations de stratégie de la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a0198-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="a0198-106">Vous pouvez également configurer le workflow de facture fournisseur de manière à exécuter des stratégies de facture fournisseur chaque fois que vous envoyez une facture dans le workflow.</span><span class="sxs-lookup"><span data-stu-id="a0198-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="a0198-107">Les stratégies de facture fournisseur ne s'appliquent pas aux factures créées dans le registre des factures ou dans le journal des factures.</span><span class="sxs-lookup"><span data-stu-id="a0198-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="a0198-108">Le contrôle du rapprochement de factures ne fait pas appel aux stratégies de facture fournisseur. Au lieu de cela, il est paramétré sur la page Paramètres de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a0198-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="a0198-109">La société fictive USMF sert d'exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="a0198-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="a0198-110">Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.</span><span class="sxs-lookup"><span data-stu-id="a0198-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="a0198-111">Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a0198-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="a0198-112">Préparation de la création des stratégies de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="a0198-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="a0198-113">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage > Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="a0198-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="a0198-114">Sélectionnez l'onglet **Contrôle de la facture**.</span><span class="sxs-lookup"><span data-stu-id="a0198-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="a0198-115">Activez ou désactivez la case à cocher **Mettre à jour automatiquement le statut d'en-tête des factures**.</span><span class="sxs-lookup"><span data-stu-id="a0198-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="a0198-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0198-116">Select **OK**.</span></span>
5. <span data-ttu-id="a0198-117">Sélectionnez une option dans le champ **Valider la facture avec les non-correspondances**.</span><span class="sxs-lookup"><span data-stu-id="a0198-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="a0198-118">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a0198-118">Close the page.</span></span>
7. <span data-ttu-id="a0198-119">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="a0198-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="a0198-120">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="a0198-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="a0198-121">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a0198-121">Select **Add**.</span></span>
10. <span data-ttu-id="a0198-122">Fermez la page pour revenir à la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="a0198-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="a0198-123">Création de types de règles de stratégie pour les factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="a0198-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="a0198-124">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Types de règles de stratégies de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="a0198-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="a0198-125">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a0198-125">Select **New**.</span></span>
3. <span data-ttu-id="a0198-126">Tapez des valeurs dans les champs **Nom de la règle** et **Description**.</span><span class="sxs-lookup"><span data-stu-id="a0198-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="a0198-127">Dans le champ **Nom de la requête**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche, puis selectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a0198-127">In the **Query name** field, select the drop-down button to open the lookup, then selec the desired record.</span></span>
5. <span data-ttu-id="a0198-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a0198-128">Select **Save**.</span></span>
6. <span data-ttu-id="a0198-129">Fermez la page pour revenir à la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="a0198-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="a0198-130">Définition d'une stratégie de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="a0198-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="a0198-131">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage de la stratégie > Stratégies de facture fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="a0198-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="a0198-132">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a0198-132">Select **New**.</span></span>
3. <span data-ttu-id="a0198-133">Tapez des valeurs dans les champs **Nom** et **Description**.</span><span class="sxs-lookup"><span data-stu-id="a0198-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="a0198-134">Développez ou réduisez la section **Organisations de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="a0198-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="a0198-135">Dans l'arborescence, sélectionnez **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="a0198-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="a0198-136">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a0198-136">Select **Add**.</span></span>
7. <span data-ttu-id="a0198-137">Développez ou réduisez la section **Règles de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="a0198-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="a0198-138">Sélectionnez **Créer une règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="a0198-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="a0198-139">Tapez une valeur dans le champ **Description de la règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="a0198-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="a0198-140">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="a0198-140">Select **Filter**.</span></span>
11. <span data-ttu-id="a0198-141">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a0198-141">Select **Add**.</span></span> <span data-ttu-id="a0198-142">Sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a0198-142">Select the desired record.</span></span>
12. <span data-ttu-id="a0198-143">Dans les champs **Table**, **Table dérivée** et **Champ**, sélectionnez ou entrez des options dans les menus déroulants.</span><span class="sxs-lookup"><span data-stu-id="a0198-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="a0198-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a0198-144">Close the page.</span></span>
14. <span data-ttu-id="a0198-145">Tapez une valeur dans le champ **Critères**.</span><span class="sxs-lookup"><span data-stu-id="a0198-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="a0198-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0198-146">Select **OK**.</span></span>
16. <span data-ttu-id="a0198-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0198-147">Select **OK**.</span></span>
17. <span data-ttu-id="a0198-148">Fermez les pages pour revenir à la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="a0198-148">Close the pages to return to the home page.</span></span>

