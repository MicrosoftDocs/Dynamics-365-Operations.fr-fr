--- 
title: "Concevoir un modèle de données spécifique au domaine pour la gestion des états électroniques (ER)"
description: "Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle de données pour les documents de paiement électronique."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6a9fff90af93e20e7f812022593d25963542fac1
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="design-a-domain-specific-data-model-for-electronic-reporting-er"></a><span data-ttu-id="09498-103">Concevoir un modèle de données spécifique au domaine pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="09498-103">Design a domain-specific data model for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="09498-104">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle de données pour les documents de paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="09498-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="09498-105">Ce modèle de données sera utilisé ultérieurement comme source de données quand vous créerez le format des documents de paiement.</span><span class="sxs-lookup"><span data-stu-id="09498-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>



<span data-ttu-id="09498-106">Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="09498-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="09498-107">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="09498-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

1. <span data-ttu-id="09498-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="09498-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="09498-109">Sélectionnez le fournisseur de configuration pour la société fictive, « Litware, Inc ».</span><span class="sxs-lookup"><span data-stu-id="09498-109">Select the configuration provider for sample company, ‘Litware, Inc.’</span></span> <span data-ttu-id="09498-110">Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="09498-110">If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
2. <span data-ttu-id="09498-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="09498-111">Click Reporting configurations.</span></span>
    * <span data-ttu-id="09498-112">Vous allez créer une configuration qui contient un modèle de données pour les documents de paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="09498-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="09498-113">Ce modèle de données sera utilisé ultérieurement comme source de données quand vous allez créer le format pour les documents de paiement.</span><span class="sxs-lookup"><span data-stu-id="09498-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="09498-114">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="09498-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="09498-115">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="09498-116">Tapez « Paiements (modèle simplifié) » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-116">In the Name field, type 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="09498-117">Paiements (modèle simplifié)</span><span class="sxs-lookup"><span data-stu-id="09498-117">Payments (simplified model)</span></span>  
3. <span data-ttu-id="09498-118">Tapez « Configuration du modèle de paiement » dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="09498-118">In the Description field, type 'Payment model configuration'.</span></span>
    * <span data-ttu-id="09498-119">Configuration du modèle de paiement</span><span class="sxs-lookup"><span data-stu-id="09498-119">Payment model configuration</span></span>  
    * <span data-ttu-id="09498-120">Le fournisseur de configuration actif est automatiquement entré ici.</span><span class="sxs-lookup"><span data-stu-id="09498-120">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="09498-121">Ce fournisseur pourra mettre à jour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="09498-121">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="09498-122">D'autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="09498-122">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
4. <span data-ttu-id="09498-123">Cliquez sur le bouton « Créer la configuration » pour terminer la tâche de création de la configuration.</span><span class="sxs-lookup"><span data-stu-id="09498-123">Click ‘Create configuration’ button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="09498-124">Créer un modèle de données</span><span class="sxs-lookup"><span data-stu-id="09498-124">Create a data model</span></span>
    * <span data-ttu-id="09498-125">Vous créez un modèle de données pour la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="09498-125">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="09498-126">Cette version de configuration aura un statut de brouillon.</span><span class="sxs-lookup"><span data-stu-id="09498-126">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="09498-127">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="09498-127">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="09498-128">Définir la structure d'une partie qui participe à un processus de paiement</span><span class="sxs-lookup"><span data-stu-id="09498-128">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="09498-129">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-129">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="09498-130">Dans le champ Nom, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="09498-130">In the Name field, type 'Party'.</span></span>
    * <span data-ttu-id="09498-131">Partie</span><span class="sxs-lookup"><span data-stu-id="09498-131">Party</span></span>  
3. <span data-ttu-id="09498-132">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-132">Click Add.</span></span>
4. <span data-ttu-id="09498-133">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-133">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="09498-134">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-134">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="09498-135">Nom</span><span class="sxs-lookup"><span data-stu-id="09498-135">Name</span></span>  
6. <span data-ttu-id="09498-136">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-136">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="09498-137">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-137">Click Add.</span></span>
8. <span data-ttu-id="09498-138">Dans le champ Rechercher, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="09498-138">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="09498-139">Partie</span><span class="sxs-lookup"><span data-stu-id="09498-139">Party</span></span>  
9. <span data-ttu-id="09498-140">Cliquez sur Précédent</span><span class="sxs-lookup"><span data-stu-id="09498-140">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="09498-141">Définir la structure de la banque pour ce modèle</span><span class="sxs-lookup"><span data-stu-id="09498-141">Define the bank structure for this model</span></span>
1. <span data-ttu-id="09498-142">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-142">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="09498-143">Tapez « Agent » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-143">In the Name field, type 'Agent'.</span></span>
    * <span data-ttu-id="09498-144">Agent ;</span><span class="sxs-lookup"><span data-stu-id="09498-144">Agent</span></span>  
3. <span data-ttu-id="09498-145">Sélectionnez « Enregistrement » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-145">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="09498-146">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-146">Click Add.</span></span>
5. <span data-ttu-id="09498-147">Dans le champ Description, entrez « Institution financière (une banque, par exemple) chargée d'un compte de la partie (débiteur/créditeur) ».</span><span class="sxs-lookup"><span data-stu-id="09498-147">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>
    * <span data-ttu-id="09498-148">Institution financière (une banque, par exemple) chargée d'un compte de la partie (débiteur/créditeur).</span><span class="sxs-lookup"><span data-stu-id="09498-148">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  
6. <span data-ttu-id="09498-149">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-149">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="09498-150">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-150">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="09498-151">Nom</span><span class="sxs-lookup"><span data-stu-id="09498-151">Name</span></span>  
8. <span data-ttu-id="09498-152">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-152">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="09498-153">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-153">Click Add.</span></span>
10. <span data-ttu-id="09498-154">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-154">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="09498-155">Tapez SWIFT dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-155">In the Name field, type 'SWIFT'.</span></span>
    * <span data-ttu-id="09498-156">SWIFT</span><span class="sxs-lookup"><span data-stu-id="09498-156">SWIFT</span></span>  
12. <span data-ttu-id="09498-157">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-157">Click Add.</span></span>
13. <span data-ttu-id="09498-158">Dans le champ Description, entrez « Code d'identification de la banque ».</span><span class="sxs-lookup"><span data-stu-id="09498-158">In the Description field, enter 'Bank identification code'.</span></span>
    * <span data-ttu-id="09498-159">Code d'identification de la banque</span><span class="sxs-lookup"><span data-stu-id="09498-159">Bank identification code</span></span>  
14. <span data-ttu-id="09498-160">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-160">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="09498-161">Tapez « RoutingNumber » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-161">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="09498-162">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="09498-162">RoutingNumber</span></span>  
16. <span data-ttu-id="09498-163">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-163">Click Add.</span></span>
17. <span data-ttu-id="09498-164">Dans le champ Description, entrez « Numéro d'acheminement ».</span><span class="sxs-lookup"><span data-stu-id="09498-164">In the Description field, enter 'Routing number'.</span></span>
    * <span data-ttu-id="09498-165">Numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="09498-165">Routing number</span></span>  
18. <span data-ttu-id="09498-166">Cliquez sur Précédent</span><span class="sxs-lookup"><span data-stu-id="09498-166">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="09498-167">Définir la structure de compte de la banque pour ce modèle</span><span class="sxs-lookup"><span data-stu-id="09498-167">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="09498-168">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-168">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="09498-169">Tapez « Compte » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-169">In the Name field, type 'Account'.</span></span>
    * <span data-ttu-id="09498-170">Compte</span><span class="sxs-lookup"><span data-stu-id="09498-170">Account</span></span>  
3. <span data-ttu-id="09498-171">Sélectionnez « Enregistrement » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-171">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="09498-172">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-172">Click Add.</span></span>
5. <span data-ttu-id="09498-173">Dans le champ Description, entrez « Identification d'un compte d'une partie dans une institution financière (une banque, par exemple) ».</span><span class="sxs-lookup"><span data-stu-id="09498-173">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>
    * <span data-ttu-id="09498-174">Identification d'un compte d'une partie dans une institution financière (une banque, par exemple).</span><span class="sxs-lookup"><span data-stu-id="09498-174">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  
6. <span data-ttu-id="09498-175">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-175">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="09498-176">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-176">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="09498-177">Devise</span><span class="sxs-lookup"><span data-stu-id="09498-177">Currency</span></span>  
8. <span data-ttu-id="09498-178">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-178">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="09498-179">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-179">Click Add.</span></span>
10. <span data-ttu-id="09498-180">Dans le champ Description, entrez « Code devise ».</span><span class="sxs-lookup"><span data-stu-id="09498-180">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="09498-181">Code devise</span><span class="sxs-lookup"><span data-stu-id="09498-181">Currency code</span></span>  
11. <span data-ttu-id="09498-182">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-182">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="09498-183">Tapez « Numéro » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-183">In the Name field, type 'Number'.</span></span>
    * <span data-ttu-id="09498-184">Numéro</span><span class="sxs-lookup"><span data-stu-id="09498-184">Number</span></span>  
13. <span data-ttu-id="09498-185">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-185">Click Add.</span></span>
14. <span data-ttu-id="09498-186">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-186">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="09498-187">Tapez « IBAN » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-187">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="09498-188">IBAN</span><span class="sxs-lookup"><span data-stu-id="09498-188">IBAN</span></span>  
16. <span data-ttu-id="09498-189">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-189">Click Add.</span></span>
17. <span data-ttu-id="09498-190">Dans le champ Description, entrez « Numéro de compte bancaire international ».</span><span class="sxs-lookup"><span data-stu-id="09498-190">In the Description field, enter 'International bank account number'.</span></span>
    * <span data-ttu-id="09498-191">Numéro de compte bancaire international</span><span class="sxs-lookup"><span data-stu-id="09498-191">International bank account number</span></span>  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="09498-192">Définir la structure du message de paiement pour le type de virement.</span><span class="sxs-lookup"><span data-stu-id="09498-192">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="09498-193">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-193">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="09498-194">Dans le nœud Nouveau sous forme de champ, entrez « Racine du modèle ».</span><span class="sxs-lookup"><span data-stu-id="09498-194">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="09498-195">Tapez « CustomerCreditTransferInitiation » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-195">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="09498-196">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="09498-196">CustomerCreditTransferInitiation</span></span>  
4. <span data-ttu-id="09498-197">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-197">Click Add.</span></span>
5. <span data-ttu-id="09498-198">Dans le champ Rechercher, tapez « CustomerCreditTransferInitiation ».</span><span class="sxs-lookup"><span data-stu-id="09498-198">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="09498-199">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="09498-199">CustomerCreditTransferInitiation</span></span>  
6. <span data-ttu-id="09498-200">Cliquez sur Précédent</span><span class="sxs-lookup"><span data-stu-id="09498-200">Click Find previous.</span></span>
7. <span data-ttu-id="09498-201">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-201">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="09498-202">Tapez « MessageIdentification » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-202">In the Name field, type 'MessageIdentification'.</span></span>
    * <span data-ttu-id="09498-203">MessageIdentification</span><span class="sxs-lookup"><span data-stu-id="09498-203">MessageIdentification</span></span>  
9. <span data-ttu-id="09498-204">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-204">Click Add.</span></span>
10. <span data-ttu-id="09498-205">Dans le champ Description, entrez « Référence point à point affectée par le donneur d'ordre (et envoyée à la partie suivante) afin d'identifier le message ».</span><span class="sxs-lookup"><span data-stu-id="09498-205">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>
    * <span data-ttu-id="09498-206">Référence point à point affectée par le donneur d'ordre et envoyée à la partie suivante dans la chaîne afin d'identifier le message.</span><span class="sxs-lookup"><span data-stu-id="09498-206">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  
11. <span data-ttu-id="09498-207">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-207">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="09498-208">Tapez « ProcessingDateTime » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-208">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="09498-209">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="09498-209">ProcessingDateTime</span></span>  
13. <span data-ttu-id="09498-210">Sélectionnez « DateTime » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-210">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="09498-211">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-211">Click Add.</span></span>
15. <span data-ttu-id="09498-212">Dans le champ Description, entrez « Date et heure de création du message de paiement ».</span><span class="sxs-lookup"><span data-stu-id="09498-212">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span>
    * <span data-ttu-id="09498-213">Date et heure de création du message de paiement</span><span class="sxs-lookup"><span data-stu-id="09498-213">Date and time at which the payment message was created.</span></span>  
16. <span data-ttu-id="09498-214">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-214">Click New to open the drop dialog.</span></span>
    * <span data-ttu-id="09498-215">Définir la structure de transaction de paiement pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="09498-215">Define the payment transaction structure for this model.</span></span>  
17. <span data-ttu-id="09498-216">Tapez « Paiements » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-216">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="09498-217">Paiements</span><span class="sxs-lookup"><span data-stu-id="09498-217">Payments</span></span>  
18. <span data-ttu-id="09498-218">Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-218">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="09498-219">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-219">Click Add.</span></span>
20. <span data-ttu-id="09498-220">Dans le champ Description, entrez « Lignes de paiement du message actuel ».</span><span class="sxs-lookup"><span data-stu-id="09498-220">In the Description field, enter 'Payment lines of the current message'.</span></span>
    * <span data-ttu-id="09498-221">Lignes de paiement du message actuel</span><span class="sxs-lookup"><span data-stu-id="09498-221">Payment lines of the current message</span></span>  
21. <span data-ttu-id="09498-222">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-222">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="09498-223">Tapez « Créancier » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-223">In the Name field, type 'Creditor'.</span></span>
    * <span data-ttu-id="09498-224">Créancier</span><span class="sxs-lookup"><span data-stu-id="09498-224">Creditor</span></span>  
23. <span data-ttu-id="09498-225">Sélectionnez « Enregistrement » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-225">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="09498-226">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-226">Click Add.</span></span>
25. <span data-ttu-id="09498-227">Dans le champ Description, entrez « Partie à laquelle un montant est dû ».</span><span class="sxs-lookup"><span data-stu-id="09498-227">In the Description field, enter 'Party to which an amount of money is due.'.</span></span>
    * <span data-ttu-id="09498-228">Partie à laquelle un montant est dû.</span><span class="sxs-lookup"><span data-stu-id="09498-228">Party to which an amount of money is due.</span></span>  
26. <span data-ttu-id="09498-229">Cliquez sur Basculer la référence d'élément.</span><span class="sxs-lookup"><span data-stu-id="09498-229">Click Switch item reference.</span></span>
27. <span data-ttu-id="09498-230">Dans le champ Rechercher, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="09498-230">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="09498-231">Partie</span><span class="sxs-lookup"><span data-stu-id="09498-231">Party</span></span>  
28. <span data-ttu-id="09498-232">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="09498-232">Click Find next.</span></span>
29. <span data-ttu-id="09498-233">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="09498-233">Click OK.</span></span>
30. <span data-ttu-id="09498-234">Dans le champ Rechercher, tapez « Paiements ».</span><span class="sxs-lookup"><span data-stu-id="09498-234">In the Find field, type 'Payments'.</span></span>
    * <span data-ttu-id="09498-235">Paiements</span><span class="sxs-lookup"><span data-stu-id="09498-235">Payments</span></span>  
31. <span data-ttu-id="09498-236">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="09498-236">Click Find next.</span></span>
32. <span data-ttu-id="09498-237">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-237">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="09498-238">Tapez « Débiteur » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-238">In the Name field, type 'Debtor'.</span></span>
    * <span data-ttu-id="09498-239">Débiteur</span><span class="sxs-lookup"><span data-stu-id="09498-239">Debtor</span></span>  
34. <span data-ttu-id="09498-240">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-240">Click Add.</span></span>
35. <span data-ttu-id="09498-241">Dans le champ Description, entrez « Partie qui doit une somme d'argent au créancier (final) ».</span><span class="sxs-lookup"><span data-stu-id="09498-241">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
    * <span data-ttu-id="09498-242">Partie qui doit une somme d'argent au créancier (final).</span><span class="sxs-lookup"><span data-stu-id="09498-242">Party that owes an amount of money to the (ultimate) creditor.</span></span>  
36. <span data-ttu-id="09498-243">Cliquez sur Basculer la référence d'élément.</span><span class="sxs-lookup"><span data-stu-id="09498-243">Click Switch item reference.</span></span>
37. <span data-ttu-id="09498-244">Dans le champ Rechercher, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="09498-244">In the Find field, type 'Party'.</span></span>
    * <span data-ttu-id="09498-245">Partie</span><span class="sxs-lookup"><span data-stu-id="09498-245">Party</span></span>  
38. <span data-ttu-id="09498-246">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="09498-246">Click Find next.</span></span>
39. <span data-ttu-id="09498-247">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="09498-247">Click OK.</span></span>
40. <span data-ttu-id="09498-248">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="09498-248">Click Find next.</span></span>
41. <span data-ttu-id="09498-249">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-249">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="09498-250">Tapez « Description » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-250">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="09498-251">Description</span><span class="sxs-lookup"><span data-stu-id="09498-251">Description</span></span>  
43. <span data-ttu-id="09498-252">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-252">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="09498-253">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-253">Click Add.</span></span>
45. <span data-ttu-id="09498-254">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-254">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="09498-255">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-255">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="09498-256">Devise</span><span class="sxs-lookup"><span data-stu-id="09498-256">Currency</span></span>  
47. <span data-ttu-id="09498-257">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-257">Click Add.</span></span>
48. <span data-ttu-id="09498-258">Dans le champ Description, entrez « Code devise ».</span><span class="sxs-lookup"><span data-stu-id="09498-258">In the Description field, enter 'Currency code'.</span></span>
    * <span data-ttu-id="09498-259">Code devise</span><span class="sxs-lookup"><span data-stu-id="09498-259">Currency code</span></span>  
49. <span data-ttu-id="09498-260">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-260">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="09498-261">Tapez « TransactionDate » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-261">In the Name field, type 'TransactionDate'.</span></span>
    * <span data-ttu-id="09498-262">TransactionDate</span><span class="sxs-lookup"><span data-stu-id="09498-262">TransactionDate</span></span>  
51. <span data-ttu-id="09498-263">Sélectionnez « Date » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-263">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="09498-264">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-264">Click Add.</span></span>
53. <span data-ttu-id="09498-265">Dans le champ Description, entrez « Date de transaction ».</span><span class="sxs-lookup"><span data-stu-id="09498-265">In the Description field, enter 'Transaction date'.</span></span>
    * <span data-ttu-id="09498-266">Date de transaction</span><span class="sxs-lookup"><span data-stu-id="09498-266">Transaction date</span></span>  
54. <span data-ttu-id="09498-267">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-267">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="09498-268">Tapez « InstructedAmount » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-268">In the Name field, type 'InstructedAmount'.</span></span>
    * <span data-ttu-id="09498-269">InstructedAmount</span><span class="sxs-lookup"><span data-stu-id="09498-269">InstructedAmount</span></span>  
56. <span data-ttu-id="09498-270">Sélectionnez « Réel » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-270">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="09498-271">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-271">Click Add.</span></span>
58. <span data-ttu-id="09498-272">Dans le champ Description, entrez « Montant à transférer entre le débiteur et le créancier, avant déduction des frais.</span><span class="sxs-lookup"><span data-stu-id="09498-272">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="09498-273">Le montant doit être exprimé dans la devise choisie par la partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="09498-273">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>
    * <span data-ttu-id="09498-274">Montant à transférer entre le débiteur et le créancier, avant déduction des frais.</span><span class="sxs-lookup"><span data-stu-id="09498-274">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="09498-275">Le montant doit être exprimé dans la devise choisie par la partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="09498-275">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  
59. <span data-ttu-id="09498-276">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="09498-276">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="09498-277">Tapez « End2EndID » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-277">In the Name field, type 'End2EndID'.</span></span>
    * <span data-ttu-id="09498-278">End2EndID</span><span class="sxs-lookup"><span data-stu-id="09498-278">End2EndID</span></span>  
61. <span data-ttu-id="09498-279">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="09498-279">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="09498-280">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="09498-280">Click Add.</span></span>
63. <span data-ttu-id="09498-281">Dans le champ Description, entrez « Identification unique affectée par la partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="09498-281">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="09498-282">Cette identification est transmise telle quelle tout au long de la chaîne de bout en bout. »</span><span class="sxs-lookup"><span data-stu-id="09498-282">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span>
    * <span data-ttu-id="09498-283">Identification unique affectée par la partie qui prend l'initiative.</span><span class="sxs-lookup"><span data-stu-id="09498-283">The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="09498-284">Cette identification est transmise telle quelle tout au long de la chaîne de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="09498-284">This identification is passed on, unchanged, throughout the entire end-to-end chain.</span></span>  
64. <span data-ttu-id="09498-285">Tapez « PaymentModel » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="09498-285">In the Name field, type 'PaymentModel'.</span></span>
    * <span data-ttu-id="09498-286">Le nom PaymentModel s'aligne avec les interfaces prédéfinies des écrans de paiement.</span><span class="sxs-lookup"><span data-stu-id="09498-286">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  
65. <span data-ttu-id="09498-287">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="09498-287">Click Save.</span></span>
66. <span data-ttu-id="09498-288">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="09498-288">Close the page.</span></span>


