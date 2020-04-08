---
title: Créer et affecter des structures de règle avancées
description: Cette rubrique explique comment créer et affecter une structure de règle avancée à une structure de compte.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb18b96d6d7db84262f8fcfadb15afa80e2fa3d8
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145121"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="306ea-103">Créer et affecter des structures de règle avancées</span><span class="sxs-lookup"><span data-stu-id="306ea-103">Create and assign advanced rule structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="306ea-104">Cette rubrique explique comment créer et affecter une structure de règle avancée à une structure de compte.</span><span class="sxs-lookup"><span data-stu-id="306ea-104">This topic explains how to create and assign an advanced rule structure to an account structure.</span></span> <span data-ttu-id="306ea-105">La société fictive USMF sert d'exemple dans ce guide.</span><span class="sxs-lookup"><span data-stu-id="306ea-105">This guide uses the USMF demo company.</span></span>

## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="306ea-106">Créer une structure de règle avancée</span><span class="sxs-lookup"><span data-stu-id="306ea-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="306ea-107">Accédez au **Volet de navigation > Modules > Comptabilité > Plan de comptes > Structures > Structures de règles avancées**.</span><span class="sxs-lookup"><span data-stu-id="306ea-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span></span>
2. <span data-ttu-id="306ea-108">Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="306ea-108">Select **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="306ea-109">Dans le champ **Structure de règle avancée**, entrez un nom pour décrire la structure de règle.</span><span class="sxs-lookup"><span data-stu-id="306ea-109">In the **Advanced rule structure** field, type a name to describe the rule structure.</span></span>
4. <span data-ttu-id="306ea-110">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="306ea-110">Select **OK**.</span></span>
5. <span data-ttu-id="306ea-111">Sélectionnez **Ajouter un segment**.</span><span class="sxs-lookup"><span data-stu-id="306ea-111">Select **Add segment**.</span></span>
6. <span data-ttu-id="306ea-112">Dans la liste des segments, sélectionnez une dimension financière.</span><span class="sxs-lookup"><span data-stu-id="306ea-112">In the list of segments, select a financial dimension.</span></span> <span data-ttu-id="306ea-113">Par exemple, **Magasin**.</span><span class="sxs-lookup"><span data-stu-id="306ea-113">For example, **Store**.</span></span>  
7. <span data-ttu-id="306ea-114">Sélectionnez **Ajouter un segment**.</span><span class="sxs-lookup"><span data-stu-id="306ea-114">Select **Add segment**.</span></span>
8. <span data-ttu-id="306ea-115">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="306ea-115">Select **Activate**.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="306ea-116">Appliquer une structure de règle avancée à une structure de compte</span><span class="sxs-lookup"><span data-stu-id="306ea-116">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="306ea-117">Accédez au **Volet de navigation > Modules > Comptabilité > Plan de comptes > Structures > Configurer les structures de compte**.</span><span class="sxs-lookup"><span data-stu-id="306ea-117">Go to **navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="306ea-118">Dans la liste, cherchez et sélectionnez la structure de compte à laquelle vous souhaitez appliquer la règle avancée.</span><span class="sxs-lookup"><span data-stu-id="306ea-118">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
3. <span data-ttu-id="306ea-119">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="306ea-119">Select **Edit**.</span></span> <span data-ttu-id="306ea-120">Vous pouvez également sélectionner **Règles avancées** ; vous êtes alors invité à passer la structure de compte en mode **Brouillon**.</span><span class="sxs-lookup"><span data-stu-id="306ea-120">You can also select **Advanced rules** and you will be prompted to put the account structure in **Draft mode**.</span></span>  
4. <span data-ttu-id="306ea-121">Sélectionnez **Règles avancées**.</span><span class="sxs-lookup"><span data-stu-id="306ea-121">Select **Advanced rules**.</span></span>
5. <span data-ttu-id="306ea-122">Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="306ea-122">Select **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="306ea-123">Tapez une valeur dans le champ **Règle avancée**.</span><span class="sxs-lookup"><span data-stu-id="306ea-123">In the **Advanced rule** field, type a value.</span></span>
7. <span data-ttu-id="306ea-124">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="306ea-124">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="306ea-125">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="306ea-125">Select **Create**.</span></span>
9. <span data-ttu-id="306ea-126">Sélectionnez **Ajouter de nouveaux critères**.</span><span class="sxs-lookup"><span data-stu-id="306ea-126">Select **Add new criteria**.</span></span>
10. <span data-ttu-id="306ea-127">Dans le champ **Où**, sélectionnez le compte principal ou une dimension financière.</span><span class="sxs-lookup"><span data-stu-id="306ea-127">In the **Where** field, select main account or a financial dimension.</span></span>
11. <span data-ttu-id="306ea-128">Dans le champ **Opérateur**, sélectionnez une option, comme **Est compris entre** et **Comprend**.</span><span class="sxs-lookup"><span data-stu-id="306ea-128">In the **Operator** field, select an option, such as **is between** and **includes**.</span></span>
12. <span data-ttu-id="306ea-129">Tapez une valeur dans le champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="306ea-129">In the **Value** field, type a value.</span></span>
13. <span data-ttu-id="306ea-130">Dans le champ **À**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="306ea-130">In the **through** field, type a value.</span></span>
14. <span data-ttu-id="306ea-131">Sélectionnez **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="306ea-131">Select **Add** to open the drop dialog.</span></span>
15. <span data-ttu-id="306ea-132">Dans la liste, cherchez la structure de règle avancée à utiliser lorsque les critères que vous avez entrés sont rencontrés.</span><span class="sxs-lookup"><span data-stu-id="306ea-132">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
16. <span data-ttu-id="306ea-133">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="306ea-133">Select **Add**.</span></span>
17. <span data-ttu-id="306ea-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="306ea-134">Close the page.</span></span>
18. <span data-ttu-id="306ea-135">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="306ea-135">Select **Activate**.</span></span>

