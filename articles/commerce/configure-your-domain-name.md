---
title: Configuration du nom de domaine
description: Cette rubrique explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2ad9ca3aee21301ef6d830d7b29982a45cd53f60
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096818"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="5ee1f-103">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="5ee1f-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5ee1f-104">Cette rubrique explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5ee1f-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="5ee1f-105">Ajouter des domaines lors de l'initialisation du commerce électronique</span><span class="sxs-lookup"><span data-stu-id="5ee1f-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="5ee1f-106">Pour associer des domaines avec votre environnement de commerce électronique, initialisez le commerce électronique comme décrit dans [Déployer un nouveau site de commerce électronique](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="5ee1f-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="5ee1f-107">Lors de l'initialisation, vous êtes invité à fournir des informations qui seront utilisées pour mettre en service votre environnement de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="5ee1f-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="5ee1f-108">Dans le champ **Noms d'hôtes pris en charge**, ajoutez des domaines que vous comptez utiliser avec l'environnement.</span><span class="sxs-lookup"><span data-stu-id="5ee1f-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="5ee1f-109">Si vous avez plusieurs domaines, séparez-les par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="5ee1f-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="5ee1f-110">Ainsi, les domaines sont tous configurés dans tous les composants requis de commerce électronique, et ils sont prêts à être utilisés lorsque vous changez le trafic de votre réseau de diffusion de contenu (CDN) ou votre serveur web et que vous le pointez vers les serveurs frontaux de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="5ee1f-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="5ee1f-111">Ajouter des domaines après l'initialisation du commerce électronique</span><span class="sxs-lookup"><span data-stu-id="5ee1f-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="5ee1f-112">Pour associer de nouveaux domaines à votre environnement de commerce électronique après l'initialisation du commerce électronique, vous devez envoyer une demande de service.</span><span class="sxs-lookup"><span data-stu-id="5ee1f-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ee1f-113">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5ee1f-113">Additional resources</span></span>

[<span data-ttu-id="5ee1f-114">Déploiement d'un nouveau site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="5ee1f-114">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="5ee1f-115">Paramétrer un canal de magasin en ligne</span><span class="sxs-lookup"><span data-stu-id="5ee1f-115">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="5ee1f-116">Création d'un site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="5ee1f-116">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="5ee1f-117">Association d'un site en ligne avec un canal</span><span class="sxs-lookup"><span data-stu-id="5ee1f-117">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="5ee1f-118">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="5ee1f-118">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="5ee1f-119">Importer des redirections d'URL en bloc</span><span class="sxs-lookup"><span data-stu-id="5ee1f-119">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="5ee1f-120">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="5ee1f-120">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="5ee1f-121">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="5ee1f-121">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="5ee1f-122">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="5ee1f-122">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="5ee1f-123">Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="5ee1f-123">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="5ee1f-124">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="5ee1f-124">Enable location-based store detection</span></span>](enable-store-detection.md)
