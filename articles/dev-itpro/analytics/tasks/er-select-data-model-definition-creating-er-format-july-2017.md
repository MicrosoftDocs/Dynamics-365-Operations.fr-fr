--- 
title: "Sélectionner la définition du modèle de données lors de la création du format pour la gestion des états électroniques (ER)"
description: "Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, ER Créer un fournisseur de configuration et le marquer comme actif."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 70d928b0f0807731a5f96ef5497fb6060fbfebf5
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="select-data-model-definition-while-creating-format-for-electronic-reporting-er"></a><span data-ttu-id="5da6c-103">Sélectionner la définition du modèle de données lors de la création du format pour la gestion des états électroniques (ER)</span><span class="sxs-lookup"><span data-stu-id="5da6c-103">Select data model definition while creating format for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5da6c-104">Pour réaliser les étapes de cette procédure, vous devez commencer par effectuer la procédure, ER Créer un fournisseur de configuration et le marquer comme actif.</span><span class="sxs-lookup"><span data-stu-id="5da6c-104">To complete the steps in this procedure, you must first complete the procedure, ER Create a configuration provider and mark it as active.</span></span> 

<span data-ttu-id="5da6c-105">Cette procédure indique comment l'élément racine d'un modèle peut être sélectionné comme définition du modèle de données pour insérer une configuration du format ER conçue pour générer des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="5da6c-105">This procedure shows how a model’s root item can be selected as a data model definition for inserting an Electronic reporting (ER) format configuration that is designed to generate electronic documents.</span></span> <span data-ttu-id="5da6c-106">Dans cette procédure, vous ajouterez une nouvelle configuration du format ER pour la société fictive, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5da6c-106">In this procedure, you will add a new ER format configuration for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="5da6c-107">Cette procédure est destinée aux utilisateurs auxquels le rôle Administrateur système ou Développeur d'états électroniques a été affecté.</span><span class="sxs-lookup"><span data-stu-id="5da6c-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="5da6c-108">Les étapes peuvent être effectuées à l'aide de n'importe quel ensemble de données.</span><span class="sxs-lookup"><span data-stu-id="5da6c-108">The steps can be completed by using any dataset.</span></span>

1. <span data-ttu-id="5da6c-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="5da6c-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="5da6c-110">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="5da6c-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="5da6c-111">Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure, Créer un fournisseur de configuration et le marquer comme actif.</span><span class="sxs-lookup"><span data-stu-id="5da6c-111">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  
2. <span data-ttu-id="5da6c-112">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="5da6c-112">Click Reporting configurations.</span></span>

## <a name="add-a-new-er-data-model-configuration"></a><span data-ttu-id="5da6c-113">Ajouter une nouvelle configuration du modèle de données ER</span><span class="sxs-lookup"><span data-stu-id="5da6c-113">Add a new ER data model configuration</span></span>
1. <span data-ttu-id="5da6c-114">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5da6c-114">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="5da6c-115">Nous ajoutons une nouvelle configuration de modèle ER contenant un modèle de données conçu pour être utilisé comme source de données pour la génération d'états ER.</span><span class="sxs-lookup"><span data-stu-id="5da6c-115">We add a new ER model configuration containing a data model that is designed to be used as data source for generation ER reports.</span></span>  
2. <span data-ttu-id="5da6c-116">Dans le champ Nom, tapez « Modèle de paiement (fictif) ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-116">In the Name field, type 'Payment model (fictitious)'.</span></span>
    * <span data-ttu-id="5da6c-117">Modèle de paiement (fictif)</span><span class="sxs-lookup"><span data-stu-id="5da6c-117">Payment model (fictitious)</span></span>  
3. <span data-ttu-id="5da6c-118">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="5da6c-118">Click Create configuration.</span></span>
4. <span data-ttu-id="5da6c-119">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="5da6c-119">Click Designer.</span></span>
    * <span data-ttu-id="5da6c-120">Ouvrez le concepteur ER pour spécifier la structure du modèle de données de cette configuration.</span><span class="sxs-lookup"><span data-stu-id="5da6c-120">Open the ER designer to specify the structure of data model of this configuration.</span></span>  
    * <span data-ttu-id="5da6c-121">Supposons que nous concevions le modèle de données pour le domaine des paiements pour prendre en charge 2 modes de paiement : virement et débit direct.</span><span class="sxs-lookup"><span data-stu-id="5da6c-121">Assume that we design the data model for payments business domain to support 2 payment methods – credit transfer and direct debit ones.</span></span>  
5. <span data-ttu-id="5da6c-122">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5da6c-122">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="5da6c-123">Dans le champ Nom, tapez « Paiements – virement ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-123">In the Name field, type 'Payments – credit transfer'.</span></span>
    * <span data-ttu-id="5da6c-124">Paiements – virement</span><span class="sxs-lookup"><span data-stu-id="5da6c-124">Payments – credit transfer</span></span>  
7. <span data-ttu-id="5da6c-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="5da6c-125">Click Add.</span></span>
8. <span data-ttu-id="5da6c-126">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5da6c-126">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="5da6c-127">Dans le nœud Nouveau sous forme de champ, entrez « Racine du modèle ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-127">In the New node as a field, enter 'Model root'.</span></span>
10. <span data-ttu-id="5da6c-128">Dans le champ Nom, tapez « Paiements – débit direct ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-128">In the Name field, type 'Payments – direct debit'.</span></span>
    * <span data-ttu-id="5da6c-129">Paiements – débit direct</span><span class="sxs-lookup"><span data-stu-id="5da6c-129">Payments – direct debit</span></span>  
11. <span data-ttu-id="5da6c-130">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="5da6c-130">Click Add.</span></span>
12. <span data-ttu-id="5da6c-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="5da6c-131">Click Save.</span></span>
13. <span data-ttu-id="5da6c-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5da6c-132">Close the page.</span></span>
14. <span data-ttu-id="5da6c-133">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="5da6c-133">Click Change status.</span></span>
    * <span data-ttu-id="5da6c-134">Exécutez la version brouillon du modèle pour la rendre disponible dans les nouvelles mises en correspondance et les nouveaux formats de modèle.</span><span class="sxs-lookup"><span data-stu-id="5da6c-134">Complete the draft version of the model to make it available in new model mappings and formats.</span></span>  
15. <span data-ttu-id="5da6c-135">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="5da6c-135">Click Complete.</span></span>
16. <span data-ttu-id="5da6c-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5da6c-136">Click OK.</span></span>

## <a name="start-to-enter-a-new-er-format-configuration"></a><span data-ttu-id="5da6c-137">Commencer à entrer une nouvelle configuration du format ER</span><span class="sxs-lookup"><span data-stu-id="5da6c-137">Start to enter a new ER format configuration</span></span>
1. <span data-ttu-id="5da6c-138">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5da6c-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="5da6c-139">Dans le champ Nouveau, entrez « Format basé sur le modèle de données Modèle de paiement (fictif) ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-139">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="5da6c-140">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5da6c-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="5da6c-141">Notez que tous les éléments racine du modèle de données sélectionné peuvent être sélectionnés comme définition du modèle de données.</span><span class="sxs-lookup"><span data-stu-id="5da6c-141">Note that all root items of the selected data model are currently available for selection as a data model definition.</span></span> <span data-ttu-id="5da6c-142">Vous pouvez continuer à créer votre format à l'aide des éléments racine requis du modèle de données.</span><span class="sxs-lookup"><span data-stu-id="5da6c-142">You can continue to design your format by using any of the required root items of the data model.</span></span> <span data-ttu-id="5da6c-143">Une mise en correspondance de modèle manquante pour l'élément racine sélectionné ne vous empêche pas de continuer.</span><span class="sxs-lookup"><span data-stu-id="5da6c-143">A missing model mapping for the selected root item doesn't prevent you from continuing.</span></span>  
4. <span data-ttu-id="5da6c-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5da6c-144">Close the page.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="5da6c-145">Ajouter une nouvelle configuration de mise en correspondance du modèle de données ER</span><span class="sxs-lookup"><span data-stu-id="5da6c-145">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="5da6c-146">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5da6c-146">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="5da6c-147">Dans le champ Nouveau, entrez « Mise en correspondance de modèle basée sur le modèle de données Modèle de paiement (fictif) ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-147">In the New field, enter 'Model Mapping based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="5da6c-148">Dans le champ Nom, tapez « Mises en correspondance de modèle de paiement (fictives) ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-148">In the Name field, type 'Payment model mappings (fictitious)'.</span></span>
    * <span data-ttu-id="5da6c-149">Mises en correspondance de modèle de paiement (fictives)</span><span class="sxs-lookup"><span data-stu-id="5da6c-149">Payment model mappings (fictitious)</span></span>  
4. <span data-ttu-id="5da6c-150">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5da6c-150">In the Data model definition field, enter or select a value.</span></span>
5. <span data-ttu-id="5da6c-151">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="5da6c-151">Click Create configuration.</span></span>

## <a name="design-er-model-mappings"></a><span data-ttu-id="5da6c-152">Créer des mises en correspondance de modèle ER</span><span class="sxs-lookup"><span data-stu-id="5da6c-152">Design ER model mappings</span></span>
1. <span data-ttu-id="5da6c-153">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="5da6c-153">Click Designer.</span></span>
    * <span data-ttu-id="5da6c-154">Utilisez le concepteur ER pour spécifier les mises en correspondance de modèle pour les éléments racine requis.</span><span class="sxs-lookup"><span data-stu-id="5da6c-154">Use the ER designer to specify the model mappings for the required root items.</span></span>  
2. <span data-ttu-id="5da6c-155">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="5da6c-155">Click Designer.</span></span>
    * <span data-ttu-id="5da6c-156">Simulez le paramétrage de la mise en correspondance de modèle sélectionnée pour l'élément racine du modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5da6c-156">Simulate setting of selected model mapping for the selected model’s root item.</span></span>  
3. <span data-ttu-id="5da6c-157">Dans l'arborescence, sélectionnez « Dynamics 365 for Operations\Enregistrements de tables ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-157">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
4. <span data-ttu-id="5da6c-158">Cliquez sur Ajouter racine.</span><span class="sxs-lookup"><span data-stu-id="5da6c-158">Click Add root.</span></span>
5. <span data-ttu-id="5da6c-159">Dans le champ Nom, tapez « Comptabilité ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-159">In the Name field, type 'Ledger'.</span></span>
6. <span data-ttu-id="5da6c-160">Dans le champ Table, tapez « LedgerJournalTrans ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-160">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="5da6c-161">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="5da6c-161">LedgerJournalTrans</span></span>  
7. <span data-ttu-id="5da6c-162">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5da6c-162">Click OK.</span></span>
8. <span data-ttu-id="5da6c-163">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="5da6c-163">Click Save.</span></span>
9. <span data-ttu-id="5da6c-164">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5da6c-164">Close the page.</span></span>
10. <span data-ttu-id="5da6c-165">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5da6c-165">Close the page.</span></span>

## <a name="start-to-enter-another-new-er-format-configuration"></a><span data-ttu-id="5da6c-166">Commencer à entrer une nouvelle autre configuration du format ER</span><span class="sxs-lookup"><span data-stu-id="5da6c-166">Start to enter another new ER format configuration</span></span>
1. <span data-ttu-id="5da6c-167">Dans l'arborescence, sélectionnez « Modèle de paiement (fictif) ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-167">In the tree, select 'Payment model (fictitious)'.</span></span>
2. <span data-ttu-id="5da6c-168">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5da6c-168">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="5da6c-169">Dans le champ Nouveau, entrez « Format basé sur le modèle de données Modèle de paiement (fictif) ».</span><span class="sxs-lookup"><span data-stu-id="5da6c-169">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
4. <span data-ttu-id="5da6c-170">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5da6c-170">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="5da6c-171">Notez qu'un seul élément racine est désormais disponible pour la mise en correspondance avec les sources de données d'application.</span><span class="sxs-lookup"><span data-stu-id="5da6c-171">Note that now only one root item is available to map to the application data sources.</span></span> <span data-ttu-id="5da6c-172">Si au moins une mise en correspondance de modèle est introduite, seuls les éléments racine du modèle qui sont mis en correspondance avec les sources de données d'application peuvent être sélectionnés comme définition de modèle lorsque le format ER est ajouté.</span><span class="sxs-lookup"><span data-stu-id="5da6c-172">When at least one model mapping is introduced, only the model’s root items that are mapped to application data sources can be selected as a model definition while the ER format is added.</span></span>   
5. <span data-ttu-id="5da6c-173">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5da6c-173">Close the page.</span></span>


