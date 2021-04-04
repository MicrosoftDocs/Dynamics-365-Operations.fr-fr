---
title: ER Mettre à niveau votre format en adoptant la nouvelle version de base de ce format
description: Cette rubrique décrit comment préserver une configuration de format pour la gestion des états électroniques.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 336551f4e9858269010ec7debd1750a8d8453163
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564240"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a><span data-ttu-id="3ee77-103">ER Mettre à niveau votre format en adoptant la nouvelle version de base de ce format</span><span class="sxs-lookup"><span data-stu-id="3ee77-103">ER Upgrade your format by adopting a new, base version of that format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3ee77-104">Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d’états électroniques peut conserver une configuration de format pour la génération d’états électronique (ER).</span><span class="sxs-lookup"><span data-stu-id="3ee77-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can maintain an Electronic reporting (ER) format configuration.</span></span> <span data-ttu-id="3ee77-105">Cette procédure explique comment une version personnalisée d’un format peut être créée en fonction du format reçu d’un fournisseur de configuration.</span><span class="sxs-lookup"><span data-stu-id="3ee77-105">This procedure explains how a custom version of a format can be created based on the format received from a configuration provider (CP).</span></span> <span data-ttu-id="3ee77-106">Elle décrit également comment adopter une nouvelle version de base de ce format.</span><span class="sxs-lookup"><span data-stu-id="3ee77-106">It also explains how to adopt a new, base version of that format.</span></span>

<span data-ttu-id="3ee77-107">Pour effectuer ces étapes, vous devez tout d’abord appliquer les procédures « Créer un fournisseur de configuration et le marquer comme actif » et « Utiliser le format créé pour générer des documents électroniques ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" and "Use created format to generate electronic documents for payments" procedures.</span></span> <span data-ttu-id="3ee77-108">Ces étapes peuvent être effectuées dans la société GBSI.</span><span class="sxs-lookup"><span data-stu-id="3ee77-108">These steps can be performed in the GBSI company.</span></span>

## <a name="select-format-configuration-for-customization"></a><span data-ttu-id="3ee77-109">Sélectionner la configuration du format pour la personnalisation</span><span class="sxs-lookup"><span data-stu-id="3ee77-109">Select format configuration for customization</span></span>
1. <span data-ttu-id="3ee77-110">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="3ee77-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="3ee77-111">Dans cet exemple, la société fictive Litware, Inc. (https://www.litware.com) fait office de fournisseur de configuration qui prend en charge les configurations de format pour les paiements électroniques pour un pays particulier.</span><span class="sxs-lookup"><span data-stu-id="3ee77-111">In this example, sample company Litware, Inc. (https://www.litware.com) will act as a configuration provider that supports format configurations for electronic payments for a particular country.</span></span>    <span data-ttu-id="3ee77-112">La société fictive Proseware, Inc. (http://www.proseware.com) fait office de consommateur de la configuration du format fourni par Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="3ee77-112">Sample company Proseware, Inc. (http://www.proseware.com) will act as a consumer of the format configuration that Litware, Inc. provided.</span></span> <span data-ttu-id="3ee77-113">Proseware, Inc. utilise des formats dans certaines régions de ce pays.</span><span class="sxs-lookup"><span data-stu-id="3ee77-113">Proseware, Inc. uses formats in certain regions of that country.</span></span>  
2. <span data-ttu-id="3ee77-114">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="3ee77-114">Click Reporting configurations.</span></span>
3. <span data-ttu-id="3ee77-115">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="3ee77-115">Click Show filters.</span></span>
4. <span data-ttu-id="3ee77-116">Appliquez les filtres suivants : entrez la valeur de filtre « BACS (nom fictif britannique) » dans le champ « Nom » à l’aide de l’opérateur de filtre « commence par ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-116">Apply the following filters: Enter a filter value of "BACS (UK fictitious)" on the "Name" field using the "begins with" filter operator.</span></span>
  
    <span data-ttu-id="3ee77-117">La configuration du format sélectionné BACS (nom fictif britannique) appartient au fournisseur Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="3ee77-117">The selected format configuration BACS (UK fictitious) is owned by provider Litware, Inc.</span></span>  

5. <span data-ttu-id="3ee77-118">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="3ee77-118">Click Show filters.</span></span>
6. <span data-ttu-id="3ee77-119">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3ee77-119">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="3ee77-120">La version du format dont le statut est Terminé est utilisée par Proseware, Inc. pour la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="3ee77-120">The version of the format with the status of Completed will be used by Proseware, Inc. for customization.</span></span>  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a><span data-ttu-id="3ee77-121">Créer une configuration pour le format personnalisé du document électronique</span><span class="sxs-lookup"><span data-stu-id="3ee77-121">Create a new configuration for your custom format of electronic document</span></span>
<span data-ttu-id="3ee77-122">Proseware, Inc. a reçu la version 1.1 de la configuration BACS (nom fictif britannique) qui contient le format initial pour générer des documents de paiement électronique à partir de Litware, Inc. conformément à leur abonnement au service.</span><span class="sxs-lookup"><span data-stu-id="3ee77-122">Proseware, Inc. received version 1.1 of BACS (UK fictitious) configuration that contains the initial format to generate electronic payment documents from Litware, Inc. in accordance to their service subscription.</span></span> <span data-ttu-id="3ee77-123">Proseware, Inc. souhaite commencer à l’aide de cette norme pour son pays, mais certaines personnalisations sont nécessaires pour prendre en charge des besoins spécifiques à la région.</span><span class="sxs-lookup"><span data-stu-id="3ee77-123">Proseware, Inc. wants to start using this as a standard for their country but some customization is required to support specific regional requirements.</span></span> <span data-ttu-id="3ee77-124">Proseware, Inc. souhaite également conserver la capacité de mettre à niveau un format personnalisé dès qu’une nouvelle version de celui-ci (avec des modifications pour prendre en charge de nouveaux besoins spécifiques au pays) est disponible à partir de Litware, Inc. et il souhaite effectuer cette mise à niveau à moindre coût.</span><span class="sxs-lookup"><span data-stu-id="3ee77-124">Proseware, Inc. also wants to keep the ability to upgrade a custom format as soon as a new version of it (with changes to support new country-specific requirements) comes from Litware, Inc. and they want to perform this upgrade with the lowest cost.</span></span>  

<span data-ttu-id="3ee77-125">Pour ce faire, Proseware, Inc. doit créer une configuration à l’aide de la configuration du format sélectionné BACS (nom fictif britannique) de Litware, Inc. comme base.</span><span class="sxs-lookup"><span data-stu-id="3ee77-125">To do this, Proseware, Inc. needs to create a configuration using the Litware, Inc. configuration BACS (UK fictitious) as a base.</span></span>  

1. <span data-ttu-id="3ee77-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3ee77-126">Close the page.</span></span>
2. <span data-ttu-id="3ee77-127">Sélectionnez Proseware, Inc. pour en faire un fournisseur actif.</span><span class="sxs-lookup"><span data-stu-id="3ee77-127">Select Proseware, Inc. to make it an active provider.</span></span>
3. <span data-ttu-id="3ee77-128">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="3ee77-128">Click Set active.</span></span>
4. <span data-ttu-id="3ee77-129">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="3ee77-129">Click Reporting configurations.</span></span>
5. <span data-ttu-id="3ee77-130">Dans l’arborescence, développez « Paiements (modèle simplifié) ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-130">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="3ee77-131">Dans l’arborescence, sélectionnez « Paiements (modèle simplifié) »\BACS (nom fictif britannique) ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-131">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="3ee77-132">Sélectionnez la configuration du format sélectionné BACS (nom fictif britannique) de Litware, Inc. Proseware, Inc. utilise la version 1.1 comme base pour la version personnalisée.</span><span class="sxs-lookup"><span data-stu-id="3ee77-132">Select the BACS (UK fictitious) configuration from Litware, Inc. Proseware, Inc. will use version 1.1 as a base for the custom version.</span></span>  

7. <span data-ttu-id="3ee77-133">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3ee77-133">Click Create configuration to open the drop dialog.</span></span>

    <span data-ttu-id="3ee77-134">Cela vous permet de créer une configuration pour un format de paiement personnalisé.</span><span class="sxs-lookup"><span data-stu-id="3ee77-134">This lets you create a new configuration for a custom payment format.</span></span>  

8. <span data-ttu-id="3ee77-135">Dans le champ Nouveau, entrez « Provenant du nom : BACS (nom fictif britannique), Litware, Inc. ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-135">In the New field, enter 'Derive from Name: BACS (UK fictitious), Litware, Inc.'.</span></span>

    <span data-ttu-id="3ee77-136">Sélectionnez l’option Déduire pour confirmer l’utilisation de BACS (nom fictif britannique) comme base pour créer la version personnalisée.</span><span class="sxs-lookup"><span data-stu-id="3ee77-136">Select the Derive option to confirm the usage of BACS (UK fictitious) as the base for creating the custom version.</span></span>  

9. <span data-ttu-id="3ee77-137">Dans le champ Nom, tapez « BACS (nom personnalisé fictif britannique) ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-137">In the Name field, type 'BACS (UK fictitious custom)'.</span></span>
10. <span data-ttu-id="3ee77-138">Dans le champ Description, entrez « Paiement fournisseur BACS (nom personnalisé fictif britannique) ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-138">In the Description field, type 'BACS vendor payment (UK fictitious custom)'.</span></span>

    <span data-ttu-id="3ee77-139">Le fournisseur de configuration actif (Proseware, Inc.) est automatiquement entré ici.</span><span class="sxs-lookup"><span data-stu-id="3ee77-139">The active configuration provider (Proseware, Inc.) is automatically entered here.</span></span> <span data-ttu-id="3ee77-140">Ce fournisseur pourra mettre à jour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="3ee77-140">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="3ee77-141">D’autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="3ee77-141">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

11. <span data-ttu-id="3ee77-142">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="3ee77-142">Click Create configuration.</span></span>

## <a name="customize-your-format-for-the-electronic-document"></a><span data-ttu-id="3ee77-143">Personnaliser le format du document électronique</span><span class="sxs-lookup"><span data-stu-id="3ee77-143">Customize your format for the electronic document</span></span>
1. <span data-ttu-id="3ee77-144">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="3ee77-144">Click Designer.</span></span>
2. <span data-ttu-id="3ee77-145">Cliquez sur Développer/réduire.</span><span class="sxs-lookup"><span data-stu-id="3ee77-145">Click Expand/collapse.</span></span>
3. <span data-ttu-id="3ee77-146">Cliquez sur Développer/réduire.</span><span class="sxs-lookup"><span data-stu-id="3ee77-146">Click Expand/collapse.</span></span>
4. <span data-ttu-id="3ee77-147">Dans l’arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="3ee77-148">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3ee77-148">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="3ee77-149">Dans l’arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-149">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="3ee77-150">Tapez « IBAN » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="3ee77-150">In the Name field, type 'IBAN'.</span></span>
8. <span data-ttu-id="3ee77-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ee77-151">Click OK.</span></span>
9. <span data-ttu-id="3ee77-152">Dans l’arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\IBAN ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-152">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\IBAN'.</span></span>
10. <span data-ttu-id="3ee77-153">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3ee77-153">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="3ee77-154">Dans l’arborescence, sélectionnez « Texte\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-154">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="3ee77-155">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ee77-155">Click OK.</span></span>
13. <span data-ttu-id="3ee77-156">Dans l’arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Nom\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-156">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="3ee77-157">Dans le champ Longueur maximale, entrez 60.</span><span class="sxs-lookup"><span data-stu-id="3ee77-157">In the Maximum length field, enter '60'.</span></span>
15. <span data-ttu-id="3ee77-158">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="3ee77-158">Click the Mapping tab.</span></span>
16. <span data-ttu-id="3ee77-159">Dans l’arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-159">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="3ee77-160">Dans l’arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="3ee77-160">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="3ee77-161">Dans l’arborescence , développez « modèle\Paiements\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-161">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="3ee77-162">Dans l’arborescence , développez « modèle\Paiements\Créditeur\Compte ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-162">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
20. <span data-ttu-id="3ee77-163">Dans l’arborescence, sélectionnez « Modèle\Paiements\Créditeur\Compte\IBAN ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-163">In the tree, select 'model\Payments\Creditor\Account\IBAN'.</span></span>
21. <span data-ttu-id="3ee77-164">Dans l’arborescence, sélectionnez « Xml\Message\Paiements\Article = model.Payments\Fournisseur\Banque\IBAN\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-164">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\IBAN\String'.</span></span>
22. <span data-ttu-id="3ee77-165">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3ee77-165">Click Bind.</span></span>
23. <span data-ttu-id="3ee77-166">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3ee77-166">Click Save.</span></span>

## <a name="validate-the-customized-format"></a><span data-ttu-id="3ee77-167">Valider le format personnalisé</span><span class="sxs-lookup"><span data-stu-id="3ee77-167">Validate the customized format</span></span>
1. <span data-ttu-id="3ee77-168">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="3ee77-168">Click Validate.</span></span>

    <span data-ttu-id="3ee77-169">Validez la structure de format personnalisée et les modifications de mise en correspondance des données pour vous assurer que toutes les liaisons sont correctes.</span><span class="sxs-lookup"><span data-stu-id="3ee77-169">Validate the customized format layout and data mapping changes to make sure that all bindings are okay.</span></span>  

2. <span data-ttu-id="3ee77-170">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3ee77-170">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a><span data-ttu-id="3ee77-171">Modifier le statut de la version actuelle de la configuration de format personnalisé</span><span class="sxs-lookup"><span data-stu-id="3ee77-171">Change the status of the current version of the custom format configuration</span></span>
<span data-ttu-id="3ee77-172">Modifiez le statut de la configuration du format conçu : remplacez Brouillon par Terminé pour le rendre disponible pour la génération de document de paiement.</span><span class="sxs-lookup"><span data-stu-id="3ee77-172">Change the status of the designed format configuration from Draft to Completed to make it available for payment document generation.</span></span>  

1. <span data-ttu-id="3ee77-173">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="3ee77-173">Click Change status.</span></span>

    <span data-ttu-id="3ee77-174">Notez que la version actuelle de la configuration sélectionnée est en mode Brouillon.</span><span class="sxs-lookup"><span data-stu-id="3ee77-174">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="3ee77-175">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="3ee77-175">Click Complete.</span></span>
3. <span data-ttu-id="3ee77-176">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3ee77-176">In the Description field, type a value.</span></span>
4. <span data-ttu-id="3ee77-177">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ee77-177">Click OK.</span></span>
5. <span data-ttu-id="3ee77-178">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3ee77-178">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="3ee77-179">Notez que la configuration créée est enregistrée comme version 1.1.1 terminée.</span><span class="sxs-lookup"><span data-stu-id="3ee77-179">Note that the created configuration is saved as completed version 1.1.1.</span></span> <span data-ttu-id="3ee77-180">Cela signifie que c’est la version 1 du format BACS (nom personnalisé fictif britannique) personnalisé, qui est basé sur la version 1 du format BACS (nom fictif britannique), basé sur la version 1 du modèle de données Paiements (modèle simplifié).</span><span class="sxs-lookup"><span data-stu-id="3ee77-180">This means it is version 1 of the custom BACS (UK fictitious custom) format, which is based on version 1 of the BACS (UK fictitious) format, which is based on version 1 of the Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-to-generate-payment-files"></a><span data-ttu-id="3ee77-181">Tester le format personnalisé pour générer des fichiers de paiement</span><span class="sxs-lookup"><span data-stu-id="3ee77-181">Test the customized format to generate payment files</span></span>
<span data-ttu-id="3ee77-182">Suivez les étapes de la procédure « Utiliser le format créé pour générer des documents électroniques de paiement » dans une session parallèle de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3ee77-182">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in a parallel Finance and Operations session.</span></span> <span data-ttu-id="3ee77-183">Sélectionnez le format BACS (nom personnalisé fictif britannique) dans les paramètres de mode de paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="3ee77-183">Select the BACS (UK fictitious custom) format in electronic payment method parameters.</span></span> <span data-ttu-id="3ee77-184">Vérifiez que le fichier de paiement créé contient le nœud XML introduit récemment présentant le code IBAN conformément aux besoins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3ee77-184">Make sure that the created payment file contains the recently introduced XML node presenting IBAN code in accordance to regional requirements.</span></span>  

## <a name="update-the-existing-country-specific-configuration"></a><span data-ttu-id="3ee77-185">Mettre à jour la configuration spécifique au pays existant</span><span class="sxs-lookup"><span data-stu-id="3ee77-185">Update the existing country-specific configuration</span></span>
<span data-ttu-id="3ee77-186">Litware, Inc. doit mettre à jour la configuration BACS (nom personnalisé fictif britannique) et adopter de nouvelles exigences spécifiques au pays pour gérer le format du document électronique.</span><span class="sxs-lookup"><span data-stu-id="3ee77-186">Litware, Inc. needs to update the BACS (UK fictitious) configuration and adopt new country requirements for managing the format of the electronic document.</span></span> <span data-ttu-id="3ee77-187">Cela sera ensuite associé à une nouvelle version de cette configuration qui sera proposée aux abonnés du service, notamment Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="3ee77-187">Later, this will be enclosed in a new version of this configuration that will be offered for service subscribers, including Proseware, Inc.</span></span>  

<span data-ttu-id="3ee77-188">Dans les véritables processus associés à l’approvisionnement de service, chaque nouvelle version de BACS (nom fictif britannique) peut être importée par Proseware, Inc. à partir du référentiel LCS de configurations Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="3ee77-188">In real service provision related processes, each new version of BACS (UK fictitious) can be imported by Proseware, Inc. from Litware, Inc. configurations' LCS repository.</span></span> <span data-ttu-id="3ee77-189">Dans cette procédure nous simulerons cela en mettant à jour BACS (nom fictif britannique) au nom d’un fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="3ee77-189">In this procedure we will simulate this by updating BACS (UK fictitious) on behalf of a service provider.</span></span>  

1. <span data-ttu-id="3ee77-190">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3ee77-190">Close the page.</span></span>
2. <span data-ttu-id="3ee77-191">Sélectionnez Litware, Inc. .</span><span class="sxs-lookup"><span data-stu-id="3ee77-191">Select Litware, inc. provider.</span></span>
3. <span data-ttu-id="3ee77-192">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="3ee77-192">Click Set active.</span></span>
4. <span data-ttu-id="3ee77-193">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="3ee77-193">Click Reporting configurations.</span></span>
5. <span data-ttu-id="3ee77-194">Dans l’arborescence, développez « Paiements (modèle simplifié) ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-194">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="3ee77-195">Dans l’arborescence, sélectionnez « Paiements (modèle simplifié) »\BACS (nom fictif britannique) ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-195">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="3ee77-196">La version temporaire BACS (nom fictif britannique) appartenant au fournisseur Litware, Inc. est sélectionnée pour apporter des modifications pour prendre en charge de nouvelles exigences spécifiques au pays.</span><span class="sxs-lookup"><span data-stu-id="3ee77-196">The draft version owned by Litware, Inc. provider BACS (UK fictitious) is selected to bring in changes to support new country-specific requirements.</span></span>  

## <a name="localize-the-base-format-of-the-electronic-document"></a><span data-ttu-id="3ee77-197">Localiser le format de base du document électronique</span><span class="sxs-lookup"><span data-stu-id="3ee77-197">Localize the base format of the electronic document</span></span>
<span data-ttu-id="3ee77-198">Supposons qu’il existe de nouvelles exigences spécifiques au pays à prendre en charge par Litware, Inc. :</span><span class="sxs-lookup"><span data-stu-id="3ee77-198">Assume that there are new country-specific requirements to be supported by Litware, Inc.:</span></span>  

- <span data-ttu-id="3ee77-199">Une valeur pour le code SWIFT de la banque créancière dans chaque transaction de paiement.</span><span class="sxs-lookup"><span data-stu-id="3ee77-199">A value for the creditor's bank SWIFT code in each payment transaction.</span></span>
- <span data-ttu-id="3ee77-200">La longueur du nom du fournisseur est limitée à 100 caractères dans la génération de fichiers.</span><span class="sxs-lookup"><span data-stu-id="3ee77-200">A limit of 100 characters for the length of text for the vendor's name in a generating file.</span></span>  
- <span data-ttu-id="3ee77-201">Nouvelles exigences spécifiques à un pays</span><span class="sxs-lookup"><span data-stu-id="3ee77-201">New country-specific requirements</span></span>  
- <span data-ttu-id="3ee77-202">Sélectionnez la version temporaire de la configuration souhaitée pour afficher les modifications requises.</span><span class="sxs-lookup"><span data-stu-id="3ee77-202">Select the draft version of the desired configuration to introduce required changes.</span></span>  


1. <span data-ttu-id="3ee77-203">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="3ee77-203">Click Designer.</span></span>
2. <span data-ttu-id="3ee77-204">Cliquez sur Développer/réduire.</span><span class="sxs-lookup"><span data-stu-id="3ee77-204">Click Expand/collapse.</span></span>
3. <span data-ttu-id="3ee77-205">Cliquez sur Développer/réduire.</span><span class="sxs-lookup"><span data-stu-id="3ee77-205">Click Expand/collapse.</span></span>
4. <span data-ttu-id="3ee77-206">Dans l’arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-206">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="3ee77-207">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3ee77-207">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="3ee77-208">Dans l’arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-208">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="3ee77-209">Tapez SWIFT dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="3ee77-209">In the Name field, type 'SWIFT'.</span></span>
8. <span data-ttu-id="3ee77-210">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ee77-210">Click OK.</span></span>
9. <span data-ttu-id="3ee77-211">Dans l’arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\SWIFT ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-211">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\SWIFT'.</span></span>
10. <span data-ttu-id="3ee77-212">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3ee77-212">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="3ee77-213">Dans l’arborescence, sélectionnez « Texte\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-213">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="3ee77-214">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ee77-214">Click OK.</span></span>
13. <span data-ttu-id="3ee77-215">Dans l’arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Nom\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-215">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="3ee77-216">Dans le champ Longueur maximale, entrez 100.</span><span class="sxs-lookup"><span data-stu-id="3ee77-216">In the Maximum length field, enter '100'.</span></span>
15. <span data-ttu-id="3ee77-217">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="3ee77-217">Click the Mapping tab.</span></span>
16. <span data-ttu-id="3ee77-218">Dans l’arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-218">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="3ee77-219">Dans l’arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="3ee77-219">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="3ee77-220">Dans l’arborescence , développez « modèle\Paiements\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-220">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="3ee77-221">Dans l’arborescence , développez « modèle\Paiements\Créditeur\Agent ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-221">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
20. <span data-ttu-id="3ee77-222">Dans l’arborescence, sélectionnez « Modèle\Paiements\Créditeur\Agent\SWIFT ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-222">In the tree, select 'model\Payments\Creditor\Agent\SWIFT'.</span></span>
21. <span data-ttu-id="3ee77-223">Dans l’arborescence, sélectionnez « Xml\Message\Paiements\Article = model.Payments\Fournisseur\Banque\SWIFT\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-223">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\SWIFT\String'.</span></span>
22. <span data-ttu-id="3ee77-224">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="3ee77-224">Click Bind.</span></span>
23. <span data-ttu-id="3ee77-225">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3ee77-225">Click Save.</span></span>

## <a name="validate-the-localized-format"></a><span data-ttu-id="3ee77-226">Valider le format localisé</span><span class="sxs-lookup"><span data-stu-id="3ee77-226">Validate the localized format</span></span>
1. <span data-ttu-id="3ee77-227">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="3ee77-227">Click Validate.</span></span>
2. <span data-ttu-id="3ee77-228">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3ee77-228">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a><span data-ttu-id="3ee77-229">Modifier le statut de la version actuelle de la configuration du format de base</span><span class="sxs-lookup"><span data-stu-id="3ee77-229">Change the status of the current version of the base format configuration</span></span>
<span data-ttu-id="3ee77-230">Modifiez le statut de la configuration du format de base mis à jour de Brouillon à Terminé pour le rendre disponible pour la génération de documents de paiement et de mises à jour des configurations de format dérivées de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="3ee77-230">Change the status of the updated base format configuration from Draft to Completed to make it available for generation of payment documents and updates of format configurations derived from it.</span></span>  

1. <span data-ttu-id="3ee77-231">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="3ee77-231">Click Change status.</span></span>

    <span data-ttu-id="3ee77-232">Notez que la version actuelle de la configuration sélectionnée est en mode Brouillon.</span><span class="sxs-lookup"><span data-stu-id="3ee77-232">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="3ee77-233">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="3ee77-233">Click Complete.</span></span>
3. <span data-ttu-id="3ee77-234">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3ee77-234">In the Description field, type a value.</span></span>
4. <span data-ttu-id="3ee77-235">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ee77-235">Click OK.</span></span>
5. <span data-ttu-id="3ee77-236">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3ee77-236">In the list, find and select the desired record.</span></span>

## <a name="change-the-base-version-for-the-custom-format-configuration"></a><span data-ttu-id="3ee77-237">Modifier la version de base pour la configuration du format personnalisé</span><span class="sxs-lookup"><span data-stu-id="3ee77-237">Change the base version for the custom format configuration</span></span>

<span data-ttu-id="3ee77-238">Proseware, Inc. est informé qu’une nouvelle version 1.2 de la configuration de BACS (nom fictif britannique) est disponible pour générer des documents de paiement électronique conformément aux nouvelles exigences spécifiques au pays annoncées.</span><span class="sxs-lookup"><span data-stu-id="3ee77-238">Proseware, Inc. is informed that a new version 1.2 of BACS (UK fictitious) configuration is available to generate electronic payment documents in accordance to recently announced country-specific requirements.</span></span> <span data-ttu-id="3ee77-239">Proseware, Inc. souhaite commencer à l’utiliser en tant que standard pour le pays.</span><span class="sxs-lookup"><span data-stu-id="3ee77-239">Proseware, Inc. wants to start using it as a standard for the country.</span></span>  

<span data-ttu-id="3ee77-240">Pour cela, Proseware, Inc. doit modifier la version de configuration de base pour la configuration personnalisée BACS (nom personnalisé fictif britannique).</span><span class="sxs-lookup"><span data-stu-id="3ee77-240">To do this, Proseware, Inc. needs to change the base configuration version for the custom configuration BACS (UK fictitious custom).</span></span> <span data-ttu-id="3ee77-241">Utilisez la nouvelle version 1.2 au lieu de la version 1.1 de BACS (nom fictif britannique).</span><span class="sxs-lookup"><span data-stu-id="3ee77-241">Instead of version 1.1 of BACS (UK fictitious) use new version 1.2.</span></span>  

1. <span data-ttu-id="3ee77-242">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="3ee77-242">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="3ee77-243">Sélectionnez le fournisseur Proseware, Inc. pour le marquer comme actif.</span><span class="sxs-lookup"><span data-stu-id="3ee77-243">Select the Proseware, Inc. provider to mark it as active.</span></span>
3. <span data-ttu-id="3ee77-244">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="3ee77-244">Click Set active.</span></span>
4. <span data-ttu-id="3ee77-245">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="3ee77-245">Click Reporting configurations.</span></span>
5. <span data-ttu-id="3ee77-246">Dans l’arborescence, développez « Paiements (modèle simplifié) ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-246">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="3ee77-247">Dans l’arborescence, développez « Paiements (modèle simplifié) »\BACS (nom fictif britannique) ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-247">In the tree, expand 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
7. <span data-ttu-id="3ee77-248">Dans l’arborescence, sélectionnez « Paiements (modèle simplifié) »\BACS (nom fictif britannique)\BACS (nom personnalisé fictif britannique) ».</span><span class="sxs-lookup"><span data-stu-id="3ee77-248">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)\BACS (UK fictitious custom)'.</span></span>

    <span data-ttu-id="3ee77-249">Sélectionnez BACS (nom personnalisé fictif britannique), qui appartient à Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="3ee77-249">Select the BACS (UK fictitious custom) configuration, which is owned by Proseware, Inc.</span></span>  

    <span data-ttu-id="3ee77-250">Utilisez la version temporaire de la configuration sélectionnée pour afficher les modifications requises.</span><span class="sxs-lookup"><span data-stu-id="3ee77-250">Use the draft version of the selected configuration to introduce required changes.</span></span>  

8. <span data-ttu-id="3ee77-251">Cliquez sur Redéfinir.</span><span class="sxs-lookup"><span data-stu-id="3ee77-251">Click Rebase.</span></span>

    <span data-ttu-id="3ee77-252">Sélectionnez la nouvelle version 1.2 de la configuration de base à appliquer nouvelle comme base pour mettre la configuration à jour.</span><span class="sxs-lookup"><span data-stu-id="3ee77-252">Select the new version 1.2 of the base configuration to be applied as a new base for updating the configuration.</span></span>  

9. <span data-ttu-id="3ee77-253">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ee77-253">Click OK.</span></span>

    <span data-ttu-id="3ee77-254">Notez que certains conflits ont été découverts entre la fusion de la version personnalisée et une nouvelle version de base représentant certaines modifications de format qui ne peuvent pas être fusionnées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="3ee77-254">Note that some conflicts have been discovered between merging the custom version and a new base version representing some format changes that can't be merged automatically.</span></span>  

## <a name="resolve-rebase-conflicts"></a><span data-ttu-id="3ee77-255">Résoudre des conflits redéfinis</span><span class="sxs-lookup"><span data-stu-id="3ee77-255">Resolve rebase conflicts</span></span>
1. <span data-ttu-id="3ee77-256">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="3ee77-256">Click Designer.</span></span>
    
    <span data-ttu-id="3ee77-257">Notez que les modifications apportées à la limite de longueur de texte du nom du fournisseur ne peuvent pas être résolues automatiquement.</span><span class="sxs-lookup"><span data-stu-id="3ee77-257">Note that changes to the vendor's name text length limit couldn't be resolved automatically.</span></span> <span data-ttu-id="3ee77-258">Elles sont par conséquent présentées dans une liste des conflits.</span><span class="sxs-lookup"><span data-stu-id="3ee77-258">Therefore, this is presented in a conflicts list.</span></span> <span data-ttu-id="3ee77-259">Pour chaque conflit de mise à jour du type, les options suivantes sont disponibles : Appliquer la valeur de base précédente (bouton en haut de la grille) pour afficher la valeur de version de base précédente (0 dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="3ee77-259">For each conflict of type Update, the following options are available:  - Apply a prior base value (button on top of the grid) to bring in the previous base version value (0 in our case).</span></span>  <span data-ttu-id="3ee77-260">- Appliquez une valeur de base (bouton en haut de la grille) pour afficher la nouvelle valeur de version de base (100 dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="3ee77-260">- Apply a base value (button on top of the grid) to bring in the new base version value (100 in our case).</span></span>  <span data-ttu-id="3ee77-261">- Conservez vos propres valeurs (personnalisées) (60 dans notre cas).</span><span class="sxs-lookup"><span data-stu-id="3ee77-261">- Keep your own (custom) value (60 in our case).</span></span>  <span data-ttu-id="3ee77-262">Cliquez sur Appliquer la valeur de base pour appliquer une limite spécifique au pays de 100 caractères pour la longueur du nom du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3ee77-262">Click Apply base value to apply a country-specific limit of 100 characters for vendor's name text length.</span></span>  

    <span data-ttu-id="3ee77-263">Notez que Proseware, Inc. et Litware, Inc. ont des versions personnalisées et locales de ce format à l’aide de codes IBAN et SWIFT avec les composants associés qui sont automatiquement fusionnés dans le format de gestion.</span><span class="sxs-lookup"><span data-stu-id="3ee77-263">Note that Proseware, Inc. and Litware, Inc. have custom and local versions of this format using IBAN and SWIFT codes with related components that are automatically merged in the managing format.</span></span>  

2. <span data-ttu-id="3ee77-264">Cliquez sur Appliquer la valeur de base.</span><span class="sxs-lookup"><span data-stu-id="3ee77-264">Click Apply base value.</span></span>

    <span data-ttu-id="3ee77-265">Cliquez sur Appliquer la valeur de base pour appliquer la limite spécifique à la région de 100 caractères aux noms de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3ee77-265">Click Apply base value to apply the country-specific limit of 100 characters for vendor names.</span></span>  

3. <span data-ttu-id="3ee77-266">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3ee77-266">Click Save.</span></span>

    <span data-ttu-id="3ee77-267">Si vous enregistrez le format, cela supprimera des conflits résolus de la liste des conflits.</span><span class="sxs-lookup"><span data-stu-id="3ee77-267">Saving the format will remove resolved conflicts from the conflicts list.</span></span>  

4. <span data-ttu-id="3ee77-268">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3ee77-268">Close the page.</span></span>

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a><span data-ttu-id="3ee77-269">Modifier le statut de la nouvelle version de la configuration du format personnalisé</span><span class="sxs-lookup"><span data-stu-id="3ee77-269">Change the status of the new version of the custom format configuration</span></span>
1. <span data-ttu-id="3ee77-270">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="3ee77-270">Click Change status.</span></span>

    <span data-ttu-id="3ee77-271">Modifiez le statut de la configuration du format personnalisé, mis à jour de Brouillon à Terminé.</span><span class="sxs-lookup"><span data-stu-id="3ee77-271">Change the status of the updated, custom format configuration from Draft to Completed.</span></span> <span data-ttu-id="3ee77-272">Cela rendra la configuration du format disponible pour générer des documents de paiement.</span><span class="sxs-lookup"><span data-stu-id="3ee77-272">This will make the format configuration available for generating payment documents.</span></span> <span data-ttu-id="3ee77-273">Notez que la version actuelle de la configuration sélectionnée est en mode Brouillon.</span><span class="sxs-lookup"><span data-stu-id="3ee77-273">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="3ee77-274">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="3ee77-274">Click Complete.</span></span>
3. <span data-ttu-id="3ee77-275">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3ee77-275">In the Description field, type a value.</span></span>
4. <span data-ttu-id="3ee77-276">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3ee77-276">Click OK.</span></span>

    <span data-ttu-id="3ee77-277">Notez que la configuration créée est enregistrée comme version 1.2.2 terminée : la version 2 du format BACS (nom personnalisé fictif britannique) de base, basé sur la version 2 du format du BACS (nom fictif britannique) de base, basé sur la version 1 du modèle de données Paiements (modèle simplifié).</span><span class="sxs-lookup"><span data-stu-id="3ee77-277">Note that the created configuration is saved as completed version 1.2.2: version 2 of base BACS (UK fictitious custom) format, which is based on version 2 of base BACS (UK fictitious) format, which is based on version 1 of Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-for-payment-files-generation"></a><span data-ttu-id="3ee77-278">Tester le format personnalisé pour la génération des fichiers de paiement</span><span class="sxs-lookup"><span data-stu-id="3ee77-278">Test the customized format for payment files generation</span></span>
<span data-ttu-id="3ee77-279">Suivez les étapes de la procédure « Utiliser le format créé pour générer des documents électroniques de paiement » dans une session parallèle de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3ee77-279">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in parallel Finance and Operations session.</span></span> <span data-ttu-id="3ee77-280">Sélectionnez le format BACS (nom personnalisé fictif britannique) créé dans les paramètres de mode de paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="3ee77-280">Select the created 'BACS (UK fictitious custom)' format in electronic payment method parameters.</span></span> <span data-ttu-id="3ee77-281">Vérifiez que le fichier de paiement créé contient le nœud XML introduit récemment par Proseware, Inc. présentant le code de compte IBAN conformément aux besoins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3ee77-281">Make sure that the created payment file contains recently introduced by Proseware, Inc. XML node presenting IBAN account code in accordance to regional requirements.</span></span> <span data-ttu-id="3ee77-282">Le fichier doit également contenir le nœud de XML récemment introduit par Litware, Inc. présentant le code de banque SWIFT dans l’accord aux besoins de pays.</span><span class="sxs-lookup"><span data-stu-id="3ee77-282">The file also should contain the recently introduced by Litware, Inc. XML node presenting SWIFT bank code in accordance to country requirements.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]