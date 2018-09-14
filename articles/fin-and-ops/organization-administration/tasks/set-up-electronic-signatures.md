--- 
title: "Paramétrage de signatures électroniques"
description: "Utilisez cette procédure pour configurer des signatures électroniques."
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: eb6bf529b1e94d598e219482f182140402f2928a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-electronic-signatures"></a><span data-ttu-id="23554-103">Paramétrage de signatures électroniques</span><span class="sxs-lookup"><span data-stu-id="23554-103">Set up electronic signatures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="23554-104">Utilisez cette procédure pour configurer des signatures électroniques.</span><span class="sxs-lookup"><span data-stu-id="23554-104">Use this procedure to set up electronic signatures.</span></span> <span data-ttu-id="23554-105">Une signature électronique confirme l'identité d'une personne qui va commencer ou approuver une procédure informatique.</span><span class="sxs-lookup"><span data-stu-id="23554-105">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="23554-106">La société fictive de démonstration utilisée pour créer cette procédure est DAT.</span><span class="sxs-lookup"><span data-stu-id="23554-106">The demo data company used to create this procedure is DAT.</span></span>


## <a name="enable-the-electronic-signature-configuration-key"></a><span data-ttu-id="23554-107">Activez la clé de configuration Signature électronique</span><span class="sxs-lookup"><span data-stu-id="23554-107">Enable the Electronic signature configuration key</span></span>
1. <span data-ttu-id="23554-108">Accédez à Administration système > Paramétrage > Configuration des licences.</span><span class="sxs-lookup"><span data-stu-id="23554-108">Go to System administration > Setup > License configuration.</span></span>
2. <span data-ttu-id="23554-109">Dans l'arborescence, développez « Administration ».</span><span class="sxs-lookup"><span data-stu-id="23554-109">In the tree, expand 'Administration'.</span></span>
    * <span data-ttu-id="23554-110">Vérifiez que la case à cocher Signature électronique est activée.</span><span class="sxs-lookup"><span data-stu-id="23554-110">Verify that the Electronic signature check box is selected.</span></span>  
    * <span data-ttu-id="23554-111">Si la case à cocher Signature électronique n'est pas activée, vous devez activer le mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="23554-111">If the Electronic signature check box is not selected, you must enable maintenance mode.</span></span> <span data-ttu-id="23554-112">Le mode de maintenance peut être activé dans cet environnement en exécutant une tâche de maintenance à partir de Lifecycle Services ou en utilisant localement l'outil Deployment.Setup.</span><span class="sxs-lookup"><span data-stu-id="23554-112">Maintenance mode can be enabled in this environment by running a maintenance job from Lifecycle Services, or by using the Deployment.Setup tool locally.</span></span>  
3. <span data-ttu-id="23554-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="23554-113">Close the page.</span></span>

## <a name="set-up-electronic-signature-parameters"></a><span data-ttu-id="23554-114">Définition des paramètres de signature électronique</span><span class="sxs-lookup"><span data-stu-id="23554-114">Set up electronic signature parameters</span></span>
1. <span data-ttu-id="23554-115">Accédez à Administration d'organisation > Paramétrage > Signature électronique > Paramètres de signature électronique.</span><span class="sxs-lookup"><span data-stu-id="23554-115">Go to Organization administration > Setup > Electronic signature > Electronic signature parameters.</span></span>
2. <span data-ttu-id="23554-116">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="23554-116">Click Edit.</span></span>
3. <span data-ttu-id="23554-117">Dans le champ Remarque, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="23554-117">In the Notice field, type a value.</span></span>
    * <span data-ttu-id="23554-118">Entrez l'avis que les signataires reçoivent lorsqu'une signature est demandée.</span><span class="sxs-lookup"><span data-stu-id="23554-118">Enter the notice that signers will receive when a signature is requested.</span></span> <span data-ttu-id="23554-119">Vous pouvez entrer un texte.</span><span class="sxs-lookup"><span data-stu-id="23554-119">You can enter any text.</span></span> <span data-ttu-id="23554-120">Généralement, ce texte explique à l'utilisateur en quoi consiste la signature électronique d'un document.</span><span class="sxs-lookup"><span data-stu-id="23554-120">Typically, this text tells the user what it means to sign a document electronically.</span></span>  
    * <span data-ttu-id="23554-121">Si vous souhaitez entrer le texte de la remarque dans d'autres langues, cliquez sur le bouton Traductions.</span><span class="sxs-lookup"><span data-stu-id="23554-121">If you want to enter the Notice text in additional languages, click the Translations button.</span></span>  
4. <span data-ttu-id="23554-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="23554-122">Click Save.</span></span>
5. <span data-ttu-id="23554-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="23554-123">Close the page.</span></span>

## <a name="set-up-reason-codes-for-electronic-signatures"></a><span data-ttu-id="23554-124">Paramétrage de codes motif pour les signatures électroniques</span><span class="sxs-lookup"><span data-stu-id="23554-124">Set up reason codes for electronic signatures</span></span>
1. <span data-ttu-id="23554-125">Accédez à Administration d'organisation > Paramétrage > Signature électronique > Codes motif des signatures électroniques.</span><span class="sxs-lookup"><span data-stu-id="23554-125">Go to Organization administration > Setup > Electronic signature > Electronic signature reason codes.</span></span>
2. <span data-ttu-id="23554-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="23554-126">Click New.</span></span>
    * <span data-ttu-id="23554-127">Vous devez paramétrer des codes motif avant d'utiliser les signatures électroniques.</span><span class="sxs-lookup"><span data-stu-id="23554-127">You must set up reason codes before using electronic signatures.</span></span> <span data-ttu-id="23554-128">Un code motif valide est obligatoire lors de la signature d'un document.</span><span class="sxs-lookup"><span data-stu-id="23554-128">A valid reason code is required when signing a document.</span></span>     <span data-ttu-id="23554-129">Un signataire sélectionne un code motif pour spécifier l'objectif d'une signature électronique.</span><span class="sxs-lookup"><span data-stu-id="23554-129">A signer selects a reason code to indicate the purpose of an electronic signature.</span></span> <span data-ttu-id="23554-130">Par exemple, un code de motif peut être utilisé pour indiquer l'approbation légale.</span><span class="sxs-lookup"><span data-stu-id="23554-130">For example, a reason code could be used to indicate legal approval.</span></span>  
3. <span data-ttu-id="23554-131">Dans le champ Code motif, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="23554-131">In the Reason code field, type a value.</span></span>
4. <span data-ttu-id="23554-132">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="23554-132">In the Description field, type a value.</span></span>
    * <span data-ttu-id="23554-133">Entrez les codes motif supplémentaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="23554-133">Enter additional reason codes, if needed.</span></span>  
5. <span data-ttu-id="23554-134">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="23554-134">Click Save.</span></span>
6. <span data-ttu-id="23554-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="23554-135">Close the page.</span></span>

## <a name="require-electronic-signatures-for-existing-processes"></a><span data-ttu-id="23554-136">Demander des signatures électroniques pour des processus existants</span><span class="sxs-lookup"><span data-stu-id="23554-136">Require electronic signatures for existing processes</span></span>
1. <span data-ttu-id="23554-137">Accédez à Administration d'organisation > Paramétrage > Signature électronique > Demandes de signature électronique.</span><span class="sxs-lookup"><span data-stu-id="23554-137">Go to Organization administration > Setup > Electronic signature > Electronic signature requirements.</span></span>
2. <span data-ttu-id="23554-138">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="23554-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="23554-139">Sélectionnez un processus nécessitant des signatures électroniques.</span><span class="sxs-lookup"><span data-stu-id="23554-139">Select a process that requires electronic signatures.</span></span>  
3. <span data-ttu-id="23554-140">Activez ou désactivez la case à cocher Signature.</span><span class="sxs-lookup"><span data-stu-id="23554-140">Select or clear the Signature required check box.</span></span>
    * <span data-ttu-id="23554-141">Répétez ces étapes pour chaque processus qui exige des signatures électroniques.</span><span class="sxs-lookup"><span data-stu-id="23554-141">Repeat these steps for each process that requires electronic signatures.</span></span>  
4. <span data-ttu-id="23554-142">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="23554-142">Click Save.</span></span>

## <a name="create-a-custom-requirement-for-electronic-signatures"></a><span data-ttu-id="23554-143">Créer une demande personnalisée pour des signatures électroniques</span><span class="sxs-lookup"><span data-stu-id="23554-143">Create a custom requirement for electronic signatures</span></span>
1. <span data-ttu-id="23554-144">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="23554-144">Click New.</span></span>
2. <span data-ttu-id="23554-145">Activez ou désactivez la case à cocher Signature.</span><span class="sxs-lookup"><span data-stu-id="23554-145">Select or clear the Signature required check box.</span></span>
3. <span data-ttu-id="23554-146">Dans le champ Nom, entrez un nom pour le processus qui nécessite des signatures électroniques.</span><span class="sxs-lookup"><span data-stu-id="23554-146">In the Name field, enter a name for the process that requires electronic signatures.</span></span>
4. <span data-ttu-id="23554-147">Dans le champ Nom de table, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="23554-147">In the Table name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="23554-148">Dans la liste, localisez et sélectionnez la table dans laquelle les données à signer sont stockées.</span><span class="sxs-lookup"><span data-stu-id="23554-148">In the list, find and select the table where the data that must be signed is stored.</span></span>
6. <span data-ttu-id="23554-149">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="23554-149">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="23554-150">Dans le champ Nom du champ, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="23554-150">In the Field name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="23554-151">Dans la liste, localisez et sélectionnez le champ de la table à surveiller.</span><span class="sxs-lookup"><span data-stu-id="23554-151">In the list, find and select the field in the table that you want to monitor.</span></span>
9. <span data-ttu-id="23554-152">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="23554-152">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="23554-153">Spécifiez le moment auquel une signature est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="23554-153">Specify when a signature is required.</span></span>     <span data-ttu-id="23554-154">Sélectionnez Toujours si une signature est obligatoire lorsque les données d'un champ sont modifiées.</span><span class="sxs-lookup"><span data-stu-id="23554-154">Select Always if a signature is required when the data in the field changes.</span></span>     <span data-ttu-id="23554-155">Sélectionnez Uniquement pour spécifier qu'une signature n'est obligatoire que dans certaines conditions.</span><span class="sxs-lookup"><span data-stu-id="23554-155">Select Only if a signature is required only under certain conditions.</span></span> <span data-ttu-id="23554-156">Si vous sélectionnez Uniquement, vous devez également sélectionner l'une des options suivantes : Lorsqu'un enregistrement est inséré, Lorsqu'un enregistrement est mis à jour, ou Lorsqu'un enregistrement est supprimé.</span><span class="sxs-lookup"><span data-stu-id="23554-156">If you select Only, you must also select one of the following options: When a record is inserted, When a record is updated, or When a record is deleted.</span></span>  
10. <span data-ttu-id="23554-157">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="23554-157">Click Save.</span></span>
11. <span data-ttu-id="23554-158">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="23554-158">Close the page.</span></span>


