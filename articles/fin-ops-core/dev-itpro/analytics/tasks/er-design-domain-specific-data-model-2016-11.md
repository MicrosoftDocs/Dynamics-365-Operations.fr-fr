---
title: ER Concevoir un modèle de données spécifiques au domaine
description: Cette rubrique décrit comment créer une nouvelle configuration de gestion des états électroniques contenant un modèle de données pour les documents de paiement électronique.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 284fad8b6646c35217789cc9936cbe9fe75a03d0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567807"
---
# <a name="er-design-domain-specific-data-model"></a><span data-ttu-id="d5e19-103">ER Concevoir un modèle de données spécifiques au domaine</span><span class="sxs-lookup"><span data-stu-id="d5e19-103">ER Design domain specific data model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5e19-104">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d’états électroniques peut créer une configuration de format pour la génération d’états électronique (ER) qui contient un modèle de données pour les documents de paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="d5e19-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="d5e19-105">Ce modèle de données sera utilisé ultérieurement comme source de données quand vous créerez le format des documents de paiement.</span><span class="sxs-lookup"><span data-stu-id="d5e19-105">This data model will later be used as a data source when you create the format of the payment documents.</span></span>

<span data-ttu-id="d5e19-106">Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n’importe quelle société car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="d5e19-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="d5e19-107">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

1. <span data-ttu-id="d5e19-108">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="d5e19-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="d5e19-109">Sélectionnez le fournisseur de configuration pour la société fictive, « Litware, Inc ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-109">Select the configuration provider for sample company, 'Litware, Inc.'</span></span> <span data-ttu-id="d5e19-110">Si vous ne voyez pas ce fournisseur de configuration, vous devez d’abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-110">If you don't see this configuration provider, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>  
    
2. <span data-ttu-id="d5e19-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="d5e19-111">Click Reporting configurations.</span></span>

    <span data-ttu-id="d5e19-112">Vous allez créer une configuration qui contient un modèle de données pour les documents de paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="d5e19-112">You will create a configuration that contains a data model for electronic payment documents.</span></span> <span data-ttu-id="d5e19-113">Ce modèle de données sera utilisé ultérieurement comme source de données quand vous allez créer le format pour les documents de paiement.</span><span class="sxs-lookup"><span data-stu-id="d5e19-113">This data model will be used later as a data source when you create the format for the payment documents.</span></span>  

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="d5e19-114">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="d5e19-114">Create a new data model configuration</span></span>
1. <span data-ttu-id="d5e19-115">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-115">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="d5e19-116">Tapez « Paiements (modèle simplifié) » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-116">In the Name field, type 'Payments (simplified model)'.</span></span>
3. <span data-ttu-id="d5e19-117">Tapez « Configuration du modèle de paiement » dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="d5e19-117">In the Description field, type 'Payment model configuration'.</span></span>

    <span data-ttu-id="d5e19-118">Le fournisseur de configuration actif est automatiquement entré ici.</span><span class="sxs-lookup"><span data-stu-id="d5e19-118">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="d5e19-119">Ce fournisseur pourra mettre à jour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="d5e19-119">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="d5e19-120">D’autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="d5e19-120">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

4. <span data-ttu-id="d5e19-121">Cliquez sur le bouton « Créer la configuration » pour terminer la tâche de création de la configuration.</span><span class="sxs-lookup"><span data-stu-id="d5e19-121">Click 'Create configuration' button to complete the configuration creation task</span></span>

## <a name="create-a-data-model"></a><span data-ttu-id="d5e19-122">Créer un modèle de données</span><span class="sxs-lookup"><span data-stu-id="d5e19-122">Create a data model</span></span>
<span data-ttu-id="d5e19-123">Vous créez un modèle de données pour la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5e19-123">You're creating a new data model for the selected configuration.</span></span> <span data-ttu-id="d5e19-124">Cette version de configuration aura un statut de brouillon.</span><span class="sxs-lookup"><span data-stu-id="d5e19-124">This configuration version will have a status of Draft.</span></span>  
1. <span data-ttu-id="d5e19-125">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="d5e19-125">Click Designer.</span></span>

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a><span data-ttu-id="d5e19-126">Définir la structure d’une partie qui participe à un processus de paiement</span><span class="sxs-lookup"><span data-stu-id="d5e19-126">Define the structure of a party participating in a payment process</span></span>
1. <span data-ttu-id="d5e19-127">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-127">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="d5e19-128">Dans le champ Nom, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-128">In the Name field, type 'Party'.</span></span>
3. <span data-ttu-id="d5e19-129">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-129">Click Add.</span></span>
4. <span data-ttu-id="d5e19-130">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-130">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="d5e19-131">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-131">In the Name field, type 'Name'.</span></span>
6. <span data-ttu-id="d5e19-132">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-132">In the Item type field, select 'String'.</span></span>
7. <span data-ttu-id="d5e19-133">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-133">Click Add.</span></span>
8. <span data-ttu-id="d5e19-134">Dans le champ Rechercher, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-134">In the Find field, type 'Party'.</span></span>
9. <span data-ttu-id="d5e19-135">Cliquez sur Précédent</span><span class="sxs-lookup"><span data-stu-id="d5e19-135">Click Find previous.</span></span>

## <a name="define-the-bank-structure-for-this-model"></a><span data-ttu-id="d5e19-136">Définir la structure de la banque pour ce modèle</span><span class="sxs-lookup"><span data-stu-id="d5e19-136">Define the bank structure for this model</span></span>
1. <span data-ttu-id="d5e19-137">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-137">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="d5e19-138">Tapez « Agent » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-138">In the Name field, type 'Agent'.</span></span>
3. <span data-ttu-id="d5e19-139">Sélectionnez « Enregistrement » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-139">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="d5e19-140">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-140">Click Add.</span></span>
5. <span data-ttu-id="d5e19-141">Dans le champ Description, entrez « Institution financière (une banque, par exemple) chargée d’un compte de la partie (débiteur/créditeur) ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-141">In the Description field, enter 'Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).'.</span></span>

    <span data-ttu-id="d5e19-142">Institution financière (une banque, par exemple) chargée d’un compte de la partie (débiteur/créditeur).</span><span class="sxs-lookup"><span data-stu-id="d5e19-142">Financial institution (for instance, a bank) servicing an account for the party (debtor/creditor).</span></span>  

6. <span data-ttu-id="d5e19-143">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-143">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="d5e19-144">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-144">In the Name field, type 'Name'.</span></span> 
8. <span data-ttu-id="d5e19-145">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-145">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="d5e19-146">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-146">Click Add.</span></span>
10. <span data-ttu-id="d5e19-147">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-147">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="d5e19-148">Tapez SWIFT dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-148">In the Name field, type 'SWIFT'.</span></span>
12. <span data-ttu-id="d5e19-149">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-149">Click Add.</span></span>
13. <span data-ttu-id="d5e19-150">Dans le champ Description, entrez « Code d’identification de la banque ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-150">In the Description field, enter 'Bank identification code'.</span></span> 
14. <span data-ttu-id="d5e19-151">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-151">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="d5e19-152">Tapez « RoutingNumber » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-152">In the Name field, type 'RoutingNumber'.</span></span>
16. <span data-ttu-id="d5e19-153">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-153">Click Add.</span></span>
17. <span data-ttu-id="d5e19-154">Dans le champ Description, entrez « Numéro d’acheminement ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-154">In the Description field, enter 'Routing number'.</span></span>
18. <span data-ttu-id="d5e19-155">Cliquez sur Précédent</span><span class="sxs-lookup"><span data-stu-id="d5e19-155">Click Find previous.</span></span>

## <a name="define-the-bank-account-structure-for-this-model"></a><span data-ttu-id="d5e19-156">Définir la structure de compte de la banque pour ce modèle</span><span class="sxs-lookup"><span data-stu-id="d5e19-156">Define the bank account structure for this model</span></span>
1. <span data-ttu-id="d5e19-157">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-157">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="d5e19-158">Tapez « Compte » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-158">In the Name field, type 'Account'.</span></span> 
3. <span data-ttu-id="d5e19-159">Sélectionnez « Enregistrement » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-159">In the Item type field, select 'Record'.</span></span>
4. <span data-ttu-id="d5e19-160">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-160">Click Add.</span></span>
5. <span data-ttu-id="d5e19-161">Dans le champ Description, entrez « Identification d’un compte d’une partie dans une institution financière (une banque, par exemple) ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-161">In the Description field, enter 'Identification of an account of a party in a financial institution (for instance, a bank).'.</span></span>

    <span data-ttu-id="d5e19-162">Identification d’un compte d’une partie dans une institution financière (une banque, par exemple).</span><span class="sxs-lookup"><span data-stu-id="d5e19-162">Identification of an account of a party in a financial institution (for instance, a bank).</span></span>  

6. <span data-ttu-id="d5e19-163">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-163">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="d5e19-164">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-164">In the Name field, type 'Currency'.</span></span> 
8. <span data-ttu-id="d5e19-165">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-165">In the Item type field, select 'String'.</span></span>
9. <span data-ttu-id="d5e19-166">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-166">Click Add.</span></span>
10. <span data-ttu-id="d5e19-167">Dans le champ Description, entrez « Code devise ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-167">In the Description field, enter 'Currency code'.</span></span>
11. <span data-ttu-id="d5e19-168">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-168">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="d5e19-169">Tapez « Numéro » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-169">In the Name field, type 'Number'.</span></span> 
13. <span data-ttu-id="d5e19-170">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-170">Click Add.</span></span>
14. <span data-ttu-id="d5e19-171">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-171">Click New to open the drop dialog.</span></span>
15. <span data-ttu-id="d5e19-172">Tapez « IBAN » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-172">In the Name field, type 'IBAN'.</span></span> 
16. <span data-ttu-id="d5e19-173">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-173">Click Add.</span></span>
17. <span data-ttu-id="d5e19-174">Dans le champ Description, entrez « Numéro de compte bancaire international ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-174">In the Description field, enter 'International bank account number'.</span></span>

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a><span data-ttu-id="d5e19-175">Définir la structure du message de paiement pour le type de virement.</span><span class="sxs-lookup"><span data-stu-id="d5e19-175">Define the payment message structure for credit transfer payment type</span></span>
1. <span data-ttu-id="d5e19-176">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-176">Click New to open the drop dialog.</span></span>
2. <span data-ttu-id="d5e19-177">Dans le nœud Nouveau sous forme de champ, entrez « Racine du modèle ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-177">In the New node as a field, enter 'Model root'.</span></span>
3. <span data-ttu-id="d5e19-178">Tapez « CustomerCreditTransferInitiation » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-178">In the Name field, type 'CustomerCreditTransferInitiation'.</span></span>
4. <span data-ttu-id="d5e19-179">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-179">Click Add.</span></span>
5. <span data-ttu-id="d5e19-180">Dans le champ Rechercher, tapez « CustomerCreditTransferInitiation ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-180">In the Find field, type 'CustomerCreditTransferInitiation'.</span></span> 
6. <span data-ttu-id="d5e19-181">Cliquez sur Précédent</span><span class="sxs-lookup"><span data-stu-id="d5e19-181">Click Find previous.</span></span>
7. <span data-ttu-id="d5e19-182">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-182">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="d5e19-183">Tapez « MessageIdentification » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-183">In the Name field, type 'MessageIdentification'.</span></span> 
9. <span data-ttu-id="d5e19-184">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-184">Click Add.</span></span>
10. <span data-ttu-id="d5e19-185">Dans le champ Description, entrez « Référence point à point affectée par le donneur d’ordre (et envoyée à la partie suivante) afin d’identifier le message ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-185">In the Description field, enter 'The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.'.</span></span>

    <span data-ttu-id="d5e19-186">Référence point à point affectée par le donneur d’ordre et envoyée à la partie suivante dans la chaîne afin d’identifier le message.</span><span class="sxs-lookup"><span data-stu-id="d5e19-186">The point-to-point reference assigned by the instructing party (and sent to the next party) to identify a message.</span></span>  

11. <span data-ttu-id="d5e19-187">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-187">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="d5e19-188">Tapez « ProcessingDateTime » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-188">In the Name field, type 'ProcessingDateTime'.</span></span>
13. <span data-ttu-id="d5e19-189">Sélectionnez « DateTime » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-189">In the Item type field, select 'DateTime'.</span></span>
14. <span data-ttu-id="d5e19-190">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-190">Click Add.</span></span>
15. <span data-ttu-id="d5e19-191">Dans le champ Description, entrez « Date et heure de création du message de paiement ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-191">In the Description field, enter 'Date and time at which the payment message was created.'.</span></span> 
16. <span data-ttu-id="d5e19-192">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-192">Click New to open the drop dialog.</span></span>

    <span data-ttu-id="d5e19-193">Définir la structure de transaction de paiement pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="d5e19-193">Define the payment transaction structure for this model.</span></span>  

17. <span data-ttu-id="d5e19-194">Tapez « Paiements » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-194">In the Name field, type 'Payments'.</span></span>
18. <span data-ttu-id="d5e19-195">Sélectionnez « Liste d’enregistrements » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-195">In the Item type field, select 'Record list'.</span></span>
19. <span data-ttu-id="d5e19-196">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-196">Click Add.</span></span>
20. <span data-ttu-id="d5e19-197">Dans le champ Description, entrez « Lignes de paiement du message actuel ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-197">In the Description field, enter 'Payment lines of the current message'.</span></span>
21. <span data-ttu-id="d5e19-198">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-198">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="d5e19-199">Tapez « Créancier » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-199">In the Name field, type 'Creditor'.</span></span> 
23. <span data-ttu-id="d5e19-200">Sélectionnez « Enregistrement » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-200">In the Item type field, select 'Record'.</span></span>
24. <span data-ttu-id="d5e19-201">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-201">Click Add.</span></span>
25. <span data-ttu-id="d5e19-202">Dans le champ Description, entrez « Partie à laquelle un montant est dû ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-202">In the Description field, enter 'Party to which an amount of money is due.'.</span></span> 
26. <span data-ttu-id="d5e19-203">Cliquez sur Basculer la référence d’élément.</span><span class="sxs-lookup"><span data-stu-id="d5e19-203">Click Switch item reference.</span></span>
27. <span data-ttu-id="d5e19-204">Dans le champ Rechercher, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-204">In the Find field, type 'Party'.</span></span>
28. <span data-ttu-id="d5e19-205">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="d5e19-205">Click Find next.</span></span>
29. <span data-ttu-id="d5e19-206">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d5e19-206">Click OK.</span></span>
30. <span data-ttu-id="d5e19-207">Dans le champ Rechercher, tapez « Paiements ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-207">In the Find field, type 'Payments'.</span></span>
31. <span data-ttu-id="d5e19-208">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="d5e19-208">Click Find next.</span></span>
32. <span data-ttu-id="d5e19-209">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-209">Click New to open the drop dialog.</span></span>
33. <span data-ttu-id="d5e19-210">Tapez « Débiteur » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-210">In the Name field, type 'Debtor'.</span></span> 
34. <span data-ttu-id="d5e19-211">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-211">Click Add.</span></span>
35. <span data-ttu-id="d5e19-212">Dans le champ Description, entrez « Partie qui doit une somme d’argent au créancier (final) ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-212">In the Description field, enter 'Party that owes an amount of money to the (ultimate) creditor.'.</span></span>
36. <span data-ttu-id="d5e19-213">Cliquez sur Basculer la référence d’élément.</span><span class="sxs-lookup"><span data-stu-id="d5e19-213">Click Switch item reference.</span></span>
37. <span data-ttu-id="d5e19-214">Dans le champ Rechercher, tapez « Partie ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-214">In the Find field, type 'Party'.</span></span>
38. <span data-ttu-id="d5e19-215">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="d5e19-215">Click Find next.</span></span>
39. <span data-ttu-id="d5e19-216">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d5e19-216">Click OK.</span></span>
40. <span data-ttu-id="d5e19-217">Cliquez sur Suivant</span><span class="sxs-lookup"><span data-stu-id="d5e19-217">Click Find next.</span></span>
41. <span data-ttu-id="d5e19-218">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-218">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="d5e19-219">Tapez « Description » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-219">In the Name field, type 'Description'.</span></span>
43. <span data-ttu-id="d5e19-220">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-220">In the Item type field, select 'String'.</span></span>
44. <span data-ttu-id="d5e19-221">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-221">Click Add.</span></span>
45. <span data-ttu-id="d5e19-222">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-222">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="d5e19-223">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-223">In the Name field, type 'Currency'.</span></span>
47. <span data-ttu-id="d5e19-224">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-224">Click Add.</span></span>
48. <span data-ttu-id="d5e19-225">Dans le champ Description, entrez « Code devise ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-225">In the Description field, enter 'Currency code'.</span></span>
49. <span data-ttu-id="d5e19-226">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-226">Click New to open the drop dialog.</span></span>
50. <span data-ttu-id="d5e19-227">Tapez « TransactionDate » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-227">In the Name field, type 'TransactionDate'.</span></span> 
51. <span data-ttu-id="d5e19-228">Sélectionnez « Date » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-228">In the Item type field, select 'Date'.</span></span>
52. <span data-ttu-id="d5e19-229">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-229">Click Add.</span></span>
53. <span data-ttu-id="d5e19-230">Dans le champ Description, entrez « Date de transaction ».</span><span class="sxs-lookup"><span data-stu-id="d5e19-230">In the Description field, enter 'Transaction date'.</span></span> 
54. <span data-ttu-id="d5e19-231">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-231">Click New to open the drop dialog.</span></span>
55. <span data-ttu-id="d5e19-232">Tapez « InstructedAmount » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-232">In the Name field, type 'InstructedAmount'.</span></span>  
56. <span data-ttu-id="d5e19-233">Sélectionnez « Réel » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-233">In the Item type field, select 'Real'.</span></span>
57. <span data-ttu-id="d5e19-234">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-234">Click Add.</span></span>
58. <span data-ttu-id="d5e19-235">Dans le champ Description, entrez « Montant à transférer entre le débiteur et le créancier, avant déduction des frais.</span><span class="sxs-lookup"><span data-stu-id="d5e19-235">In the Description field, enter 'The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="d5e19-236">Le montant doit être exprimé dans la devise choisie par la partie qui prend l’initiative.</span><span class="sxs-lookup"><span data-stu-id="d5e19-236">The amount should be expressed in the currency as ordered by the initiating party.'.</span></span>

    <span data-ttu-id="d5e19-237">Montant à transférer entre le débiteur et le créancier, avant déduction des frais.</span><span class="sxs-lookup"><span data-stu-id="d5e19-237">The amount of money to be moved between the debtor and creditor, before deduction of charges.</span></span> <span data-ttu-id="d5e19-238">Le montant doit être exprimé dans la devise choisie par la partie qui prend l’initiative.</span><span class="sxs-lookup"><span data-stu-id="d5e19-238">The amount should be expressed in the currency as ordered by the initiating party.</span></span>  

59. <span data-ttu-id="d5e19-239">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d5e19-239">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="d5e19-240">Tapez « End2EndID » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-240">In the Name field, type 'End2EndID'.</span></span> 
61. <span data-ttu-id="d5e19-241">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="d5e19-241">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="d5e19-242">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="d5e19-242">Click Add.</span></span>
63. <span data-ttu-id="d5e19-243">Dans le champ Description, entrez « Identification unique affectée par la partie qui prend l’initiative.</span><span class="sxs-lookup"><span data-stu-id="d5e19-243">In the Description field, enter 'The unique identification assigned by the initiating party.</span></span> <span data-ttu-id="d5e19-244">Cette identification est transmise telle quelle tout au long de la chaîne de bout en bout. »</span><span class="sxs-lookup"><span data-stu-id="d5e19-244">This identification is passed on, unchanged, throughout the entire end-to-end chain.'.</span></span> 
64. <span data-ttu-id="d5e19-245">Tapez « PaymentModel » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="d5e19-245">In the Name field, type 'PaymentModel'.</span></span>

    <span data-ttu-id="d5e19-246">Le nom PaymentModel s’aligne avec les interfaces prédéfinies des écrans de paiement.</span><span class="sxs-lookup"><span data-stu-id="d5e19-246">The PaymentModel name aligns with predefined interfaces of payment forms.</span></span>  

65. <span data-ttu-id="d5e19-247">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d5e19-247">Click Save.</span></span>
66. <span data-ttu-id="d5e19-248">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d5e19-248">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]