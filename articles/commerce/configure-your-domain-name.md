---
title: Configuration du nom de domaine
description: Cette rubrique explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d3df563b62b40970509340802a09bb36dda14777
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000998"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="050d1-103">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="050d1-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="050d1-104">Cette rubrique explique comment configurer un nom de domaine pour un site de commerce électronique Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="050d1-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="050d1-105">Ajouter des domaines lors de l'initialisation de l'e-commerce</span><span class="sxs-lookup"><span data-stu-id="050d1-105">Add domains during e-commerce initialization</span></span>

<span data-ttu-id="050d1-106">Pour associer des domaines avec votre environnement d'e-commerce Dynamics 365 Commerce, initialisez l'e-commerce comme décrit dans [Déployer un nouveau site d'e-commerce](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="050d1-106">To associate domains with your Dynamics 365 Commerce e-commerce environment, initialize e-commerce as described in [Deploy a new e-commerce tenant](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="050d1-107">Lors de l'initialisation, vous êtes invité à fournir des informations qui seront utilisées pour mettre en service votre environnement d'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="050d1-107">During initialization, you're asked to provide information that will be used to provision your e-commerce environment.</span></span> <span data-ttu-id="050d1-108">Dans le champ **Noms d'hôtes pris en charge**, ajoutez des domaines que vous comptez utiliser avec l'environnement.</span><span class="sxs-lookup"><span data-stu-id="050d1-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="050d1-109">Si vous avez plusieurs domaines, séparez-les par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="050d1-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="050d1-110">Ainsi, les domaines sont tous configurés dans tous les composants requis d'e-commerce, et ils sont prêts à être utilisés lorsque vous changez le trafic de votre réseau de diffusion de contenu (CDN) ou votre serveur web et que vous le pointez vers les serveurs frontaux d'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="050d1-110">In this way, the domains are configured in all the required Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="050d1-111">Ajouter des domaines après l'initialisation de l'e-commerce</span><span class="sxs-lookup"><span data-stu-id="050d1-111">Add domains after e-commerce initialization</span></span>

<span data-ttu-id="050d1-112">Pour associer de nouveaux domaines à votre environnement d'e-commerce après l'initialisation de l'e-commerce, vous devez envoyer une demande de service.</span><span class="sxs-lookup"><span data-stu-id="050d1-112">To associate new domains with your e-commerce environment after e-commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="050d1-113">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="050d1-113">Additional resources</span></span>

[<span data-ttu-id="050d1-114">Déployer un nouveau client e-commerce</span><span class="sxs-lookup"><span data-stu-id="050d1-114">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="050d1-115">Créer un site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="050d1-115">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="050d1-116">Associer un site Dynamics 365 Commerce avec un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="050d1-116">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="050d1-117">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="050d1-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="050d1-118">Importer des redirections d’URL en bloc</span><span class="sxs-lookup"><span data-stu-id="050d1-118">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="050d1-119">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="050d1-119">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="050d1-120">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="050d1-120">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="050d1-121">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="050d1-121">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="050d1-122">Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="050d1-122">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="050d1-123">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="050d1-123">Enable location-based store detection</span></span>](enable-store-detection.md)
