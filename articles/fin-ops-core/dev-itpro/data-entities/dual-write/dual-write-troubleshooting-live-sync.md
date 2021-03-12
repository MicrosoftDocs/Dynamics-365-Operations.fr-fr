---
title: Résoudre les problèmes de synchronisation en direct
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la synchronisation en direct.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 59c8bd80b167cdfaa7a65e469f4dc7ebf8f50844
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744611"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="c2659-103">Résoudre les problèmes de synchronisation en direct</span><span class="sxs-lookup"><span data-stu-id="c2659-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="c2659-104">Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c2659-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="c2659-105">Notamment elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="c2659-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2659-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c2659-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="c2659-107">La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="c2659-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="c2659-108">La synchronisation en direct génère une erreur de type 403 Forbidden lorsque vous créez une ligne dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c2659-108">Live synchronization throws a 403 Forbidden error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="c2659-109">Vous pouvez recevoir le message d’erreur suivant lorsque vous créez une ligne dans une application Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="c2659-109">You might receive the following error message when you create a row in a Finance and Operations app:</span></span>

<span data-ttu-id="c2659-110">*\[{\\« Erreur\\ » :{\\« Code\\ » :\\« 0x80072560\\ »,\\« message\\ » :\\« L’utilisateur n’est pas un membre de l’organisation.\\ »}}\], Le serveur distant a renvoyé une erreur : (403) Forbidden."}}".*</span><span class="sxs-lookup"><span data-stu-id="c2659-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="c2659-111">Pour résoudre le problème, suivez les étapes dans [Configuration requise et conditions préalables](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="c2659-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="c2659-112">Pour valider ces étapes, les utilisateurs de l’application de double écriture créés dans Dataverse doivent avoir le rôle d’administrateur système.</span><span class="sxs-lookup"><span data-stu-id="c2659-112">To complete those steps, the dual-write application users who are created in Dataverse must have the system admin role.</span></span> <span data-ttu-id="c2659-113">L’équipe propriétaire par défaut doit également avoir le rôle d’administrateur système.</span><span class="sxs-lookup"><span data-stu-id="c2659-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="c2659-114">La synchronisation en direct pour toute table génère uniformément une erreur similaire lorsque vous créez une ligne dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c2659-114">Live synchronization for any table consistently throws a similar error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="c2659-115">**Rôle requis pour résoudre le problème :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="c2659-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="c2659-116">Vous pouvez recevoir un message d’erreur comme le suivant chaque fois que vous essayez d’enregistrer des données de table dans une application Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="c2659-116">You might receive an error message like the following every time that you try to save table data in a Finance and Operations app:</span></span>

<span data-ttu-id="c2659-117">*Impossible d’enregistrer les modifications dans la base de données. L’unité de travail ne peut pas valider la transaction. Impossible d’écrire des données sur les UM de l’entité. Échec de l’écriture dans UnitOfMeasureEntity avec le message d’erreur Impossible de synchroniser avec les UM de l’entité.*</span><span class="sxs-lookup"><span data-stu-id="c2659-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="c2659-118">Pour résoudre le problème, vous devez vous assurer que les données de référence préalables existent dans l’application Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c2659-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Dataverse.</span></span> <span data-ttu-id="c2659-119">Par exemple, si le client dans lequel vous vous trouvez dans l’application Finance and Operations appartient à un groupe de clients spécifique, assurez-vous que le groupe de clients existe dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c2659-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Dataverse.</span></span>

<span data-ttu-id="c2659-120">Si des données existent des deux côtés et si vous avez confirmé que le problème n’est pas lié aux données, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c2659-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="c2659-121">Arrêtez la table associée.</span><span class="sxs-lookup"><span data-stu-id="c2659-121">Stop the related table.</span></span>
2. <span data-ttu-id="c2659-122">Connectez-vous à l’application Finance and Operations et assurez-vous que les lignes de la table défaillante existent dans les tables DualWriteProjectConfiguration et DualWriteProjectFieldConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c2659-122">Sign in to the Finance and Operations app, and make sure that rows for the failing table exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="c2659-123">Par exemple, voici à quoi ressemble la requête si la table **Clients** échoue.</span><span class="sxs-lookup"><span data-stu-id="c2659-123">For example, here is what the query looks like if the **Customers** table is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="c2659-124">S’il existe des lignes pour la table défaillante même après avoir arrêté le mappage de tables, supprimez les lignes liés à la table défaillante.</span><span class="sxs-lookup"><span data-stu-id="c2659-124">If there are rows for the failing table even after you stop the table mapping, delete the rows that are related to the failing table.</span></span> <span data-ttu-id="c2659-125">Prenez note de la colonne **nom du projet** dans la table DualWriteProjectConfiguration et récupérez l’enregistrement dans la ligne DualWriteProjectFieldConfiguration en utilisant le nom du projet pour supprimer la ligne.</span><span class="sxs-lookup"><span data-stu-id="c2659-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the row in the DualWriteProjectFieldConfiguration table by using the project name to delete the row.</span></span>
4. <span data-ttu-id="c2659-126">Démarrez le mappage de tables.</span><span class="sxs-lookup"><span data-stu-id="c2659-126">Start the table mapping.</span></span> <span data-ttu-id="c2659-127">Validez si les données sont synchronisées sans aucun problème.</span><span class="sxs-lookup"><span data-stu-id="c2659-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="c2659-128">Gérer les erreurs de privilège de lecture ou d’écriture lorsque vous créez des données dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c2659-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="c2659-129">Vous pouvez recevoir un message d’erreur de type « Bad Request » qui ressemble à l’exemple suivant lorsque vous créez des données dans une application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c2659-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Exemple de message d’erreur « Bad Request »](media/error_record_id_source.png)

<span data-ttu-id="c2659-131">Pour résoudre le problème, vous devez attribuer le rôle de sécurité correct à l’équipe de l’unité commerciale Dynamics 365 Sales ou Dynamics 365 Customer Service mappée pour activer le privilège manquant.</span><span class="sxs-lookup"><span data-stu-id="c2659-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="c2659-132">Dans l’application Finance and Operations, recherchez l’unité commerciale mappée dans le jeu de connexions d’intégration de données.</span><span class="sxs-lookup"><span data-stu-id="c2659-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Cartographie de l’organisation](media/mapped_business_unit.png)

2. <span data-ttu-id="c2659-134">Connectez-vous à l’environnement dans l’application pilotée par le modèle dans Dynamics 365, accédez à **Paramètre \> Sécurité** et recherchez l’équipe de l’unité commerciale mappée.</span><span class="sxs-lookup"><span data-stu-id="c2659-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Équipe de l’unité commerciale cartographiée](media/setting_security_page.png)

3. <span data-ttu-id="c2659-136">Ouvrez la page de l’équipe à modifier, puis sélectionnez **Gérer les rôles** pour ouvrir la boîte de dialogue **Gérer les rôles d’équipe**.</span><span class="sxs-lookup"><span data-stu-id="c2659-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Bouton Gérer les rôles](media/manage_team_roles.png)

4. <span data-ttu-id="c2659-138">Attribuez le rôle disposant du privilège de lecture/écriture aux tables concernées, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2659-138">Assign the role that has the read/write privilege for the relevant tables, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a><span data-ttu-id="c2659-139">Résoudre les problèmes de synchronisation dans un environnement Dataverse récemment modifié</span><span class="sxs-lookup"><span data-stu-id="c2659-139">Fix synchronization issues in an environment that has a recently changed Dataverse environment</span></span>

<span data-ttu-id="c2659-140">**Rôle requis pour résoudre le problème :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="c2659-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="c2659-141">Vous pouvez recevoir le message d’erreur suivant lorsque vous créez des données dans une application Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="c2659-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="c2659-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Impossible de générer la charge utile pour vérifier CustCustomerV3Entity** », « logDateTime » : « 2019-08-27T18:51:52.5843124Z », « verboseError » : « Échec de la création de la charge utile avec l’erreur URI non valide : l’URI est vide. »}\], « isErrorCountUpdated » : true}*</span><span class="sxs-lookup"><span data-stu-id="c2659-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="c2659-143">Voici à quoi ressemble l’erreur dans l’application pilotée par modèle dans Dynamics 365 :</span><span class="sxs-lookup"><span data-stu-id="c2659-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="c2659-144">*Une erreur inattendue s’est produite depuis le code ISV. (ErrorType = ClientError) Exception inattendue depuis le plug-in (Execute) : Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: échec du triatement du compte d’entité - (Échec de la tentative de connexion, car la partie connectée n’a pas répondu correctement après un temps donné, ou la connexion établie a échoué en raison de l’absence de réponse de l’hôte connecté*</span><span class="sxs-lookup"><span data-stu-id="c2659-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="c2659-145">Cette erreur se produit lorsque l’environnement Dataverse est mal réinitialisé lorsque vous essayez de créer des données dans l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c2659-145">This error occurs when the Dataverse environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="c2659-146">Pour régler le problème, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c2659-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="c2659-147">Connectez-vous à la machine virtuelle Finance and Operations (VM), ouvrez SQL Server Management Studio (SSMS) et recherchez des lignes dans la table DUALWRITEPROJECTCONFIGURATIONENTITY où **internalentityname** équivaut à **Customers V3** et **externalentityname** équivaut à **accounts**.</span><span class="sxs-lookup"><span data-stu-id="c2659-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for rows in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="c2659-148">Voici à quoi ressemble la requête.</span><span class="sxs-lookup"><span data-stu-id="c2659-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="c2659-149">Utilisez le nom du projet à partir des résultats de la requête précédente pour exécuter la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="c2659-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="c2659-150">Assurez-vous que la colonne **externalenvironmentURL** a l’URL Dataverse ou d’application appropriée.</span><span class="sxs-lookup"><span data-stu-id="c2659-150">Make sure that the **externalenvironmentURL** column has the correct Dataverse or app URL.</span></span> <span data-ttu-id="c2659-151">Supprimez toutes les lignes en double qui pointent vers la mauvaise URL Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c2659-151">Delete any duplicate rows that point to the wrong Dataverse URL.</span></span> <span data-ttu-id="c2659-152">Supprimez les lignes correspondantes dans les tables DUALWRITEPROJECTFIELDCONFIGURATION et DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="c2659-152">Delete the corresponding rows in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="c2659-153">Arrêter le mappage de tables et le redémarrer</span><span class="sxs-lookup"><span data-stu-id="c2659-153">Stop the table mapping, and then restart it</span></span>
