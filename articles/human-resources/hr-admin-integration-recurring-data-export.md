---
title: Créer une application d’exportation de données récurrentes
description: Cet article montre comment créer une application logique Microsoft Azure qui exporte des données de Microsoft Dynamics 365 Human Resources sur un calendrier récurrent.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5bc9b5c97f855f1d8eb44765c98473b69f96adec
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466975"
---
# <a name="create-a-recurring-data-export-app"></a><span data-ttu-id="4c745-103">Créer une application d’exportation de données récurrentes</span><span class="sxs-lookup"><span data-stu-id="4c745-103">Create a recurring data export app</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4c745-104">Cet article montre comment créer une application logique Microsoft Azure qui exporte des données de Microsoft Dynamics 365 Human Resources sur un calendrier récurrent.</span><span class="sxs-lookup"><span data-stu-id="4c745-104">This article shows how to create a Microsoft Azure logic app that exports data from Microsoft Dynamics 365 Human Resources on a recurring schedule.</span></span> <span data-ttu-id="4c745-105">Le didacticiel tire parti de l’interface de programmation d’application (API) du package DMF Human Resources pour exporter les données.</span><span class="sxs-lookup"><span data-stu-id="4c745-105">The tutorial takes advantage of Human Resources' DMF package REST application programming interface (API) to export the data.</span></span> <span data-ttu-id="4c745-106">Une fois les données exportées, l’application logique enregistre le package de données exporté dans un dossier Microsoft OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="4c745-106">After the data has been exported, the logic app saves the exported data package to a Microsoft OneDrive for Business folder.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="4c745-107">Scénario d’entreprise</span><span class="sxs-lookup"><span data-stu-id="4c745-107">Business scenario</span></span>

<span data-ttu-id="4c745-108">Dans un scénario d’entreprise typique pour les intégrations Microsoft Dynamics 365, les données doivent être exportées vers un système en aval selon un calendrier récurrent.</span><span class="sxs-lookup"><span data-stu-id="4c745-108">In one typical business scenario for Microsoft Dynamics 365 integrations, data must be exported to a downstream system on a recurring schedule.</span></span> <span data-ttu-id="4c745-109">Ce didacticiel montre comment exporter tous les enregistrements de travail de Microsoft Dynamics 365 Human Resources et enregistrer la liste des collaborateurs dans un dossier OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="4c745-109">This tutorial shows how to export all worker records from Microsoft Dynamics 365 Human Resources and save the list of workers in a OneDrive for Business folder.</span></span>

> [!TIP]
> <span data-ttu-id="4c745-110">Les données spécifiques qui sont exportées dans ce didacticiel et la destination des données exportées ne sont que des exemples.</span><span class="sxs-lookup"><span data-stu-id="4c745-110">The specific data that is exported in this tutorial and the destination of the exported data are only examples.</span></span> <span data-ttu-id="4c745-111">Vous pouvez facilement les modifier pour répondre à vos besoins professionnels.</span><span class="sxs-lookup"><span data-stu-id="4c745-111">You can easily change them to meet your business needs.</span></span>

## <a name="technologies-used"></a><span data-ttu-id="4c745-112">Technologies utilisées</span><span class="sxs-lookup"><span data-stu-id="4c745-112">Technologies used</span></span>

<span data-ttu-id="4c745-113">Ce didacticiel utilise les technologies suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c745-113">This tutorial uses the following technologies:</span></span>

- <span data-ttu-id="4c745-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**- La source de données principales pour les collaborateurs qui seront exportés.</span><span class="sxs-lookup"><span data-stu-id="4c745-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – The master data source for workers that will be exported.</span></span>
- <span data-ttu-id="4c745-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** - La technologie qui fournit l’orchestration et la planification de l’exportation récurrente.</span><span class="sxs-lookup"><span data-stu-id="4c745-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – The technology that provides orchestration and scheduling of the recurring export.</span></span>

    - <span data-ttu-id="4c745-116">**[Connecteurs](https://docs.microsoft.com/azure/connectors/apis-list)** - La technologie utilisée pour connecter l’application logique aux points de terminaison requis.</span><span class="sxs-lookup"><span data-stu-id="4c745-116">**[Connectors](https://docs.microsoft.com/azure/connectors/apis-list)** – The technology that is used to connect the logic app to the required endpoints.</span></span>

        - <span data-ttu-id="4c745-117">Connecteur [HTTP with Azure AD](https://docs.microsoft.com/connectors/webcontents/)</span><span class="sxs-lookup"><span data-stu-id="4c745-117">[HTTP with Azure AD](https://docs.microsoft.com/connectors/webcontents/) connector</span></span>
        - <span data-ttu-id="4c745-118">Connecteur [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness)</span><span class="sxs-lookup"><span data-stu-id="4c745-118">[OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector</span></span>

- <span data-ttu-id="4c745-119">**[API REST du package DMF](../dev-itpro/data-entities/data-management-api.md)** - La technologie utilisée pour déclencher l’exportation et suivre sa progression.</span><span class="sxs-lookup"><span data-stu-id="4c745-119">**[DMF package REST API](../dev-itpro/data-entities/data-management-api.md)** – The technology that is used to trigger the export and monitor its progress.</span></span>
- <span data-ttu-id="4c745-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** - La destination des collaborateurs exportés.</span><span class="sxs-lookup"><span data-stu-id="4c745-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** – The destination for the exported workers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c745-121">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="4c745-121">Prerequisites</span></span>

<span data-ttu-id="4c745-122">Avant de commencer l’exercice de ce didacticiel, vous devez disposer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4c745-122">Before you begin the exercise in this tutorial, you must have the following items:</span></span>

- <span data-ttu-id="4c745-123">Un environnement de ressources humaines doté d’autorisations de niveau administrateur dans l’environnement</span><span class="sxs-lookup"><span data-stu-id="4c745-123">A Human Resources environment that has admin-level permissions in the environment</span></span>
- <span data-ttu-id="4c745-124">Un [Abonnement Azure](https://azure.microsoft.com/free/) pour héberger l’application logique</span><span class="sxs-lookup"><span data-stu-id="4c745-124">An [Azure subscription](https://azure.microsoft.com/free/) to host the logic app</span></span>

## <a name="the-exercise"></a><span data-ttu-id="4c745-125">Exercice</span><span class="sxs-lookup"><span data-stu-id="4c745-125">The exercise</span></span>

<span data-ttu-id="4c745-126">À la fin de cet exercice, vous disposerez d’une application logique connectée à votre environnement de ressources humaines et à votre compte OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="4c745-126">At the end of this exercise, you will have a logic app that is connected to your Human Resources environment and your OneDrive for Business account.</span></span> <span data-ttu-id="4c745-127">L’application logique exportera un package de données à partir des ressources humaines, attendra la fin de l’exportation, téléchargera le package de données exporté et enregistrera le package de données dans le dossier OneDrive for Business que vous avez spécifié.</span><span class="sxs-lookup"><span data-stu-id="4c745-127">The logic app will export a data package from Human Resources, wait for the export to be completed, download the exported data package, and save the data package in the OneDrive for Business folder that you specified.</span></span>

<span data-ttu-id="4c745-128">L’application logique terminée ressemblera à l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="4c745-128">The completed logic app will resemble the following illustration.</span></span>

![Présentation de l’application logique](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a><span data-ttu-id="4c745-130">Étape 1 : créer un projet d’exportation de données dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="4c745-130">Step 1: Create a data export project in Human Resources</span></span>

<span data-ttu-id="4c745-131">Dans Human Resources, créezun projet d’exportation de données qui exporte des collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="4c745-131">In Human Resources, create a data export project that exports workers.</span></span> <span data-ttu-id="4c745-132">Nommez le projet **Exportation de collaborateurs** et assurez-vous que l’option **Générer le package de données** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="4c745-132">Name the project **Export Workers**, and make sure that the **Generate data package** option is set to **Yes**.</span></span> <span data-ttu-id="4c745-133">Ajoutez une seule entité (**Collaborateur**) au projet et sélectionnez le format dans lequel exporter.</span><span class="sxs-lookup"><span data-stu-id="4c745-133">Add a single entity (**Worker**) to the project, and select the format to export in.</span></span> <span data-ttu-id="4c745-134">(Le format Microsoft Excel est utilisé dans ce didacticiel.)</span><span class="sxs-lookup"><span data-stu-id="4c745-134">(Microsoft Excel format is used in this tutorial.)</span></span>

![Projet de données Exportation de collaborateurs](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> <span data-ttu-id="4c745-136">Notez le nom du projet d’exportation de données.</span><span class="sxs-lookup"><span data-stu-id="4c745-136">Remember the name of the data export project.</span></span> <span data-ttu-id="4c745-137">Vous en aurez besoin lorsque vous créerez l’application logique à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="4c745-137">You will need it when you create the logic app in the next step.</span></span>

### <a name="step-2-create-the-logic-app"></a><span data-ttu-id="4c745-138">Étape 2 : créer l’application logique</span><span class="sxs-lookup"><span data-stu-id="4c745-138">Step 2: Create the logic app</span></span>

<span data-ttu-id="4c745-139">La majeure partie de l’exercice consiste à créer l’application logique.</span><span class="sxs-lookup"><span data-stu-id="4c745-139">The bulk of the exercise involves creating the logic app.</span></span>

1. <span data-ttu-id="4c745-140">Dans le portail Azure, créez une application logique.</span><span class="sxs-lookup"><span data-stu-id="4c745-140">In the Azure portal, create a logic app.</span></span>

    ![Page de création d’application logique](media/integration-logic-app-creation-1.png)

2. <span data-ttu-id="4c745-142">Dans Logic Apps Designer, commencez par une application logique vide.</span><span class="sxs-lookup"><span data-stu-id="4c745-142">In the Logic Apps Designer, start with a blank logic app.</span></span>
3. <span data-ttu-id="4c745-143">Ajoutez un [Déclencheur de calendrier de récurrence ](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence)pour exécuter l’application logique toutes les 24 heures (ou selon un horaire de votre choix).</span><span class="sxs-lookup"><span data-stu-id="4c745-143">Add a [Recurrence Schedule trigger](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) to run the logic app every 24 hours (or according to a schedule of your choice).</span></span>

    ![Boîte de dialogue de récurrence](media/integration-logic-app-recurrence-step.png)

4. <span data-ttu-id="4c745-145">Appelez l’API REST DMF [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage)pour planifier l’exportation de votre package de données.</span><span class="sxs-lookup"><span data-stu-id="4c745-145">Call the [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API to schedule the export of your data package.</span></span>

    1. <span data-ttu-id="4c745-146">Utilisez l’action **Appeler une requête HTTP** depuis le connecteur HTTP with Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4c745-146">Use the **Invoke an HTTP request** action from the HTTP with Azure AD connector.</span></span>

        - <span data-ttu-id="4c745-147">**URL de la ressource de base :** l’URL de votre environnement Human Resources (n’incluez pas les informations de chemin / espace de noms.)</span><span class="sxs-lookup"><span data-stu-id="4c745-147">**Base Resource URL:** The URL of your Human Resources environment (Don't include path/namespace information.)</span></span>
        - <span data-ttu-id="4c745-148">**URI ressource Azure AD :** `http://hr.talent.dynamics.com`</span><span class="sxs-lookup"><span data-stu-id="4c745-148">**Azure AD Resource URI:** `http://hr.talent.dynamics.com`</span></span>

        > [!NOTE]
        > <span data-ttu-id="4c745-149">Le service Human Resources ne fournit pas encore de connecteur qui expose toutes les API qui composent l’API REST du package DMF, telles que **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="4c745-149">The Human Resources service doesn't yet provide a connector that exposes all the APIs that make up the DMF package REST API, such as **ExportToPackage**.</span></span> <span data-ttu-id="4c745-150">Au lieu de cela, vous devez appeler les API en utilisant des requêtes HTTPS brutes via le connecteur HTTP with Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4c745-150">Instead, you must call the APIs by using raw HTTPS requests through the HTTP with Azure AD connector.</span></span> <span data-ttu-id="4c745-151">Ce connecteur utilise Azure Active Directory (Azure AD) pour l’authentification et l’autorisation des ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="4c745-151">This connector uses Azure Active Directory (Azure AD) for authentication and authorization to Human Resources.</span></span>

        ![Connecteur HTTP with Azure AD](media/integration-logic-app-http-aad-connector-step.png)

    2. <span data-ttu-id="4c745-153">Connectez-vous à votre environnement Human Resources via le connecteur HTTP with Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4c745-153">Sign in to your Human Resources environment through the HTTP with Azure AD connector.</span></span>
    3. <span data-ttu-id="4c745-154">Configurez une requête HTTP **POST** pour appeler l’API REST DMF **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="4c745-154">Set up an HTTP **POST** request to call the **ExportToPackage** DMF REST API.</span></span>

        - <span data-ttu-id="4c745-155">**Méthode :** POST</span><span class="sxs-lookup"><span data-stu-id="4c745-155">**Method:** POST</span></span>
        - <span data-ttu-id="4c745-156">**URL de la demande :** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span><span class="sxs-lookup"><span data-stu-id="4c745-156">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span></span>
        - <span data-ttu-id="4c745-157">**Corps de la requête :**</span><span class="sxs-lookup"><span data-stu-id="4c745-157">**Body of the request:**</span></span>

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Appeler une action de requête HTTP](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > <span data-ttu-id="4c745-159">Vous voudrez peut-être renommer chaque étape afin qu’elle soit plus significative que le nom par défaut, **Appeler une requête HTTP**.</span><span class="sxs-lookup"><span data-stu-id="4c745-159">You might want to rename each step so that it's more meaningful than the default name, **Invoke an HTTP request**.</span></span> <span data-ttu-id="4c745-160">Par exemple, vous pouvez renommer cette étape **ExporterVersPackage**.</span><span class="sxs-lookup"><span data-stu-id="4c745-160">For example, you can rename this step **ExportToPackage**.</span></span>

5. <span data-ttu-id="4c745-161">[Initialisez une variable](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable)pour stocker l’état d’exécution de la requête **ExporterVersPackage**.</span><span class="sxs-lookup"><span data-stu-id="4c745-161">[Initialize a variable](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) to store the execution status of the **ExportToPackage** request.</span></span>

    ![Initialiser l’action variable](media/integration-logic-app-initialize-variable-step.png)

6. <span data-ttu-id="4c745-163">Attendez que l’état d’exécution de l’exportation de données soit **Réussi**.</span><span class="sxs-lookup"><span data-stu-id="4c745-163">Wait until the execution status of the data export is **Succeeded**.</span></span>

    1. <span data-ttu-id="4c745-164">Ajoutez une action [Jusqu’à la boucle](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop)qui se répète jusqu’à ce que la valeur de la variable **ExecutionStatus** soit **Réussi**.</span><span class="sxs-lookup"><span data-stu-id="4c745-164">Add an [Until loop](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) that repeats until the value of the **ExecutionStatus** variable is **Succeeded**.</span></span>
    2. <span data-ttu-id="4c745-165">Ajoutez une action **Retard** qui attend cinq secondes avant d’interroger l’état d’exécution actuel de l’exportation.</span><span class="sxs-lookup"><span data-stu-id="4c745-165">Add a **Delay** action that waits five seconds before it polls for the current execution status of the export.</span></span>

        ![Conteneur jusqu’à la boucle](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > <span data-ttu-id="4c745-167">Définissez le nombre limite sur **15** pour attendre un maximum de 75 secondes (15 itérations × 5 secondes) que l’exportation soit terminée.</span><span class="sxs-lookup"><span data-stu-id="4c745-167">Set the limit count to **15** to wait a maximum of 75 seconds (15 iterations × 5 seconds) for the export to be completed.</span></span> <span data-ttu-id="4c745-168">Si votre exportation prend plus de temps, ajustez la limite comme il convient.</span><span class="sxs-lookup"><span data-stu-id="4c745-168">If your export takes more time, adjust the limit count as appropriate.</span></span>        

    3. <span data-ttu-id="4c745-169">Ajoutez une action **Appeler une requête HTTP** pour appeler l’API REST DMF [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus)et définissez la variable **ExecutionStatus** sur résultat de la réponse **GetExecutionSummaryStatus**.</span><span class="sxs-lookup"><span data-stu-id="4c745-169">Add an **Invoke HTTP request** action to call the [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API, and set the **ExecutionStatus** variable to the result of the **GetExecutionSummaryStatus** response.</span></span>

        > <span data-ttu-id="4c745-170">Cet exemple ne vérifie pas les erreurs.</span><span class="sxs-lookup"><span data-stu-id="4c745-170">This sample doesn't do error checking.</span></span> <span data-ttu-id="4c745-171">L’API **GetExecutionSummaryStatus** peut renvoyer des états de terminal non réussis (c’est-à-dire des états autres que **Réussi**).</span><span class="sxs-lookup"><span data-stu-id="4c745-171">The **GetExecutionSummaryStatus** API can return non-successful terminal states (that is, states other than **Succeeded**).</span></span> <span data-ttu-id="4c745-172">Pour plus d’informations, voir la [Documentation d’API](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span><span class="sxs-lookup"><span data-stu-id="4c745-172">For more information, see the [API documentation](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span></span>

        - <span data-ttu-id="4c745-173">**Méthode :** POST</span><span class="sxs-lookup"><span data-stu-id="4c745-173">**Method:** POST</span></span>
        - <span data-ttu-id="4c745-174">**URL de la demande :** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span><span class="sxs-lookup"><span data-stu-id="4c745-174">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span></span>
        - <span data-ttu-id="4c745-175">**Corps de la demande :** body(’Invoke\_an\_HTTP\_request’)?[’value’]</span><span class="sxs-lookup"><span data-stu-id="4c745-175">**Body of the request:** body('Invoke\_an\_HTTP\_request')?['value']</span></span>

            > [!NOTE]
            > <span data-ttu-id="4c745-176">Vous devrez peut-être saisir la valeur **Corps de la demande** soit en mode code, soit dans l’éditeur de fonctions du concepteur.</span><span class="sxs-lookup"><span data-stu-id="4c745-176">You might have to enter the **Body of the request** value either in code view or in the function editor in the designer.</span></span>

        ![Appeler une action de requête HTTP 2](media/integration-logic-app-get-execution-status-step.png)

        ![Définir l’action variable](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > <span data-ttu-id="4c745-179">La valeur pour l’action **Définir la variable** (**body(’Invoke\_an\_HTTP\_request\_2’)?[’value’]**) différera de la valeur du corps **Appeler une requête HTTP 2**, même si le concepteur affichera les valeurs de la même manière.</span><span class="sxs-lookup"><span data-stu-id="4c745-179">The value for the **Set variable** action (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) will differ from the value for the **Invoke an HTTP request 2** body value, even though the designer will show the values in the same way.</span></span>

7. <span data-ttu-id="4c745-180">Obtenez l’URL de téléchargement du package exporté.</span><span class="sxs-lookup"><span data-stu-id="4c745-180">Get the download URL of the exported package.</span></span>

    - <span data-ttu-id="4c745-181">Ajoutez une action **Appeler une requête HTTP** pour appeler l’API REST DMF [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).</span><span class="sxs-lookup"><span data-stu-id="4c745-181">Add an **Invoke HTTP request** action to call the [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API.</span></span>

        - <span data-ttu-id="4c745-182">**Méthode :** POST</span><span class="sxs-lookup"><span data-stu-id="4c745-182">**Method:** POST</span></span>
        - <span data-ttu-id="4c745-183">**URL de la demande :** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span><span class="sxs-lookup"><span data-stu-id="4c745-183">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span></span>
        - <span data-ttu-id="4c745-184">**Corps de la demande :** {"executionId": body(’GetExportedPackageURL’)?[’value’]}</span><span class="sxs-lookup"><span data-stu-id="4c745-184">**Body of the request:** {"executionId": body('GetExportedPackageURL')?['value']}</span></span>

        ![Action GetExportedPackageURL](media/integration-logic-app-get-exported-package-step.png)

8. <span data-ttu-id="4c745-186">Téléchargez le package exporté.</span><span class="sxs-lookup"><span data-stu-id="4c745-186">Download the exported package.</span></span>

    - <span data-ttu-id="4c745-187">Ajoutez une requête HTTP **GET** (une fonction intégrée [HTTP connector action](https://docs.microsoft.com/azure/connectors/connectors-native-http)) pour télécharger le package à partir de l’URL renvoyée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="4c745-187">Add an HTTP **GET** request (a built-in [HTTP connector action](https://docs.microsoft.com/azure/connectors/connectors-native-http)) to download the package from the URL that was returned in the previous step.</span></span>

        - <span data-ttu-id="4c745-188">**Méthode :** GET</span><span class="sxs-lookup"><span data-stu-id="4c745-188">**Method:** GET</span></span>
        - <span data-ttu-id="4c745-189">**URI :** body(’Invoke\_an\_HTTP\_request\_3’).value</span><span class="sxs-lookup"><span data-stu-id="4c745-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span></span>

            > [!NOTE]
            > <span data-ttu-id="4c745-190">Vous devrez peut-être saisir la valeur **URI** soit en mode code, soit dans l’éditeur de fonctions du concepteur.</span><span class="sxs-lookup"><span data-stu-id="4c745-190">You might have to enter the **URI** value either in code view or in the function editor in the designer.</span></span>

        ![Action HTTP GET](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > <span data-ttu-id="4c745-192">Cette requête ne nécessite aucune authentification supplémentaire, car l’URL retournée par l’API **GetExportedPackageUrl** inclut un jeton de signatures d’accès partagé qui autorise l’accès au téléchargement du fichier.</span><span class="sxs-lookup"><span data-stu-id="4c745-192">This request doesn't require any additional authentication, because the URL that the **GetExportedPackageUrl** API returns includes a shared access signatures token that grants access to download the file.</span></span>

9. <span data-ttu-id="4c745-193">Enregistrez le package téléchargé en utilisant le connecteur [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness).</span><span class="sxs-lookup"><span data-stu-id="4c745-193">Save the downloaded package by using the [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector.</span></span>

    - <span data-ttu-id="4c745-194">Ajoutez une action OneDrive for Business [Créer un fichier ](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file).</span><span class="sxs-lookup"><span data-stu-id="4c745-194">Add a OneDrive for Business [Create File](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file) action.</span></span>
    - <span data-ttu-id="4c745-195">Connectez-vous à votre compte OneDrive for Business, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="4c745-195">Connect to your OneDrive for Business account, as required.</span></span>

        - <span data-ttu-id="4c745-196">**Chemin du dossier :** un dossier de votre choix</span><span class="sxs-lookup"><span data-stu-id="4c745-196">**Folder Path:** A folder of your choice</span></span>
        - <span data-ttu-id="4c745-197">**Nom de fichier :** worker\_package.zip</span><span class="sxs-lookup"><span data-stu-id="4c745-197">**File Name:** worker\_package.zip</span></span>
        - <span data-ttu-id="4c745-198">**Contenu du fichier :** le corps de l’étape précédente (contenu dynamique)</span><span class="sxs-lookup"><span data-stu-id="4c745-198">**File Content:** The body from the previous step (dynamic content)</span></span>

        ![Créer une action de fichier](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a><span data-ttu-id="4c745-200">Étape 3 : tester l’application logique</span><span class="sxs-lookup"><span data-stu-id="4c745-200">Step 3: Test the logic app</span></span>

<span data-ttu-id="4c745-201">Pour tester votre application logique, sélectionnez le bouton **Exécuter** dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="4c745-201">To test your logic app, select the **Run** button in the designer.</span></span> <span data-ttu-id="4c745-202">Vous verrez que les étapes de l’application logique commencent à s’exécuter.</span><span class="sxs-lookup"><span data-stu-id="4c745-202">You will see that the steps of the logic app start to run.</span></span> <span data-ttu-id="4c745-203">Après 30 à 40 secondes, l’application logique devrait terminer son exécution et votre dossier OneDrive for Business devrait inclure un nouveau fichier de package contenant les collaborateurs exportés.</span><span class="sxs-lookup"><span data-stu-id="4c745-203">After 30 to 40 seconds, the logic app should finish running, and your OneDrive for Business folder should include a new package file that contains the exported workers.</span></span>

<span data-ttu-id="4c745-204">Si un échec est signalé pour une étape, sélectionnez l’étape ayant échoué dans le concepteur et examinez les champs **Entrées** et **Sorties** correspondants.</span><span class="sxs-lookup"><span data-stu-id="4c745-204">If a failure is reported for any step, select the failed step in the designer, and examine the **Inputs** and **Outputs** fields for it.</span></span> <span data-ttu-id="4c745-205">Déboguez et ajustez l’étape au besoin pour corriger les erreurs.</span><span class="sxs-lookup"><span data-stu-id="4c745-205">Debug and adjust the step as required to correct the errors.</span></span>

<span data-ttu-id="4c745-206">L’illustration suivante montre à quoi ressemble Logic Apps Designer lorsque toutes les étapes de l’application logique s’exécutent correctement.</span><span class="sxs-lookup"><span data-stu-id="4c745-206">The following illustration shows what the Logic Apps Designer looks like when all the steps of the logic app run successfully.</span></span>

![Exécution de l’application logique réussie](media/integration-logic-app-successful-run.png)

## <a name="summary"></a><span data-ttu-id="4c745-208">Synthèse</span><span class="sxs-lookup"><span data-stu-id="4c745-208">Summary</span></span>

<span data-ttu-id="4c745-209">Dans ce didacticiel, vous avez appris à utiliser une application logique pour exporter des données à partir de Human Resources et enregistrer les données exportées vers un dossier OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="4c745-209">In this tutorial, you learned how to use a logic app to export data from Human Resources and save the exported data to a OneDrive for Business folder.</span></span> <span data-ttu-id="4c745-210">Vous pouvez modifier les étapes de ce didacticiel selon vos besoins pour répondre aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="4c745-210">You can modify the steps of this tutorial as required to suit your business needs.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]