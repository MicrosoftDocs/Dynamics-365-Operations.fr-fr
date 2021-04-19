---
title: Options de mise en œuvre d’un réseau de diffusion de contenu
description: Cette rubrique passe en revue les différentes options d’implémentation d’un réseau de diffusion de contenu (CDN) pouvant être utilisées avec les environnements Microsoft Dynamics 365 Commerce. Ces options incluent des instances Azure Front Door natives fournies par Commerce et des instances Azure Front Door appartenant au client.
author: BrianShook
ms.date: 03/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9e98cf81f13b9181059bc96b95ac277a088311ea
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800709"
---
# <a name="content-delivery-network-implementation-options"></a><span data-ttu-id="a3dfd-104">Options de mise en œuvre d’un réseau de diffusion de contenu</span><span class="sxs-lookup"><span data-stu-id="a3dfd-104">Content delivery network implementation options</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a3dfd-105">Cette rubrique passe en revue les différentes options d’implémentation d’un réseau de diffusion de contenu (CDN) pouvant être utilisées avec les environnements Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-105">This topic reviews the different options for content delivery network (CDN) implementation that can be used with Microsoft Dynamics 365 Commerce environments.</span></span> <span data-ttu-id="a3dfd-106">Ces options incluent des instances Azure Front Door natives fournies par Commerce et des instances Azure Front Door appartenant au client.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-106">These options include native, Commerce-provided instances of Azure Front Door and customer-owned instances of Azure Front Door.</span></span>

<span data-ttu-id="a3dfd-107">Les clients Commerce ont plusieurs options lorsqu’ils doivent choisir quel service CDN utiliser avec leur environnement Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-107">Commerce customers have several options when they are considering which CDN service to use with their Commerce environment.</span></span> <span data-ttu-id="a3dfd-108">Commerce est lancé avec la prise en charge Azure Front Door de base, qui couvre l’hébergement de base et les exigences de domaine personnalisé.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-108">Commerce is released with basic Azure Front Door support that covers basic hosting and custom domain requirements.</span></span> <span data-ttu-id="a3dfd-109">Pour les entreprises qui souhaitent plus de contrôle et des capacités de sécurité plus spécifiques, par exemple un pare-feu d’application web (WAF), la meilleure option peut être d’utiliser une instance Azure Front Door appartenant au client ou un service CDN externe.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-109">For companies that want more control and more specific security abilities, such as a web application firewall (WAF), the best option might be to use either a customer-owned instance of Azure Front Door or an external CDN service.</span></span>

<span data-ttu-id="a3dfd-110">Les trois options d’implémentation CDN suivantes peuvent être utilisées avec les environnements Commerce :</span><span class="sxs-lookup"><span data-stu-id="a3dfd-110">The following three CDN implementation options can be used with Commerce environments:</span></span>

- <span data-ttu-id="a3dfd-111">L’instance Azure Front Door fournie par Commerce</span><span class="sxs-lookup"><span data-stu-id="a3dfd-111">The Commerce-provided instance of Azure Front Door</span></span>
- <span data-ttu-id="a3dfd-112">Une instance Azure Front Door appartenant au client (pour un contrôle accru et des fonctionnalités de sécurité supplémentaires)</span><span class="sxs-lookup"><span data-stu-id="a3dfd-112">A customer-owned instance of Azure Front Door (for increased control and additional security features)</span></span>
- <span data-ttu-id="a3dfd-113">Un service CDN externe</span><span class="sxs-lookup"><span data-stu-id="a3dfd-113">An external CDN service</span></span>

<span data-ttu-id="a3dfd-114">Les trois options d’implémentation CDN fournissent uniquement du contenu HTML dynamique de domaines personnalisés.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-114">All three CDN implementation options deliver only dynamic HTML content from custom domains.</span></span> <span data-ttu-id="a3dfd-115">Commerce gère automatiquement tous les contenus JavaScript, les feuilles de style en cascade (CSS), les images, les vidéos et d’autres contenus statiques via des CDN gérés par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-115">Commerce automatically handles all JavaScript, Cascading Style Sheets (CSS), images, video, and other static content through Microsoft-managed CDNs.</span></span> <span data-ttu-id="a3dfd-116">L’option que vous choisissez détermine les capacités opérationnelles, les capacités de contrôle et les capacités de sécurité supplémentaires disponibles.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-116">The option that you choose determines the operational capabilities, control capabilities, and additional security capabilities that are available.</span></span>

<span data-ttu-id="a3dfd-117">L’illustration suivante présente une vue d’ensemble de l’architecture de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-117">The following illustration shows an overview of the Commerce architecture.</span></span>

![Présentation de l’architecture de Commerce](media/Commerce_CDN-Option_ComparisonModels.png)

<span data-ttu-id="a3dfd-119">Pour plus d’informations sur la configuration d’une instance Azure Front Door pour votre site Commerce, consultez [Ajouter la prise en charge d’un CDN](add-cdn-support.md).</span><span class="sxs-lookup"><span data-stu-id="a3dfd-119">For more information about how to set up an instance of Azure Front Door for your Commerce site, see [Add CDN Support](add-cdn-support.md).</span></span>

## <a name="use-the-commerce-provided-azure-front-door-instance"></a><span data-ttu-id="a3dfd-120">Utiliser l’instance Azure Front Door fournie par Commerce</span><span class="sxs-lookup"><span data-stu-id="a3dfd-120">Use the Commerce-provided Azure Front Door instance</span></span>

<span data-ttu-id="a3dfd-121">Le tableau suivant répertorie les avantages et les inconvénients de l’utilisation de l’instance Azure Front Door fournie par Commerce pour gérer les points de terminaison de contenu.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-121">The following table lists the pros and cons of using the Commerce-provided instance of Azure Front Door to manage content endpoints.</span></span>

| <span data-ttu-id="a3dfd-122">Avantages</span><span class="sxs-lookup"><span data-stu-id="a3dfd-122">Pros</span></span> | <span data-ttu-id="a3dfd-123">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="a3dfd-123">Cons</span></span> |
|------|------|
| <ul><li><span data-ttu-id="a3dfd-124">L’instance est incluse dans le coût de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-124">The instance is included in the Commerce cost.</span></span></li><li><span data-ttu-id="a3dfd-125">Étant donné que l’instance est gérée par l’équipe de Commerce, moins de maintenance est requise et des étapes de configuration sont partagées.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-125">Because the instance is managed by the Commerce team, less maintenance is required, and there are shared setup steps.</span></span></li><li><span data-ttu-id="a3dfd-126">L’infrastructure hébergée par Azure est évolutive, sécurisée et fiable.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-126">The Azure-hosted infrastructure is scalable, secure, and reliable.</span></span></li><li><span data-ttu-id="a3dfd-127">Le certificat SSL (Secure Sockets Layer) nécessite une configuration unique et est automatiquement renouvelé.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-127">The Secure Sockets Layer (SSL) certificate requires a one-time setup and is automatically renewed.</span></span></li><li><span data-ttu-id="a3dfd-128">L’instance est surveillée par l’équipe Commerce qui recherche les erreurs et les anomalies.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-128">The instance is monitored for errors and anomalies by the Commerce team.</span></span></li></ul> | <ul><li><span data-ttu-id="a3dfd-129">Aucun WAF n’est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-129">A WAF isn't supported.</span></span></li><li><span data-ttu-id="a3dfd-130">Il n’y a pas de personnalisations ou d’ajustements de paramètres spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-130">There are no specific customizations or setting adjustments.</span></span></li><li><span data-ttu-id="a3dfd-131">Les mises à jour ou les modifications de l’instance dépendent de l’équipe Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-131">The instance depends on the Commerce team for updates or changes.</span></span></li><li><span data-ttu-id="a3dfd-132">Une instance Azure Front Door distincte est requise pour les domaines apex, et un travail supplémentaire est requis pour intégrer les domaines apex avec Azure DNS.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-132">A separate Azure Front Door instance is required for apex domains, and extra work is required to integrate apex domains with Azure DNS.</span></span></li><li><span data-ttu-id="a3dfd-133">Aucune télémétrie sur les réponses par seconde (RPS) ou le taux d’erreur n’est fournie au client.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-133">No telemetry about responses per second (RPS) or the error rate is provided to the customer.</span></span></li></ul> |

<span data-ttu-id="a3dfd-134">L’illustration suivante montre l’architecture de l’instance Azure Front Door fournie par Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-134">The following illustration shows the architecture of the Commerce-provided Azure Front Door instance.</span></span>

![Instance Azure Front Door fournie par Commerce](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a><span data-ttu-id="a3dfd-136">Utiliser une instance Azure Front Door appartenant au client</span><span class="sxs-lookup"><span data-stu-id="a3dfd-136">Use a customer-owned Azure Front Door instance</span></span>

<span data-ttu-id="a3dfd-137">Le tableau suivant répertorie les avantages et les inconvénients de l’utilisation d’une instance Azure Front Door appartenant au client pour gérer les points de terminaison de contenu.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-137">The following table lists the pros and cons of using a customer-owned instance of Azure Front Door to manage content endpoints.</span></span>

| <span data-ttu-id="a3dfd-138">Avantages</span><span class="sxs-lookup"><span data-stu-id="a3dfd-138">Pros</span></span> | <span data-ttu-id="a3dfd-139">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="a3dfd-139">Cons</span></span> |
|------|------|
| <ul><li><span data-ttu-id="a3dfd-140">La configuration est sécurisée et facile à gérer.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-140">Setup is secure and easy to manage.</span></span></li><li><span data-ttu-id="a3dfd-141">L’infrastructure hébergée par Azure est évolutive, sécurisée et fiable.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-141">The Azure-hosted infrastructure is scalable, secure, and reliable.</span></span></li><li><span data-ttu-id="a3dfd-142">L’instance permet une intégration WAF et des contrôles de règles précis pour une sécurité de meilleure qualité, spécialement adaptée à votre site.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-142">The instance allows for WAF integration and granular rule controls for finer-grade security that is tuned specifically for your site.</span></span></li><li><span data-ttu-id="a3dfd-143">L’instance permet un contrôle plus précis des certificats SSL (appartenant au client et gérés par Azure Front Door) et la liaison de domaine.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-143">The instance allows for finer control of SSL certificates (both customer-owned and Azure Front Door–managed) and domain linking.</span></span></li><li><span data-ttu-id="a3dfd-144">L’instance offre une solution de domaine apex si elle est directement associée à Azure DNS.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-144">The instance offers an apex domain solution if it's paired directly with Azure DNS.</span></span></li><li><span data-ttu-id="a3dfd-145">La télémétrie et les alertes sont fournies.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-145">Telemetry and alerting are provided.</span></span></li><li><span data-ttu-id="a3dfd-146">Le certificat SSL nécessite une configuration unique et est automatiquement renouvelé.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-146">The SSL certificate requires a one-time setup and is automatically renewed.</span></span></li></ul> | <ul><li><span data-ttu-id="a3dfd-147">L’instance est autogérée.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-147">The instance is self-managed.</span></span></li><li><span data-ttu-id="a3dfd-148">Une période initiale d’acquisition des connaissances est requise.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-148">Initial knowledge ramp-up is required.</span></span></li></ul> |

<span data-ttu-id="a3dfd-149">L’illustration suivante montre une infrastructure Commerce qui comprend une instance Azure Front Door appartenant au client.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-149">The following illustration shows a Commerce infrastructure that includes a customer-owned Azure Front Door instance.</span></span>

![Infrastructure Commerce qui comprend une instance Azure Front Door appartenant au client](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a><span data-ttu-id="a3dfd-151">Utiliser un service CDN externe</span><span class="sxs-lookup"><span data-stu-id="a3dfd-151">Use an external CDN service</span></span>

<span data-ttu-id="a3dfd-152">Le tableau suivant répertorie les avantages et les inconvénients de l’utilisation d’un service CDN externe pour gérer les points de terminaison de contenu.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-152">The following table lists the pros and cons of using an external CDN service to manage content endpoints.</span></span>

| <span data-ttu-id="a3dfd-153">Avantages</span><span class="sxs-lookup"><span data-stu-id="a3dfd-153">Pros</span></span> | <span data-ttu-id="a3dfd-154">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="a3dfd-154">Cons</span></span> |
|------|------|
| <ul><li><span data-ttu-id="a3dfd-155">Cette option est utile lorsque le domaine existant est déjà hébergé sur un CDN externe.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-155">This option is useful when the existing domain is already hosted on an external CDN.</span></span></li><li><span data-ttu-id="a3dfd-156">Les CDN concurrents (par exemple, Akamai) peuvent avoir plus de capacités WAF.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-156">Competitor CDNs (for example, Akamai) might have more WAF capabilities.</span></span></li></ul> | <ul><li><span data-ttu-id="a3dfd-157">Un contrat séparé est requis et des coûts supplémentaires s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-157">A separate contract and additional costing are required.</span></span></li><li><span data-ttu-id="a3dfd-158">SSL peut entraîner des coûts supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-158">SSL might incur additional costs.</span></span></li><li><span data-ttu-id="a3dfd-159">Étant donné que le service est distinct de la structure cloud Azure, une infrastructure supplémentaire doit être gérée.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-159">Because the service is separate from the Azure cloud structure, additional infrastructure must be managed.</span></span></li><li><span data-ttu-id="a3dfd-160">Le service peut nécessiter des investissements en temps plus longs pour la configuration des points de terminaison et de la sécurité.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-160">The service might require longer time investments in endpoint and security setup.</span></span></li><li><span data-ttu-id="a3dfd-161">Les service est autogéré.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-161">The service is self-managed.</span></span></li><li><span data-ttu-id="a3dfd-162">Les service est autocontrôlé.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-162">The service is self-monitored.</span></span></li></ul> |

<span data-ttu-id="a3dfd-163">L’illustration suivante montre une infrastructure Commerce qui comprend un service CDN externe.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-163">The following illustration shows a Commerce infrastructure that includes an external CDN service.</span></span>

![Infrastructure Commerce qui comprend un service CDN externe](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a><span data-ttu-id="a3dfd-165">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a3dfd-165">Additional resources</span></span>

[<span data-ttu-id="a3dfd-166">Ajouter la prise en charge d’un réseau de distribution de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="a3dfd-166">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)