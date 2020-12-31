---
title: Accéder aux métadonnées d’application à l’aide de la configuration de la gestion des états électroniques
description: Les étapes de cette rubrique expliquent comment un utilisateur du service RCS (Regulatory Configuration Service) peut créer une mise en correspondance de modèle de génération d’états électroniques (ER) à l’aide des métadonnées de Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fa8e9ac4940bbc1252819ebcc3de2e21c9e0933f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682163"
---
# <a name="access-application-metadata-by-using-er-configuration"></a><span data-ttu-id="ad29e-103">Accéder aux métadonnées d’application à l’aide de la configuration de la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="ad29e-103">Access application metadata by using ER configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ad29e-104">Les étapes suivantes expliquent comment un utilisateur du service RCS (Regulatory Configuration Service) ayant le rôle d’administrateur système ou de développeur d’états électroniques peut créer une mise en correspondance de modèle de génération d’états électronique (ER) en utilisant les métadonnées de l’application.</span><span class="sxs-lookup"><span data-stu-id="ad29e-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using the application metadata.</span></span> <span data-ttu-id="ad29e-105">Les métadonnées d’application sont accessibles à l’aide d’une configuration de métadonnées ER contenant un échantillon de métadonnées pour accéder aux transactions de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="ad29e-105">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span> <span data-ttu-id="ad29e-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de cette rubrique dans RCS, [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="ad29e-106">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> <span data-ttu-id="ad29e-107">Ensuite, suivez les étapes de la rubrique [Préparer les métadonnées d’application à utiliser dans RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="ad29e-107">Then complete the steps in the topic, [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ad29e-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="ad29e-108">Prerequisites</span></span>
1. <span data-ttu-id="ad29e-109">Accédez à **Tous les espaces de travail** > **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-109">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="ad29e-110">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="ad29e-111">Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="ad29e-111">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="import-metadata-configuration"></a><span data-ttu-id="ad29e-112">Importer la configuration des métadonnées</span><span class="sxs-lookup"><span data-stu-id="ad29e-112">Import metadata configuration</span></span> 
1. <span data-ttu-id="ad29e-113">Cliquez sur **Configuration des métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-113">Click **Metadata configurations**.</span></span> 
2. <span data-ttu-id="ad29e-114">Importez la configuration de métadonnées ER contenant des métadonnées configurées pour générer des documents électroniques pour le commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="ad29e-114">Import the ER metadata configuration that contains metadata that has been configured to generate electronic documents for foreign trade business.</span></span> <span data-ttu-id="ad29e-115">Cette configuration de métadonnées ER a été exportées en tant que fichier XML lors des étapes de la procédure [Préparer les métadonnées d’application à utiliser dans RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="ad29e-115">This ER metadata configuration has been exported as XML file while the steps in the [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md) procedure have been completed.</span></span> 
3. <span data-ttu-id="ad29e-116">Cliquez sur **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-116">Click **Exchange**.</span></span> 
4. <span data-ttu-id="ad29e-117">Cliquez sur **Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-117">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="ad29e-118">Cliquez sur **Parcourir** et sélectionnez le fichier « Foreign trade metadata.xml ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-118">Click **Browse** and select the 'Foreign trade metadata.xml' file.</span></span> 
6. <span data-ttu-id="ad29e-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-119">Click **OK**.</span></span> 
7. <span data-ttu-id="ad29e-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ad29e-120">Close the page.</span></span> 

## <a name="create-data-model-configuration"></a><span data-ttu-id="ad29e-121">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="ad29e-121">Create data model configuration</span></span>
1. <span data-ttu-id="ad29e-122">Cliquez sur **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-122">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="ad29e-123">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ad29e-123">Click **Create configuration** to open the drop dialog.</span></span> 
3. <span data-ttu-id="ad29e-124">Dans le champ **Nom**, tapez « Modèle commerce extérieur ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-124">In the **Name** field, type 'Foreign trade model'.</span></span> 
4. <span data-ttu-id="ad29e-125">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-125">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="ad29e-126">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-126">Click **Designer**.</span></span> 
6. <span data-ttu-id="ad29e-127">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ad29e-127">Click **New** to open the drop dialog.</span></span> 
7. <span data-ttu-id="ad29e-128">Dans le champ **Nom**, tapez « Racine ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-128">In the **Name** field, type 'Root'.</span></span> 
8. <span data-ttu-id="ad29e-129">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-129">Click **Add**.</span></span> 
9. <span data-ttu-id="ad29e-130">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ad29e-130">Click **New** to open the drop dialog.</span></span> 
10.    <span data-ttu-id="ad29e-131">Dans le champ **Nom**, tapez « Transaction ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-131">In the **Name** field, type 'Transaction'.</span></span> 
11.    <span data-ttu-id="ad29e-132">Dans le champ **Type d’article**, sélectionnez **Liste d’enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-132">In the **Item type** field, select **Record list**.</span></span> 
12.    <span data-ttu-id="ad29e-133">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-133">Click **Add**.</span></span> 
13.    <span data-ttu-id="ad29e-134">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ad29e-134">Click **New** to open the drop dialog.</span></span> 
14.    <span data-ttu-id="ad29e-135">Dans le champ **Nom**, tapez « Code marchandise ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-135">In the **Name** field, type 'Commodity code'.</span></span> 
15.    <span data-ttu-id="ad29e-136">Dans le champ **Type d’article**, sélectionnez **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-136">In the **Item type** field, select **String**.</span></span> 
16.    <span data-ttu-id="ad29e-137">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-137">Click **Add**.</span></span> 
17.    <span data-ttu-id="ad29e-138">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ad29e-138">Click **New** to open the drop dialog.</span></span> 
18.    <span data-ttu-id="ad29e-139">Dans le champ **Nom**, tapez « Montant facture »</span><span class="sxs-lookup"><span data-stu-id="ad29e-139">In the **Name** field, type 'Invoiced amount'.</span></span> 
19.    <span data-ttu-id="ad29e-140">Dans le champ **Type d’article**, sélectionnez **Réel**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-140">In the **Item type** field, select **Real**.</span></span> 
20.    <span data-ttu-id="ad29e-141">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-141">Click **Add**.</span></span> 
21.    <span data-ttu-id="ad29e-142">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ad29e-142">Click **New** to open the drop dialog.</span></span> 
22.    <span data-ttu-id="ad29e-143">Dans le champ **Nom**, tapez « Date ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-143">In the **Name** field, type 'Date'.</span></span> 
23.    <span data-ttu-id="ad29e-144">Dans le champ **Type d’article**, sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-144">In the **Item type** field, select **Date**.</span></span> 
24.    <span data-ttu-id="ad29e-145">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-145">Click **Add**.</span></span> 
25.    <span data-ttu-id="ad29e-146">Cliquez sur **Référence racine**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-146">Click **Root reference**.</span></span> 
26.    <span data-ttu-id="ad29e-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-147">Click **OK**.</span></span> 
27.    <span data-ttu-id="ad29e-148">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-148">Click **Save**.</span></span> 
28.    <span data-ttu-id="ad29e-149">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ad29e-149">Close the page.</span></span> 
29.    <span data-ttu-id="ad29e-150">Cliquez sur **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-150">Click **Change status**.</span></span> 
30.    <span data-ttu-id="ad29e-151">Cliquez sur **Terminé.**</span><span class="sxs-lookup"><span data-stu-id="ad29e-151">Click **Complete**.</span></span> 
31.    <span data-ttu-id="ad29e-152">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-152">Click **OK**.</span></span> 

## <a name="create-model-mapping-configuration"></a><span data-ttu-id="ad29e-153">Créer une configuration de mise en correspondance de modèle</span><span class="sxs-lookup"><span data-stu-id="ad29e-153">Create model mapping configuration</span></span> 
1. <span data-ttu-id="ad29e-154">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ad29e-154">Click **Create configuration** to open the drop dialog.</span></span> 
2. <span data-ttu-id="ad29e-155">Dans le champ **Nouveau**, entrez « Mise en correspondance de modèle basée sur le modèle de commerce extérieur ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-155">In the **New** field, enter 'Model Mapping based on data model Foreign trade model'.</span></span> 
3. <span data-ttu-id="ad29e-156">Dans le champ **Nom**, tapez « Mise en correspondance de commerce extérieur ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-156">In the **Name** field, type 'Foreign trade mapping'.</span></span> 
4. <span data-ttu-id="ad29e-157">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-157">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="ad29e-158">Développez la section **Conditions préalables**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-158">Expand the **Prerequisites** section.</span></span> 
6. <span data-ttu-id="ad29e-159">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-159">Click **Edit**.</span></span> 
7. <span data-ttu-id="ad29e-160">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-160">Click **New**.</span></span> 
8. <span data-ttu-id="ad29e-161">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ad29e-161">In the list, mark the selected row.</span></span> 
9. <span data-ttu-id="ad29e-162">Dans le champ **Type nécessaire de composant**, sélectionnez **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-162">In the **Prerequisite component type** field, select **Configuration**.</span></span> 
10.    <span data-ttu-id="ad29e-163">Sélectionnez la configuration **Métadonnées de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-163">Select **Foreign trade metadata** configuration.</span></span> 
11.    <span data-ttu-id="ad29e-164">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-164">Click **Save**.</span></span> 
12.    <span data-ttu-id="ad29e-165">Nous avons ajouté la référence à la version 1 de la configuration « Métadonnées de commerce extérieur ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-165">We added the reference to the version 1 of the 'Foreign trade metadata' configuration.</span></span> <span data-ttu-id="ad29e-166">Les métadonnées d’application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue.</span><span class="sxs-lookup"><span data-stu-id="ad29e-166">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 
13.    <span data-ttu-id="ad29e-167">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ad29e-167">Close the page.</span></span> 
14.    <span data-ttu-id="ad29e-168">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-168">Click **Designer**.</span></span> 
15.    <span data-ttu-id="ad29e-169">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-169">Click **Designer**.</span></span> 
16.    <span data-ttu-id="ad29e-170">Dans l’arborescence, sélectionnez **Dynamics 365 for Operations\Enregistrements de table**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
17.    <span data-ttu-id="ad29e-171">Cliquez sur **Ajouter racine**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-171">Click **Add root**.</span></span> 
18.    <span data-ttu-id="ad29e-172">Dans le champ **Nom**, tapez « Déclaration d’échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="ad29e-172">In the **Name** field, type 'Intrastat'.</span></span> 
19.    <span data-ttu-id="ad29e-173">Sélectionnez les enregistrements de table **Déclaration d’échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-173">Select **Intrastat** table records.</span></span> 
20.    <span data-ttu-id="ad29e-174">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-174">Click **OK**.</span></span> 

> [!NOTE]
> <span data-ttu-id="ad29e-175">Seules 2 tables sont proposées car ces seules 2 tables ont été ajoutées à l’ensemble de métadonnées en cours de utilisation.</span><span class="sxs-lookup"><span data-stu-id="ad29e-175">The only 2 tables were offered as the only 2 tables were added into the set of metadata which is currently in use.</span></span> 

21.    <span data-ttu-id="ad29e-176">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-176">Click **Bind**.</span></span> 
22.    <span data-ttu-id="ad29e-177">Dans l’arborescence, développez **Déclaration d’échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-177">In the tree, expand **Intrastat**.</span></span> 
23.    <span data-ttu-id="ad29e-178">Dans l’arborescence, sélectionnez **Déclaration d’échanges de biens\AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-178">In the tree, select **Intrastat\AmountMST**.</span></span> 
24.    <span data-ttu-id="ad29e-179">Dans l’arborescence, développez **Transaction = Déclaration d’échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-179">In the tree, expand **Transaction = Intrastat**.</span></span> 
25.    <span data-ttu-id="ad29e-180">Dans l’arborescence, sélectionnez **Transaction = Déclaration d’échanges de biens\Montant facturé**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-180">In the tree, select **Transaction = Intrastat\Invoiced amount**.</span></span> 
26.    <span data-ttu-id="ad29e-181">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-181">Click **Bind**.</span></span> 
27.    <span data-ttu-id="ad29e-182">Dans l’arborescence, sélectionnez **Déclaration d’échanges de biens\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-182">In the tree, select **Intrastat\TransDate**.</span></span> 
28.    <span data-ttu-id="ad29e-183">Dans l’arborescence, sélectionnez **Transaction = Déclaration d’échanges de biens\Date**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-183">In the tree, select **Transaction = Intrastat\Date**.</span></span> 
29.    <span data-ttu-id="ad29e-184">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-184">Click **Bind**.</span></span> 
30.    <span data-ttu-id="ad29e-185">Dans l’arborescence, développez **Déclaration d’échanges de biens\>Relations**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-185">In the tree, expand **Intrastat\>Relations**.</span></span> 
31.    <span data-ttu-id="ad29e-186">Dans l’arborescence, développez **Déclaration d’échanges de biens\>Relations\IntrastatCommodity**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-186">In the tree, expand **Intrastat\>Relations\IntrastatCommodity**.</span></span> 
32.    <span data-ttu-id="ad29e-187">Dans l’arborescence, développez **Déclaration d’échanges de biens\>Relations\IntrastatCommodity\Code**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-187">In the tree, select **Intrastat\>Relations\IntrastatCommodity\Code**.</span></span> 
33.    <span data-ttu-id="ad29e-188">Dans l’arborescence, sélectionnez **Transaction = Déclaration d’échanges de biens\Code marchandise**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-188">In the tree, select **Transaction = Intrastat\Commodity code**.</span></span> 
34.    <span data-ttu-id="ad29e-189">Cliquez sur **Lier**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-189">Click **Bind**.</span></span> 
35.    <span data-ttu-id="ad29e-190">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-190">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="ad29e-191">Nous avons lié avec succès les éléments de modèle de données avec les éléments des sources de données qui sont décrits à l’aide des informations des métadonnées de l’application issues de la configuration de métadonnées ER associée.</span><span class="sxs-lookup"><span data-stu-id="ad29e-191">We have successfully bound elements of data model with items of data sources that are described by using details of application metadata from the referred ER metadata configuration.</span></span> 
36.    <span data-ttu-id="ad29e-192">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-192">Click **Save**.</span></span> 
37.    <span data-ttu-id="ad29e-193">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ad29e-193">Close the page.</span></span> 
38.    <span data-ttu-id="ad29e-194">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ad29e-194">Close the page.</span></span> 
39.    <span data-ttu-id="ad29e-195">Le cas échéant, vous pouvez étendre l’ensemble existant de métadonnées, puis exporter la nouvelle version terminée de la configuration de métadonnées ER.</span><span class="sxs-lookup"><span data-stu-id="ad29e-195">When needed, you can extend the existing set of metadata and then export the new completed version of ER metadata configuration.</span></span> <span data-ttu-id="ad29e-196">Vous pouvez ensuite l’importer dans RCS et mettre à jour les conditions préalables et la configuration de mise en correspondance du modèle configuré se référant à une nouvelle version de la configuration des métadonnées importée.</span><span class="sxs-lookup"><span data-stu-id="ad29e-196">You can then import it to RCS, and update the prerequisites of the configured model mapping configuration referring to a new version of imported metadata configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="ad29e-197">Cette manière d’obtenir des informations sur les métadonnées d’application est la seule disponible pour les applications déployées localement (lorsqu’un modèle de déploiement de données métier local (LBD) ou sur site est utilisé).</span><span class="sxs-lookup"><span data-stu-id="ad29e-197">This way of getting information about application metadata is the only one available for locally deployed applications (when local business data (LBD), or on-premises, deployment model is used).</span></span>
        
