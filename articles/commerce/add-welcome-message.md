---
title: Ajouter un message de bienvenue
description: Cette rubrique décrit la procédure d'ajout d'un message d'accueil à votre site web Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 25a4e91646916b03c8a138fc713577f429ab633c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697380"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="84c13-103">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="84c13-103">Add a welcome message</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="84c13-104">Cette rubrique décrit la procédure d'ajout d'un message d'accueil à votre site web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="84c13-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="84c13-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="84c13-105">Overview</span></span>

<span data-ttu-id="84c13-106">Un message de bienvenue de votre site web de commerce électronique peut informer les visiteurs sur les soldes en cours, les mises à jour du site, ou de la disponibilité des collections de la saison.</span><span class="sxs-lookup"><span data-stu-id="84c13-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="84c13-107">Le message de bienvenue est défini à l'aide du module d'alerte.</span><span class="sxs-lookup"><span data-stu-id="84c13-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="84c13-108">Le module d'alerte doit être ajouté à l'emplacement **Messages d'erreur/d'information** du fragment d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="84c13-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="84c13-109">Le module d'alerte vous permet de spécifier le texte qui s'affiche, la couleur du texte, et l'alignement.</span><span class="sxs-lookup"><span data-stu-id="84c13-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="84c13-110">Il vous permet également de spécifier si les visiteurs du site peuvent ignorer le message.</span><span class="sxs-lookup"><span data-stu-id="84c13-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="84c13-111">Lorsqu'un message de bienvenue est ajouté à un fragment d'en-tête partagé, il s'affiche sur chaque page qui utilise le modèle dans lequel ce fragment d'en-tête partagé est utilisé.</span><span class="sxs-lookup"><span data-stu-id="84c13-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="84c13-112">Pour ajouter un message de bienvenue à votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="84c13-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="84c13-113">Dans Dynamics 365 Commerce, accédez à votre site.</span><span class="sxs-lookup"><span data-stu-id="84c13-113">In Dynamics 365 Commerce, go to your site.</span></span>
1. <span data-ttu-id="84c13-114">Sélectionnez **Fragments**.</span><span class="sxs-lookup"><span data-stu-id="84c13-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="84c13-115">Sélectionnez le fragment d'en-tête pour ajouter le message.</span><span class="sxs-lookup"><span data-stu-id="84c13-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="84c13-116">Dans l'arborescence du contour, développez **Messages d'erreur/d'information**.</span><span class="sxs-lookup"><span data-stu-id="84c13-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="84c13-117">Sélectionnez le module d'alerte.</span><span class="sxs-lookup"><span data-stu-id="84c13-117">Select the alert module.</span></span>

    <span data-ttu-id="84c13-118">Si un module d'alerte n'existe pas encore, sélectionnez le bouton représentant des points de suspension (**...**) en regard de **Messages d'erreur/d'information**, et le sélectionnez **Ajouter le module**.</span><span class="sxs-lookup"><span data-stu-id="84c13-118">If an alert module doesn't yet exist, select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span> <span data-ttu-id="84c13-119">Sélectionnez le module d'alerte, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="84c13-119">Select the alert module, and then select **OK**.</span></span>

1. <span data-ttu-id="84c13-120">Dans le volet de propriété de droite, sous l'onglet **Données**, sélectionnez **Ajouter une source de données**, puis sélectionnez **Contenu**.</span><span class="sxs-lookup"><span data-stu-id="84c13-120">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="84c13-121">Dans le champ **Texte entré**, entrez le texte du message de bienvenue.</span><span class="sxs-lookup"><span data-stu-id="84c13-121">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="84c13-122">Enregistrez le fragment d'en-tête, archivez-le, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="84c13-122">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="84c13-123">Le message de bienvenue apparaît désormais en haut de chaque page du site qui utilise le fragment d'en-tête sélectionné.</span><span class="sxs-lookup"><span data-stu-id="84c13-123">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="84c13-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="84c13-124">Additional resources</span></span>

[<span data-ttu-id="84c13-125">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="84c13-125">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="84c13-126">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="84c13-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="84c13-127">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="84c13-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="84c13-128">Ajouter un avis de droits d'auteur</span><span class="sxs-lookup"><span data-stu-id="84c13-128">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="84c13-129">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="84c13-129">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="84c13-130">Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="84c13-130">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

