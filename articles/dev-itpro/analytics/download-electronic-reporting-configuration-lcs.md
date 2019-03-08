---
title: Télécharger les configurations des états électroniques à partir de Lifecycle Services
description: Cette rubrique explique comment télécharger des configurations d'états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8686d2639a3ab7f2e79944cc5eed51571d463261
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "315749"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="44b9d-103">Télécharger les configurations d'états électroniques à partir de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="44b9d-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="44b9d-104">Cette rubrique explique comment télécharger des configurations d'états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="44b9d-104">This topic explains how to download Electronic reporting (ER) configurations from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="44b9d-105">Ce didacticiel vous guide via le processus de téléchargement de la version la plus récente des configurations d'états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="44b9d-105">This tutorial guides you through the process of downloading the newest version of Electronic reporting (ER) configurations from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="44b9d-106">Se connecter à Finance and Operations en utilisant l'un des rôles suivants :</span><span class="sxs-lookup"><span data-stu-id="44b9d-106">Sign in to Finance and Operations by using one of the following roles:</span></span>

    - <span data-ttu-id="44b9d-107">Développeur de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="44b9d-107">Electronic reporting developer</span></span>
    - <span data-ttu-id="44b9d-108">Consultant fonctionnel de gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="44b9d-108">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="44b9d-109">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="44b9d-109">System administrator</span></span>

2. <span data-ttu-id="44b9d-110">Allez dans **Administration d'organisation** &gt; **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="44b9d-110">Go to **Organization administration** &gt; **Electronic reporting**.</span></span>
3. <span data-ttu-id="44b9d-111">Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="44b9d-111">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4. <span data-ttu-id="44b9d-112">Dans la vignette **Microsoft**, cliquez sur **Référentiels**.</span><span class="sxs-lookup"><span data-stu-id="44b9d-112">On the **Microsoft** tile, click **Repositories**.</span></span>

    <span data-ttu-id="44b9d-113">[![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="44b9d-113">[![update-er-from-lcs-for-ms-open-ms-repositories-list](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>

5. <span data-ttu-id="44b9d-114">Sur la page **Référentiels de configuration**, dans la grille, sélectionnez le référentiel existant du type **LCS**.</span><span class="sxs-lookup"><span data-stu-id="44b9d-114">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="44b9d-115">Si ce référentiel n'apparaît pas dans la grille, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="44b9d-115">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="44b9d-116">Cliquez sur **Ajouter** pour ajouter un nouveau référentiel.</span><span class="sxs-lookup"><span data-stu-id="44b9d-116">Click **Add** to add a new repository.</span></span>
    2. <span data-ttu-id="44b9d-117">Sélectionnez **LCS** comme type de référentiel.</span><span class="sxs-lookup"><span data-stu-id="44b9d-117">Select **LCS** as the repository type.</span></span>
    3. <span data-ttu-id="44b9d-118">Cliquez sur **Créer un référentiel**.</span><span class="sxs-lookup"><span data-stu-id="44b9d-118">Click **Create repository**.</span></span>
    4. <span data-ttu-id="44b9d-119">Si vous recevez une invite, suivez les instructions d'autorisation.</span><span class="sxs-lookup"><span data-stu-id="44b9d-119">If prompted, follow the authorization instructions.</span></span>
    5. <span data-ttu-id="44b9d-120">Entrez un nom et une description pour le référentiel.</span><span class="sxs-lookup"><span data-stu-id="44b9d-120">Enter a name and description for the repository.</span></span>
    6. <span data-ttu-id="44b9d-121">Cliquez **OK** pour confirmer la nouvelle entrée de référentiel.</span><span class="sxs-lookup"><span data-stu-id="44b9d-121">Click **OK** to confirm the new repository entry.</span></span>
    7. <span data-ttu-id="44b9d-122">Dans la grille, sélectionnez le nouveau référentiel de type **LCS**.</span><span class="sxs-lookup"><span data-stu-id="44b9d-122">In the grid, select the new repository of the **LCS** type.</span></span>

6. <span data-ttu-id="44b9d-123">Cliquez sur **Ouvrir** pour afficher la liste des configurations ER pour le référentiel sélectionné.</span><span class="sxs-lookup"><span data-stu-id="44b9d-123">Click **Open** to view the list of ER configurations for the selected repository.</span></span>

    <span data-ttu-id="44b9d-124">[![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="44b9d-124">[![update-er-from-lcs-for-ms-make-lcs-repository](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>

7. <span data-ttu-id="44b9d-125">Dans l'arborescence de configurations du volet gauche, sélectionnez la configuration ER voulue.</span><span class="sxs-lookup"><span data-stu-id="44b9d-125">In the configurations tree in the left pane, select the ER configuration that you require.</span></span>
8. <span data-ttu-id="44b9d-126">Dans l'organisateur **Versions**, sélectionnez la version requise de la configuration ER sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="44b9d-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9. <span data-ttu-id="44b9d-127">Cliquez sur **Importer** pour télécharger la version sélectionnée de LCS vers l'instance Finance and Operations actuelle.</span><span class="sxs-lookup"><span data-stu-id="44b9d-127">Click **Import** to download the selected version from LCS to the current Finance and Operations instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="44b9d-128">Le bouton **Importer** n'est pas disponible pour les versions de configuration des états électroniques qui sont déjà présentes dans l'instance Finance and Operations actuelle.</span><span class="sxs-lookup"><span data-stu-id="44b9d-128">The **Import** button is unavailable for ER configuration versions that are already present in the current Finance and Operations instance.</span></span>

    <span data-ttu-id="44b9d-129">[![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="44b9d-129">[![update-er-from-lcs-for-ms-download-configuration](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="44b9d-130">Selon les paramètres d'états électroniques, les configurations sont validées après leur importation.</span><span class="sxs-lookup"><span data-stu-id="44b9d-130">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="44b9d-131">Il est possible que vous soyez averti des problèmes d'incohérences qui sont détectés.</span><span class="sxs-lookup"><span data-stu-id="44b9d-131">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="44b9d-132">Vous devez résoudre ces problèmes avant d'utiliser la version de configuration importée.</span><span class="sxs-lookup"><span data-stu-id="44b9d-132">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="44b9d-133">Pour plus d'informations, voir la liste des articles associés pour cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="44b9d-133">For more information, see the list of related articles for this topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="44b9d-134">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="44b9d-134">Additional resources</span></span>

[<span data-ttu-id="44b9d-135">Vue d'ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="44b9d-135">Electronic reporting overview</span></span>](general-electronic-reporting.md)
