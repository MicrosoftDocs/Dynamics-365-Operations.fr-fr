---
title: Recherche dans le programme SEFA
description: Cette rubrique fournit des informations sur l’enquête sur l’annexe des dépenses des bourses fédérales.
author: velofog
manager: Ann Beebe
ms.date: 04/2/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PSNProjSEFAinquiry
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.tgt_pltfrm: ''
ms.custom: ''
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-alpavk
ms.search.validFrom: 2020-4-01
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 0b4228a9592efb54714186fc6b36276e915dc122
ms.sourcegitcommit: be51e892003778e71b67fb409a8e16965c89b5ac
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2020
ms.locfileid: "3618453"
---
# <a name="schedule-of-expenditures-of-federal-awards-inquiry"></a><span data-ttu-id="a27ed-103">Recherche dans le programme SEFA</span><span class="sxs-lookup"><span data-stu-id="a27ed-103">Schedule of Expenditures of Federal Awards inquiry</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a27ed-104">Selon le Bureau de la gestion et la circulaire budgétaire A-133, les organismes qui reçoivent des fonds fédéraux sont soumis à des obligations d’audit, également appelées audits uniques.</span><span class="sxs-lookup"><span data-stu-id="a27ed-104">According to Office of Management and Budget Circular A-133, agencies that receive federal funds are subject to audit requirements, which are also known as single audits.</span></span> <span data-ttu-id="a27ed-105">Le processus d’audit sert à rendre compte des revenus et des dépenses des subventions fédérales de façon récurrente.</span><span class="sxs-lookup"><span data-stu-id="a27ed-105">The audit process is used to report on the revenues and expenditures of federal grants on a recurring basis.</span></span> <span data-ttu-id="a27ed-106">Une partie du rapport d’audit unique comprend l’annexe des dépenses des bourses fédérales (SEFA).</span><span class="sxs-lookup"><span data-stu-id="a27ed-106">Part of the single audit report includes the Schedule of Expenditures of Federal Awards (SEFA).</span></span>

<span data-ttu-id="a27ed-107">L’enquête sur l’annexe des dépenses des bourses fédérales comprend le titre et le numéro du Catalogue de l’aide nationale fédérale (CFDA), le numéro de la subvention, l’année de la subvention, le nom de l’organisme fédéral qui fournit les fonds et le nom de l’entité de validation.</span><span class="sxs-lookup"><span data-stu-id="a27ed-107">The Schedule of Expenditures of Federal Awards inquiry includes the Catalog of Federal Domestic Assistance (CFDA) title and number, the grant number, the year of the grant, the name of the federal agency that provides the funds, and the name of the pass-through entity.</span></span> <span data-ttu-id="a27ed-108">L’enquête concerne une période déterminée.</span><span class="sxs-lookup"><span data-stu-id="a27ed-108">The inquiry is for a specific period.</span></span> <span data-ttu-id="a27ed-109">En règle générale, cette période est la même que celle des états financiers, qui est un exercice.</span><span class="sxs-lookup"><span data-stu-id="a27ed-109">Typically, that period is the same as the financial statement period, which is a fiscal year.</span></span>

<span data-ttu-id="a27ed-110">L’enquête inclut les subventions dont les dates de projection se situent dans la plage de dates sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a27ed-110">The inquiry includes grants that have projection dates in the selected date range.</span></span> <span data-ttu-id="a27ed-111">La colonne **Organisme concédant** de la demande indique le client de la subvention ou, pour une subvention de validation, l’organisme concédant.</span><span class="sxs-lookup"><span data-stu-id="a27ed-111">The **Grantor agency** column of the inquiry shows the grant customer or, for a pass-through grant, the grantor agency.</span></span> <span data-ttu-id="a27ed-112">Pour une subvention de validation, la colonne **Organisme de validation** montre le client de la subvention.</span><span class="sxs-lookup"><span data-stu-id="a27ed-112">For a pass-through grant, the **Pass-through agency** column shows the grant customer.</span></span> <span data-ttu-id="a27ed-113">Si la subvention n’est pas une subvention de validation, la colonne **Organisme de validation** est vide.</span><span class="sxs-lookup"><span data-stu-id="a27ed-113">If the grant isn't a pass-through grant, the **Pass-through agency** column is blank.</span></span>

## <a name="set-up-the-cfda-clusters"></a><span data-ttu-id="a27ed-114">Paramétrage des clusters CFDA</span><span class="sxs-lookup"><span data-stu-id="a27ed-114">Set up the CFDA clusters</span></span>

<span data-ttu-id="a27ed-115">Vous devez configurer les clusters CFDA qui peuvent être associés à des numéros CFDA dans l’enquête sur l’annexe des dépenses des bourses fédérales.</span><span class="sxs-lookup"><span data-stu-id="a27ed-115">You must set up the CFDA clusters that can be associated with CFDA numbers in the Schedule of Expenditures of Federal Awards inquiry.</span></span>

1. <span data-ttu-id="a27ed-116">Aller à **Gestion de projets et comptabilité \> Configurer \> Subventions \> Catalogue des clusters d’assistance nationale fédérale**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-116">Go to **Project management and accounting \> Setup \> Grants \> Catalog of Federal Domestic Assistance clusters**.</span></span>
2. <span data-ttu-id="a27ed-117">Sélectionnez **Nouveau** pour créer un cluster CFDA.</span><span class="sxs-lookup"><span data-stu-id="a27ed-117">Select **New** to create a CFDA cluster.</span></span>
3. <span data-ttu-id="a27ed-118">Entrez le nom du cluster.</span><span class="sxs-lookup"><span data-stu-id="a27ed-118">Enter the cluster name.</span></span>
4. <span data-ttu-id="a27ed-119">Sélectionnez **Enregistrer** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="a27ed-119">Select **Save** to save your changes.</span></span>

## <a name="set-up-cfda-numbers"></a><span data-ttu-id="a27ed-120">Définir les numéros CFDA</span><span class="sxs-lookup"><span data-stu-id="a27ed-120">Set up CFDA numbers</span></span>

<span data-ttu-id="a27ed-121">Vous devez configurer les numéros CFDA qui peuvent être ajoutés aux subventions et inclus dans l’enquête sur l’annexe des dépenses des bourses fédérales.</span><span class="sxs-lookup"><span data-stu-id="a27ed-121">You must set up CFDA numbers that can be added to grants and included in the Schedule of Expenditures of Federal Awards inquiry.</span></span>

1. <span data-ttu-id="a27ed-122">Aller à **Gestion de projets et comptabilité \> Configurer \> Subventions \> Catalogue des numéros d’assistance nationale fédérale**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-122">Go to **Project management and accounting \> Setup \> Grants \> Catalog of Federal Domestic Assistance numbers**.</span></span>
2. <span data-ttu-id="a27ed-123">Sélectionnez **Nouveau** pour créer un numéro CFDA.</span><span class="sxs-lookup"><span data-stu-id="a27ed-123">Select **New** to create a CFDA number.</span></span>
3. <span data-ttu-id="a27ed-124">Entrez le numéro CFDA dans la colonne **Numéro**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-124">In the **Number** column, enter the CFDA number.</span></span>
4. <span data-ttu-id="a27ed-125">Appuyez sur la touche **Tab**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-125">Press the **Tab** key.</span></span>
5. <span data-ttu-id="a27ed-126">Entrez le titre CFDA dans la colonne **Description**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-126">In the **Description** column, enter the CFDA title.</span></span>
6. <span data-ttu-id="a27ed-127">Appuyez sur la touche **Tab**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-127">Press the **Tab** key.</span></span>
7. <span data-ttu-id="a27ed-128">Facultatif : Dans le champ **Cluster de programmes**, ajoutez le cluster CFDA approprié.</span><span class="sxs-lookup"><span data-stu-id="a27ed-128">Optional: In the **Program cluster** field, add the appropriate CFDA cluster.</span></span>
8. <span data-ttu-id="a27ed-129">Sélectionnez **Enregistrer** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="a27ed-129">Select **Save** to save your changes.</span></span>

## <a name="set-up-grants-to-report-for-the-schedule-of-expenditures-of-federal-awards-inquiry"></a><span data-ttu-id="a27ed-130">Mettre en place des subventions à déclarer dans l’enquête sur l’annexe des dépenses des bourses fédérales</span><span class="sxs-lookup"><span data-stu-id="a27ed-130">Set up grants to report for the Schedule of Expenditures of Federal Awards inquiry</span></span>

1. <span data-ttu-id="a27ed-131">Aller à **Gestion de projet et comptabilité \> Subventions \> Subventions** et sélectionnez une subvention existante.</span><span class="sxs-lookup"><span data-stu-id="a27ed-131">Go to **Project management and accounting \> Grants \> Grants**, and select an existing grant.</span></span>
2. <span data-ttu-id="a27ed-132">Sur le raccourci **Installer**, dans le champ **Catalogue de l’aide national fédérale**, attribuez le numéro CFDA.</span><span class="sxs-lookup"><span data-stu-id="a27ed-132">On the **Setup** FastTab, in the **Catalog of Federal Domestic Assistance** field, assign the CFDA number.</span></span> <span data-ttu-id="a27ed-133">Le numéro CFDA sur la subvention détermine le cluster CFDA pour la génération d’états.</span><span class="sxs-lookup"><span data-stu-id="a27ed-133">The CFDA number on the grant determines the CFDA cluster for reporting.</span></span>
3. <span data-ttu-id="a27ed-134">Sur le raccourci **Informations de contact**, entrez les informations sur le concédant en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="a27ed-134">On **Contact information** FastTab, enter the grantor information by following these steps:</span></span>

    1. <span data-ttu-id="a27ed-135">Dans le champ **Client de la subvention**, saisissez le client responsable de la subvention.</span><span class="sxs-lookup"><span data-stu-id="a27ed-135">In the **Grant customer** field, enter the customer who is responsible for the grant.</span></span> <span data-ttu-id="a27ed-136">Pour une subvention existante, ces informations peuvent déjà être saisies.</span><span class="sxs-lookup"><span data-stu-id="a27ed-136">For an existing grant, this information might already be entered.</span></span>
    2. <span data-ttu-id="a27ed-137">Indiquez si le client de la subvention est le bailleur de fonds.</span><span class="sxs-lookup"><span data-stu-id="a27ed-137">Indicate whether the grant customer is the funder.</span></span> <span data-ttu-id="a27ed-138">Si le client de la subvention est le bailleur de fonds, décochez la case **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-138">If the grant customer is the funder, leave the **Pass-through** check box cleared.</span></span> <span data-ttu-id="a27ed-139">Si un autre client est le bailleur de fonds et que le client de la subvention est responsable des dépenses et du suivi de l’argent, cochez la case **Validation**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-139">If another customer is the funder, and the grant customer is responsible for spending and tracking the money, select the **Pass-through** check box.</span></span>

4. <span data-ttu-id="a27ed-140">Si vous avez coché la case **Valider** à l’étape précédente, dans le champ **Organisme concédant**, entrez le client qui a fourni la subvention.</span><span class="sxs-lookup"><span data-stu-id="a27ed-140">If you selected the **Pass-through** check box in the previous step, in the **Grantor agency** field, enter the customer who provided the grant.</span></span> <span data-ttu-id="a27ed-141">L’organisme concédant et le client de la subvention ne peuvent pas être le même client.</span><span class="sxs-lookup"><span data-stu-id="a27ed-141">The grantor agency and the grant customer can't be the same customer.</span></span>

<span data-ttu-id="a27ed-142">Voici un exemple d’une subvention de validation :</span><span class="sxs-lookup"><span data-stu-id="a27ed-142">Here is an example of a pass-through grant:</span></span>

<span data-ttu-id="a27ed-143">Le gouvernement fédéral a financé un projet d’infrastructure pour un État.</span><span class="sxs-lookup"><span data-stu-id="a27ed-143">The federal government funded an infrastructure project for a state.</span></span> <span data-ttu-id="a27ed-144">Le gouvernement fédéral a donné l’argent à l’État à dépenser.</span><span class="sxs-lookup"><span data-stu-id="a27ed-144">The federal government gave the money to the state to spend.</span></span> <span data-ttu-id="a27ed-145">Dans ce cas, le gouvernement fédéral est l’organisme concédant et l’État est le client de la subvention.</span><span class="sxs-lookup"><span data-stu-id="a27ed-145">In this case, the federal government is the grantor agency, and the state is the grant customer.</span></span>

> [!NOTE] 
> <span data-ttu-id="a27ed-146">Lorsque vous activez la fonction pour la première fois, les numéros CFDA initiaux seront entrés en utilisant les numéros existants sur les subventions.</span><span class="sxs-lookup"><span data-stu-id="a27ed-146">When you first turn on the feature, initial CFDA numbers will be entered by using the existing numbers on grants.</span></span>

## <a name="exclude-grants-from-sefa-reporting-based-on-the-grant-type"></a><span data-ttu-id="a27ed-147">Exclure les subventions des rapports SEFA en fonction du type de subvention</span><span class="sxs-lookup"><span data-stu-id="a27ed-147">Exclude grants from SEFA reporting based on the grant type</span></span>

1. <span data-ttu-id="a27ed-148">Accédez à **Gestion et comptabilité des projets \> Configurer \> Subventions \> Types de subventions**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-148">Go to **Project management and accounting \> Setup \> Grants \> Grant types**.</span></span>
2. <span data-ttu-id="a27ed-149">Sur le raccourci **Informations par défaut**, cochez la case **Exclure de ’annexe des dépenses des bourses fédérales**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-149">On the **Default information** FastTab, select the **Exclude from Schedule of Expenditures of Federal Awards** check box.</span></span>
3. <span data-ttu-id="a27ed-150">Sélectionnez **Enregistrer** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="a27ed-150">Select **Save** to save your changes.</span></span>

## <a name="run-the-schedule-of-expenditures-of-federal-awards-inquiry"></a><span data-ttu-id="a27ed-151">Exécutez le calendrier des dépenses de l’enquête sur les bourses fédérales</span><span class="sxs-lookup"><span data-stu-id="a27ed-151">Run the Schedule of Expenditures of Federal Awards inquiry</span></span>

1. <span data-ttu-id="a27ed-152">Aller à **Gestion de projets et comptabilité \> Demandes de renseignements et rapports \> Demande de subvention \> Annexe des dépenses des bourses fédérales**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-152">Go to **Project management and accounting \> Inquiries and reports \> Grant inquiry \> Schedule of Expenditures of Federal Awards**.</span></span>
2. <span data-ttu-id="a27ed-153">Dans la section **Paramètres**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a27ed-153">In the **Parameters** section, follow these steps:</span></span>

    1. <span data-ttu-id="a27ed-154">Dans le champ **Intervalle de dates**, sélectionnez le code de l’intervalle de dates.</span><span class="sxs-lookup"><span data-stu-id="a27ed-154">In the **Date interval** field, select the code for the date interval.</span></span> <span data-ttu-id="a27ed-155">Sinon, dans les champs **Date de début** et **Date de fin**, définissez l’intervalle de dates.</span><span class="sxs-lookup"><span data-stu-id="a27ed-155">Alternatively, in the **From date** and **To date** fields, define the date interval.</span></span>
    2. <span data-ttu-id="a27ed-156">Facultatif : Pour inclure uniquement les transactions facturées en tant que revenus dans l’enquête, définissez l’option **Inclure uniquement les revenus facturés** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="a27ed-156">Optional: To include only billed transactions as revenue in the inquiry, set the **Include only billed revenues** option to **Yes**.</span></span>

## <a name="columns"></a><span data-ttu-id="a27ed-157">Colonnes</span><span class="sxs-lookup"><span data-stu-id="a27ed-157">Columns</span></span>

<span data-ttu-id="a27ed-158">L’enquête sur l’annexe des dépenses des bourses fédérales comprend les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a27ed-158">The Schedule of Expenditures of Federal Awards inquiry includes the following columns:</span></span>

- <span data-ttu-id="a27ed-159">Nom du groupement Catalogue d’assistance nationale fédérale</span><span class="sxs-lookup"><span data-stu-id="a27ed-159">Catalog of Federal Domestic Assistance cluster name</span></span>
- <span data-ttu-id="a27ed-160">Agence du donateur</span><span class="sxs-lookup"><span data-stu-id="a27ed-160">Grantor agency</span></span>
- <span data-ttu-id="a27ed-161">Organisme de validation</span><span class="sxs-lookup"><span data-stu-id="a27ed-161">Pass-through agency</span></span>
- <span data-ttu-id="a27ed-162">Nom de la subvention</span><span class="sxs-lookup"><span data-stu-id="a27ed-162">Grant name</span></span>
- <span data-ttu-id="a27ed-163">ID subvention</span><span class="sxs-lookup"><span data-stu-id="a27ed-163">Grant ID</span></span>
- <span data-ttu-id="a27ed-164">ID candidature de subvention</span><span class="sxs-lookup"><span data-stu-id="a27ed-164">Grant application ID</span></span>
- <span data-ttu-id="a27ed-165">Catalogue d’assistance nationale fédérale</span><span class="sxs-lookup"><span data-stu-id="a27ed-165">Catalog of Federal Domestic Assistance</span></span>
- <span data-ttu-id="a27ed-166">Réceptions</span><span class="sxs-lookup"><span data-stu-id="a27ed-166">Receipts</span></span>
- <span data-ttu-id="a27ed-167">Dépenses</span><span class="sxs-lookup"><span data-stu-id="a27ed-167">Expenditures</span></span>
