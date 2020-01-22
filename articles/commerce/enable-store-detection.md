---
title: Activation de la détection du magasin selon l’emplacement
description: Cette rubrique décrit la procédure d'activation de la détection du magasin selon l’emplacement pour votre site Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c5fb59a9798e2cddfb75b71235ee7754e54b0e28
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945767"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="4e577-103">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="4e577-103">Enable location-based store detection</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4e577-104">Cette rubrique décrit la procédure d'activation de la détection du magasin selon l’emplacement pour votre site Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e577-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="4e577-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="4e577-105">Overview</span></span>

<span data-ttu-id="4e577-106">La détection du magasin selon l’emplacement dans Commerce vous permet de fournir le contenu approprié de site aux clients, en fonction de leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="4e577-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="4e577-107">Lorsque la détection du magasin selon l’emplacement est activée, le service d'affichage de Commerce utilise les informations de pays/région de l'adresse IP du navigateur web du client pour diriger le client vers la meilleure configuration géographique de site disponible.</span><span class="sxs-lookup"><span data-stu-id="4e577-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="4e577-108">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="4e577-108">Privacy notice</span></span>

<span data-ttu-id="4e577-109">Si vous activez la fonction de détection du magasin selon l’emplacement, les informations du navigateur du client sont envoyées à un service d'emplacement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e577-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="4e577-110">Cette information est alors utilisée pour fournir le contenu du client approprié à son emplacement.</span><span class="sxs-lookup"><span data-stu-id="4e577-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="4e577-111">Les informations envoyées à partir du navigateur et les informations basées sur l’emplacement renvoyées au client sont soumises à des politiques de conformité des cookies et de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="4e577-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="4e577-112">Activer la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="4e577-112">Turn on location-based store detection</span></span>

<span data-ttu-id="4e577-113">Pour activer la détection du magasin selon l’emplacement dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="4e577-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="4e577-114">Dans l'outil de création, accédez à votre site.</span><span class="sxs-lookup"><span data-stu-id="4e577-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="4e577-115">Dans le volet de navigation sur la gauche, sélectionnez **Gestion du site**.</span><span class="sxs-lookup"><span data-stu-id="4e577-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="4e577-116">Sélectionnez **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="4e577-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="4e577-117">Définissez l'option **Activer la détection du magasin selon l’emplacement** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="4e577-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4e577-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4e577-118">Additional resources</span></span>

[<span data-ttu-id="4e577-119">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="4e577-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="4e577-120">Déploiement d'un nouveau site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="4e577-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="4e577-121">Création d'un site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="4e577-121">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="4e577-122">Association d'un site en ligne avec un canal</span><span class="sxs-lookup"><span data-stu-id="4e577-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="4e577-123">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="4e577-123">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="4e577-124">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="4e577-124">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="4e577-125">Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="4e577-125">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
