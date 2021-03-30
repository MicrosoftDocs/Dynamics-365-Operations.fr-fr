---
title: Utilisation de fichiers de remplacement CSS
description: Cette rubrique décrit pourquoi, quand et comment utiliser les fichiers de remplacement de feuilles de style en cascade (CSS) dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 41fb0be51f7af25faba1b860319aea84ae7a8b56
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207797"
---
# <a name="work-with-css-override-files"></a><span data-ttu-id="75e0f-103">Utiliser CSS pour remplacer les fichiers</span><span class="sxs-lookup"><span data-stu-id="75e0f-103">Work with CSS override files</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="75e0f-104">Cette rubrique décrit pourquoi, quand et comment utiliser les fichiers de remplacement de feuilles de style en cascade (CSS) dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="75e0f-104">This topic describes why, when, and how to use Cascading Style Sheets (CSS) override files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="75e0f-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="75e0f-105">Overview</span></span>

<span data-ttu-id="75e0f-106">Les styles de sites permanents doivent généralement être gérés via le thème d'un site.</span><span class="sxs-lookup"><span data-stu-id="75e0f-106">Permanent site styles should usually be handled through a site's theme.</span></span> <span data-ttu-id="75e0f-107">Les thèmes fournissent les paramètres de CSS et de style de base pour les modules sur n'importe quelle page de votre site.</span><span class="sxs-lookup"><span data-stu-id="75e0f-107">Themes provide the foundational CSS and style settings for the modules on any page of your site.</span></span> <span data-ttu-id="75e0f-108">Les thèmes sont créés à l'aide du kit de développement logiciel en ligne (SDK) Dynamics 365 Commerce, et ils sont déployés sur vos sites web via Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="75e0f-108">Themes are created by using the Dynamics 365 Commerce online software development kit (SDK), and they are deployed to your websites through Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="75e0f-109">Les capacités de débogage de thème et les configurations d'interface de module dans le kit de développement logiciel en ligne (SDK) aident les développeurs de sites à créer des packages de conception de site personnalisables et cohérents.</span><span class="sxs-lookup"><span data-stu-id="75e0f-109">Theme debugging capabilities and module interface configurations in the SDK help site developers create customizable and cohesive site design packages.</span></span> <span data-ttu-id="75e0f-110">Lorsque ces packages de conception sont déployés sur un site, les auteurs du site peuvent se concentrer sur la création, la modification et la publication de contenu au lieu du développement du site.</span><span class="sxs-lookup"><span data-stu-id="75e0f-110">When these design packages are deployed to a site, site authors can focus on creating, editing, and publishing content instead of site development.</span></span>

<span data-ttu-id="75e0f-111">Étant donné le cycle de vie habituel d'un thème, la dépendance aux développeurs d'apporter des modifications de style via le pipeline de déploiement de Kit de développement logiciel (SDK) et LCS peut être prohibitive dans certains scénarios.</span><span class="sxs-lookup"><span data-stu-id="75e0f-111">Given the usual lifecycle of a theme, the dependency on developers to make style changes through the SDK and LCS deployment pipeline can be prohibitive in some scenarios.</span></span> <span data-ttu-id="75e0f-112">Les prototypes de site ou les correctifs peuvent sembler encombrants si le Kit de développement logiciel (SDK) n'est pas configuré ou si vous n'avez pas le temps d'attendre un déploiement LCS.</span><span class="sxs-lookup"><span data-stu-id="75e0f-112">Site prototypes or hotfixes can seem cumbersome if the SDK isn't configured, or if you don't have time to wait for an LCS deployment.</span></span>

<span data-ttu-id="75e0f-113">Dans ces scénarios, les fichiers de remplacement CSS peuvent aider.</span><span class="sxs-lookup"><span data-stu-id="75e0f-113">In these scenarios, CSS override files can help.</span></span> <span data-ttu-id="75e0f-114">Dans les outils de création Commerce, les utilisateurs authentifiés peuvent télécharger un fichier CSS, le prévisualiser, puis l'activer pour remplacer le thème d'un site.</span><span class="sxs-lookup"><span data-stu-id="75e0f-114">In the Commerce authoring tools, authenticated users can upload a CSS file, preview it, and then activate it to override a site's theme.</span></span> <span data-ttu-id="75e0f-115">La surcharge du déploiement du Kit de développement logiciel (SDK) ou de LCS n'est pas requise.</span><span class="sxs-lookup"><span data-stu-id="75e0f-115">The overhead of SDK or LCS deployment isn't required.</span></span> <span data-ttu-id="75e0f-116">Les remplacements spécifiés dans un fichier de remplacement CSS peuvent être aussi petits qu'une modification d'un style de texte unique ou aussi étendus qu'une refonte complète de la marque.</span><span class="sxs-lookup"><span data-stu-id="75e0f-116">The overrides that are specified in a CSS override file can be as small as a change to a single text style or as wide-ranging as a complete brand overhaul.</span></span>

<span data-ttu-id="75e0f-117">Avant d'utiliser les fichiers de remplacement CSS, tenez compte des limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="75e0f-117">Before you use CSS override files, be aware of the following limitations:</span></span>

- <span data-ttu-id="75e0f-118">Seul un fichier de remplacement CSS peut être actif sur un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="75e0f-118">Only one CSS override file can be active on a site at a time.</span></span> <span data-ttu-id="75e0f-119">Par conséquent, tous les remplacements actifs doivent être présents dans un seul fichier de remplacement.</span><span class="sxs-lookup"><span data-stu-id="75e0f-119">Therefore, all active overrides must be present in a single override file.</span></span>
- <span data-ttu-id="75e0f-120">Bien que vous puissiez prévisualiser les remplacements dans les outils de création Commerce, il n'y a pas de fonctionnalités de débogage dédiées pour identifier les bogues que les remplacements introduisent.</span><span class="sxs-lookup"><span data-stu-id="75e0f-120">Although you can preview the overrides in the Commerce authoring tools, there are no dedicated debugging features to help identify any bugs that the overrides introduce.</span></span> <span data-ttu-id="75e0f-121">En d'autres termes, lorsque vous utilisez les fichiers de remplacement CSS, vous n'avez pas le même ensemble d'outils que le Kit de développement logiciel (SDK) fournit pour la validation du module et de la création.</span><span class="sxs-lookup"><span data-stu-id="75e0f-121">In other words, when you use CSS override files, you don't have the same toolset that the SDK provides for module and authoring validation.</span></span>

<span data-ttu-id="75e0f-122">Cependant, les fichiers de remplacement CSS fournissent un moyen rapide de prototyper une conception ou d'implémenter un correctif avant qu'une mise à jour complète du thème ne soit développée et déployée.</span><span class="sxs-lookup"><span data-stu-id="75e0f-122">Nevertheless, CSS override files provide a quick way to prototype a design or implement a hotfix before a full theme update is developed and deployed.</span></span>

## <a name="create-a-css-override-file"></a><span data-ttu-id="75e0f-123">Créer un fichier de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="75e0f-123">Create a CSS override file</span></span>

<span data-ttu-id="75e0f-124">Pour créer un fichier de remplacement CSS, vous pouvez utiliser n'importe quel environnement de développement intégré (IDE), éditeur de texte ou éditeur de code source.</span><span class="sxs-lookup"><span data-stu-id="75e0f-124">To create a CSS override file, you can use any integrated development environment (IDE), text editor, or source code editor.</span></span> <span data-ttu-id="75e0f-125">Une approche typique consiste à utiliser des débogueurs web standard dans votre navigateur pour identifier les sélecteurs de style, les propriétés et les valeurs sur votre site existant.</span><span class="sxs-lookup"><span data-stu-id="75e0f-125">A typical approach is to use standard web debuggers in your browser to identify style selectors, properties, and values on your existing site.</span></span> <span data-ttu-id="75e0f-126">La plupart des navigateurs vous permettent de modifier des valeurs et de les prévisualiser dans le débogueur.</span><span class="sxs-lookup"><span data-stu-id="75e0f-126">Most browsers let you change values and preview them in the debugger.</span></span> <span data-ttu-id="75e0f-127">Après avoir identifié les modifications que vous souhaitez apporter, vous pouvez les enregistrer dans votre propre fichier CSS.</span><span class="sxs-lookup"><span data-stu-id="75e0f-127">After you've identified the changes that you want to make, you can save them to your own CSS file.</span></span>

## <a name="upload-a-css-override-file"></a><span data-ttu-id="75e0f-128">Charger un fichier de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="75e0f-128">Upload a CSS override file</span></span>

<span data-ttu-id="75e0f-129">Pour télécharger un fichier CSS sur votre site dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="75e0f-129">To upload a CSS file to your site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="75e0f-130">Dans les outils de création, accédez à votre site.</span><span class="sxs-lookup"><span data-stu-id="75e0f-130">In the authoring tools, go to your site.</span></span>
1. <span data-ttu-id="75e0f-131">Dans le volet de navigation sur la gauche, sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="75e0f-131">In the navigation pane on the left, select **Design**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75e0f-132">Selon la version des outils de création Commerce que vous utilisez, vous devrez peut-être développer **Paramètres** dans le volet de navigation avant de pouvoir sélectionner **Conception**.</span><span class="sxs-lookup"><span data-stu-id="75e0f-132">Depending on the version of the Commerce authoring tools that you're using, you might have to expand **Settings** in the navigation pane before you can select **Design**.</span></span>

1. <span data-ttu-id="75e0f-133">En haut du volet de conception principal, sélectionnez l'onglet **Remplacement par CSS**, s'il n'est pas déjà sélectionné.</span><span class="sxs-lookup"><span data-stu-id="75e0f-133">At the top of the main design pane, select the **CSS override** tab, if it isn't already selected.</span></span>
1. <span data-ttu-id="75e0f-134">En dessous de **Remplacements CSS disponibles**, sélectionnez **Télécharger un fichier CSS**.</span><span class="sxs-lookup"><span data-stu-id="75e0f-134">Under **Available CSS overrides**, select **Upload CSS file**.</span></span> <span data-ttu-id="75e0f-135">Une fenêtre de l'Explorateur de fichiers apparaît.</span><span class="sxs-lookup"><span data-stu-id="75e0f-135">A File Explorer window appears.</span></span>
1. <span data-ttu-id="75e0f-136">Dans l'Explorateur de fichiers, recherchez et sélectionnez un fichier CSS, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="75e0f-136">In File Explorer, browse to and select a CSS file, and then select **Open**.</span></span> <span data-ttu-id="75e0f-137">Le fichier CSS téléchargé apparaît maintenant sous **Remplacements CSS disponibles**.</span><span class="sxs-lookup"><span data-stu-id="75e0f-137">The uploaded CSS file now appears under **Available CSS overrides**.</span></span>

## <a name="preview-a-css-override-file"></a><span data-ttu-id="75e0f-138">Aperçu d'un fichier de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="75e0f-138">Preview a CSS override file</span></span>

<span data-ttu-id="75e0f-139">Pour prévisualiser un fichier de remplacement CSS avant de le rendre actif sur votre site en ligne, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="75e0f-139">To preview a CSS override file before you make it active on your live site, follow these steps.</span></span>

1. <span data-ttu-id="75e0f-140">Dans le volet de navigation de gauche, sélectionnez **Conception**, puis, sous l'onglet **Remplacement CSS**, sous **Remplacements CSS disponibles**, recherchez le fichier CSS que vous souhaitez prévisualiser.</span><span class="sxs-lookup"><span data-stu-id="75e0f-140">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to preview.</span></span>
1. <span data-ttu-id="75e0f-141">À côté du nom du fichier CSS, sélectionnez **Aperçu du site**.</span><span class="sxs-lookup"><span data-stu-id="75e0f-141">Next to the CSS file name, select **Preview site**.</span></span>
1. <span data-ttu-id="75e0f-142">Dans la boîte de dialogue **Sélectionnez une URL**, sélectionnez l'URL du site auquel vous souhaitez voir la substitution appliquée, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="75e0f-142">In the **Select a URL** dialog box, select the URL of the site that you want to see the override applied to, and then select **OK**.</span></span>
1. <span data-ttu-id="75e0f-143">S'il existe plusieurs variantes pour l'URL sélectionnée, sélectionnez la variante souhaitée dans la boîte de dialogue **Aperçu des variations** qui apparaît.</span><span class="sxs-lookup"><span data-stu-id="75e0f-143">If there are multiple variants for the selected URL, select the desired variant in the **Preview variations** dialog box that appears.</span></span>

<span data-ttu-id="75e0f-144">Un nouvel onglet ou une nouvelle fenêtre de navigateur s'ouvre, où vous pouvez valider vos remplacements de style par rapport à votre site.</span><span class="sxs-lookup"><span data-stu-id="75e0f-144">A new browser tab or window is opened, where you can validate your style overrides against your site.</span></span> <span data-ttu-id="75e0f-145">Vous pouvez ensuite partager l'URL avec d'autres utilisateurs de Commerce authentifiés pour évaluation et commentaires.</span><span class="sxs-lookup"><span data-stu-id="75e0f-145">You can then share the URL with other authenticated Commerce users for review and feedback.</span></span>

## <a name="activate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="75e0f-146">Activez un fichier de remplacement CSS sur votre site en ligne</span><span class="sxs-lookup"><span data-stu-id="75e0f-146">Activate a CSS override file on your live site</span></span>

<span data-ttu-id="75e0f-147">Après avoir prévisualisé et approuvé le fichier de remplacement CSS, vous pouvez l'activer sur votre site en ligne.</span><span class="sxs-lookup"><span data-stu-id="75e0f-147">After you've previewed and approved the CSS override file, you can activate it on your live site.</span></span>

> [!NOTE]
> <span data-ttu-id="75e0f-148">Seul un fichier de remplacement CSS peut être actif sur votre site à la fois.</span><span class="sxs-lookup"><span data-stu-id="75e0f-148">Only one CSS override file can be active on your site at a time.</span></span> <span data-ttu-id="75e0f-149">Si vous activez un nouveau fichier de remplacement, le fichier de remplacement précédent est désactivé.</span><span class="sxs-lookup"><span data-stu-id="75e0f-149">If you activate a new override file, the previous override file is inactivated.</span></span> <span data-ttu-id="75e0f-150">Par conséquent, assurez-vous que tous les remplacements requis sont présents dans un seul fichier de remplacement CSS.</span><span class="sxs-lookup"><span data-stu-id="75e0f-150">Therefore, make sure that all required overrides are present in a single CSS override file.</span></span>

<span data-ttu-id="75e0f-151">Pour activer un fichier de remplacement CSS, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="75e0f-151">To activate a CSS override file, follow these steps.</span></span>

1. <span data-ttu-id="75e0f-152">Dans le volet de navigation de gauche, sélectionnez **Conception**, puis, sous l'onglet **Remplacement CSS**, sous **Remplacements CSS disponibles**, recherchez le fichier CSS que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="75e0f-152">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to activate.</span></span>
1. <span data-ttu-id="75e0f-153">Sous le nom du fichier CSS, sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="75e0f-153">Under the CSS file name, select **Activate**.</span></span> <span data-ttu-id="75e0f-154">Le fichier de remplacement devient immédiatement actif sur votre site en ligne.</span><span class="sxs-lookup"><span data-stu-id="75e0f-154">The override file immediately becomes active on your live site.</span></span>

## <a name="deactivate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="75e0f-155">Désactivez un fichier de remplacement CSS sur votre site en ligne</span><span class="sxs-lookup"><span data-stu-id="75e0f-155">Deactivate a CSS override file on your live site</span></span>

<span data-ttu-id="75e0f-156">Pour désactiver un fichier de remplacement CSS sur votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="75e0f-156">To deactivate a CSS override file on your site, follow these steps.</span></span>

1. <span data-ttu-id="75e0f-157">Dans le volet de navigation de gauche, sélectionnez **Conception**, puis, sous l'onglet **Remplacement CSS**, sous **Remplacements CSS disponibles**, recherchez le fichier CSS que vous souhaitez désactiver.</span><span class="sxs-lookup"><span data-stu-id="75e0f-157">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to deactivate.</span></span>
1. <span data-ttu-id="75e0f-158">Sous le nom du fichier CSS, sélectionnez **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="75e0f-158">Under the CSS file name, select **Deactivate**.</span></span> <span data-ttu-id="75e0f-159">Le fichier de remplacement devient immédiatement inactif sur votre site en ligne.</span><span class="sxs-lookup"><span data-stu-id="75e0f-159">The override file immediately becomes inactive on your live site.</span></span>

> [!TIP]
> <span data-ttu-id="75e0f-160">Pour accéder à des options supplémentaires pour les fichiers de remplacement CSS, sélectionnez les points de suspension (**...**) à côté du nom de fichier CSS.</span><span class="sxs-lookup"><span data-stu-id="75e0f-160">To access additional options for CSS override files, select the ellipsis (**...**) next to the CSS file name.</span></span> <span data-ttu-id="75e0f-161">Les options **Télécharger**, **Renommer** et **Remplacer** sont utiles pour des changements rapides à un fichier de remplacement CSS existant.</span><span class="sxs-lookup"><span data-stu-id="75e0f-161">The **Download**, **Rename**, and **Replace** options are useful for quick changes to an existing CSS override file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="75e0f-162">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="75e0f-162">Additional resources</span></span>

[<span data-ttu-id="75e0f-163">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="75e0f-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="75e0f-164">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="75e0f-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="75e0f-165">Utiliser des réglages de style prédéfinis</span><span class="sxs-lookup"><span data-stu-id="75e0f-165">Work with style presets</span></span>](style-presets.md)

[<span data-ttu-id="75e0f-166">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="75e0f-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="75e0f-167">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="75e0f-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="75e0f-168">Ajouter un avis de droits d'auteur</span><span class="sxs-lookup"><span data-stu-id="75e0f-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="75e0f-169">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="75e0f-169">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="75e0f-170">Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="75e0f-170">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]