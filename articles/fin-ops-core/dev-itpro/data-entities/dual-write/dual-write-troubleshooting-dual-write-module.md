---
title: Résoudre les problèmes de double écriture dans les applications Finance and Operations
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés au module Double écriture dans les applications Finance and Operations.
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
ms.openlocfilehash: 3ffeb2de0acc1761bccf62a1a124852c504e2a3a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5131243"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a><span data-ttu-id="e46d2-103">Résoudre les problèmes de double écriture dans les applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e46d2-103">Troubleshoot dual-write issues in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e46d2-104">Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e46d2-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="e46d2-105">Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés au module **Double écriture** dans les applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e46d2-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e46d2-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e46d2-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="e46d2-107">La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="e46d2-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="e46d2-108">Vous ne pouvez pas charger le module Double écriture dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e46d2-108">You can't load the dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="e46d2-109">Si vous ne pouvez pas ouvrir la page **Double écriture** en sélectionnant la vignette **Double écriture** dans l’espace de travail **Gestion des données**, le service d’intégration de données est probablement en panne.</span><span class="sxs-lookup"><span data-stu-id="e46d2-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="e46d2-110">Créez un ticket de support pour demander un redémarrage du service d’intégration de données.</span><span class="sxs-lookup"><span data-stu-id="e46d2-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-table-map"></a><span data-ttu-id="e46d2-111">Erreur lorsque vous essayez de créer un mappage de table</span><span class="sxs-lookup"><span data-stu-id="e46d2-111">Error when you try to create a new table map</span></span>

<span data-ttu-id="e46d2-112">**Informations d’identification requises pour résoudre le problème :** Le même utilisateur qui a configuré la double écriture.</span><span class="sxs-lookup"><span data-stu-id="e46d2-112">**Required credentials to fix the issue:** The same user that setup dual-write.</span></span>

<span data-ttu-id="e46d2-113">Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez de configurer une nouvelle table pour la double écriture.</span><span class="sxs-lookup"><span data-stu-id="e46d2-113">You might receive the following error message when you try to configure a new table for dual-write.</span></span> <span data-ttu-id="e46d2-114">Le seul utilisateur qui peut créer un mappage est celui qui a configuré la connexion à double écriture.</span><span class="sxs-lookup"><span data-stu-id="e46d2-114">The only user that can create a map is the user who setup the dual-write connection.</span></span>

<span data-ttu-id="e46d2-115">*Le code d’état de réponse n’indique pas la réussite : 401 (Non autorisé).*</span><span class="sxs-lookup"><span data-stu-id="e46d2-115">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>


## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="e46d2-116">Erreur lorsque vous ouvrez l’interface utilisateur de double écriture</span><span class="sxs-lookup"><span data-stu-id="e46d2-116">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="e46d2-117">Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’accéder à la double écriture à partir de l’espace de travail **Gestion des données** :</span><span class="sxs-lookup"><span data-stu-id="e46d2-117">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="e46d2-118">*login.microsoftonline.com a refusé de se connecter.*</span><span class="sxs-lookup"><span data-stu-id="e46d2-118">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="e46d2-119">Pour résoudre le problème, connectez-vous à l’aide d’une fenêtre InPrivate dans Microsoft Edge, une fenêtre de navigation privée dans Chromium ou une fenêtre de navigation privée dans Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="e46d2-119">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="e46d2-120">Vous devez également débloquer ou effacer les cookies tiers.</span><span class="sxs-lookup"><span data-stu-id="e46d2-120">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a><span data-ttu-id="e46d2-121">Erreur lorsque vous liez l’environnement pour la double écriture ou ajoutez un nouveau mappage de table</span><span class="sxs-lookup"><span data-stu-id="e46d2-121">Error when you link the environment for dual-write or add a new table mapping</span></span>

<span data-ttu-id="e46d2-122">**Rôle requis pour corriger le problème :** Administrateur système dans les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e46d2-122">**Required role to fix the issue:** System administrator in both Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="e46d2-123">Vous pouvez rencontrer l’erreur suivante lors de la liaison ou de la création de cartes :</span><span class="sxs-lookup"><span data-stu-id="e46d2-123">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="e46d2-124">*Le code d’état de réponse n’indique pas la réussite : 403 (échange de jetons).<br> ID de session : \<your session id\><br> ID d’activité racine : \<your root activity id\>*</span><span class="sxs-lookup"><span data-stu-id="e46d2-124">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="e46d2-125">Cette erreur peut se produire si vous ne disposez pas des autorisations suffisantes pour lier la double écriture ou créer des cartes.</span><span class="sxs-lookup"><span data-stu-id="e46d2-125">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="e46d2-126">Cette erreur peut également se produire si l’environnement Dataverse a été réinitialisé sans dissocier la double écriture.</span><span class="sxs-lookup"><span data-stu-id="e46d2-126">This error can also occur if the Dataverse environment was reset without unlinking dual-write.</span></span> <span data-ttu-id="e46d2-127">Tout utilisateur ayant un rôle d’administrateur système dans les applications Finance and Operations et Dataverse peut relier les environnements.</span><span class="sxs-lookup"><span data-stu-id="e46d2-127">Any user with system administrator role in both Finance and Operations apps and Dataverse can link the environments.</span></span> <span data-ttu-id="e46d2-128">Seul l’utilisateur qui a configuré la connexion à double écriture peut ajouter de nouveaux mappages de tables.</span><span class="sxs-lookup"><span data-stu-id="e46d2-128">Only the user who setup the dual-write connection can add new table maps.</span></span> <span data-ttu-id="e46d2-129">Après la configuration, tout utilisateur ayant un rôle d’administrateur système peut surveiller le statut et modifier les mappages.</span><span class="sxs-lookup"><span data-stu-id="e46d2-129">After setup, any user with system administrator role can monitor the status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-table-mapping"></a><span data-ttu-id="e46d2-130">Erreur lorsque vous arrêtez le mappage de tables</span><span class="sxs-lookup"><span data-stu-id="e46d2-130">Error when you stop the table mapping</span></span>

<span data-ttu-id="e46d2-131">Vous pouvez recevoir le message d’erreur suivant lorsque vous essayez d’arrêter les mappages de tables :</span><span class="sxs-lookup"><span data-stu-id="e46d2-131">You might receive the following error message when you try to stop the table mappings:</span></span>

<span data-ttu-id="e46d2-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Le serveur distant a renvoyé une erreur : (403) Forbidden.*</span><span class="sxs-lookup"><span data-stu-id="e46d2-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="e46d2-133">Cette erreur se produit lorsque l’environnement Dataverse associé n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="e46d2-133">This error occurs when the linked Dataverse environment isn't available.</span></span>

<span data-ttu-id="e46d2-134">Pour résoudre le problème, créez un ticket pour l’équipe d’intégration de données.</span><span class="sxs-lookup"><span data-stu-id="e46d2-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="e46d2-135">Associez le suivi du réseau afin que l’équipe d’intégration de données puisse marquer les cartes comme **Pas en cours d’exécution** à l’arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="e46d2-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>

## <a name="error-while-trying-to-start-a-table-mapping"></a><span data-ttu-id="e46d2-136">Erreur lors de la tentative de démarrage d’un mappage de tables</span><span class="sxs-lookup"><span data-stu-id="e46d2-136">Error while trying to start a table mapping</span></span>

<span data-ttu-id="e46d2-137">Vous pouvez recevoir une erreur comme celle-ci lorsque vous essayez de définir cet état d’un mappage sur **Exécution en cours** :</span><span class="sxs-lookup"><span data-stu-id="e46d2-137">You might receive an error like the following when you try to set that state of a mapping to **Running**:</span></span>

<span data-ttu-id="e46d2-138">*Impossible de terminer la synchronisation initiale des données. Erreur : échec de double écriture - échec de l’enregistrement du plug-in : impossible de créer des métadonnées de recherche en double écriture. La référence d’objet d’erreur n’est pas définie sur une instance d’un objet.*</span><span class="sxs-lookup"><span data-stu-id="e46d2-138">*Unable to complete initial data sync. Error: dual-write failure - plugin registration failed: Unable to build dual-write lookup metadata. Error object reference not set to an instance of an object.*</span></span>

<span data-ttu-id="e46d2-139">Le correctif de cette erreur dépend de la cause de l’erreur :</span><span class="sxs-lookup"><span data-stu-id="e46d2-139">The fix for this error depends on the cause of the error:</span></span>

+ <span data-ttu-id="e46d2-140">Si le mappage a des mappages dépendants, assurez-vous d’activer les mappages dépendants de ce mappage de table.</span><span class="sxs-lookup"><span data-stu-id="e46d2-140">If the mapping has dependent mappings, then make sure to enable the dependent mappings of this table mapping.</span></span>
+ <span data-ttu-id="e46d2-141">Le mappage peut ne pas contenir de colonnes sources ou de destination.</span><span class="sxs-lookup"><span data-stu-id="e46d2-141">The mapping might be missing source or destination columns.</span></span> <span data-ttu-id="e46d2-142">Si une colonne de l’application Finance and Operations est manquant, suivez les étapes de la section [Problème de colonnes de table manquantes sur les mappages](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps).</span><span class="sxs-lookup"><span data-stu-id="e46d2-142">If a column in the Finance and Operations app is missing, then follow the steps in the section [Missing table columns issue on maps](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps).</span></span> <span data-ttu-id="e46d2-143">Si une colonne dans Dataverse est manquante, cliquez sur **Actualiser les tables** sur le mappage afin que les colonnes soient automatiquement remplies à nouveau dans le mappage.</span><span class="sxs-lookup"><span data-stu-id="e46d2-143">If a column in Dataverse is missing, then click **Refresh tables** button on the mapping so that the columns are automatically populated back into the mapping.</span></span>
