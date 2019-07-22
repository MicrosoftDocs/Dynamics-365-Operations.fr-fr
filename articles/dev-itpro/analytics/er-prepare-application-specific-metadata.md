---
title: Préparer les métadonnées spécifiques à l'application pour RCS et ER
description: Cette rubrique explique comment préparer des métadonnées spécifiques à l'application pour le service RCS (Regulatory Configuration Service) et la génération d'états électroniques (ER)
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 289f901501a68319c9d85e993d8dfbfc3838a8eb
ms.sourcegitcommit: d940c7892b6caa6141b3bda8abf1c56e9df4687a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2019
ms.locfileid: "1726430"
---
# <a name="prepare-application-specific-metadata-for-rcs"></a><span data-ttu-id="2b24b-103">Préparer les métadonnées spécifiques à l'application pour RCS</span><span class="sxs-lookup"><span data-stu-id="2b24b-103">Prepare application-specific metadata for RCS</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2b24b-104">Cette rubrique que vous guide via les exemples de tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="2b24b-104">This topic walks you through examples of the following tasks:</span></span>

- [<span data-ttu-id="2b24b-105">Préparer les métadonnées d'application à utiliser dans RCS</span><span class="sxs-lookup"><span data-stu-id="2b24b-105">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)
- [<span data-ttu-id="2b24b-106">Accéder aux métadonnées d'application à l'aide d'une configuration de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="2b24b-106">Access application metadata by using an ER configuration</span></span>](#access-application-metadata-by-using-an-er-configuration)
- [<span data-ttu-id="2b24b-107">Accéder aux métadonnées d'application à l'aide des applications connectées</span><span class="sxs-lookup"><span data-stu-id="2b24b-107">Access application metadata by using connected applications</span></span>](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a><span data-ttu-id="2b24b-108">Préparer les métadonnées d'application à utiliser dans RCS</span><span class="sxs-lookup"><span data-stu-id="2b24b-108">Prepare application metadata that can be used in RCS</span></span>

<span data-ttu-id="2b24b-109">La procédure suivante montre comment un utilisateur de Finance and Operations ayant le rôle **Administrateur système** ou **Développeur d'états électroniques** peut créer une configuration de génération d'états électroniques (ER) contenant des métadonnées pour l'application Microsoft Dynamics 365 for Finance and Operations, et qui est utilisée pour concevoir les configurations de mise en correspondance de modèles ER dans le service RCS (Regulatory Configuration Service).</span><span class="sxs-lookup"><span data-stu-id="2b24b-109">The following procedure shows how a user of Finance and Operations who has the **System Administrator** or **Electronic Reporting Developer** role can create an Electronic reporting (ER) configuration that contains metadata for the Microsoft Dynamics 365 for Finance and Operations application, and that is used to design ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="2b24b-110">L'exemple de configuration de mise en correspondance de modèle ER créée dans cette procédure sera utilisé pour accéder à des transactions de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="2b24b-110">The sample ER model mapping configuration that is created in this example will be used to access foreign trade transactions.</span></span>

<span data-ttu-id="2b24b-111">Pour cet exemple, vous souhaitez utiliser RCS pour créer une solution ER pour Finance and Operations qui sera utilisée pour générer les documents électroniques contenant les informations du commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="2b24b-111">For this example, you want to use RCS to design an ER solution for Finance and Operations that will be used to generate electronic documents that contain information from the foreign trade business domain.</span></span> <span data-ttu-id="2b24b-112">Pour spécifier la mise en correspondance entre le modèle de données ER et les sources de données nécessaires, vous devez avoir accès aux métadonnées d'application pour Finance and Operations dans RCS.</span><span class="sxs-lookup"><span data-stu-id="2b24b-112">To specify the mapping between the ER data model and the sources of required data, you must have access to application metadata for Finance and Operations in RCS.</span></span> <span data-ttu-id="2b24b-113">Par conséquent, dans le cadre de la conception de la solution ER, vous devez paramétrer une nouvelle configuration de métadonnées ER contenant toutes les métadonnées actuellement requises pour générer des les états électroniques pour le domaine d'activité sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2b24b-113">Therefore, as part of the process of designing the ER solution, you must configure a new ER metadata configuration that contains all the metadata that is currently required in order to generate ER reports for the selected business domain.</span></span>

> [!NOTE]
> <span data-ttu-id="2b24b-114">Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="2b24b-114">In this example, you will create a configuration for the sample company, Litware, Inc. These steps can be performed in any company.</span></span>

1. <span data-ttu-id="2b24b-115">Allez dans **Administration d'organisation \> Espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-115">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="2b24b-116">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-116">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="2b24b-117">Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="2b24b-117">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="2b24b-118">Sélectionnez **Configuration des métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-118">Select **Metadata configurations**.</span></span>
4. <span data-ttu-id="2b24b-119">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-119">Select **Create configuration**.</span></span>
5. <span data-ttu-id="2b24b-120">Dans la boîte de dialogue déroulante, dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="2b24b-120">In the drop-down dialog box, in the **Name** field, enter a name.</span></span> <span data-ttu-id="2b24b-121">Pour cet exemple, entrez **Métadonnées de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-121">For this example, enter **Foreign trade metadata**.</span></span>
6. <span data-ttu-id="2b24b-122">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-122">Select **Create configuration**.</span></span>
7. <span data-ttu-id="2b24b-123">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-123">Select **Designer**.</span></span>
8. <span data-ttu-id="2b24b-124">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-124">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b24b-125">Vous pouvez sélectionner toutes les métadonnées pour l'application entière, ou pour des modèles ou des modules sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="2b24b-125">You can select all metadata either for the whole application, or for selected models or modules.</span></span> <span data-ttu-id="2b24b-126">Dans les deux cas, notez que les métadonnées suivantes sont automatiquement ajoutées : tables des enregistrements, énumérations, et types de données étendus (EDT, Extended Data Types).</span><span class="sxs-lookup"><span data-stu-id="2b24b-126">In both cases, be aware that the following metadata will be automatically added: tables of records, enumerations, and extended data types (EDTs).</span></span> <span data-ttu-id="2b24b-127">Lorsque d'autres types de métadonnées sont requis, ils doivent être ajoutés manuellement.</span><span class="sxs-lookup"><span data-stu-id="2b24b-127">When additional types of metadata are required, they must be manually added.</span></span>

<span data-ttu-id="2b24b-128">Vous devez ajouter des métadonnées relatives aux transactions de commerce extérieur et sélectionner manuellement les éléments de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="2b24b-128">You must add some metadata that is related to foreign trade transactions and manually select metadata items.</span></span>

9. <span data-ttu-id="2b24b-129">Sélectionnez **Ajouter une source de données \> Enregistrements de table**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-129">Select **Add data source \> Table records**.</span></span>
10. <span data-ttu-id="2b24b-130">Filtrez sur une valeur de **Déclaration d'échanges de biens** dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-130">Filter on a value of **Intrastat** in the **Name** field.</span></span>
11. <span data-ttu-id="2b24b-131">Sélectionnez l'enregistrement de table **Déclaration d'échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-131">Select the **Intrastat** table record.</span></span>
12. <span data-ttu-id="2b24b-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-132">Select **OK**.</span></span>

<span data-ttu-id="2b24b-133">Vous devez ajouter des informations de métadonnées sur la table d'enregistrements de la déclaration d'échanges de biens.</span><span class="sxs-lookup"><span data-stu-id="2b24b-133">You must add metadata information about the Intrastat table of records.</span></span>

13. <span data-ttu-id="2b24b-134">Dans l'arborescence, sélectionnez **Enregistrements de table Déclaration d'échanges de biens \> \>Relations \> IntrastatCommodity (Enregistrements de table EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-134">In the tree, select **Table records Intrastat \> \>Relations \> IntrastatCommodity (Table records EcoResCategory)**.</span></span>
14. <span data-ttu-id="2b24b-135">Sélectionnez **Ajouter des métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-135">Select **Add metadata**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b24b-136">Les métadonnées sur les relations requises pour la table d'enregistrements sélectionnée doivent être ajoutées manuellement.</span><span class="sxs-lookup"><span data-stu-id="2b24b-136">Metadata about required relations for the selected table of records must be added manually.</span></span>

15. <span data-ttu-id="2b24b-137">Sélectionnez **Ajouter une source de données**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-137">Select **Add data source**.</span></span>
16. <span data-ttu-id="2b24b-138">Sélectionnez **Énumération**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-138">Select **Enumeration**.</span></span>
17. <span data-ttu-id="2b24b-139">Filtrez sur une valeur de **IntrastatDirection** dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-139">Filter on a value of **IntrastatDirection** in the **Name** field.</span></span>
18. <span data-ttu-id="2b24b-140">Sélectionnez l'enregistrement d'énumération **IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-140">Select the **IntrastatDirection** enumeration record.</span></span>
19. <span data-ttu-id="2b24b-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-141">Select **OK**.</span></span>
20. <span data-ttu-id="2b24b-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-142">Select **Save**.</span></span>
21. <span data-ttu-id="2b24b-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2b24b-143">Close the page.</span></span>
22. <span data-ttu-id="2b24b-144">Complétez la version temporaire de la configuration de métadonnées :</span><span class="sxs-lookup"><span data-stu-id="2b24b-144">Complete the draft version of the metadata configuration:</span></span>

    1. <span data-ttu-id="2b24b-145">Sélectionnez **Modifier le statut \> Terminé**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-145">Select **Change status \> Complete**.</span></span>
    2. <span data-ttu-id="2b24b-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-146">Select **OK**.</span></span>
    3. <span data-ttu-id="2b24b-147">Sélectionnez la version 1 terminée.</span><span class="sxs-lookup"><span data-stu-id="2b24b-147">Select the completed version 1.</span></span>

23. <span data-ttu-id="2b24b-148">Exportez la version achevée de la configuration des métadonnées à partir de l'application dans un fichier XML :</span><span class="sxs-lookup"><span data-stu-id="2b24b-148">Export the completed version of the metadata configuration from the application as an XML file:</span></span>

    1. <span data-ttu-id="2b24b-149">Sélectionnez **Exchange \> Exporter en tant que fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-149">Select **Exchange \> Export as XML file**.</span></span>
    2. <span data-ttu-id="2b24b-150">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-150">Select **OK**.</span></span>

<span data-ttu-id="2b24b-151">La configuration de métadonnées ER que vous avez créée est enregistrée comme fichier **Foreign trade metadata.xml**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-151">The ER metadata configuration that you created is saved as the **Foreign trade metadata.xml** file.</span></span> <span data-ttu-id="2b24b-152">Vous pouvez désormais l'importer dans RCS pour qu'elle soit utilisée comme la source des métadonnées pour le domaine du commerce extérieur dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2b24b-152">You can now import it into RCS, so that it can be used as the source of metadata for the foreign trade business domain in Finance and Operations.</span></span> <span data-ttu-id="2b24b-153">Sur la base de ces informations, vous pouvez spécifier la mise en correspondance entre les métadonnées d'application et le modèle de données ER.</span><span class="sxs-lookup"><span data-stu-id="2b24b-153">Based on this information, you can specify the mapping between application metadata and the ER data model.</span></span>

## <a name="access-application-metadata-by-using-an-er-configuration"></a><span data-ttu-id="2b24b-154">Accéder aux métadonnées d'application à l'aide d'une configuration de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="2b24b-154">Access application metadata by using an ER configuration</span></span>

<span data-ttu-id="2b24b-155">La procédure suivante ontre comment un utilisateur de RCS ayant le rôle **Administrateur système** ou **Développeur d'états électroniques** peut créer une mise en correspondance de modèle ER à l'aide des métadonnées de l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2b24b-155">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata from the Finance and Operations application.</span></span> <span data-ttu-id="2b24b-156">Les métadonnées d'application sont accessibles à l'aide d'une configuration de métadonnées ER contenant un échantillon de métadonnées pour accéder aux transactions de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="2b24b-156">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span>

<span data-ttu-id="2b24b-157">Avant d'exécuter cette procédure, vous devez d'abord réaliser celles qui suivent :</span><span class="sxs-lookup"><span data-stu-id="2b24b-157">Before you can complete this procedure, you must first complete the following procedures:</span></span>

- [<span data-ttu-id="2b24b-158">Créer un fournisseur de configuration et le marquer comme actif</span><span class="sxs-lookup"><span data-stu-id="2b24b-158">Create a configuration provider and mark it as active</span></span>](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [<span data-ttu-id="2b24b-159">Préparer les métadonnées d'application à utiliser dans RCS</span><span class="sxs-lookup"><span data-stu-id="2b24b-159">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)

1. <span data-ttu-id="2b24b-160">Accédez à **Tous les espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-160">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="2b24b-161">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-161">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="2b24b-162">Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="2b24b-162">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="2b24b-163">Importez la configuration de métadonnées ER contenant les métadonnées pour l'application Finance and Operations, configurée pour générer des documents électroniques pour le commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="2b24b-163">Import the ER metadata configuration that contains metadata for the Finance and Operations application, and that is configured to generate electronic documents for the foreign trade business domain.</span></span> <span data-ttu-id="2b24b-164">Vous avez créé cette configuration de métadonnées ER et l'avez exportée dans un fichier XML dans la procédure [Préparer les métadonnées d'application à utiliser dans RCS](#prepare-application-metadata-that-can-be-used-in-rcs) décrite plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="2b24b-164">You created this ER metadata configuration and exported it as an XML file in the [Prepare application metadata that can be used in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) procedure earlier in this topic.</span></span>

    1. <span data-ttu-id="2b24b-165">Sélectionnez **Configuration des métadonnées**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-165">Select **Metadata configurations**.</span></span>
    2. <span data-ttu-id="2b24b-166">Sélectionnez **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-166">Select **Exchange**.</span></span>
    3. <span data-ttu-id="2b24b-167">Sélectionnez **Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-167">Select **Load from XML file**.</span></span>
    4. <span data-ttu-id="2b24b-168">Recherchez et sélectionnez le fichier **Foreign trade metadata.xml**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-168">Browse to select the **Foreign trade metadata.xml** file.</span></span>
    5. <span data-ttu-id="2b24b-169">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-169">Select **OK**.</span></span>
    6. <span data-ttu-id="2b24b-170">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2b24b-170">Close the page.</span></span>

4. <span data-ttu-id="2b24b-171">Créez une configuration de modèle de données :</span><span class="sxs-lookup"><span data-stu-id="2b24b-171">Create a data model configuration:</span></span>

    1. <span data-ttu-id="2b24b-172">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-172">Select **Reporting configurations**.</span></span>
    2. <span data-ttu-id="2b24b-173">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-173">Select **Create configuration**.</span></span>
    3. <span data-ttu-id="2b24b-174">Dans la boîte de dialogue déroulante, dans le champ **Nom**, tapez **Modèle de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-174">In the drop-down dialog box, in the **Name** field, enter **Foreign trade model**.</span></span>
    4. <span data-ttu-id="2b24b-175">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-175">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="2b24b-176">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-176">Select **Designer**.</span></span>
    6. <span data-ttu-id="2b24b-177">Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2b24b-177">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="2b24b-178">Dans le champ **Nom**, tapez **Racine**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-178">In the **Name** field, type **Root**.</span></span>
        2. <span data-ttu-id="2b24b-179">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-179">Select **Add**.</span></span>
    
    7. <span data-ttu-id="2b24b-180">Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2b24b-180">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="2b24b-181">Dans le champ **Nom**, tapez **Transaction**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-181">In the **Name** field, type **Transaction**.</span></span>
        2. <span data-ttu-id="2b24b-182">Dans le champ **Type d'article**, sélectionnez **Liste d'enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-182">In the **Item type** field, select **Record list**.</span></span>
        3. <span data-ttu-id="2b24b-183">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-183">Select **Add**.</span></span>
 
    8. <span data-ttu-id="2b24b-184">Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2b24b-184">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="2b24b-185">Dans le champ **Nom**, tapez **Code marchandise**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-185">In the **Name** field, type **Commodity code**.</span></span>
        2. <span data-ttu-id="2b24b-186">Dans le champ **Type d'article**, sélectionnez **Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-186">In the **Item type** field, select **String**.</span></span>
        3. <span data-ttu-id="2b24b-187">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-187">Select **Add**.</span></span>

    9. <span data-ttu-id="2b24b-188">Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2b24b-188">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="2b24b-189">Dans le champ Nom, tapez **Montant facture**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-189">In the Name field, type **Invoiced amount**.</span></span>
        2. <span data-ttu-id="2b24b-190">Dans le champ **Type d'article**, sélectionnez **Réel**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-190">In the **Item type** field, select **Real**.</span></span>
        3. <span data-ttu-id="2b24b-191">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-191">Select **Add**.</span></span>

    10. <span data-ttu-id="2b24b-192">Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2b24b-192">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="2b24b-193">Dans le champ **Nom**, tapez **Date**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-193">In the **Name** field, type **Date**.</span></span>
        2. <span data-ttu-id="2b24b-194">Dans le champ **Type d'article**, sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-194">In the **Item type** field, select **Date**.</span></span>
        3. <span data-ttu-id="2b24b-195">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-195">Select **Add**.</span></span>
 
    11. <span data-ttu-id="2b24b-196">Sélectionnez **Ajouter \> Référence racine**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-196">Select **Add \> Root reference**.</span></span>
    12. <span data-ttu-id="2b24b-197">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-197">Select **OK**.</span></span>
    13. <span data-ttu-id="2b24b-198">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-198">Select **Save**.</span></span>
    14. <span data-ttu-id="2b24b-199">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2b24b-199">Close the page.</span></span>
    15. <span data-ttu-id="2b24b-200">Sélectionnez **Modifier le statut \> Terminé**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-200">Select **Change status \> Complete**.</span></span>
    16. <span data-ttu-id="2b24b-201">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-201">Select **OK**.</span></span>

5. <span data-ttu-id="2b24b-202">Créez une configuration de mise en correspondance de modèle :</span><span class="sxs-lookup"><span data-stu-id="2b24b-202">Create a model mapping configuration:</span></span>

    1. <span data-ttu-id="2b24b-203">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-203">Select **Create configuration**.</span></span>
    2. <span data-ttu-id="2b24b-204">Dans la boîte de dialogue déroulante, dans le champ **Nouveau**, entrez **Mise en correspondance de modèle basée sur le modèle de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-204">In the drop-down dialog box, in the **New** field, enter **Model Mapping based on data model Foreign trade model**.</span></span>
    3. <span data-ttu-id="2b24b-205">Dans le champ **Nom**, tapez **Mise en correspondance de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-205">In the **Name** field, enter **Foreign trade mapping**.</span></span>
    4. <span data-ttu-id="2b24b-206">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-206">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="2b24b-207">Dans l'organisateur **Conditions préalables**, sélectionnez **Éditer**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-207">On the **Prerequisites** FastTab, select **Edit**.</span></span>
    6. <span data-ttu-id="2b24b-208">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-208">Select **New**.</span></span>
    7. <span data-ttu-id="2b24b-209">Dans le champ **Type nécessaire de composant**, sélectionnez **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-209">In the **Prerequisite component type** field, select **Configuration**.</span></span>
    8. <span data-ttu-id="2b24b-210">Sélectionnez la configuration **Métadonnées de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-210">Select the **Foreign trade metadata** configuration.</span></span>
    9. <span data-ttu-id="2b24b-211">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-211">Select **Save**.</span></span> <span data-ttu-id="2b24b-212">Notez que nous avons ajouté la référence à la version 1 de la configuration **Métadonnées de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-212">Notice that the reference is added to version 1 of the **Foreign trade metadata** configuration.</span></span> <span data-ttu-id="2b24b-213">Les métadonnées d'application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue.</span><span class="sxs-lookup"><span data-stu-id="2b24b-213">Application metadata from this configuration will be offered while the model mapping is designed.</span></span>
    10. <span data-ttu-id="2b24b-214">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2b24b-214">Close the page.</span></span>
    11. <span data-ttu-id="2b24b-215">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-215">Select **Designer**.</span></span>
    12. <span data-ttu-id="2b24b-216">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-216">Select **Designer**.</span></span>
    13. <span data-ttu-id="2b24b-217">Dans l'arborescence, sélectionnez **Dynamics 365 for Operations \> Enregistrements de table**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-217">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
    14. <span data-ttu-id="2b24b-218">Sélectionnez **Ajoutez racine**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-218">Select **Add root**.</span></span>
    15. <span data-ttu-id="2b24b-219">Dans le champ **Nom**, entrez **Déclaration d'échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-219">In the **Name** field, enter **Intrastat**.</span></span>
    16. <span data-ttu-id="2b24b-220">Sélectionnez les enregistrements de table **Déclaration d'échanges de biens**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-220">Select **Intrastat** table records.</span></span>
    17. <span data-ttu-id="2b24b-221">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-221">Select **OK**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2b24b-222">Seules 2 tables sont proposées, car ces seules 2 tables ont été ajoutées à l'ensemble de métadonnées en cours de utilisation.</span><span class="sxs-lookup"><span data-stu-id="2b24b-222">Only two tables are offered, because only two tables were added to the set of metadata that is currently used.</span></span>

    18. <span data-ttu-id="2b24b-223">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-223">Select **Bind**.</span></span>
    19. <span data-ttu-id="2b24b-224">Dans l'arborescence, sélectionnez **Déclaration d'échanges de biens \> AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-224">In the tree, select **Intrastat \> AmountMST**.</span></span>
    20. <span data-ttu-id="2b24b-225">Dans l'arborescence, sélectionnez **Transaction = Déclaration d'échanges de biens \> Montant facturé**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-225">In the tree, select **Transaction = Intrastat \> Invoiced amount**.</span></span>
    21. <span data-ttu-id="2b24b-226">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-226">Select **Bind**.</span></span>
    22. <span data-ttu-id="2b24b-227">Dans l'arborescence, sélectionnez **Déclaration d'échanges de biens \> TransDate**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-227">In the tree, select **Intrastat \> TransDate**.</span></span>
    23. <span data-ttu-id="2b24b-228">Dans l'arborescence, sélectionnez **Transaction = Déclaration d'échanges de biens \> Date**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-228">In the tree, select **Transaction = Intrastat \> Date**.</span></span>
    24. <span data-ttu-id="2b24b-229">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-229">Select **Bind**.</span></span>
    25. <span data-ttu-id="2b24b-230">Dans l'arborescence, sélectionnez **Déclaration d'échanges de biens \> \>Relations \> IntrastatCommodity \> Code**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-230">In the tree, select **Intrastat \> \>Relations \> IntrastatCommodity \> Code**.</span></span>
    26. <span data-ttu-id="2b24b-231">Dans l'arborescence, sélectionnez **Transaction = Déclaration d'échanges de biens \> Code marchandise**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-231">In the tree, select **Transaction = Intrastat \> Commodity code**.</span></span>
    27. <span data-ttu-id="2b24b-232">Sélectionnez **Lier**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-232">Select **Bind**.</span></span>
    28. <span data-ttu-id="2b24b-233">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-233">Select **Validate**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2b24b-234">Une fois la validation effectuée, nous avons lié avec succès les éléments de modèle de données avec les éléments des sources de données qui sont décrits à l'aide des informations des métadonnées de l'application issues de la configuration de métadonnées ER associée.</span><span class="sxs-lookup"><span data-stu-id="2b24b-234">After validation is completed, you've successfully bound elements of the data model to items of the data sources that are described by using details of the application metadata from the referenced ER metadata configuration.</span></span>

    29. <span data-ttu-id="2b24b-235">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-235">Select **Save**.</span></span>

<span data-ttu-id="2b24b-236">Selon vos besoins, vous pouvez étendre l'ensemble de métadonnées existant dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2b24b-236">As you require, you can extend the existing set of metadata in Finance and Operations.</span></span> <span data-ttu-id="2b24b-237">Vous pouvez ensuite exporter la nouvelle version achevée de la configuration des métadonnées ER à partir de Finance and Operations, l'importer dans RCS et mettre à jour les conditions préalables et la configuration de mise en correspondance du modèle configurée se référant à une nouvelle version de la configuration des métadonnées importée.</span><span class="sxs-lookup"><span data-stu-id="2b24b-237">You can then export the new completed version of the ER metadata configuration from Finance and Operations, import it into RCS, and update the prerequisites of the configured model mapping configuration to refer to a new version of the imported metadata configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="2b24b-238">Cette manière d'obtenir des informations sur les métadonnées d'application est la seule disponible pour les applications déployées localement (c'est-à-dire lorsqu'un modèle de déploiement de données métier local \[LBD\], ou sur site, est utilisé pour Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="2b24b-238">This method for getting information about application metadata is the only available method for applications that are locally deployed (that is, when a local business data \[LBD\], or on-premises, deployment model is used for Finance and Operations).</span></span>

## <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="2b24b-239">Accéder aux métadonnées d'application à l'aide des applications connectées</span><span class="sxs-lookup"><span data-stu-id="2b24b-239">Access application metadata by using connected applications</span></span>

<span data-ttu-id="2b24b-240">La procédure suivante ontre comment un utilisateur de RCS ayant le rôle **Administrateur système** ou **Développeur d'états électroniques** peut créer une mise en correspondance de modèle ER à l'aide des métadonnées de l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2b24b-240">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata of the Finance and Operations application.</span></span> <span data-ttu-id="2b24b-241">Les métadonnées d'application ne sons accessibles en ligne qu'à l'aide de l'application RCS connectée.</span><span class="sxs-lookup"><span data-stu-id="2b24b-241">Application metadata will be accessed online by using RCS connected application.</span></span> <span data-ttu-id="2b24b-242">Un exemple de mise en correspondance de modèle ER est configuré pour accéder à des transactions de commerce extérieur.</span><span class="sxs-lookup"><span data-stu-id="2b24b-242">A sample ER model mapping will be configured to access foreign trade transactions.</span></span>

<span data-ttu-id="2b24b-243">Pour réaliser cette procédure, vous devez commencer par effectuer la procédure [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md) dans RCS.</span><span class="sxs-lookup"><span data-stu-id="2b24b-243">To complete this procedure, you must first complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure in RCS.</span></span> <span data-ttu-id="2b24b-244">Si vous n'avez pas encore réalisé les la procédure [Accéder aux métadonnées d'application à l'aide de la configuration de la gestion des états électroniques](#access-application-metadata-by-using-an-er-configuration) plus haut dans cette rubrique, accédez à la page [Guides de tâches de la génération d'états électroniques pour Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) pour télécharger par avance les fichiers de configuration ER suivants et les enregistrer localement : **Foreign trade metadata.xml**, **Foreign trade model.xml** et **Foreign trade mapping.xml**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-244">If you haven't yet completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, go to [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page to download the following ER configuration files in advance and save them locally: **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml**.</span></span>


### <a name="get-required-er-configurations"></a><span data-ttu-id="2b24b-245">Obtenir les configurations ER requises</span><span class="sxs-lookup"><span data-stu-id="2b24b-245">Get required ER configurations</span></span>

<span data-ttu-id="2b24b-246">Si vous avez déjà réalisé les étapes de la procédure [Accéder aux métadonnées d'application à l'aide d'une configuration de la gestion des états électroniques](#access-application-metadata-by-using-an-er-configuration) plus haut dans cette rubrique, vous disposez déjà de toutes les configurations ER nécessaires (métadonnées de commerce extérieur, configurations de modèle et de mise en correspondance) dans l'instance RCS actuelle.</span><span class="sxs-lookup"><span data-stu-id="2b24b-246">If you've already completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, you already have all the required ER configurations (the foreign trade metadata, model, and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="2b24b-247">Dans ce cas, vous pouvez ignorer cette procédure.</span><span class="sxs-lookup"><span data-stu-id="2b24b-247">In that case, you can skip this procedure.</span></span>

1. <span data-ttu-id="2b24b-248">Accédez à **Tous les espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-248">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="2b24b-249">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-249">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="2b24b-250">Chargez les fichiers de configuration **Foreign trade metadata.xml**, **Foreign trade model.xml**, et **CForeign trade mapping.xml** répétant la chaîne d'étapes suivantes pour chacun d'eux :</span><span class="sxs-lookup"><span data-stu-id="2b24b-250">Load the **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml** configuration files repeating the following chain of steps for each of them:</span></span>

    1. <span data-ttu-id="2b24b-251">Sélectionnez **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-251">Select **Exchange**.</span></span>
    2. <span data-ttu-id="2b24b-252">Sélectionnez **Charger depuis le fichier XML**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-252">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="2b24b-253">Sélectionnez **Parcourir** et sélectionnez un fichier.</span><span class="sxs-lookup"><span data-stu-id="2b24b-253">Select **Browse**, and select a file.</span></span>
    4. <span data-ttu-id="2b24b-254">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-254">Select **OK**.</span></span>

### <a name="register-the-connection-with-finance-and-operations"></a><span data-ttu-id="2b24b-255">Inscrivez la connexion à Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2b24b-255">Register the connection with Finance and Operations</span></span>

1. <span data-ttu-id="2b24b-256">Accédez à **Tous les espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-256">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="2b24b-257">Sélectionnez **Applications connectées**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-257">Select **Connected applications**.</span></span>
3. <span data-ttu-id="2b24b-258">Assurez-vous que l'application configurée est basée sur Microsoft Azure, et qu'elle est accessible en général aux utilisateurs de RCS.</span><span class="sxs-lookup"><span data-stu-id="2b24b-258">Make sure that the configured application is based on Microsoft Azure, and that it is accessible in general to RCS users.</span></span> <span data-ttu-id="2b24b-259">L'utilisateur RCS actuel doit avoir accès à l'application configurée en étant inscrit comme utilisateur de cette application avec un rôle lui accordant les privilèges d'accès aux métadonnées de l'application.</span><span class="sxs-lookup"><span data-stu-id="2b24b-259">The current RCS user must have access to the configured application being registered as a user of this application in a role that gives him or her privileges to access the application's metadata.</span></span>
4. <span data-ttu-id="2b24b-260">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-260">Select **New**.</span></span>
5. <span data-ttu-id="2b24b-261">Dans le champ **Nom**, entrez **MyConnectedApp** comme nom de l'application connectée.</span><span class="sxs-lookup"><span data-stu-id="2b24b-261">In the **Name** field, enter **MyConnectedApp** as the name of the connected application.</span></span>
6. <span data-ttu-id="2b24b-262">Dans le champ **Application**, spécifiez l'URL de l'application.</span><span class="sxs-lookup"><span data-stu-id="2b24b-262">In the **Application** field, specify the URL of the application.</span></span>
7. <span data-ttu-id="2b24b-263">Dans le champ **Locataire**, spécifiez le fournisseur de l'application.</span><span class="sxs-lookup"><span data-stu-id="2b24b-263">In the **Tenant** field, specify the provider of the application.</span></span>
8. <span data-ttu-id="2b24b-264">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-264">Select **Save**.</span></span> 
9. <span data-ttu-id="2b24b-265">Lorsque vous vérifiez la connexion à l'application configurée, dans la page **Se connecter à l'application distante** sélectionnez le lien **Cliquer ici pour vous connecter à l'application distante sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-265">When you check the connection to the configured application, on the **Connect to remote application** page, select the **Select here to connect to selected remote application** link.</span></span> 
10. <span data-ttu-id="2b24b-266">Sélectionnez **Vérifier la connexion** pour valider l'accès à l'application configurée.</span><span class="sxs-lookup"><span data-stu-id="2b24b-266">Select **Check connection** to validate access to the configured application.</span></span>
11. <span data-ttu-id="2b24b-267">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-267">Select **Close**.</span></span>

<span data-ttu-id="2b24b-268">Une fois la procédure exécutée et la validation de la connexion réussie, les détails de la version et du client sont mis à jour pour l'application configurée dans la grille actuelle.</span><span class="sxs-lookup"><span data-stu-id="2b24b-268">After you complete this procedure and validation of the connection succeeds, the version and tenant details for the configured application will be updated in the current grid.</span></span>

### <a name="review-the-existing-model-mapping-configuration"></a><span data-ttu-id="2b24b-269">Examiner la configuration de mise en correspondance de modèle existante</span><span class="sxs-lookup"><span data-stu-id="2b24b-269">Review the existing model mapping configuration</span></span>

1. <span data-ttu-id="2b24b-270">Accédez à **Tous les espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-270">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="2b24b-271">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-271">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="2b24b-272">Dans l'arborescence, sélectionnez **Modèle de commerce extérieur \> Mise en correspondance de commerce extérieur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-272">In the tree, select **Foreign trade model \> Foreign trade mapping**.</span></span>
4. <span data-ttu-id="2b24b-273">Sélectionnez l'organisateur **Conditions préalables**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-273">Select the **Prerequisites** FasTab.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b24b-274">Actuellement, cette mise en correspondance fait référence à la configuration de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="2b24b-274">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="2b24b-275">Les métadonnées d'application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue.</span><span class="sxs-lookup"><span data-stu-id="2b24b-275">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

4. <span data-ttu-id="2b24b-276">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-276">Select **Designer**.</span></span>
5. <span data-ttu-id="2b24b-277">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-277">Select **Designer**.</span></span>
6. <span data-ttu-id="2b24b-278">Dans l'arborescence, sélectionnez **Dynamics 365 for Operations \> Enregistrements de table**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-278">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
7. <span data-ttu-id="2b24b-279">Sélectionnez **Ajoutez racine**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-279">Select **Add root**.</span></span>
8. <span data-ttu-id="2b24b-280">Dans le champ **Table**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2b24b-280">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b24b-281">Actuellement, cette mise en correspondance fait référence à la configuration de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="2b24b-281">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="2b24b-282">Les métadonnées d'application de cette configuration seront proposées lorsque cette mise en correspondance modèle sera conçue.</span><span class="sxs-lookup"><span data-stu-id="2b24b-282">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

9. <span data-ttu-id="2b24b-283">Sélectionnez **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-283">Select **Cancel**.</span></span>

### <a name="assign-the-connected-application-to-a-model-mapping"></a><span data-ttu-id="2b24b-284">Affecter l'application connectée à une mise en correspondance de modèle</span><span class="sxs-lookup"><span data-stu-id="2b24b-284">Assign the connected application to a model mapping</span></span>

1. <span data-ttu-id="2b24b-285">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-285">Select **Edit**.</span></span>
2. <span data-ttu-id="2b24b-286">Dans le champ **Application connectée**, sélectionnez l'application **MyConnectedApp**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-286">In the **Connected application field**, select the **MyConnectedApp** application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b24b-287">Cette mise en correspondance fait référence aux métadonnées de l'application connectée sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2b24b-287">This mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="2b24b-288">Si une mise en correspondance fait référence à la configuration des métadonnées et à l'application connectée en même temps, les métadonnées de l'application connectée sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="2b24b-288">If a mapping refers to the metadata configuration and the connected application at the same time, the metadata of the connected application will be used.</span></span>

3. <span data-ttu-id="2b24b-289">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-289">Select **Designer**.</span></span>
4. <span data-ttu-id="2b24b-290">Sélectionnez **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-290">Select **Designer**.</span></span>
5. <span data-ttu-id="2b24b-291">Dans l'arborescence, sélectionnez **Dynamics 365 for Operations \> Enregistrements de table**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-291">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
6. <span data-ttu-id="2b24b-292">Sélectionnez **Ajoutez racine**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-292">Select **Add root**.</span></span>
7. <span data-ttu-id="2b24b-293">Dans le champ **Table**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2b24b-293">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b24b-294">À ce stade, plus de deux tables d'application sont présentées, car cette mise en correspondance utilise toutes les métadonnées de l'application connectée qui lui a été affectée.</span><span class="sxs-lookup"><span data-stu-id="2b24b-294">At this point, more than two application tables are offered, because this mapping uses all the metadata of the connected application that has been assigned to it.</span></span>

8. <span data-ttu-id="2b24b-295">Sélectionnez **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-295">Select **Cancel**.</span></span>
9. <span data-ttu-id="2b24b-296">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="2b24b-296">Select **Validate**.</span></span>

<span data-ttu-id="2b24b-297">Vous avez lié avec succès les éléments de modèle de données avec les éléments des sources de données qui sont décrits à l'aide des informations des métadonnées de l'application connectée qui a été affectée à cette mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="2b24b-297">You've now bound elements of the data model to items of the data sources that are described by using details of the metadata of the connected application that has been assigned to this mapping.</span></span>

<span data-ttu-id="2b24b-298">Lorsque vous devez évaluer cette mise en correspondance de modèle à l'aide de métadonnées d'une version différente de l'application, enregistrez une autre application connectée, affectez-la à cette mise en correspondance de modèle et validez-la par rapport aux nouvelles métadonnées.</span><span class="sxs-lookup"><span data-stu-id="2b24b-298">When you must evaluate this model mapping by using the metadata of a different version of the application, register another connected application, assign it to this model mapping, and validate it against the new metadata.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b24b-299">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2b24b-299">Additional resources</span></span>

<span data-ttu-id="2b24b-300">Sinon, vous pouvez lire le guide de tâche **Préparer les métadonnées d'application à utiliser dans RCS** dans Finance and Operations, ainsi que les guides de tâche **Accéder aux métadonnées d'application à l'aide d'une configuration de gestion des états électroniques** et **Accéder aux métadonnées d'application à l'aide des applications connectées** dans RCS.</span><span class="sxs-lookup"><span data-stu-id="2b24b-300">Alternatively, you can play the **Prepare application metadata that can be used in RCS** task guide in Finance and Operationsas as well as the **Access application metadata by using an ER configuration** and **Access application metadata by using connected applications** task guides in RCS.</span></span> <span data-ttu-id="2b24b-301">Ces guides de tâche peuvent être téléchargés à partir de la page [Guides de tâches de la génération d'états électroniques pour Dynamics 365 for Finance and Operations 8,1](https://go.microsoft.com/fwlink/?linkid=2082739).</span><span class="sxs-lookup"><span data-stu-id="2b24b-301">These task guides can be downloaded from the [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page.</span></span>
