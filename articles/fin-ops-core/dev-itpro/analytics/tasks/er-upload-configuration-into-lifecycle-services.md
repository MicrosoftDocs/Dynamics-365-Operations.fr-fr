---
title: Charger une configuration dans Lifecycle Services
description: Cette rubrique explique comment créer une configuration pour la gestion des états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
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
ms.openlocfilehash: 6f17763236594092d04dfe2d2f9912e764b4f8d4
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562635"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="2c1f4-103">Charger une configuration dans Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="2c1f4-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2c1f4-104">Cette rubrique explique comment un utilisateur ayant le rôle d’administrateur système ou de développeur d’états électroniques peut créer une [configuration pour la génération d’états électroniques (ER)](../general-electronic-reporting.md#Configuration) et la charger dans la [bibliothèque d’actifs au niveau du projet](../../lifecycle-services/asset-library.md) dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="2c1f4-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="2c1f4-105">Dans cet exemple, vous allez créer une configuration et la charger dans LCS pour un exemple de société nommé Litware, Inc. Ces étapes peuvent être effectuées dans n’importe quelle société, car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-105">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="2c1f4-106">Pour effectuer ces étapes, vous devez commencer par effectuer la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="2c1f4-106">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="2c1f4-107">L’accès à LCS est également requis.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="2c1f4-108">Se connecter à l’application en utilisant l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="2c1f4-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="2c1f4-109">Développeur de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="2c1f4-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="2c1f4-110">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="2c1f4-110">System administrator</span></span>

2. <span data-ttu-id="2c1f4-111">Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="2c1f4-112">Sélectionnez **Litware, Inc.** et marquez-le comme **Actif**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-112">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="2c1f4-113">Sélectionnez **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-113">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="2c1f4-114">Assurez-vous que l’utilisateur Dynamics 365 Finance actuel est membre du projet LCS qui contient la [bibliothèque d’actifs](../../lifecycle-services/asset-library.md#asset-library-support) utilisée importer des configurations ER.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-114">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="2c1f4-115">Vous ne pouvez pas accéder à un projet LCS à partir d’un référentiel ER qui représente un domaine différent du domaine utilisé dans Finance.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-115">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="2c1f4-116">Si vous essayez, une liste vide de projets LCS s’affichera et vous ne pourrez pas importer de configurations ER à partir de la bibliothèque d’actifs au niveau du projet dans LCS.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-116">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="2c1f4-117">Pour accéder aux bibliothèques d’actifs au niveau du projet à partir d’un référentiel ER utilisé pour importer des configurations ER, connectez-vous à Finance en utilisant les informations d’identification d’un utilisateur qui appartient au client (domaine) pour lequel l’instance Finance actuelle a été provisionnée.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-117">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="2c1f4-118">Créer une configuration de modèle de données</span><span class="sxs-lookup"><span data-stu-id="2c1f4-118">Create a new data model configuration</span></span>

1. <span data-ttu-id="2c1f4-119">Accédez à **Administration d’organisation \> États électroniques \> Configurations**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-119">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="2c1f4-120">Sur la page **Configurations**, sélectionnez **Créer une configuration** pour ouvrir la boîte de dialogue déroulante.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-120">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="2c1f4-121">Dans cet exemple, vous allez créer une configuration qui contient un modèle de données pour les documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-121">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="2c1f4-122">Cette configuration de modèle de données sera téléchargée dans LCS ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-122">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="2c1f4-123">Dans le champ **Nom**, saisissez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-123">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="2c1f4-124">Dans le champ **Description**, saisissez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-124">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="2c1f4-125">Sélectionnez **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-125">Select **Create configuration**.</span></span>
6. <span data-ttu-id="2c1f4-126">Sélectionnez **Concepteur de modèle**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-126">Select **Model designer**.</span></span>
7. <span data-ttu-id="2c1f4-127">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-127">Select **New**.</span></span>
8. <span data-ttu-id="2c1f4-128">Dans le champ **Nom**, entrez **Point d’entrée**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-128">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="2c1f4-129">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-129">Select **Add**.</span></span>
10. <span data-ttu-id="2c1f4-130">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-130">Select **Save**.</span></span>
11. <span data-ttu-id="2c1f4-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-131">Close the page.</span></span>
12. <span data-ttu-id="2c1f4-132">Sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-132">Select **Change status**.</span></span>
13. <span data-ttu-id="2c1f4-133">Sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-133">Select **Complete**.</span></span>
14. <span data-ttu-id="2c1f4-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-134">Select **OK**.</span></span>
15. <span data-ttu-id="2c1f4-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-135">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="2c1f4-136">Enregistrer un nouveau référentiel</span><span class="sxs-lookup"><span data-stu-id="2c1f4-136">Register a new repository</span></span>

1. <span data-ttu-id="2c1f4-137">Allez dans **Administration d’organisation \> Espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-137">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="2c1f4-138">Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-138">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="2c1f4-139">Dans la vignette **Litware, Inc.**, sélectionnez **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-139">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="2c1f4-140">Vous pouvez à présent ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-140">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="2c1f4-141">Sélectionnez **Ajouter** pour ouvrir la boîte de dialogue déroulante.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-141">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="2c1f4-142">Vous pouvez maintenant ajouter un nouveau référentiel.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-142">You can now add a new repository.</span></span>

5. <span data-ttu-id="2c1f4-143">Dans le champ **Entrée du référentiel de configuration**, sélectionnez **LCS**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-143">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="2c1f4-144">Sélectionnez **Créer un référentiel**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-144">Select **Create repository**.</span></span>
7. <span data-ttu-id="2c1f4-145">Dans le champ **Projet**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-145">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="2c1f4-146">Pour cette exemple, sélectionnez le projet LCS souhaité.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-146">For this example, select the desired LCS project.</span></span> <span data-ttu-id="2c1f4-147">Vous devez avoir [accès](#accessconditions) au projet.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-147">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="2c1f4-148">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-148">Select **OK**.</span></span>

    <span data-ttu-id="2c1f4-149">Effectuez une nouvelle entrée de référentiel.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-149">Complete a new repository entry.</span></span>

9. <span data-ttu-id="2c1f4-150">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-150">In the list, mark the selected row.</span></span>

    <span data-ttu-id="2c1f4-151">Pour cet exemple, sélectionnez l’enregistrement du référentiel **LCS**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-151">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="2c1f4-152">Notez qu’un référentiel enregistré est marqué par le fournisseur actuel.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-152">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="2c1f4-153">En d’autres termes, seules les configurations appartenant à ce fournisseur peuvent être placées dans ce référentiel et donc chargées dans le projet LCS sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-153">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="2c1f4-154">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-154">Select **Open**.</span></span>

    <span data-ttu-id="2c1f4-155">Vous ouvrez le référentiel pour afficher la liste des configurations d’ER.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-155">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="2c1f4-156">Si le projet sélectionné n’a pas encore été utilisé pour le partage de configurations d’ER, la liste sera vide.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-156">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="2c1f4-157">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-157">Close the page.</span></span>
12. <span data-ttu-id="2c1f4-158">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-158">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="2c1f4-159">Charger une configuration dans LCS</span><span class="sxs-lookup"><span data-stu-id="2c1f4-159">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="2c1f4-160">Accédez à **Administration d’organisation \> États électroniques \> Configurations**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-160">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="2c1f4-161">Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-161">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="2c1f4-162">Vous devez sélectionner une configuration qui est déjà terminée.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-162">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="2c1f4-163">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-163">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="2c1f4-164">Pour cet exemple, sélectionnez la version de la configuration sélectionnée dont le statut est **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-164">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="2c1f4-165">Sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-165">Select **Change status**.</span></span>
5. <span data-ttu-id="2c1f4-166">Sélectionnez **Partager**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-166">Select **Share**.</span></span>

    <span data-ttu-id="2c1f4-167">L’état de la configuration est modifié de **Terminé** à **Partagé** lorsque la configuration est publiée dans LCS.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-167">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="2c1f4-168">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-168">Select **OK**.</span></span>
7. <span data-ttu-id="2c1f4-169">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-169">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="2c1f4-170">Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Partagé**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-170">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="2c1f4-171">Notez que le statut de la version sélectionnée est passé de **Terminé** à **Partagé**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-171">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="2c1f4-172">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-172">Close the page.</span></span>
9. <span data-ttu-id="2c1f4-173">Sélectionnez **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-173">Select **Repositories**.</span></span>

    <span data-ttu-id="2c1f4-174">Vous pouvez à présent ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-174">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="2c1f4-175">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-175">Select **Open**.</span></span>

    <span data-ttu-id="2c1f4-176">Pour cet exemple, sélectionnez le référentiel **LCS** et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-176">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="2c1f4-177">Notez que la configuration sélectionnée est indiquée comme un actif du projet LCS sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-177">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="2c1f4-178">Ouvrez LCS en accédant à <https://lcs.dynamics.com>.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-178">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="2c1f4-179">Ouvrez un projet qui a été utilisé précédemment pour l’enregistrement du référentiel.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-179">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="2c1f4-180">Ouvrez la bibliothèque d’actifs du projet.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-180">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="2c1f4-181">Sélectionnez le type d’actif **Configuration GER**.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-181">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="2c1f4-182">La configuration ER que vous avez chargée doit être répertoriée.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-182">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="2c1f4-183">Notez que la configuration LCS chargée peut être importée dans une autre instance si les fournisseurs ont accès à ce projet LCS.</span><span class="sxs-lookup"><span data-stu-id="2c1f4-183">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]