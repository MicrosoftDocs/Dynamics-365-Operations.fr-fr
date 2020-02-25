---
title: ER Concevoir un modèle de données spécifiques au domaine
description: Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle de données pour les documents de paiement électronique.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3fe08b30977b8515ffd8d0acc1fd8f4b3085de93
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026084"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="e27a5-103">ER Concevoir un modèle de données spécifiques au domaine</span><span class="sxs-lookup"><span data-stu-id="e27a5-103">ER Design domain specific data model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e27a5-104">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle de données pour les documents de paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="e27a5-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="e27a5-105">Ce modèle de données sera utilisé ultérieurement comme source de données quand vous créerez le format des documents de paiement.</span><span class="sxs-lookup"><span data-stu-id="e27a5-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="e27a5-106">Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="e27a5-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="e27a5-107">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="e27a5-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="e27a5-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="e27a5-109">Sélectionnez le fournisseur de configuration pour la société fictive, « Litware, Inc ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="e27a5-110">Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="e27a5-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="e27a5-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="e27a5-112">Vous allez créer une configuration qui contient un modèle de données pour les documents de paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="e27a5-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="e27a5-113">Ce modèle de données sera utilisé ultérieurement comme source de données quand vous allez créer le format pour les documents de paiement.</span><span class="sxs-lookup"><span data-stu-id="e27a5-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="e27a5-114">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="e27a5-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="e27a5-115">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="e27a5-116">Tapez « Paiements (modèle simplifié) » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="e27a5-117">Paiements (modèle simplifié)</span><span class="sxs-lookup"><span data-stu-id="e27a5-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="e27a5-118">Tapez « Configuration du modèle de paiement » dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="e27a5-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="e27a5-119">Configuration du modèle de paiement</span><span class="sxs-lookup"><span data-stu-id="e27a5-119">Payment model configuration</span></span>  
    * <span data-ttu-id="e27a5-120">Le fournisseur de configuration actif est automatiquement entré ici.</span><span class="sxs-lookup"><span data-stu-id="e27a5-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="e27a5-121">Ce fournisseur pourra mettre à jour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="e27a5-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="e27a5-122">D'autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="e27a5-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="e27a5-123">Cliquez sur le bouton « Créer la configuration » pour terminer la tâche de création de la configuration.</span><span class="sxs-lookup"><span data-stu-id="e27a5-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="e27a5-124">Créer un modèle de données</span><span class="sxs-lookup"><span data-stu-id="e27a5-124">Create a data model</span></span>
<span data-ttu-id="e27a5-125">Vous créez un modèle de données pour la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e27a5-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="e27a5-126">Cette version de configuration aura un statut de brouillon.</span><span class="sxs-lookup"><span data-stu-id="e27a5-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="e27a5-127">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="e27a5-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="e27a5-128">Définir la structure d'une partie qui participe à un processus de paiement</span><span class="sxs-lookup"><span data-stu-id="e27a5-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="e27a5-129">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="e27a5-130">Dans le champ Nom, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="e27a5-131">Partie</span><span class="sxs-lookup"><span data-stu-id="e27a5-131">Party</span></span>  
3. <span data-ttu-id="e27a5-132">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-132">Click Add.</span></span>
4. <span data-ttu-id="e27a5-133">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="e27a5-134">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="e27a5-135">Nom</span><span class="sxs-lookup"><span data-stu-id="e27a5-135">Name</span></span>  
6. <span data-ttu-id="e27a5-136">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="e27a5-137">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-137">Click Add.</span></span>
8. <span data-ttu-id="e27a5-138">Dans le champ Rechercher, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="e27a5-139">Partie</span><span class="sxs-lookup"><span data-stu-id="e27a5-139">Party</span></span>  
9. <span data-ttu-id="e27a5-140">Cliquez sur Précédent</span><span class="sxs-lookup"><span data-stu-id="e27a5-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="e27a5-141">Définir la structure de la banque pour ce modèle</span><span class="sxs-lookup"><span data-stu-id="e27a5-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="e27a5-142">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="e27a5-143">Tapez « Agent » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="e27a5-144">Agent ;</span><span class="sxs-lookup"><span data-stu-id="e27a5-144">Agent</span></span>  
3. <span data-ttu-id="e27a5-145">Sélectionnez « Enregistrement » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="e27a5-146">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-146">Click Add.</span></span>
5. <span data-ttu-id="e27a5-147">Dans le champ Description, entrez « Institution financière (une banque, par exemple) chargée d'un compte de la partie (débiteur/créditeur) ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="e27a5-148">Institution financière (une banque, par exemple) chargée d'un compte de la partie (débiteur/créditeur).</span><span class="sxs-lookup"><span data-stu-id="e27a5-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="e27a5-149">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="e27a5-150">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="e27a5-151">Nom</span><span class="sxs-lookup"><span data-stu-id="e27a5-151">Name</span></span>  
8. <span data-ttu-id="e27a5-152">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="e27a5-153">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-153">Click Add.</span></span>
10. <span data-ttu-id="e27a5-154">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="e27a5-155">Tapez SWIFT dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="e27a5-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="e27a5-156">SWIFT</span></span>  
12. <span data-ttu-id="e27a5-157">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-157">Click Add.</span></span>
13. <span data-ttu-id="e27a5-158">Dans le champ Description, entrez « Code d'identification de la banque ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="e27a5-159">Code d'identification de la banque</span><span class="sxs-lookup"><span data-stu-id="e27a5-159">Bank identification code</span></span>  
14. <span data-ttu-id="e27a5-160">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="e27a5-161">Tapez « RoutingNumber » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="e27a5-162">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="e27a5-162">RoutingNumber</span></span>  
16. <span data-ttu-id="e27a5-163">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-163">Click Add.</span></span>
17. <span data-ttu-id="e27a5-164">Dans le champ Description, entrez « Numéro d'acheminement ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="e27a5-165">Numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="e27a5-165">Routing number</span></span>  
18. <span data-ttu-id="e27a5-166">Cliquez sur Précédent</span><span class="sxs-lookup"><span data-stu-id="e27a5-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="e27a5-167">Définir la structure de compte de la banque pour ce modèle</span><span class="sxs-lookup"><span data-stu-id="e27a5-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="e27a5-168">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="e27a5-169">Tapez « Compte » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="e27a5-170">Compte</span><span class="sxs-lookup"><span data-stu-id="e27a5-170">Account</span></span>  
3. <span data-ttu-id="e27a5-171">Sélectionnez « Enregistrement » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="e27a5-172">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-172">Click Add.</span></span>
5. <span data-ttu-id="e27a5-173">Dans le champ Description, entrez « Identification d'un compte d'une partie dans une institution financière (une banque, par exemple) ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="e27a5-174">Identification d'un compte d'une partie dans une institution financière (une banque, par exemple).</span><span class="sxs-lookup"><span data-stu-id="e27a5-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="e27a5-175">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="e27a5-176">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="e27a5-177">Devise</span><span class="sxs-lookup"><span data-stu-id="e27a5-177">Currency</span></span>  
8. <span data-ttu-id="e27a5-178">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="e27a5-179">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-179">Click Add.</span></span>
10. <span data-ttu-id="e27a5-180">Dans le champ Description, entrez « Code devise ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="e27a5-181">Code devise</span><span class="sxs-lookup"><span data-stu-id="e27a5-181">Currency code</span></span>  
11. <span data-ttu-id="e27a5-182">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="e27a5-183">Tapez « Numéro » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="e27a5-184">Numéro</span><span class="sxs-lookup"><span data-stu-id="e27a5-184">Number</span></span>  
13. <span data-ttu-id="e27a5-185">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-185">Click Add.</span></span>
14. <span data-ttu-id="e27a5-186">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="e27a5-187">Tapez « IBAN » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="e27a5-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="e27a5-188">IBAN</span></span>  
16. <span data-ttu-id="e27a5-189">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-189">Click Add.</span></span>
17. <span data-ttu-id="e27a5-190">Dans le champ Description, entrez « Numéro de compte bancaire international ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="e27a5-191">Numéro de compte bancaire international</span><span class="sxs-lookup"><span data-stu-id="e27a5-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="e27a5-192">Définir la structure du message de paiement pour le type de virement.</span><span class="sxs-lookup"><span data-stu-id="e27a5-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="e27a5-193">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="e27a5-194">Dans le nœud Nouveau sous forme de champ, entrez « Racine du modèle ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="e27a5-195">Tapez « CustomerCreditTransferInitiation » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="e27a5-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="e27a5-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="e27a5-197">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-197">Click Add.</span></span>
5. <span data-ttu-id="e27a5-198">Dans le champ Rechercher, tapez « CustomerCreditTransferInitiation ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="e27a5-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="e27a5-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="e27a5-200">Cliquez sur Précédent</span><span class="sxs-lookup"><span data-stu-id="e27a5-200">Click Find previous.</span></span>
7. <span data-ttu-id="e27a5-201">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="e27a5-202">Tapez « MessageIdentification » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="e27a5-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="e27a5-203">MessageIdentification</span></span>  
9. <span data-ttu-id="e27a5-204">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-204">Click Add.</span></span>
10. <span data-ttu-id="e27a5-205">Dans le champ Description, entrez « Référence point à point affectée par le donneur d'ordre (et envoyée à la partie suivante) afin d'identifier le message ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="e27a5-206">Référence point à point affectée par le donneur d'ordre et envoyée à la partie suivante dans la chaîne afin d'identifier le message.</span><span class="sxs-lookup"><span data-stu-id="e27a5-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="e27a5-207">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="e27a5-208">Tapez « ProcessingDateTime » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="e27a5-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="e27a5-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="e27a5-210">Sélectionnez « DateTime » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="e27a5-211">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-211">Click Add.</span></span>
15. <span data-ttu-id="e27a5-212">Dans le champ Description, entrez « Date et heure de création du message de paiement ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="e27a5-213">Date et heure de création du message de paiement</span><span class="sxs-lookup"><span data-stu-id="e27a5-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="e27a5-214">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="e27a5-215">Définir la structure de transaction de paiement pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="e27a5-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="e27a5-216">Tapez « Paiements » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="e27a5-217">Paiements</span><span class="sxs-lookup"><span data-stu-id="e27a5-217">Payments</span></span>  
18. <span data-ttu-id="e27a5-218">Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="e27a5-219">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-219">Click Add.</span></span>
20. <span data-ttu-id="e27a5-220">Dans le champ Description, entrez « Lignes de paiement du message actuel ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="e27a5-221">Lignes de paiement du message actuel</span><span class="sxs-lookup"><span data-stu-id="e27a5-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="e27a5-222">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="e27a5-223">Tapez « Créancier » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="e27a5-224">Créancier</span><span class="sxs-lookup"><span data-stu-id="e27a5-224">Creditor</span></span>  
23. <span data-ttu-id="e27a5-225">Sélectionnez « Enregistrement » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="e27a5-226">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-226">Click Add.</span></span>
25. <span data-ttu-id="e27a5-227">Dans le champ Description, entrez « Partie à laquelle un montant est dû ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="e27a5-228">Partie à laquelle un montant est dû.</span><span class="sxs-lookup"><span data-stu-id="e27a5-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="e27a5-229">Cliquez sur Basculer la référence d'élément.</span><span class="sxs-lookup"><span data-stu-id="e27a5-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="e27a5-230">Dans le champ Rechercher, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="e27a5-231">Partie</span><span class="sxs-lookup"><span data-stu-id="e27a5-231">Party</span></span>  
28. <span data-ttu-id="e27a5-232">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="e27a5-232">Click Find next.</span></span>
29. <span data-ttu-id="e27a5-233">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e27a5-233">Click OK.</span></span>
30. <span data-ttu-id="e27a5-234">Dans le champ Rechercher, tapez « Paiements ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="e27a5-235">Paiements</span><span class="sxs-lookup"><span data-stu-id="e27a5-235">Payments</span></span>  
31. <span data-ttu-id="e27a5-236">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="e27a5-236">Click Find next.</span></span>
32. <span data-ttu-id="e27a5-237">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="e27a5-238">Tapez « Débiteur » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="e27a5-239">Débiteur</span><span class="sxs-lookup"><span data-stu-id="e27a5-239">Debtor</span></span>  
34. <span data-ttu-id="e27a5-240">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-240">Click Add.</span></span>
35. <span data-ttu-id="e27a5-241">Dans le champ Description, entrez « Partie qui doit une somme d'argent au créancier (final) ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="e27a5-242">Partie qui doit une somme d'argent au créancier (final).</span><span class="sxs-lookup"><span data-stu-id="e27a5-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="e27a5-243">Cliquez sur Basculer la référence d'élément.</span><span class="sxs-lookup"><span data-stu-id="e27a5-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="e27a5-244">Dans le champ Rechercher, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="e27a5-245">Partie</span><span class="sxs-lookup"><span data-stu-id="e27a5-245">Party</span></span>  
38. <span data-ttu-id="e27a5-246">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="e27a5-246">Click Find next.</span></span>
39. <span data-ttu-id="e27a5-247">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e27a5-247">Click OK.</span></span>
40. <span data-ttu-id="e27a5-248">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="e27a5-248">Click Find next.</span></span>
41. <span data-ttu-id="e27a5-249">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="e27a5-250">Tapez « Description » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="e27a5-251">Description</span><span class="sxs-lookup"><span data-stu-id="e27a5-251">Description</span></span>  
43. <span data-ttu-id="e27a5-252">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="e27a5-253">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-253">Click Add.</span></span>
45. <span data-ttu-id="e27a5-254">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="e27a5-255">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="e27a5-256">Devise</span><span class="sxs-lookup"><span data-stu-id="e27a5-256">Currency</span></span>  
47. <span data-ttu-id="e27a5-257">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-257">Click Add.</span></span>
48. <span data-ttu-id="e27a5-258">Dans le champ Description, entrez « Code devise ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="e27a5-259">Code devise</span><span class="sxs-lookup"><span data-stu-id="e27a5-259">Currency code</span></span>  
49. <span data-ttu-id="e27a5-260">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="e27a5-261">Tapez « TransactionDate » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="e27a5-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="e27a5-262">TransactionDate</span></span>  
51. <span data-ttu-id="e27a5-263">Sélectionnez « Date » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="e27a5-264">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-264">Click Add.</span></span>
53. <span data-ttu-id="e27a5-265">Dans le champ Description, entrez « Date de transaction ».</span><span class="sxs-lookup"><span data-stu-id="e27a5-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="e27a5-266">Date de transaction</span><span class="sxs-lookup"><span data-stu-id="e27a5-266">Transaction date</span></span>  
54. <span data-ttu-id="e27a5-267">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="e27a5-268">Tapez « InstructedAmount » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="e27a5-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="e27a5-269">InstructedAmount</span></span>  
56. <span data-ttu-id="e27a5-270">Sélectionnez « Réel » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="e27a5-271">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-271">Click Add.</span></span>
58. <span data-ttu-id="e27a5-272">Dans le champ Description, entrez « Montant à transférer entre le débiteur et le créancier, avant déduction des frais.</span><span class="sxs-lookup"><span data-stu-id="e27a5-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="e27a5-273">Le montant doit être exprimé dans la devise choisie par la partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="e27a5-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="e27a5-274">Montant à transférer entre le débiteur et le créancier, avant déduction des frais.</span><span class="sxs-lookup"><span data-stu-id="e27a5-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="e27a5-275">Le montant doit être exprimé dans la devise choisie par la partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="e27a5-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="e27a5-276">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e27a5-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="e27a5-277">Tapez « End2EndID » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="e27a5-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="e27a5-278">End2EndID</span></span>  
61. <span data-ttu-id="e27a5-279">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="e27a5-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="e27a5-280">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e27a5-280">Click Add.</span></span>
63. <span data-ttu-id="e27a5-281">Dans le champ Description, entrez « Identification unique affectée par la partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="e27a5-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="e27a5-282">Cette identification est transmise telle quelle tout au long de la chaîne de bout en bout. »</span><span class="sxs-lookup"><span data-stu-id="e27a5-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="e27a5-283">Identification unique affectée par la partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="e27a5-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="e27a5-284">Cette identification est transmise telle quelle tout au long de la chaîne de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="e27a5-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="e27a5-285">Tapez « PaymentModel » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e27a5-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="e27a5-286">Le nom PaymentModel s'aligne avec les interfaces prédéfinies des écrans de paiement.</span><span class="sxs-lookup"><span data-stu-id="e27a5-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="e27a5-287">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e27a5-287">Click Save.</span></span>
66. <span data-ttu-id="e27a5-288">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e27a5-288">Close the page.</span></span>

