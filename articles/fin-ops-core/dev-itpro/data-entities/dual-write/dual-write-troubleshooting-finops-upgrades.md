---
title: Résoudre les problèmes liés aux mises à niveau des applications Finance and Operations
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés aux mises à niveau des applications Finance and Operations.
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
ms.openlocfilehash: 59384d8e8d043eb14231a471c7218ced2dddf739
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172875"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a><span data-ttu-id="d3186-103">Résoudre les problèmes liés aux mises à niveau des applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d3186-103">Troubleshoot issues related to upgrades of Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d3186-104">Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d3186-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="d3186-105">Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés aux mises à niveau des applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3186-105">Specifically, it provides information that can help you fix issues that are related to upgrades of Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3186-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d3186-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="d3186-107">La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="d3186-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="database-synchronization-errors"></a><span data-ttu-id="d3186-108">Erreurs de synchronisation de base de données</span><span class="sxs-lookup"><span data-stu-id="d3186-108">Database synchronization errors</span></span>

<span data-ttu-id="d3186-109">**Rôle requis pour résoudre le problème :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="d3186-109">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="d3186-110">Vous pouvez recevoir un message d'erreur semblable à l'exemple suivant lorsque vous essayez d'utiliser l'entité **DualWriteProjectConfiguration** pour mettre à jour une application Finance and Operations vers Platform Update 30.</span><span class="sxs-lookup"><span data-stu-id="d3186-110">You might receive an error message that resembles the following example when you try to use the **DualWriteProjectConfiguration** entity to update a Finance and Operations app to Platform update 30.</span></span>

```console
Infolog diagnostic message: 'Cannot select a record in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

<span data-ttu-id="d3186-111">Pour régler le problème, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d3186-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="d3186-112">Connectez-vous à la machine virtuelle pour l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3186-112">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="d3186-113">Ouvrez Visual Studio en tant qu'administrateur et ouvrez l'arbre d'objets d'application (AOA).</span><span class="sxs-lookup"><span data-stu-id="d3186-113">Open Visual Studio as an admin, and open the Application Object Tree (AOT).</span></span>
3. <span data-ttu-id="d3186-114">Recherchez **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d3186-114">Search for **DualWriteProjectConfiguration**.</span></span>
4. <span data-ttu-id="d3186-115">Dans l'AOA, faites un clic droit sur **DualWriteProjectConfiguration** et sélectionnez **Ajouter au nouveau projet**.</span><span class="sxs-lookup"><span data-stu-id="d3186-115">In the AOT, right-click **DualWriteProjectConfiguration**, and select **Add to new project**.</span></span> <span data-ttu-id="d3186-116">Sélectionnez **OK** pour créer le nouveau projet qui utilise les options par défaut.</span><span class="sxs-lookup"><span data-stu-id="d3186-116">Select **OK** to create the new project that uses default options.</span></span>
5. <span data-ttu-id="d3186-117">Dans l'Explorateur de solutions, cliquez avec le bouton droit sur **Propriétés du projet** et définissez **Synchroniser la base de données lors de la construction** sur la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="d3186-117">In Solution Explorer, right-click **Project properties**, and set **Synchronize Database on Build** to **True**.</span></span>
6. <span data-ttu-id="d3186-118">Générez le projet et confirmez que la génération a réussi.</span><span class="sxs-lookup"><span data-stu-id="d3186-118">Build the project, and confirm that the build is successful.</span></span>
7. <span data-ttu-id="d3186-119">Sur le menu **Dynamics 365**, sélectionnez **Synchroniser la base de données**.</span><span class="sxs-lookup"><span data-stu-id="d3186-119">On the **Dynamics 365** menu, select **Synchronize database**.</span></span>
8. <span data-ttu-id="d3186-120">Sélectionnez **Synchroniser** pour faire une synchronisation complète de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d3186-120">Select **Synchronize** to do a full database synchronization.</span></span>
9. <span data-ttu-id="d3186-121">Une fois la synchronisation complète de la base de données réussie, réexécutez l'étape de synchronisation de la base de données dans Microsoft Dynamics Lifecycle Services (LCS) et utilisez les scripts de mise à niveau manuelle le cas échéant, afin de pouvoir procéder à la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d3186-121">After the full database synchronization is successful, rerun the database synchronization step in Microsoft Dynamics Lifecycle Services (LCS) and use the manual upgrade scripts as applicable, so that you can proceed with the update.</span></span>

## <a name="missing-entity-fields-issue-on-maps"></a><span data-ttu-id="d3186-122">Problème de champs d'entité manquants sur les cartes</span><span class="sxs-lookup"><span data-stu-id="d3186-122">Missing entity fields issue on maps</span></span>

<span data-ttu-id="d3186-123">**Rôle requis pour résoudre le problème :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="d3186-123">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="d3186-124">Sur la page **Double écriture**, vous pouvez recevoir un message d'erreur semblable à l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="d3186-124">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="d3186-125">*Champ source manquant \<nom de domaine\> dans le schéma.*</span><span class="sxs-lookup"><span data-stu-id="d3186-125">*Missing source field \<field name\> in the schema.*</span></span>

![Exemple de message d'erreur de champ source manquant](media/error_missing_field.png)

<span data-ttu-id="d3186-127">Pour résoudre le problème, suivez d'abord ces étapes pour vous assurer que les champs se trouvent dans l'entité.</span><span class="sxs-lookup"><span data-stu-id="d3186-127">To fix the issue, first follow these steps to make sure that the fields are in the entity.</span></span>

1. <span data-ttu-id="d3186-128">Connectez-vous à la machine virtuelle pour l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3186-128">Sign in to the VM for the Finance and Operations app.</span></span>
2. <span data-ttu-id="d3186-129">Accédez à **Espaces de travail \> Gestion de données**, sélectionnez la vignette **Paramètres de l'environnement**, puis, sur l'onglet **Paramètres d'entité**, sélectionnez **Actualiser la liste d'entités** pour actualiser les entités.</span><span class="sxs-lookup"><span data-stu-id="d3186-129">Go to **Workspaces \> Data management**, select the **Framework parameters** tile, and then, on the **Entity settings** tab, select **Refresh entity list** to refresh the entities.</span></span>
3. <span data-ttu-id="d3186-130">Accédez à **Espaces de travail \> Gestion des données**, sélectionnez l'onglet **Entités de données** et assurez-vous que l'entité est répertoriée.</span><span class="sxs-lookup"><span data-stu-id="d3186-130">Go to **Workspaces \> Data management**, select the **Data entities** tab, and make sure that the entity is listed.</span></span> <span data-ttu-id="d3186-131">Si l'entité n'est pas répertoriée, connectez-vous à la machine virtuelle pour l'application Finance and Operations et assurez-vous que l'entité est disponible.</span><span class="sxs-lookup"><span data-stu-id="d3186-131">If the entity isn't listed, sign in to the VM for the Finance and Operations app, and make sure the entity is available.</span></span>
4. <span data-ttu-id="d3186-132">Ouvrez la page **Mappage d'entités** depuis la page **Double écriture** dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3186-132">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="d3186-133">Sélectionnez **Actualiser la liste d'entités** pour remplir automatiquement les champs dans les mappages d'entités.</span><span class="sxs-lookup"><span data-stu-id="d3186-133">Select **Refresh entity list** to automatically fill the fields in the entity mappings.</span></span>

<span data-ttu-id="d3186-134">Si le problème n'est toujours pas résolu, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d3186-134">If the issue still isn't fixed, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3186-135">Ces étapes vous guident tout au long du processus de suppression d'une entité, puis de son ajout à nouveau.</span><span class="sxs-lookup"><span data-stu-id="d3186-135">These steps guide you through the process of deleting an entity and then adding it again.</span></span> <span data-ttu-id="d3186-136">Pour éviter les problèmes, assurez-vous de suivre exactement les étapes.</span><span class="sxs-lookup"><span data-stu-id="d3186-136">To avoid issues, be sure to follow the steps exactly.</span></span>

1. <span data-ttu-id="d3186-137">Dans l'application Finance and Operations, accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Entités de données**.</span><span class="sxs-lookup"><span data-stu-id="d3186-137">In the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Data entities** tile.</span></span>
2. <span data-ttu-id="d3186-138">Recherchez l'entité qui manque pour le champ.</span><span class="sxs-lookup"><span data-stu-id="d3186-138">Find the entity that is missing the field.</span></span> <span data-ttu-id="d3186-139">Prenez note de l'entité cible, de la table intermédiaire, du nom de l'entité et des autres valeurs de colonne.</span><span class="sxs-lookup"><span data-stu-id="d3186-139">Make a note of the target entity, staging table, entity name, and other column values.</span></span>
3. <span data-ttu-id="d3186-140">Si l'un de vos groupes de traitement dépend de cette entité, prenez les mesures appropriées pour les groupes de traitement avant de supprimer l'entité.</span><span class="sxs-lookup"><span data-stu-id="d3186-140">If any of your processing groups depend on this entity, take appropriate action for the processing groups before you delete the entity.</span></span>
4. <span data-ttu-id="d3186-141">Supprimez l'entité qui manque pour le champ.</span><span class="sxs-lookup"><span data-stu-id="d3186-141">Delete the entity that is missing the field.</span></span>
5. <span data-ttu-id="d3186-142">Sélectionner **Nouveau** et ajoutez à nouveau l'entité.</span><span class="sxs-lookup"><span data-stu-id="d3186-142">Select **New**, and add the entity back.</span></span> <span data-ttu-id="d3186-143">Spécifiez les valeurs que vous avez notées à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="d3186-143">Specify the values that you made a note of in step 2.</span></span>
6. <span data-ttu-id="d3186-144">Ouvrez la page **Mappage d'entités** depuis la page **Double écriture** dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d3186-144">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
7. <span data-ttu-id="d3186-145">Sélectionnez **Actualiser la liste d'entités** pour remplir automatiquement les champs dans les mappages d'entités.</span><span class="sxs-lookup"><span data-stu-id="d3186-145">Select **Refresh entity list** to automatically fill the fields in the entity mappings.</span></span>