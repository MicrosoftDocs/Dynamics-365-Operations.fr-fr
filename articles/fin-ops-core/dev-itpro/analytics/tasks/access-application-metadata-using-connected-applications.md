---
title: Accéder aux métadonnées d’application à l’aide des applications connectées
description: Les étapes de cette rubrique expliquent comment un utilisateur du service RCS (Regulatory Configuration Service) peut créer une mise en correspondance de modèle de génération d’états électroniques à l’aide des métadonnées.
author: NickSelin
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0b113f0db1d44dc5fbda30e10d62ff939550f299
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748691"
---
# <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="5d310-103">Accéder aux métadonnées d’application à l’aide des applications connectées</span><span class="sxs-lookup"><span data-stu-id="5d310-103">Access application metadata by using connected applications</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5d310-104">Les étapes suivantes expliquent comment un utilisateur du service RCS (Regulatory Configuration Service) ayant le rôle d’administrateur système ou de développeur d’états électroniques peut créer une mise en correspondance de modèle de génération d’états électronique (ER) en utilisant les métadonnées de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5d310-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using metadata in Finance and Operations.</span></span> <span data-ttu-id="5d310-105">Les métadonnées d’application ne sons accessibles en ligne qu’à l’aide de l’application RCS connectée.</span><span class="sxs-lookup"><span data-stu-id="5d310-105">Application metadata will be accessed online by using the RCS connected application.</span></span> <span data-ttu-id="5d310-106">L’exemple de mise en correspondance de modèle ER est configuré pour accéder à des transactions de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="5d310-106">Sample ER model mapping will be configured to access foreign trade transactions.</span></span> <span data-ttu-id="5d310-107">Pour effectuer ces étapes, dans RCS vous devez commencer par effectuer les étapes de cette rubrique, [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="5d310-107">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="5d310-108">Si vous n’avez pas réalisé les étapes de la rubrique [Accéder aux métadonnées d’application à l’aide de la configuration de la gestion des états électroniques](access-application-metadata-er-configuration.md), ouvrez la [Page d’exemples de génération d’états électroniques](https://go.microsoft.com/fwlink/?linkid=862266) pour télécharger et enregistrer les configurations ER suivantes : Foreign trade metadata.xml ; Foreign trade model.xml ; Foreign trade mapping.xml ; puis exécutez les étapes de la procédure.</span><span class="sxs-lookup"><span data-stu-id="5d310-108">If you have not completed the steps in the topic, [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md), go to the [Electronic reporting examples page](https://go.microsoft.com/fwlink/?linkid=862266) to download and save the following ER configurations: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, and then complete the steps in the procedure.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d310-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="5d310-109">Prerequisites</span></span>
1. <span data-ttu-id="5d310-110">Accédez à **Tous les espaces de travail** > **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="5d310-110">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="5d310-111">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="5d310-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="5d310-112">Si ce fournisseur de configuration ne s’affiche pas, effectuez les étapes de la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="5d310-112">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="get-required-er-configurations"></a><span data-ttu-id="5d310-113">Obtenir les configurations ER requises</span><span class="sxs-lookup"><span data-stu-id="5d310-113">Get required ER configurations</span></span>
1. <span data-ttu-id="5d310-114">Cliquez sur **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="5d310-114">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="5d310-115">Si vous avez déjà réalisé les étapes de la procédure [Accéder aux métadonnées d’application à l’aide de la configuration de la gestion des états électroniques](access-application-metadata-er-configuration.md), vous disposez déjà de toutes les configurations ER nécessaires (métadonnées de commerce extérieur, configurations de modèle et de mise en correspondance) dans l’instance RCS actuelle.</span><span class="sxs-lookup"><span data-stu-id="5d310-115">If you already completed the steps in the [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md) procedure, you already have all necessary ER configurations (foreign trade metadata, model and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="5d310-116">Vous pouvez ignorer toutes les étapes restantes de cette sous-tâche.</span><span class="sxs-lookup"><span data-stu-id="5d310-116">You can skip all the remaining steps of this sub-task.</span></span> 
3. <span data-ttu-id="5d310-117">Cliquez sur **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="5d310-117">Click **Exchange**.</span></span> 
4. <span data-ttu-id="5d310-118">Cliquez sur **Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="5d310-118">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="5d310-119">Cliquez sur **Parcourir** et sélectionnez le fichier **Foreign trade metadata.xml**.</span><span class="sxs-lookup"><span data-stu-id="5d310-119">Click **Browse** and select the **Foreign trade metadata.xml** file.</span></span> 
6. <span data-ttu-id="5d310-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d310-120">Click **OK**.</span></span> 
7. <span data-ttu-id="5d310-121">Cliquez sur **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="5d310-121">Click **Exchange**.</span></span> 
8. <span data-ttu-id="5d310-122">Cliquez sur **Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="5d310-122">Click **Load from XML file**.</span></span> 
9. <span data-ttu-id="5d310-123">Cliquez sur **Parcourir** et sélectionnez le fichier **Foreign trade model.xml**.</span><span class="sxs-lookup"><span data-stu-id="5d310-123">Click **Browse** and select the **Foreign trade model.xml** file.</span></span> 
10. <span data-ttu-id="5d310-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d310-124">Click **OK**.</span></span> 
11. <span data-ttu-id="5d310-125">Cliquez sur **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="5d310-125">Click **Exchange**.</span></span> 
12. <span data-ttu-id="5d310-126">Cliquez sur **Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="5d310-126">Click **Load from XML file**.</span></span> 
13. <span data-ttu-id="5d310-127">Cliquez sur **Parcourir** et sélectionnez le fichier **Foreign trade mapping.xml**.</span><span class="sxs-lookup"><span data-stu-id="5d310-127">Click **Browse** and select the **Foreign trade mapping.xml** file.</span></span> 
14. <span data-ttu-id="5d310-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d310-128">Click **OK**.</span></span> 

## <a name="register-a-connected-application"></a><span data-ttu-id="5d310-129">Inscrire une application connectée</span><span class="sxs-lookup"><span data-stu-id="5d310-129">Register a connected application</span></span>
1. <span data-ttu-id="5d310-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5d310-130">Close the page.</span></span> 
2. <span data-ttu-id="5d310-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5d310-131">Close the page.</span></span> 
3. <span data-ttu-id="5d310-132">Accédez à **Tous les espaces de travail** > **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="5d310-132">Go to **All workspaces** > **Electronic reporting**.</span></span> 
4. <span data-ttu-id="5d310-133">Cliquez sur **Applications connectées**.</span><span class="sxs-lookup"><span data-stu-id="5d310-133">Click **Connected applications**.</span></span> 
5. <span data-ttu-id="5d310-134">Assurez-vous que l’application configurée est basée sur Azure et est accessible à l’utilisateur RCS actuel.</span><span class="sxs-lookup"><span data-stu-id="5d310-134">Make sure that the configured application is Azure based and accessible for the current RCS user.</span></span> <span data-ttu-id="5d310-135">Il est également nécessaire que l’utilisateur RCS actuel ait accès à l’application sélectionnée et ait été enregistré comme utilisateur de cette application avec un rôle lui accordant les privilèges d’accès aux métadonnées de l’application.</span><span class="sxs-lookup"><span data-stu-id="5d310-135">It is also required that the current RCS user has access to the selected application and has been registered as a user of this application playing a role giving them privileges to access application's metadata.</span></span> 
6. <span data-ttu-id="5d310-136">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5d310-136">Click **New**.</span></span> 
7. <span data-ttu-id="5d310-137">Dans le champ **Nom**, tapez ’MyConnectedApp’.</span><span class="sxs-lookup"><span data-stu-id="5d310-137">In the **Name** field, type 'MyConnectedApp'.</span></span> 
8. <span data-ttu-id="5d310-138">Dans le champ **Application**, tapez « https:// mycompany.operations.dynamics.com. »</span><span class="sxs-lookup"><span data-stu-id="5d310-138">In the **Application** field, type 'https:// mycompany.operations.dynamics.com'.</span></span> 
9. <span data-ttu-id="5d310-139">Dans le champ **Locataire**, tapez « mycompany.onmicrosoft.com ».</span><span class="sxs-lookup"><span data-stu-id="5d310-139">In the **Tenant** field, type 'mycompany.onmicrosoft.com'.</span></span> 
10. <span data-ttu-id="5d310-140">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5d310-140">Click **Save**.</span></span> 
11. <span data-ttu-id="5d310-141">Lorsque vous vérifiez la connexion à l’application configurée, dans la page **Se connecter à l’application distante** cliquez sur le lien **Cliquer ici pour vous connecter à l’application distante sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="5d310-141">When you check connection to configured application, on the **Connect to remote application** page click **Click here to connect to selected remote application** link.</span></span> 
12. <span data-ttu-id="5d310-142">Cliquez sur **Vérifier la connexion**.</span><span class="sxs-lookup"><span data-stu-id="5d310-142">Click **Check connection**.</span></span> 
13. <span data-ttu-id="5d310-143">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="5d310-143">Click **Close**.</span></span> 
14. <span data-ttu-id="5d310-144">Lorsque le contrôle de connexion a réussi, les détails de la version et du client sont mis à jour pour l’application configurée dans la grille actuelle.</span><span class="sxs-lookup"><span data-stu-id="5d310-144">When the connection validation succeeded, version and tenant details will be updated for the configured application in the current grid.</span></span> 

## <a name="review-existing-model-mapping-configuration"></a><span data-ttu-id="5d310-145">Examiner une configuration de mise en correspondance de modèle existante</span><span class="sxs-lookup"><span data-stu-id="5d310-145">Review existing model mapping configuration</span></span>
1. <span data-ttu-id="5d310-146">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5d310-146">Close the page.</span></span> 
2. <span data-ttu-id="5d310-147">Cliquez sur **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="5d310-147">Click **Reporting configurations**.</span></span> 
3. <span data-ttu-id="5d310-148">Dans l’arborescence , développez **Modèle de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="5d310-148">In the tree, expand **Foreign trade model**.</span></span> 
4. <span data-ttu-id="5d310-149">Dans l’arborescence, sélectionnez **Modèle de commerce extérieur\Mise en correspondance de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="5d310-149">In the tree, select **Foreign trade model\Foreign trade mapping**.</span></span> 
5. <span data-ttu-id="5d310-150">Développez la section **Conditions préalables**.</span><span class="sxs-lookup"><span data-stu-id="5d310-150">Expand the **Prerequisites** section.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5d310-151">Actuellement, cette mise en correspondance fait référence à la configuration de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="5d310-151">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="5d310-152">Les métadonnées d’application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue.</span><span class="sxs-lookup"><span data-stu-id="5d310-152">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

6. <span data-ttu-id="5d310-153">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="5d310-153">Click **Designer**.</span></span> 
7. <span data-ttu-id="5d310-154">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="5d310-154">Click **Designer**.</span></span> 
8. <span data-ttu-id="5d310-155">Dans l’arborescence, sélectionnez **Dynamics 365 for Operations\Enregistrements de table**.</span><span class="sxs-lookup"><span data-stu-id="5d310-155">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
9. <span data-ttu-id="5d310-156">Cliquez sur **Ajouter racine**.</span><span class="sxs-lookup"><span data-stu-id="5d310-156">Click **Add root**.</span></span> 
10. <span data-ttu-id="5d310-157">Dans le champ **Table**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d310-157">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5d310-158">Actuellement, cette mise en correspondance fait référence à la configuration de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="5d310-158">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="5d310-159">Les métadonnées d’application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue.</span><span class="sxs-lookup"><span data-stu-id="5d310-159">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

11. <span data-ttu-id="5d310-160">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="5d310-160">Click **Cancel**.</span></span> 
12. <span data-ttu-id="5d310-161">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5d310-161">Close the page.</span></span> 
13. <span data-ttu-id="5d310-162">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5d310-162">Close the page.</span></span> 

## <a name="assign-connected-application-to-model-mapping"></a><span data-ttu-id="5d310-163">Affecter l’application connectée à la mise en correspondance de modèle</span><span class="sxs-lookup"><span data-stu-id="5d310-163">Assign connected application to model mapping</span></span> 
1. <span data-ttu-id="5d310-164">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="5d310-164">Click **Edit**.</span></span> 
2. <span data-ttu-id="5d310-165">Sélectionnez l’application **MyConnectedApp**.</span><span class="sxs-lookup"><span data-stu-id="5d310-165">Select **MyConnectedApp** application.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5d310-166">Actuellement, cette mise en correspondance fait référence aux métadonnées de l’application connectée sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5d310-166">Currently, this mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="5d310-167">Lorsque la même mise en correspondance fait référence à la configuration des métadonnées et à l’application connectée en même temps, les métadonnées de l’application connectée sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="5d310-167">When the same mapping refers to metadata configuration and connected application at the same time, metadata of the connected application will be used.</span></span> 

3. <span data-ttu-id="5d310-168">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="5d310-168">Click **Designer**.</span></span> 
4. <span data-ttu-id="5d310-169">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="5d310-169">Click **Designer**.</span></span> 
5. <span data-ttu-id="5d310-170">Dans l’arborescence, sélectionnez **Dynamics 365 for Operations\Enregistrements de table**.</span><span class="sxs-lookup"><span data-stu-id="5d310-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
6. <span data-ttu-id="5d310-171">Cliquez sur **Ajouter racine**.</span><span class="sxs-lookup"><span data-stu-id="5d310-171">Click **Add root**.</span></span> 
7. <span data-ttu-id="5d310-172">Dans le champ **Table**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5d310-172">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5d310-173">Plus de deux tables d’application sont présentées actuellement, car cette mise en correspondance utilise toutes les métadonnées de l’application connectée qui lui a été affectée.</span><span class="sxs-lookup"><span data-stu-id="5d310-173">More than two application tables were offered now as this mapping uses all the metadata of the connected application that has been assigned for it.</span></span> 

8. <span data-ttu-id="5d310-174">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="5d310-174">Click **Cancel**.</span></span> 
9. <span data-ttu-id="5d310-175">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5d310-175">Click **Validate**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5d310-176">Nous avons lié avec succès les éléments de modèle de données avec les éléments des sources de données qui sont décrits à l’aide des informations des métadonnées de l’application connectée qui a été affectée à cette mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="5d310-176">We successfully bound elements of data model with items of data sources that are described by using details of metadata of the connected application that has been assigned for this mapping.</span></span> 

10. <span data-ttu-id="5d310-177">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5d310-177">Close the page.</span></span> 
11. <span data-ttu-id="5d310-178">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5d310-178">Close the page.</span></span> 

<span data-ttu-id="5d310-179">Lorsque vous devez évaluer cette mise en correspondance de modèle à l’aide de métadonnées d’une application d’une version différente, enregistrez une autre application connectée, affectez-la à cette mise en correspondance de modèle et validez-la par rapport aux nouvelles métadonnées.</span><span class="sxs-lookup"><span data-stu-id="5d310-179">When you need to evaluate this model mapping by using metadata of a different version application, register another connected application, assign it to this model mapping and validate it against new metadata.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]