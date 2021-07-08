---
title: Importer une configuration à partir de Lifecycle Services
description: Cette rubrique décrit comment importer une nouvelle version d’une configuration pour la gestion des états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b58ecb8a7d6f52631dbca7642a4acbcf6ff895a3
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270835"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="042a4-103">Importer une configuration à partir de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="042a4-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="042a4-104">Cette rubrique explique comment un utilisateur ayant le rôle d’administrateur système ou de développeur d’états électroniques peut importer une nouvelle version d’une configuration pour la [génération d’états électroniques (ER)](../general-electronic-reporting.md#Configuration) à partir de la [bibliothèque d’actifs au niveau du projet](../../lifecycle-services/asset-library.md) dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="042a4-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="042a4-105">L’utilisation de LCS comme référentiel de stockage pour les configurations ER est en cours [d’abandon](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="042a4-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="042a4-106">Pour plus d’informations, voir [Regulatory Configuration Service (RCS) – Abandon du stockage Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span><span class="sxs-lookup"><span data-stu-id="042a4-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="042a4-107">Dans cet exemple, vous allez sélectionner la version souhaitée de la configuration ER et l’importer pour un exemple société nommée Litware, Inc. Ces étapes peuvent être réalisées dans n’importe quelle société, car les configurations ER sont partagées entre les sociétés.</span><span class="sxs-lookup"><span data-stu-id="042a4-107">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="042a4-108">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure [Charger une configuration dans Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="042a4-108">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="042a4-109">L’accès à LCS est également requis.</span><span class="sxs-lookup"><span data-stu-id="042a4-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="042a4-110">Se connecter à l’application en utilisant l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="042a4-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="042a4-111">Développeur de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="042a4-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="042a4-112">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="042a4-112">System administrator</span></span>

2. <span data-ttu-id="042a4-113">Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="042a4-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="042a4-114">Sélectionner **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="042a4-114">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="042a4-115">Assurez-vous que l’utilisateur Dynamics 365 Finance actuel est membre du projet LCS qui contient la bibliothèque d’actifs à laquelle l’utilisateur souhaite [accéder](../../lifecycle-services/asset-library.md#asset-library-support) pour importer des configurations ER.</span><span class="sxs-lookup"><span data-stu-id="042a4-115">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="042a4-116">Vous ne pouvez pas accéder à un projet LCS à partir d’un référentiel ER qui représente un domaine différent du domaine utilisé dans Finance.</span><span class="sxs-lookup"><span data-stu-id="042a4-116">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="042a4-117">Si vous essayez, une liste vide de projets LCS s’affichera et vous ne pourrez pas importer de configurations ER à partir de la bibliothèque d’actifs au niveau du projet dans LCS.</span><span class="sxs-lookup"><span data-stu-id="042a4-117">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="042a4-118">Pour accéder aux bibliothèques d’actifs au niveau du projet à partir d’un référentiel ER utilisé pour importer des configurations ER, connectez-vous à Finance en utilisant les informations d’identification d’un utilisateur qui appartient au client (domaine) pour lequel l’instance Finance actuelle a été provisionnée.</span><span class="sxs-lookup"><span data-stu-id="042a4-118">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="042a4-119">Supprimer une version partagée d’une configuration du modèle de données</span><span class="sxs-lookup"><span data-stu-id="042a4-119">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="042a4-120">Sur la page **Configurations**, dans l’arborescence de configuration, sélectionnez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="042a4-120">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="042a4-121">Vous avez créé la première version d’un exemple de configuration de modèle de données et l’avez publiée dans LCS après avoir exécuté les étapes [Charger une configuration dans Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="042a4-121">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="042a4-122">Dans cette procédure, vous supprimerez cette version de la configuration ER.</span><span class="sxs-lookup"><span data-stu-id="042a4-122">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="042a4-123">Vous importerez ensuite cette version de LCS plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="042a4-123">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="042a4-124">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="042a4-124">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="042a4-125">Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Partagé**.</span><span class="sxs-lookup"><span data-stu-id="042a4-125">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="042a4-126">Ce statut indique que la configuration a été publiée dans LCS.</span><span class="sxs-lookup"><span data-stu-id="042a4-126">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="042a4-127">Sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="042a4-127">Select **Change status**.</span></span>
4. <span data-ttu-id="042a4-128">Sélectionnez **Interrompre**.</span><span class="sxs-lookup"><span data-stu-id="042a4-128">Select **Discontinue**.</span></span>

    <span data-ttu-id="042a4-129">En modifiant le statut de la version sélectionnée de **Partagé** à **Interrompu**, vous rendez la version disponible pour la suppression.</span><span class="sxs-lookup"><span data-stu-id="042a4-129">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="042a4-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="042a4-130">Select **OK**.</span></span>
6. <span data-ttu-id="042a4-131">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="042a4-131">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="042a4-132">Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Interrompu**.</span><span class="sxs-lookup"><span data-stu-id="042a4-132">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="042a4-133">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="042a4-133">Select **Delete**.</span></span>
8. <span data-ttu-id="042a4-134">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="042a4-134">Select **Yes**.</span></span>

    <span data-ttu-id="042a4-135">Notez que seule la version temporaire 2 de la configuration de modèle de données sélectionnée est maintenant disponible.</span><span class="sxs-lookup"><span data-stu-id="042a4-135">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="042a4-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="042a4-136">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="042a4-137">Importer une version partagée d’une configuration du modèle de données à partir de LCS</span><span class="sxs-lookup"><span data-stu-id="042a4-137">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="042a4-138">Allez dans **Administration d’organisation \> Espaces de travail \> États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="042a4-138">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="042a4-139">Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="042a4-139">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="042a4-140">Dans la vignette **Litware, Inc.**, sélectionnez **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="042a4-140">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="042a4-141">Vous pouvez à présent ouvrir la liste des référentiels pour le fournisseur de configuration Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="042a4-141">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="042a4-142">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="042a4-142">Select **Open**.</span></span>

    <span data-ttu-id="042a4-143">Pour cet exemple, sélectionnez le référentiel **LCS** et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="042a4-143">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="042a4-144">Vous devez avoir [accès](#accessconditions) au projet LCS et à la bibliothèque d’actifs accessible par le référentiel ER sélectionné.</span><span class="sxs-lookup"><span data-stu-id="042a4-144">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="042a4-145">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="042a4-145">In the list, mark the selected row.</span></span>

    <span data-ttu-id="042a4-146">Pour cet exemple, sélectionnez la première version **Exemple de configuration de modèle** dans la liste des versions.</span><span class="sxs-lookup"><span data-stu-id="042a4-146">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="042a4-147">Sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="042a4-147">Select **Import**.</span></span>
7. <span data-ttu-id="042a4-148">Cliquez sur **Oui** pour confirmer l’importation de la version sélectionnée de LCS.</span><span class="sxs-lookup"><span data-stu-id="042a4-148">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="042a4-149">Un message d’information confirme que la version sélectionnée a été importée avec succès.</span><span class="sxs-lookup"><span data-stu-id="042a4-149">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="042a4-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="042a4-150">Close the page.</span></span>
9. <span data-ttu-id="042a4-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="042a4-151">Close the page.</span></span>
10. <span data-ttu-id="042a4-152">Sélectionner **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="042a4-152">Select **Configurations**.</span></span>
11. <span data-ttu-id="042a4-153">Dans l’arborescence, sélectionnez **Exemple de configuration de modèle**.</span><span class="sxs-lookup"><span data-stu-id="042a4-153">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="042a4-154">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="042a4-154">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="042a4-155">Pour cet exemple, sélectionnez la version de la configuration dont le statut est **Partagé**.</span><span class="sxs-lookup"><span data-stu-id="042a4-155">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="042a4-156">Notez que seule la version partagée 1 de la configuration de modèle de données sélectionnée est également disponible.</span><span class="sxs-lookup"><span data-stu-id="042a4-156">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
