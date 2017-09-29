---
title: "Configuration des paramètres de RH dans les entités juridiques"
description: "Vous devez définir des paramètres partagés pour les enregistrements communs à des sociétés, tels que les Enregistrements de poste. Cet article explique comment définir des paramètres de Ressources humaines communs à des entités juridiques."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 90d348f8b8414d6e31092cdd18760375dd283155
ms.contentlocale: fr-fr
ms.lasthandoff: 06/29/2017


---

# <a name="set-up-hr-parameters-across-legal-entities"></a><span data-ttu-id="ca214-104">Configuration des paramètres de RH dans les entités juridiques</span><span class="sxs-lookup"><span data-stu-id="ca214-104">Set up HR parameters across legal entities</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="ca214-105">Vous devez définir des paramètres partagés pour les enregistrements communs à des sociétés, tels que les Enregistrements de poste.</span><span class="sxs-lookup"><span data-stu-id="ca214-105">You must set up shared parameters for records that are shared across companies, such as Position records.</span></span> <span data-ttu-id="ca214-106">Cet article explique comment définir des paramètres de Ressources humaines communs à des entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="ca214-106">This article explains how to set up Human resources parameters across legal entities.</span></span>

<span data-ttu-id="ca214-107">Certains types d'enregistrements, tels que les enregistrements de poste, sont partagés entre des sociétés.</span><span class="sxs-lookup"><span data-stu-id="ca214-107">Some types of records, such as Position records, are shared across companies.</span></span> <span data-ttu-id="ca214-108">Pour ces enregistrements, vous devez définir des paramètres partagés.</span><span class="sxs-lookup"><span data-stu-id="ca214-108">For these records, you must set up shared parameters.</span></span> <span data-ttu-id="ca214-109">Par exemple, vous utilisez la page **Paramètres partagés de ressources humaines** pour définir les paramètres de ressources humaines dans les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="ca214-109">For example, you use the **Human resources shared parameters** page to set up Human resources parameters across legal entities.</span></span> 

<span data-ttu-id="ca214-110">Sur la page **Paramètres partagés de ressources humaines**, les paramètres sont regroupés en zones, selon leur fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ca214-110">On the **Human resources shared parameters** page, parameters are grouped into areas, based on their functionality.</span></span> 

### <a name="previously-released-functionality"></a><span data-ttu-id="ca214-111">Fonctionnalité précédemment lancée</span><span class="sxs-lookup"><span data-stu-id="ca214-111">Previously released functionality</span></span>
<span data-ttu-id="ca214-112">Sous l'onglet **Identification**, vous devez sélectionner les types d'identifications qui représentent les numéros d'identification répertoriés sur la page.</span><span class="sxs-lookup"><span data-stu-id="ca214-112">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="ca214-113">Vous devez paramétrer des types d'identification pour pouvoir entrer des informations d'identification pour les travailleurs.</span><span class="sxs-lookup"><span data-stu-id="ca214-113">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="ca214-114">Les informations sur le numéro de sécurité sociale, le numéro d'identité national, l'ID étranger, et le code ID personnel sont tenues à jour sur la page **Type d'identification**.</span><span class="sxs-lookup"><span data-stu-id="ca214-114">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="ca214-115">Pour définir un nouveau type d'identification ou consulter la liste des types existants, cliquez sur **Gestion du personnel** &gt; **Onglet Liens** &gt; **Paramétrage** &gt; **Types d'identification**.</span><span class="sxs-lookup"><span data-stu-id="ca214-115">To define a new identification type or review the list of existing types, click **Personnel management** &gt; **Links tab** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="ca214-116">Vous pouvez entrer un code et une description simples.</span><span class="sxs-lookup"><span data-stu-id="ca214-116">You can enter a simple code and description.</span></span> 

### <a name="if-youre-using-dynamics-365-for-talent"></a><span data-ttu-id="ca214-117">Si vous utilisez Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="ca214-117">If you're using Dynamics 365 for Talent</span></span>
<span data-ttu-id="ca214-118">Sous l'onglet **Identification**, vous devez sélectionner les types d'identifications qui représentent les numéros d'identification répertoriés sur la page.</span><span class="sxs-lookup"><span data-stu-id="ca214-118">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="ca214-119">Vous devez paramétrer des types d'identification pour pouvoir entrer des informations d'identification pour les travailleurs.</span><span class="sxs-lookup"><span data-stu-id="ca214-119">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="ca214-120">Les informations sur le numéro de sécurité sociale, le numéro d'identité national, l'ID étranger, et le code ID personnel sont tenues à jour sur la page **Type d'identification**.</span><span class="sxs-lookup"><span data-stu-id="ca214-120">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="ca214-121">Pour définir un nouveau type d'identification ou consulter la liste des types existants, cliquez sur **Ressources humaines** &gt; **Paramétrage** &gt; **Types d'identification**.</span><span class="sxs-lookup"><span data-stu-id="ca214-121">To define a new identification type or review the list of existing types, click **Human resources** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="ca214-122">Vous pouvez entrer un code et une description simples.</span><span class="sxs-lookup"><span data-stu-id="ca214-122">You can enter a simple code and description.</span></span> 

<span data-ttu-id="ca214-123">Sous l'onglet **Souches de numéros**, vous pouvez sélectionner les souches de numéros utilisées pour les enregistrements suivants : Numéro personnel, Poste, ID demande de l'utilisateur, Document I-9, Candidat, Discussion, ID avantage et Action d'un membre du personnel (si ce type d'enregistrement est activé).</span><span class="sxs-lookup"><span data-stu-id="ca214-123">On the **Number sequences** tab, you can select the number sequences that are used for the following records: Personnel number, Position, User request ID, I-9 document, Applicant, Discussion, Benefit ID, and Personnel action (if this record type is enabled).</span></span> <span data-ttu-id="ca214-124">Pour tenir à jour les références et codes des souches de numéros, utilisez la page de liste **Souches de numéros**.</span><span class="sxs-lookup"><span data-stu-id="ca214-124">To maintain number sequence references and codes, use the **Number sequences** list page.</span></span> <span data-ttu-id="ca214-125">Pour rechercher cette page, utilisez la fonctionnalité de recherche de page.</span><span class="sxs-lookup"><span data-stu-id="ca214-125">To find this page, use the page search feature.</span></span> 

<span data-ttu-id="ca214-126">Sous l'onglet **Postes**, indiquez si de nouveaux postes sont disponibles pour l'affectation par défaut :</span><span class="sxs-lookup"><span data-stu-id="ca214-126">On the **Positions** tab, indicate whether new positions are available for assignment by default:</span></span>

-   <span data-ttu-id="ca214-127">**Toujours** – Vous ne pouvez pas affecter de collaborateurs à de nouveaux postes lorsque des postes sont créés.</span><span class="sxs-lookup"><span data-stu-id="ca214-127">**Always** – You can assign workers to new positions when positions are created.</span></span> <span data-ttu-id="ca214-128">Lorsque des postes sont créés, la date et l'heure **Disponible pour affectation** de l'onglet **Général** de la page **Poste** sont automatiquement définis à la date et à l'heure de création.</span><span class="sxs-lookup"><span data-stu-id="ca214-128">When positions are created, the **Available for assignment** date and time on the **General** tab of the **Position** page are automatically set to the creation date and time.</span></span>
-   <span data-ttu-id="ca214-129">**Jamais** – Vous ne pouvez pas affecter de collaborateurs à de nouveaux postes lorsque des postes sont créés.</span><span class="sxs-lookup"><span data-stu-id="ca214-129">**Never** – You can't assign workers to new positions when positions are created.</span></span> <span data-ttu-id="ca214-130">Si vous sélectionnez cette option, vous devez ouvrir la page **Poste** pour chaque nouveau poste lorsqu'il devient disponible, puis sous l'onglet **Général**, entrez la date **Disponible pour affectation** afin d'activer l'affectation du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="ca214-130">If you select this option, you must open the **Position** page for each new position as it becomes available, and then, on the **General** tab, enter the **Available for assignment** date to enable worker assignment.</span></span>


<a name="see-also"></a><span data-ttu-id="ca214-131">Voir également :</span><span class="sxs-lookup"><span data-stu-id="ca214-131">See also</span></span>
--------

[<span data-ttu-id="ca214-132">Définition des paramètres de RH spécifiques à la société</span><span class="sxs-lookup"><span data-stu-id="ca214-132">Set up company specific HR parameters</span></span>](set-up-company-specific-hr-parameters.md)




