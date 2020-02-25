---
title: ER Mapper des composants au format créé à des éléments de modèle de données (novembre 2016)
description: La procédure suivante explique comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut mettre en correspondance des éléments de modèle de données aux composants de la configuration de la gestion des états électroniques, qui définit un format de document électronique pour le domaine de paiements de l'entreprise.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 548f16034ebdf7e0f29e8e89d85aac880f6323a1
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026238"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a><span data-ttu-id="dc9b3-103">ER Mapper des composants au format créé à des éléments de modèle de données (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="dc9b3-103">ER Map components of the created format to data model elements (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dc9b3-104">La procédure suivante explique comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut mettre en correspondance des éléments de modèle de données aux composants de la configuration de la gestion des états électroniques, qui définit un format de document électronique pour le domaine de paiements de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-104">The following procedure shows how a user in either the System administrator or Electronic reporting developer role can map data model elements to components of the created Electronic reporting (ER) configuration, which defines an electronic document format for the payments business domain.</span></span> <span data-ttu-id="dc9b3-105">Ce format sera utilisé ultérieurement pour générer des documents électroniques pour traiter les paiements.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-105">This format will be used later to generate electronic documents for processing payments.</span></span> <span data-ttu-id="dc9b3-106">Dans cet exemple, vous créerez une configuration de format pour la société fictive, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-106">In this example, you will create a format configuration for the sample company, ‘Litware, Inc.’.</span></span> <span data-ttu-id="dc9b3-107">Ces étapes peuvent être effectuées dans n'importe quelle société car les fournisseurs de configurations ER sont partagés pour toutes les sociétés.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-107">These steps can be performed in any company as ER configurations are shared for all companies.</span></span> <span data-ttu-id="dc9b3-108">Pour mener à bien ces étapes, vous devez d'abord effectuer les étapes du Guide de tâche « Créer une configuration de format ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-108">To complete these steps, you must first complete the steps in the “Create a format configuration” task guide.</span></span>


## <a name="select-a-format-configuration"></a><span data-ttu-id="dc9b3-109">Sélectionner une configuration de format</span><span class="sxs-lookup"><span data-stu-id="dc9b3-109">Select a format configuration</span></span>
1. <span data-ttu-id="dc9b3-110">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="dc9b3-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="dc9b3-112">Dans l'arborescence, développez « Paiements (modèle simplifié) ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-112">In the tree, expand 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="dc9b3-113">Dans l'arborescence, sélectionnez « Paiements (modèle simplifié) »\BACS (nom fictif britannique) ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-113">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
5. <span data-ttu-id="dc9b3-114">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-114">Click Designer.</span></span>

## <a name="map-format-components-to-data-model-elements"></a><span data-ttu-id="dc9b3-115">Mettre en correspondance des composants de format aux éléments de modèle de données</span><span class="sxs-lookup"><span data-stu-id="dc9b3-115">Map format components to data model elements</span></span>
1. <span data-ttu-id="dc9b3-116">Cliquez sur Développer/réduire.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-116">Click Expand/collapse.</span></span>
2. <span data-ttu-id="dc9b3-117">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-117">Click the Mapping tab.</span></span>
3. <span data-ttu-id="dc9b3-118">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-118">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="dc9b3-119">Dans l'arborescence, sélectionnez « Xml\Message\ProcessingDate\DateTime ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-119">In the tree, select 'Xml\Message\ProcessingDate\DateTime'.</span></span>
5. <span data-ttu-id="dc9b3-120">Dans l'arborescence, sélectionnez « modèle\ProcessingDateTime »</span><span class="sxs-lookup"><span data-stu-id="dc9b3-120">In the tree, select 'model\ProcessingDateTime'.</span></span>
6. <span data-ttu-id="dc9b3-121">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-121">Click Bind.</span></span>
7. <span data-ttu-id="dc9b3-122">Dans l'arborescence, sélectionnez « Xml\Message\MessageId\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-122">In the tree, select 'Xml\Message\MessageId\String'.</span></span>
8. <span data-ttu-id="dc9b3-123">Dans l'arborescence, sélectionnez « modèle\MessageIdentification ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-123">In the tree, select 'model\MessageIdentification'.</span></span>
9. <span data-ttu-id="dc9b3-124">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-124">Click Bind.</span></span>
10. <span data-ttu-id="dc9b3-125">Dans l'arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-125">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="dc9b3-126">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Montant\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-126">In the tree, select 'Xml\Message\Payments\Item\Amount\String'.</span></span>
12. <span data-ttu-id="dc9b3-127">Dans l'arborescence, sélectionnez « modèle\Paiements\InstructedAmount ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-127">In the tree, select 'model\Payments\InstructedAmount'.</span></span>
13. <span data-ttu-id="dc9b3-128">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-128">Click Bind.</span></span>
14. <span data-ttu-id="dc9b3-129">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\TransDate\DateTime ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-129">In the tree, select 'Xml\Message\Payments\Item\TransDate\DateTime'.</span></span>
15. <span data-ttu-id="dc9b3-130">Dans l'arborescence, sélectionnez « modèle\Paiements\TransactionDate ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-130">In the tree, select 'model\Payments\TransactionDate'.</span></span>
16. <span data-ttu-id="dc9b3-131">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-131">Click Bind.</span></span>
17. <span data-ttu-id="dc9b3-132">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Description\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-132">In the tree, select 'Xml\Message\Payments\Item\Description\String'.</span></span>
18. <span data-ttu-id="dc9b3-133">Dans l'arborescence, sélectionnez « modèle\Paiements\Description ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-133">In the tree, select 'model\Payments\Description'.</span></span>
19. <span data-ttu-id="dc9b3-134">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-134">Click Bind.</span></span>
20. <span data-ttu-id="dc9b3-135">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Devise\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-135">In the tree, select 'Xml\Message\Payments\Item\Currency\String'.</span></span>
21. <span data-ttu-id="dc9b3-136">Dans l'arborescence, sélectionnez modèle\Paiements\Devise.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-136">In the tree, select 'model\Payments\Currency'.</span></span>
22. <span data-ttu-id="dc9b3-137">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-137">Click Bind.</span></span>
23. <span data-ttu-id="dc9b3-138">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\ID ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-138">In the tree, select 'Xml\Message\Payments\Item\Id'.</span></span>
24. <span data-ttu-id="dc9b3-139">Dans l'arborescence, sélectionnez « modèle\Paiements\End2EndID ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-139">In the tree, select 'model\Payments\End2EndID'.</span></span>
25. <span data-ttu-id="dc9b3-140">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-140">Click Bind.</span></span>
26. <span data-ttu-id="dc9b3-141">Dans l'arborescence , développez « modèle\Paiements\Créditeur ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-141">In the tree, expand 'model\Payments\Creditor'.</span></span>
27. <span data-ttu-id="dc9b3-142">Dans l'arborescence , développez « modèle\Paiements\Créditeur\Compte ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-142">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
28. <span data-ttu-id="dc9b3-143">Dans l'arborescence , développez « modèle\Paiements\Créditeur\Agent ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-143">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
29. <span data-ttu-id="dc9b3-144">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Nom\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-144">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
30. <span data-ttu-id="dc9b3-145">Dans l'arborescence, sélectionnez « modèle\Paiements\Créditeur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-145">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
31. <span data-ttu-id="dc9b3-146">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-146">Click Bind.</span></span>
32. <span data-ttu-id="dc9b3-147">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\RoutingNumber\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String'.</span></span>
33. <span data-ttu-id="dc9b3-148">Dans l'arborescence, sélectionnez « Modèle\Paiements\Créditeur\Agent\RoutingNumber ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-148">In the tree, select 'model\Payments\Creditor\Agent\RoutingNumber'.</span></span>
34. <span data-ttu-id="dc9b3-149">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-149">Click Bind.</span></span>
35. <span data-ttu-id="dc9b3-150">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Fournisseur\Banque\AccountNumber\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-150">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String'.</span></span>
36. <span data-ttu-id="dc9b3-151">Dans l'arborescence, sélectionnez « modèle\Paiements\Créditeur\Compte\Numéro ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-151">In the tree, select 'model\Payments\Creditor\Account\Number'.</span></span>
37. <span data-ttu-id="dc9b3-152">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-152">Click Bind.</span></span>
38. <span data-ttu-id="dc9b3-153">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Nom\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-153">In the tree, select 'Xml\Message\Payments\Item\Payer\Name\String'.</span></span>
39. <span data-ttu-id="dc9b3-154">Dans l'arborescence , développez « modèle\Paiements\Débiteur ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-154">In the tree, expand 'model\Payments\Debtor'.</span></span>
40. <span data-ttu-id="dc9b3-155">Dans l'arborescence , développez « modèle\Paiements\Débiteur\Compte ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-155">In the tree, expand 'model\Payments\Debtor\Account'.</span></span>
41. <span data-ttu-id="dc9b3-156">Dans l'arborescence , développez « modèle\Paiements\Débiteur\Agent ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-156">In the tree, expand 'model\Payments\Debtor\Agent'.</span></span>
42. <span data-ttu-id="dc9b3-157">Dans l'arborescence, sélectionnez « modèle\Paiements\Débiteur\Nom ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-157">In the tree, select 'model\Payments\Debtor\Name'.</span></span>
43. <span data-ttu-id="dc9b3-158">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-158">Click Bind.</span></span>
44. <span data-ttu-id="dc9b3-159">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\RoutingNumber\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-159">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String'.</span></span>
45. <span data-ttu-id="dc9b3-160">Dans l'arborescence, sélectionnez « modèle\Paiements\Débiteur\Agent\RoutingNumber ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-160">In the tree, select 'model\Payments\Debtor\Agent\RoutingNumber'.</span></span>
46. <span data-ttu-id="dc9b3-161">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-161">Click Bind.</span></span>
47. <span data-ttu-id="dc9b3-162">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article\Payeur\Banque\AccountNumber\Chaîne ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-162">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String'.</span></span>
48. <span data-ttu-id="dc9b3-163">Dans l'arborescence, sélectionnez « modèle\Paiements\Débiteur\Compte\Numéro ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-163">In the tree, select 'model\Payments\Debtor\Account\Number'.</span></span>
49. <span data-ttu-id="dc9b3-164">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-164">Click Bind.</span></span>
50. <span data-ttu-id="dc9b3-165">Dans l'arborescence, sélectionnez « Xml\Message\Paiements\Article ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-165">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="dc9b3-166">Dans l'arborescence, sélectionnez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-166">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="dc9b3-167">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-167">Click Bind.</span></span>
53. <span data-ttu-id="dc9b3-168">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-168">Click Save.</span></span>

## <a name="validate-format-mapping"></a><span data-ttu-id="dc9b3-169">Valider une mise en correspondance de format</span><span class="sxs-lookup"><span data-stu-id="dc9b3-169">Validate format mapping</span></span>
1. <span data-ttu-id="dc9b3-170">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-170">Click Validate.</span></span>
    * <span data-ttu-id="dc9b3-171">Validez la nouvelle mise en correspondance pour vous assurer que toutes les liaisons sont correctes.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-171">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="dc9b3-172">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-172">Close the page.</span></span>

## <a name="change-status-of-the-current-version-of-format-configuration"></a><span data-ttu-id="dc9b3-173">Modifier le statut de la version actuelle de la configuration du format</span><span class="sxs-lookup"><span data-stu-id="dc9b3-173">Change status of the current version of format configuration</span></span>
<span data-ttu-id="dc9b3-174">Dans les étapes suivantes, vous modifierez le statut de la configuration de format de Brouillon sur Terminé pour la rendre disponible pour la génération de documents de paiement.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-174">In the next steps, you’ll change the status of the format configuration from Draft to Completed to make it available for payment document generation.</span></span>  
1. <span data-ttu-id="dc9b3-175">Cliquez sur Modifier le statut.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-175">Click Change status.</span></span>
2. <span data-ttu-id="dc9b3-176">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-176">Click Complete.</span></span>
3. <span data-ttu-id="dc9b3-177">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-177">In the Description field, type a value.</span></span>
    * <span data-ttu-id="dc9b3-178">Par exemple, « version 1 ».</span><span class="sxs-lookup"><span data-stu-id="dc9b3-178">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="dc9b3-179">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-179">Click OK.</span></span>
5. <span data-ttu-id="dc9b3-180">Sélectionnez une version terminée de la configuration actuelle.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-180">Select completed version of the current configuration.</span></span>
    * <span data-ttu-id="dc9b3-181">Notez que la configuration est enregistrée comme version terminée 1.1 : version 1 du format selon la version 1 du modèle de données.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-181">Note that the configuration is saved as completed version 1.1: version 1 of the format based on the version 1 of the data model.</span></span>  

## <a name="define-effective-date-for-completed-version-of-format"></a><span data-ttu-id="dc9b3-182">Définir la date d'effet de la version du format terminée</span><span class="sxs-lookup"><span data-stu-id="dc9b3-182">Define effective date for completed version of format</span></span>
<span data-ttu-id="dc9b3-183">Chaque version de format peut être configurée comme disponible pour l'utilisation à partir d'une certaine date.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-183">Each format version can be configured as available for usage starting from a certain date.</span></span> <span data-ttu-id="dc9b3-184">Lorsque plusieurs versions de format sont actives à une certaine date, le format le plus récent (selon le numéro de version) est activé pour l'utilisation.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-184">When more than one format version is active on a certain date, the latest format (based on version number) will be selected for usage.</span></span> <span data-ttu-id="dc9b3-185">La valeur de date de session est utilisée pour la sélection de la version appropriée.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-185">The session date value is used for proper version selection.</span></span>  

## <a name="restrict-access-to-created-format-from-companies"></a><span data-ttu-id="dc9b3-186">Limiter l'accès au format créé des sociétés</span><span class="sxs-lookup"><span data-stu-id="dc9b3-186">Restrict access to created format from companies</span></span>
1. <span data-ttu-id="dc9b3-187">Développez la section Codes pays/région ISO.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-187">Expand the ISO Country/region codes section.</span></span>
    * <span data-ttu-id="dc9b3-188">Chaque accès au format peut être limité en identifiant les pays/régions particuliers dans lesquels un format s'applique.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-188">Each format access can be restricted by identifying particular countries/regions in which a format is applicable.</span></span> <span data-ttu-id="dc9b3-189">Lorsque la liste de pays/régions pour le format spécifique est vide, ce format peut être utilisé dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-189">When the list of countries/regions for particular format is empty, this format can be used in any company.</span></span> <span data-ttu-id="dc9b3-190">Lorsque certains codes pays/région ISO sont insérés dans la liste de pays/régions, le format ne peut être utilisé que pour des sociétés pour lesquelles l'adresse principale se trouve dans le pays/la région.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-190">When some ISO country/region codes are inserted in the list of countries/regions, the format can only be use in companies if the primary address is in the country/region.</span></span>  

