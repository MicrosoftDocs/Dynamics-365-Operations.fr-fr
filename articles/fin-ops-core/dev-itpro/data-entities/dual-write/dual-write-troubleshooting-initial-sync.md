---
title: Résoudre les problèmes lors de la synchronisation initiale
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes susceptibles de survenir pendant la synchronisation initiale.
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
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410079"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="66cb2-103">Résoudre les problèmes lors de la synchronisation initiale</span><span class="sxs-lookup"><span data-stu-id="66cb2-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="66cb2-104">Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="66cb2-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="66cb2-105">Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes susceptibles de survenir pendant la synchronisation initiale.</span><span class="sxs-lookup"><span data-stu-id="66cb2-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66cb2-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="66cb2-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="66cb2-107">La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="66cb2-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="66cb2-108">Vérifier les erreurs de synchronisation initiales dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="66cb2-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="66cb2-109">Après avoir activé les modèles de mappage, le statut des cartes doit être **En cours d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="66cb2-110">Si le statut est défini sur **Pas en cours d'exécution**, des erreurs se sont produites lors de la synchronisation initiale.</span><span class="sxs-lookup"><span data-stu-id="66cb2-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="66cb2-111">Pour afficher les erreurs, sélectionnez l'onglet **Détails de la synchronisation initiale** sur la page **Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Onglet Détails de la synchronisation initiale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="66cb2-113">Vous ne pouvez pas terminer la synchronisation initiale : 400 Bad Request</span><span class="sxs-lookup"><span data-stu-id="66cb2-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="66cb2-114">**Rôle requis pour résoudre le problème :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="66cb2-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="66cb2-115">Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez d'exécuter le mappage et la synchronisation initiale :</span><span class="sxs-lookup"><span data-stu-id="66cb2-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="66cb2-116">*Le serveur distant a renvoyé une erreur : (400) Bad Request.), l'exportation AX a rencontré une erreur*</span><span class="sxs-lookup"><span data-stu-id="66cb2-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="66cb2-117">Voici un exemple du message de l'intégralité du message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="66cb2-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="66cb2-118">Si cette erreur se produit régulièrement et si vous ne pouvez pas terminer la synchronisation initiale, procédez comme suit pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="66cb2-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="66cb2-119">Connectez-vous à la machine virtuelle pour l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="66cb2-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="66cb2-120">Ouvrez Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="66cb2-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="66cb2-121">Dans le volet **Services**, assurez-vous que le service de structure d'exportation et d'importation des données Microsoft Dynamics 365 est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="66cb2-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="66cb2-122">Redémarrez-le s'il a été arrêté, car la synchronisation initiale l'exige.</span><span class="sxs-lookup"><span data-stu-id="66cb2-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="66cb2-123">Erreur de synchronisation initiale : 403 Forbidden</span><span class="sxs-lookup"><span data-stu-id="66cb2-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="66cb2-124">Vous pouvez recevoir le message d'erreur suivant pendant la synchronisation initiale :</span><span class="sxs-lookup"><span data-stu-id="66cb2-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="66cb2-125">*(\[Forbidden\], Le serveur distant a renvoyé une erreur : (403) Forbidden.), l'exportation AX a rencontré une erreur*</span><span class="sxs-lookup"><span data-stu-id="66cb2-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="66cb2-126">Pour régler le problème, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="66cb2-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="66cb2-127">Connectez-vous à l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="66cb2-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="66cb2-128">Sur la page **Applications Azure Active Directory**, supprimez le client **DtAppID**, puis ajoutez-le à nouveau.</span><span class="sxs-lookup"><span data-stu-id="66cb2-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Liste des applications Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="66cb2-130">Échecs d'auto-référence ou de référence circulaire lors de la synchronisation initiale</span><span class="sxs-lookup"><span data-stu-id="66cb2-130">Self-reference or circular-reference failures during initial synchronization</span></span>

<span data-ttu-id="66cb2-131">Vous pouvez recevoir un message d'erreur si l'un de vos mappages présente des auto-références ou des références circulaires :</span><span class="sxs-lookup"><span data-stu-id="66cb2-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="66cb2-132">Ces erreurs entrent dans les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="66cb2-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="66cb2-133">Mappage d'entité Fournisseurs V2 vers msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="66cb2-133">Vendors V2 to msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="66cb2-134">Mappage d'entité Clients V3 vers Comptes</span><span class="sxs-lookup"><span data-stu-id="66cb2-134">Customers V3 to Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="66cb2-135">Résoudre une erreur dans un mappage d'entité Fournisseurs V2 vers msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="66cb2-135">Resolve an error in Vendors V2 to msdyn_vendors entity mapping</span></span>

<span data-ttu-id="66cb2-136">Vous pouvez rencontrer les erreurs de synchronisation initiale suivantes sur le mappage de **Fournisseurs V2** vers **msdyn_vendors** si les entités comportent des enregistrements existants avec des valeurs dans les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-136">You might run into the following initial sync errors on the **Vendors V2** to **msdyn_vendors** mapping if the entities have existing records with values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="66cb2-137">C'est parce que **InvoiceVendorAccountNumber** est un champ qui fait référence à lui-même et que **PrimaryContactPersonId** est une référence circulaire dans le mappage des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="66cb2-137">This because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="66cb2-138">*Impossible de résoudre le GUID pour le champ : <field>. La recherche est introuvable : <value>. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity> ?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="66cb2-138">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

<span data-ttu-id="66cb2-139">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="66cb2-139">Here are a couple of examples:</span></span>

- <span data-ttu-id="66cb2-140">*Impossible de résoudre le GUID pour le champ : msdyn_vendorprimarycontactperson.msdyn_contactpersonid. La recherche est introuvable : 000056. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="66cb2-140">*Couldn't resolve the guid for the field: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="66cb2-141">*Impossible de résoudre le GUID pour le champ : msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. La recherche est introuvable : V24-1. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1*</span><span class="sxs-lookup"><span data-stu-id="66cb2-141">*Couldn't resolve the guid for the field: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span></span>

<span data-ttu-id="66cb2-142">Si vous avez des enregistrements comportant des valeurs dans ces champs dans l'entité fournisseur, suivez les étapes de la section ci-dessous pour terminer la synchronisation initiale avec succès.</span><span class="sxs-lookup"><span data-stu-id="66cb2-142">If you have records with values in these fields in the vendor entity follow the steps in the below section to complete initial sync successfully.</span></span>

1. <span data-ttu-id="66cb2-143">Dans l'application Finance and Operations, supprimez les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber** du mappage et enregistrez les modifications.</span><span class="sxs-lookup"><span data-stu-id="66cb2-143">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping and save the changes.</span></span>

    1. <span data-ttu-id="66cb2-144">Accédez à la page de mappage en double écriture pour **Fournisseurs V2 (msdyn_vendors)** et sélectionnez l'onglet **Mappages d'entités**. Dans le filtre de gauche, sélectionnez **Finance and Operations apps.Fournisseurs V2**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-144">Navigate to the dual-write mapping page for **Vendors V2 (msdyn_vendors)**, and select the **Entity mappings** tab. In the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="66cb2-145">Dans le filtre de droite, sélectionnez **Ventes.Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-145">In the right filter, select **Sales.Vendor**.</span></span>

    2. <span data-ttu-id="66cb2-146">Recherchez **primarycontactperson** pour trouver le champ source **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-146">Search for **primarycontactperson** to find the source field **PrimaryContactPersonId**.</span></span>
    
    3. <span data-ttu-id="66cb2-147">Cliquez sur le bouton **Actions** et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-147">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![Auto-référence ou référence circulaire 3](media/vend_selfref3.png)
    
    4. <span data-ttu-id="66cb2-149">Répétez l'opération pour supprimer le champ **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-149">Repeat to delete the **InvoiceVendorAccountNumber** field.</span></span>
    
        ![Auto-référence ou référence circulaire 4](media/vend-selfref4.png)
    
    5. <span data-ttu-id="66cb2-151">Enregistrez les modifications de mappage.</span><span class="sxs-lookup"><span data-stu-id="66cb2-151">Save the mapping changes.</span></span>

2. <span data-ttu-id="66cb2-152">Désactivez le suivi des modifications pour l'entité **Fournisseurs V2**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-152">Disable the change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="66cb2-153">Accédez à **Gestion des données \> Entités de données**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-153">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="66cb2-154">Sélectionnez l'entité **Fournisseurs V2**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-154">Select the **Vendors V2** entity.</span></span>
    
    3. <span data-ttu-id="66cb2-155">Cliquez sur **Options** dans la barre de menus, puis sur **Suivi des modifications**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-155">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![Auto-référence ou référence circulaire 5](media/selfref_options.png)
    
    4. <span data-ttu-id="66cb2-157">Cliquez sur **Désactiver le suivi des modifications**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-157">Click **Disable Change Tracking**.</span></span>
    
        ![Auto-référence ou référence circulaire 6](media/selfref_tracking.png)

3. <span data-ttu-id="66cb2-159">Exécutez la synchronisation initiale du mappage **Fournisseurs V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-159">Run the initial sync of **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="66cb2-160">La synchronisation initiale doit s'exécuter correctement sans aucune erreur.</span><span class="sxs-lookup"><span data-stu-id="66cb2-160">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="66cb2-161">Exécutez la synchronisation initiale pour le mappage **Contacts CDS V2 (contacts)**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-161">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="66cb2-162">Vous devez synchroniser ce mappage si vous souhaitez synchroniser le champ de contact principal sur l'entité des fournisseurs, car les enregistrements de contacts doivent également être synchronisés initialement.</span><span class="sxs-lookup"><span data-stu-id="66cb2-162">You must sync this mapping if you want to sync primary contact field on vendors entity as the contacts records also need to be initial synced.</span></span>

5. <span data-ttu-id="66cb2-163">Ajoutez les champs **PrimaryContactPersonId** et **InvoiceVendorAccountNumber** de nouveau dans le mappage **Fournisseurs V2 (msdyn_vendors)** et enregistrez le mappage.</span><span class="sxs-lookup"><span data-stu-id="66cb2-163">Add the fields **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** back to the **Vendors V2 (msdyn_vendors)** mapping and save the mapping.</span></span>

6. <span data-ttu-id="66cb2-164">Exécutez à nouveau la synchronisation initiale du mappage **Fournisseurs V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-164">Run the initial sync again for the **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="66cb2-165">Tous les enregistrements seront synchronisés, car le suivi des modifications est désactivé.</span><span class="sxs-lookup"><span data-stu-id="66cb2-165">All the records will be synced, because change tracking is disabled.</span></span>

7. <span data-ttu-id="66cb2-166">Activez le suivi des modifications pour l'entité **Fournisseurs V2**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-166">Enable change tracking for the **Vendors V2** entity.</span></span>

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="66cb2-167">Résoudre une erreur dans le mappage d'entité Clients V3 vers Comptes</span><span class="sxs-lookup"><span data-stu-id="66cb2-167">Resolve an error in Customers V3 to Accounts entity mapping</span></span>

<span data-ttu-id="66cb2-168">Vous pouvez rencontrer les erreurs de synchronisation initiale suivantes sur le mappage de **Clients V3** vers **Comptes** si les entités comportent des enregistrements existants avec des valeurs dans les champs **ContactPersonID** et **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-168">You might run into the following initial sync errors on the **Customers V3** to **Accounts** mapping if the entities have existing records with values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="66cb2-169">C'est parce que **InvoiceAccount** est un champ qui fait référence à lui-même et que **ContactPersonID** est une référence circulaire dans le mappage des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="66cb2-169">This because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="66cb2-170">*Impossible de résoudre le GUID pour le champ : <field>. La recherche est introuvable : <value>. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity> ?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="66cb2-170">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

- <span data-ttu-id="66cb2-171">*Impossible de résoudre le GUID pour le champ : primarycontactid.msdyn_contactpersonid. La recherche est introuvable : 000056. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="66cb2-171">*Couldn't resolve the guid for the field: primarycontactid.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="66cb2-172">*Impossible de résoudre le GUID pour le champ : msdyn_billingaccount.accountnumber. La recherche est introuvable : 1206-1. Essayez ces URL pour vérifier si les données de référence existent : https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span><span class="sxs-lookup"><span data-stu-id="66cb2-172">*Couldn't resolve the guid for the field: msdyn_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span></span>

<span data-ttu-id="66cb2-173">Si vous avez des enregistrements comportant des valeurs dans ces champs dans l'entité client, suivez les étapes de la section ci-dessous pour terminer la synchronisation initiale avec succès.</span><span class="sxs-lookup"><span data-stu-id="66cb2-173">If you have records with values in these fields in the customer entity follow the steps in the below section to complete initial sync successfully.</span></span> <span data-ttu-id="66cb2-174">Vous pouvez utiliser cette approche pour toutes les entités prêtes à l'emploi telles que les comptes et les contacts.</span><span class="sxs-lookup"><span data-stu-id="66cb2-174">You can use this approach for any out-of-the-box entities such Accounts and Contacts.</span></span>

1. <span data-ttu-id="66cb2-175">Dans l'application Finance and Operations, supprimez les champs **ContactPersonID** et **InvoiceAccount** du mappage **Clients V3 (comptes)** et enregistrez le mappage.</span><span class="sxs-lookup"><span data-stu-id="66cb2-175">In the Finance and Operations app, delete the fields **ContactPersonID** and **InvoiceAccount** from the **Customers V3 (accounts)** mapping and save the mapping.</span></span>

    1. <span data-ttu-id="66cb2-176">Accédez à la page de mappage en double écriture pour **Clients V3 (comptes)** et sélectionnez l'onglet **Mappages d'entités**. Dans le filtre de gauche, sélectionnez **Finance and Operations apps.Clients V3**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-176">Navigate to the dual-write mapping page for **Customers V3 (accounts)**, select the **Entity mappings** tab. In the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="66cb2-177">ns le filtre de droite, sélectionnez **Common Data Service.Compte**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-177">In the right filter, select **Common Data Service.Account**.</span></span>

    2. <span data-ttu-id="66cb2-178">Recherchez **contactperson** pour trouver le champ source **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-178">Search for **contactperson** to find the source field **ContactPersonID**.</span></span>
    
    3. <span data-ttu-id="66cb2-179">Cliquez sur le bouton **Actions** et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-179">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![Auto-référence ou référence circulaire 3](media/cust_selfref3.png)
    
    4. <span data-ttu-id="66cb2-181">Répétez l'opération pour supprimer le champ **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-181">Repeat to delete the **InvoiceAccount** field.</span></span>
    
        ![Auto-référence ou référence circulaire](media/cust_selfref4.png)
    
    5. <span data-ttu-id="66cb2-183">Enregistrez les modifications de mappage.</span><span class="sxs-lookup"><span data-stu-id="66cb2-183">Save the mapping changes.</span></span>

2. <span data-ttu-id="66cb2-184">Désactivez le suivi des modifications pour l'entité **Clients V3**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-184">Disable the change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="66cb2-185">Accédez à **Gestion des données \> Entités de données**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-185">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="66cb2-186">Sélectionnez l'entité **Clients V3**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-186">Select the **Customers V3** entity.</span></span>
    
    3. <span data-ttu-id="66cb2-187">Cliquez sur **Options** dans la barre de menus, puis sur **Suivi des modifications**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-187">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![Auto-référence ou référence circulaire 5](media/selfref_options.png)
    
    4. <span data-ttu-id="66cb2-189">Cliquez sur **Désactiver le suivi des modifications**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-189">Click **Disable Change Tracking**.</span></span>
    
        ![Auto-référence ou référence circulaire 6](media/selfref_tracking.png)

3. <span data-ttu-id="66cb2-191">Exécutez la synchronisation initiale pour le mappage **Clients V3 (Comptes)**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-191">Run the initial sync for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="66cb2-192">La synchronisation initiale doit s'exécuter correctement sans aucune erreur.</span><span class="sxs-lookup"><span data-stu-id="66cb2-192">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="66cb2-193">Exécutez la synchronisation initiale pour le mappage **Contacts CDS V2 (contacts)**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-193">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="66cb2-194">Il existe 2 mappages du même nom.</span><span class="sxs-lookup"><span data-stu-id="66cb2-194">There are 2 maps with the same name.</span></span> <span data-ttu-id="66cb2-195">Sélectionnez celui portant la description **Modèle à double écriture pour la synchronisation entre FO.CDS Fournisseur Contacts V2 et CDS.Contacts. Nécessite un nouveau package \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="66cb2-195">Select the one with the description **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span> <span data-ttu-id="66cb2-196">Dans l'onglet **Détails** du mappage.</span><span class="sxs-lookup"><span data-stu-id="66cb2-196">on the **Details** tab of the map.</span></span>

5. <span data-ttu-id="66cb2-197">Ajoutez les champs **InvoiceAccount** et **ContactPersonId** de nouveau dans le mappage **Clients V3 (Comptes)** et enregistrez le mappage.</span><span class="sxs-lookup"><span data-stu-id="66cb2-197">Add the fields **InvoiceAccount** and **ContactPersonId** back to the **Customers V3 (Accounts)** mapping and save the mapping.</span></span> <span data-ttu-id="66cb2-198">Maintenant, les deux champs **InvoiceAccount** et **ContactPersonId** font à nouveau partie du mode de synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="66cb2-198">Now, both the **InvoiceAccount** field and the **ContactPersonId** field are again part of live sync mode.</span></span> <span data-ttu-id="66cb2-199">À l'étape suivante, vous achèverez la synchronisation initiale de ces champs.</span><span class="sxs-lookup"><span data-stu-id="66cb2-199">In the next step, you complete the initial sync for these fields.</span></span>

6. <span data-ttu-id="66cb2-200">Exécutez la synchronisation à nouveau initiale pour le mappage **Clients V3 (Comptes)**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-200">Run the initial sync again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="66cb2-201">Le suivi des modifications étant désactivé, l'exécution de la synchronisation synchronisera les données pour **InvoiceAccount** et **ContactPersonId** de l'application Finance and Operations vers Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="66cb2-201">Because change tracking is disabled, running the sync will sync the data for **InvoiceAccount** and **ContactPersonId** from the Finance and Operations app to Common Data Service.</span></span>

7. <span data-ttu-id="66cb2-202">Pour synchroniser les données pour **InvoiceAccount** et **ContactPersonId** depuis Common Data Service vers Finance and Operations, vous utilisez un projet d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="66cb2-202">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations, you use a data integration project.</span></span>

    1. <span data-ttu-id="66cb2-203">Dans Power Apps, créez un projet d'intégration de données entre **Ventes.Compte** et les entités **Finance and Operations apps.Clients V3**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-203">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="66cb2-204">La direction des données doit aller de Common Data Service vers l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="66cb2-204">The data direction must be from Common Data Service to the Finance and Operations app.</span></span>  <span data-ttu-id="66cb2-205">Comme **InvoiceAccount** est un nouvel attribut en double écriture, vous pouvez souhaiter ignorer la synchronisation initiale pour cet attribut.</span><span class="sxs-lookup"><span data-stu-id="66cb2-205">Because **InvoiceAccount** is a new attribute in dual-write, you may want to skip initial sync for this attribute.</span></span> <span data-ttu-id="66cb2-206">Pour plus d'informations, voir [Intégration des données dans Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="66cb2-206">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="66cb2-207">L'image suivante montre un projet qui met à jour **CustomerAccount** et **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-207">The following image shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Auto-référence ou référence circulaire](media/cust_selfref6.png)

    2. <span data-ttu-id="66cb2-209">Ajoutez les critères de l'entreprise dans le filtre du côté Common Data Service, car seuls les enregistrements correspondant aux critères de filtrage seront mis à jour dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="66cb2-209">Add the company criteria in the filter on Common Data Service side, because only the records that match filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="66cb2-210">Pour ajouter un filtre, cliquez sur l'icône de filtre.</span><span class="sxs-lookup"><span data-stu-id="66cb2-210">To add a filter, click the filter icon.</span></span> <span data-ttu-id="66cb2-211">Dans la boîte de dialogue **Modifier la requête**, vous pouvez ajouter une requête de filtre telle que **_msdyn_company_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="66cb2-211">In the **Edit query** dialog, you can add a filter query like **_msdyn_company_value eq '\<guid\>'**.</span></span> <span data-ttu-id="66cb2-212">Si l'icône de filtre n'est pas présente, créez un ticket de support pour demander à l'équipe d'intégration de données d'activer la fonction de filtrage sur votre locataire.</span><span class="sxs-lookup"><span data-stu-id="66cb2-212">If the filter icon is not present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span> <span data-ttu-id="66cb2-213">Si vous n'entrez pas de requête de filtre pour **_msdyn_company_value**, tous les enregistrements sont synchronisés.</span><span class="sxs-lookup"><span data-stu-id="66cb2-213">If you do not enter a filter query for **_msdyn_company_value**, then all the records are synced.</span></span>

        ![Auto-référence ou référence circulaire](media/cust_selfref7.png)

        <span data-ttu-id="66cb2-215">Ceci termine la synchronisation initiale des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="66cb2-215">This completes the initial sync of the records.</span></span>

8. <span data-ttu-id="66cb2-216">Activez le suivi des modifications pour l'entité **Clients V3** dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="66cb2-216">Enable change tracking for the **Customers V3** entity in the Finance and Operations app.</span></span>

