---
title: Définir des stratégies d'audit pour les documents sources
description: Cette procédure décrit comment paramétrer et exécuter des règles de stratégie d'audit.
author: ryansandness
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a82c3e8e8787beb309b75b73cda36f4ca8031d6f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "336794"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="0c86f-103">Définir des stratégies d'audit pour les documents sources</span><span class="sxs-lookup"><span data-stu-id="0c86f-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0c86f-104">Cette procédure décrit comment paramétrer et exécuter des règles de stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="0c86f-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="0c86f-105">L'exemple utilise des états de dépenses avec le type de dépense Hôtel.</span><span class="sxs-lookup"><span data-stu-id="0c86f-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="0c86f-106">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="0c86f-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="0c86f-107">Le rôle d'auditeur contient les autorisations adéquates afin d'exécuter ces tâches.</span><span class="sxs-lookup"><span data-stu-id="0c86f-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="0c86f-108">Allez dans Console d'audit > Configuration > Type de règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="0c86f-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="0c86f-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0c86f-109">Click New.</span></span>
3. <span data-ttu-id="0c86f-110">Tapez une valeur dans le champ Nom de la règle.</span><span class="sxs-lookup"><span data-stu-id="0c86f-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="0c86f-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0c86f-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0c86f-112">Sélectionnez Ligne d'état de dépenses dans le champ Nom de la requête.</span><span class="sxs-lookup"><span data-stu-id="0c86f-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="0c86f-113">Sélectionnez Regroupement dans le champ de type de requête</span><span class="sxs-lookup"><span data-stu-id="0c86f-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="0c86f-114">Sélectionnez Entité juridique dans le champ Entité juridique</span><span class="sxs-lookup"><span data-stu-id="0c86f-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="0c86f-115">Dans le champ Référence de date du document, sélectionnez Date et heure de modification.</span><span class="sxs-lookup"><span data-stu-id="0c86f-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="0c86f-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0c86f-116">Click Save.</span></span>
10. <span data-ttu-id="0c86f-117">Allez dans Console d'audit > Configuration > Stratégies d'audit.</span><span class="sxs-lookup"><span data-stu-id="0c86f-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="0c86f-118">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0c86f-118">Click New.</span></span>
12. <span data-ttu-id="0c86f-119">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0c86f-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="0c86f-120">Développez la section Organisations de stratégie.</span><span class="sxs-lookup"><span data-stu-id="0c86f-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="0c86f-121">Dans l'arborescence, sélectionnez Contoso Entertainment System USA.</span><span class="sxs-lookup"><span data-stu-id="0c86f-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="0c86f-122">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0c86f-122">Click Add.</span></span>
16. <span data-ttu-id="0c86f-123">Dans l'arborescence, sélectionnez Contoso Consulting USA.</span><span class="sxs-lookup"><span data-stu-id="0c86f-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="0c86f-124">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0c86f-124">Click Add.</span></span>
18. <span data-ttu-id="0c86f-125">Dans l'arborescence, sélectionnez Contoso Retail USA.</span><span class="sxs-lookup"><span data-stu-id="0c86f-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="0c86f-126">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0c86f-126">Click Add.</span></span>
20. <span data-ttu-id="0c86f-127">Réduisez la section Organisations de stratégie.</span><span class="sxs-lookup"><span data-stu-id="0c86f-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="0c86f-128">Développez la section Règles de stratégie.</span><span class="sxs-lookup"><span data-stu-id="0c86f-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="0c86f-129">Dans la liste, recherchez et sélectionnez la règle de stratégie créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="0c86f-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="0c86f-130">Cliquez sur Créer une règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="0c86f-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="0c86f-131">Entrez une date et une heure dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="0c86f-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="0c86f-132">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="0c86f-132">Click Filter.</span></span>
26. <span data-ttu-id="0c86f-133">Dans la liste, sélectionnez la ligne en regard de la catégorie Dépense, puis indiquez Hôtel dans les détails.</span><span class="sxs-lookup"><span data-stu-id="0c86f-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="0c86f-134">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0c86f-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="0c86f-135">Cliquez sur l'onglet Regroupement.</span><span class="sxs-lookup"><span data-stu-id="0c86f-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="0c86f-136">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0c86f-136">Click Add.</span></span>
30. <span data-ttu-id="0c86f-137">Dans la liste, sélectionnez une valeur de champ pour Montant de la transaction.</span><span class="sxs-lookup"><span data-stu-id="0c86f-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="0c86f-138">Saisissez ou sélectionnez une valeur dans le champ Champ.</span><span class="sxs-lookup"><span data-stu-id="0c86f-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="0c86f-139">Sélectionnez « Somme » dans le champ AggregateFunction.</span><span class="sxs-lookup"><span data-stu-id="0c86f-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="0c86f-140">Cliquez sur l'onglet Grouper par.</span><span class="sxs-lookup"><span data-stu-id="0c86f-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="0c86f-141">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0c86f-141">Click Add.</span></span>
35. <span data-ttu-id="0c86f-142">Sélectionnez une valeur pour Employé dans la liste </span><span class="sxs-lookup"><span data-stu-id="0c86f-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="0c86f-143">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0c86f-143">Click Add.</span></span>
37. <span data-ttu-id="0c86f-144">Sélectionnez une valeur pour Catégorie de dépenses dans la liste.</span><span class="sxs-lookup"><span data-stu-id="0c86f-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="0c86f-145">Saisissez ou sélectionnez une valeur dans le champ Champ.</span><span class="sxs-lookup"><span data-stu-id="0c86f-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="0c86f-146">Cliquez sur l'onglet Ayant.</span><span class="sxs-lookup"><span data-stu-id="0c86f-146">Click the Having tab.</span></span>
40. <span data-ttu-id="0c86f-147">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0c86f-147">Click Add.</span></span>
41. <span data-ttu-id="0c86f-148">Sélectionner le montant de la transaction</span><span class="sxs-lookup"><span data-stu-id="0c86f-148">Select Transaction amount</span></span>
42. <span data-ttu-id="0c86f-149">Saisissez ou sélectionnez une valeur dans le champ Champ.</span><span class="sxs-lookup"><span data-stu-id="0c86f-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="0c86f-150">Sélectionnez « Somme » dans le champ AggregateFunction.</span><span class="sxs-lookup"><span data-stu-id="0c86f-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="0c86f-151">Tapez « >2000 » dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="0c86f-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="0c86f-152">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0c86f-152">Click OK.</span></span>
46. <span data-ttu-id="0c86f-153">Cliquez sur Tester.</span><span class="sxs-lookup"><span data-stu-id="0c86f-153">Click Test.</span></span>
47. <span data-ttu-id="0c86f-154">Entrez une date et une heure dans le champ Date de début de la sélection de document.</span><span class="sxs-lookup"><span data-stu-id="0c86f-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="0c86f-155">Entrez une date et une heure dans le champ Date de fin de la sélection de document.</span><span class="sxs-lookup"><span data-stu-id="0c86f-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="0c86f-156">Cliquez sur Exécuter le test.</span><span class="sxs-lookup"><span data-stu-id="0c86f-156">Click Run test.</span></span>
50. <span data-ttu-id="0c86f-157">Dans le volet Actions, cliquez sur Stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="0c86f-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="0c86f-158">Cliquez sur Options supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="0c86f-158">Click Additional options.</span></span>
52. <span data-ttu-id="0c86f-159">Entrez une date et une heure dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="0c86f-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="0c86f-160">Entrez une date et une heure dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="0c86f-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="0c86f-161">Cliquez sur Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="0c86f-161">Click Batch.</span></span>
55. <span data-ttu-id="0c86f-162">Développez la section Exécuter à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="0c86f-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="0c86f-163">Sélectionnez Oui dans le champ Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="0c86f-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="0c86f-164">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0c86f-164">Click OK.</span></span>
58. <span data-ttu-id="0c86f-165">Allez dans Console d'audit > Dossiers d'audit.</span><span class="sxs-lookup"><span data-stu-id="0c86f-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="0c86f-166">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0c86f-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="0c86f-167">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0c86f-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="0c86f-168">Développez la section Associations.</span><span class="sxs-lookup"><span data-stu-id="0c86f-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="0c86f-169">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0c86f-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="0c86f-170">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0c86f-170">In the list, click the link in the selected row.</span></span>

