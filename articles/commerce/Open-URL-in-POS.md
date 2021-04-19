---
title: Ouvrir une URL dans PDV
description: Cette rubrique fournit une vue d’ensemble des améliorations apportées à la fonctionnalité de recherche de produits et de clients dans Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 252b24919e4c22233ee8fe7e94c9bc6bbf60dacd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796460"
---
# <a name="open-url-in-pos"></a><span data-ttu-id="872ea-103">Ouvrir une URL dans le point de vente</span><span class="sxs-lookup"><span data-stu-id="872ea-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="872ea-104">Cette rubrique décrit comment configurer un bouton dans le point de vente (PDV) Retail pour ouvrir une URL.</span><span class="sxs-lookup"><span data-stu-id="872ea-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="872ea-105">Cette fonctionnalité ne nécessite pas de personnalisation du code, et peut être configurée par une personne avec un rôle non développeur.</span><span class="sxs-lookup"><span data-stu-id="872ea-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span> 

<span data-ttu-id="872ea-106">Cette fonctionnalité permet la configuration d’un bouton dans PDV, à l’aide du concepteur de grille de boutons pour ouvrir une URL.</span><span class="sxs-lookup"><span data-stu-id="872ea-106">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="872ea-107">Actuellement, cette opération est prise en charge dans les configurations suivantes :</span><span class="sxs-lookup"><span data-stu-id="872ea-107">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="872ea-108">Ouvrir dans une nouvelle fenêtre.</span><span class="sxs-lookup"><span data-stu-id="872ea-108">Open in new window.</span></span>
- <span data-ttu-id="872ea-109">Ouvrir dans PDV.</span><span class="sxs-lookup"><span data-stu-id="872ea-109">Open within POS.</span></span>
- <span data-ttu-id="872ea-110">Ouvrir une application native.</span><span class="sxs-lookup"><span data-stu-id="872ea-110">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="872ea-111">Ouvrir dans une nouvelle fenêtre</span><span class="sxs-lookup"><span data-stu-id="872ea-111">Open in new window</span></span>

<span data-ttu-id="872ea-112">Cette configuration détermine si l’URL doit s’ouvrir dans une nouvelle fenêtre ou de l’application.</span><span class="sxs-lookup"><span data-stu-id="872ea-112">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="872ea-113">Si elle est configurée pour ouvrir une URL web dans l’application, le volet de navigation latéral et la barre supérieure du PDV sont visibles et disponibles pour une intervention de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="872ea-113">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="872ea-114">Si elle est configurée pour s’ouvrir dans une nouvelle fenêtre, l’URL s’ouvre dans une nouvelle fenêtre d’application sur Modern POS pour Windows, et dans un nouvel onglet du navigateur dans tous les autres clients du PDV.</span><span class="sxs-lookup"><span data-stu-id="872ea-114">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="872ea-115">Pour ce faire, vous devez configurer l’URL avec l’option **Ouvrir dans une nouvelle fenêtre** sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="872ea-115">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="872ea-116">Ouvrir dans le PDV</span><span class="sxs-lookup"><span data-stu-id="872ea-116">Open within POS</span></span>

<span data-ttu-id="872ea-117">L’ouverture d’une URL Web dans le PDV n’est pris en charge actuellement que pour Modern POS sous Windows.</span><span class="sxs-lookup"><span data-stu-id="872ea-117">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="872ea-118">Sous d’autres clients, cette capacité est en cours de développement et son lancement est planifié dans les futures mises à jour.</span><span class="sxs-lookup"><span data-stu-id="872ea-118">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="872ea-119">Pour ce faire, vous devez configurer l’URL avec l’option **Ouvrir dans une nouvelle fenêtre** non sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="872ea-119">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="872ea-120">Ouvrir une application native</span><span class="sxs-lookup"><span data-stu-id="872ea-120">Open a native app</span></span>

<span data-ttu-id="872ea-121">Cette fonction vous permet également de spécifier les URL non Web pour ouvrir une application native.</span><span class="sxs-lookup"><span data-stu-id="872ea-121">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="872ea-122">Par exemple, vous pouvez spécifier des protocoles d’URL tels que MailTo, SIP, IM ou MSTEAMS, qui peuvent ensuite être gérés par les applications natives respectives dans le périphérique de serveur.</span><span class="sxs-lookup"><span data-stu-id="872ea-122">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="872ea-123">Pour ce faire, vous devez configurer l’URL avec l’option **Ouvrir dans une nouvelle fenêtre** sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="872ea-123">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="872ea-124">Pour les ordinateurs Windows, voir [Exporter ou importer les associations d’applications par défaut](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) pour définir les associations de protocoles par défaut si vous paramétrez votre ordinateur à l’aide de DISM (Deployment Image Servicing and Management).</span><span class="sxs-lookup"><span data-stu-id="872ea-124">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="872ea-125">Si vous utilisez MDM, tel qu’Intune, pour gérer vos ordinateurs Windows, voir [Stratégie CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="872ea-125">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="872ea-126">Si vous êtes développeur et que vous générez un site Web personnalisé, voir [Lancer l’application par défaut pour une URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="872ea-126">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="872ea-127">Ouvrir une application native en toute transparence</span><span class="sxs-lookup"><span data-stu-id="872ea-127">Open a native app seamlessly</span></span>

<span data-ttu-id="872ea-128">Windows, iOS et Android permettent également l’ouverture des applications de façon plus transparente, selon l’association du protocole d’application.</span><span class="sxs-lookup"><span data-stu-id="872ea-128">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="872ea-129">Si votre application n’est pas déjà configurée pour gérer l’ouverture d’un navigateur Web, vous pouvez nécessiter un développeur pour la configurer.</span><span class="sxs-lookup"><span data-stu-id="872ea-129">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="872ea-130">Pour Windows, voir [Activer les applications pour les sites Web avec des gestionnaires d’URI d’application](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="872ea-130">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="872ea-131">Pour iOS, voir [Liens universels pour les développeurs](https://developer.apple.com/ios/universal-links/).</span><span class="sxs-lookup"><span data-stu-id="872ea-131">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="872ea-132">Pour Android, voir [Gestion des liens d’applications Android](https://developer.android.com/training/app-links/).</span><span class="sxs-lookup"><span data-stu-id="872ea-132">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="872ea-133">Client</span><span class="sxs-lookup"><span data-stu-id="872ea-133">Client</span></span>                | <span data-ttu-id="872ea-134">Ouvrir dans une nouvelle fenêtre</span><span class="sxs-lookup"><span data-stu-id="872ea-134">Open in new window</span></span> | <span data-ttu-id="872ea-135">Ouvrir une application native</span><span class="sxs-lookup"><span data-stu-id="872ea-135">Open native app</span></span> | <span data-ttu-id="872ea-136">Ouvrir dans le PDV</span><span class="sxs-lookup"><span data-stu-id="872ea-136">Open within POS</span></span> | <span data-ttu-id="872ea-137">Détails</span><span class="sxs-lookup"><span data-stu-id="872ea-137">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="872ea-138">Modern POS sous Windows</span><span class="sxs-lookup"><span data-stu-id="872ea-138">Modern POS on Windows</span></span> | <span data-ttu-id="872ea-139">✓\*</span><span class="sxs-lookup"><span data-stu-id="872ea-139">✓\*</span></span>                | <span data-ttu-id="872ea-140">✓</span><span class="sxs-lookup"><span data-stu-id="872ea-140">✓</span></span>               | <span data-ttu-id="872ea-141">✓</span><span class="sxs-lookup"><span data-stu-id="872ea-141">✓</span></span>              | <span data-ttu-id="872ea-142">\* S’ouvre dans une nouvelle fenêtre Modern POS</span><span class="sxs-lookup"><span data-stu-id="872ea-142">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="872ea-143">PDV Cloud</span><span class="sxs-lookup"><span data-stu-id="872ea-143">Cloud POS</span></span>             | <span data-ttu-id="872ea-144">✓\*</span><span class="sxs-lookup"><span data-stu-id="872ea-144">✓\*</span></span>                | <span data-ttu-id="872ea-145">✓</span><span class="sxs-lookup"><span data-stu-id="872ea-145">✓</span></span>               | <span data-ttu-id="872ea-146">O</span><span class="sxs-lookup"><span data-stu-id="872ea-146">X</span></span>              | <span data-ttu-id="872ea-147">\* S’ouvre dans un nouvel onglet du navigateur</span><span class="sxs-lookup"><span data-stu-id="872ea-147">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="872ea-148">Modern POS sous iOS</span><span class="sxs-lookup"><span data-stu-id="872ea-148">Modern POS on iOS</span></span>     | <span data-ttu-id="872ea-149">✓\*</span><span class="sxs-lookup"><span data-stu-id="872ea-149">✓\*</span></span>                | <span data-ttu-id="872ea-150">✓</span><span class="sxs-lookup"><span data-stu-id="872ea-150">✓</span></span>               | <span data-ttu-id="872ea-151">O</span><span class="sxs-lookup"><span data-stu-id="872ea-151">X</span></span>              | <span data-ttu-id="872ea-152">\* S’ouvre dans un nouvel onglet du navigateur</span><span class="sxs-lookup"><span data-stu-id="872ea-152">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="872ea-153">Modern POS sous Android</span><span class="sxs-lookup"><span data-stu-id="872ea-153">Modern POS on Android</span></span> | <span data-ttu-id="872ea-154">✓\*</span><span class="sxs-lookup"><span data-stu-id="872ea-154">✓\*</span></span>                | <span data-ttu-id="872ea-155">✓</span><span class="sxs-lookup"><span data-stu-id="872ea-155">✓</span></span>               | <span data-ttu-id="872ea-156">O</span><span class="sxs-lookup"><span data-stu-id="872ea-156">X</span></span>              | <span data-ttu-id="872ea-157">\* S’ouvre dans un nouvel onglet du navigateur</span><span class="sxs-lookup"><span data-stu-id="872ea-157">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="872ea-158">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="872ea-158">Before you begin</span></span>

<span data-ttu-id="872ea-159">Avant de commencer, examinez la procédure de configuration des [Mises en page de l’écran pour le point de vente (PDV)](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="872ea-159">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="872ea-160">Ouvrir une URL dans PDV</span><span class="sxs-lookup"><span data-stu-id="872ea-160">Open URL in POS</span></span>

<span data-ttu-id="872ea-161">Pour configurer l’ouverture d’une URL dans le PDV, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="872ea-161">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="872ea-162">Au niveau du siège social, accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Mises en page de l’écran**.</span><span class="sxs-lookup"><span data-stu-id="872ea-162">In head office, go to **Retail and Commerce \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="872ea-163">Sélectionnez **Grilles de boutons \> Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="872ea-163">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="872ea-164">Créez un bouton.</span><span class="sxs-lookup"><span data-stu-id="872ea-164">Create a new button.</span></span>
4. <span data-ttu-id="872ea-165">Sélectionnez les propriétés du **Bouton**.</span><span class="sxs-lookup"><span data-stu-id="872ea-165">Select **Button** properties.</span></span>
5. <span data-ttu-id="872ea-166">Sélectionnez **Ouvrir l’URL** comme action.</span><span class="sxs-lookup"><span data-stu-id="872ea-166">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="872ea-167">Entrez l’URL à utiliser.</span><span class="sxs-lookup"><span data-stu-id="872ea-167">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="872ea-168">Indiquez si l’URL doit s’ouvrir dans une nouvelle fenêtre.</span><span class="sxs-lookup"><span data-stu-id="872ea-168">Configure whether to open the URL in a new window.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]