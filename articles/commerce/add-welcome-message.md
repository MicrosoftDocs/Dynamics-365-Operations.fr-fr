---
title: Ajouter un message de bienvenue
description: Cette rubrique décrit la procédure d'ajout d'un message d'accueil à votre site web Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5910ab85b1b0b2df992a24ad3cf7a032e7b98ea9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980130"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="37166-103">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="37166-103">Add a welcome message</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="37166-104">Cette rubrique décrit la procédure d'ajout d'un message d'accueil à votre site web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="37166-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="37166-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="37166-105">Overview</span></span>

<span data-ttu-id="37166-106">Un message de bienvenue de votre site web de commerce électronique peut informer les visiteurs sur les soldes en cours, les mises à jour du site, ou de la disponibilité des collections de la saison.</span><span class="sxs-lookup"><span data-stu-id="37166-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="37166-107">Le message de bienvenue est défini à l'aide du module d'alerte.</span><span class="sxs-lookup"><span data-stu-id="37166-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="37166-108">Le module d'alerte doit être ajouté à l'emplacement **Messages d'erreur/d'information** du fragment d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="37166-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="37166-109">Le module d'alerte vous permet de spécifier le texte qui s'affiche, la couleur du texte, et l'alignement.</span><span class="sxs-lookup"><span data-stu-id="37166-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="37166-110">Il vous permet également de spécifier si les visiteurs du site peuvent ignorer le message.</span><span class="sxs-lookup"><span data-stu-id="37166-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="37166-111">Lorsqu'un message de bienvenue est ajouté à un fragment d'en-tête partagé, il s'affiche sur chaque page qui utilise le modèle dans lequel ce fragment d'en-tête partagé est utilisé.</span><span class="sxs-lookup"><span data-stu-id="37166-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="37166-112">Pour ajouter un message de bienvenue à votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="37166-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="37166-113">Dans le générateur de site Commerce, accédez à votre site.</span><span class="sxs-lookup"><span data-stu-id="37166-113">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="37166-114">Sélectionnez **Fragments**.</span><span class="sxs-lookup"><span data-stu-id="37166-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="37166-115">Sélectionnez le fragment d'en-tête pour ajouter le message.</span><span class="sxs-lookup"><span data-stu-id="37166-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="37166-116">Dans l'arborescence du contour, développez **Messages d'erreur/d'information**.</span><span class="sxs-lookup"><span data-stu-id="37166-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="37166-117">Sélectionnez le module d'alerte, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="37166-117">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="37166-118">Si un module d'alerte n'existe pas encore, sélectionnez d'abord le bouton représentant des points de suspension (**...**) en regard de **Messages d'erreur/d'information**, et sélectionnez **Ajouter le module**.</span><span class="sxs-lookup"><span data-stu-id="37166-118">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="37166-119">Dans le volet de propriété de droite, sous l'onglet **Données**, sélectionnez **Ajouter une source de données**, puis sélectionnez **Contenu**.</span><span class="sxs-lookup"><span data-stu-id="37166-119">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="37166-120">Dans le champ **Texte entré**, entrez le texte du message de bienvenue.</span><span class="sxs-lookup"><span data-stu-id="37166-120">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="37166-121">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment d'en-tête, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="37166-121">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="37166-122">Le message de bienvenue apparaît désormais en haut de chaque page du site qui utilise le fragment d'en-tête sélectionné.</span><span class="sxs-lookup"><span data-stu-id="37166-122">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="37166-123">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="37166-123">Additional resources</span></span>

[<span data-ttu-id="37166-124">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="37166-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="37166-125">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="37166-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="37166-126">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="37166-126">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="37166-127">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="37166-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="37166-128">Ajouter un avis de droits d'auteur</span><span class="sxs-lookup"><span data-stu-id="37166-128">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="37166-129">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="37166-129">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="37166-130">Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="37166-130">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

