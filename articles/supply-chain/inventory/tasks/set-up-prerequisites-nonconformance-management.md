--- 
title: "Paramétrer des conditions préalables pour la gestion de la non-conformité"
description: "Utilisez cette procédure pour activer les processus de gestion de non-conformité."
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0a4062acc91e024e3a0a41c0b3cb35ff5ffe2a4a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-prerequisites-for-nonconformance-management"></a><span data-ttu-id="21191-103">Paramétrer des conditions préalables pour la gestion de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="21191-103">Set up prerequisites for nonconformance management</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="21191-104">Utilisez cette procédure pour activer les processus de gestion de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="21191-104">Use this procedure to enable nonconformance management processes.</span></span> <span data-ttu-id="21191-105">Une non-conformité décrit une procédure ou un article présentant un problème qualitatif (des informations descriptives incluent la source et le type du problème).</span><span class="sxs-lookup"><span data-stu-id="21191-105">A nonconformance describes a procedure or item that has a quality problem, where the descriptive information includes the source and type of problem.</span></span> <span data-ttu-id="21191-106">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="21191-106">This procedure uses the USMF demo data company.</span></span> <span data-ttu-id="21191-107">Cette procédure est généralement effectuée par un responsable de la qualité.</span><span class="sxs-lookup"><span data-stu-id="21191-107">This procedure is typically performed by a quality manager.</span></span>


## <a name="enable-quality-management-processes-within-the-company"></a><span data-ttu-id="21191-108">Activer les processus de gestion de la qualité au sein de la société</span><span class="sxs-lookup"><span data-stu-id="21191-108">Enable quality management processes within the company</span></span>
1. <span data-ttu-id="21191-109">Accédez à Gestion des stocks > Paramétrage > Paramètres de gestion des stocks et des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="21191-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="21191-110">Cliquez sur l'onglet Gestion de la qualité.</span><span class="sxs-lookup"><span data-stu-id="21191-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="21191-111">Sélectionnez Oui dans le champ Utiliser la gestion de la qualité.</span><span class="sxs-lookup"><span data-stu-id="21191-111">Select Yes in the Use quality management field.</span></span>
    * <span data-ttu-id="21191-112">Sélectionnez ce paramètre pour activer les processus de gestion de la qualité pour la société.</span><span class="sxs-lookup"><span data-stu-id="21191-112">Select this parameter to enable quality management processes for the company.</span></span>  
4. <span data-ttu-id="21191-113">Entrez un nombre dans le champ Taux horaire.</span><span class="sxs-lookup"><span data-stu-id="21191-113">In the Hourly rate field, enter a number.</span></span>
    * <span data-ttu-id="21191-114">Utilisez le champ Taux horaire pour entrer un taux horaire de main-œuvre dans la devise locale.</span><span class="sxs-lookup"><span data-stu-id="21191-114">Use the Hourly rate field to enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="21191-115">Le taux horaire permet de calculer les coûts des opérations associées à une non-conformité.</span><span class="sxs-lookup"><span data-stu-id="21191-115">The hourly rate is used for calculating costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="21191-116">Le taux horaire et les coûts calculés fournissent des informations de référence pour une non-conformité et n'interagissent pas avec les autres fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="21191-116">The hourly rate and calculated costs provide reference information for a nonconformance, and they do not interact with other functionality.</span></span>  
5. <span data-ttu-id="21191-117">Cliquez sur Paramétrage d'état.</span><span class="sxs-lookup"><span data-stu-id="21191-117">Click Report setup.</span></span>
    * <span data-ttu-id="21191-118">Cette page vous permet de définir les types de note d'état de qualité qui seront utilisés dans différents types d'états de gestion de la qualité.</span><span class="sxs-lookup"><span data-stu-id="21191-118">This page allows you define the quality report note types that will be used on different kinds of quality management reports.</span></span>  
6. <span data-ttu-id="21191-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-119">Close the page.</span></span>
7. <span data-ttu-id="21191-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-120">Close the page.</span></span>

## <a name="enable-user-for-nonconformance-processing"></a><span data-ttu-id="21191-121">Activer l'utilisateur pour le traitement de non-conformité</span><span class="sxs-lookup"><span data-stu-id="21191-121">Enable user for nonconformance processing</span></span>
1. <span data-ttu-id="21191-122">Accédez à Administration système > Utilisateurs > Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="21191-122">Go to System administration > Users > Users.</span></span>
    * <span data-ttu-id="21191-123">Pour traiter l'approbation d'une non-conformité, l'utilisateur qui approuve ou rejette la non-conformité doit avoir une valeur « Nom » affectée sur la page Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="21191-123">To process the approval of a nonconformance the user who  approves or rejects nonconformances must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="21191-124">Pour utiliser les notes de document, l'utilisateur doit également avoir activé la gestion des documents dans les options d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21191-124">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
2. <span data-ttu-id="21191-125">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="21191-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="21191-126">Par exemple, filtrez sur le champ Nom avec le valeur « Ricardo ».</span><span class="sxs-lookup"><span data-stu-id="21191-126">For example, filter on the Name field with a value of 'Ricardo'.</span></span>
    * <span data-ttu-id="21191-127">Utilisez le filtre pour rechercher l'utilisateur qui va approuver ou rejeter les enregistrements de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="21191-127">Use the filter to find the user who will be approving or rejecting the nonconformance records.</span></span>  
3. <span data-ttu-id="21191-128">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="21191-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="21191-129">Pour traiter l'approbation d'une non-conformité, assurez-vous que l'utilisateur qui approuve ou rejette une non-conformité ait une valeur « Nom » affectée sur la page Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="21191-129">To process the approval of a nonconformance, make sure the user who approves or rejects nonconformances has a “Name” value assigned on the Users page.</span></span>  
4. <span data-ttu-id="21191-130">Cliquez sur Options utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21191-130">Click User options.</span></span>
5. <span data-ttu-id="21191-131">Cliquez sur l'onglet Préférences.</span><span class="sxs-lookup"><span data-stu-id="21191-131">Click the Preferences tab.</span></span>
6. <span data-ttu-id="21191-132">Sélectionnez Oui dans le champ Activer la gestion des documents.</span><span class="sxs-lookup"><span data-stu-id="21191-132">Select Yes in the Enable document handling field.</span></span>
    * <span data-ttu-id="21191-133">Pour utiliser les notes de document, l'utilisateur doit également avoir activé la gestion des documents dans les options d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21191-133">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
7. <span data-ttu-id="21191-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-134">Close the page.</span></span>
8. <span data-ttu-id="21191-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-135">Close the page.</span></span>
9. <span data-ttu-id="21191-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-136">Close the page.</span></span>

## <a name="define-diagnostic-types-for-nonconformance-processing"></a><span data-ttu-id="21191-137">Définir les types de diagnostics pour le traitement de non-conformité</span><span class="sxs-lookup"><span data-stu-id="21191-137">Define diagnostic types for nonconformance processing</span></span>
1. <span data-ttu-id="21191-138">Accédez à Gestion des stocks > Paramétrage > Gestion de la qualité > Types de diagnostics.</span><span class="sxs-lookup"><span data-stu-id="21191-138">Go to Inventory management > Setup > Quality management > Diagnostic types.</span></span>
    * <span data-ttu-id="21191-139">Utilisez la page Types de diagnostics pour définir une classification des actions de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="21191-139">Use the Diagnostic types page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="21191-140">Une correction identifie le type d'action de diagnostic devant être entreprise pour une non-conformité approuvée, l'utilisateur devant l'exécuter et la date d'exécution demandée et prévue.</span><span class="sxs-lookup"><span data-stu-id="21191-140">A correction identifies what type of diagnostic action should be taken on an approved nonconformance, who should perform it, and the requested and planned completion date.</span></span>  
2. <span data-ttu-id="21191-141">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="21191-141">Click New.</span></span>
3. <span data-ttu-id="21191-142">Tapez une valeur dans le champ Diagnostic.</span><span class="sxs-lookup"><span data-stu-id="21191-142">In the Diagnostic field, type a value.</span></span>
4. <span data-ttu-id="21191-143">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="21191-143">In the Description field, type a value.</span></span>
5. <span data-ttu-id="21191-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-144">Close the page.</span></span>

## <a name="define-quality-charges-for-nonconformance-processing"></a><span data-ttu-id="21191-145">Définir les frais de qualité pour le traitement de non-conformité</span><span class="sxs-lookup"><span data-stu-id="21191-145">Define quality charges for nonconformance processing</span></span>
1. <span data-ttu-id="21191-146">Accédez à Gestion des stocks > Paramétrage > Gestion de la qualité > Frais de qualité.</span><span class="sxs-lookup"><span data-stu-id="21191-146">Go to Inventory management > Setup > Quality management > Quality charges.</span></span>
    * <span data-ttu-id="21191-147">Utilisez la page Frais de qualité pour définir une classification des frais qui seront utilisés dans les opérations liées aux non-conformités.</span><span class="sxs-lookup"><span data-stu-id="21191-147">Use the Quality charges page to define a classification of charges that will used in operations related to nonconformances.</span></span>  
2. <span data-ttu-id="21191-148">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="21191-148">Click New.</span></span>
3. <span data-ttu-id="21191-149">Tapez une valeur dans le champ Codes frais.</span><span class="sxs-lookup"><span data-stu-id="21191-149">In the Charges code field, type a value.</span></span>
4. <span data-ttu-id="21191-150">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="21191-150">In the Description field, type a value.</span></span>
5. <span data-ttu-id="21191-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-151">Close the page.</span></span>

## <a name="define-the-operations-for-nonconformance-processing"></a><span data-ttu-id="21191-152">Définir les opérations pour le traitement de non-conformité</span><span class="sxs-lookup"><span data-stu-id="21191-152">Define the operations for nonconformance processing</span></span>
1. <span data-ttu-id="21191-153">Accédez à Gestion des stocks > Paramétrage > Gestion de la qualité > Opérations.</span><span class="sxs-lookup"><span data-stu-id="21191-153">Go to Inventory management > Setup > Quality management > Operations.</span></span>
    * <span data-ttu-id="21191-154">Utilisez la page Opérations pour définir une classification des tâches pouvant être exécutées pour une non-conformité approuvée.</span><span class="sxs-lookup"><span data-stu-id="21191-154">Use the Operations page to define a classification of the work that may be performed for an approved nonconformance.</span></span> <span data-ttu-id="21191-155">Lorsque vous associez une opération associée à une non-conformité, vous pouvez définir des informations détaillées sur les matériaux, les heures travaillées et les charges diverses associées, requises pour l'exécution de l'opération.</span><span class="sxs-lookup"><span data-stu-id="21191-155">When you relate an operation to a nonconformance, you can define information about the associated material, labor hours, and miscellaneous charges that are required to perform the operation.</span></span> <span data-ttu-id="21191-156">Ces informations constituent la base de calcul du coût estimé d'exécution de l'opération.</span><span class="sxs-lookup"><span data-stu-id="21191-156">This information provides the basis for calculating an estimated cost for performing the operation.</span></span>  
2. <span data-ttu-id="21191-157">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="21191-157">Click New.</span></span>
3. <span data-ttu-id="21191-158">Tapez une valeur dans le champ Opérations.</span><span class="sxs-lookup"><span data-stu-id="21191-158">In the Operation field, type a value.</span></span>
4. <span data-ttu-id="21191-159">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="21191-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="21191-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-160">Close the page.</span></span>

## <a name="define-problem-types-for-nonconformance-processing"></a><span data-ttu-id="21191-161">Définir les types de problème pour le traitement de non-conformité</span><span class="sxs-lookup"><span data-stu-id="21191-161">Define problem types for nonconformance processing</span></span>
1. <span data-ttu-id="21191-162">Accédez à Gestion des stocks > Paramétrage > Gestion de la qualité > Types de problèmes.</span><span class="sxs-lookup"><span data-stu-id="21191-162">Go to Inventory management > Setup > Quality management > Problem types.</span></span>
    * <span data-ttu-id="21191-163">Utilisez la page Types de problèmes pour définir une classification des problèmes de qualité rencontrés dans les divers types de non-conformités.</span><span class="sxs-lookup"><span data-stu-id="21191-163">Use the Problem types page to define a classification of quality problems that are encountered in the various nonconformance types.</span></span> <span data-ttu-id="21191-164">Parmi les types de non-conformités on trouve : Interne, Client, Fournisseur, Demande de service, Production et Production de coproduits.</span><span class="sxs-lookup"><span data-stu-id="21191-164">The nonconformance types include Internal, Customer, Vendor, Service request, Production, and Co-product production.</span></span> <span data-ttu-id="21191-165">Un seul type de problème peut être associé à plusieurs types de non-conformités.</span><span class="sxs-lookup"><span data-stu-id="21191-165">A single problem type can be associated with multiple nonconformance types.</span></span>  
2. <span data-ttu-id="21191-166">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="21191-166">Click New.</span></span>
3. <span data-ttu-id="21191-167">Tapez une valeur dans le champ Type de problème.</span><span class="sxs-lookup"><span data-stu-id="21191-167">In the Problem type field, type a value.</span></span>
4. <span data-ttu-id="21191-168">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="21191-168">In the Description field, type a value.</span></span>
5. <span data-ttu-id="21191-169">Cliquez sur Types de non-conformités.</span><span class="sxs-lookup"><span data-stu-id="21191-169">Click Non conformance types.</span></span>
    * <span data-ttu-id="21191-170">Utilisez la page Types de non-conformités pour autoriser l'utilisation d'un type de problème pour un ou plusieurs types de non-conformités.</span><span class="sxs-lookup"><span data-stu-id="21191-170">Use the Non conformance types page to authorize the use of a problem type for one or more of the nonconformance types.</span></span> <span data-ttu-id="21191-171">Par exemple, un type de problème en lien avec un code défaut peut s'appliquer à tous les types de non-conformités, alors qu'un type de problème en lien avec la réclamation d'un client peut uniquement s'appliquer aux types de non-conformités Client et Demande de service.</span><span class="sxs-lookup"><span data-stu-id="21191-171">For example, a problem type regarding a defect code could apply to all nonconformance types, whereas a problem type about customer complaints may only apply to the customer and service request nonconformance types.</span></span>  
6. <span data-ttu-id="21191-172">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="21191-172">Click New.</span></span>
7. <span data-ttu-id="21191-173">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="21191-173">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="21191-174">Sélectionnez une option dans le champ Type de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="21191-174">In the Non conformance type field, select an option.</span></span>
9. <span data-ttu-id="21191-175">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-175">Close the page.</span></span>
10. <span data-ttu-id="21191-176">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-176">Close the page.</span></span>

## <a name="define-quarantine-zones-for-nonconformance-processing"></a><span data-ttu-id="21191-177">Définir les zones de quarantaine pour le traitement de non-conformité</span><span class="sxs-lookup"><span data-stu-id="21191-177">Define quarantine zones for nonconformance processing</span></span>
1. <span data-ttu-id="21191-178">Accédez à Gestion des stocks > Paramétrage > Gestion de la qualité > Zones de quarantaines.</span><span class="sxs-lookup"><span data-stu-id="21191-178">Go to Inventory management > Setup > Quality management > Quarantine zones.</span></span>
2. <span data-ttu-id="21191-179">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="21191-179">Click New.</span></span>
3. <span data-ttu-id="21191-180">Tapez une valeur dans le champ Zone de quarantaine.</span><span class="sxs-lookup"><span data-stu-id="21191-180">In the Quarantine zone field, type a value.</span></span>
4. <span data-ttu-id="21191-181">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="21191-181">In the Description field, type a value.</span></span>
5. <span data-ttu-id="21191-182">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21191-182">Close the page.</span></span>


