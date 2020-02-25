---
title: Configuration du libre-service employé
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e44a35071b8d0987e6c949fb11312204317b44a1
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009025"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="78779-102">Configuration du libre-service employé</span><span class="sxs-lookup"><span data-stu-id="78779-102">Configure employee self service</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="78779-103">Dans Microsoft Dynamics 365 Human Resources, vous pouvez configurer des vignettes pour une navigation de niveau supérieur dans le libre-service employé.</span><span class="sxs-lookup"><span data-stu-id="78779-103">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="78779-104">Les vignettes de plan d'avantages dirigent les utilisateurs vers les plans d'avantages auxquels ils sont admissibles.</span><span class="sxs-lookup"><span data-stu-id="78779-104">Benefit plan tiles direct users to benefit plans that they are eligible to enroll in.</span></span>

## <a name="set-up-a-role-center-tile"></a><span data-ttu-id="78779-105">Configuration de la vignette d'aperçu interactif</span><span class="sxs-lookup"><span data-stu-id="78779-105">Set up a role center tile</span></span>

1. <span data-ttu-id="78779-106">Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres du libre-service employé**.</span><span class="sxs-lookup"><span data-stu-id="78779-106">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="78779-107">Sélectionnez l'onglet **Configuration de la vignette d'aperçu interactif**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="78779-107">Select the **Role center tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="78779-108">Spécifiez les valeurs les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="78779-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="78779-109">Champ</span><span class="sxs-lookup"><span data-stu-id="78779-109">Field</span></span> | <span data-ttu-id="78779-110">Description</span><span class="sxs-lookup"><span data-stu-id="78779-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="78779-111">ID vignette</span><span class="sxs-lookup"><span data-stu-id="78779-111">Tile ID</span></span> | <span data-ttu-id="78779-112">Identificateur unique de la vignette.</span><span class="sxs-lookup"><span data-stu-id="78779-112">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="78779-113">Texte d'étiquette de vignette</span><span class="sxs-lookup"><span data-stu-id="78779-113">Tile label text</span></span> | <span data-ttu-id="78779-114">Texte qui sera affiché pour la vignette sur le libre-service.</span><span class="sxs-lookup"><span data-stu-id="78779-114">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="78779-115">Description</span><span class="sxs-lookup"><span data-stu-id="78779-115">Description</span></span> | <span data-ttu-id="78779-116">Description de la vignette.</span><span class="sxs-lookup"><span data-stu-id="78779-116">A description of the tile.</span></span> |
   | <span data-ttu-id="78779-117">Adresse Internet</span><span class="sxs-lookup"><span data-stu-id="78779-117">Internet address</span></span> | <span data-ttu-id="78779-118">Saisissez l'URL de la page du libre-service employé.</span><span class="sxs-lookup"><span data-stu-id="78779-118">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="78779-119">Taille de la vignette</span><span class="sxs-lookup"><span data-stu-id="78779-119">Tile size</span></span> | <span data-ttu-id="78779-120">Taille de la vignette : petite, moyenne ou grande.</span><span class="sxs-lookup"><span data-stu-id="78779-120">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="78779-121">Cible</span><span class="sxs-lookup"><span data-stu-id="78779-121">Target</span></span> | <span data-ttu-id="78779-122">Spécifie si la page doit s'ouvrir dans une nouvelle fenêtre ou la fenêtre actuelle.</span><span class="sxs-lookup"><span data-stu-id="78779-122">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="78779-123">Image d'arrière-plan de la vignette</span><span class="sxs-lookup"><span data-stu-id="78779-123">Tile background image</span></span> | <span data-ttu-id="78779-124">URL de l'image à utiliser pour la vignette (facultatif).</span><span class="sxs-lookup"><span data-stu-id="78779-124">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="78779-125">Commencement</span><span class="sxs-lookup"><span data-stu-id="78779-125">Start</span></span> | <span data-ttu-id="78779-126">Date et heure de début auxquelles la vignette doit être disponible.</span><span class="sxs-lookup"><span data-stu-id="78779-126">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="78779-127">Terminer</span><span class="sxs-lookup"><span data-stu-id="78779-127">End</span></span> | <span data-ttu-id="78779-128">Date et heure de fin auxquelles la vignette doit être disponible.</span><span class="sxs-lookup"><span data-stu-id="78779-128">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="78779-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="78779-129">Select **Save**.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="78779-130">Paramétrage d'une vignette de plans d'avantage</span><span class="sxs-lookup"><span data-stu-id="78779-130">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="78779-131">Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres du libre-service employé**.</span><span class="sxs-lookup"><span data-stu-id="78779-131">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="78779-132">Sélectionnez l'onglet **Paramétrage d'une vignette de plans d'avantage**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="78779-132">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="78779-133">Spécifiez les valeurs les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="78779-133">Specify values for the following fields:</span></span>

   | <span data-ttu-id="78779-134">Champ</span><span class="sxs-lookup"><span data-stu-id="78779-134">Field</span></span> | <span data-ttu-id="78779-135">Description</span><span class="sxs-lookup"><span data-stu-id="78779-135">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="78779-136">ID vignette</span><span class="sxs-lookup"><span data-stu-id="78779-136">Tile ID</span></span> | <span data-ttu-id="78779-137">Identificateur unique de la vignette.</span><span class="sxs-lookup"><span data-stu-id="78779-137">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="78779-138">Texte d'étiquette de vignette</span><span class="sxs-lookup"><span data-stu-id="78779-138">Tile label text</span></span> | <span data-ttu-id="78779-139">Texte qui sera affiché pour la vignette sur le libre-service.</span><span class="sxs-lookup"><span data-stu-id="78779-139">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="78779-140">Description</span><span class="sxs-lookup"><span data-stu-id="78779-140">Description</span></span> | <span data-ttu-id="78779-141">Description de la vignette.</span><span class="sxs-lookup"><span data-stu-id="78779-141">A description of the tile.</span></span> |
   | <span data-ttu-id="78779-142">Adresse Internet</span><span class="sxs-lookup"><span data-stu-id="78779-142">Internet address</span></span> | <span data-ttu-id="78779-143">Saisissez l'URL de la page du libre-service employé.</span><span class="sxs-lookup"><span data-stu-id="78779-143">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="78779-144">Taille de la vignette</span><span class="sxs-lookup"><span data-stu-id="78779-144">Tile size</span></span> | <span data-ttu-id="78779-145">Taille de la vignette : petite, moyenne ou grande.</span><span class="sxs-lookup"><span data-stu-id="78779-145">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="78779-146">Cible</span><span class="sxs-lookup"><span data-stu-id="78779-146">Target</span></span> | <span data-ttu-id="78779-147">Spécifie si la page doit s'ouvrir dans une nouvelle fenêtre ou la fenêtre actuelle.</span><span class="sxs-lookup"><span data-stu-id="78779-147">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="78779-148">Image d'arrière-plan de la vignette</span><span class="sxs-lookup"><span data-stu-id="78779-148">Tile background image</span></span> | <span data-ttu-id="78779-149">URL de l'image à utiliser pour la vignette (facultatif).</span><span class="sxs-lookup"><span data-stu-id="78779-149">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="78779-150">Commencement</span><span class="sxs-lookup"><span data-stu-id="78779-150">Start</span></span> | <span data-ttu-id="78779-151">Date et heure de début auxquelles la vignette doit être disponible.</span><span class="sxs-lookup"><span data-stu-id="78779-151">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="78779-152">Terminer</span><span class="sxs-lookup"><span data-stu-id="78779-152">End</span></span> | <span data-ttu-id="78779-153">Date et heure de fin auxquelles la vignette doit être disponible.</span><span class="sxs-lookup"><span data-stu-id="78779-153">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="78779-154">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="78779-154">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="78779-155">Configuration d'une vignette de plan de crédit flexible</span><span class="sxs-lookup"><span data-stu-id="78779-155">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="78779-156">Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres du libre-service employé**.</span><span class="sxs-lookup"><span data-stu-id="78779-156">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="78779-157">Sélectionnez l'onglet **Paramétrage d'une vignette de plan de crédit flexible**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="78779-157">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="78779-158">Spécifiez les valeurs les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="78779-158">Specify values for the following fields:</span></span>

   | <span data-ttu-id="78779-159">Champ</span><span class="sxs-lookup"><span data-stu-id="78779-159">Field</span></span> | <span data-ttu-id="78779-160">Description</span><span class="sxs-lookup"><span data-stu-id="78779-160">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="78779-161">ID vignette</span><span class="sxs-lookup"><span data-stu-id="78779-161">Tile ID</span></span> | <span data-ttu-id="78779-162">Identificateur unique de la vignette.</span><span class="sxs-lookup"><span data-stu-id="78779-162">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="78779-163">Texte d'étiquette de vignette</span><span class="sxs-lookup"><span data-stu-id="78779-163">Tile label text</span></span> | <span data-ttu-id="78779-164">Texte qui sera affiché pour la vignette sur le libre-service.</span><span class="sxs-lookup"><span data-stu-id="78779-164">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="78779-165">Description</span><span class="sxs-lookup"><span data-stu-id="78779-165">Description</span></span> | <span data-ttu-id="78779-166">Description de la vignette.</span><span class="sxs-lookup"><span data-stu-id="78779-166">A description of the tile.</span></span> |
   | <span data-ttu-id="78779-167">Adresse Internet</span><span class="sxs-lookup"><span data-stu-id="78779-167">Internet address</span></span> | <span data-ttu-id="78779-168">Saisissez l'URL de la page du libre-service employé.</span><span class="sxs-lookup"><span data-stu-id="78779-168">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="78779-169">Taille de la vignette</span><span class="sxs-lookup"><span data-stu-id="78779-169">Tile size</span></span> | <span data-ttu-id="78779-170">Taille de la vignette : petite, moyenne ou grande.</span><span class="sxs-lookup"><span data-stu-id="78779-170">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="78779-171">Cible</span><span class="sxs-lookup"><span data-stu-id="78779-171">Target</span></span> | <span data-ttu-id="78779-172">Spécifie si la page doit s'ouvrir dans une nouvelle fenêtre ou la fenêtre actuelle.</span><span class="sxs-lookup"><span data-stu-id="78779-172">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="78779-173">Image d'arrière-plan de la vignette</span><span class="sxs-lookup"><span data-stu-id="78779-173">Tile background image</span></span> | <span data-ttu-id="78779-174">URL de l'image à utiliser pour la vignette (facultatif).</span><span class="sxs-lookup"><span data-stu-id="78779-174">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="78779-175">Commencement</span><span class="sxs-lookup"><span data-stu-id="78779-175">Start</span></span> | <span data-ttu-id="78779-176">Date et heure de début auxquelles la vignette doit être disponible.</span><span class="sxs-lookup"><span data-stu-id="78779-176">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="78779-177">Terminer</span><span class="sxs-lookup"><span data-stu-id="78779-177">End</span></span> | <span data-ttu-id="78779-178">Date et heure de fin auxquelles la vignette doit être disponible.</span><span class="sxs-lookup"><span data-stu-id="78779-178">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="78779-179">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="78779-179">Select **Save**.</span></span>
