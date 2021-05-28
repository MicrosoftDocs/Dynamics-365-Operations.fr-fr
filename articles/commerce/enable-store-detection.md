---
title: Activation de la détection du magasin selon l’emplacement
description: Cette rubrique décrit la procédure d’activation de la détection du magasin selon l’emplacement pour votre site Dynamics 365 Commerce.
author: brianshook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e26c3130914ebef5a63b79c477d7d5846fd5b71
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027598"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="305ff-103">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="305ff-103">Enable location-based store detection</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="305ff-104">Cette rubrique décrit la procédure d’activation de la détection du magasin selon l’emplacement pour votre site Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="305ff-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="305ff-105">La détection du magasin selon l’emplacement dans Commerce vous permet de fournir le contenu approprié de site aux clients, en fonction de leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="305ff-105">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="305ff-106">Lorsque la détection du magasin selon l’emplacement est activée, le service d’affichage de Commerce utilise les informations de pays/région de l’adresse IP du navigateur web du client pour diriger le client vers la meilleure configuration géographique de site disponible.</span><span class="sxs-lookup"><span data-stu-id="305ff-106">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="305ff-107">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="305ff-107">Privacy notice</span></span>

<span data-ttu-id="305ff-108">Si vous activez la fonction de détection du magasin selon l’emplacement, les informations du navigateur du client sont envoyées à un service d’emplacement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="305ff-108">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="305ff-109">Cette information est alors utilisée pour fournir le contenu du client approprié à l'emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="305ff-109">This information is then used to provide the customer content that is relevant to the customer's location.</span></span> <span data-ttu-id="305ff-110">Les informations envoyées à partir du navigateur et les informations basées sur l’emplacement renvoyées au client sont soumises à des politiques de conformité des cookies et de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="305ff-110">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="305ff-111">Activer la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="305ff-111">Turn on location-based store detection</span></span>

<span data-ttu-id="305ff-112">Pour activer la détection du magasin selon l’emplacement dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="305ff-112">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="305ff-113">Dans l’outil de création, accédez à votre site.</span><span class="sxs-lookup"><span data-stu-id="305ff-113">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="305ff-114">Dans le volet de navigation sur la gauche, sélectionnez **Gestion du site**.</span><span class="sxs-lookup"><span data-stu-id="305ff-114">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="305ff-115">Sélectionnez **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="305ff-115">Select **Site Settings**.</span></span>
1. <span data-ttu-id="305ff-116">Définissez l’option **Activer la détection du magasin selon l’emplacement** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="305ff-116">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="305ff-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="305ff-117">Additional resources</span></span>

[<span data-ttu-id="305ff-118">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="305ff-118">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="305ff-119">Déployer un nouveau client e-commerce</span><span class="sxs-lookup"><span data-stu-id="305ff-119">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="305ff-120">Créer un site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="305ff-120">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="305ff-121">Associer un site Dynamics 365 Commerce avec un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="305ff-121">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="305ff-122">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="305ff-122">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="305ff-123">Importer des redirections d’URL en bloc</span><span class="sxs-lookup"><span data-stu-id="305ff-123">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="305ff-124">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="305ff-124">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="305ff-125">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="305ff-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="305ff-126">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="305ff-126">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="305ff-127">Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="305ff-127">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
