---
title: Ajouter un message de bienvenue
description: Cette rubrique décrit la procédure d’ajout d’un message d’accueil à votre site web Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e61f43eca7d1343d020e1c01b5b1140f07b63c6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797381"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="a5fe8-103">Ajouter un message de bienvenue</span><span class="sxs-lookup"><span data-stu-id="a5fe8-103">Add a welcome message</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a5fe8-104">Cette rubrique décrit la procédure d’ajout d’un message d’accueil à votre site web Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

<span data-ttu-id="a5fe8-105">Un message de bienvenue de votre site web de commerce électronique peut informer les visiteurs sur les soldes en cours, les mises à jour du site, ou de la disponibilité des collections de la saison.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-105">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="a5fe8-106">Le message de bienvenue est défini à l’aide du module d’alerte.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-106">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="a5fe8-107">Le module d’alerte doit être ajouté à l’emplacement **Messages d’erreur/d’information** du fragment d’en-tête.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-107">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="a5fe8-108">Le module d’alerte vous permet de spécifier le texte qui s’affiche, la couleur du texte, et l’alignement.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-108">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="a5fe8-109">Il vous permet également de spécifier si les visiteurs du site peuvent ignorer le message.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-109">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="a5fe8-110">Lorsqu’un message de bienvenue est ajouté à un fragment d’en-tête partagé, il s’affiche sur chaque page qui utilise le modèle dans lequel ce fragment d’en-tête partagé est utilisé.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-110">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="a5fe8-111">Pour ajouter un message de bienvenue à votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-111">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="a5fe8-112">Dans le générateur de site Commerce, accédez à votre site.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-112">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="a5fe8-113">Sélectionnez **Fragments**.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-113">Select **Fragments**.</span></span>
1. <span data-ttu-id="a5fe8-114">Sélectionnez le fragment d’en-tête pour ajouter le message.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-114">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="a5fe8-115">Dans l’arborescence du contour, développez **Messages d’erreur/d’information**.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-115">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="a5fe8-116">Sélectionnez le module d’alerte, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-116">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="a5fe8-117">Si un module d’alerte n’existe pas encore, sélectionnez d’abord le bouton représentant des points de suspension (**...**) en regard de **Messages d’erreur/d’information**, et sélectionnez **Ajouter le module**.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-117">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="a5fe8-118">Dans le volet de propriété de droite, sous l’onglet **Données**, sélectionnez **Ajouter une source de données**, puis sélectionnez **Contenu**.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-118">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="a5fe8-119">Dans le champ **Texte entré**, entrez le texte du message de bienvenue.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-119">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="a5fe8-120">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment d’en-tête, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-120">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="a5fe8-121">Le message de bienvenue apparaît désormais en haut de chaque page du site qui utilise le fragment d’en-tête sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a5fe8-121">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5fe8-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a5fe8-122">Additional resources</span></span>

[<span data-ttu-id="a5fe8-123">Ajouter un logo</span><span class="sxs-lookup"><span data-stu-id="a5fe8-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="a5fe8-124">Sélectionner un thème pour le site</span><span class="sxs-lookup"><span data-stu-id="a5fe8-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="a5fe8-125">Utilisation de fichiers de remplacement CSS</span><span class="sxs-lookup"><span data-stu-id="a5fe8-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="a5fe8-126">Ajouter une icône de favori</span><span class="sxs-lookup"><span data-stu-id="a5fe8-126">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="a5fe8-127">Ajouter un avis de droits d’auteur</span><span class="sxs-lookup"><span data-stu-id="a5fe8-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="a5fe8-128">Ajouter des langues à votre site</span><span class="sxs-lookup"><span data-stu-id="a5fe8-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="a5fe8-129">Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="a5fe8-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
