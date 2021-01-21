---
title: Établir des valeurs communes pour la gestion du changement d'ingénierie
description: Cette rubrique décrit comment établir des valeurs communes utilisées pour les paramètres dans diverses parties de la gestion des modifications techniques.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductParameters, EngChgEcmSeverityTable, EngChgEcmSeverityRuleSet, EngChgEcmSeverityLookup,EngChgEcmSeverityChart,EngChgEcmRequestSeverityChart,EngChgEcmPriorityTable, EngChgEcmPriorityLookup, EngChgEcmPriorityChart, EngChgEcmMaterialDisposition, EngChgEcmEH
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 86de050ef4110e3485a77099440f3402e46cc498
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4428342"
---
# <a name="establish-common-values-for-engineering-change-management"></a><span data-ttu-id="0b21f-103">Établir des valeurs communes pour la gestion du changement d'ingénierie</span><span class="sxs-lookup"><span data-stu-id="0b21f-103">Establish common values for engineering change management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b21f-104">Lorsque vous configurez la gestion des modifications techniques, vous devez établir plusieurs collections de valeurs qui seront utilisées pour remplir les listes déroulantes dans d'autres parties de l'interface utilisateur (IU).</span><span class="sxs-lookup"><span data-stu-id="0b21f-104">When you set up engineering change management, you must establish several collections of values that will be used to fill in drop-down lists in other parts of the user interface (UI).</span></span> <span data-ttu-id="0b21f-105">Vous devez spécifier ces valeurs en fonction des types de produits que vous produisez et de vos besoins commerciaux spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0b21f-105">You should specify these values according to the types of products that you produce and your specific business needs.</span></span>

## <a name="engineering-change-categories"></a><span data-ttu-id="0b21f-106">Catégories de modification d’ingénierie</span><span class="sxs-lookup"><span data-stu-id="0b21f-106">Engineering change categories</span></span>

<span data-ttu-id="0b21f-107">Vous utilisez des catégories de modifications techniques pour organiser vos demandes de modification technique, afin qu'elles soient plus faciles à gérer et à examiner.</span><span class="sxs-lookup"><span data-stu-id="0b21f-107">You use engineering change categories to organize your engineering change orders, so that they are easier to manage and review.</span></span> <span data-ttu-id="0b21f-108">Par exemple, vous pouvez trouver utile de configurer un workflow où, selon la catégorie, un service spécifique doit examiner les modifications proposées.</span><span class="sxs-lookup"><span data-stu-id="0b21f-108">For example, you might find it useful to set up a workflow where, depending on the category, a specific department must review the proposed changes.</span></span> <span data-ttu-id="0b21f-109">Par conséquent, l'ordre de modification technique comprend un champ **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-109">Therefore, the engineering change order includes a **Category** field.</span></span>

<span data-ttu-id="0b21f-110">Pour établir la collection de catégories de modifications techniques utilisées dans votre entreprise, accédez à **Gestion du changement d'ingénierie \> Installer \> Gestion du changement d'ingénierie \> Catégories de modifications techniques**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-110">To establish the collection of engineering change categories that is used in your company, go to **Engineering change management \> Setup \> Engineering change management \> Engineering change categories**.</span></span> <span data-ttu-id="0b21f-111">Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l'ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.</span><span class="sxs-lookup"><span data-stu-id="0b21f-111">You can then use the buttons on the Action Pane to add, remove, and edit values, and to arrange them into the order in which they should appear in the drop-down lists where they are shown.</span></span>

## <a name="engineering-change-priorities"></a><span data-ttu-id="0b21f-112">Priorités des modifications d’ingénierie</span><span class="sxs-lookup"><span data-stu-id="0b21f-112">Engineering change priorities</span></span>

<span data-ttu-id="0b21f-113">Vous utilisez les priorités de changement d'ingénierie pour indiquer l'importance ou l'urgence d'un ordre de changement d'ingénierie.</span><span class="sxs-lookup"><span data-stu-id="0b21f-113">You use engineering change priorities to indicate the importance or urgency of an engineering change order.</span></span> <span data-ttu-id="0b21f-114">Ils peuvent vous aider à garder une trace de l'importance d'une demande de modification technique, afin que vous puissiez facilement identifier les commandes à traiter en premier et à quelle vitesse.</span><span class="sxs-lookup"><span data-stu-id="0b21f-114">They can help you keep track of the importance of an engineering change order, so that you can easily identify which orders should be processed first, and how quickly.</span></span>

<span data-ttu-id="0b21f-115">Pour établir la collection de priorités de modifications techniques utilisées dans votre entreprise, accédez à **Gestion du changement d'ingénierie \> Installer \> Gestion du changement d'ingénierie \> Priorités de modifications techniques**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-115">To establish the collection of engineering change priorities that is used in your company, go to **Engineering change management \> Setup \> Engineering change management \> Engineering change priorities**.</span></span> <span data-ttu-id="0b21f-116">Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l'ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.</span><span class="sxs-lookup"><span data-stu-id="0b21f-116">You can then use the buttons on the Action Pane to add, remove, and edit values, and to arrange them into the order in which they should appear in the drop-down lists where they are shown.</span></span>

## <a name="engineering-change-reasons"></a><span data-ttu-id="0b21f-117">Motifs de la modification d’ingénierie</span><span class="sxs-lookup"><span data-stu-id="0b21f-117">Engineering change reasons</span></span>

<span data-ttu-id="0b21f-118">Les raisons de la modification technique indiquent la cause ou la nature de la modification de l'ordre de modification.</span><span class="sxs-lookup"><span data-stu-id="0b21f-118">Engineering change reasons indicate the cause or nature of the change in the change order.</span></span>

<span data-ttu-id="0b21f-119">Pour établir la collection de motifs de modifications techniques utilisées dans votre entreprise, accédez à **Gestion du changement d'ingénierie \> Installer \> Gestion du changement d'ingénierie \> Motifs de modifications techniques**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-119">To establish the collection of engineering change reasons that is used in your company, go to **Engineering change management \> Setup \> Engineering change management \> Engineering change reasons**.</span></span> <span data-ttu-id="0b21f-120">Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l'ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.</span><span class="sxs-lookup"><span data-stu-id="0b21f-120">You can then use the buttons on the Action Pane to add, remove, and edit values, and to arrange them into the order in which they should appear in the drop-down lists where they are shown.</span></span>

## <a name="material-disposal-codes"></a><span data-ttu-id="0b21f-121">Codes de cession de matières</span><span class="sxs-lookup"><span data-stu-id="0b21f-121">Material disposal codes</span></span>

<span data-ttu-id="0b21f-122">Vous utilisez des codes d'élimination des matériaux pour classer les matériaux qui sont utilisés dans vos produits finis, ou les composants qui doivent être éliminés d'une manière spécifique ou qui nécessitent un traitement avant de pouvoir être ajoutés à votre poubelle habituelle.</span><span class="sxs-lookup"><span data-stu-id="0b21f-122">You use material disposal codes to categorize materials that are used in your finished goods, or components that must be disposed of in a specific way or require some treatment before they can be added to your regular trash.</span></span> <span data-ttu-id="0b21f-123">Lorsque vous ajoutez un produit pertinent à une demande de modification technique, vous pouvez affecter un code d'élimination dans le cadre des détails de modification.</span><span class="sxs-lookup"><span data-stu-id="0b21f-123">When you add a relevant product to an engineering change order, you can assign a disposal code as part of the change details.</span></span>

<span data-ttu-id="0b21f-124">Pour établir la collection de codes d'élimination des matériaux utilisées dans votre entreprise, accédez à **Gestion du changement d'ingénierie \> Installer \> Gestion du changement d'ingénierie \> Codes d'élimination des matériaux**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-124">To establish the collection of material disposal codes that is used in your company, go to **Engineering change management \> Setup \> Engineering change management \> Material disposal codes**.</span></span> <span data-ttu-id="0b21f-125">Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l'ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.</span><span class="sxs-lookup"><span data-stu-id="0b21f-125">You can then use the buttons on the Action Pane to add, remove, and edit values, and to arrange them into the order in which they should appear in the drop-down lists where they are shown.</span></span>

## <a name="received-customer-approval"></a><span data-ttu-id="0b21f-126">Approbation du client reçue</span><span class="sxs-lookup"><span data-stu-id="0b21f-126">Received customer approval</span></span>

<span data-ttu-id="0b21f-127">Lorsque vous concevez des produits pour un client spécifique, la conception et les spécifications doivent souvent être validées avant que le produit puisse être défini comme prêt.</span><span class="sxs-lookup"><span data-stu-id="0b21f-127">When you design products for a specific customer, the design and specifications often must be validated before the product can be set as ready.</span></span> <span data-ttu-id="0b21f-128">Le champ **Réception de l'approbation du client** vous permet d'indiquer jusqu'où le produit se trouve dans le processus d'approbation du client et/ou si l'approbation a été reçue.</span><span class="sxs-lookup"><span data-stu-id="0b21f-128">The **Received customer approval** field lets you indicate how far in the customer approval process the product is and/or whether the approval has been received.</span></span>

<span data-ttu-id="0b21f-129">Pour établir la collection des valeurs d'approbation des clients utilisées dans votre entreprise, accédez à **Gestion du changement d'ingénierie \> Installer \> Gestion du changement d'ingénierie \> Réception de l'approbation du client**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-129">To establish the collection of received customer approval values that is used in your company, go to **Engineering change management \> Setup \> Engineering change management \> Received customer approval**.</span></span> <span data-ttu-id="0b21f-130">Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l'ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.</span><span class="sxs-lookup"><span data-stu-id="0b21f-130">You can then use the buttons on the Action Pane to add, remove, and edit values, and to arrange them into the order in which they should appear in the drop-down lists where they are shown.</span></span>

## <a name="engineering-change--environmental-health-and-safety-codes"></a><span data-ttu-id="0b21f-131">Changement technique – Codes de santé et de sécurité environnementales</span><span class="sxs-lookup"><span data-stu-id="0b21f-131">Engineering change – Environmental health and safety codes</span></span>

<span data-ttu-id="0b21f-132">Si des réglementations environnementales standard en matière de santé et de sécurité, ou des réglementations ou procédures spécifiques à l'entreprise, doivent être prises en compte dans la fabrication d'un produit, vous pouvez utiliser les codes de santé et de sécurité environnementaux pour les définir.</span><span class="sxs-lookup"><span data-stu-id="0b21f-132">If any standard environmental health and safety regulations, or company-specific regulations or procedures, must be considered in the manufacture of a product, you can use the environmental health and safety codes to define them.</span></span> <span data-ttu-id="0b21f-133">Dans l'ordre de modification technique, vous pouvez indiquer les codes qui s'appliquent à la fabrication d'un produit pendant que vous modifiez les détails du produit concerné.</span><span class="sxs-lookup"><span data-stu-id="0b21f-133">In the engineering change order, you can indicate which codes apply to the manufacture of a product while you edit the details of the affected product.</span></span>

<span data-ttu-id="0b21f-134">Pour établir la collection de valeurs d'hygiène et de sécurité utilisées dans votre entreprise, accédez à **Gestion du changement d'ingénierie \> Installer \> Gestion du changement d'ingénierie \> Codes d'hygiène et de sécurité de l'environnement**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-134">To establish the collection of health and safety values that is used in your company, go to **Engineering change management \> Setup \> Engineering change management \> Engineering change - Environmental health and safety codes**.</span></span> <span data-ttu-id="0b21f-135">Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l'ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.</span><span class="sxs-lookup"><span data-stu-id="0b21f-135">You can then use the buttons on the Action Pane to add, remove, and edit values, and to arrange them into the order in which they should appear in the drop-down lists where they are shown.</span></span>

## <a name="engineering-change-severities"></a><span data-ttu-id="0b21f-136">Niveaux de gravité de modification d’ingénierie</span><span class="sxs-lookup"><span data-stu-id="0b21f-136">Engineering change severities</span></span>

<span data-ttu-id="0b21f-137">Vous utilisez les niveaux de gravité des modifications techniques pour indiquer le niveau d'impact qui s'applique aux produits dans un ordre de modification technique.</span><span class="sxs-lookup"><span data-stu-id="0b21f-137">You use engineering change severities to indicate the level of impact that applies to the products in an engineering change order.</span></span>

<span data-ttu-id="0b21f-138">Pour établir la collection de la gravité de modifications techniques utilisées dans votre entreprise, accédez à **Gestion du changement d'ingénierie \> Installer \> Gestion du changement d'ingénierie \> Gravité de modifications techniques**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-138">To establish the collection of engineering change severities that is used in your company, go to **Engineering change management \> Setup \> Engineering change management \> Engineering change severities**.</span></span> <span data-ttu-id="0b21f-139">Vous pouvez ensuite utiliser les boutons du volet Actions pour ajouter, supprimer et modifier des valeurs, et pour les organiser dans l'ordre dans lequel elles doivent apparaître dans les listes déroulantes où elles sont affichées.</span><span class="sxs-lookup"><span data-stu-id="0b21f-139">You can then use the buttons on the Action Pane to add, remove, and edit values, and to arrange them into the order in which they should appear in the drop-down lists where they are shown.</span></span>

<span data-ttu-id="0b21f-140">Vous pouvez établir des règles qui s'appliquent à chaque niveau de gravité que vous créez.</span><span class="sxs-lookup"><span data-stu-id="0b21f-140">You can establish rules that apply to each severity level that you create.</span></span> <span data-ttu-id="0b21f-141">Pour plus d'informations sur l'attribution de ces règles, consultez la section suivante.</span><span class="sxs-lookup"><span data-stu-id="0b21f-141">For more information about how to assign these rules, see the next section.</span></span>

## <a name="engineering-change-severity-rule-sets"></a><span data-ttu-id="0b21f-142">Ensembles de règles de gravité des modifications d’ingénierie</span><span class="sxs-lookup"><span data-stu-id="0b21f-142">Engineering change severity rule sets</span></span>

<span data-ttu-id="0b21f-143">Vous utilisez des ensembles de règles de gravité des modifications techniques pour établir un groupe de règles que vous pouvez utiliser pour calculer automatiquement la gravité de l'ordre de modification, en fonction du type de modifications des produits concernés.</span><span class="sxs-lookup"><span data-stu-id="0b21f-143">You use engineering change severity rule sets to establish a group of rules that you can use to automatically calculate the severity of the change order, based on the type of changes in the affected products.</span></span> <span data-ttu-id="0b21f-144">Pour utiliser les règles de gravité, ouvrez la page **Paramètres de gestion des modifications techniques** et définissez le champ **Règle de gravité** sur *Calculer* ou *Calculer automatiquement*.</span><span class="sxs-lookup"><span data-stu-id="0b21f-144">To use the severity rules, open the **Engineering change management parameters** page, and set the **Severity rule** field to *Calculate* or *Calculate automatically*.</span></span>

<span data-ttu-id="0b21f-145">Lorsque le système évalue la gravité, il traite les règles dans l'ordre dans lequel elles apparaissent sur la page, de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="0b21f-145">When the system evaluates severity, it processes the rules in the order in which they appear on the page, from top to bottom.</span></span> <span data-ttu-id="0b21f-146">Pour qu'une règle soit sélectionnée et que sa priorité soit établie, toutes les règles d'un ensemble de règles doivent être respectées.</span><span class="sxs-lookup"><span data-stu-id="0b21f-146">For a rule to be selected and have its priority established, all the rules in a rule set must be met.</span></span>

<span data-ttu-id="0b21f-147">Pour configurer les règles qui s'appliquent à chaque niveau de gravité de modification que vous avez défini, accédez à **Gestion du changement d'ingénierie \> Configurer \> Gestion du changement d'ingénierie \> Ensembles de règles de gravité des modifications techniques**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-147">To set up the rules that apply to each change severity level that you've defined, go to **Engineering change management \> Setup \> Engineering change management \> Engineering change severity rule sets**.</span></span> <span data-ttu-id="0b21f-148">Suivez ensuite l’une des procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="0b21f-148">Then follow one of these steps.</span></span>

- <span data-ttu-id="0b21f-149">Pour créer ensemble de règles, sélectionnez **Nouveau** dans le volet Actions, puis définissez les champs comme décrit plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="0b21f-149">To create a new rule set, select **New** on the Action Pane, and then set the fields as described later in this section.</span></span>
- <span data-ttu-id="0b21f-150">Pour modifier un ensemble de règles existant, sélectionnez-la dans le volet de liste, sélectionnez **Modifier** dans le volet Actions, puis définissez les champs comme décrit plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="0b21f-150">To edit an existing rule set, select it in the list pane, select **Edit** on the Action Pane, and then set the fields as described later in this section.</span></span>
- <span data-ttu-id="0b21f-151">Pour supprimer un ensemble de règles existante, sélectionnez-le dans le volet de liste, puis sélectionnez **Supprimer** sur le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="0b21f-151">To delete an existing rule set, select it in the list pane, and then select **Delete** on the Action Pane.</span></span>
- <span data-ttu-id="0b21f-152">Pour réorganiser la liste des ensembles de règles, sélectionnez un ensemble de règles dans le volet de liste, puis utilisez les boutons **Haut** et **Bas** du volet Actions pour le repositionner.</span><span class="sxs-lookup"><span data-stu-id="0b21f-152">To rearrange the list of rule sets, select a rule set in the list pane, and then use the **Up** and **Down** buttons on the Action Pane to reposition it.</span></span>

<span data-ttu-id="0b21f-153">Pour chaque ensemble de règles, définissez le champ suivant :</span><span class="sxs-lookup"><span data-stu-id="0b21f-153">For each rule set, set the following field:</span></span>

- <span data-ttu-id="0b21f-154">**Gravité** – Sélectionnez le niveau de gravité pour lequel établir des règles.</span><span class="sxs-lookup"><span data-stu-id="0b21f-154">**Severity** – Select the severity level to establish rules for.</span></span> <span data-ttu-id="0b21f-155">Vous utilisez la page **Gravités des changements d'ingénierie** pour créer et nommer les niveaux.</span><span class="sxs-lookup"><span data-stu-id="0b21f-155">You use the **Engineering change severities** page to create and name the levels.</span></span> <span data-ttu-id="0b21f-156">(Pour plus d'informations, voir la section précédente.)</span><span class="sxs-lookup"><span data-stu-id="0b21f-156">(For more information, see the previous section.)</span></span>

<span data-ttu-id="0b21f-157">Utilisez les boutons du raccourci **Règles** pour ajouter ou supprimer une règle pour le paramètre de gravité actuel.</span><span class="sxs-lookup"><span data-stu-id="0b21f-157">Use the buttons on the **Rules** FastTab to add or remove a rule for the current severity setting.</span></span> <span data-ttu-id="0b21f-158">Chaque règle a un champ **Règle** et un champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="0b21f-158">Each rule has a **Rule** field and a **Name** field.</span></span> <span data-ttu-id="0b21f-159">Les règles sont établies par le système et indiquent les types de modifications qu'un produit peut avoir.</span><span class="sxs-lookup"><span data-stu-id="0b21f-159">The rules are established by the system and indicate the types of changes that a product can have.</span></span> <span data-ttu-id="0b21f-160">Le nom indique le type de modification.</span><span class="sxs-lookup"><span data-stu-id="0b21f-160">The name indicates the type of change.</span></span>