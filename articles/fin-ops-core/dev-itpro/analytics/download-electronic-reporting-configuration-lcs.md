---
title: Télécharger les configurations des états électroniques à partir de Lifecycle Services
description: Cette rubrique explique comment télécharger des configurations d’états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 719b277fb828ea2085ea80bc4a36c2af3412f66b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683303"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="0714a-103">Télécharger les configurations d’états électroniques à partir de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="0714a-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0714a-104">Cette rubrique explique comment télécharger la dernière version de [Configurations de la génération d’états électroniques (ER)](general-electronic-reporting.md#Configuration) de la [Bibliothèque de ressources partagée](../lifecycle-services/asset-library.md) dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="0714a-104">This topic explains how to download the newest version of [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the [Shared asset library](../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="0714a-105">Se connecter à l’application en utilisant l’un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="0714a-105">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="0714a-106">Développeur d’états électroniques</span><span class="sxs-lookup"><span data-stu-id="0714a-106">Electronic reporting developer</span></span>
    - <span data-ttu-id="0714a-107">Consultant fonctionnel des états électroniques</span><span class="sxs-lookup"><span data-stu-id="0714a-107">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="0714a-108">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="0714a-108">System administrator</span></span>

2. <span data-ttu-id="0714a-109">Accédez à **Administration d’organisation** &gt; **Espaces de travail** &gt; **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="0714a-109">Go to **Organization administration** &gt; **Workspaces** &gt; **Electronic reporting**.</span></span>
3. <span data-ttu-id="0714a-110">Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0714a-110">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4. <span data-ttu-id="0714a-111">Dans la vignette **Microsoft**, sélectionnez **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="0714a-111">On the **Microsoft** tile, select **Repositories**.</span></span>

    <span data-ttu-id="0714a-112">[![Vignette Microsoft sur la page des configurations de localisation](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="0714a-112">[![Microsoft tile on the Localization configurations page](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>

5. <span data-ttu-id="0714a-113">Sur la page **Référentiels de configuration**, dans la grille, sélectionnez le référentiel existant du type **LCS**.</span><span class="sxs-lookup"><span data-stu-id="0714a-113">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="0714a-114">Si ce référentiel n’apparaît pas dans la grille, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0714a-114">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="0714a-115">Sélectionnez **Ajouter** pour ajouter un référentiel.</span><span class="sxs-lookup"><span data-stu-id="0714a-115">Select **Add** to add a repository.</span></span>
    2. <span data-ttu-id="0714a-116">Sélectionnez **LCS** comme type de référentiel.</span><span class="sxs-lookup"><span data-stu-id="0714a-116">Select **LCS** as the repository type.</span></span>
    3. <span data-ttu-id="0714a-117">Sélectionnez **Créer un référentiel**.</span><span class="sxs-lookup"><span data-stu-id="0714a-117">Select **Create repository**.</span></span>
    4. <span data-ttu-id="0714a-118">Si vous êtes invité à fournir une autorisation, suivez les instructions à l’écran.</span><span class="sxs-lookup"><span data-stu-id="0714a-118">If you're prompted about authorization, follow the on-screen instructions.</span></span>
    5. <span data-ttu-id="0714a-119">Entrez un nom et une description pour le référentiel.</span><span class="sxs-lookup"><span data-stu-id="0714a-119">Enter a name and description for the repository.</span></span>
    6. <span data-ttu-id="0714a-120">Cliquez sur **OK** pour confirmer la nouvelle entrée de référentiel.</span><span class="sxs-lookup"><span data-stu-id="0714a-120">Select **OK** to confirm the new repository entry.</span></span>
    7. <span data-ttu-id="0714a-121">Dans la grille, sélectionnez le nouveau référentiel de type **LCS**.</span><span class="sxs-lookup"><span data-stu-id="0714a-121">In the grid, select the new repository of the **LCS** type.</span></span>

6. <span data-ttu-id="0714a-122">Sélectionnez **Ouvrir** pour afficher la liste des configurations ER pour le référentiel sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0714a-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    <span data-ttu-id="0714a-123">[![Page des référentiels de configurations](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="0714a-123">[![Configuration repositories page](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>

    > [!TIP]
    > <span data-ttu-id="0714a-124">Si vous ne parvenez pas à accéder au référentiel LCS pour télécharger des configurations à partir de la bibliothèque d’actifs partagée dans LCS, vous pouvez télécharger des configurations à partir du [référentiel général](er-download-configurations-global-repo.md).</span><span class="sxs-lookup"><span data-stu-id="0714a-124">If you have trouble accessing the LCS repository to download configurations from the Shared asset library in LCS, you can download configurations from the [Global repository](er-download-configurations-global-repo.md) instead.</span></span>

7. <span data-ttu-id="0714a-125">Dans l’arborescence de configurations du volet gauche, sélectionnez la configuration ER requise.</span><span class="sxs-lookup"><span data-stu-id="0714a-125">In the configurations tree in the left pane, select the required ER configuration.</span></span>
8. <span data-ttu-id="0714a-126">Dans l’organisateur **Versions**, sélectionnez la version requise de la configuration ER sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0714a-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9. <span data-ttu-id="0714a-127">Cliquez sur **Importer** pour télécharger la version sélectionnée de LCS vers l’instance actuelle.</span><span class="sxs-lookup"><span data-stu-id="0714a-127">Select **Import** to download the selected version from LCS to the current instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0714a-128">Le bouton **Importer** n’est pas disponible pour les versions de configuration des états électroniques qui sont déjà présentes dans l’instance actuelle.</span><span class="sxs-lookup"><span data-stu-id="0714a-128">The **Import** button is unavailable for ER configuration versions that are already present in the current instance.</span></span>

    <span data-ttu-id="0714a-129">[![Page du référentiel de configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="0714a-129">[![Configuration repository page](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0714a-130">Selon les paramètres d’états électroniques, les configurations sont validées après leur importation.</span><span class="sxs-lookup"><span data-stu-id="0714a-130">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="0714a-131">Il est possible que vous soyez averti des problèmes d’incohérences qui sont détectés.</span><span class="sxs-lookup"><span data-stu-id="0714a-131">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="0714a-132">Vous devez résoudre ces problèmes avant d’utiliser la version de configuration importée.</span><span class="sxs-lookup"><span data-stu-id="0714a-132">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="0714a-133">Pour plus d’informations, voir la liste des rubriques associées pour cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="0714a-133">For more information, see the list of related topics for this topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0714a-134">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0714a-134">Additional resources</span></span>

[<span data-ttu-id="0714a-135">Vue d’ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="0714a-135">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="0714a-136">Télécharger les configurations ER depuis le référentiel global du service de configuration</span><span class="sxs-lookup"><span data-stu-id="0714a-136">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)
