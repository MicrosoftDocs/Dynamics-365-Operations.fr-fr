---
title: Télécharger les configurations ER depuis le référentiel global du service de configuration
description: Cette rubrique explique comment télécharger des configurations de gestion des états électroniques (ER) à partir du référentiel global du service de configuration.
author: NickSelin
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: c4f083163db72569d91825819a904319a0fe3123
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561900"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a><span data-ttu-id="b91f2-103">Télécharger les configurations ER depuis le référentiel global du service de configuration</span><span class="sxs-lookup"><span data-stu-id="b91f2-103">Download ER configurations from the Global repository of Configuration service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b91f2-104">Cette rubrique explique comment télécharger des [configurations de gestion des états électroniques (ER)](general-electronic-reporting.md#Configuration) à partir du référentiel global du service de configuration.</span><span class="sxs-lookup"><span data-stu-id="b91f2-104">This topic explains how to download [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the Global repository of configuration service.</span></span> <span data-ttu-id="b91f2-105">Pour plus d’informations, voir [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, service de configuration](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="b91f2-105">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="open-configurations-repository"></a><span data-ttu-id="b91f2-106">Ouvrir le référentiel de configurations</span><span class="sxs-lookup"><span data-stu-id="b91f2-106">Open configurations repository</span></span>

1. <span data-ttu-id="b91f2-107">Connectez-vous à l’application Dynamics 365 Finance en utilisant l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="b91f2-107">Sign in to the Dynamics 365 Finance application using one of the following roles:</span></span>

    - <span data-ttu-id="b91f2-108">Développeur de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="b91f2-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="b91f2-109">Consultant fonctionnel des états électroniques</span><span class="sxs-lookup"><span data-stu-id="b91f2-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="b91f2-110">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="b91f2-110">System administrator</span></span>

2. <span data-ttu-id="b91f2-111">Accédez à **Administration d’organisation > Espaces de travail > États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="b91f2-111">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="b91f2-112">Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b91f2-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
3. <span data-ttu-id="b91f2-113">Dans la vignette **Microsoft**, sélectionnez **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="b91f2-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    ![Espace de travail des états électroniques](./media/er-download-configurations-global-repo-er-workspace.png)

4. <span data-ttu-id="b91f2-115">Sur la page **Référentiels de configuration**, dans la grille, sélectionnez le référentiel existant du type **Global**.</span><span class="sxs-lookup"><span data-stu-id="b91f2-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **Global** type.</span></span> <span data-ttu-id="b91f2-116">Si ce référentiel n’apparaît pas dans la grille, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b91f2-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="b91f2-117">Sélectionnez **Ajouter** pour ajouter un nouveau référentiel.</span><span class="sxs-lookup"><span data-stu-id="b91f2-117">Select **Add** to add a new repository.</span></span>
    2. <span data-ttu-id="b91f2-118">Sélectionnez **Global** comme type de référentiel, puis sélectionnez **Créer un référentiel**.</span><span class="sxs-lookup"><span data-stu-id="b91f2-118">Select **Global** as the repository type, and then select **Create repository**.</span></span>
    3. <span data-ttu-id="b91f2-119">Si vous recevez une invite, suivez les instructions d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="b91f2-119">If prompted, follow the authorization instructions.</span></span>
    4. <span data-ttu-id="b91f2-120">Saisissez un nom et une description pour le référentiel, puis sélectionnez **OK** pour confirmer la nouvelle entrée de référentiel.</span><span class="sxs-lookup"><span data-stu-id="b91f2-120">Enter a name and description for the repository and then select **OK** to confirm the new repository entry.</span></span>
    5. <span data-ttu-id="b91f2-121">Dans la grille, sélectionnez le nouveau référentiel de type **Global**.</span><span class="sxs-lookup"><span data-stu-id="b91f2-121">In the grid, select the new repository of the **Global** type.</span></span>

5. <span data-ttu-id="b91f2-122">Sélectionnez **Ouvrir** pour afficher la liste des configurations ER pour le référentiel sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b91f2-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    ![Page des référentiels de configurations](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a><span data-ttu-id="b91f2-124">Importer une configuration unique</span><span class="sxs-lookup"><span data-stu-id="b91f2-124">Import a single configuration</span></span>

1. <span data-ttu-id="b91f2-125">Dans la page **Référentiels de configurations**, dans l’arborescence des configurations, sélectionnez la configuration ER souhaitée.</span><span class="sxs-lookup"><span data-stu-id="b91f2-125">On the **Configuration repositories** page, in the configurations tree, select the ER configuration that you want.</span></span>
2. <span data-ttu-id="b91f2-126">Dans l’organisateur **Versions**, sélectionnez la version requise de la configuration ER sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b91f2-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
3. <span data-ttu-id="b91f2-127">Sélectionnez **Importer** pour télécharger la version sélectionnée depuis le référentiel global vers l’instance Finance and Operations actuelle.</span><span class="sxs-lookup"><span data-stu-id="b91f2-127">Select **Import** to download the selected version from Global repository to the current Finance instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b91f2-128">Le bouton **Importer** n’est pas disponible pour les versions de configuration de gestion des états électroniques qui sont déjà présentes dans l’instance Finance actuelle.</span><span class="sxs-lookup"><span data-stu-id="b91f2-128">The **Import** button is unavailable for ER configuration versions that are already present in the current Finance instance.</span></span>

    ![Page du référentiel de configuration](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a><span data-ttu-id="b91f2-130">Importer des configurations filtrées</span><span class="sxs-lookup"><span data-stu-id="b91f2-130">Import filtered configurations</span></span>

1. <span data-ttu-id="b91f2-131">Dans la page **Référentiels de configurations**, dans l’arborescence des configurations, développez le raccourci **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="b91f2-131">On the **Configuration repositories** page, in the configurations tree, expand the **Filter** FastTab.</span></span>
2. <span data-ttu-id="b91f2-132">Dans la grille **Balises**, ajoutez les balises nécessaires.</span><span class="sxs-lookup"><span data-stu-id="b91f2-132">In the **Tags** grid, add any tags that are needed.</span></span>
3. <span data-ttu-id="b91f2-133">Dans le champ **Applicabilité par pays/région**, sélectionnez les codes de pays/région appropriés, puis sélectionnez **Appliquer le filtre**.</span><span class="sxs-lookup"><span data-stu-id="b91f2-133">In the **Country/region applicability** field, select the appropriate country/region codes, and then select  **Apply filter**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b91f2-134">Le raccourci **Configurations** affiche toutes les configurations qui satisfont aux conditions de sélection spécifiées.</span><span class="sxs-lookup"><span data-stu-id="b91f2-134">The **Configurations** FastTab shows all the configurations that satisfy the specified selection conditions.</span></span>

4. <span data-ttu-id="b91f2-135">Dans le raccourci **Configurations**, sélectionnez **Importer** pour télécharger les configurations filtrées depuis le référentiel global vers l’instance actuelle.</span><span class="sxs-lookup"><span data-stu-id="b91f2-135">On the **Configurations** FastTab, select **Import** to download the filtered configurations from the Global repository to the current instance.</span></span>
5. <span data-ttu-id="b91f2-136">Dans le raccourci **Configurations**, sélectionnez **Réinitialiser le filtre** pour effacer les conditions de sélection spécifiées.</span><span class="sxs-lookup"><span data-stu-id="b91f2-136">On the **Configurations** FastTab, select **Reset filter** to clean up the specified selection conditions.</span></span>

    ![Page du référentiel de configuration](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> <span data-ttu-id="b91f2-138">Selon les paramètres d’états électroniques, les configurations sont validées après leur importation.</span><span class="sxs-lookup"><span data-stu-id="b91f2-138">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="b91f2-139">Il est possible que vous soyez averti des problèmes d’incohérences qui sont détectés.</span><span class="sxs-lookup"><span data-stu-id="b91f2-139">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="b91f2-140">Avant de pouvoir utiliser la version de configuration importée, vous devez résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="b91f2-140">Before you can use the imported configuration version, you must resolve the issues.</span></span> <span data-ttu-id="b91f2-141">Pour plus d’informations, voir la liste des ressources associées pour cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b91f2-141">For more information, see the list of related resources for this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="b91f2-142">Les configurations de gestion des états électroniques peuvent être configurées comme dépendantes d’autres configurations.</span><span class="sxs-lookup"><span data-stu-id="b91f2-142">ER configurations can be configured as being dependent on other configurations.</span></span> <span data-ttu-id="b91f2-143">Par conséquent, d’autres configurations peuvent être automatiquement importées avec une configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b91f2-143">Therefore, along with a selected configuration, other configurations might be automatically imported.</span></span> <span data-ttu-id="b91f2-144">Pour plus d’informations sur les dépendances des configurations, voir [Définir la dépendance des configurations ER à d’autres composants](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span><span class="sxs-lookup"><span data-stu-id="b91f2-144">For more about configuration dependencies, see [Define the dependency of ER configurations on other components](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b91f2-145">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b91f2-145">Additional resources</span></span>

[<span data-ttu-id="b91f2-146">Vue d’ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="b91f2-146">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]