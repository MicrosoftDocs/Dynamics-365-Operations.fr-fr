---
title: Préparer les métadonnées d'application à utiliser dans RCS
description: Les étapes de cette rubrique expliquent comment un utilisateur peut créer une nouvelle configuration de génération d'états électroniques (ER) contenant les métadonnées de l'application pour concevoir les configurations de mise en correspondance de modèle ER dans le service RCS (Regulatory Configuration Service).
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3a33eefca98e14ed0435f8f1a7a9f90a69498ee
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182161"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a><span data-ttu-id="56504-103">Préparer les métadonnées d'application à utiliser dans RCS</span><span class="sxs-lookup"><span data-stu-id="56504-103">Prepare application metadata to be used in RCS</span></span>
[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="56504-104">Les étapes suivantes expliquent comment un utilisateur doté du rôle Administrateur système ou Développeur d'états électroniques peut créer une nouvelle configuration de génération d'états électroniques (ER) contenant les métadonnées de l'application pour concevoir les configurations de mise en correspondance de modèle ER dans le service RCS (Regulatory Configuration Service).</span><span class="sxs-lookup"><span data-stu-id="56504-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains application metadata for designing ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="56504-105">Cette configuration sera utilisée pour concevoir un exemple de configuration de mise en correspondance de modèle ER pour accéder à des transactions de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="56504-105">This configuration will be used for designing a sample ER model mapping configuration to access foreign trade transactions.</span></span> <span data-ttu-id="56504-106">Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="56504-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company.</span></span> <span data-ttu-id="56504-107">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de cette rubrique, [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="56504-107">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56504-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="56504-108">Prerequisites</span></span>
1.  <span data-ttu-id="56504-109">Accédez à **Administration d'organisation** > **Espaces de travail** > **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="56504-109">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2.  <span data-ttu-id="56504-110">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="56504-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="56504-111">Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="56504-111">If you don’t see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3.  <span data-ttu-id="56504-112">Cliquez sur **Configuration des métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="56504-112">Click **Metadata configurations**.</span></span> 
4.  <span data-ttu-id="56504-113">Supposons que nous utilisons RCS pour créer une solution ER pour une application Finance and Operations générera des documents électroniques contenant les informations du commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="56504-113">Assume that RCS will be used to design an ER solution for a Finance and Operation application that will generate electronic documents that contain information from foreign trade business domain.</span></span> <span data-ttu-id="56504-114">Pour spécifier la mise en correspondance entre le modèle de données ER et les sources de données nécessaires, nous devons avoir accès dans RCS aux métadonnées de l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="56504-114">To specify the mapping between ER data model and sources of required data, in RCS we need to have access to metadata of the Finance and Operation application.</span></span> <span data-ttu-id="56504-115">Par conséquent, dans le cadre de la conception de la solution ER, nous devons paramétrer une nouvelle configuration de métadonnées ER contenant toutes les métadonnées actuellement requises pour générer des les états électroniques pour le domaine d'activité sélectionné.</span><span class="sxs-lookup"><span data-stu-id="56504-115">Therefore, as part of designing ER solution we configure a new ER metadata configuration containing all metadata that is currently required for generation ER reports for selected business domain.</span></span> 

## <a name="add-metadata-configuration"></a><span data-ttu-id="56504-116">Ajouter une configuration des métadonnées</span><span class="sxs-lookup"><span data-stu-id="56504-116">Add metadata configuration</span></span> 
1.  <span data-ttu-id="56504-117">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="56504-117">Click **Create configuration** to open the drop dialog.</span></span> 
2.  <span data-ttu-id="56504-118">Dans le champ **Nom**, tapez « Métadonnées du commerce extérieur ».</span><span class="sxs-lookup"><span data-stu-id="56504-118">In the **Name** field, type 'Foreign trade metadata'.</span></span> 
3.  <span data-ttu-id="56504-119">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="56504-119">Click **Create configuration**.</span></span> 
4.  <span data-ttu-id="56504-120">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="56504-120">Click **Designer**.</span></span> 
5.  <span data-ttu-id="56504-121">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="56504-121">Click **Add**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="56504-122">Vous pouvez sélectionner toutes les métadonnées pour l'application entière, ou pour des modèles ou des modules sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="56504-122">You can select all metadata for the entire application or selected models or selected modules.</span></span> <span data-ttu-id="56504-123">Notez que dans ce cas les métadonnées suivantes sont automatiquement ajoutées : tables des enregistrements, énumérations, et types de données étendus (EDT, Extended Data Types).</span><span class="sxs-lookup"><span data-stu-id="56504-123">Be aware that in this case the following metadata will be automatically added: tables of records, enumerations, and extended data types.</span></span> <span data-ttu-id="56504-124">Lorsque d'autres types de métadonnées sont requis, ils doivent être ajoutés manuellement.</span><span class="sxs-lookup"><span data-stu-id="56504-124">When additional types of metadata are needed, they must be added manually.</span></span> 
 
<span data-ttu-id="56504-125">Nous avons des métadonnées relatives aux transactions de commerce extérieur en sélectionnant manuellement les éléments de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="56504-125">We have some foreign trade transactions related metadata by selecting metadata items manually.</span></span> 
  
6.  <span data-ttu-id="56504-126">Cliquez sur **Ajouter une source de données**.</span><span class="sxs-lookup"><span data-stu-id="56504-126">Click **Add data source**.</span></span> 
7.  <span data-ttu-id="56504-127">Cliquez sur **Enregistrements de la table**.</span><span class="sxs-lookup"><span data-stu-id="56504-127">Click **Table records**.</span></span> 
8.  <span data-ttu-id="56504-128">Utilisez le filtre rapide pour filtrer sur le champ **Nom** avec une valeur « déclaration d'échanges de biens ».</span><span class="sxs-lookup"><span data-stu-id="56504-128">Use the Quick Filter to filter on the **Name** field with a value of 'Intrastat'.</span></span> 
9.  <span data-ttu-id="56504-129">Sélectionnez l'enregistrement de table **Déclaration d'échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="56504-129">Select the **Intrastat** table record.</span></span> 
10. <span data-ttu-id="56504-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="56504-130">Click **OK**.</span></span>
  
<span data-ttu-id="56504-131">Nous avons ajouté des informations de métadonnées sur la table d'enregistrements de la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="56504-131">We added metadata information about the Intrastat table of records.</span></span> 
  
11. <span data-ttu-id="56504-132">Dans l'arborescence, développez **Enregistrements de table Déclaration d'échanges de biens**\>**Relations**.</span><span class="sxs-lookup"><span data-stu-id="56504-132">In the tree, expand **Table records Intrastat**\>**Relations**.</span></span> 
12. <span data-ttu-id="56504-133">Dans l'arborescence, sélectionnez **Enregistrements de table Déclaration d'échanges de biens**\>**Relations\IntrastatCommodity (Enregistrements de table EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="56504-133">In the tree, select **Table records Intrastat**\>**Relations\IntrastatCommodity (Table records EcoResCategory)**.</span></span>   
13. <span data-ttu-id="56504-134">Cliquez sur **Ajouter des métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="56504-134">Click **Add metadata**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="56504-135">Les métadonnées sur les relations requises pour la table d'enregistrements sélectionnée doivent être ajoutées manuellement.</span><span class="sxs-lookup"><span data-stu-id="56504-135">Metadata about required relations for selected table of records must be added manually.</span></span> 
  
16. <span data-ttu-id="56504-136">Cliquez sur **Ajouter une source de données**.</span><span class="sxs-lookup"><span data-stu-id="56504-136">Click **Add data source**.</span></span> 
17. <span data-ttu-id="56504-137">Cliquez sur **Énumération**.</span><span class="sxs-lookup"><span data-stu-id="56504-137">Click **Enumeration**.</span></span> 
18. <span data-ttu-id="56504-138">Utilisez le filtre rapide pour filtrer sur le champ **Nom** avec une valeur « IntrastatDirection ».</span><span class="sxs-lookup"><span data-stu-id="56504-138">Use the Quick Filter to filter on the **Name** field with a value of 'IntrastatDirection'.</span></span> 
19. <span data-ttu-id="56504-139">Sélectionnez l'enregistrement d'énumération **IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="56504-139">Select the **IntrastatDirection enumeration** record.</span></span> 
20. <span data-ttu-id="56504-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="56504-140">Click **OK**.</span></span> 
21. <span data-ttu-id="56504-141">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="56504-141">Click **Save**.</span></span>  
22. <span data-ttu-id="56504-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="56504-142">Close the page.</span></span> 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a><span data-ttu-id="56504-143">Compléter la version temporaire de la configuration de métadonnées</span><span class="sxs-lookup"><span data-stu-id="56504-143">Complete the draft version of metadata configuration</span></span>
1.  <span data-ttu-id="56504-144">Cliquez sur **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="56504-144">Click **Change status**.</span></span> 
2.  <span data-ttu-id="56504-145">Cliquez sur **Terminé.**</span><span class="sxs-lookup"><span data-stu-id="56504-145">Click **Complete**.</span></span> 
3.  <span data-ttu-id="56504-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="56504-146">Click **OK**.</span></span> 
4.  <span data-ttu-id="56504-147">Sélectionnez la version **1** terminée.</span><span class="sxs-lookup"><span data-stu-id="56504-147">Select the completed version **1**.</span></span> 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a><span data-ttu-id="56504-148">Exporter la version achevée de la configuration des métadonnées à partir de l'application dans un fichier XML</span><span class="sxs-lookup"><span data-stu-id="56504-148">Export the completed version of metadata configuration from application as XML file</span></span>
1.  <span data-ttu-id="56504-149">Cliquez sur **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="56504-149">Click **Exchange**.</span></span> 
2.  <span data-ttu-id="56504-150">Cliquez sur **Exporter en tant que fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="56504-150">Click **Export as XML file**.</span></span> 
3.  <span data-ttu-id="56504-151">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="56504-151">Click **OK**.</span></span> 
    
<span data-ttu-id="56504-152">La configuration de métadonnées ER créée a été enregistrée comme fichier XML qui peut être importé dans RCS et utilisé comme source d'informations sur les métadonnées du domaine du commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="56504-152">The created ER metadata configuration has been saved as XML file that can be imported to RCS and used as the source of information about metadata for the foreign trade business domain.</span></span> <span data-ttu-id="56504-153">Sur la base de ces informations, nous pouvons spécifier la mise en correspondance entre les métadonnées d'application et le modèle de données ER.</span><span class="sxs-lookup"><span data-stu-id="56504-153">Based on this information, we can specify the mapping between application metadata and ER data model.</span></span>
