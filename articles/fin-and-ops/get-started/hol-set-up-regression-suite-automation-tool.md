---
title: Didacticiel pour la configuration et l'installation de Regression Suite Automation Tool
description: Cette rubrique est un didacticiel qui indique comment configurer et installer l'outil Regression Suite Automation Tool (RSAT).
author: kfend
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: e2287cb0281e920de219cb88d41cd69264911f93
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850857"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="75b64-103">Didacticiel pour la configuration et l'installation de Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="75b64-103">Set up and install Regression suite automation tool tutorial</span></span>
<span data-ttu-id="75b64-104">Cette rubrique est un didacticiel qui vous aide à paramétrer et faire vos premiers pas avec RSAT et les outils qui y sont associés.</span><span class="sxs-lookup"><span data-stu-id="75b64-104">This topic is a tutorial that helps you get setup and get started with RSAT and the tools associated with using RSAT.</span></span> 

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="75b64-105">Utilisez les outils du navigateur Internet pour télécharger et enregistrer cette page au format PDF.</span><span class="sxs-lookup"><span data-stu-id="75b64-105">Use your internet browser tools to download and save this page in PDF format.</span></span> 

## <a name="key-concepts"></a><span data-ttu-id="75b64-106">Concepts clés</span><span class="sxs-lookup"><span data-stu-id="75b64-106">Key concepts</span></span>

- <span data-ttu-id="75b64-107">Appréhendez l'installation et le paramétrage préalable requis pour les différentes applications qui prennent en charge l'outil RSAT (Regression Suite Automation Tool).</span><span class="sxs-lookup"><span data-stu-id="75b64-107">Understand the installation and prerequisite setup that are required for the various applications that support Regression suite automation tool (RSAT).</span></span>
- <span data-ttu-id="75b64-108">Découvrez comment la fonction d'enregistrement de tâches dans Microsoft Dynamics 365 for Finance and Operations, ainsi que Microsoft Dynamics Lifecycle Services (LCS) et Microsoft Azure DevOps vous aident à créer, configurer, exécuter, étudier, et générer des rapports sur des scénarios de test.</span><span class="sxs-lookup"><span data-stu-id="75b64-108">Understand how the Task recorder feature in Microsoft Dynamics 365 for Finance and Operations, together with Microsoft Dynamics Lifecycle Services (LCS) and Microsoft Azure DevOps, let you create, configure, run, investigate, and report on test cases.</span></span>
- <span data-ttu-id="75b64-109">Donnez aux utilisateurs fonctionnels les moyens d'enregistrer les tâches métier à l'aide de l'enregistreur de Finance and Operations, puis de convertir ces enregistrements en une suite de tests automatisés, sans devoir écrire de code source.</span><span class="sxs-lookup"><span data-stu-id="75b64-109">Empower functional users to record business tasks by using Task recorder in Finance and Operations, and then convert the task recordings into a suite of automated tests, without having to write source code.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="75b64-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="75b64-110">Before you begin</span></span>

### <a name="prerequisites"></a><span data-ttu-id="75b64-111">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="75b64-111">Prerequisites</span></span>

- <span data-ttu-id="75b64-112">Un environnement Finance and Operations qui exécute la version 10.0 de Microsoft Dynamics 365 for Finance and Operations (avril 2019) ou une version ultérieure est requis pour ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="75b64-112">A Finance and Operations environment that runs Microsoft Dynamics 365 for Finance and Operations version 10.0 (April 2019) or later is required for this tutorial.</span></span> <span data-ttu-id="75b64-113">Pour les clients utilisant Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, Platform Update 20 (PU20) ou version ultérieure est également prise en charge.</span><span class="sxs-lookup"><span data-stu-id="75b64-113">For customers who are using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, Platform update 20 (PU20) or later is also supported.</span></span>
- <span data-ttu-id="75b64-114">L'utilisateur doit disposer des droits d'administrateur dans l'environnement Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="75b64-114">The user must have admin rights to the Finance and Operations environment.</span></span>
- <span data-ttu-id="75b64-115">Vous devez avoir accès au LCS du client et à Azure DevOps (auparavant connu sous le nom de Microsoft Visual Studio Team Services \[VSTS\]).</span><span class="sxs-lookup"><span data-stu-id="75b64-115">You must have access to the customer tenant LCS and Azure DevOps (previously known as Microsoft Visual Studio Team Services \[VSTS\]).</span></span>
- <span data-ttu-id="75b64-116">L'utilisateur qui crée et gère les suites de tests doit disposer d'une licence de plan de test ou de responsable de tests Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-116">The user that is creating and managing tests suites must have an Azure DevOps Test Plans or Test Manager license.</span></span> <span data-ttu-id="75b64-117">Les licences suivantes vous octroient également l'accès aux plans de test :</span><span class="sxs-lookup"><span data-stu-id="75b64-117">The following licenses will also give you access to Test Plans:</span></span>
    - <span data-ttu-id="75b64-118">Licence Visual Studio Enterprise</span><span class="sxs-lookup"><span data-stu-id="75b64-118">Visual Studio Enterprise license</span></span>
    - <span data-ttu-id="75b64-119">Licence Visual Studio Test Professional</span><span class="sxs-lookup"><span data-stu-id="75b64-119">Visual Studio Test Professional license</span></span>
    - <span data-ttu-id="75b64-120">Licence d'abonné de plateformes MSDN</span><span class="sxs-lookup"><span data-stu-id="75b64-120">MSDN Platforms subscriber license</span></span>
- <span data-ttu-id="75b64-121">RSAT doit avoir accès à l'environnement de test via un navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="75b64-121">RSAT must have access to the test environment via a web browser.</span></span>
- <span data-ttu-id="75b64-122">Pour générer et modifier les paramètres de test, vous devez avoir Microsoft Excel installé.</span><span class="sxs-lookup"><span data-stu-id="75b64-122">To generate and edit test parameters, you must have Microsoft Excel installed.</span></span>

## <a name="configure-azure-devops"></a><span data-ttu-id="75b64-123">Configurer Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="75b64-123">Configure Azure DevOps</span></span>

### <a name="user-eligibility"></a><span data-ttu-id="75b64-124">Admissibilité des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="75b64-124">User eligibility</span></span>

<span data-ttu-id="75b64-125">Assurez-vous que l'utilisateur est créé dans Azure DevOps et dispose d'un niveau d'abonnement qui permet d'accéder aux plans de test Azure.</span><span class="sxs-lookup"><span data-stu-id="75b64-125">Make sure that the user is created in Azure DevOps and has a subscription level that provides access to Azure Test Plans.</span></span> <span data-ttu-id="75b64-126">Une licence de plans de test Azure DevOps n'est requise que si l'utilisateur crée et traite des scénarios de test (autrement dit, tous les utilisateurs de RSAT n'ont pas besoin de cette licence).</span><span class="sxs-lookup"><span data-stu-id="75b64-126">An Azure DevOps Test Plans license is required only if the user will create and manage test cases (that is, not all RSAT users require this license).</span></span> <span data-ttu-id="75b64-127">Pour plus d'informations sur les exigences de licence, voir [Exigences relatives aux licences](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span><span class="sxs-lookup"><span data-stu-id="75b64-127">For information about the license requirements, see [License requirements](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span></span>

### <a name="create-a-new-azure-devops-project"></a><span data-ttu-id="75b64-128">Créer un nouveau projet Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="75b64-128">Create a new Azure DevOps project</span></span>
<span data-ttu-id="75b64-129">RSAT utilise Azure Devops pour gérer les scénarios de test et les suites de test, la génération d'états, et l'examen des résultats des essais.</span><span class="sxs-lookup"><span data-stu-id="75b64-129">RSAT uses Azure Devops for test case and test suite management, reporting, and investigating test run results.</span></span> 

> [!NOTE]
> <span data-ttu-id="75b64-130">Vous pouvez utiliser un projet Azure DevOps existant.</span><span class="sxs-lookup"><span data-stu-id="75b64-130">You can use an existing Azure DevOps project.</span></span> <span data-ttu-id="75b64-131">Toutefois, si votre projet Azure DevOps existant est paramétré de sorte à disposer d'un modèle personnalisé, vous recevez un message d'erreur « Échec de synchronisation de VSTS » lors de la synchronisation de scénarios de test issus du Concepteur de processus d'entreprise (BPM) avec Azure DevOps (voir la section [Test de la synchronisation entre BPM et Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)).</span><span class="sxs-lookup"><span data-stu-id="75b64-131">However, if your existing Azure DevOps project is set up so that it has a custom template, you will receive a "VSTS Sync Failure" error when you sync test cases from Business process modeler (BPM) to Azure DevOps (see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section).</span></span> <span data-ttu-id="75b64-132">Si les bonnes pratiques suivantes ont été suivies pour le modèle personnalisé, vous pourrez synchroniser les scénarios de test avec Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-132">If the following best practices have been followed for the custom template, you will be able to sync the test cases to Azure DevOps.</span></span> <span data-ttu-id="75b64-133">(Ces bonnes pratiques sont répertoriées dans le message d'erreur.)</span><span class="sxs-lookup"><span data-stu-id="75b64-133">(These best practices are listed in the error message.)</span></span>

- <span data-ttu-id="75b64-134">Ne pas supprimer les types d'éléments de travail ou les champ prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="75b64-134">Do not delete any work item types or out-of-the-box fields.</span></span>
- <span data-ttu-id="75b64-135">Ne pas supprimer l'état d'un type d'élément de travail.</span><span class="sxs-lookup"><span data-stu-id="75b64-135">Do not delete any state of a work item type.</span></span>
- <span data-ttu-id="75b64-136">Ne pas ajouter de champs obligatoires à un type d'élément de travail.</span><span class="sxs-lookup"><span data-stu-id="75b64-136">Do not add any required fields to a work item type.</span></span>

![Message d'erreur avec une liste de pratiques recommandées](./media/setup_rsa_tool_02.png)

<span data-ttu-id="75b64-138">Sinon, pour ce didacticiel, nous vous recommandons de créer un nouveau projet Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-138">Otherwise, for this tutorial, we recommend that you create a new Azure DevOps project.</span></span> <span data-ttu-id="75b64-139">Pour plus d'informations, voir [Problèmes lors de la synchronisation avec BPM à l'aide d'un modèle de processus Azure DevOps (VSTS) personnalisé](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span><span class="sxs-lookup"><span data-stu-id="75b64-139">For more information, see [Issues when syncing to BPM using a custom Azure DevOps (VSTS) process template](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span></span>

1. <span data-ttu-id="75b64-140">Ouvrez l'URL Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).</span><span class="sxs-lookup"><span data-stu-id="75b64-140">Open the Azure DevOps URL (`https://dev.azure.com/<Azure DevOps Name>`).</span></span>
2. <span data-ttu-id="75b64-141">Sélectionnez **Créer un projet** dans le coin supérieur droit de la page Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-141">Select **Create project** in the upper-right corner of the Azure DevOps page.</span></span>

    ![Créer un bouton de projet](./media/setup_rsa_tool_03.png)

3. <span data-ttu-id="75b64-143">Renseignez les champs suivants, puis sélectionnez **Créer** :</span><span class="sxs-lookup"><span data-stu-id="75b64-143">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="75b64-144">**Nom du projet**</span><span class="sxs-lookup"><span data-stu-id="75b64-144">**Project name**</span></span>
    - <span data-ttu-id="75b64-145">**Contrôle de version** – Sélectionnez **Contrôle de version Team Foundation**.</span><span class="sxs-lookup"><span data-stu-id="75b64-145">**Version control** – Select **Team Foundation Version Control**.</span></span> <span data-ttu-id="75b64-146">Notez que l'option par défaut, **Git**, n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="75b64-146">Note that the default option, **Git**, isn't supported.</span></span>
    - <span data-ttu-id="75b64-147">**Traitement d'élément de travail**</span><span class="sxs-lookup"><span data-stu-id="75b64-147">**Work item process**</span></span>

    ![Créer une boîte de dialogue de nouveau projet](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a><span data-ttu-id="75b64-149">Créer un jeton d'accès personnel</span><span class="sxs-lookup"><span data-stu-id="75b64-149">Create a personal access token</span></span>

<span data-ttu-id="75b64-150">Dans ce didacticiel, vous allez utiliser le Concepteur de processus d'entreprise (BPM) LCS pour créer une bibliothèque de scénario de test et synchroniser vos scénarios de test avec Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-150">In this tutorial, you will use the LCS Business Process Modeler (BPM) to create a test case library and synchronize your test cases with Azure DevOps.</span></span> <span data-ttu-id="75b64-151">Vous avez besoin d'un jeton personnel d'accès pour synchroniser BPM avec Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-151">You will need a personal access token to sync BPM with Azure DevOps.</span></span>

1. <span data-ttu-id="75b64-152">Sélectionnez l'icône de profil dans le coin supérieur droit de la page pour le projet Azure DevOps, puis sélectionnez **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="75b64-152">Select the profile icon in the upper-right corner of the page for your Azure DevOps project, and then select **Security**.</span></span>

    ![Commande de sécurité](./media/setup_rsa_tool_05.png)

2. <span data-ttu-id="75b64-154">Dans le volet de gauche, sous **Sécurité**, sélectionnez **Jetons personnels d'accès**.</span><span class="sxs-lookup"><span data-stu-id="75b64-154">In the left pane, under **Security**, select **Personal access tokens**.</span></span> <span data-ttu-id="75b64-155">Sélectionnez **Nouveau jeton**.</span><span class="sxs-lookup"><span data-stu-id="75b64-155">Then select **New Token**.</span></span>

    ![Bouton Nouveau jeton de l'onglet Jetons personnels d'accès dans les Paramètres utilisateur](./media/setup_rsa_tool_06.png)

3. <span data-ttu-id="75b64-157">Renseignez les champs suivants, puis sélectionnez **Créer** :</span><span class="sxs-lookup"><span data-stu-id="75b64-157">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="75b64-158">**Nom**</span><span class="sxs-lookup"><span data-stu-id="75b64-158">**Name**</span></span>
    - <span data-ttu-id="75b64-159">**Expiration (UTC)** – Sélectionnez **Personnalisé**, puis utilisez le sélecteur de date pour sélectionner la dernière date disponible.</span><span class="sxs-lookup"><span data-stu-id="75b64-159">**Expiration (UTC)** – Select **Custom defined**, and then use the date picker to select the last available date.</span></span>
    - <span data-ttu-id="75b64-160">**Champs d'application** – Sélectionnez l'option **Accès total**.</span><span class="sxs-lookup"><span data-stu-id="75b64-160">**Scopes** – Select the **Full access** option.</span></span>

    ![Créer une boîte de dialogue de nouveau jeton personnel d'accès](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > <span data-ttu-id="75b64-162">Notez le jeton personnel d'accès créé.</span><span class="sxs-lookup"><span data-stu-id="75b64-162">Make a note of the personal access token that is created.</span></span> <span data-ttu-id="75b64-163">Vous aurez besoin de lui ultérieurement lors du paramétrage de la configuration de RSAT.</span><span class="sxs-lookup"><span data-stu-id="75b64-163">You will need it later when you set up the RSAT configuration.</span></span>

    ![Jeton d'accès personnel](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a><span data-ttu-id="75b64-165">Configurer le projet LCS</span><span class="sxs-lookup"><span data-stu-id="75b64-165">Configure the LCS project</span></span>

<span data-ttu-id="75b64-166">Vous devez disposer d'un projet LCS (Lifecycle Services) pour votre bibliothèque de tests principale.</span><span class="sxs-lookup"><span data-stu-id="75b64-166">You need a Lifecycle Services (LCS) project for your master test library.</span></span> <span data-ttu-id="75b64-167">Le Concepteur de processus d'entreprise (BPM) est utilisé comme bibliothèque principale pour les scénarios de test.</span><span class="sxs-lookup"><span data-stu-id="75b64-167">The LCS Business Process Modeler (BPM) is used as the master library for your test cases.</span></span> <span data-ttu-id="75b64-168">BPM permet de gérer et répartir les bibliothèques de test sur plusieurs projets LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-168">BPM is used to manage and distribute test libraries across LCS projects.</span></span> <span data-ttu-id="75b64-169">Par exemple, un partenaire Microsoft ou un éditeur de logiciels indépendant (ISV) créateur de bibliothèques de tests publiera des scénarios de tests sous la forme de bibliothèque BPM.</span><span class="sxs-lookup"><span data-stu-id="75b64-169">For example, a Microsoft partner or independent software vendor (ISV) building test libraries will release test cases in the form of BPM libraries.</span></span> <span data-ttu-id="75b64-170">Dans BPM, les scénarios de test sont organisés par processus métier.</span><span class="sxs-lookup"><span data-stu-id="75b64-170">In BPM, test cases are organized by business process.</span></span> <span data-ttu-id="75b64-171">BPM ne définit pas l'ordre d'exécution ou la fréquence de vos tests.</span><span class="sxs-lookup"><span data-stu-id="75b64-171">BPM doesn't define the execution order or frequency of your test pass.</span></span> <span data-ttu-id="75b64-172">Ces détails sont gérés dans Azure DevOps, comme décrit plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="75b64-172">These details are managed in Azure DevOps, as described later in this topic.</span></span>  

<span data-ttu-id="75b64-173">Pour votre projet LCS, vous pouvez utiliser un projet d'implémentation existant d'un client ou d'un partenaire.</span><span class="sxs-lookup"><span data-stu-id="75b64-173">For your LCS project, you can use an existing customer implementation or partner project.</span></span>

### <a name="update-the-lcs-language"></a><span data-ttu-id="75b64-174">Mettre à jour la langue de LCS</span><span class="sxs-lookup"><span data-stu-id="75b64-174">Update the LCS language</span></span>

> [!NOTE]
> <span data-ttu-id="75b64-175">Pour que l'interface utilisateur affiche correctement les processus métier, la langue privilégiée de LCS doit être définie sur **Anglais (États-Unis)**.</span><span class="sxs-lookup"><span data-stu-id="75b64-175">For the user interface (UI) to correctly show business processes, the LCS preferred language must be set to **English (United States)**.</span></span>

1. <span data-ttu-id="75b64-176">Accédez au projet d'implémentation LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-176">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="75b64-177">Sélectionnez le bouton **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit de la page, puis sélectionnez **Préférences linguistiques**.</span><span class="sxs-lookup"><span data-stu-id="75b64-177">Select the **Settings** button (the gear symbol) in the upper-right corner, and then select **Language preference**.</span></span>

    ![Commandes dans le menu Paramètres](./media/setup_rsa_tool_09.png)

3. <span data-ttu-id="75b64-179">Dans le champ **Langue favorite**, sélectionnez **Anglais (États-Unis)**, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-179">In the **Preferred language** field, select **English (United States)**, and then select **Save**.</span></span>

    ![Onglet Préférences linguistiques dans les Paramètres utilisateur](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a><span data-ttu-id="75b64-181">Configurer LCS pour se connecter au projet Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="75b64-181">Configure LCS to connect to the Azure DevOps project</span></span>

<span data-ttu-id="75b64-182">Si vous avez créé un projet Azure DevOps auparavant, configurez le projet LCS pour vous y connecter.</span><span class="sxs-lookup"><span data-stu-id="75b64-182">If you created a new Azure DevOps project earlier, configure the LCS project to connect to it.</span></span> <span data-ttu-id="75b64-183">Sinon, si votre projet LCS est déjà connecté à votre projet Azure DevOps, vous pouvez passer à la section suivante.</span><span class="sxs-lookup"><span data-stu-id="75b64-183">Otherwise, if your LCS project is already connected to your Azure DevOps project, you can continue to the next section.</span></span>

1. <span data-ttu-id="75b64-184">Accédez au projet d'implémentation LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-184">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="75b64-185">Sélectionnez le bouton **Menu**, puis sélectionnez **Paramètres de projet**.</span><span class="sxs-lookup"><span data-stu-id="75b64-185">Select the **Menu** button, and then select **Project settings**.</span></span>

    ![Commande des paramètres du projet](./media/setup_rsa_tool_11.png)

3. <span data-ttu-id="75b64-187">Dans le volet gauche, sélectionnez **Visual Studio Team Services**, puis sélectionnez **Configuration de Visual StudioTeam Services**.</span><span class="sxs-lookup"><span data-stu-id="75b64-187">In the left pane, select **Visual Studio Team Services**, and then select **Setup Visual Studio Team Services**.</span></span>

    ![Onglet Visual Studio Team Services dans les Paramètres du projet](./media/setup_rsa_tool_12.png)

4. <span data-ttu-id="75b64-189">Dans le champ **URL de site Azure DevOps**, saisissez l'URL du site Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-189">In the **Azure DevOps site URL** field, enter the URL of the Azure DevOps site.</span></span> <span data-ttu-id="75b64-190">Dans le champ **Jeton personnel d'accès**, entrez le jeton personnel d'accès créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="75b64-190">In the **Personal access token** field, enter the personal access token that was created earlier.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-191">Bien que VSTS s'appelle désormais Azure DevOps, connectez LCS à votre projet Azure DevOps, utilisez l'ancienne URL.</span><span class="sxs-lookup"><span data-stu-id="75b64-191">Although VSTS is now known as Azure DevOps, to connect LCS to your Azure DevOps project, use the old URL.</span></span> <span data-ttu-id="75b64-192">Par exemple, l'URL Azure DevOps qui est utilisée dans ce didacticiel est `https://dev.azure.com/D365FOFastTrack/`.</span><span class="sxs-lookup"><span data-stu-id="75b64-192">For example, the Azure DevOps URL that is used in this tutorial is `https://dev.azure.com/D365FOFastTrack/`.</span></span> <span data-ttu-id="75b64-193">Toutefois, dans l'illustration suivante, elle est saisie comme `https://D365FOFastTrack.visualstudio.com/`.</span><span class="sxs-lookup"><span data-stu-id="75b64-193">However, in the following illustration, it's entered as `https://D365FOFastTrack.visualstudio.com/`.</span></span>

    ![Étape 1 de Configuration de Visual Studio Team Services](./media/setup_rsa_tool_13.png)

5. <span data-ttu-id="75b64-195">Sélectionnez **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-195">Select **Continue**.</span></span>
6. <span data-ttu-id="75b64-196">Dans le champ **Projet Visual Studio Team Services**, sélectionnez le projet VSTS sur le site sélectionné pour le lier au projet LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-196">In the **Visual Studio Team Services project** field, select the VSTS project on the selected site to link with the LCS project.</span></span> <span data-ttu-id="75b64-197">Le champ **Modèle de traitement** est défini sur **Agile** par défaut.</span><span class="sxs-lookup"><span data-stu-id="75b64-197">The **Process template** field is set to **Agile** by default.</span></span> <span data-ttu-id="75b64-198">Pour un modèle personnalisé, examinez les bonnes pratiques recommandées de la section [Créer un nouveau projet Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="75b64-198">For a custom template, review the best practice guidance in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span> <span data-ttu-id="75b64-199">Ensuite, sélectionnez **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-199">Then select **Continue**.</span></span>

    ![Étape 2 de Configuration de Visual Studio Team Services](./media/setup_rsa_tool_14.png)

7. <span data-ttu-id="75b64-201">Vérifiez vos paramètres, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-201">Review your settings, and then select **Save**.</span></span>

    ![Étape 3 de Configuration de Visual Studio Team Services](./media/setup_rsa_tool_15.png)

8. <span data-ttu-id="75b64-203">Sélectionnez **Autoriser** pour autoriser LCS à accéder au site Azure DevOps configuré en votre nom et pour activer les fonctions qui s'intègrent avec VSTS.</span><span class="sxs-lookup"><span data-stu-id="75b64-203">Select **Authorize** to authorize LCS to access the configured Azure DevOps site on your behalf and to turn on features that integrate with VSTS.</span></span>

    ![Bouton Autoriser](./media/setup_rsa_tool_16.png)

9. <span data-ttu-id="75b64-205">Une boîte de message s'affiche. Elle indique « Vous êtes sur le point d'être redirigé(e) vers un site externe pour autoriser LCS à se connecter à Visual Studio Team Services en votre nom.</span><span class="sxs-lookup"><span data-stu-id="75b64-205">A message box appears that states, "You are about to be redirected to an eternal site to authorize LCS to connect to Visual Studio Team Services on your behalf.</span></span> <span data-ttu-id="75b64-206">Voulez-vous continuer ? »</span><span class="sxs-lookup"><span data-stu-id="75b64-206">Proceed?"</span></span> <span data-ttu-id="75b64-207">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="75b64-207">Select **Yes**.</span></span>

    ![Zone de message](./media/setup_rsa_tool_17.png)

10. <span data-ttu-id="75b64-209">Sélectionner **Accepter**.</span><span class="sxs-lookup"><span data-stu-id="75b64-209">Select **Accept**.</span></span>

    ![Autoriser l'accès](./media/setup_rsa_tool_18.png)

11. <span data-ttu-id="75b64-211">Si vous êtes un utilisateur autorisé, l'IU doit revenir à la page Paramètres du projet LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-211">If you're authorized as a user, the UI should you return to the LCS project settings page.</span></span>

    ![Utilisateur autorisé](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a><span data-ttu-id="75b64-213">Créer une bibliothèque BPM</span><span class="sxs-lookup"><span data-stu-id="75b64-213">Create a new BPM library</span></span>

1. <span data-ttu-id="75b64-214">Accédez au projet d'implémentation LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-214">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="75b64-215">Sélectionnez le bouton **Menu**, puis sélectionnez **Concepteur de processus d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="75b64-215">Select the **Menu** button, and then select **Business process modeler**.</span></span>

    ![Commande Concepteur de processus d'entreprise](./media/setup_rsa_tool_20.png)

3. <span data-ttu-id="75b64-217">Sélectionnez **Nouvelle bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="75b64-217">Select **New library**.</span></span>

    ![Bouton Nouvelle bibliothèque](./media/setup_rsa_tool_21.png)

4. <span data-ttu-id="75b64-219">Dans le champ **Nom de la bibliothèque**, entrez un nom, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-219">In the **Library name** field, enter a name, and then select **Create**.</span></span> <span data-ttu-id="75b64-220">Pour ce didacticiel, nommez la bibliothèque BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="75b64-220">For this tutorial, name the BPM library **RSAT**.</span></span>

    ![Créer une boîte de dialogue de nouvelle bibliothèque](./media/setup_rsa_tool_22.png)

5. <span data-ttu-id="75b64-222">Ouvrez la nouvelle bibliothèque BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="75b64-222">Open the new **RSAT** BPM library.</span></span>
6. <span data-ttu-id="75b64-223">Sélectionnez le processus **Exemple de processus métier essentiel**, puis, à droite, sélectionnez **Mode d'édition**.</span><span class="sxs-lookup"><span data-stu-id="75b64-223">Select the **Sample Core Business Process** process, and then, on the right, select **Edit mode**.</span></span>

    ![Bouton Mode d'édition](./media/setup_rsa_tool_23.png)

7. <span data-ttu-id="75b64-225">Modifiez la valeur du champ **Nom** et du champ **Description** en **Créer un produit**.</span><span class="sxs-lookup"><span data-stu-id="75b64-225">Change the value of both the **Name** field and the **Description** field to **Create a product**.</span></span> <span data-ttu-id="75b64-226">Sélectionnez ensuite **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-226">Then select **Save**.</span></span>

    ![Champs Nom et description](./media/setup_rsa_tool_24.png)

## <a name="finance-and-operations-environment"></a><span data-ttu-id="75b64-228">Environnement Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="75b64-228">Finance and Operations environment</span></span>

### <a name="version-requirement"></a><span data-ttu-id="75b64-229">Exigences relatives à la version</span><span class="sxs-lookup"><span data-stu-id="75b64-229">Version requirement</span></span>

<span data-ttu-id="75b64-230">Un environnement Finance and Operations de test ou de sandbox exécutant la version 10 est requis.</span><span class="sxs-lookup"><span data-stu-id="75b64-230">A Finance and Operations test or sandbox environment that runs version 10 is required.</span></span> <span data-ttu-id="75b64-231">Pour les clients utilisant la version 7.3, Platform Update 20 ou une version ultérieure est également prise en charge.</span><span class="sxs-lookup"><span data-stu-id="75b64-231">For customers that are using version 7.3, Platform update 20 or later is also supported.</span></span>

> [!NOTE]
> <span data-ttu-id="75b64-232">RSAT doit avoir accès à l'environnement de test Finance and Operations via un navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="75b64-232">RSAT must have access to your Finance and Operations test environment via a web browser.</span></span>

### <a name="user-criteria"></a><span data-ttu-id="75b64-233">Critères utilisateur</span><span class="sxs-lookup"><span data-stu-id="75b64-233">User criteria</span></span>

<span data-ttu-id="75b64-234">L'utilisateur doit disposer de droits d'administrateur dans cet environnement.</span><span class="sxs-lookup"><span data-stu-id="75b64-234">The user must have admin rights to this environment.</span></span>

### <a name="set-up-help-settings-to-connect-with-lcs"></a><span data-ttu-id="75b64-235">Configuration des Paramètres d'aide pour la connexion à LCS</span><span class="sxs-lookup"><span data-stu-id="75b64-235">Set up Help settings to connect with LCS</span></span>

<span data-ttu-id="75b64-236">Cette étape est obligatoire pour se connecter à LCS de manière à pouvoir enregistrer les enregistrements de tâches dans la bibliothèque BPM appropriée dans LCS par l'intermédiaire du client Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="75b64-236">This step is required in order to connect with LCS so that task recordings can be saved to the appropriate BPM library in LCS through the Finance and Operations client.</span></span>

1. <span data-ttu-id="75b64-237">Ouvrez le client Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="75b64-237">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="75b64-238">Accédez à **Administration système \> Paramétrage \> Paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="75b64-238">Go to **System Administration \> Setup \> System parameters**.</span></span>
3. <span data-ttu-id="75b64-239">Dans l'onglet **Aide**, dans le champ **Configuration de l'aide de Lifecycle Services**, sélectionnez le projet LCS approprié (**RSAT** pour ce didacticiel).</span><span class="sxs-lookup"><span data-stu-id="75b64-239">On the **Help** tab, in the **Lifecycle Services help configuration** field, select the relevant LCS project (**RSAT** for this tutorial).</span></span>

    ![Champ Aide de Lifecycle Services sous l'onglet d'aide](./media/setup_rsa_tool_25.png)

    <span data-ttu-id="75b64-241">Les bibliothèques BPM sont renseignées sous le projet LCS approprié.</span><span class="sxs-lookup"><span data-stu-id="75b64-241">BPM libraries are filled in under the appropriate LCS project.</span></span>

4. <span data-ttu-id="75b64-242">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-242">Select **Save**.</span></span>
5. <span data-ttu-id="75b64-243">Vous devez actualiser le navigateur pour afficher le contenu de l'aide mis à jour.</span><span class="sxs-lookup"><span data-stu-id="75b64-243">You might have to refresh the browser to see the updated Help content.</span></span>

    ![Notification sur l'actualisation du navigateur](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a><span data-ttu-id="75b64-245">Enregistrements de tâches</span><span class="sxs-lookup"><span data-stu-id="75b64-245">Task recordings</span></span>

> [!NOTE]
> <span data-ttu-id="75b64-246">Assurez-vous que tous les enregistrements de tâches démarrent dans le tableau de bord principal Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="75b64-246">Make sure that all your task recordings start on the main dashboard of Finance and Operations.</span></span> <span data-ttu-id="75b64-247">Faites en sorte que les différents enregistrements soient courts et concentrez-vous sur une tâche métier, comme la création d'une commande client.</span><span class="sxs-lookup"><span data-stu-id="75b64-247">Keep individual recordings short, and focus on one business task, such as creating a sales order.</span></span>

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a><span data-ttu-id="75b64-248">Créer un enregistrement de tâche et l'enregistre dans la bibliothèque BPM</span><span class="sxs-lookup"><span data-stu-id="75b64-248">Create a task recording and save it to the BPM library</span></span>

<span data-ttu-id="75b64-249">Créez un enregistrement de tâche correspondant que vous pouvez associer au processus métier simple qui a été créé dans la nouvelle bibliothèque BPM.</span><span class="sxs-lookup"><span data-stu-id="75b64-249">Create a corresponding task recording that you can attach to the simple business process that was created in the new BPM library.</span></span>

1. <span data-ttu-id="75b64-250">Ouvrez le client Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="75b64-250">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="75b64-251">Dans le tableau de bord principal, sélectionnez le bouton **Paramètres** (le symbole d'engrenage), puis sélectionnez **Enregistreur de tâches**.</span><span class="sxs-lookup"><span data-stu-id="75b64-251">On the main dashboard, select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>

    ![Commandes dans le menu Paramètres](./media/setup_rsa_tool_27.png)

3. <span data-ttu-id="75b64-253">Sélectionnez **Créer un enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="75b64-253">Select **Create recording**.</span></span>

    ![Bouton Créer un enregistrement](./media/setup_rsa_tool_28.png)

4. <span data-ttu-id="75b64-255">Renseignez les champs **Nom de l'enregistrement** et **Description de l'enregistrement**, puis sélectionnez **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-255">Fill in the **Recording name** and **Recording description** fields, and then select **Start**.</span></span>

    ![Champs Nom de l'enregistrement et Description de l'enregistrement](./media/setup_rsa_tool_29.png)

5. <span data-ttu-id="75b64-257">Enregistrez les étapes de la création d'un produit.</span><span class="sxs-lookup"><span data-stu-id="75b64-257">Record the steps for creating a product.</span></span> <span data-ttu-id="75b64-258">Lorsque vous avez terminé, sélectionnez **Arrêter** pour arrêter l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="75b64-258">When you've finished, select **Stop** to stop recording.</span></span>

    ![Étapes pour créer un produit](./media/setup_rsa_tool_30.png)

6. <span data-ttu-id="75b64-260">Sélectionnez **Enregistrer sur Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="75b64-260">Select **Save to Lifecycle Services**.</span></span>

    ![Options d'enregistrement](./media/setup_rsa_tool_31.png)

    <span data-ttu-id="75b64-262">Les informations sur la bibliothèque sont chargées à partir de LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-262">Library information is loaded from LCS.</span></span>

    ![Indicateur de progression](./media/setup_rsa_tool_32.png)

7. <span data-ttu-id="75b64-264">Sélectionnez la bibliothèque BPM pour y associer l'enregistrement de tâche</span><span class="sxs-lookup"><span data-stu-id="75b64-264">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="75b64-265">Pour ce didacticiel, sélectionnez la bibliothèque BPM **RSAT** créée précédemment et le processus métier **Créer un produit** sous celle-ci.</span><span class="sxs-lookup"><span data-stu-id="75b64-265">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Create a product** business process under it.</span></span> <span data-ttu-id="75b64-266">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="75b64-266">Then select **OK**.</span></span>

    ![Associer l'enregistrement de tâche avec une bibliothèque PM et un processus métier](./media/setup_rsa_tool_33.png)

    <span data-ttu-id="75b64-268">Un message « L'enregistrement dans Lifecycle Services a réussi » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="75b64-268">A "Saving to Lifecycle Services was successful" message appears.</span></span>

    ![Message d'enregistrement réussi dans LCS](./media/setup_rsa_tool_34.png)

8. <span data-ttu-id="75b64-270">Si vous souhaitez enregistrer l'enregistrement de tâche localement, puis le charger dans BPM via LCS, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="75b64-270">If you want to save the task recording locally and then upload it to BPM through LCS, follow these steps:</span></span>

    1. <span data-ttu-id="75b64-271">Une fois l'enregistrement terminé, sélectionnez **Enregistrer sur ce PC**.</span><span class="sxs-lookup"><span data-stu-id="75b64-271">After the recording is completed, select **Save to this PC**.</span></span>

        ![Options d'enregistrement](./media/setup_rsa_tool_35.png)

    2. <span data-ttu-id="75b64-273">Dans la barre de Notifications du navigateur, sélectionnez **Enregistrer** ou **Enregistrer sous** pour enregistrer le fichier sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="75b64-273">In the browser's Notification bar, select **Save** or **Save As** to save the file on your local computer.</span></span>

        ![Barre de notifications](./media/setup_rsa_tool_36.png)

    3. <span data-ttu-id="75b64-275">Accédez à la bibliothèque BPM **RSAT**, puis sélectionnez le processus métier par rapport auquel enregistrer l'enregistrement de tâche.</span><span class="sxs-lookup"><span data-stu-id="75b64-275">Go to the **RSAT** BPM library, and select the business process to save the task recording against.</span></span>
    4. <span data-ttu-id="75b64-276">Dans l'onglet **Vue d'ensemble**, sélectionnez **Charger**.</span><span class="sxs-lookup"><span data-stu-id="75b64-276">On the **Overview** tab, select **Upload**.</span></span>

        ![Bouton Charger](./media/setup_rsa_tool_37.png)

    5. <span data-ttu-id="75b64-278">Sélectionnez **Parcourir**, puis sélectionnez le fichier de .axtr que vous enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="75b64-278">Select **Browse**, and select the .axtr file that you saved earlier.</span></span> <span data-ttu-id="75b64-279">Sélectionnez **Charger**.</span><span class="sxs-lookup"><span data-stu-id="75b64-279">Then select **Upload**.</span></span>

        ![Sélection du fichier .axtr à charger](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a><span data-ttu-id="75b64-281">Tester la synchronisation de BPM avec Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="75b64-281">Test the synchronization from BPM to Azure DevOps</span></span>

<span data-ttu-id="75b64-282">Maintenant que l'enregistrement de tâche est associé au processus métier, vous devez valider le fait que le processus métier et l'enregistrement de tâche associé peuvent être synchronisés avec Azure DevOps en tant que fonction et scénario de test (respectivement) à l'aide de la fonction de synchronisation de VSTS dans LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-282">Now that a task recording is attached to the business process, you must validate that the business process and the associated task recording can be synced to Azure DevOps as a feature and a test case (respectively) by using the VSTS sync feature in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="75b64-283">Le type d'élément de travail correspondant qui est créé dans Azure DevOps est variable selon le modèle de processus sélectionné lors de la configuration du projet LCS avec Azure DevOps, comme décrit dans la section [Créer un nouveau projet Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="75b64-283">The corresponding work item type that is created in Azure DevOps will vary, depending on the process template that you selected when you configured the LCS project with Azure DevOps, as described in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span>

1. <span data-ttu-id="75b64-284">Accédez à la bibliothèque BPM, puis ouvrez la bibliothèque **RSAT** que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="75b64-284">Go to the BPM library, and open the **RSAT** library that you created earlier.</span></span>
2. <span data-ttu-id="75b64-285">Sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Synchronisation VSTS**.</span><span class="sxs-lookup"><span data-stu-id="75b64-285">Select the ellipsis button (**...**), and select **VSTS sync**.</span></span>

    ![Commande Synchronisation VSTS dans le menu Points de suspension](./media/setup_rsa_tool_39.png)

    <span data-ttu-id="75b64-287">Une fois la synchronisation de VSTS terminée, un onglet **Configuration requise** apparaît sur la gauche. Il comprend l'élément de travail Azure DevOps correspondant.</span><span class="sxs-lookup"><span data-stu-id="75b64-287">After VSTS sync is completed, a **Requirements** tab appears on the left side and includes the corresponding Azure DevOps work item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-288">L'élément de travail créé dans Azure DevOps a le nom de la bibliothèque BPM en préfixe de titre.</span><span class="sxs-lookup"><span data-stu-id="75b64-288">The work item that is created in Azure DevOps will have the BPM library name as the title prefix.</span></span>

    ![Onglet Configuration requise](./media/setup_rsa_tool_40.png)

3. <span data-ttu-id="75b64-290">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="75b64-290">Refresh the page.</span></span>
4. <span data-ttu-id="75b64-291">Sélectionnez le bouton représentant des points de suspension (**...**). Vous obtenez une option supplémentaire, **Synchroniser les cas de test**.</span><span class="sxs-lookup"><span data-stu-id="75b64-291">Select the ellipsis button (**...**). You will see an additional option, **Sync test cases**.</span></span> <span data-ttu-id="75b64-292">Sélectionnez cette option.</span><span class="sxs-lookup"><span data-stu-id="75b64-292">Select this option.</span></span>

    ![Commande Synchroniser les cas de test dans le menu Points de suspension](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > <span data-ttu-id="75b64-294">Si l'option **Synchroniser les cas de test** n'est pas disponible lorsque vous actualisez la page, accédez à la page principale de BPM, puis sélectionnez **Synchroniser les cas de test** pour toute la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="75b64-294">If the **Sync test cases** option isn't available after you refresh the page, go to main page for BPM, and select **Sync test cases** for the whole library itself.</span></span> <span data-ttu-id="75b64-295">Ainsi, vous forcez efficacement la synchronisation pour toute la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="75b64-295">In this way, you effectively force a synchronization for the whole library.</span></span>
    > 
    > ![Sélection de Synchroniser les cas de test pour toute la bibliothèque](./media/setup_rsa_tool_42.png)

    <span data-ttu-id="75b64-297">Une fois la synchronisation des cas de test terminée, un nouveau scénario de test est créé dans l'onglet **Configuration requise**.</span><span class="sxs-lookup"><span data-stu-id="75b64-297">After Sync test cases is completed, a new test case is created on the **Requirements** tab.</span></span>

    ![Nouveau scénario de test sous l'onglet Configuration requise](./media/setup_rsa_tool_43.png)

5. <span data-ttu-id="75b64-299">Accédez à votre projet Azure DevOps, puis sélectionnez **Tableaux \> Éléments de travail**.</span><span class="sxs-lookup"><span data-stu-id="75b64-299">Go to your Azure DevOps project, and select **Boards \> Work Items**.</span></span>

    ![Commande Éléments de travail sous Tableaux](./media/setup_rsa_tool_44.png)

6. <span data-ttu-id="75b64-301">Vérifiez que l'élément de travail et le scénario de test que vous avez créés via la synchronisation de BPM existent.</span><span class="sxs-lookup"><span data-stu-id="75b64-301">Validate that the work item and test case that you created through BPM synchronization exist.</span></span>

    ![Élément de travail et scénario de test](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a><span data-ttu-id="75b64-303">Installer et configurer RSAT</span><span class="sxs-lookup"><span data-stu-id="75b64-303">Install and Configure RSAT</span></span>

<span data-ttu-id="75b64-304">RSAT peut être installé sur tout ordinateur qui exécute Windows 10 et pouvant se connecter à l'environnement Finance and Operations via un navigateur Web (Internet Explorer ou Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="75b64-304">RSAT can be installed on any computer that runs Windows 10 and that can connect to the Finance and Operations environment via a web browser (Internet Explorer or Google Chrome).</span></span>

> [!NOTE]
> <span data-ttu-id="75b64-305">Avant d'installer une nouvelle version de l'outil, nous vous recommandons de désinstaller la version précédente.</span><span class="sxs-lookup"><span data-stu-id="75b64-305">Before you install a new version of the tool, we recommend that you uninstall the previous version.</span></span>

### <a name="install-an-authentication-certificate"></a><span data-ttu-id="75b64-306">Installation d'un certificat d'authentification</span><span class="sxs-lookup"><span data-stu-id="75b64-306">Install an authentication certificate</span></span>

<span data-ttu-id="75b64-307">Pour activer l'authentification, vous devez générer et installer un certificat sur l'ordinateur où RSAT s'exécute.</span><span class="sxs-lookup"><span data-stu-id="75b64-307">To enable authentication, you must generate and install a certificate on the same computer that RSAT is running on.</span></span>

#### <a name="generate-a-certificate"></a><span data-ttu-id="75b64-308">Générer un certificat</span><span class="sxs-lookup"><span data-stu-id="75b64-308">Generate a certificate</span></span>

1. <span data-ttu-id="75b64-309">Pour générer un fichier de certificat, ouvrez une fenêtre Microsoft Windows PowerShell en tant qu'administrateur, puis exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="75b64-309">To generate a certificate file, open a Microsoft Windows PowerShell window as an admin, and run the following command.</span></span>

    ```
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. <span data-ttu-id="75b64-310">Ouvrez le Gestionnaire de certificat en entrant **certlm.msc** dans la boîte de dialogue **Exécuter**, et vérifiez que le certificat **Certificat de test automatisé D365** est créé sous **Personnel \> Certificats**.</span><span class="sxs-lookup"><span data-stu-id="75b64-310">Open certificate manager by entering **certlm.msc** in the **Run** dialog box, and confirm that the **D365 Automated testing certificate** certificate is created under **Personal \> Certificates**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-311">Veillez à entrer **certlm.msc**, pas **certmgr.msc**, car les certificats sont stockés sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="75b64-311">Be sure to enter **certlm.msc**, not **certmgr.msc**, because the certificates are stored on the local computer.</span></span>

    ![Certificat de test automatisé D365](./media/setup_rsa_tool_46.png)

3. <span data-ttu-id="75b64-313">Cliquez avec le bouton droit sur le certificat, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="75b64-313">Right-click the certificate, and then select **Copy**.</span></span>
4. <span data-ttu-id="75b64-314">Accédez à **Autorités de certification racines de confiance \> Certificats**.</span><span class="sxs-lookup"><span data-stu-id="75b64-314">Go to **Trusted Root Certification Authorities \> Certificates**.</span></span>

    ![Dossier Certificats sous le dossier Autorités de certification racines de confiance](./media/setup_rsa_tool_47.png)

5. <span data-ttu-id="75b64-316">Dans le menu **Action**, sélectionnez **Coller** pour copier le certificat à l'emplacement **Autorités de certification racines de confiance**.</span><span class="sxs-lookup"><span data-stu-id="75b64-316">On the **Action** menu, select **Paste** to copy the certificate to the **Trusted Root Certification Authorities** location.</span></span>

    ![Commande Coller dans le menu Action](./media/setup_rsa_tool_48.png)

6. <span data-ttu-id="75b64-318">Pour obtenir l'empreinte du certificat installé, mais sans espaces ni caractères spéciaux, ouvrez une fenêtre Windows PowerShell en tant qu'administrateur, puis exécutez les commandes suivantes.</span><span class="sxs-lookup"><span data-stu-id="75b64-318">To get the thumbprint of the installed certificate, but without spaces or special characters, open a Windows PowerShell window as an admin, and run the following commands.</span></span>

    ```
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > <span data-ttu-id="75b64-319">Enregistrez l'empreinte, car vous en aurez besoin ultérieurement lorsque vous mettrez à jour les fichiers .wif du serveur d'objets d'application (AOS) et paramétrerez la configuration de RSAT.</span><span class="sxs-lookup"><span data-stu-id="75b64-319">Save the thumbprint, because you will need it later when you update the .wif files for Application Object Server (AOS) and set up the RSAT configuration.</span></span>

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a><span data-ttu-id="75b64-320">Configurer l'ordinateur AOS pour approuver la connexion</span><span class="sxs-lookup"><span data-stu-id="75b64-320">Configure the AOS computer to trust the connection</span></span>

> [!NOTE]
> <span data-ttu-id="75b64-321">Si l'environnement Finance and Operations est un environnement de niveau 2 ou plus, l'empreinte du certificat doit être mise à jour dans le fichier wif.config pour **tous** les ordinateurs AOS de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="75b64-321">If the Finance and Operations environment is a Tier 2+ environment, the certificate thumbprint must be updated in the wif.config file for **all** AOS computers for the environment.</span></span>

1. <span data-ttu-id="75b64-322">Établissez une connexion RDP (Remote Desktop Protocol) à l'ordinateur AOS.</span><span class="sxs-lookup"><span data-stu-id="75b64-322">Establish a Remote Desktop Protocol (RDP) connection to the AOS computer.</span></span> <span data-ttu-id="75b64-323">Les informations de connexion sont disponibles dans la page de détails d'environnement dans LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-323">Sign-in details are available on the environment details page in LCS.</span></span>
2. <span data-ttu-id="75b64-324">Ouvrez Microsoft Internet Information Services (IIS), puis recherchez **AOSService** dans la liste des sites.</span><span class="sxs-lookup"><span data-stu-id="75b64-324">Open Microsoft Internet Information Services (IIS), and find **AOSService** in the list of sites.</span></span>

    ![AOSService dans la liste des sites](./media/setup_rsa_tool_49.png)

3. <span data-ttu-id="75b64-326">Cliquez avec le bouton droit sur **Explorer** pour ouvrir le dossier **\<Lecteur\>: \\AosService\\Webroot**.</span><span class="sxs-lookup"><span data-stu-id="75b64-326">Right-click **Explore** to open the **\<Drive\>: \\AosService\\WebRoot** folder.</span></span> <span data-ttu-id="75b64-327">Cherchez le fichier **wif.config**.</span><span class="sxs-lookup"><span data-stu-id="75b64-327">Find the **wif.config** file.</span></span>

    ![Fichier wif.config dans le dossier Webroot](./media/setup_rsa_tool_50.png)

4. <span data-ttu-id="75b64-329">Mettez à jour le fichier **wif.config** en ajoutant une nouvelle entrée d'autorité pour votre certificat et le nom de l'autorité, comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="75b64-329">Update the **wif.config** file by adding a new authority entry for your certificate and authority name, as shown in the following example.</span></span>

    ```
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > <span data-ttu-id="75b64-330">Si plusieurs utilisateurs utilisent la même application Finance and Operations, chaque utilisateur doit générer des empreintes distinctes, et chacune de ces empreintes doit être ajoutée dans la section **\<clés\>**.</span><span class="sxs-lookup"><span data-stu-id="75b64-330">If multiple users are using the same Finance and Operations application, each user must generate separate thumbprints, and each of those thumbprints must be added in the **\<keys\>** section.</span></span>

5. <span data-ttu-id="75b64-331">S'il existe plusieurs ordinateurs AOS, répétez les étapes 3 à 4 pour chaque ordinateur supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="75b64-331">If there is more than one AOS computer, repeat steps 3 through 4 for each additional computer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-332">Contrairement aux environnements plus anciens de niveau 2, les nouveaux environnements de niveau 2 sont déployés avec deux instances AOS.</span><span class="sxs-lookup"><span data-stu-id="75b64-332">Unlike older Tier 2 environments, new Tier 2 environments are deployed with two AOS instances.</span></span>

6. <span data-ttu-id="75b64-333">Exécutez **iisreset** sur tous les ordinateurs AOS.</span><span class="sxs-lookup"><span data-stu-id="75b64-333">Run **iisreset** on all the AOS computers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-334">Si vous n'avez pas les droits d'administrateur pour exécuter **iisreset** sur un ordinateur de niveau 1, dans la page des détails d'environnement de LCS, sélectionnez Maintenance > Redémarrer les services.</span><span class="sxs-lookup"><span data-stu-id="75b64-334">If you don't have admin rights to run **iisreset** on a Tier 1 computer, on the Environment details page in LCS, select Maintain > Restart services.</span></span>

#### <a name="tier-2-environment"></a><span data-ttu-id="75b64-335">Environnement de niveau 2 ou plus</span><span class="sxs-lookup"><span data-stu-id="75b64-335">Tier 2+ environment</span></span>

<span data-ttu-id="75b64-336">Si un environnement Finance and Operations de niveau 2 ou plus (sandbox de test d'acceptation standard ou supérieur) est utilisé, vérifiez ou définissez le paramètre de registre suivant sur l'ordinateur où RSAT est installé.</span><span class="sxs-lookup"><span data-stu-id="75b64-336">If a Tier 2+ (Standard Acceptance Test sandbox or higher) Finance and Operations environment is used, verify or set the following registry setting on the computer where RSAT is installed.</span></span> <span data-ttu-id="75b64-337">Cette étape est obligatoire car elle permet d'éviter les erreurs d'authentification ou de connexion de RSAT.</span><span class="sxs-lookup"><span data-stu-id="75b64-337">This step is required because it helps you avoid authentication or RSAT connection errors.</span></span>

```
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a><span data-ttu-id="75b64-338">Installation de RSAT</span><span class="sxs-lookup"><span data-stu-id="75b64-338">Install RSAT</span></span>

1. <span data-ttu-id="75b64-339">Accédez à <https://www.microsoft.com/download/details.aspx?id=57357>, puis sélectionnez **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="75b64-339">Go to <https://www.microsoft.com/download/details.aspx?id=57357>, and select **Download**.</span></span>
2. <span data-ttu-id="75b64-340">Sélectionnez tous les fichiers, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="75b64-340">Select all the files, and then select **Next**.</span></span>

    ![Sélectionner tous les fichiers](./media/setup_rsa_tool_51.png)

3. <span data-ttu-id="75b64-342">Double-cliquez sur le module .msi pour exécuter le programme d'installation.</span><span class="sxs-lookup"><span data-stu-id="75b64-342">Double-click the .msi package to run the installer.</span></span> <span data-ttu-id="75b64-343">Puis, lorsque l'installation est terminée, sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-343">Then, when the installation is completed, select **Finish**.</span></span>

    ![Fichier de programme d'installation de RSAT](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a><span data-ttu-id="75b64-345">Installer Selenium et les pilotes du navigateur</span><span class="sxs-lookup"><span data-stu-id="75b64-345">Install Selenium and browser drivers</span></span>

<span data-ttu-id="75b64-346">Dans les versions précédentes de RSAT, vous deviez installer Selenium et les pilotes du navigateur.</span><span class="sxs-lookup"><span data-stu-id="75b64-346">In older versions of RSAT, you had to install Selenium and browser drivers.</span></span> <span data-ttu-id="75b64-347">Il n'est plus nécessaire d'installer ces pilotes. C'est fait automatiquement.</span><span class="sxs-lookup"><span data-stu-id="75b64-347">You no longer have to install these drivers because they are automatically installed.</span></span>

1. <span data-ttu-id="75b64-348">La première fois que vous ouvrez RSAT, vous êtes invité à télécharger et installer Selenium.</span><span class="sxs-lookup"><span data-stu-id="75b64-348">The first time that you open RSAT, you're prompted to automatically download and install Selenium.</span></span> <span data-ttu-id="75b64-349">Pour plus d'informations, voir la section [Configuration de RSAT](#configure-rsat).</span><span class="sxs-lookup"><span data-stu-id="75b64-349">For more information, see the [Configure RSAT](#configure-rsat) section.</span></span>
2. <span data-ttu-id="75b64-350">Avant d'exécuter scénario de test, vous êtes invité à télécharger et installer automatiquement le pilote de navigateur correspondant au navigateur par défaut sélectionné dans la configuration de RSAT.</span><span class="sxs-lookup"><span data-stu-id="75b64-350">Before you can run a test case, you're prompted to automatically download and install the browser driver that corresponds to the default browser that is selected in the RSAT configuration.</span></span> <span data-ttu-id="75b64-351">Pour plus d'informations, voir la section [Charger et exécuter des scénarios de test](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="75b64-351">For more information, see the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

## <a name="get-started-with-rsat"></a><span data-ttu-id="75b64-352">Mise en route de RSAT</span><span class="sxs-lookup"><span data-stu-id="75b64-352">Get started with RSAT</span></span>

### <a name="create-a-test-plan-and-test-suites"></a><span data-ttu-id="75b64-353">Création d'un plan de test et de suites de tests</span><span class="sxs-lookup"><span data-stu-id="75b64-353">Create a test plan and test suites</span></span>

1. <span data-ttu-id="75b64-354">Accédez au projet Azure DevOps, puis sélectionnez **Plans de test**.</span><span class="sxs-lookup"><span data-stu-id="75b64-354">Go to the Azure DevOps project, and select **Test Plans**.</span></span>

    ![Commande Plans de test](./media/setup_rsa_tool_53.png)

2. <span data-ttu-id="75b64-356">Sélectionnez **Nouveau plan de test**.</span><span class="sxs-lookup"><span data-stu-id="75b64-356">Select **New Test Plan**.</span></span>

    ![Bouton nouveau plan de test](./media/setup_rsa_tool_54.png)

3. <span data-ttu-id="75b64-358">Renseignez le champ **Nom**, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-358">Fill in the **Name** field, and then select **Create**.</span></span> <span data-ttu-id="75b64-359">Pour ce didacticiel, nommez le plan de test **Plan de test RSAT**.</span><span class="sxs-lookup"><span data-stu-id="75b64-359">For this tutorial, name the test plan **RSAT Test Plan**.</span></span>

    ![Boîte de dialogue Nouveau plan de test](./media/setup_rsa_tool_55.png)

4. <span data-ttu-id="75b64-361">Sélectionnez le signe plus (**+**), puis sélectionnez **Suite statique** pour créer une suite statique dans le nouveau plan de test.</span><span class="sxs-lookup"><span data-stu-id="75b64-361">Select the plus sign (**+**), and then select **Static suite** to create a static suite under the new test plan.</span></span> <span data-ttu-id="75b64-362">Nommez la suite de tests **T01 – Make to Stock**.</span><span class="sxs-lookup"><span data-stu-id="75b64-362">Name the new test suite **T01 – Make to Stock**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-363">Vous pouvez également créer une suite à base de requêtes, si vous souhaitez que les nouveaux scénarios de test BPM soient automatiquement envoyés à la suite de tests RSAT.</span><span class="sxs-lookup"><span data-stu-id="75b64-363">You can also create a query-based suite, if you want the new test cases from BPM to be automatically pulled into the RSAT test suite.</span></span>

    ![Créer une suite statique](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a><span data-ttu-id="75b64-365">Associer des scénarios de test à des suites de tests</span><span class="sxs-lookup"><span data-stu-id="75b64-365">Attach test cases to test suites</span></span>

1. <span data-ttu-id="75b64-366">Sélectionnez **Ajouter existant** sur le côté droit pour ajouter les scénarios de test existants à la suite de tests.</span><span class="sxs-lookup"><span data-stu-id="75b64-366">Select **Add existing** on the right side to add existing test cases to the test suite.</span></span>

    ![Bouton Ajouter existant](./media/setup_rsa_tool_57.png)

2. <span data-ttu-id="75b64-368">Dans la page **Ajouter les scénarios de test à la suite**, sélectionnez **Exécuter la requête**, puis sélectionnez le scénario de test à ajouter à la suite de tests.</span><span class="sxs-lookup"><span data-stu-id="75b64-368">On the **Add test cases to suite** page, select **Run query**, and then select the test case to add to the test suite.</span></span> <span data-ttu-id="75b64-369">Pour ce didacticiel, sélectionnez le scénario de test **Créer un nouveau produit**.</span><span class="sxs-lookup"><span data-stu-id="75b64-369">For this tutorial, select the **Create a new product** test case.</span></span> <span data-ttu-id="75b64-370">Sélectionnez ensuite **Ajouter des scénarios de test** dans le coin inférieur droit de la page (ce bouton n'est pas affiché dans l'illustration suivante).</span><span class="sxs-lookup"><span data-stu-id="75b64-370">Then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Bouton Exécuter la requête](./media/setup_rsa_tool_58.png)

    <span data-ttu-id="75b64-372">Le scénario de test est ajouté à la suite de tests **T01-Make to Stock**.</span><span class="sxs-lookup"><span data-stu-id="75b64-372">The test case is added to the **T01-Make to Stock** test suite.</span></span>

    ![Scénario de test ajouté à la suite de tests](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a><span data-ttu-id="75b64-374">Configurer RSAT</span><span class="sxs-lookup"><span data-stu-id="75b64-374">Configure RSAT</span></span>

1. <span data-ttu-id="75b64-375">Ouvrez RSAT.</span><span class="sxs-lookup"><span data-stu-id="75b64-375">Open RSAT.</span></span>

    ![Icône RSAT](./media/setup_rsa_tool_60.png)

2. <span data-ttu-id="75b64-377">Vous recevez un message d'avertissement indiquant que « Regression Suite Automation Tool a besoin de Selenium ; souhaitez-vous automatiquement le télécharger et l'installer maintenant ? »</span><span class="sxs-lookup"><span data-stu-id="75b64-377">You receive a warning message that states, "The Regression Suite Automation Tool requires Selenium, do you want to automatically download and install it now?"</span></span> <span data-ttu-id="75b64-378">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="75b64-378">Select **Yes**.</span></span>

    ![Message d'avertissement](./media/setup_rsa_tool_61.png)

3. <span data-ttu-id="75b64-380">Sélectionnez le bouton **Paramètres** (le symbole d'engrenage) dans l'angle supérieur droit, puis, dans la boîte de dialogue qui s'affiche, renseignez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="75b64-380">Select the **Settings** button (the gear symbol) in the upper-right corner, and then, in the dialog box that appears, fill in the following fields:</span></span>

    - <span data-ttu-id="75b64-381">**URL Azure DevOps** – Saisissez l'URL de votre projet Azure DevOps, telle que `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span><span class="sxs-lookup"><span data-stu-id="75b64-381">**Azure DevOps Url** – Enter the URL of your Azure DevOps project, such as `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span></span>
    - <span data-ttu-id="75b64-382">**Jeton d'accès** – Saisissez le jeton d'accès qui permet à l'outil de se connecter à Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-382">**Access Token** – Enter the access token that lets the tool connect to Azure DevOps.</span></span> <span data-ttu-id="75b64-383">Utilisez le jeton personnel d'accès créé précédemment dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="75b64-383">Use the personal access token that you created earlier in this tutorial.</span></span> <span data-ttu-id="75b64-384">Pour plus d'informations, voir [Authentifier l'accès à l'aide de jetons d'accès personnels](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="75b64-384">For more information, see [Authenticate access with personal access tokens](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span></span>
    - <span data-ttu-id="75b64-385">**Nom du projet** – Sélectionnez le nom de votre projet Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-385">**Project Name** – Select the name of your Azure DevOps project.</span></span>
    - <span data-ttu-id="75b64-386">**Plan de test** – Sélectionnez le plan de test Azure DevOps qui contient vos scénarios de test.</span><span class="sxs-lookup"><span data-stu-id="75b64-386">**Test Plan** – Select the Azure DevOps test plan that contains your test cases.</span></span> <span data-ttu-id="75b64-387">Pour plus d'informations, voir [Création d'un plan de test et de suites de tests](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span><span class="sxs-lookup"><span data-stu-id="75b64-387">For more information, see [Create test plans and test suites](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span></span> <span data-ttu-id="75b64-388">Après avoir sélectionné un plan de test, sélectionnez **Tester la connexion** pour tester votre connexion à Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-388">After you select a test plan, select **Test Connection** to test your connection to Azure DevOps.</span></span>
    - <span data-ttu-id="75b64-389">**Nom d'hôte** – Saisissez le nom d'hôte de l'environnement de test Finance and Operations, tel que **\<myaos\>.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="75b64-389">**Hostname** – Enter the host name of the Finance and Operations test environment, such as **\<myaos\>.cloudax.dynamics.com**.</span></span> <span data-ttu-id="75b64-390">N'incluez pas le préfixe **https://** ou **http://**.</span><span class="sxs-lookup"><span data-stu-id="75b64-390">Don't include the **https://** or **http://** prefix.</span></span>
    - <span data-ttu-id="75b64-391">**Nom d'hôte SOAP** – Saisissez le nom d'hôte SOAP de l'environnement de test Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="75b64-391">**SOAP Hostname** – Enter the SOAP host name of the Finance and Operations test environment.</span></span> <span data-ttu-id="75b64-392">Généralement, le nom d'hôte SOAP est identique au nom d'hôte, mais avec le suffixe **SOAP**.</span><span class="sxs-lookup"><span data-stu-id="75b64-392">Typically, the SOAP host name is the same as the host name, but it has a **soap** suffix.</span></span> <span data-ttu-id="75b64-393">Voici un exemple : **\<myaos\>soap.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="75b64-393">Here is an example: **\<myaos\>soap.cloudax.dynamics.com**.</span></span> <span data-ttu-id="75b64-394">N'incluez pas le préfixe **https://** ou **http://**.</span><span class="sxs-lookup"><span data-stu-id="75b64-394">Don't include the **https://** or **http://** prefix.</span></span>

        > [!NOTE]
        > <span data-ttu-id="75b64-395">Pour rechercher le nom d'hôte et le nom d'hôte SOAP, ouvrez le Gestionnaire IIS, cliquez avec le bouton droit sur **Sites \> AOSService**, puis sélectionnez **Modifier les liaisons**.</span><span class="sxs-lookup"><span data-stu-id="75b64-395">To find the host name and SOAP host name, open IIS Manager, right-click **Sites \> AOSService**, and then select **Edit bindings**.</span></span> <span data-ttu-id="75b64-396">Les valeurs de la colonne **Nom d'hôte** vous indiquent le nom d'hôte et le nom d'hôte SOAP (le nom d'hôte SOAP a le suffixe **soap** dans l'URL).</span><span class="sxs-lookup"><span data-stu-id="75b64-396">The values in the **Host Name** column give you the host name and SOAP host name (the SOAP host name has the suffix **soap** in the URL).</span></span>

        ![Nom d'hôte et nom d'hôte SOAP dans la colonne Nom d'hôte](./media/setup_rsa_tool_63.png)

    - <span data-ttu-id="75b64-398">**Nom d'utilisateur administrateur** – Saisissez l'adresse e-mail de l'utilisateur administrateur dans l'environnement de test Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="75b64-398">**Admin user name** – Enter the email address of an admin user in the Finance and Operations test environment.</span></span>
    - <span data-ttu-id="75b64-399">**Empreinte** – Saisissez l'empreinte du certificat d'authentification, comme décrit précédemment dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="75b64-399">**Thumbprint** – Enter the thumbprint of the authentication certificate, as described earlier in this tutorial.</span></span>
    - <span data-ttu-id="75b64-400">**Répertoire de travail** – Spécifiez l'emplacement du dossier de stockage des fichiers d'automatisation des tests, tels que les fichiers des données de test Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-400">**Working directory** – Specify the folder location for storing test automation files, such as Excel test data files.</span></span> <span data-ttu-id="75b64-401">Par exemple, entrez ou sélectionnez **C:\\Temp\\RegressionTool**.</span><span class="sxs-lookup"><span data-stu-id="75b64-401">For example, enter or select **C:\\Temp\\RegressionTool**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="75b64-402">Si le nom du dossier comporte des espaces, l'exécution échouera car le dossier sera introuvable.</span><span class="sxs-lookup"><span data-stu-id="75b64-402">If the name of the folder has spaces, execution will fail because the folder can't be found.</span></span> <span data-ttu-id="75b64-403">Ce problème est connu et doit être résolu dans la dernière version de l'outil.</span><span class="sxs-lookup"><span data-stu-id="75b64-403">This issue is a known issue and should be fixed in the latest version of the tool.</span></span>

    - <span data-ttu-id="75b64-404">**Navigateur par défaut** – Sélectionnez **Internet Explorer** ou **Google Chrome**.</span><span class="sxs-lookup"><span data-stu-id="75b64-404">**Default browser** – Select either **Internet Explorer** or **Google Chrome**.</span></span> <span data-ttu-id="75b64-405">Assurez-vous que les pilotes de navigateur appropriés ont été installés.</span><span class="sxs-lookup"><span data-stu-id="75b64-405">Make sure that the appropriate browser drivers have been installed.</span></span>
    - <span data-ttu-id="75b64-406">**Délai d'exécution du test** – Spécifiez le délai d'expiration, en minutes, pour l'exécution des tests.</span><span class="sxs-lookup"><span data-stu-id="75b64-406">**Test run timeout** – Specify the time-out period, in minutes, for test runs.</span></span> <span data-ttu-id="75b64-407">Une fois le délai d'expiration dépassé, toutes les fenêtres actives sont fermées et les scénarios de test en attente échouent.</span><span class="sxs-lookup"><span data-stu-id="75b64-407">When the time-out period elapses, all active windows are closed, and pending test cases fail.</span></span>
    - <span data-ttu-id="75b64-408">**Délai d'action du test** – Ce champ détermine la période d'expiration, en minutes, pour les requêtes de serveur de l'environnement Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="75b64-408">**Test action timeout** – This field controls the time-out period, in minutes, for Finance and Operation environment server requests.</span></span> <span data-ttu-id="75b64-409">Généralement, la valeur par défaut (2 minutes) doit être suffisante.</span><span class="sxs-lookup"><span data-stu-id="75b64-409">Usually, the default value (2 minutes) should be enough.</span></span> <span data-ttu-id="75b64-410">Toutefois, pour les environnements plus lents, vous aurez peut-être besoin d'augmenter cette valeur en cas d'erreurs liées au délai d'expiration.</span><span class="sxs-lookup"><span data-stu-id="75b64-410">However, for slower environments, you might want to increase the value if errors that are related to time-outs occur.</span></span>
    - <span data-ttu-id="75b64-411">**Nom de la société** – Entrez le nom de la société à utiliser comme votre société Finance and Operations par défaut lors de la création des fichiers de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-411">**Company name** – Enter the company name to use as your default Finance and Operations company when Excel parameter files are created.</span></span> <span data-ttu-id="75b64-412">Vous pourrez modifier la société ultérieurement en modifiant le fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-412">You can change the company later by editing the Excel parameter file.</span></span>

    ![Boîte de dialogue Paramètres](./media/setup_rsa_tool_62.png)

4. <span data-ttu-id="75b64-414">Sélectionnez **Appliquer** pour appliquer et enregistrer les paramètres.</span><span class="sxs-lookup"><span data-stu-id="75b64-414">Select **Apply** to apply and save your settings.</span></span>

    <span data-ttu-id="75b64-415">Pour enregistrer vos paramètres actuels dans un fichier de configuration sur votre ordinateur, sélectionnez **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="75b64-415">To save your current settings to a configuration file on your computer, select **Save as**.</span></span> <span data-ttu-id="75b64-416">Pour restaurer vos paramètres à partir d'un fichier de configuration sur votre ordinateur, sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="75b64-416">To restore your settings from a configuration file on your computer, select **Open**.</span></span>

5. <span data-ttu-id="75b64-417">Sélectionnez **Fermer** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="75b64-417">Select **Close** to close the dialog box.</span></span>

### <a name="load-and-run-test-cases"></a><span data-ttu-id="75b64-418">Charger et exécuter des scénarios de test</span><span class="sxs-lookup"><span data-stu-id="75b64-418">Load and run test cases</span></span>

1. <span data-ttu-id="75b64-419">Sélectionner **Charger** pour charger le **Plan de test RSAT** à partir du projet Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-419">Select **Load** to load the **RSAT Test Plan** test plan from the Azure DevOps project.</span></span>

    ![Bouton Charger](./media/setup_rsa_tool_64.png)

2. <span data-ttu-id="75b64-421">Sélectionnez le scénario de test **Créer un nouveau produit** à partir de la suite de test, puis sélectionnez **Nouveau \> Générer des fichiers de paramètre et d'exécution de test**.</span><span class="sxs-lookup"><span data-stu-id="75b64-421">Select the **Create a new product** test case from the test suite, and then select **New \> Generate Test Execution and Parameter files**.</span></span>

    ![Commande Générer des fichiers de paramètre et d'exécution de test dans le menu Nouveau](./media/setup_rsa_tool_65.png)

    <span data-ttu-id="75b64-423">Le fichier de paramètres Excel est créé dans le dossier local que vous avez spécifié dans la configuration RSAT (par exemple, **C:\\Temp\\RegressionTool**).</span><span class="sxs-lookup"><span data-stu-id="75b64-423">The Excel parameter file is created in the local folder that you specified in the RSAT configuration (for example, **C:\\Temp\\RegressionTool**).</span></span>

    ![Fichier de paramètres Excel créé](./media/setup_rsa_tool_66.png)

3. <span data-ttu-id="75b64-425">Si vous souhaitez enregistrer les fichiers de paramètres, sélectionnez **Charger**.</span><span class="sxs-lookup"><span data-stu-id="75b64-425">If you want to save the parameter files, select **Upload**.</span></span> <span data-ttu-id="75b64-426">Les fichiers d'automatisation de test de tous les scénarios de test sélectionnés sont chargés vers Azure DevOps pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="75b64-426">Test automation files of all selected test cases are uploaded to Azure DevOps for future use.</span></span> <span data-ttu-id="75b64-427">(Ils incluent les fichiers de paramètres de test Excel.)</span><span class="sxs-lookup"><span data-stu-id="75b64-427">(These files include Excel test parameter files.)</span></span>

    <span data-ttu-id="75b64-428">De cette manière, vous pouvez sélectionner **Charge** pour charger les fichiers de paramètres (et les fichiers d'automatisation) du scénario de test directement depuis Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-428">In this way, you can select **Load** to load the parameter files (and automation files) from the test case directly from Azure DevOps.</span></span> <span data-ttu-id="75b64-429">Vous n'avez pas besoin de générer de nouveau les fichiers de paramètres.</span><span class="sxs-lookup"><span data-stu-id="75b64-429">You don't have to regenerate the parameter files.</span></span> <span data-ttu-id="75b64-430">Cette approche aura de l'importance ultérieurement, lorsque vous souhaiterez conserver les modifications dans le fichier de paramètres et ne souhaiterez pas qu'elles soient écrasées.</span><span class="sxs-lookup"><span data-stu-id="75b64-430">This approach will become important later, when you want to keep the modifications in the parameter file and don't want them to be overwritten.</span></span>

4. <span data-ttu-id="75b64-431">Pour vérifier que les fichiers d'automatisation et les fichiers de paramètres sont enregistrés dans Azure DevOps, accédez au projet Azure DevOps, sélectionnez **Tableaux \> Éléments de travail**, puis sélectionnez le scénario de test **Créer un nouveau produit**.</span><span class="sxs-lookup"><span data-stu-id="75b64-431">To verify that the automation files and parameter files are saved to Azure DevOps, go to the Azure DevOps project, select **Boards \> Work Items**, and select the **Create a new product** test case.</span></span> <span data-ttu-id="75b64-432">Dans l'onglet **Pièces jointes**, vous devez voir quatre fichiers :</span><span class="sxs-lookup"><span data-stu-id="75b64-432">On the **Attachments** tab, you should see four files:</span></span>

    - <span data-ttu-id="75b64-433">**.cs** – Fichier d'automatisation C\#</span><span class="sxs-lookup"><span data-stu-id="75b64-433">**.cs** – C\# automation file</span></span>
    - <span data-ttu-id="75b64-434">**.dll** – Fichier d'automatisation compilé comme assembly</span><span class="sxs-lookup"><span data-stu-id="75b64-434">**.dll** – Compiled automation file as an assembly</span></span>
    - <span data-ttu-id="75b64-435">**.xlsx** – Fichier de paramètres Excel</span><span class="sxs-lookup"><span data-stu-id="75b64-435">**.xlsx** – Excel parameter file</span></span>
    - <span data-ttu-id="75b64-436">**.xml** – Fichier d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="75b64-436">**.xml** – Recording file</span></span>

    ![Fichiers sous l'onglet Pièces jointes](./media/setup_rsa_tool_67.png)

5. <span data-ttu-id="75b64-438">Sélectionnez le scénario de test à exécuter, puis sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="75b64-438">Select the test case to run, and then select **Run**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-439">Avant d'exécuter des scénarios de test, si vous utilisez Internet Explorer comme navigateur, vérifiez que la résolution de votre bureau est définie sur **100%** dans les **Paramètres d'affichage Windows \> Échelle et mise en page**.</span><span class="sxs-lookup"><span data-stu-id="75b64-439">Before you run test cases, if you're using Internet Explorer as the browser, make sure that your desktop resolution is set to **100%** at **Windows Display settings \> Scale and layout**.</span></span> <span data-ttu-id="75b64-440">Si vous ne pouvez pas modifier ce paramètre sur un ordinateur virtuel (VM), changez-le sur le client (ordinateur portable) à partir duquel vous accédez à l'ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="75b64-440">If you can't change this setting on a virtual machine (VM), change it on the client (laptop) that you're trying to access the VM from.</span></span> <span data-ttu-id="75b64-441">Les paramètres de résolution seront alors hérités par les paramètres d'affichage de l'ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="75b64-441">The resolution settings will then be inherited by the VM display settings.</span></span>

    ![Résolution du bureau définie sur 100 %](./media/setup_rsa_tool_68.png)

6. <span data-ttu-id="75b64-443">Si les pilotes de navigateur ne sont pas installés dans le système, vous recevez un message d'avertissement qui indique « Cette opération nécessite le pilote \<nom du navigateur\> ;</span><span class="sxs-lookup"><span data-stu-id="75b64-443">If the browser drivers aren't installed in the system, you receive a warning message that states, "This operation requires the \<browser name\> driver.</span></span> <span data-ttu-id="75b64-444">souhaitez-vous automatiquement le télécharger et l'installer maintenant ? »</span><span class="sxs-lookup"><span data-stu-id="75b64-444">Do you want to automatically downloads and install it now?"</span></span> <span data-ttu-id="75b64-445">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="75b64-445">Select **Yes**.</span></span>

    ![Message d'avertissement pour Internet Explorer](./media/setup_rsa_tool_69.png)

    ![Message d'avertissement pour Chrome](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > <span data-ttu-id="75b64-448">Si votre navigateur est Chrome et que vous recevez un message d'erreur indiquant que la session n'a pas été créée car la version de Chrome n'est pas appropriée, chargez le dernier pilote Chrome depuis <http://chromedriver.chromium.org/downloads> vers le dossier **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium**.</span><span class="sxs-lookup"><span data-stu-id="75b64-448">If you're using Chrome as the browser and receive an error message that states that the session wasn't created because the Chrome version isn't correct, download the latest Chrome driver from <http://chromedriver.chromium.org/downloads> to the **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** folder.</span></span>

    ![Message d'erreur pour Chrome](./media/setup_rsa_tool_71.png)

    <span data-ttu-id="75b64-450">Le scénario de test est exécuté, et le champ **Résultat** est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="75b64-450">The test case is run, and the **Result** field is updated.</span></span>

    ![Indicateur de progression](./media/setup_rsa_tool_72.png)

    <span data-ttu-id="75b64-452">Si vous avez suivi ce didacticiel tel qu'il a été écrit, le scénario de test **Créer un nouveau produit** doit échouer, car l'enregistrement de tâche de création de produit a enregistré le nom du produit comme une valeur codée en dur.</span><span class="sxs-lookup"><span data-stu-id="75b64-452">If you've followed this tutorial as it's written, the **Create a new product** test case will fail, because the task recording for creating a product saved the product name as a hard-coded value.</span></span> <span data-ttu-id="75b64-453">Si vous réexécutez le même scénario de test, vous devez recevoir un message d'erreur, car le produit existe déjà.</span><span class="sxs-lookup"><span data-stu-id="75b64-453">If you rerun the same test case, you should receive an error message, because the product already exists.</span></span>

    ![Champ de résultat défini sur Échec](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a><span data-ttu-id="75b64-455">Afficher les résultats du test</span><span class="sxs-lookup"><span data-stu-id="75b64-455">View the test results</span></span>

1. <span data-ttu-id="75b64-456">Double-cliquez sur le scénario de test défaillant.</span><span class="sxs-lookup"><span data-stu-id="75b64-456">Double-click the failed test case.</span></span>

    <span data-ttu-id="75b64-457">Vous recevez un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="75b64-457">You receive an error message.</span></span>

    ![Message d'erreur](./media/setup_rsa_tool_73.png)

2. <span data-ttu-id="75b64-459">Sélectionnez **Détails** pour afficher le message d'erreur entier.</span><span class="sxs-lookup"><span data-stu-id="75b64-459">Select **Details** to view the whole error message.</span></span>

    ![Message d'erreur entier](./media/setup_rsa_tool_74.png)

3. <span data-ttu-id="75b64-461">Pour afficher une version détaillée du message d'erreur dans Azure DevOps, sélectionnez **Ouvrir dans Azure DevOps**.</span><span class="sxs-lookup"><span data-stu-id="75b64-461">To view a detailed version of the error message in Azure DevOps, select **Open in Azure DevOps**.</span></span> <span data-ttu-id="75b64-462">Dans Azure DevOps, vous pouvez afficher le statut du scénario de test et le message d'erreur détaillé.</span><span class="sxs-lookup"><span data-stu-id="75b64-462">In Azure DevOps, you can view the status of the test case and the detailed error message.</span></span>

    ![Message d'erreur détaillé dans Azure DevOps](./media/setup_rsa_tool_75.png)

4. <span data-ttu-id="75b64-464">Pour afficher les résultats du test directement dans le projet Azure DevOps, accédez à **Plans de test \> Plans de test \> Exécutions**.</span><span class="sxs-lookup"><span data-stu-id="75b64-464">To view the test results directly in the Azure DevOps project, go to **Test Plans \> Test Plans \> Runs**.</span></span> <span data-ttu-id="75b64-465">Double-cliquez sur le test exécuté pour lequel vous souhaitez afficher plus de détails.</span><span class="sxs-lookup"><span data-stu-id="75b64-465">Double-click the test run that you want to see more details for.</span></span>

    ![Liste des exécutions de test dans Azure DevOps](./media/setup_rsa_tool_76.png)

5. <span data-ttu-id="75b64-467">L'onglet **Récapitulatif d'exécution** indique que le scénario de test a échoué, mais il ne comprend pas le message d'erreur proprement dit.</span><span class="sxs-lookup"><span data-stu-id="75b64-467">The **Run summary** tab indicates that the test case failed, but it doesn't provide the actual error message.</span></span> <span data-ttu-id="75b64-468">Pour afficher le message d'erreur détaillé, sélectionnez l'onglet **Résultats du test**.</span><span class="sxs-lookup"><span data-stu-id="75b64-468">To view the detailed error message, select the **Test results** tab.</span></span>

    ![Onglet Récapitulatif d'exécution](./media/setup_rsa_tool_77.png)

    <span data-ttu-id="75b64-470">L'onglet **Résultats du test** fournit des informations sur le scénario de test, ainsi que les résultats et le message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="75b64-470">The **Test results** tab provides the test case information, together with the outcome and the error message.</span></span>

    ![Onglet Résultats du test](./media/setup_rsa_tool_78.png)

6. <span data-ttu-id="75b64-472">Double-cliquez sur l'enregistrement approprié pour afficher le message d'erreur détaillé.</span><span class="sxs-lookup"><span data-stu-id="75b64-472">Double-click the relevant record to view the detailed error message.</span></span>

    ![Message d'erreur détaillé](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > <span data-ttu-id="75b64-474">Tous les messages d'erreur sont également disponibles localement dans **C:\\Utilisateurs\\\$Notrenomdutilisateur\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span><span class="sxs-lookup"><span data-stu-id="75b64-474">All error messages are also available locally in **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span></span>

7. <span data-ttu-id="75b64-475">Vous pouvez également exporter les résultats d'exécution de test depuis le niveau de plan de test en sélectionnant **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="75b64-475">You can also export the test run results from the test plan level by selecting **Export**.</span></span>

    ![Exporter un plan de test](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a><span data-ttu-id="75b64-477">Modifier le fichier de paramètres Excel</span><span class="sxs-lookup"><span data-stu-id="75b64-477">Modify the Excel parameter file</span></span>

1. <span data-ttu-id="75b64-478">Ouvrez RSAT.</span><span class="sxs-lookup"><span data-stu-id="75b64-478">Open RSAT.</span></span>
2. <span data-ttu-id="75b64-479">Sélectionnez le scénario de test, puis sélectionnez **Modifier** pour ouvrir le fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-479">Select the test case, and then select **Edit** to open the Excel parameter file.</span></span>

    <span data-ttu-id="75b64-480">Dans l'écran **EcoResProductCreate**, notez que la valeur du champ **Numéro de produit** est codée en dur.</span><span class="sxs-lookup"><span data-stu-id="75b64-480">On the **EcoResProductCreate** sheet, notice that the value of the **Product number** field is hard-coded.</span></span> <span data-ttu-id="75b64-481">Vous devez mettre ce champ à jour à un nouveau numéro de produit avant d'exécuter de nouveau le scénario de test.</span><span class="sxs-lookup"><span data-stu-id="75b64-481">You must update this field to a new product number before you run the test case again.</span></span>

3. <span data-ttu-id="75b64-482">Pour générer un numéro de produit unique pour chaque exécution sans devoir rouvrir le fichier de paramètres Excel et mettre manuellement le numéro de produit à jour à chaque fois, utilisez la formule Excel suivante.</span><span class="sxs-lookup"><span data-stu-id="75b64-482">To generate a unique product number for each run without having to reopen the Excel parameter file and manually update the product number every time, use the following Excel formula.</span></span>

    ```
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > <span data-ttu-id="75b64-483">Outre l'onglet **Général**, le fichier de paramètres Excel contient un onglet de données pour chaque page de formulaire Finance and Operations visitée par le scénario de test.</span><span class="sxs-lookup"><span data-stu-id="75b64-483">In addition to the **General** tab, the Excel parameter file contains a data tab for every Finance and Operations form page the test case visits.</span></span>

    ![Champ Numéro de produit](./media/setup_rsa_tool_81.png)

4. <span data-ttu-id="75b64-485">Sélectionnez **Enregistrer**, puis fermez le classeur Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-485">Select **Save**, and then close the Excel workbook.</span></span>
5. <span data-ttu-id="75b64-486">Sélectionnez **Charger** pour enregistrer le fichier de paramètres Excel dans Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-486">Select **Upload** to save the Excel parameter file to Azure DevOps.</span></span>

    ![Message de chargement réussi](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > <span data-ttu-id="75b64-488">Pour exécuter des scénarios de test dans un contexte d'utilisateur spécifique, entrez l'identificater e-mail de l'utilisateur dans le champ **Utilisateur du test** de l'onglet **Général** du fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-488">To run test cases in a specific user context, enter the user's email ID in the **Test User** field on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="75b64-489">Dans la dernière version de RSAT, la mise en page des champs dans le fichier de paramètres Excel a été mise à jour, mais le concept reste le même.</span><span class="sxs-lookup"><span data-stu-id="75b64-489">In the latest version of RSAT, the layout of the fields in the Excel parameter file has been updated, but the concept remains the same.</span></span>
    >
    > ![Champ Utilisateur du test](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a><span data-ttu-id="75b64-491">Valider les résultats</span><span class="sxs-lookup"><span data-stu-id="75b64-491">Validate the results</span></span>

- <span data-ttu-id="75b64-492">Sélectionnez **Exécuter** pour réexécuter le scénario de test, puis vérifier que le scénario de test a réussi.</span><span class="sxs-lookup"><span data-stu-id="75b64-492">Select **Run** to rerun the test case, and verify that the test case has passed.</span></span> <span data-ttu-id="75b64-493">Vous pouvez afficher les résultats du test de la manière décrite dans la section [Afficher les résultats du test](#view-the-test-results).</span><span class="sxs-lookup"><span data-stu-id="75b64-493">You can view the test results as described in the [View the test results](#view-the-test-results) section.</span></span>

    ![Champ de résultat défini sur Réussite](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a><span data-ttu-id="75b64-495">Enchaînement de scénarios de test</span><span class="sxs-lookup"><span data-stu-id="75b64-495">Chaining of test cases</span></span>

<span data-ttu-id="75b64-496">Une des fonctions essentielles de RSAT est l'enchaînement de scénarios de test (c'est-à-dire, la capacité d'un test de transmettre des valeurs à d'autres tests).</span><span class="sxs-lookup"><span data-stu-id="75b64-496">One key feature of RSAT is the chaining of test cases (that is, the capability of a test to pass values to other tests).</span></span> <span data-ttu-id="75b64-497">Les scénarios de test sont exécutés dans l'ordre défini dans le plan de test Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-497">Test cases are run according to their defined order in the Azure DevOps test plan.</span></span> <span data-ttu-id="75b64-498">(Cet ordre peut également être mis à jour dans l'outil de test lui-même.) Par conséquent, si vous souhaitez transmettre des variables d'un scénario de test à un autre, il est primordial que les tests soient dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="75b64-498">(This order can also be updated in the test tool itself.) Therefore, if you want to pass variables from one test case to another, it's very important that the tests be in the correct order.</span></span>

<span data-ttu-id="75b64-499">Dans cette section, vous allez créer une variable enregistrée dans le premier scénario de test, créer un second scénario de test, puis transmettre la variable enregistrée du premier scénario de test vers le second.</span><span class="sxs-lookup"><span data-stu-id="75b64-499">In this section, you will create a saved variable in the first test case, create a second test case, and pass the saved variable from the first test case to the second test case.</span></span> <span data-ttu-id="75b64-500">Vous exécuterez ensuite les scénarios de test comme scénario de test enchaîné dans RSAT.</span><span class="sxs-lookup"><span data-stu-id="75b64-500">You will then run the test cases as a chained test case in RSAT.</span></span>

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a><span data-ttu-id="75b64-501">Modifier un enregistrement de tâche existant pour créer une variable enregistrée</span><span class="sxs-lookup"><span data-stu-id="75b64-501">Modify an existing task recording to create a saved variable</span></span>

1. <span data-ttu-id="75b64-502">Ouvrez le client Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="75b64-502">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="75b64-503">Sélectionnez le bouton **Paramètres** (le symbole d'engrenage), puis sélectionnez **Enregistreur de tâches**.</span><span class="sxs-lookup"><span data-stu-id="75b64-503">Select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>
3. <span data-ttu-id="75b64-504">Sélectionnez **Modifier l'enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="75b64-504">Select **Edit Recording**.</span></span>

    ![Bouton Modifier l'enregistrement](./media/setup_rsa_tool_85.png)

4. <span data-ttu-id="75b64-506">Sélectionnez **Ouvrir à partir de Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="75b64-506">Select **Open from Lifecycle Services**.</span></span>

    ![Bouton Ouvrir à partir de Lifecycle Services](./media/setup_rsa_tool_86.png)

5. <span data-ttu-id="75b64-508">Sélectionnez **Sélectionner la bibliothèque Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="75b64-508">Select **Select the Lifecycle Services library**.</span></span>

    ![Bouton Sélectionner la bibliothèque Lifecycle Services](./media/setup_rsa_tool_87.png)

    <span data-ttu-id="75b64-510">Les bibliothèques BPM sont chargées depuis LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-510">BPM libraries are loaded from LCS.</span></span>

    ![Indicateur de progression](./media/setup_rsa_tool_88.png)

6. <span data-ttu-id="75b64-512">Une fois les bibliothèques BPM chargées depuis LCS, sélectionnez la bibliothèque BPM **RSAT** et le processus métier **Créer un nouveau produit** auquel l'enregistrement de tâche a été associé.</span><span class="sxs-lookup"><span data-stu-id="75b64-512">After the BPM libraries are loaded from LCS, select the **RSAT** BPM library and the **Create a new product** business process that the task recording was associated with.</span></span> <span data-ttu-id="75b64-513">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="75b64-513">Then select **OK**.</span></span>

    ![Sélection d'une bibliothèque BPM et d'un processus métier](./media/setup_rsa_tool_89.png)

7. <span data-ttu-id="75b64-515">Nom de l'enregistrement de tâche approprié est entré dans le champ **Nom de l'enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="75b64-515">The name of the appropriate task recording is entered in the **Recording name** field.</span></span> <span data-ttu-id="75b64-516">Sélectionnez **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-516">Select **Start**.</span></span>

    ![Nom de l'enregistrement de tâche dans le champ Nom de l'enregistrement](./media/setup_rsa_tool_90.png)

8. <span data-ttu-id="75b64-518">Accédez à **Gestion des informations produit \> Produits**, puis sélectionnez **Nouveau** pour ouvrir la page dans lequel l'enregistrement de tâche d'origine, **Créez un produit**, a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="75b64-518">Go to **Product information management \> Products**, and select **New** to open the page where the original task recording, **Create a product**, was recorded.</span></span>
9. <span data-ttu-id="75b64-519">Sélectionnez **Insérer une étape**.</span><span class="sxs-lookup"><span data-stu-id="75b64-519">Select **Insert step**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-520">La nouvelle étape est insérée **après** l'étape sélectionnée dans le volet.</span><span class="sxs-lookup"><span data-stu-id="75b64-520">The new step is inserted **after** the step that you selected in the pane.</span></span>

    ![Bouton Insérer une étape](./media/setup_rsa_tool_91.png)

10. <span data-ttu-id="75b64-522">Cliquez avec le bouton droit sur le champ **Numéro de produit**, puis sélectionnez **Enregistreur de tâches \> Copier**.</span><span class="sxs-lookup"><span data-stu-id="75b64-522">Right-click the **Product number** field, and then select **Task recorder \> Copy**.</span></span>

    ![Commande Copier](./media/setup_rsa_tool_92.png)

11. <span data-ttu-id="75b64-524">Une nouvelle étape est ajoutée dans le volet.</span><span class="sxs-lookup"><span data-stu-id="75b64-524">A new step is added in the pane.</span></span> <span data-ttu-id="75b64-525">Notez la valeur dans le champ **Numéro de produit**, car vous en aurez besoin ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="75b64-525">Make a note of the value in the **Product number** field, because you will need it later.</span></span>

    ![Nouvelle étape ajoutée](./media/setup_rsa_tool_93.png)

12. <span data-ttu-id="75b64-527">Sélectionnez **Modification terminée**.</span><span class="sxs-lookup"><span data-stu-id="75b64-527">Select **Done editing**.</span></span>
13. <span data-ttu-id="75b64-528">Sélectionnez **Enregistrer sur Lifecycle Services**, puis associez le nouvel enregistrement de tâche avec les mêmes bibliothèque BPM et processus métier que ceux auxquels était associé l'enregistrement de tâche d'origine.</span><span class="sxs-lookup"><span data-stu-id="75b64-528">Select **Save to Lifecycle Services**, and associate the new task recording with the same BPM library and business process that the original task recording was associated with.</span></span> <span data-ttu-id="75b64-529">Pour plus d'informations, voir la section [Créer un enregistrement de tâche et l'enregistrer dans la bibliothèque BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="75b64-529">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>
14. <span data-ttu-id="75b64-530">Accédez à la bibliothèque de BPM, puis sélectionnez **Synchroniser les cas de test** pour remplacer l'enregistrement de tâche associé au scénario de test dans Azure DevOps, comme décrit dans la section [Tester la synchronisation de BPM avec Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="75b64-530">Go to the BPM library, and select **Sync testcases** to overwrite the task recording that is attached to the test case in Azure DevOps, as described in the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>
15. <span data-ttu-id="75b64-531">Ouvrez RSAT, et sélectionnez **Charger** pour recharger tous les scénarios de test dans la suite de tests.</span><span class="sxs-lookup"><span data-stu-id="75b64-531">Open RSAT, and select **Load** to reload all the test cases in the test suite.</span></span> <span data-ttu-id="75b64-532">Vous devez recréer les fichiers d'automatisation et de paramètre pour le scénario de test approprié en sélectionnant le scénario de test, puis en sélectionnant **Nouveau \> Générer des fichiers de paramètre et d'exécution de test**, comme décrit dans la section [Charger et exécuter des scénarios de test](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="75b64-532">You must regenerate the automation and parameter files for the appropriate test case by selecting the test case and then selecting **New \> Generate Test Execution and Parameter files**, as described in the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-533">Si le fichier de paramètres Excel a été laissé ouvert, la régénération échoue.</span><span class="sxs-lookup"><span data-stu-id="75b64-533">If the Excel parameter file was left open, regeneration will fail.</span></span> <span data-ttu-id="75b64-534">Par conséquent, veillez à ce que le fichier de paramètres Excel du scénario de test soit fermé avant de générer le nouveau fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-534">Therefore, make sure that the Excel parameter file for the test case is closed before you generate the new Excel parameter file.</span></span>

16. <span data-ttu-id="75b64-535">Sélectionnez **Éditer** pour ouvrir le nouveau fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-535">Select **Edit** to open the new Excel parameter file.</span></span> <span data-ttu-id="75b64-536">Vous obtenez une nouvelle entrée **Variable enregistrée** sur la ligne 9.</span><span class="sxs-lookup"><span data-stu-id="75b64-536">You will see a new **Saved variable** entry on line 9.</span></span> <span data-ttu-id="75b64-537">Cette variable, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, est enregistrée dans le fichier XML de l'enregistrement de tâche et peut être utilisé pour les tests suivants.</span><span class="sxs-lookup"><span data-stu-id="75b64-537">This variable, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, is saved in the task recording's XML file and can be used in subsequent tests.</span></span>

    ![Entrée de variable enregistrée](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a><span data-ttu-id="75b64-539">Créer un nouveau scénario de test</span><span class="sxs-lookup"><span data-stu-id="75b64-539">Create a new test case</span></span>

1. <span data-ttu-id="75b64-540">Accédez à la bibliothèque BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="75b64-540">Go to the **RSAT** BPM library.</span></span>
2. <span data-ttu-id="75b64-541">Sélectionnez le processus **Exemple de processus métier accessoire**, puis, à droite, sélectionnez **Mode d'édition**.</span><span class="sxs-lookup"><span data-stu-id="75b64-541">Select the **Sample Support Business Process** process, and then, on the right, select **Edit mode**.</span></span>
3. <span data-ttu-id="75b64-542">Modifiez la valeur du champ **Nom** et du champ **Description** en **Lancer un produit**.</span><span class="sxs-lookup"><span data-stu-id="75b64-542">Change the value of both the **Name** field and the **Description** field to **Release a product**.</span></span> <span data-ttu-id="75b64-543">Sélectionnez ensuite **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="75b64-543">Then select **Save**.</span></span>

    ![Nom et description modifiés pour Lancer un produit](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a><span data-ttu-id="75b64-545">Créer un nouvel enregistrement de tâche possédant une fonction de validation</span><span class="sxs-lookup"><span data-stu-id="75b64-545">Create a new task recording that has a Validate function</span></span>

- <span data-ttu-id="75b64-546">Créez un enregistrement de tâche pour lancer le produit créé précédemment dans l'entité juridique USRT.</span><span class="sxs-lookup"><span data-stu-id="75b64-546">Create a task recording to release the product that was created earlier to the USRT legal entity.</span></span> <span data-ttu-id="75b64-547">Pour plus d'informations, voir la section [Créer un enregistrement de tâche et l'enregistrer dans la bibliothèque BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="75b64-547">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b64-548">Pour les scénarios de test enchaînés, nous vous recommandons de toujours rechercher ou filtrer l'enregistrement désiré en *saisissant manuellement la valeur du champ*.</span><span class="sxs-lookup"><span data-stu-id="75b64-548">For chained test cases, we always recommend that you find or filter for the record that you require by *manually typing the value of the field*.</span></span> <span data-ttu-id="75b64-549">Ainsi, l'outil peut déterminer sur quel enregistrement appliquer l'action par rapport au scénario de test suivant.</span><span class="sxs-lookup"><span data-stu-id="75b64-549">In that way, the tool can determine the record that the action must be taken against in the subsequent test case.</span></span>

    ![Nouvel enregistrement de tâche possédant une fonction de validation](./media/setup_rsa_tool_96.png)

    <span data-ttu-id="75b64-551">Comme le montre l'illustration précédente, lorsque le produit est trouvé à l'aide du filtre rapide, mais avant de sélectionner **Lancer des produits**, vous validez la valeur du champ **Numéro de produit** pour vous assurer que l'identificateur du produit est bien celui qui a été créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="75b64-551">As the preceding illustration shows, after the product is found by using the Quick Filter, but before you select **Release products**, you validate the value of the **Product number** field to make sure that the product ID is the product ID that was created earlier.</span></span> <span data-ttu-id="75b64-552">Pour valider la valeur, cliquez avec le bouton droit sur le champ **Numéro de produit**, puis sélectionnez **Enregistreur de tâches \> Valider \> Valeur actuelle**.</span><span class="sxs-lookup"><span data-stu-id="75b64-552">To validate the value, right-click the **Product number** field, and then select **Task recorder \> Validate \> Current Value**.</span></span>

    ![Validation de la valeur actuelle](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a><span data-ttu-id="75b64-554">Enregistrer l'enregistrement de tâche dans BPM</span><span class="sxs-lookup"><span data-stu-id="75b64-554">Save the task recording to BPM</span></span>

1. <span data-ttu-id="75b64-555">Une fois l'enregistrement de tâche terminé, sélectionnez **Enregistrer sur Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="75b64-555">After the task recording is completed, select **Save to Lifecycle Services**.</span></span>

    ![Options d'enregistrement](./media/setup_rsa_tool_98.png)

2. <span data-ttu-id="75b64-557">Les informations sur la bibliothèque sont chargées à partir de LCS.</span><span class="sxs-lookup"><span data-stu-id="75b64-557">Library information is loaded from LCS.</span></span>

    ![Indicateur de progression](./media/setup_rsa_tool_99.png)

3. <span data-ttu-id="75b64-559">Sélectionnez la bibliothèque BPM pour y associer l'enregistrement de tâche</span><span class="sxs-lookup"><span data-stu-id="75b64-559">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="75b64-560">Pour ce didacticiel, sélectionnez la bibliothèque BPM **RSAT** créée précédemment et le processus métier **Lancer un produit** sous celle-ci.</span><span class="sxs-lookup"><span data-stu-id="75b64-560">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Release a product** business process under it.</span></span> <span data-ttu-id="75b64-561">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="75b64-561">Then select **OK**.</span></span>

#### <a name="sync-bpm-to-azure-devops"></a><span data-ttu-id="75b64-562">Synchronisation de BPM avec Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="75b64-562">Sync BPM to Azure DevOps</span></span>

1. <span data-ttu-id="75b64-563">Accédez à la bibliothèque BPM, puis ouvrez la bibliothèque **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="75b64-563">Go to the BPM library, and open the **RSAT** library.</span></span>
2. <span data-ttu-id="75b64-564">Sélectionnez **Synchronisation VSTS**, puis **Synchroniser les cas de test**.</span><span class="sxs-lookup"><span data-stu-id="75b64-564">Select **VSTS sync** and then **Sync test cases**.</span></span> <span data-ttu-id="75b64-565">Pour plus d'informations, voir la section [Tester la synchronisation de BPM avec Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span><span class="sxs-lookup"><span data-stu-id="75b64-565">For more information, see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>

    <span data-ttu-id="75b64-566">Une fois la synchronisation terminée, le nouvel élément de travail et le scénario de test correspondant pour le processus métier **Lancer un produit** s'affiche dans Azure DevOps dans **Tableaux \> Éléments de travail**.</span><span class="sxs-lookup"><span data-stu-id="75b64-566">After the synchronization is completed, the new work item and the corresponding test case for the **Release a product** business process appear in Azure DevOps at **Boards \> Work Items**.</span></span>

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a><span data-ttu-id="75b64-567">Ajouter le nouveau scénario de test à la suite de tests existante</span><span class="sxs-lookup"><span data-stu-id="75b64-567">Add the new test case to the existing test suite</span></span>

1. <span data-ttu-id="75b64-568">Accédez à **Plans de test \> Plans de test**, puis sélectionnez le plan **Plan de test RSAT**.</span><span class="sxs-lookup"><span data-stu-id="75b64-568">Go to **Test plans \> Test plans**, and select the **RSAT Test Plan** plan.</span></span>
2. <span data-ttu-id="75b64-569">Sélectionnez **Ajouter existant**.</span><span class="sxs-lookup"><span data-stu-id="75b64-569">Select **Add existing**.</span></span>
3. <span data-ttu-id="75b64-570">Dans la page **Ajouter des scénarios de test à la suite**, sélectionnez **Exécuter la requête**.</span><span class="sxs-lookup"><span data-stu-id="75b64-570">On the **Add test cases to suite** page, select **Run query**.</span></span>
4. <span data-ttu-id="75b64-571">Sélectionnez le nouveau scénario de test créé pour **Lancer un produit**, puis sélectionnez **Ajoutez des scénarios de test** dans le coin inférieur droit de la page (ce bouton n'est pas affiché dans l'illustration suivante).</span><span class="sxs-lookup"><span data-stu-id="75b64-571">Select the new test case that was created for **Release a product**, and then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Page Ajouter des scénarios de test à la suite](./media/setup_rsa_tool_100.png)

    <span data-ttu-id="75b64-573">La suite de tests comporte désormais deux scénarios de test.</span><span class="sxs-lookup"><span data-stu-id="75b64-573">The test suite now has two test cases.</span></span>

    ![Deux scénarios de test dans la suite de test](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a><span data-ttu-id="75b64-575">Charger les scénarios de test dans RSAT</span><span class="sxs-lookup"><span data-stu-id="75b64-575">Load test cases into RSAT</span></span>

1. <span data-ttu-id="75b64-576">Ouvrez RSAT, et sélectionnez **Charger**.</span><span class="sxs-lookup"><span data-stu-id="75b64-576">Open RSAT, and select **Load**.</span></span>
2. <span data-ttu-id="75b64-577">Les scénarios de test sont chargés, et vous recevez un avertissement indiquant « Cette action va remplacer les fichiers de données de test Excel, les modifications locales seront perdues.</span><span class="sxs-lookup"><span data-stu-id="75b64-577">The test cases are loaded, and you receive a warning that states, "This action will overwrite Excel test data files, local changes will be lost.</span></span> <span data-ttu-id="75b64-578">Voulez-vous continuer ? »</span><span class="sxs-lookup"><span data-stu-id="75b64-578">Do you want to proceed?"</span></span> <span data-ttu-id="75b64-579">Sélectionnez **Oui** pour mettre à jour les fichiers de paramètres Excel dans le système local, mais pas les fichiers de paramètres Excel qui ont été chargés dans Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-579">Select **Yes** to update the Excel parameter files in the local system but not the Excel parameter files that were uploaded to Azure DevOps.</span></span>

    ![Message d'avertissement](./media/setup_rsa_tool_102.png)

    <span data-ttu-id="75b64-581">Les deux scénarios de test sont chargés, ainsi que le fichier de paramètres Excel pour le premier scénario de test.</span><span class="sxs-lookup"><span data-stu-id="75b64-581">Both the test cases are loaded, together with the Excel parameter file for the first test case.</span></span> <span data-ttu-id="75b64-582">Comme vous avez sélectionné **Charger** dans la dernière exécution, les fichiers de paramètres sont extraits d'Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="75b64-582">Because you selected **Upload** in the last run, the parameter files are pulled from Azure DevOps.</span></span>

    ![Scénarios de test chargés](./media/setup_rsa_tool_103.png)

3. <span data-ttu-id="75b64-584">Sélectionnez uniquement le second scénario de test, puis sélectionnez **Nouveau \> Générer des fichiers de paramètre et d'exécution de test**.</span><span class="sxs-lookup"><span data-stu-id="75b64-584">Select only the second test case, and then select **New \> Generate test execution and parameter files**.</span></span>

#### <a name="edit-the-excel-parameter-file"></a><span data-ttu-id="75b64-585">Éditer le fichier de paramètres Excel</span><span class="sxs-lookup"><span data-stu-id="75b64-585">Edit the Excel parameter file</span></span>

1. <span data-ttu-id="75b64-586">Sélectionnez seulement le deuxième scénario de test, puis sélectionnez **Modifier** pour ouvrir le fichier de paramètres Excel correspondant.</span><span class="sxs-lookup"><span data-stu-id="75b64-586">Select only the second test case, and then select **Edit** to open the corresponding Excel parameter file.</span></span>
2. <span data-ttu-id="75b64-587">Copiez la variable enregistrée **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (voir la section [Modifier un enregistrement de tâche existant pour créer une variable enregistrée](#modify-an-existing-task-recording-to-create-a-saved-variable) ) du premier scénario de test dans tous les champs dans lesquels le numéro de produit est utilisé.</span><span class="sxs-lookup"><span data-stu-id="75b64-587">Copy the **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** saved variable (see the [Modify an existing task recording to create a saved variable](#modify-an-existing-task-recording-to-create-a-saved-variable) section) from the first test case into all the fields where the product number is used.</span></span> <span data-ttu-id="75b64-588">Dans ce cas, vous copiez la variable dans les champs **Numéro de produit** et **Valider le numéro de produit** de la feuille **EcoResProductListPage**.</span><span class="sxs-lookup"><span data-stu-id="75b64-588">In this case, you copy the variable into the **Product number** and **Validate Product number** fields on the **EcoResProductListPage** sheet.</span></span>

    ![Champs Numéro de produit et Valider le numéro de produit](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > <span data-ttu-id="75b64-590">Les variables ne peuvent être transférées entre tests que pendant la même exécution de test.</span><span class="sxs-lookup"><span data-stu-id="75b64-590">Variables can be passed between tests only during the same test run.</span></span> <span data-ttu-id="75b64-591">Les noms des variables doivent correspondre parfaitement.</span><span class="sxs-lookup"><span data-stu-id="75b64-591">The names of the variables must match exactly.</span></span>

3. <span data-ttu-id="75b64-592">Sélectionnez **Enregistrer**, puis fermez le classeur Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-592">Select **Save**, and then close the Excel workbook.</span></span>
4. <span data-ttu-id="75b64-593">Sélectionnez **Charger** pour enregistrer les modifications apportées au fichier de paramètres Excel.</span><span class="sxs-lookup"><span data-stu-id="75b64-593">Select **Upload** to save the changes that you made to the Excel parameter file.</span></span>

#### <a name="run-the-chained-test-cases"></a><span data-ttu-id="75b64-594">Exécuter des scénarios de test enchaînés</span><span class="sxs-lookup"><span data-stu-id="75b64-594">Run the chained test cases</span></span>

1. <span data-ttu-id="75b64-595">Sélectionnez les deux scénarios de test, puis sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="75b64-595">Select both the test cases, and then select **Run**.</span></span>
2. <span data-ttu-id="75b64-596">Vérifiez que les deux scénarios de test sont réussis.</span><span class="sxs-lookup"><span data-stu-id="75b64-596">Verify that both test cases have passed.</span></span>

    ![Champ de résultat défini sur Réussi pour les deux scénarios de test](./media/setup_rsa_tool_105.png)
