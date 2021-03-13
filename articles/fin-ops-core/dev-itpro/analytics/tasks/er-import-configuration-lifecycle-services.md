---
title: Importer une configuration à partir de Lifecycle Services
description: Cette rubrique décrit comment importer une nouvelle version d’une configuration pour la gestion des états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 602886b0dd729b8ec52940f42bd1c393dac8acda
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093693"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="c812f-103">Importer une configuration à partir de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="c812f-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c812f-104">Cette rubrique explique comment un utilisateur ayant le rôle d’administrateur système ou de développeur d’états électroniques peut importer une nouvelle version d’une configuration pour la [génération d’états électroniques (ER)](../general-electronic-reporting.md#Configuration) à partir de la [bibliothèque d’actifs au niveau du projet](../../lifecycle-services/asset-library.md) dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c812f-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="c812f-105">Dans cet exemple, vous allez sélectionner la version souhaitée de la configuration ER et l’importer pour un exemple société nommée Litware, Inc. Ces étapes peuvent être réalisées dans n’importe quelle société, car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="c812f-105">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="c812f-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure [Charger une configuration dans Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="c812f-106">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="c812f-107">L’accès à LCS est également requis.</span><span class="sxs-lookup"><span data-stu-id="c812f-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="c812f-108">Se connecter à l’application en utilisant l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="c812f-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="c812f-109">Développeur de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="c812f-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="c812f-110">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="c812f-110">System administrator</span></span>

2. <span data-ttu-id="c812f-111">Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="c812f-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="c812f-112">Sélectionner **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="c812f-112">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="c812f-113">Assurez-vous que l’utilisateur Dynamics 365 Finance actuel est membre du projet LCS qui contient la bibliothèque d’actifs à laquelle l’utilisateur souhaite [accéder](../../lifecycle-services/asset-library.md#asset-library-support) pour importer des configurations ER.</span><span class="sxs-lookup"><span data-stu-id="c812f-113">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="c812f-114">Vous ne pouvez pas accéder à un projet LCS à partir d’un référentiel ER qui représente un domaine différent du domaine utilisé dans Finance.</span><span class="sxs-lookup"><span data-stu-id="c812f-114">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="c812f-115">Si vous essayez, une liste vide de projets LCS s’affichera et vous ne pourrez pas importer de configurations ER à partir de la bibliothèque d’actifs au niveau du projet dans LCS.</span><span class="sxs-lookup"><span data-stu-id="c812f-115">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="c812f-116">Pour accéder aux bibliothèques d’actifs au niveau du projet à partir d’un référentiel ER utilisé pour importer des configurations ER, connectez-vous à Finance en utilisant les informations d’identification d’un utilisateur qui appartient au client (domaine) pour lequel l’instance Finance actuelle a été provisionnée.</span><span class="sxs-lookup"><span data-stu-id="c812f-116">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="c812f-117">Supprimer une version partagée d’une configuration du modèle de données</span><span class="sxs-lookup"><span data-stu-id="c812f-117">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="c812f-118">Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="c812f-118">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="c812f-119">Vous avez créé la première version d’un exemple de configuration de modèle de données et l’avez publiée dans LCS après avoir exécuté les étapes [Charger une configuration dans Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="c812f-119">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="c812f-120">Dans cette procédure, vous supprimerez cette version de la configuration ER.</span><span class="sxs-lookup"><span data-stu-id="c812f-120">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="c812f-121">Vous importerez ensuite cette version de LCS plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c812f-121">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="c812f-122">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c812f-122">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c812f-123">Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Partagé**.</span><span class="sxs-lookup"><span data-stu-id="c812f-123">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="c812f-124">Ce statut indique que la configuration a été publiée dans LCS.</span><span class="sxs-lookup"><span data-stu-id="c812f-124">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="c812f-125">Sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="c812f-125">Select **Change status**.</span></span>
4. <span data-ttu-id="c812f-126">Sélectionnez **Interrompre**.</span><span class="sxs-lookup"><span data-stu-id="c812f-126">Select **Discontinue**.</span></span>

    <span data-ttu-id="c812f-127">En modifiant le statut de la version sélectionnée de **Partagé** à **Interrompu**, vous rendez la version disponible pour la suppression.</span><span class="sxs-lookup"><span data-stu-id="c812f-127">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="c812f-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c812f-128">Select **OK**.</span></span>
6. <span data-ttu-id="c812f-129">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c812f-129">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c812f-130">Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Interrompu**.</span><span class="sxs-lookup"><span data-stu-id="c812f-130">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="c812f-131">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c812f-131">Select **Delete**.</span></span>
8. <span data-ttu-id="c812f-132">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c812f-132">Select **Yes**.</span></span>

    <span data-ttu-id="c812f-133">Notez que seule la version temporaire 2 de la configuration de modèle de données sélectionnée est maintenant disponible.</span><span class="sxs-lookup"><span data-stu-id="c812f-133">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="c812f-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c812f-134">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="c812f-135">Importer une version partagée d’une configuration du modèle de données à partir de LCS</span><span class="sxs-lookup"><span data-stu-id="c812f-135">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="c812f-136">Allez dans **Administration d’organisation \> Espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="c812f-136">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="c812f-137">Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="c812f-137">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="c812f-138">Dans la vignette **Litware, Inc.**, sélectionnez **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="c812f-138">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="c812f-139">Vous pouvez à présent ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c812f-139">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="c812f-140">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="c812f-140">Select **Open**.</span></span>

    <span data-ttu-id="c812f-141">Pour cet exemple, sélectionnez le référentiel **LCS** et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="c812f-141">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="c812f-142">Vous devez avoir [accès](#accessconditions) au projet LCS et à la bibliothèque d’actifs accessible par le référentiel ER sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c812f-142">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="c812f-143">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c812f-143">In the list, mark the selected row.</span></span>

    <span data-ttu-id="c812f-144">Pour cet exemple, sélectionnez la première version **Exemple de configuration de modèle** dans la liste des versions.</span><span class="sxs-lookup"><span data-stu-id="c812f-144">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="c812f-145">Sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="c812f-145">Select **Import**.</span></span>
7. <span data-ttu-id="c812f-146">Cliquez sur **Oui** pour confirmer l’importation de la version sélectionnée de LCS.</span><span class="sxs-lookup"><span data-stu-id="c812f-146">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="c812f-147">Un message d’information confirme que la version sélectionnée a été importée avec succès.</span><span class="sxs-lookup"><span data-stu-id="c812f-147">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="c812f-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c812f-148">Close the page.</span></span>
9. <span data-ttu-id="c812f-149">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c812f-149">Close the page.</span></span>
10. <span data-ttu-id="c812f-150">Sélectionner **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="c812f-150">Select **Configurations**.</span></span>
11. <span data-ttu-id="c812f-151">Dans l’arborescence, sélectionnez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="c812f-151">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="c812f-152">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c812f-152">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c812f-153">Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Partagé**.</span><span class="sxs-lookup"><span data-stu-id="c812f-153">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="c812f-154">Notez que seule la version partagée 1 de la configuration de modèle de données sélectionnée est également disponible.</span><span class="sxs-lookup"><span data-stu-id="c812f-154">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>
