---
title: Définir des stratégies d’audit pour les documents sources
description: Cette rubrique décrit comment paramétrer et exécuter des règles de stratégie d’audit.
author: panolte
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e020a9e82ff18055e40e3e0ddc7bbed1068c886c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021427"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="f6117-103">Définir des stratégies d’audit pour les documents sources</span><span class="sxs-lookup"><span data-stu-id="f6117-103">Define audit policies for source documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f6117-104">Cette rubrique décrit comment paramétrer et exécuter des règles de stratégie d’audit.</span><span class="sxs-lookup"><span data-stu-id="f6117-104">This topic explains how to set up and run audit policy rules.</span></span> <span data-ttu-id="f6117-105">L’exemple utilise des états de dépenses avec le type de dépense Hôtel.</span><span class="sxs-lookup"><span data-stu-id="f6117-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="f6117-106">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f6117-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="f6117-107">Le rôle d’auditeur contient les autorisations adéquates afin d’exécuter ces tâches.</span><span class="sxs-lookup"><span data-stu-id="f6117-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="f6117-108">Dans le volet de navigation, allez dans **Modules > Console d’audit > Configuration > Type de règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="f6117-108">In the navigation pane, go to **Modules > Audit workbench > Setup > Policy rule type**.</span></span>
2. <span data-ttu-id="f6117-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f6117-109">Select **New**.</span></span>
3. <span data-ttu-id="f6117-110">Tapez une valeur dans le champ **Nom de la règle**.</span><span class="sxs-lookup"><span data-stu-id="f6117-110">In the **Rule name** field, type a value.</span></span>
4. <span data-ttu-id="f6117-111">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="f6117-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="f6117-112">Sélectionnez **Ligne d’état de dépenses** dans le champ **Nom de la requête**</span><span class="sxs-lookup"><span data-stu-id="f6117-112">In the **Query name** field, select **Expense report line**</span></span>
6. <span data-ttu-id="f6117-113">Sélectionnez **Regroupement** dans le champ de **type de requête**</span><span class="sxs-lookup"><span data-stu-id="f6117-113">In the **query type** field, select **Aggregate**</span></span>
7. <span data-ttu-id="f6117-114">Sélectionnez **Entité juridique** dans le champ **Entité juridique**</span><span class="sxs-lookup"><span data-stu-id="f6117-114">In the **Legal entity** field, select **Legal entity**</span></span>
8. <span data-ttu-id="f6117-115">Dans le champ **Référence de date du document**, sélectionnez **Date et heure de modification**</span><span class="sxs-lookup"><span data-stu-id="f6117-115">In the **Document date reference** field, select **Modified date and time**</span></span>
9. <span data-ttu-id="f6117-116">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f6117-116">Select **Save**.</span></span>
10. <span data-ttu-id="f6117-117">Dans le volet de navigation, allez dans **Modules > Console d’audit > Configuration > Stratégies d’audit**.</span><span class="sxs-lookup"><span data-stu-id="f6117-117">In the navigation pane, go to **Modules > Audit workbench > Setup > Audit policies**.</span></span>
11. <span data-ttu-id="f6117-118">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f6117-118">Select **New**.</span></span>
12. <span data-ttu-id="f6117-119">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="f6117-119">In the **Name** field, type a value.</span></span>
13. <span data-ttu-id="f6117-120">Développez la section **Organisations de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="f6117-120">Expand the **Policy organizations** section.</span></span>
14. <span data-ttu-id="f6117-121">Dans l’arborescence, sélectionnez **Contoso Entertainment System USA**, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6117-121">In the tree, select **Contoso Entertainment System USA**, then select **Add**.</span></span>
15. <span data-ttu-id="f6117-122">Dans l’arborescence, sélectionnez **Contoso Consulting USA**, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6117-122">In the tree, select **Contoso Consulting USA**, then select **Add**.</span></span>
16. <span data-ttu-id="f6117-123">Dans l’arborescence, sélectionnez **Contoso Retail USA**, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6117-123">In the tree, select **Contoso Retail USA**, then select **Add**.</span></span>
17. <span data-ttu-id="f6117-124">Réduisez la section **Organisations de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="f6117-124">Collapse the **Policy organizations** section.</span></span>
18. <span data-ttu-id="f6117-125">Développez la section **Règles de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="f6117-125">Expand the **Policy rules** section.</span></span>
19. <span data-ttu-id="f6117-126">Dans la liste, recherchez et sélectionnez la règle de stratégie créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="f6117-126">In the list, find and select the Policy Rule that was created previously.</span></span>
20. <span data-ttu-id="f6117-127">Sélectionnez **Créer une règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="f6117-127">Select **Create policy rule**.</span></span>
21. <span data-ttu-id="f6117-128">Entrez une date et une heure dans le champ **Date d’effet**.</span><span class="sxs-lookup"><span data-stu-id="f6117-128">In the **Effective date** field, enter a date and time.</span></span>
22. <span data-ttu-id="f6117-129">Sélectionnez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="f6117-129">Select **Filter**.</span></span>
23. <span data-ttu-id="f6117-130">Dans la liste, sélectionnez la ligne en regard de la catégorie **Dépense**, puis indiquez **Hôtel** dans les détails.</span><span class="sxs-lookup"><span data-stu-id="f6117-130">In the list, select the row for **Expense category**, and set the details to **Hotel**.</span></span>
24. <span data-ttu-id="f6117-131">Dans le champ **Critères**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f6117-131">In the **Criteria** field, enter or select a value.</span></span>
25. <span data-ttu-id="f6117-132">Cliquez sur l’onglet **Regroupement**.</span><span class="sxs-lookup"><span data-stu-id="f6117-132">Select the **Aggregate** tab.</span></span>
26. <span data-ttu-id="f6117-133">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6117-133">Select **Add**.</span></span>
27. <span data-ttu-id="f6117-134">Dans la liste, sélectionnez une valeur de champ pour **Montant de la transaction**.</span><span class="sxs-lookup"><span data-stu-id="f6117-134">In the list, select a field value of **Transaction amount**.</span></span>
28. <span data-ttu-id="f6117-135">Saisissez ou sélectionnez une valeur dans le champ **Champ**.</span><span class="sxs-lookup"><span data-stu-id="f6117-135">In the **Field** field, enter or select a value.</span></span>
29. <span data-ttu-id="f6117-136">Sélectionnez **Somme** dans le champ **AggregateFunction**.</span><span class="sxs-lookup"><span data-stu-id="f6117-136">In the **AggregateFunction** field, select **Sum**.</span></span>
30. <span data-ttu-id="f6117-137">Sélectionnez l’onglet **Grouper par**.</span><span class="sxs-lookup"><span data-stu-id="f6117-137">Select the **Group by** tab.</span></span>
31. <span data-ttu-id="f6117-138">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6117-138">Select **Add**.</span></span>
32. <span data-ttu-id="f6117-139">Sélectionnez une valeur pour **Employé** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f6117-139">In the list, select a value of **Employee** .</span></span>
33. <span data-ttu-id="f6117-140">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6117-140">Select **Add**.</span></span>
34. <span data-ttu-id="f6117-141">Sélectionnez une valeur pour **Catégorie de dépenses** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f6117-141">In the list, select a value of **Expense category**.</span></span>
35. <span data-ttu-id="f6117-142">Saisissez ou sélectionnez une valeur dans le champ **Champ**.</span><span class="sxs-lookup"><span data-stu-id="f6117-142">In the **Field** field, enter or select a value.</span></span>
36. <span data-ttu-id="f6117-143">Sélectionnez l’onglet **Ayant**.</span><span class="sxs-lookup"><span data-stu-id="f6117-143">Select the **Having** tab.</span></span>
37. <span data-ttu-id="f6117-144">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6117-144">Select **Add**.</span></span>
38. <span data-ttu-id="f6117-145">Sélectionnez le **montant de la transaction**.</span><span class="sxs-lookup"><span data-stu-id="f6117-145">Select **Transaction amount**.</span></span>
39. <span data-ttu-id="f6117-146">Saisissez ou sélectionnez une valeur dans le champ **Champ**.</span><span class="sxs-lookup"><span data-stu-id="f6117-146">In the **Field** field, enter or select a value.</span></span>
40. <span data-ttu-id="f6117-147">Sélectionnez **Somme** dans le champ **AggregateFunction**.</span><span class="sxs-lookup"><span data-stu-id="f6117-147">In the **AggregateFunction** field, select **Sum**.</span></span>
41. <span data-ttu-id="f6117-148">Tapez `>2000` dans le champ **Critères**.</span><span class="sxs-lookup"><span data-stu-id="f6117-148">In the **Criteria** field, type `>2000`.</span></span>
42. <span data-ttu-id="f6117-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6117-149">Select **OK**.</span></span>
43. <span data-ttu-id="f6117-150">Sélectionnez **Test**.</span><span class="sxs-lookup"><span data-stu-id="f6117-150">Select **Test**.</span></span>
44. <span data-ttu-id="f6117-151">Entrez une date et une heure dans le champ **Date de début de la sélection de document**.</span><span class="sxs-lookup"><span data-stu-id="f6117-151">In the **Document selection starting date** field, enter a date and time.</span></span>
45. <span data-ttu-id="f6117-152">Entrez une date et une heure dans le champ **Date de fin de la sélection de document**.</span><span class="sxs-lookup"><span data-stu-id="f6117-152">In the **Document selection ending date** field, enter a date and time.</span></span>
46. <span data-ttu-id="f6117-153">Sélectionnez **Exécuter le test**.</span><span class="sxs-lookup"><span data-stu-id="f6117-153">Select **Run test**.</span></span>
47. <span data-ttu-id="f6117-154">Dans le volet Actions, cliquez sur **Stratégie d’audit**.</span><span class="sxs-lookup"><span data-stu-id="f6117-154">On the Action Pane, select **Audit policy**.</span></span>
48. <span data-ttu-id="f6117-155">Sélectionnez **Options supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="f6117-155">Select **Additional options**.</span></span>
49. <span data-ttu-id="f6117-156">Entrez une date et une heure dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="f6117-156">In the **Starting date** field, enter a date and time.</span></span>
50. <span data-ttu-id="f6117-157">Entrez une date et une heure dans le champ **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="f6117-157">In the **Ending date** field, enter a date and time.</span></span>
51. <span data-ttu-id="f6117-158">Sélectionnez **Traitement par lots**.</span><span class="sxs-lookup"><span data-stu-id="f6117-158">Select **Batch**.</span></span>
52. <span data-ttu-id="f6117-159">Développez la section **Exécuter à l’arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="f6117-159">Expand the **Run in the background** section.</span></span>
53. <span data-ttu-id="f6117-160">Sélectionnez **Oui** dans le champ **Traitement par lots**.</span><span class="sxs-lookup"><span data-stu-id="f6117-160">Select **Yes** in the **Batch processing** field.</span></span>
54. <span data-ttu-id="f6117-161">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6117-161">Select **OK**.</span></span>
55. <span data-ttu-id="f6117-162">Dans le volet de navigation, allez dans **Modules > Console d’audit > Dossiers d’audit**.</span><span class="sxs-lookup"><span data-stu-id="f6117-162">In the navigation pane, go to **Modules > Audit workbench > Audit cases**.</span></span>
56. <span data-ttu-id="f6117-163">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f6117-163">In the list, find and select the desired record.</span></span>
57. <span data-ttu-id="f6117-164">Développez la section **Associations**.</span><span class="sxs-lookup"><span data-stu-id="f6117-164">Expand the **Associations** section.</span></span>
58. <span data-ttu-id="f6117-165">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f6117-165">In the list, find and select the desired record.</span></span>

