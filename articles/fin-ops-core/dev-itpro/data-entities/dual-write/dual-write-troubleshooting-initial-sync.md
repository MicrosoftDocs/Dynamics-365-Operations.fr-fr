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
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172712"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="546fb-103">Résoudre les problèmes lors de la synchronisation initiale</span><span class="sxs-lookup"><span data-stu-id="546fb-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="546fb-104">Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="546fb-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="546fb-105">Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes susceptibles de survenir pendant la synchronisation initiale.</span><span class="sxs-lookup"><span data-stu-id="546fb-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="546fb-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="546fb-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="546fb-107">La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="546fb-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="546fb-108">Vérifier les erreurs de synchronisation initiales dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="546fb-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="546fb-109">Après avoir activé les modèles de mappage, le statut des cartes doit être **En cours d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="546fb-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="546fb-110">Si le statut est défini sur **Pas en cours d'exécution**, des erreurs se sont produites lors de la synchronisation initiale.</span><span class="sxs-lookup"><span data-stu-id="546fb-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="546fb-111">Pour afficher les erreurs, sélectionnez l'onglet **Détails de la synchronisation initiale** sur la page **Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="546fb-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Onglet Détails de la synchronisation initiale](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="546fb-113">Vous ne pouvez pas terminer la synchronisation initiale : 400 Bad Request</span><span class="sxs-lookup"><span data-stu-id="546fb-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="546fb-114">**Rôle requis pour résoudre le problème :** Administrateur système</span><span class="sxs-lookup"><span data-stu-id="546fb-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="546fb-115">Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez d'exécuter le mappage et la synchronisation initiale :</span><span class="sxs-lookup"><span data-stu-id="546fb-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="546fb-116">*Le serveur distant a renvoyé une erreur : (400) Bad Request.), l'exportation AX a rencontré une erreur*</span><span class="sxs-lookup"><span data-stu-id="546fb-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="546fb-117">Voici un exemple du message de l'intégralité du message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="546fb-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="546fb-118">Si cette erreur se produit régulièrement et si vous ne pouvez pas terminer la synchronisation initiale, procédez comme suit pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="546fb-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="546fb-119">Connectez-vous à la machine virtuelle pour l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="546fb-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="546fb-120">Ouvrez Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="546fb-120">Open Microsoft Management Console.</span></span> 
3. <span data-ttu-id="546fb-121">Dans le volet **Services**, assurez-vous que le service de structure d'exportation et d'importation des données Microsoft Dynamics 365 est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="546fb-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="546fb-122">Redémarrez-le s'il a été arrêté, car la synchronisation initiale l'exige.</span><span class="sxs-lookup"><span data-stu-id="546fb-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="546fb-123">Erreur de synchronisation initiale : 403 Forbidden</span><span class="sxs-lookup"><span data-stu-id="546fb-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="546fb-124">Vous pouvez recevoir le message d'erreur suivant pendant la synchronisation initiale :</span><span class="sxs-lookup"><span data-stu-id="546fb-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="546fb-125">*(\[Forbidden\], Le serveur distant a renvoyé une erreur : (403) Forbidden.), l'exportation AX a rencontré une erreur*</span><span class="sxs-lookup"><span data-stu-id="546fb-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="546fb-126">Pour régler le problème, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="546fb-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="546fb-127">Connectez-vous à l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="546fb-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="546fb-128">Sur la page **Applications Azure Active Directory**, supprimez le client **DtAppID**, puis ajoutez-le à nouveau.</span><span class="sxs-lookup"><span data-stu-id="546fb-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Liste des applications Azure AD](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a><span data-ttu-id="546fb-130">Échecs d'auto-référence lors de la synchronisation initiale</span><span class="sxs-lookup"><span data-stu-id="546fb-130">Self-reference failures during initial synchronization</span></span>

<span data-ttu-id="546fb-131">Vous pouvez recevoir un message d'erreur qui ressemble à l'exemple suivant si l'un de vos mappages a des références automatiques :</span><span class="sxs-lookup"><span data-stu-id="546fb-131">You might receive an error message that resembles the following example if any of your mappings have self-references:</span></span>

<span data-ttu-id="546fb-132">*Sur les fournisseurs V2, l'erreur suivante : ID enregistrement : nouvel enregistrement, Message d'erreur : Impossible de résoudre le guid pour le champ : msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. La valeur de recherche est introuvable : CN-001. Essayez cette URL pour vérifier si les données de référence existent : `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span><span class="sxs-lookup"><span data-stu-id="546fb-132">*On the Vendors V2, the following error: Record Id: new record, ErrorMessage: Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup value was not found: CN-001. Try this URL(s) to check if the reference data exists: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span></span>

<span data-ttu-id="546fb-133">Ce type d'erreur se produit lors de la synchronisation initiale des mappages dotés d'auto-références.</span><span class="sxs-lookup"><span data-stu-id="546fb-133">This type of error occurs during initial synchronization of mappings that have self-references.</span></span> <span data-ttu-id="546fb-134">Dans l'exemple précédent, le compte de facture de champ fait référence à l'entité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="546fb-134">In the preceding example, the field invoice account references the vendor entity.</span></span>

<span data-ttu-id="546fb-135">Pour résoudre le problème, vous devrez peut-être exécuter le mappage deux fois avant la réussite de la synchronisation initiale.</span><span class="sxs-lookup"><span data-stu-id="546fb-135">To fix the issue, you might have to run the mapping two times before the initial synchronization is successful.</span></span>

