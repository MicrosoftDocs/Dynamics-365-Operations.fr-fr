---
title: Regulatory Configuration Services (RCS) - Fonctions de globalisation
description: Cette rubrique explique comment utiliser Microsoft Regulatory Configuration Services (RCS) et le référentiel global pour créer et utiliser des fonctions de globalisation.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: ae46dab5250fbe8096f43e420cb7ef33a5862af0
ms.sourcegitcommit: 97206552616b248f88e516fea08b3f059257e8d1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3432045"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a><span data-ttu-id="1387e-103">Regulatory Configuration Services (RCS) - Fonctions de globalisation</span><span class="sxs-lookup"><span data-stu-id="1387e-103">Regulatory Configuration Services (RCS) - Globalization features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1387e-104">Vous pouvez utiliser Microsoft Regulatory Configuration Services (RCS) pour créer une fonctionnalité de globalisation utilisable dans les services de globalisation, tels qu'un service de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="1387e-104">You can use Microsoft Regulatory Configuration Services (RCS) to create a Globalization feature that can be used in Globalization services, such as an e-invoicing service.</span></span> <span data-ttu-id="1387e-105">RCS vous permet d'effectuer ces tâches :</span><span class="sxs-lookup"><span data-stu-id="1387e-105">RCS lets you perform these tasks:</span></span>

- <span data-ttu-id="1387e-106">Définir les composants associés à une fonction.</span><span class="sxs-lookup"><span data-stu-id="1387e-106">Define related components of a feature.</span></span>
- <span data-ttu-id="1387e-107">Gérer le cycle de vie des fonctionnalités via le statut des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="1387e-107">Manage the feature lifecycle through a feature's status.</span></span>
- <span data-ttu-id="1387e-108">Rendre une fonctionnalité disponible pour des environnements définis.</span><span class="sxs-lookup"><span data-stu-id="1387e-108">Make a feature available for defined environments.</span></span>
- <span data-ttu-id="1387e-109">Partager une fonctionnalité avec d'autres organisations.</span><span class="sxs-lookup"><span data-stu-id="1387e-109">Share a feature with other organizations.</span></span>

<span data-ttu-id="1387e-110">Les procédures suivantes expliquent comment un utilisateur dans RCS peut ajouter une fonctionnalité de globalisation et des composants associés, mettre à jour le statut de la fonctionnalité et rendre la fonctionnalité disponible afin qu'elle puisse être utilisée dans les services de globalisation.</span><span class="sxs-lookup"><span data-stu-id="1387e-110">The following procedures explain how a user in RCS can add a Globalization feature and related components, update the feature's status, and make the feature available so that it can be used in Globalization services.</span></span>

<span data-ttu-id="1387e-111">Avant de terminer les procédures, vous devez effectuer les étapes liées aux tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1387e-111">Before you complete the procedures, you must complete the steps that are related to the following tasks:</span></span>

- <span data-ttu-id="1387e-112">Accéder à une instance RCS.</span><span class="sxs-lookup"><span data-stu-id="1387e-112">Accessing an RCS instance.</span></span>
- <span data-ttu-id="1387e-113">Créer et activer un fournisseur de configuration.</span><span class="sxs-lookup"><span data-stu-id="1387e-113">Creating and activating a configuration provider.</span></span> <span data-ttu-id="1387e-114">Pour plus d'informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1387e-114">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="1387e-115">Dans votre instance d'applications Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1387e-115">In your Finance and Operations apps instance, follow these steps.</span></span>

1. <span data-ttu-id="1387e-116">Accédez à **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="1387e-116">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="1387e-117">Si vous n'avez pas d'environnement RCS configuré dans votre société, sélectionnez **Regulatory services – Configuration** et suivez les instructions pour en mettre un en service.</span><span class="sxs-lookup"><span data-stu-id="1387e-117">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration**, and follow the instructions to provision one.</span></span>

> [!NOTE]
> <span data-ttu-id="1387e-118">Si un environnement RCS a déjà été configuré pour votre entreprise, utilisez l'URL de la page pour accéder à l'environnement en sélectionnant l'option de connexion.</span><span class="sxs-lookup"><span data-stu-id="1387e-118">If an RCS environment has already been provisioned for your company, use the page URL to access the environment by selecting the sign-in option.</span></span>

## <a name="turn-on-the-globalization-features"></a><span data-ttu-id="1387e-119">Activer les fonctionnalités de globalisation</span><span class="sxs-lookup"><span data-stu-id="1387e-119">Turn on the Globalization features</span></span>

1. <span data-ttu-id="1387e-120">Dans votre instance RCS, sélectionnez la vignette **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="1387e-120">In your RCS instance, select the **Feature management** tile.</span></span>
2. <span data-ttu-id="1387e-121">Dans l'espace de travail **Gestion des fonctionnalités**, sélectionnez **Fonctionnalités de globalisation** dans la liste, puis sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="1387e-121">In the **Feature management** workspace, select **Globalization features** in the list, and then select **Enable now**.</span></span>

    ![Fonctionnalités de globalisation dans la gestion des fonctionnalités](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a><span data-ttu-id="1387e-123">Fonctionnalités de globalisation</span><span class="sxs-lookup"><span data-stu-id="1387e-123">Globalization features</span></span>

<span data-ttu-id="1387e-124">Pour utiliser une fonctionnalité de globalisation, vous devez d'abord l'importer à partir du référentiel global et en créer votre propre version.</span><span class="sxs-lookup"><span data-stu-id="1387e-124">To use a Globalization feature, you must first import it from the the Global repository and create your own version of it.</span></span> <span data-ttu-id="1387e-125">Il existe deux façons d'ajouter des fonctionnalités de globalisation :</span><span class="sxs-lookup"><span data-stu-id="1387e-125">There are two ways to add Globalization features:</span></span>

- <span data-ttu-id="1387e-126">Ajouter une fonctionnalité dérivée basée sur une fonctionnalité existante qui a été publiée ou partagée.</span><span class="sxs-lookup"><span data-stu-id="1387e-126">Add a derived feature that is based on an existing feature that has been published or shared.</span></span>
- <span data-ttu-id="1387e-127">Ajouter une nouvelle fonctionnalité que vous avez créée à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="1387e-127">Add a new feature that you've created from scratch.</span></span>

## <a name="access-globalization-features"></a><span data-ttu-id="1387e-128">Accéder aux fonctionnalités de globalisation</span><span class="sxs-lookup"><span data-stu-id="1387e-128">Access Globalization features</span></span>

1. <span data-ttu-id="1387e-129">Assurez-vous que la fonctionnalité **Fonctionnalités de globalisation** est activée dans la gestion des fonctionnalités, comme décrit précédemment dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="1387e-129">Make sure that the **Globalization features** feature is turned on in Feature management, as described earlier in this topic.</span></span>
2. <span data-ttu-id="1387e-130">Ouvrez le nouvel espace de travail **Fonctionnalités de globalisation**, puis, sous **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="1387e-130">Open the new **Globalization Features** workspace, and then, under **Features**, select the **e-Invoicing** tile.</span></span>

    ![Espace de travail Fonctionnalités globales](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    <span data-ttu-id="1387e-132">La page **Fonctionnalités de facturation électronique** est ouverte.</span><span class="sxs-lookup"><span data-stu-id="1387e-132">The **e-Invoicing Features** page is opened.</span></span>

    ![Page Fonctionnalités de facturation électronique](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a><span data-ttu-id="1387e-134">Ajouter une fonctionnalité de globalisation dérivée</span><span class="sxs-lookup"><span data-stu-id="1387e-134">Add a derived Globalization feature</span></span>

<span data-ttu-id="1387e-135">Vous pouvez ajouter une nouvelle fonctionnalité de globalisation en la dérivant d'une fonctionnalité existante qui a été publiée ou partagée.</span><span class="sxs-lookup"><span data-stu-id="1387e-135">You can add a new Globalization feature by deriving it from an existing feature that has been published or shared.</span></span>

1. <span data-ttu-id="1387e-136">Sélectionnez **Importation** pour ouvrir la page **Importer une fonctionnalité depuis le référentiel global**.</span><span class="sxs-lookup"><span data-stu-id="1387e-136">Select **Import** to open the **Import feature from Global repository** page.</span></span>

    ![Importer une fonctionnalité depuis le référentiel global](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. <span data-ttu-id="1387e-138">Sélectionnez **Synchroniser** pour obtenir les fonctionnalités les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="1387e-138">Select **Synchronize** to get the latest features.</span></span>

    <span data-ttu-id="1387e-139">La liste synchronisée comprend les fonctionnalités qui vous sont disponibles, soit parce qu'elles ont été publiées par Microsoft, soit parce qu'elles ont été partagées avec vous par un autre fournisseur de configuration.</span><span class="sxs-lookup"><span data-stu-id="1387e-139">The synced list includes features that are available to you either because they were published by Microsoft or because they were shared with you by another configuration provider.</span></span>

    ![Liste synchronisée des fonctionnalités](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. <span data-ttu-id="1387e-141">Dans la liste, sélectionnez les fonctionnalités à importer, puis sélectionnez **Importation**.</span><span class="sxs-lookup"><span data-stu-id="1387e-141">In the list, select the features to import, and then select **Import**.</span></span> <span data-ttu-id="1387e-142">Vous recevez un message lorsque les fonctionnalités sélectionnées ont été importées avec succès.</span><span class="sxs-lookup"><span data-stu-id="1387e-142">You receive a message when the selected features have been successfully imported.</span></span>

    ![Message d'importation réussie](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. <span data-ttu-id="1387e-144">Sélectionnez **Ajouter** puis, dans la boîte de dialogue déroulante, sélectionnez l'option **Basé sur une version existante**.</span><span class="sxs-lookup"><span data-stu-id="1387e-144">Select **Add**, and then, in the drop-down dialog box, select the **Based on existing version** option.</span></span>
5. <span data-ttu-id="1387e-145">Entrez un nom et une description de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-145">Enter a name and description for the feature.</span></span>
6. <span data-ttu-id="1387e-146">Dans la liste des fonctionnalités disponibles, sélectionnez la version de base de la fonctionnalité, puis sélectionnez **Créer la fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="1387e-146">In the list of available features, select the base version of the feature, and then select **Create feature**.</span></span>

    ![Ajout d'une fonctionnalité dérivée](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    <span data-ttu-id="1387e-148">La fonctionnalité que vous avez ajoutée est créée et a le statut **Brouillon**.</span><span class="sxs-lookup"><span data-stu-id="1387e-148">The feature that you added is created and has a status of **Draft**.</span></span>

    ![Fonctionnalité dérivée ayant le statut Brouillon](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. <span data-ttu-id="1387e-150">Passez en revue les composants de la fonctionnalité pour déterminer si des mises à jour sont requises :</span><span class="sxs-lookup"><span data-stu-id="1387e-150">Review the feature components to determine whether updates are required:</span></span>

    - <span data-ttu-id="1387e-151">Passez en revue les configurations, au cas où vous auriez besoin de personnaliser les formats de gestion des états électroniques (ER) et leur liaison avec les mappages de format pour la version de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-151">Review the configurations, in case you need to customize the Electronic reporting (ER) formats and their binding with format mappings for the feature version.</span></span>
    - <span data-ttu-id="1387e-152">Passez en revue la configuration, au cas où vous auriez besoin de personnaliser l'onglet **Actions**, l'onglet **Règles d'applicabilité** ou l'onglet **Variables** pour la version de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-152">Review the setup, in case you need to customize the **Actions** tab, **Applicability rules** tab, or **Variables** tab for the feature version.</span></span>

8. <span data-ttu-id="1387e-153">Dans l'onglet **Versions**, sélectionnez une **Date d'effet** et entrez une description si le champ **Description** est vide.</span><span class="sxs-lookup"><span data-stu-id="1387e-153">On the **Versions** tab, select an **Effective from** date, and enter a description if the **Description** field is blank.</span></span>
9. <span data-ttu-id="1387e-154">Sélectionnez **Modifier le statut** pour terminer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-154">Select **Change status** to complete the feature.</span></span> <span data-ttu-id="1387e-155">Les fonctionnalités terminées peuvent être mises à disposition pour un environnement spécifique afin de pouvoir être utilisées dans les services de globalisation ou être publiées dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="1387e-155">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="1387e-156">Les fonctionnalités dont la valeur **Statut de version de la fonctionnalité** est **Publié** peuvent être partagées avec des organisations externes.</span><span class="sxs-lookup"><span data-stu-id="1387e-156">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="add-a-new-globalization-feature"></a><span data-ttu-id="1387e-157">Ajouter une nouvelle fonctionnalité de globalisation</span><span class="sxs-lookup"><span data-stu-id="1387e-157">Add a new Globalization feature</span></span>

<span data-ttu-id="1387e-158">Vous pouvez ajouter une nouvelle fonctionnalité de globalisation en la créant à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="1387e-158">You can add a new Globalization feature by creating it from scratch.</span></span>

1. <span data-ttu-id="1387e-159">Dans la page **Importer une fonctionnalité depuis le référentiel global**, sélectionnez **Ajouter** puis, dans la boîte de dialogue déroulante, sélectionnez l'option **Nouvelle fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="1387e-159">On the **Import feature from Global repository** page, select **Add**, and then, in the drop-down dialog box, select the **New feature** option.</span></span>
2. <span data-ttu-id="1387e-160">Entrez un nom et une description de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-160">Enter a name and description for the feature.</span></span>
3. <span data-ttu-id="1387e-161">Sélectionnez **Créer une fonctionnalité**.</span><span class="sxs-lookup"><span data-stu-id="1387e-161">Select **Create feature**.</span></span>

    ![Ajout d'une nouvelle fonctionnalité](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. <span data-ttu-id="1387e-163">Dans l'onglet **Versions**, sélectionnez une **Date d'effet**, puis sélectionnez **Modifier le statut** pour terminer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-163">On the **Versions** tab, select an **Effective from** date, and then select **Change status** to complete the feature.</span></span> <span data-ttu-id="1387e-164">Les fonctionnalités terminées peuvent être mises à disposition pour un environnement spécifique afin de pouvoir être utilisées dans les services de globalisation ou être publiées dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="1387e-164">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="1387e-165">Les fonctionnalités dont la valeur **Statut de version de la fonctionnalité** est **Publié** peuvent être partagées avec des organisations externes.</span><span class="sxs-lookup"><span data-stu-id="1387e-165">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="feature-component-overview"></a><span data-ttu-id="1387e-166">Vue d'ensemble des composants de la fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="1387e-166">Feature component overview</span></span>

<span data-ttu-id="1387e-167">Les fonctionnalités de globalisation comportent plusieurs composants :</span><span class="sxs-lookup"><span data-stu-id="1387e-167">Globalization features have several components:</span></span>

- <span data-ttu-id="1387e-168">**Version** – Ce composant prend en charge la gestion du cycle de vie des fonctionnalités et permet aux utilisateurs de gérer le statut des différentes versions de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-168">**Version** – This component supports feature lifecycle management and lets users manage the status for different versions of the feature.</span></span>
- <span data-ttu-id="1387e-169">**Configurations** – Ce composant permet aux utilisateurs de gérer, d'afficher et de modifier les formats de gestion des états électroniques et les mappages de formats associés.</span><span class="sxs-lookup"><span data-stu-id="1387e-169">**Configurations** – This component lets users manage, view, and edit related ER formats and format mappings.</span></span>
- <span data-ttu-id="1387e-170">**Paramétrages** – Ce composant permet aux utilisateurs des services de globalisation, tels qu'un service de facturation électronique, de gérer les paramètres de la version de fonctionnalité associée.</span><span class="sxs-lookup"><span data-stu-id="1387e-170">**Setups** – This component lets users of Globalization services, such as an e-invoicing service, manage the setup of the related feature version.</span></span> <span data-ttu-id="1387e-171">Par conséquent, il permet une construction flexible des règles de communication et de réaction.</span><span class="sxs-lookup"><span data-stu-id="1387e-171">Therefore, it supports the flexible construction of communication and responses rules.</span></span>
- <span data-ttu-id="1387e-172">**Environnement** – Ce composant permet aux utilisateurs des services de globalisation, tels qu'un service de facturation électronique, de gérer l'environnement dans lequel le paramétrage de la version de la fonctionnalité est utilisé et d'accorder une autorisation aux utilisateurs qui y auront accès.</span><span class="sxs-lookup"><span data-stu-id="1387e-172">**Environment** – This component lets users of Globalization services, such as an e-invoicing service, manage the environment where the feature version setup is used and grant authorization to the users who will have access to it.</span></span>
- <span data-ttu-id="1387e-173">**Organisations** – Ce composant permet aux utilisateurs de partager la fonctionnalité avec des organisations externes.</span><span class="sxs-lookup"><span data-stu-id="1387e-173">**Organizations** – This component lets users to share the feature with external organizations.</span></span>

## <a name="configuring-feature-components"></a><span data-ttu-id="1387e-174">Configuration des composants de la fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="1387e-174">Configuring feature components</span></span>

### <a name="version-and-status"></a><span data-ttu-id="1387e-175">Version et statut</span><span class="sxs-lookup"><span data-stu-id="1387e-175">Version and status</span></span>

<span data-ttu-id="1387e-176">La version est utilisée pour gérer le cycle de vie de la fonctionnalité de globalisation.</span><span class="sxs-lookup"><span data-stu-id="1387e-176">The version is used to manage the Globalization feature lifecycle.</span></span>

<span data-ttu-id="1387e-177">Le statut peut être modifié dans le champ **Statut** de l'onglet **Version**. Les statuts suivants sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="1387e-177">The status can be changed in the **Status** field on the **Version** tab. The following statuses are available:</span></span>

- <span data-ttu-id="1387e-178">**Brouillon** – La fonctionnalité ne peut être modifiée que lorsqu'elle est dans cet état.</span><span class="sxs-lookup"><span data-stu-id="1387e-178">**Draft** – The feature can be edited only when it's in this status.</span></span>
- <span data-ttu-id="1387e-179">**Terminée** – La fonctionnalité et tous les composants associés ont été finalisés (terminés) et ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="1387e-179">**Complete** – The feature and all related components have been finalized (completed) and can't be edited.</span></span>
- <span data-ttu-id="1387e-180">**Publiée** – La fonctionnalité et tous les composants associés ont été publiés dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="1387e-180">**Published** – The feature and all related components have been published to the Global repository.</span></span>
- <span data-ttu-id="1387e-181">**Partagée** – La fonctionnalité et tous les composants associés ont été partagés avec des organisations externes.</span><span class="sxs-lookup"><span data-stu-id="1387e-181">**Shared** – The feature and all related components have been shared with external organizations.</span></span>
- <span data-ttu-id="1387e-182">**Activée** – La fonctionnalité et tous les composants associés ont été activés pour être utilisés dans un service de globalisation, tel qu'un service de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="1387e-182">**Enabled** – The feature and all related components have been enabled for use in a Globalization service, such as an e-invoicing service.</span></span>

> [!NOTE]
> <span data-ttu-id="1387e-183">Les fonctionnalités doivent passer séquentiellement par certains de ces statuts.</span><span class="sxs-lookup"><span data-stu-id="1387e-183">Features must move sequentially through some of these statuses.</span></span> <span data-ttu-id="1387e-184">Par conséquent, tous les statuts peuvent ne pas être disponibles à chaque étape du cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="1387e-184">Therefore, not every status might be available at every lifecycle stage.</span></span>

### <a name="configurations"></a><span data-ttu-id="1387e-185">Configurations</span><span class="sxs-lookup"><span data-stu-id="1387e-185">Configurations</span></span>

<span data-ttu-id="1387e-186">Les actions suivantes sont disponibles pour les configurations :</span><span class="sxs-lookup"><span data-stu-id="1387e-186">The following actions are available for configurations:</span></span>

- <span data-ttu-id="1387e-187">**Afficher** – Permet d'afficher les configurations de fonctionnalités sous-jacentes qui ne nécessitent aucune mise à jour.</span><span class="sxs-lookup"><span data-stu-id="1387e-187">**View** – View the underlying feature configurations that don't require any update.</span></span>
- <span data-ttu-id="1387e-188">**Modifier** – Permet de créer une version provisoire d'une configuration sélectionnée afin de pouvoir modifier le format ou le mappage de format dans le Concepteur de format.</span><span class="sxs-lookup"><span data-stu-id="1387e-188">**Edit** – Create a draft version of a selected configuration so that you can edit the format or format mapping in the Format designer.</span></span>
- <span data-ttu-id="1387e-189">**Supprimer** – Permet de supprimer une configuration sélectionnée de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-189">**Delete** – Delete a selected configuration from the feature.</span></span>
- <span data-ttu-id="1387e-190">**Redéfinir** – Permet de redéfinir la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-190">**Rebase** – Rebase the feature.</span></span> <span data-ttu-id="1387e-191">Pour plus d'informations, voir la section [Redéfinir les fonctionnalités de globalisation dérivées](#rebase) située plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="1387e-191">For more information, see the [Rebase derived Globalization features](#rebase) section later in this topic.</span></span>

### <a name="setups"></a><span data-ttu-id="1387e-192">Paramétrages</span><span class="sxs-lookup"><span data-stu-id="1387e-192">Setups</span></span>

<span data-ttu-id="1387e-193">Les actions suivantes sont disponibles pour les paramétrages de fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="1387e-193">The following actions are available for feature setups:</span></span>

- <span data-ttu-id="1387e-194">**Ajouter** – Permet de créer une nouvelle configuration de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-194">**Add** – Create a new feature setup.</span></span> <span data-ttu-id="1387e-195">Ce paramétrage de fonctionnalité peut être dérivé d'un paramétrage de fonctionnalité existant ou être créé à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="1387e-195">This feature setup can be derived from an existing feature setup or created from scratch.</span></span>
- <span data-ttu-id="1387e-196">**Supprimer** – Permet de supprimer un paramétrage de fonctionnalité sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1387e-196">**Delete** – Delete a selected feature setup.</span></span>
- <span data-ttu-id="1387e-197">**Afficher** – Permet d'afficher un paramétrage de fonctionnalité sous-jacent qui ne nécessite aucune modification.</span><span class="sxs-lookup"><span data-stu-id="1387e-197">**View** – View an underlying feature setup that doesn't require any changes.</span></span>
- <span data-ttu-id="1387e-198">**Modifier** – Permet de créer, supprimer ou modifier les attributs des trois principaux composants d'un paramétrage de fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="1387e-198">**Edit** – Create, delete, or modify the attributes of the three main components of a feature setup:</span></span>

    - <span data-ttu-id="1387e-199">Actions et leurs paramètres</span><span class="sxs-lookup"><span data-stu-id="1387e-199">Actions and their parameters</span></span>
    - <span data-ttu-id="1387e-200">Règles d'applicabilité</span><span class="sxs-lookup"><span data-stu-id="1387e-200">Applicability rules</span></span>
    - <span data-ttu-id="1387e-201">Variables</span><span class="sxs-lookup"><span data-stu-id="1387e-201">Variables</span></span>

![Page de paramétrage d'une version de fonctionnalité](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a><span data-ttu-id="1387e-203">Environnements</span><span class="sxs-lookup"><span data-stu-id="1387e-203">Environments</span></span>

<span data-ttu-id="1387e-204">Les actions suivantes sont disponibles pour les environnements :</span><span class="sxs-lookup"><span data-stu-id="1387e-204">The following actions are available for environments:</span></span>

- <span data-ttu-id="1387e-205">**Activer** – Pour une version de fonctionnalité sélectionnée, sélectionnez un environnement publié et sélectionnez une **Date d'effet** à compter de laquelle elle devrait être disponible.</span><span class="sxs-lookup"><span data-stu-id="1387e-205">**Enable** – For a selected feature version, select a published environment, and select an **Effective from** date when it should be available.</span></span> <span data-ttu-id="1387e-206">Pour plus d'informations, voir la section [Configurer des environnements pour l'activation](#configureenvironment) située plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="1387e-206">For more information, see the [Configure environments for enablement](#configureenvironment) section later in this topic.</span></span>
- <span data-ttu-id="1387e-207">**Annuler** – Permet de supprimer un environnement pour un paramétrage de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-207">**Cancel** – Remove an environment for a feature setup.</span></span>

### <a name="organizations"></a><span data-ttu-id="1387e-208">Organisations</span><span class="sxs-lookup"><span data-stu-id="1387e-208">Organizations</span></span>

<span data-ttu-id="1387e-209">Suivez ces étapes pour partager une fonctionnalité de globalisation avec une organisation externe.</span><span class="sxs-lookup"><span data-stu-id="1387e-209">Follow these steps to share a Globalization feature with an external organization.</span></span>

1. <span data-ttu-id="1387e-210">Dans la page **Fonctionnalités de facturation électronique**, sélectionnez la fonctionnalité et la version de la fonctionnalité à partager.</span><span class="sxs-lookup"><span data-stu-id="1387e-210">On the **e-Invoicing features** page, select the feature and the feature version to share.</span></span>
2. <span data-ttu-id="1387e-211">Dans l'onglet **Organisations**, sélectionnez **Partager avec** puis, dans la boîte de dialogue déroulante, entrez le nom de domaine de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="1387e-211">On the **Organizations** tab, select **Share with**, and then, in the drop-down dialog box, enter the organization's domain name.</span></span>
3. <span data-ttu-id="1387e-212">Sélectionnez **Partager**.</span><span class="sxs-lookup"><span data-stu-id="1387e-212">Select **Share**.</span></span>

    ![Partage d'une fonctionnalité avec une organisation](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

<span data-ttu-id="1387e-214">La fonctionnalité est partagée avec l'organisation sélectionnée et lui est disponible dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="1387e-214">The feature is shared with the selected organization and is available for that organization in the Global repository.</span></span> <span data-ttu-id="1387e-215">De là, la fonctionnalité peut être importée dans l'instance RCS de l'organisation ou dans Dynamics 365 Finance afin de pouvoir être utilisée.</span><span class="sxs-lookup"><span data-stu-id="1387e-215">From there, the feature can be imported into the organization's instance of RCS or Dynamics 365 Finance so that it can be used.</span></span>

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a><span data-ttu-id="1387e-216">Redéfinir les fonctionnalités de globalisation dérivées</span><span class="sxs-lookup"><span data-stu-id="1387e-216">Rebase derived Globalization features</span></span>

<span data-ttu-id="1387e-217">Vous pouvez redéfinir une fonction de globalisation dérivée vers une nouvelle version ou la version de base mise à jour de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1387e-217">You can rebase a derived Globalization feature to the new or updated base feature version.</span></span> <span data-ttu-id="1387e-218">De cette façon, les modifications survenues dans la version de base peuvent être automatiquement mises à jour.</span><span class="sxs-lookup"><span data-stu-id="1387e-218">In this way, changes that have occurred in the base version can be automatically updated.</span></span> <span data-ttu-id="1387e-219">La version de base mise à jour de la fonctionnalité est créée par le fournisseur de configuration d'origine, puis est publiée ou partagée.</span><span class="sxs-lookup"><span data-stu-id="1387e-219">The updated base feature version is created by the originating configuration provider, and it's then published or shared.</span></span>

![Version de base mise à jour de la fonctionnalité](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

<span data-ttu-id="1387e-221">Par exemple, si vous souhaitez redéfinir la version dérivée d'une fonctionnalité que vous avez créée, vous devez d'abord obtenir la dernière version de la fonctionnalité en l'important à partir du référentiel global.</span><span class="sxs-lookup"><span data-stu-id="1387e-221">For example, if you want to rebase the derived version of a feature that you created, you first get the latest version of the feature by importing it from the Global repository.</span></span>

1. <span data-ttu-id="1387e-222">Dans la page **Fonctionnalités de facturation électronique**, sélectionnez **Importation**.</span><span class="sxs-lookup"><span data-stu-id="1387e-222">On the **e-Invoicing features** page, select **Import**.</span></span>
2. <span data-ttu-id="1387e-223">Sélectionnez **Synchroniser** pour obtenir les fonctionnalités les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="1387e-223">Select **Synchronize** to get the latest features.</span></span>
3. <span data-ttu-id="1387e-224">Dans la liste des fonctionnalités, sélectionnez les fonctionnalités à importer, puis sélectionnez **Importation**.</span><span class="sxs-lookup"><span data-stu-id="1387e-224">In the list of features, select the features to import, and then select **Import**.</span></span>

    ![Importation de la dernière version d'une fonctionnalité](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. <span data-ttu-id="1387e-226">Dans la liste des fonctionnalités, sélectionnez la fonctionnalité à redéfinir.</span><span class="sxs-lookup"><span data-stu-id="1387e-226">In the list of features, select the feature to rebase.</span></span>
5. <span data-ttu-id="1387e-227">Dans l'onglet **Version**, sélectionnez **Nouveau** pour créer une version de brouillon.</span><span class="sxs-lookup"><span data-stu-id="1387e-227">On the **Version** tab, select **New** to create a draft version.</span></span>

    ![Nouvelle version de brouillon créée](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. <span data-ttu-id="1387e-229">Sélectionnez **Redéfinir**.</span><span class="sxs-lookup"><span data-stu-id="1387e-229">Select **Rebase**.</span></span>
7. <span data-ttu-id="1387e-230">Dans la boîte de dialogue **Redéfinir**, sélectionnez la dernière version de la fonctionnalité à redéfinir.</span><span class="sxs-lookup"><span data-stu-id="1387e-230">In the **Rebase** dialog box, select the latest version of the feature to rebase to.</span></span>

    ![Boîte de dialogue Redéfinir](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. <span data-ttu-id="1387e-232">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1387e-232">Select **OK**.</span></span>
9. <span data-ttu-id="1387e-233">Passez en revue les composants de la fonctionnalité et apportez les modifications nécessaires.</span><span class="sxs-lookup"><span data-stu-id="1387e-233">Review the feature components, and make any changes that are required.</span></span>
10. <span data-ttu-id="1387e-234">Sélectionnez **Modifier le statut** pour terminer la fonctionnalité redéfinie.</span><span class="sxs-lookup"><span data-stu-id="1387e-234">Select **Change status** to complete the rebased feature.</span></span> <span data-ttu-id="1387e-235">Une fois la redéfinition terminée, vous pouvez effectuer des actions supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="1387e-235">When the rebase is completed, you can perform additional actions.</span></span> <span data-ttu-id="1387e-236">Par exemple, vous pouvez publier la fonctionnalité et la rendre disponible pour être utilisée dans les services de globalisation.</span><span class="sxs-lookup"><span data-stu-id="1387e-236">For example, you can publish the feature and make it available for use in Globalization services.</span></span>

    ![Statut de la fonctionnalité mis à jour sur Terminé](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a><span data-ttu-id="1387e-238">Configurer les environnements pour les fonctionnalités de globalisation</span><span class="sxs-lookup"><span data-stu-id="1387e-238">Configure environments for Globalization features</span></span>

<span data-ttu-id="1387e-239">Les utilisateurs des services de globalisation peuvent gérer l'environnement pour paramétrer une fonctionnalité de globalisation et accorder une autorisation aux autres utilisateurs qui y auront accès.</span><span class="sxs-lookup"><span data-stu-id="1387e-239">Users of Globalization services can manage the environment to set up a Globalization feature and grant authorization to other users who will have access to it.</span></span>

1. <span data-ttu-id="1387e-240">Dans l'espace de travail **Fonctionnalités de globalisation**, sous **Environnements**, sélectionnez la vignette **Facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="1387e-240">In the **Globalization Features** workspace, under **Environments**, select the **e-Invoicing** tile.</span></span>

    ![Espace de travail Fonctionnalités de globalisation](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. <span data-ttu-id="1387e-242">Sélectionnez **Paramètres du coffre de clés**, puis sélectionnez **Nouveau** pour créer un secret Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="1387e-242">Select **Key Vault parameters**, and then select **New** to create an Azure Key Vault secret.</span></span>
3. <span data-ttu-id="1387e-243">Entrez un nom et une description pour le coffre de clés puis, dans le champ **URI Key Vault**, entrez l'URL qui identifie la ressource Key Vault dans Azure.</span><span class="sxs-lookup"><span data-stu-id="1387e-243">Enter a name and description for the key vault, and then, in the **Key Vault URI** field, enter the URL that identifies the Key Vault resource in Azure.</span></span>
4. <span data-ttu-id="1387e-244">Dans le raccourci **Certificats**, sélectionnez **Ajouter** pour ajouter le certificat et entrez un nom et une description pour chaque certificat.</span><span class="sxs-lookup"><span data-stu-id="1387e-244">On the **Certificates** FastTab, select **Add** to add the certificate, and enter a name and description for each certificate.</span></span>

    ![Certificat ajouté](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. <span data-ttu-id="1387e-246">Sélectionnez **Nouveau** pour créer un environnement.</span><span class="sxs-lookup"><span data-stu-id="1387e-246">Select **New** to create a new environment.</span></span>
6. <span data-ttu-id="1387e-247">Entrez un nom, une description et le secret du jeton de signature de l'accès partagé requis pour le stockage.</span><span class="sxs-lookup"><span data-stu-id="1387e-247">Enter a name, a description, and the shared access signature token secret required for the storage.</span></span>
7. <span data-ttu-id="1387e-248">dans le raccourci **Utilisateurs**, sélectionnez **Nouveau** pour ajouter un utilisateur qui sera autorisé à accéder à cet environnement.</span><span class="sxs-lookup"><span data-stu-id="1387e-248">On the **Users** FastTab, select **New** to add a user who will have permission to access this environment.</span></span>
8. <span data-ttu-id="1387e-249">Saisissez l'ID utilisateur et l'adresse e-mail de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1387e-249">Enter the user's user ID and email address.</span></span>
9. <span data-ttu-id="1387e-250">Répétez les étapes 7 et 8 pour ajouter d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1387e-250">Repeat steps 7 and 8 to add more users.</span></span>
10. <span data-ttu-id="1387e-251">Sélectionnez **Publier** pour publier l'environnement.</span><span class="sxs-lookup"><span data-stu-id="1387e-251">Select **Publish** to publish the environment.</span></span>

    ![Environnement publié](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)
