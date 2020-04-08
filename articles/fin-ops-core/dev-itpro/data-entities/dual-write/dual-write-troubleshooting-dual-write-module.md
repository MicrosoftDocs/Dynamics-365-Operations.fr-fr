---
title: Résoudre les problèmes liés au module Double écriture dans les applications Finance and Operations
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172758"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="3b1a0-103">Résoudre les problèmes liés au module Double écriture dans les applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3b1a0-103">Troubleshoot issues with the Dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="3b1a0-104">Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="3b1a0-105">Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés au module **Double écriture** dans les applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b1a0-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3b1a0-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="3b1a0-107">La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="3b1a0-108">Vous ne pouvez pas charger le module Double écriture dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3b1a0-108">You can't load the Dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="3b1a0-109">Si vous ne pouvez pas ouvrir la page **Double écriture** en sélectionnant la vignette **Double écriture** dans l'espace de travail **Gestion des données**, le service d'intégration de données est probablement en panne.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="3b1a0-110">Créez un ticket de support pour demander un redémarrage du service d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a><span data-ttu-id="3b1a0-111">Erreur lorsque vous essayez de créer un nouveau mappage d'entité</span><span class="sxs-lookup"><span data-stu-id="3b1a0-111">Error when you try to create a new entity mapping</span></span>

<span data-ttu-id="3b1a0-112">**Informations d'identification requises pour résoudre le problème :** admin client Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b1a0-112">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="3b1a0-113">Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez de configurer une nouvelle entité pour la double écriture :</span><span class="sxs-lookup"><span data-stu-id="3b1a0-113">You might receive the following error message when you try to configure a new entity for dual-write:</span></span>

<span data-ttu-id="3b1a0-114">*Le code d'état de réponse n'indique pas la réussite : 401 (Non autorisé).*</span><span class="sxs-lookup"><span data-stu-id="3b1a0-114">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>

<span data-ttu-id="3b1a0-115">Cette erreur se produit, car seul un admin client Azure AD peut ajouter un nouveau mappage d'entité.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-115">This error occurs because only an Azure AD tenant admin can add a new entity mapping.</span></span>

<span data-ttu-id="3b1a0-116">Pour résoudre le problème, connectez-vous à l'application Finance and Operations en tant qu'admin client Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-116">To fix the issue, sign in to the Finance and Operations app as an Azure AD admin tenant.</span></span> <span data-ttu-id="3b1a0-117">Vous devez également aller sur web.PowerApps.com et revalider votre connexion.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-117">You must also go to web.PowerApps.com and revalidate your connection.</span></span>

## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="3b1a0-118">Erreur lorsque vous ouvrez l'interface utilisateur de double écriture</span><span class="sxs-lookup"><span data-stu-id="3b1a0-118">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="3b1a0-119">Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez d'accéder à la double écriture à partir de l'espace de travail **Gestion des données** :</span><span class="sxs-lookup"><span data-stu-id="3b1a0-119">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="3b1a0-120">*login.microsoftonline.com a refusé de se connecter.*</span><span class="sxs-lookup"><span data-stu-id="3b1a0-120">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="3b1a0-121">Pour résoudre le problème, connectez-vous à l'aide d'une fenêtre InPrivate dans Microsoft Edge, une fenêtre de navigation privée dans Chromium ou une fenêtre de navigation privée dans Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-121">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="3b1a0-122">Vous devez également débloquer ou effacer les cookies tiers.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-122">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="3b1a0-123">Erreur lorsque vous liez l'environnement pour la double écriture ou ajoutez un nouveau mappage d'entité</span><span class="sxs-lookup"><span data-stu-id="3b1a0-123">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="3b1a0-124">**Informations d'identification requises pour résoudre le problème :** admin client Azure AD</span><span class="sxs-lookup"><span data-stu-id="3b1a0-124">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="3b1a0-125">Vous pouvez rencontrer l'erreur suivante lors de la liaison ou de la création de cartes :</span><span class="sxs-lookup"><span data-stu-id="3b1a0-125">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="3b1a0-126">*Le code d'état de réponse n'indique pas la réussite : 403 (échange de jetons).<br> ID de session : \<votre identifiant de session\><br> ID d'activité racine : \<votre identifiant d'activité racine\>*</span><span class="sxs-lookup"><span data-stu-id="3b1a0-126">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="3b1a0-127">Cette erreur peut se produire si vous ne disposez pas des autorisations suffisantes pour lier la double écriture ou créer des cartes.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-127">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="3b1a0-128">Vous devez utiliser un compte admin client Azure AD pour lier les environnements et ajouter de nouveaux mappages d'entités.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-128">You must use an Azure AD tenant admin account to link environments and add new entity mappings.</span></span> <span data-ttu-id="3b1a0-129">Cependant, après la configuration, vous pouvez utiliser un compte non administrateur pour surveiller l'état et modifier les mappages.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-129">However, after setup, you can use a non-admin account to monitor status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="3b1a0-130">Erreur lorsque vous arrêtez le mappage d'entité</span><span class="sxs-lookup"><span data-stu-id="3b1a0-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="3b1a0-131">Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez d'arrêter les mappages d'entités :</span><span class="sxs-lookup"><span data-stu-id="3b1a0-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="3b1a0-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Le serveur distant a renvoyé une erreur : (403) Forbidden.*</span><span class="sxs-lookup"><span data-stu-id="3b1a0-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="3b1a0-133">Cette erreur se produit lorsque l'environnement Common Data Service associé n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="3b1a0-134">Pour résoudre le problème, créez un ticket pour l'équipe d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="3b1a0-135">Associez le suivi du réseau afin que l'équipe d'intégration de données puisse marquer les cartes comme **Pas en cours d'exécution** à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="3b1a0-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>
