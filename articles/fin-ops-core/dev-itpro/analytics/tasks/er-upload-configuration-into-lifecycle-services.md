---
title: Charger une configuration dans Lifecycle Services
description: Cette rubrique explique comment créer une configuration pour la gestion des états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41a8fcf2592bde4901aba703e0cd124b1155dac6
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270557"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="e5224-103">Charger une configuration dans Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="e5224-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e5224-104">Cette rubrique explique comment un utilisateur ayant le rôle d’administrateur système ou de développeur d’états électroniques peut créer une [configuration pour la génération d’états électroniques (ER)](../general-electronic-reporting.md#Configuration) et la charger dans la [bibliothèque d’actifs au niveau du projet](../../lifecycle-services/asset-library.md) dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e5224-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5224-105">L’utilisation de LCS comme référentiel de stockage pour les configurations ER est en cours [d’abandon](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="e5224-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="e5224-106">Pour plus d’informations, voir [Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span><span class="sxs-lookup"><span data-stu-id="e5224-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="e5224-107">Dans cet exemple, vous allez créer une configuration et la charger dans LCS pour un exemple de société nommé Litware, Inc. Ces étapes peuvent être effectuées dans n’importe quelle société, car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="e5224-107">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="e5224-108">Pour effectuer ces étapes, vous devez commencer par effectuer la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e5224-108">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="e5224-109">L’accès à LCS est également requis.</span><span class="sxs-lookup"><span data-stu-id="e5224-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="e5224-110">Se connecter à l’application en utilisant l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="e5224-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="e5224-111">Développeur de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="e5224-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="e5224-112">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="e5224-112">System administrator</span></span>

2. <span data-ttu-id="e5224-113">Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e5224-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="e5224-114">Sélectionnez **Litware, Inc.** et marquez-le comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="e5224-114">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="e5224-115">Sélectionnez **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="e5224-115">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="e5224-116">Assurez-vous que l’utilisateur Dynamics 365 Finance actuel est membre du projet LCS qui contient la [bibliothèque d’actifs](../../lifecycle-services/asset-library.md#asset-library-support) utilisée importer des configurations ER.</span><span class="sxs-lookup"><span data-stu-id="e5224-116">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="e5224-117">Vous ne pouvez pas accéder à un projet LCS à partir d’un référentiel ER qui représente un domaine différent du domaine utilisé dans Finance.</span><span class="sxs-lookup"><span data-stu-id="e5224-117">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="e5224-118">Si vous essayez, une liste vide de projets LCS s’affichera et vous ne pourrez pas importer de configurations ER à partir de la bibliothèque d’actifs au niveau du projet dans LCS.</span><span class="sxs-lookup"><span data-stu-id="e5224-118">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="e5224-119">Pour accéder aux bibliothèques d’actifs au niveau du projet à partir d’un référentiel ER utilisé pour importer des configurations ER, connectez-vous à Finance en utilisant les informations d’identification d’un utilisateur qui appartient au client (domaine) pour lequel l’instance Finance actuelle a été provisionnée.</span><span class="sxs-lookup"><span data-stu-id="e5224-119">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="e5224-120">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="e5224-120">Create a new data model configuration</span></span>

1. <span data-ttu-id="e5224-121">Accédez à **Administration d’organisation \> États électroniques \> Configurations**.</span><span class="sxs-lookup"><span data-stu-id="e5224-121">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="e5224-122">Sur la page **Configurations**, sélectionnez **Créer une configuration** pour ouvrir la boîte de dialogue déroulante.</span><span class="sxs-lookup"><span data-stu-id="e5224-122">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="e5224-123">Dans cet exemple, vous allez créer une configuration qui contient un modèle de données pour les documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="e5224-123">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="e5224-124">Cette configuration de modèle de données sera téléchargée dans LCS ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="e5224-124">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="e5224-125">Dans le champ **Nom**, saisissez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="e5224-125">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="e5224-126">Dans le champ **Description**, saisissez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="e5224-126">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="e5224-127">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="e5224-127">Select **Create configuration**.</span></span>
6. <span data-ttu-id="e5224-128">Sélectionnez **Concepteur de modèle**.</span><span class="sxs-lookup"><span data-stu-id="e5224-128">Select **Model designer**.</span></span>
7. <span data-ttu-id="e5224-129">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e5224-129">Select **New**.</span></span>
8. <span data-ttu-id="e5224-130">Dans le champ **Nom**, entrez **Point d’entrée**.</span><span class="sxs-lookup"><span data-stu-id="e5224-130">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="e5224-131">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e5224-131">Select **Add**.</span></span>
10. <span data-ttu-id="e5224-132">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e5224-132">Select **Save**.</span></span>
11. <span data-ttu-id="e5224-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e5224-133">Close the page.</span></span>
12. <span data-ttu-id="e5224-134">Sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="e5224-134">Select **Change status**.</span></span>
13. <span data-ttu-id="e5224-135">Sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e5224-135">Select **Complete**.</span></span>
14. <span data-ttu-id="e5224-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5224-136">Select **OK**.</span></span>
15. <span data-ttu-id="e5224-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e5224-137">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="e5224-138">Enregistrer un nouveau référentiel</span><span class="sxs-lookup"><span data-stu-id="e5224-138">Register a new repository</span></span>

1. <span data-ttu-id="e5224-139">Allez dans **Administration d’organisation \> Espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e5224-139">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="e5224-140">Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="e5224-140">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="e5224-141">Dans la vignette **Litware, Inc.**, sélectionnez **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="e5224-141">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="e5224-142">Vous pouvez à présent ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="e5224-142">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="e5224-143">Sélectionnez **Ajouter** pour ouvrir la boîte de dialogue déroulante.</span><span class="sxs-lookup"><span data-stu-id="e5224-143">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="e5224-144">Vous pouvez maintenant ajouter un nouveau référentiel.</span><span class="sxs-lookup"><span data-stu-id="e5224-144">You can now add a new repository.</span></span>

5. <span data-ttu-id="e5224-145">Dans le champ **Entrée du référentiel de configuration**, sélectionnez **LCS**.</span><span class="sxs-lookup"><span data-stu-id="e5224-145">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="e5224-146">Sélectionnez **Créer un référentiel**.</span><span class="sxs-lookup"><span data-stu-id="e5224-146">Select **Create repository**.</span></span>
7. <span data-ttu-id="e5224-147">Dans le champ **Projet**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e5224-147">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="e5224-148">Pour cette exemple, sélectionnez le projet LCS souhaité.</span><span class="sxs-lookup"><span data-stu-id="e5224-148">For this example, select the desired LCS project.</span></span> <span data-ttu-id="e5224-149">Vous devez avoir [accès](#accessconditions) au projet.</span><span class="sxs-lookup"><span data-stu-id="e5224-149">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="e5224-150">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5224-150">Select **OK**.</span></span>

    <span data-ttu-id="e5224-151">Effectuez une nouvelle entrée de référentiel.</span><span class="sxs-lookup"><span data-stu-id="e5224-151">Complete a new repository entry.</span></span>

9. <span data-ttu-id="e5224-152">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e5224-152">In the list, mark the selected row.</span></span>

    <span data-ttu-id="e5224-153">Pour cet exemple, sélectionnez l’enregistrement du référentiel **LCS**.</span><span class="sxs-lookup"><span data-stu-id="e5224-153">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="e5224-154">Notez qu’un référentiel enregistré est marqué par le fournisseur actuel.</span><span class="sxs-lookup"><span data-stu-id="e5224-154">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="e5224-155">En d’autres termes, seules les configurations appartenant à ce fournisseur peuvent être placées dans ce référentiel et donc chargées dans le projet LCS sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e5224-155">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="e5224-156">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="e5224-156">Select **Open**.</span></span>

    <span data-ttu-id="e5224-157">Vous ouvrez le référentiel pour afficher la liste des configurations d’ER.</span><span class="sxs-lookup"><span data-stu-id="e5224-157">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="e5224-158">Si le projet sélectionné n’a pas encore été utilisé pour le partage de configurations d’ER, la liste sera vide.</span><span class="sxs-lookup"><span data-stu-id="e5224-158">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="e5224-159">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e5224-159">Close the page.</span></span>
12. <span data-ttu-id="e5224-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e5224-160">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="e5224-161">Charger une configuration dans LCS</span><span class="sxs-lookup"><span data-stu-id="e5224-161">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="e5224-162">Accédez à **Administration d’organisation \> États électroniques \> Configurations**.</span><span class="sxs-lookup"><span data-stu-id="e5224-162">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="e5224-163">Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="e5224-163">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="e5224-164">Vous devez sélectionner une configuration qui est déjà terminée.</span><span class="sxs-lookup"><span data-stu-id="e5224-164">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="e5224-165">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e5224-165">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="e5224-166">Pour cet exemple, sélectionnez la version de la configuration sélectionnée dont le statut est **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="e5224-166">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="e5224-167">Sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="e5224-167">Select **Change status**.</span></span>
5. <span data-ttu-id="e5224-168">Sélectionnez **Partager**.</span><span class="sxs-lookup"><span data-stu-id="e5224-168">Select **Share**.</span></span>

    <span data-ttu-id="e5224-169">L’état de la configuration est modifié de **Terminé** à **Partagé** lorsque la configuration est publiée dans LCS.</span><span class="sxs-lookup"><span data-stu-id="e5224-169">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="e5224-170">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5224-170">Select **OK**.</span></span>
7. <span data-ttu-id="e5224-171">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e5224-171">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="e5224-172">Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Partagé**.</span><span class="sxs-lookup"><span data-stu-id="e5224-172">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="e5224-173">Notez que le statut de la version sélectionnée est passé de **Terminé** à **Partagé**.</span><span class="sxs-lookup"><span data-stu-id="e5224-173">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="e5224-174">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e5224-174">Close the page.</span></span>
9. <span data-ttu-id="e5224-175">Sélectionnez **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="e5224-175">Select **Repositories**.</span></span>

    <span data-ttu-id="e5224-176">Vous pouvez à présent ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="e5224-176">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="e5224-177">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="e5224-177">Select **Open**.</span></span>

    <span data-ttu-id="e5224-178">Pour cet exemple, sélectionnez le référentiel **LCS** et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="e5224-178">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="e5224-179">Notez que la configuration sélectionnée est indiquée comme un actif du projet LCS sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e5224-179">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="e5224-180">Ouvrez LCS en accédant à <https://lcs.dynamics.com>.</span><span class="sxs-lookup"><span data-stu-id="e5224-180">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="e5224-181">Ouvrez un projet qui a été utilisé précédemment pour l’enregistrement du référentiel.</span><span class="sxs-lookup"><span data-stu-id="e5224-181">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="e5224-182">Ouvrez la bibliothèque d’actifs du projet.</span><span class="sxs-lookup"><span data-stu-id="e5224-182">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="e5224-183">Sélectionnez le type d’actif **Configuration GER**.</span><span class="sxs-lookup"><span data-stu-id="e5224-183">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="e5224-184">La configuration ER que vous avez chargée doit être répertoriée.</span><span class="sxs-lookup"><span data-stu-id="e5224-184">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="e5224-185">Notez que la configuration LCS chargée peut être importée dans une autre instance si les fournisseurs ont accès à ce projet LCS.</span><span class="sxs-lookup"><span data-stu-id="e5224-185">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
