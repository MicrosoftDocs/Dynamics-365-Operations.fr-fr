---
title: Résoudre les problèmes lors de la configuration initiale
description: Cette rubrique fournit des informations pour la résolution des problèmes pouvant survenir lors de la configuration initiale de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.
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
ms.openlocfilehash: e20c9c5e1250c8e65b5642a7c45d7ae859315697
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172666"
---
# <a name="troubleshoot-issues-during-initial-setup"></a><span data-ttu-id="62b06-103">Résoudre les problèmes lors de la configuration initiale</span><span class="sxs-lookup"><span data-stu-id="62b06-103">Troubleshoot issues during initial setup</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="62b06-104">Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="62b06-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="62b06-105">Notamment elle fournit des informations pour la résolution des problèmes pouvant survenir lors de la configuration initiale de l'intégration de la double écriture.</span><span class="sxs-lookup"><span data-stu-id="62b06-105">Specifically, it provides information that can help you fix issues that might occur during the initial setup of dual-write integration.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62b06-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="62b06-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="62b06-107">La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="62b06-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-link-a-finance-and-operations-app-to-common-data-service"></a><span data-ttu-id="62b06-108">Vous ne pouvez pas lier une application Finance and Operations à Common Data Service</span><span class="sxs-lookup"><span data-stu-id="62b06-108">You can't link a Finance and Operations app to Common Data Service</span></span>

<span data-ttu-id="62b06-109">**Informations d'identification requises pour configurer la double écriture :** admin client Azure AD</span><span class="sxs-lookup"><span data-stu-id="62b06-109">**Required credentials to set up dual-write:** Azure AD tenant admin</span></span>

<span data-ttu-id="62b06-110">Les erreurs sur la page **Lien de configuration vers Common Data Service** sont généralement causés par des problèmes de configuration ou d'autorisations incomplets.</span><span class="sxs-lookup"><span data-stu-id="62b06-110">Errors on the **Setup link to Common Data Service** page are usually caused by incomplete setup or permissions issues.</span></span> <span data-ttu-id="62b06-111">Veillez à ce que l'ensemble du contrôle d'intégrité passe sur la page **Lien de configuration vers Common Data Service**, comme indiqué dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="62b06-111">Make sure that the whole health check passes on the **Setup link to Common Data Service** page, as shown in the following illustration.</span></span> <span data-ttu-id="62b06-112">Vous ne pouvez pas lier la double écriture sauf si le contrôle d'intégrité réussit.</span><span class="sxs-lookup"><span data-stu-id="62b06-112">You can't link dual-write unless the whole health check passes.</span></span>

![Contrôle d'intégrité réussi](media/health_check.png)

<span data-ttu-id="62b06-114">Vous devez avoir les identifiants d'admin client Azure AD pour lier les environnements Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="62b06-114">You must have Azure AD tenant admin credentials to link the Finance and Operations and Common Data Service environments.</span></span> <span data-ttu-id="62b06-115">Après avoir lié les environnements, les utilisateurs peuvent se connecter en utilisant leurs informations d'identification de compte et mettre à jour une carte d'entité existante.</span><span class="sxs-lookup"><span data-stu-id="62b06-115">After you link the environments, users can sign in by using their account credentials and update an existing entity map.</span></span>

## <a name="error-when-you-open-the-link-to-common-data-service-page"></a><span data-ttu-id="62b06-116">Erreur lorsque vous ouvrez la page Lier à Common Data Service</span><span class="sxs-lookup"><span data-stu-id="62b06-116">Error when you open the Link to Common Data Service page</span></span>

<span data-ttu-id="62b06-117">**Informations d'identification requises pour résoudre le problème :** admin client Azure AD</span><span class="sxs-lookup"><span data-stu-id="62b06-117">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="62b06-118">Vous pouvez recevoir le message d'erreur suivant lorsque vous ouvrez la page **Lier à Common Data Service** dans une application Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="62b06-118">You might receive the following error message when you open the **Link to Common Data Service** page in a Finance and Operations app:</span></span>

<span data-ttu-id="62b06-119">*Le code d'état de réponse n'indique pas la réussite : 404 (Introuvable).*</span><span class="sxs-lookup"><span data-stu-id="62b06-119">*Response status code does not indicate success: 404 (Not Found).*</span></span>

<span data-ttu-id="62b06-120">Cette erreur se produit lorsque l'étape de consentement n'est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="62b06-120">This error occurs when the consent step hasn't been completed.</span></span> <span data-ttu-id="62b06-121">Pour valider si l'étape de consentement est terminée, connectez-vous à portal.Azure.com en utilisant le compte admin client Azure AD et voyez si l'application tierce avec l'ID **33976c19-1db5-4c02-810e-c243db79efde** apparaît dans la liste **Applications d'entreprise** Azure AD.</span><span class="sxs-lookup"><span data-stu-id="62b06-121">To validate whether the consent step has been completed, sign in to portal.Azure.com by using the Azure AD tenant admin account, and see whether the third-party app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** appears in the Azure AD **Enterprise applications** list.</span></span> <span data-ttu-id="62b06-122">Si ce n'est pas le cas, vous devez fournir le consentement de l'application.</span><span class="sxs-lookup"><span data-stu-id="62b06-122">If it doesn't, you must provide app consent.</span></span>

<span data-ttu-id="62b06-123">Pour fournir le consentement de l'application, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="62b06-123">To provide app consent, follow these steps.</span></span>

1. <span data-ttu-id="62b06-124">Ouvrez l'URL suivante en utilisant vos informations d'identification d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="62b06-124">Open the following URL by using your admin credentials.</span></span> <span data-ttu-id="62b06-125">Vous devriez être invité à donner votre consentement.</span><span class="sxs-lookup"><span data-stu-id="62b06-125">You should be prompted for consent.</span></span>

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. <span data-ttu-id="62b06-126">Sélectionnez **Accepter** pour indiquer que vous donnez votre consentement pour installer l'application avec l'ID **33976c19-1db5-4c02-810e-c243db79efde** dans votre client.</span><span class="sxs-lookup"><span data-stu-id="62b06-126">Select **Accept** to indicate that you're giving your consent to install the app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** in your tenant.</span></span>

    > [!TIP]
    > <span data-ttu-id="62b06-127">Cette application est nécessaire pour lier les applications Common Data Service et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="62b06-127">This app is required to link Common Data Service and Finance and Operations apps.</span></span> <span data-ttu-id="62b06-128">Si vous rencontrez des problèmes avec cette étape, ouvrez votre navigateur en mode navigation privée (dans Google Chrome) ou en mode InPrivate (dans Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="62b06-128">If you have trouble with this step, open your browser in incognito mode (in Google Chrome) or InPrivate mode (in Microsoft Edge).</span></span>

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a><span data-ttu-id="62b06-129">Vérifier que les données d'entreprise et les équipes en double écriture sont correctement configurées lors de la liaison</span><span class="sxs-lookup"><span data-stu-id="62b06-129">Verify that company data and dual-write teams are set up correctly during linking</span></span>

<span data-ttu-id="62b06-130">Pour garantir le bon fonctionnement de la double écriture, les sociétés que vous sélectionnez lors de la configuration sont créées dans l'environnement Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="62b06-130">To ensure that dual-write works correctly, the companies that you select during configuration are created in the Common Data Service environment.</span></span> <span data-ttu-id="62b06-131">Par défaut, ces sociétés sont en lecture seule et la propriété **IsDualWriteEnable** est définie sur la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="62b06-131">By default, these companies are read-only, and the **IsDualWriteEnable** property is set to **True**.</span></span> <span data-ttu-id="62b06-132">De plus, le propriétaire et l'équipe de l'unité commerciale propriétaire par défaut et l'équipe sont créés et comprennent le nom de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="62b06-132">In addition, the default owning business unit owner and team are created and include the company name.</span></span> <span data-ttu-id="62b06-133">Avant d'activer les cartes, vérifiez que le propriétaire de l'équipe par défaut est spécifié.</span><span class="sxs-lookup"><span data-stu-id="62b06-133">Before you enable the maps, verify that the default team owner is specified.</span></span> <span data-ttu-id="62b06-134">Pour trouver l'entité **Sociétés (CDM\_Company)**, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="62b06-134">To find the **Companies (CDM\_Company)** entity, follow these steps.</span></span>

1. <span data-ttu-id="62b06-135">Dans l'application pilotée par modèle dans Dynamics 365, sélectionnez le filtre dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="62b06-135">In the model-driven app in Dynamics 365, select the filter in the upper-right corner.</span></span>
2. <span data-ttu-id="62b06-136">Dans la liste déroulante sélectionnez **Société**.</span><span class="sxs-lookup"><span data-stu-id="62b06-136">In the drop-down list, select **Company**.</span></span>
3. <span data-ttu-id="62b06-137">Sélectionnez **Exécuter** pour voir les résultats.</span><span class="sxs-lookup"><span data-stu-id="62b06-137">Select **Run** to see the results.</span></span>
4. <span data-ttu-id="62b06-138">Sélectionnez la société qui était liée lorsque vous avez configuré la double écriture.</span><span class="sxs-lookup"><span data-stu-id="62b06-138">Select the company that was linked when you configured dual-write.</span></span>
5. <span data-ttu-id="62b06-139">Vérifiez que le champ **Équipe propriétaire par défaut** a une valeur.</span><span class="sxs-lookup"><span data-stu-id="62b06-139">Verify that the **Default owning team** field has a value.</span></span> <span data-ttu-id="62b06-140">Dans l'illustration suivante, le champ **Équipe propriétaire par défaut** est défini sur **Double écriture USMF**.</span><span class="sxs-lookup"><span data-stu-id="62b06-140">In the following illustration, the **Default owning team** field is set to **USMF Dual Write**.</span></span>

    ![Vérification de l'équipe propriétaire par défaut](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-entities-or-companies-that-can-be-linked-for-dual-write"></a><span data-ttu-id="62b06-142">Trouver la limite du nombre d'entités juridiques ou de sociétés pouvant être liées pour la double écriture</span><span class="sxs-lookup"><span data-stu-id="62b06-142">Find the limit on the number of legal entities or companies that can be linked for dual-write</span></span>

<span data-ttu-id="62b06-143">Vous pouvez recevoir le message d'erreur suivant lorsque vous essayez d'activer des cartes :</span><span class="sxs-lookup"><span data-stu-id="62b06-143">You might receive the following error message when you try to enable maps:</span></span>

<span data-ttu-id="62b06-144">*Échec de la double écriture - Échec de l'enregistrement du plugin : \[(Impossible d'obtenir la carte de partition pour le projet DWM - 1ae35e60-4bc2-4905-88ea-69efd3b29260 - 7f12cb89-1550-42e2-858e-4761fc1443ea. L'erreur dépasse le nombre maximal de partitions autorisé pour le mappage DWM - 1ae35e60-4bc2-4905-88ea-69efd3b29260 - 7f12cb89-1550-42e2-858e-4761fc1443ea) \], Une ou plusieurs erreurs se sont produites.*</span><span class="sxs-lookup"><span data-stu-id="62b06-144">*Dual write failure - Plugin registration failed: \[(Unable to get partition map for project DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Exceeds the maximum partitions allowed for mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], One or more errors occurred.*</span></span>

<span data-ttu-id="62b06-145">La limite actuelle lorsque vous liez les environnements est d'environ 40 entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="62b06-145">The current limit when you link the environments is approximately 40 legal entities.</span></span> <span data-ttu-id="62b06-146">Cette erreur se produit si vous essayez d'activer des cartes et si plus de 40 entités juridiques sont liées entre les environnements.</span><span class="sxs-lookup"><span data-stu-id="62b06-146">This error occurs if you try to enable maps, and more than 40 legal entities are linked between the environments.</span></span>