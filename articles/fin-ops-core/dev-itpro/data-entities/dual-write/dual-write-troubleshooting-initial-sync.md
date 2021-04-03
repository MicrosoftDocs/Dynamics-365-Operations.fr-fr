---
title: Résoudre les problèmes lors de la synchronisation initiale
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes susceptibles de survenir pendant la synchronisation initiale.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8aa7d156d0f0dad921b5c0aceec941295950b308
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566835"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="6ad8a-103">Résoudre les problèmes lors de la synchronisation initiale</span><span class="sxs-lookup"><span data-stu-id="6ad8a-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="6ad8a-104">Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="6ad8a-105">Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes susceptibles de survenir pendant la synchronisation initiale.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ad8a-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="6ad8a-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="6ad8a-107">La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="6ad8a-108">Vérifier les erreurs de synchronisation initiales dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6ad8a-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="6ad8a-109">Après avoir activé les modèles de mappage, le statut des cartes doit être **En cours d’exécution**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="6ad8a-110">Si le statut est défini sur **Pas en cours d’exécution**, des erreurs se sont produites lors de la synchronisation initiale.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="6ad8a-111">Pour afficher les erreurs, sélectionnez l’onglet **Détails de la synchronisation initiale** sur la page **Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Erreur sur l’onglet Détails de la synchronisation initiale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="6ad8a-113">Vous ne pouvez pas terminer la synchronisation initiale : 400 Bad Request</span><span class="sxs-lookup"><span data-stu-id="6ad8a-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="6ad8a-114">**Rôle requis pour résoudre le problème :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="6ad8a-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="6ad8a-115">Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’exécuter le mappage et la synchronisation initiale :</span><span class="sxs-lookup"><span data-stu-id="6ad8a-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="6ad8a-116">*(\[Bad Request\], Le serveur distant a renvoyé une erreur : (400) Bad Request.), l’exportation AX a rencontré une erreur*</span><span class="sxs-lookup"><span data-stu-id="6ad8a-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="6ad8a-117">Voici un exemple du message de l’intégralité du message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-117">Here is an example of the full error message.</span></span>

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

<span data-ttu-id="6ad8a-118">Si cette erreur se produit régulièrement et si vous ne pouvez pas terminer la synchronisation initiale, procédez comme suit pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="6ad8a-119">Connectez-vous à la machine virtuelle pour l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="6ad8a-120">Ouvrez Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="6ad8a-121">Dans le volet **Services**, assurez-vous que le service de structure d’exportation et d’importation des données Microsoft Dynamics 365 est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="6ad8a-122">Redémarrez-le s’il a été arrêté, car la synchronisation initiale l’exige.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="6ad8a-123">Erreur de synchronisation initiale : 403 Forbidden</span><span class="sxs-lookup"><span data-stu-id="6ad8a-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="6ad8a-124">Vous pouvez recevoir le message d’erreur suivant pendant la synchronisation initiale :</span><span class="sxs-lookup"><span data-stu-id="6ad8a-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="6ad8a-125">*(\[Forbidden\], Le serveur distant a renvoyé une erreur : (403) Forbidden.), l’exportation AX a rencontré une erreur*</span><span class="sxs-lookup"><span data-stu-id="6ad8a-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="6ad8a-126">Pour régler le problème, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="6ad8a-127">Connectez-vous à l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="6ad8a-128">Sur la page **Applications Azure Active Directory**, supprimez le client **DtAppID**, puis ajoutez-le à nouveau.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Client DtAppID dans la liste des applications Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="6ad8a-130">Échecs d’auto-référence ou de référence circulaire lors de la synchronisation initiale</span><span class="sxs-lookup"><span data-stu-id="6ad8a-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="6ad8a-131">Vous pouvez recevoir un message d’erreur si l’un de vos mappages présente des auto-références ou des références circulaires :</span><span class="sxs-lookup"><span data-stu-id="6ad8a-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="6ad8a-132">Ces erreurs entrent dans les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="6ad8a-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="6ad8a-133">Erreurs dans le mappage de tables Fournisseurs V2–avec–Fournisseurs_msdyn</span><span class="sxs-lookup"><span data-stu-id="6ad8a-133">Errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="6ad8a-134">Erreurs dans le mappage de tables Clients V3-avec-Comptes</span><span class="sxs-lookup"><span data-stu-id="6ad8a-134">Errors in the Customers V3–to–Accounts table mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="6ad8a-135">Résoudre les erreurs dans le mappage de tables Fournisseurs V2–avec–Fournisseurs_msdyn</span><span class="sxs-lookup"><span data-stu-id="6ad8a-135">Resolve errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>

<span data-ttu-id="6ad8a-136">Vous pouvez rencontrer les erreurs de synchronisation initiale suivantes pour le mappage de **Fournisseurs V2** avec **Fournisseurs\_msdyn** si les tables comportent des lignes existantes avec des valeurs dans les colonnes **PrimaryContactPersonId** et **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the tables have existing rows where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns.</span></span> <span data-ttu-id="6ad8a-137">Ces erreurs se produisent parce que **InvoiceVendorAccountNumber** est une colonne qui fait référence à lui-même et que **PrimaryContactPersonId** est une référence circulaire dans le mappage des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing column, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6ad8a-138">Les messages d’erreur que vous recevez auront le formulaire suivant.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="6ad8a-139">*Impossible de résoudre le GUID pour le champ : \<field\>. La recherche est introuvable : \<value\>. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="6ad8a-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="6ad8a-140">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="6ad8a-140">Here are some examples:</span></span>

- <span data-ttu-id="6ad8a-141">*Impossible de résoudre le GUID pour le champ : msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. La recherche est introuvable : 000056. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="6ad8a-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="6ad8a-142">*Impossible de résoudre le GUID pour le champ : msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. La recherche est introuvable : V24-1. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="6ad8a-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="6ad8a-143">Si des ligne de la table fournisseur ont des valeurs dans les colonnes **PrimaryContactPersonId** et **InvoiceVendorAccountNumber**, suivez les étapes de la section ci-dessous pour effectuer la synchronisation initiale.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-143">If any rows in the vendor table have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="6ad8a-144">Dans l’application Finance and Operations, supprimez les colonnes **PrimaryContactPersonId** et **InvoiceVendorAccountNumber** du mappage et enregistrez le mappage.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="6ad8a-145">Dans la page de mappage en double écriture pour **Fournisseurs V2 (fournisseurs\_msdyn)**, dans l’onglet **Mappages de tables** dans le filtre, sélectionnez **App.Finance and Operations.Fournisseurs V2**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="6ad8a-146">Dans le filtre de droite, sélectionnez **Ventes.Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="6ad8a-147">Recherchez **primarycontactperson** pour trouver la colonne source **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source column.</span></span>
    3. <span data-ttu-id="6ad8a-148">Sélectionnez **Actions**, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-148">Select **Actions**, and then select **Delete**.</span></span>

        ![Suppression de la colonne PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="6ad8a-150">Répétez cette procédure pour supprimer la colonne **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** column.</span></span>

        ![Suppression de la colonne InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="6ad8a-152">Enregistrez vos modifications dans le mappage.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="6ad8a-153">Désactivez le suivi des modifications pour la table **Fournisseurs V2**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-153">Turn off change tracking for the **Vendors V2** table.</span></span>

    1. <span data-ttu-id="6ad8a-154">Dans l’espace de travail **Gestion des données**, sélectionnez la vignette **Tables de données**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-154">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="6ad8a-155">Sélectionnez la table **Fournisseurs V2**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-155">Select the **Vendors V2** table.</span></span>
    3. <span data-ttu-id="6ad8a-156">Dans le volet Actions, sélectionnez **Options**, puis sélectionnez **Change tracking**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-156">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Sélection de l’option de Suivi des modifications](media/selfref_options.png)

    4. <span data-ttu-id="6ad8a-158">Sélectionnez **Désactiver le suivi des modifications**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-158">Select **Disable Change Tracking**.</span></span>

        ![Sélection du paramètre Désactiver le suivi des modifications](media/selfref_tracking.png)

3. <span data-ttu-id="6ad8a-160">Exécutez la synchronisation initiale du mappage **Fournisseurs V2 (fournisseurs\_msdyn)**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="6ad8a-161">La synchronisation initiale doit s’exécuter correctement sans aucune erreur.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="6ad8a-162">Exécutez la synchronisation initiale pour le mappage **Contacts CDS V2 (contacts)**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="6ad8a-163">Vous devez synchroniser ce mappage si vous souhaitez synchroniser la colonne de contact principal sur la table des fournisseurs, car la synchronisation initiale doit également être effectuée pour les lignes de contacts.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-163">You must sync this mapping if you want to sync the primary contact column on the vendors table, because initial synchronization must also be done for the contact rows.</span></span>
5. <span data-ttu-id="6ad8a-164">Ajoutez les colonnes **PrimaryContactPersonId** et **InvoiceVendorAccountNumber** de nouveau dans le mappage **Fournisseurs V2 (fournisseurs\_msdyn)**, puis enregistrez le mappage.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="6ad8a-165">Exécutez à nouveau la synchronisation initiale du mappage **Fournisseurs V2 (fournisseurs\_msdyn)**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="6ad8a-166">Parce que le suivi des modifications est désactivé, toutes les lignes seront synchronisées.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-166">Because change tracking is turned off, all the rows will be synced.</span></span>
7. <span data-ttu-id="6ad8a-167">Réactivez le suivi des modifications pour la table **Fournisseurs V2**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-167">Turn change tracking back on for the **Vendors V2** table.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="6ad8a-168">Résoudre des erreurs dans le mappage de tables Clients V3–vers–Comptes</span><span class="sxs-lookup"><span data-stu-id="6ad8a-168">Resolve errors in the Customers V3–to–Accounts table mapping</span></span>

<span data-ttu-id="6ad8a-169">Vous pouvez rencontrer les erreurs de synchronisation initiale suivantes pour le mappage de **Clients V3** avec **Comptes** si les tables comportent des lignes existantes avec des valeurs dans les colonnes **ContactPersonID** et **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the tables have existing rows where there are values in the **ContactPersonID** and **InvoiceAccount** columns.</span></span> <span data-ttu-id="6ad8a-170">Ces erreurs se produisent parce que **InvoiceAccount** est une colonne qui fait référence à lui-même et que **ContactPersonID** est une référence circulaire dans le mappage des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-170">These errors occur because **InvoiceAccount** is a self-referencing column, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6ad8a-171">Les messages d’erreur que vous recevez auront le formulaire suivant.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="6ad8a-172">*Impossible de résoudre le GUID pour le champ : \<field\>. La recherche est introuvable : \<value\>. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="6ad8a-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="6ad8a-173">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="6ad8a-173">Here are some examples:</span></span>

- <span data-ttu-id="6ad8a-174">*Impossible de résoudre le GUID pour le champ : primarycontactid.msdyn\_contactpersonid. La recherche est introuvable : 000056. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="6ad8a-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="6ad8a-175">*Impossible de résoudre le GUID pour le champ : msdyn\_billingaccount.accountnumber. La recherche est introuvable : 1206-1. Essayez ces URL pour vérifier si les données de référence existent : `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="6ad8a-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="6ad8a-176">Si des lignes de la table client ont des valeurs dans les colonnes **ContactPersonID** et **InvoiceAccount**, suivez les étapes de la section ci-dessous pour effectuer la synchronisation initiale.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-176">If any rows in the customer table have values in the **ContactPersonID** and **InvoiceAccount** columns, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="6ad8a-177">Vous pouvez utiliser cette approche pour toutes les tables prêtes à l’emploi telles que **Comptes** et **Contacts**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-177">You can use this approach for any out-of-box tables, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="6ad8a-178">Dans l’application Finance and Operations, supprimez les colonnes **ContactPersonID** et **InvoiceAccount** du mappage **Clients V3 (comptes)** et enregistrez le mappage.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** columns from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="6ad8a-179">Dans la page de mappage en double écriture pour **Clients V3 (comptes)**, dans l’onglet **Mappages de tables**, sous le filtre de gauche, sélectionnez **Finance and Operations apps.Clients V3**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-179">On the dual-write mapping page for **Customers V3 (accounts)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="6ad8a-180">ns le filtre de droite, sélectionnez **Dataverse.Compte**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-180">In the right filter, select **Dataverse.Account**.</span></span>
    2. <span data-ttu-id="6ad8a-181">Recherchez **contactperson** pour trouver la colonne source **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-181">Search for **contactperson** to find the **ContactPersonID** source column.</span></span>
    3. <span data-ttu-id="6ad8a-182">Sélectionnez **Actions**, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-182">Select **Actions**, and then select **Delete**.</span></span>

        ![Suppression de la colonne PrimaryContactPersonId](media/cust_selfref3.png)

    4. <span data-ttu-id="6ad8a-184">Répétez cette procédure pour supprimer la colonne **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-184">Repeat these steps to delete the **InvoiceAccount** column.</span></span>

        ![Suppression de la colonne InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="6ad8a-186">Enregistrez vos modifications dans le mappage.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="6ad8a-187">Désactivez le suivi des modifications pour la table **Clients V3**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-187">Turn off change tracking for the **Customers V3** table.</span></span>

    1. <span data-ttu-id="6ad8a-188">Dans l’espace de travail **Gestion des données**, sélectionnez la vignette **Tables de données**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-188">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="6ad8a-189">Sélectionnez la table **Clients V3**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-189">Select the **Customers V3** table.</span></span>
    3. <span data-ttu-id="6ad8a-190">Dans le volet Actions, sélectionnez **Options**, puis sélectionnez **Change tracking**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-190">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Sélection de l’option de Suivi des modifications](media/selfref_options.png)

    4. <span data-ttu-id="6ad8a-192">Sélectionnez **Désactiver le suivi des modifications**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-192">Select **Disable Change Tracking**.</span></span>

        ![Sélection du paramètre Désactiver le suivi des modifications](media/selfref_tracking.png)

3. <span data-ttu-id="6ad8a-194">Exécutez la synchronisation initiale pour le mappage **Clients V3 (Comptes)**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6ad8a-195">La synchronisation initiale doit s’exécuter correctement sans aucune erreur.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="6ad8a-196">Exécutez la synchronisation initiale pour le mappage **Contacts CDS V2 (contacts)**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ad8a-197">Il y a deux cartes qui portent le même nom.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-197">There are two maps that have the same name.</span></span> <span data-ttu-id="6ad8a-198">Veillez à sélectionner le mappage ayant la description suivante dans l’onglet **Détails** : **Modèle à double écriture pour la synchronisation entre FO.CDS Fournisseur Contacts V2 et CDS.Contacts. Nécessite un nouveau package \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="6ad8a-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="6ad8a-199">Ajoutez les colonnes **InvoiceAccount** et **ContactPersonId** de nouveau dans le mappage **Clients V3 (Comptes)**, puis enregistrez le mappage.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-199">Add the **InvoiceAccount** and **ContactPersonId** columns back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="6ad8a-200">Les deux colonnes **InvoiceAccount** et **ContactPersonId** font maintenant partie à nouveau du mode de synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-200">Both the **InvoiceAccount** column and the **ContactPersonId** column are now part of live synchronization mode again.</span></span> <span data-ttu-id="6ad8a-201">À l’étape suivante, vous effectuerez la synchronisation initiale de ces colonnes.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-201">In the next step, you will do the initial synchronization for these columns.</span></span>
6. <span data-ttu-id="6ad8a-202">Exécutez à nouveau la synchronisation initiale pour le mappage **Clients V3 (Comptes)**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6ad8a-203">Le suivi des modifications étant désactivés, les données de **InvoiceAccount** et **ContactPersonId** seront synchronisées à partir de l’application Finance and Operations avec Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Dataverse.</span></span>
7. <span data-ttu-id="6ad8a-204">Pour synchroniser les données pour **InvoiceAccount** et **ContactPersonId** depuis Dataverse vers l’application Finance and Operations, vous utilisez un projet d’intégration de données.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Dataverse to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="6ad8a-205">Dans Power Apps, créez un projet d’intégration de données entre **Ventes.Compte** et les tables **Finance and Operations apps.Clients V3**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** tables.</span></span> <span data-ttu-id="6ad8a-206">La direction des données doit aller de Dataverse vers l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-206">The data direction must be from Dataverse to the Finance and Operations app.</span></span> <span data-ttu-id="6ad8a-207">Comme **InvoiceAccount** est un nouvel attribut en double écriture, vous pourrez souhaiter ignorer la synchronisation initiale pour cet attribut.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="6ad8a-208">Pour plus d’informations, voir [Intégration des données dans Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="6ad8a-208">For more information, see [Integrate data into Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="6ad8a-209">L’illustration suivante montre un projet qui met à jour **CustomerAccount** et **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Projet d’intégration de données pour mettre à jour CustomerAccount et ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="6ad8a-211">Ajoutez les critères de l’entreprise dans le filtre du côté Dataverse, car seules les lignes correspondant aux critères de filtrage seront mis à jour dans l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-211">Add the company criteria in the filter on the Dataverse side, so that only rows that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="6ad8a-212">Pour ajouter un filtre, sélectionnez le bouton de filtre.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="6ad8a-213">Ensuite, dans la boîte de dialogue **Modifier la requête**, vous pouvez ajouter une requête de filtre telle que **\_msdyn\_company\_value eq ’\<guid\>’**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="6ad8a-214">[REMARQUE] Si le bouton de filtre n’est pas présent, créez un ticket de support pour demander à l’équipe d’intégration de données d’activer la fonction de filtrage sur votre locataire.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="6ad8a-215">Si vous n’entrez pas de requête de filtre pour **\_msdyn\_company\_value**, toutes les lignes seront synchronisées.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-215">If you don't enter a filter query for **\_msdyn\_company\_value**, all the rows will be synced.</span></span>

        ![Ajout d’une requête de filtre](media/cust_selfref7.png)

    <span data-ttu-id="6ad8a-217">La synchronisation initiale des lignes est maintenant terminée.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-217">The initial synchronization of the rows is now completed.</span></span>

8. <span data-ttu-id="6ad8a-218">Dans l’application Finance and Operations, réactivez le suivi des modifications pour la table **Clients V3**.</span><span class="sxs-lookup"><span data-stu-id="6ad8a-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** table.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]