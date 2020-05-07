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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d45b19c1e88e6a27bde4335d4a356f2173bdfcd3
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275415"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="2fc2c-103">Résoudre les problèmes de synchronisation en direct</span><span class="sxs-lookup"><span data-stu-id="2fc2c-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="2fc2c-104">Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="2fc2c-105">Notamment elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fc2c-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="2fc2c-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="2fc2c-107">La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="2fc2c-108">La synchronisation en direct génère une erreur de type 403 Forbidden lorsque vous créez un enregistrement dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2fc2c-108">Live synchronization throws a 403 Forbidden error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="2fc2c-109">Vous pouvez recevoir le message d'erreur suivant lorsque vous créez un enregistrement dans une application Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="2fc2c-109">You might receive the following error message when you create a record in a Finance and Operations app:</span></span>

<span data-ttu-id="2fc2c-110">*\[{\\« Erreur\\ » :{\\« Code\\ » :\\« 0x80072560\\ »,\\« message\\ » :\\« L'utilisateur n'est pas un membre de l'organisation.\\ »}}\], Le serveur distant a renvoyé une erreur : (403) Forbidden."}}".*</span><span class="sxs-lookup"><span data-stu-id="2fc2c-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="2fc2c-111">Pour résoudre le problème, suivez les étapes dans [Configuration requise et conditions préalables](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="2fc2c-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="2fc2c-112">Pour valider ces étapes, les utilisateurs de l'application de double écriture créés dans Common Data Service doivent avoir le rôle d'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-112">To complete those steps, the dual-write application users who are created in Common Data Service must have the system admin role.</span></span> <span data-ttu-id="2fc2c-113">L'équipe propriétaire par défaut doit également avoir le rôle d'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="2fc2c-114">La synchronisation en direct pour toute entité génère uniformément une erreur similaire lorsque vous créez un enregistrement dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2fc2c-114">Live synchronization for any entity consistently throws a similar error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="2fc2c-115">**Rôle requis pour résoudre le problème :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="2fc2c-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="2fc2c-116">Vous pouvez recevoir un message d'erreur comme le suivant chaque fois que vous essayez d'enregistrer des données d'entité dans une application Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="2fc2c-116">You might receive an error message like the following every time that you try to save entity data in a Finance and Operations app:</span></span>

<span data-ttu-id="2fc2c-117">*Impossible d'enregistrer les modifications dans la base de données. L'unité de travail ne peut pas valider la transaction. Impossible d'écrire des données sur les UM de l'entité. Échec de l'écriture dans UnitOfMeasureEntity avec le message d'erreur Impossible de synchroniser avec les UM de l'entité.*</span><span class="sxs-lookup"><span data-stu-id="2fc2c-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="2fc2c-118">Pour résoudre le problème, vous devez vous assurer que les données de référence préalables existent dans l'application Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Common Data Service.</span></span> <span data-ttu-id="2fc2c-119">Par exemple, si le client dans lequel vous vous trouvez dans l'application Finance and Operations appartient à un groupe de clients spécifique, assurez-vous que le groupe de clients existe dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Common Data Service.</span></span>

<span data-ttu-id="2fc2c-120">Si des données existent des deux côtés et si vous avez confirmé que le problème n'est pas lié aux données, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="2fc2c-121">Arrêtez l'entité associée.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-121">Stop the related entity.</span></span>
2. <span data-ttu-id="2fc2c-122">Connectez-vous à l'application Finance and Operations et assurez-vous que les enregistrements de l'entité défaillante existent dans les tables DualWriteProjectConfiguration et DualWriteProjectFieldConfiguration.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-122">Sign in to the Finance and Operations app, and make sure that records for the failing entity exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="2fc2c-123">Par exemple, voici à quoi ressemble la requête si l'entité **Clients** échoue.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-123">For example, here is what the query looks like if the **Customers** entity is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="2fc2c-124">S'il existe des enregistrements pour l'entité défaillante même après avoir arrêté le mappage d'entité, supprimez les enregistrements liés à l'entité défaillante.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-124">If there are records for the failing entity even after you stop the entity mapping, delete the records that are related to the failing entity.</span></span> <span data-ttu-id="2fc2c-125">Prenez note de la colonne **nom du projet** dans la table DualWriteProjectConfiguration et récupérez l'enregistrement dans la table DualWriteProjectFieldConfiguration en utilisant le nom du projet pour supprimer l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the record in the DualWriteProjectFieldConfiguration table by using the project name to delete the record.</span></span>
4. <span data-ttu-id="2fc2c-126">Démarrez le mappage d'entité.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-126">Start the entity mapping.</span></span> <span data-ttu-id="2fc2c-127">Validez si les données sont synchronisées sans aucun problème.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="2fc2c-128">Gérer les erreurs de privilège de lecture ou d'écriture lorsque vous créez des données dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2fc2c-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="2fc2c-129">Vous pouvez recevoir un message d'erreur de type « Bad Request » qui ressemble à l'exemple suivant lorsque vous créez des données dans une application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Exemple de message d'erreur « Bad Request »](media/error_record_id_source.png)

<span data-ttu-id="2fc2c-131">Pour résoudre le problème, vous devez attribuer le rôle de sécurité correct à l'équipe de l'unité commerciale Dynamics 365 Sales ou Dynamics 365 Customer Service mappée pour activer le privilège manquant.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="2fc2c-132">Dans l'application Finance and Operations, recherchez l'unité commerciale mappée dans le jeu de connexions d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Cartographie de l'organisation](media/mapped_business_unit.png)

2. <span data-ttu-id="2fc2c-134">Connectez-vous à l'environnement dans l'application pilotée par le modèle dans Dynamics 365, accédez à **Paramètre \> Sécurité** et recherchez l'équipe de l'unité commerciale mappée.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Équipe de l'unité commerciale cartographiée](media/setting_security_page.png)

3. <span data-ttu-id="2fc2c-136">Ouvrez la page de l'équipe à modifier, puis sélectionnez **Gérer les rôles** pour ouvrir la boîte de dialogue **Gérer les rôles d'équipe**.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Bouton Gérer les rôles](media/manage_team_roles.png)

4. <span data-ttu-id="2fc2c-138">Attribuez le rôle disposant du privilège de lecture/écriture aux entités concernées, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-138">Assign the role that has the read/write privilege for the relevant entities, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a><span data-ttu-id="2fc2c-139">Résoudre les problèmes de synchronisation dans un environnement Common Data Service récemment modifié</span><span class="sxs-lookup"><span data-stu-id="2fc2c-139">Fix synchronization issues in an environment that has a recently changed Common Data Service environment</span></span>

<span data-ttu-id="2fc2c-140">**Rôle requis pour résoudre le problème :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="2fc2c-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="2fc2c-141">Vous pouvez recevoir le message d'erreur suivant lorsque vous créez des données dans une application Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="2fc2c-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="2fc2c-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Impossible de générer la charge utile pour vérifier CustCustomerV3Entity** », « logDateTime » : « 2019-08-27T18:51:52.5843124Z », « verboseError » : « Échec de la création de la charge utile avec l'erreur URI non valide : l'URI est vide. »}\], « isErrorCountUpdated » : true}*</span><span class="sxs-lookup"><span data-stu-id="2fc2c-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="2fc2c-143">Voici à quoi ressemble l'erreur dans l'application pilotée par modèle dans Dynamics 365 :</span><span class="sxs-lookup"><span data-stu-id="2fc2c-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="2fc2c-144">*Une erreur inattendue s'est produite depuis le code ISV. (ErrorType = ClientError) Exception inattendue depuis le plug-in (Execute) : Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: échec du triatement du compte d'entité - (Échec de la tentative de connexion, car la partie connectée n'a pas répondu correctement après un temps donné, ou la connexion établie a échoué en raison de l'absence de réponse de l'hôte connecté*</span><span class="sxs-lookup"><span data-stu-id="2fc2c-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="2fc2c-145">Cette erreur se produit lorsque l'environnement Common Data Service est mal réinitialisé lorsque vous essayez de créer des données dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-145">This error occurs when the Common Data Service environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="2fc2c-146">Pour régler le problème, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="2fc2c-147">Connectez-vous à la machine virtuelle Finance and Operations (VM), ouvrez SQL Server Management Studio (SSMS) et recherchez des enregistrements dans la table DUALWRITEPROJECTCONFIGURATIONENTITY où **internalentityname** équivaut à **Customers V3** et **externalentityname** équivaut à **accounts**.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for records in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="2fc2c-148">Voici à quoi ressemble la requête.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="2fc2c-149">Utilisez le nom du projet à partir des résultats de la requête précédente pour exécuter la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="2fc2c-150">Assurez-vous que la colonne **externalenvironmentURL** a l'URL Common Data Service ou d'application appropriée.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-150">Make sure that the **externalenvironmentURL** column has the correct Common Data Service or app URL.</span></span> <span data-ttu-id="2fc2c-151">Supprimez tous les enregistrements en double qui pointent vers la mauvaise URL Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-151">Delete any duplicate records that point to the wrong Common Data Service URL.</span></span> <span data-ttu-id="2fc2c-152">Supprimez les enregistrements correspondants dans les tables DUALWRITEPROJECTFIELDCONFIGURATION et DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="2fc2c-152">Delete the corresponding records in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="2fc2c-153">Arrêter le mappage d'entités et le redémarrer</span><span class="sxs-lookup"><span data-stu-id="2fc2c-153">Stop the entity mapping, and then restart it</span></span>
