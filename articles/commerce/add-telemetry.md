---
title: Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie
description: Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 674d00faf1b30f87a0b0062129e1b9fbff955dd4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001275"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="13307-103">Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="13307-103">Add script code to site pages to support telemetry</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="13307-104">Cette rubrique décrit comment ajouter un code du script côté client à vos pages du site pour prendre en charge la collection de télémétrie côté client.</span><span class="sxs-lookup"><span data-stu-id="13307-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="13307-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="13307-105">Overview</span></span>

<span data-ttu-id="13307-106">Les analyses web sont un outil essentiel lorsque vous souhaitez inclure la manière dont vos clients peuvent interagir avec votre site et prendre des décisions qui aideront à optimiser l'expérience pour la conversion maximale.</span><span class="sxs-lookup"><span data-stu-id="13307-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="13307-107">De nombreux packages d'analyses web sont disponibles pour vous aider à atteindre ces objectifs, comme Google Analytics, Clicky, Moz Analytics, et KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="13307-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="13307-108">La plupart des packages d'analyses web nécessitent que vous ajoutiez un code du script côté client dans l'élément **\<en-tête\>** du fichier HTML pour toutes les pages du site.</span><span class="sxs-lookup"><span data-stu-id="13307-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="13307-109">Les instructions de cette rubrique s'appliquent également à l'autre fonctionnalité côté client personnalisée que Microsoft Dynamics 365 Commerce n'offre pas en mode natif.</span><span class="sxs-lookup"><span data-stu-id="13307-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="13307-110">Créer un fragment réutilisable pour votre code de script</span><span class="sxs-lookup"><span data-stu-id="13307-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="13307-111">Après avoir créé un fragment pour votre code du script, il peut être réutilisé dans l'ensemble des pages sur votre site.</span><span class="sxs-lookup"><span data-stu-id="13307-111">After you create a fragment for your script code, it can be reused across all pages on your site.</span></span>

1. <span data-ttu-id="13307-112">Accédez à **Fragments \> Nouveau fragment de page**.</span><span class="sxs-lookup"><span data-stu-id="13307-112">Go to **Fragments \> New page fragment**.</span></span>
2. <span data-ttu-id="13307-113">Sélectionnez **Script externe**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="13307-113">Select **External Script**, enter a name for the fragment, and then select **OK**.</span></span>
3. <span data-ttu-id="13307-114">Dans la hiérarchie du fragment, sélectionnez l'enfant du module **injecteur de script** du fragment que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="13307-114">In the fragment hierarchy, select the **script injector** module child of the fragment that you just created.</span></span>
4. <span data-ttu-id="13307-115">Dans le volet de propriétés de droite, ajoutez le script côté client, et définissez d'autres options de configuration comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="13307-115">In the property pane on the right, add your client-side script, and set other configuration options as you require.</span></span>

## <a name="add-the-fragment-to-templates"></a><span data-ttu-id="13307-116">Ajouter le fragment aux modèles</span><span class="sxs-lookup"><span data-stu-id="13307-116">Add the fragment to templates</span></span>

1. <span data-ttu-id="13307-117">Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre code de script.</span><span class="sxs-lookup"><span data-stu-id="13307-117">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
2. <span data-ttu-id="13307-118">Dans le volet gauche, développez la hiérarchie de modèle pour afficher l'emplacement **En-tête HTML**.</span><span class="sxs-lookup"><span data-stu-id="13307-118">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
3. <span data-ttu-id="13307-119">Sélectionnez le bouton représentant des points de suspension (**...**) en regard de l'emplacement **Pied de page HTML**, et sélectionnez **Ajouter un fragment**.</span><span class="sxs-lookup"><span data-stu-id="13307-119">Select the ellipsis button (**...**) for the **HTML Head** slot, and then select **Add fragment**.</span></span>
4. <span data-ttu-id="13307-120">Sélectionnez le fragment créé pour votre code de script.</span><span class="sxs-lookup"><span data-stu-id="13307-120">Select the fragment that you created for your script code.</span></span>
5. <span data-ttu-id="13307-121">Enregistrez le modèle, et archivez-le.</span><span class="sxs-lookup"><span data-stu-id="13307-121">Save the template, and check it in.</span></span>

> [!NOTE]
> <span data-ttu-id="13307-122">Après avoir terminé, vous devez publier fragment et le modèle principal.</span><span class="sxs-lookup"><span data-stu-id="13307-122">After you've finished, you must publish the fragment and the master template.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="13307-123">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="13307-123">Additional resources</span></span>

[<span data-ttu-id="13307-124">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="13307-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="13307-125">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="13307-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="13307-126">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="13307-126">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="13307-127">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="13307-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="13307-128">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="13307-128">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="13307-129">Ajouter un avis de droits d'auteur</span><span class="sxs-lookup"><span data-stu-id="13307-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="13307-130">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="13307-130">Add languages to your site</span></span>](add-languages-to-site.md)

