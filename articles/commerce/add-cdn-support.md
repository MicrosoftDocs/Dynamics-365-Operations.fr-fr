---
title: Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)
description: Cette rubrique décrit la procédure d’ajout d’un réseau de diffusion de contenu (CDN) à votre environnement Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d653b072eca134c765a5db5659b228648fc13c4a
ms.sourcegitcommit: 3fe4d9a33447aa8a62d704fbbf18aeb9cb667baa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5582717"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="6aca6-103">Ajouter la prise en charge d’un réseau de distribution de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="6aca6-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6aca6-104">Cette rubrique décrit la procédure d’ajout d’un réseau de diffusion de contenu (CDN) à votre environnement Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6aca6-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="6aca6-105">Lorsque vous paramétrez un environnement d'e-commerce dans Dynamics 365 Commerce, vous pouvez le configurer pour travailler avec votre service CDN.</span><span class="sxs-lookup"><span data-stu-id="6aca6-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="6aca6-106">Votre domaine personnalisé peut être activé lors de le processus de mise en service pour votre environnement d'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="6aca6-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="6aca6-107">Sinon, vous pouvez utiliser une demande de service pour le configurer une fois le processus de mise en service terminé.</span><span class="sxs-lookup"><span data-stu-id="6aca6-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="6aca6-108">Le processus de mise en service de l’environnement d'e-commerce génère un nom d’hôte associé à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="6aca6-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="6aca6-109">Ce nom d’hôte a le format suivant, où \<*e-commerce-tenant-name*\> est le nom de votre environnement :</span><span class="sxs-lookup"><span data-stu-id="6aca6-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="6aca6-110">&lt;nom-client-e-commerce&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="6aca6-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="6aca6-111">Le nom de l’hôte ou le point de terminaison généré lors de le processus de mise en service prend en charge un certificat SSL (Secure Sockets Layer) uniquement pour \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="6aca6-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="6aca6-112">Il ne prend pas en charge le protocole SSL pour les domaines personnalisés.</span><span class="sxs-lookup"><span data-stu-id="6aca6-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="6aca6-113">Par conséquent, vous devez arrêter SSL pour les domaines personnalisés dans votre CDN et transférer le trafic du CDN vers le nom d’hôte ou le point de terminaison que le commerce a généré.</span><span class="sxs-lookup"><span data-stu-id="6aca6-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="6aca6-114">En outre, les *statistiques* (fichiers Javascript ou de feuilles de style en cascade \[CSS\]) de Commerce sont fournis par le point de terminaison que Commerce a généré (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="6aca6-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="6aca6-115">Les statistiques peuvent être mises en cache uniquement si le nom d’hôte ou le point de terminaison que Commerce a généré est placé après le CDN.</span><span class="sxs-lookup"><span data-stu-id="6aca6-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="6aca6-116">Paramétrer SSL</span><span class="sxs-lookup"><span data-stu-id="6aca6-116">Set up SSL</span></span>

<span data-ttu-id="6aca6-117">Pour garantir que le protocole SSL est paramétré, et que ces statistiques sont mises en cache, vous devez configurer votre CDN afin qu’il soit associé au nom de l’hôte que Commerce a généré pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="6aca6-117">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="6aca6-118">Vous devez également mettre en cache le schéma suivant pour les statistiques uniquement :</span><span class="sxs-lookup"><span data-stu-id="6aca6-118">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="6aca6-119">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="6aca6-119">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="6aca6-120">Après avoir mis votre environnement Commerce en service avec le domaine personnalisé qui est fourni, ou après que vous ayez fourni le domaine personnalisé pour votre environnement à l’aide d’une requête de service, indiquez votre domaine personnalisé au nom d’hôte ou au point de terminaison que Commerce a généré.</span><span class="sxs-lookup"><span data-stu-id="6aca6-120">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="6aca6-121">Comme précédemment mentionné, le nom d’hôte ou le point de terminaison généré prend en charge un certificat SSL uniquement pour \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="6aca6-121">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="6aca6-122">Il ne prend pas en charge le protocole SSL pour les domaines personnalisés.</span><span class="sxs-lookup"><span data-stu-id="6aca6-122">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="6aca6-123">Services CDN</span><span class="sxs-lookup"><span data-stu-id="6aca6-123">CDN services</span></span>

<span data-ttu-id="6aca6-124">Tout service CDN peut être utilisé avec un environnement Commerce.</span><span class="sxs-lookup"><span data-stu-id="6aca6-124">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="6aca6-125">Voici deux exemples :</span><span class="sxs-lookup"><span data-stu-id="6aca6-125">Here are two examples:</span></span>

- <span data-ttu-id="6aca6-126">**Microsoft Azure Front Door Service** – La solution d’Azure CDN.</span><span class="sxs-lookup"><span data-stu-id="6aca6-126">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="6aca6-127">Pour plus d’informations sur Azure Front Door Service, voir la [Documentation Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="6aca6-127">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="6aca6-128">**Accélérateur dynamique de site Akamai** – Pour plus d’informations, voir [Accélérateur de site dynamique](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="6aca6-128">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="6aca6-129">Paramétrage CDN</span><span class="sxs-lookup"><span data-stu-id="6aca6-129">CDN setup</span></span>

<span data-ttu-id="6aca6-130">Le processus de paramétrage de CDN se compose de ces étapes générales :</span><span class="sxs-lookup"><span data-stu-id="6aca6-130">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="6aca6-131">Ajoutez un hôte frontal.</span><span class="sxs-lookup"><span data-stu-id="6aca6-131">Add a front-end host.</span></span>
1. <span data-ttu-id="6aca6-132">Configurez un regroupement principal.</span><span class="sxs-lookup"><span data-stu-id="6aca6-132">Configure a backend pool.</span></span>
1. <span data-ttu-id="6aca6-133">Paramétrez les règles d’acheminement et de mise en cache.</span><span class="sxs-lookup"><span data-stu-id="6aca6-133">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="6aca6-134">Ajoutez un hôte frontal</span><span class="sxs-lookup"><span data-stu-id="6aca6-134">Add a front-end host</span></span>

<span data-ttu-id="6aca6-135">Tout service CDN peut être utilisé, mais pour l’exemple dans cette rubrique, Azure Front Door Service est utilisé.</span><span class="sxs-lookup"><span data-stu-id="6aca6-135">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="6aca6-136">Pour plus d’informations sur la configuration du Azure Front Door Service, voir [Démarrage rapide : Créez une Front Door pour une application web global très disponible](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="6aca6-136">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="6aca6-137">Configurer un regroupement principal dans Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="6aca6-137">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="6aca6-138">Pour configurer un regroupement principal dans Azure Front Door Service, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6aca6-138">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="6aca6-139">Ajoutez **&lt;nom-client-ecom&gt;.commerce.dynamics.com** à un regroupement principal comme serveur personnalisé qui a un en-tête d’hôte principal vide.</span><span class="sxs-lookup"><span data-stu-id="6aca6-139">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has an empty backend host header.</span></span>
1. <span data-ttu-id="6aca6-140">Sous **Équilibrage de la charge**, laissez les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="6aca6-140">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="6aca6-141">L’illustration suivante présente la boîte de dialogue **Ajouter un regroupement principal** dans Azure Front Door Service avec le nom d’hôte principal entré.</span><span class="sxs-lookup"><span data-stu-id="6aca6-141">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Boîte de dialogue Ajouter un regroupement principal](./media/CDN_BackendPool.png)

<span data-ttu-id="6aca6-143">L’illustration suivante présente la boîte de dialogue **Ajouter un regroupement principal** dans Azure Front Door Service avec les valeurs d’équilibrage de charge par défaut.</span><span class="sxs-lookup"><span data-stu-id="6aca6-143">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Boîte de dialogue Ajouter un regroupement principal](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="6aca6-145">Paramétrer des règles dans Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="6aca6-145">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="6aca6-146">Pour paramétrer une règle d’acheminement dans Azure Front Door Service, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6aca6-146">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="6aca6-147">Ajoutez une règle d’acheminement.</span><span class="sxs-lookup"><span data-stu-id="6aca6-147">Add a routing rule.</span></span>
1. <span data-ttu-id="6aca6-148">Dans le champ **Nom**, entrez **par défaut**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-148">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="6aca6-149">Dans le champ **Protocole accepté**, sélectionnez **HTTP et HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-149">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="6aca6-150">Dans le champ **Hôtes frontaux**, entrez **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-150">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="6aca6-151">Sous **Modèles à respecter**, dans le champ supérieur, entrez **/\***.</span><span class="sxs-lookup"><span data-stu-id="6aca6-151">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="6aca6-152">Sous **Détails de l’acheminement**, définissez l’option **Type d’acheminement** sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-152">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="6aca6-153">Dans le champ **Regroupement principal**, sélectionnez **ecom-principal**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-153">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="6aca6-154">Dans le groupe de champ **Protocole de transfert**, sélectionnez l’option **Demande de mise en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-154">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="6aca6-155">Définissez l’option **Réécriture de l’URL** sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-155">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="6aca6-156">Définissez l’option **Mise en cache** sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-156">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="6aca6-157">Pour paramétrer une règle de mise en cache dans Azure Front Door Service, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6aca6-157">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="6aca6-158">Ajoutez une règle de mise en cache.</span><span class="sxs-lookup"><span data-stu-id="6aca6-158">Add a caching rule.</span></span>
1. <span data-ttu-id="6aca6-159">Dans le champ **Nom**, entrez **statistiques**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-159">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="6aca6-160">Dans le champ **Protocole accepté**, sélectionnez **HTTP et HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-160">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="6aca6-161">Dans le champ **Hôtes frontaux**, entrez **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-161">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="6aca6-162">Sous **Modèles à respecter**, dans le champ supérieur, entrez **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="6aca6-162">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="6aca6-163">Sous **Détails de l’acheminement**, définissez l’option **Type d’acheminement** sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-163">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="6aca6-164">Dans le champ **Regroupement principal**, sélectionnez **ecom-principal**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-164">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="6aca6-165">Dans le groupe de champ **Protocole de transfert**, sélectionnez l’option **Demande de mise en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-165">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="6aca6-166">Définissez l’option **Réécriture de l’URL** sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-166">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="6aca6-167">Définissez l’option **Mise en cache** sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-167">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="6aca6-168">Dans le champ **Comportement de mise en cache de la chaîne de requête**, sélectionnez **Mettre en cache chaque URL unique**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-168">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="6aca6-169">Dans le groupe de champ **Compression dynamique**, sélectionnez l’option **Activé**.</span><span class="sxs-lookup"><span data-stu-id="6aca6-169">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="6aca6-170">L’illustration suivante présente la boîte de dialogue **Ajouter une règle** à Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="6aca6-170">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Boîte de dialogue Ajouter une règle](./media/CDN_CachingRule.png)

> [!WARNING]
> <span data-ttu-id="6aca6-172">Si le domaine que vous utilisez est déjà actif et en service, créez un ticket de support à partir de la vignette **Support** dans [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) pour obtenir de l’aide pour vos prochaines étapes.</span><span class="sxs-lookup"><span data-stu-id="6aca6-172">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="6aca6-173">Pour plus d’informations, voir [Obtenir de l’aide sur les applications Finance and Operations ou Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="6aca6-173">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="6aca6-174">Si votre domaine est nouveau et n’est pas un domaine actif préexistant, vous pouvez ajouter votre domaine personnalisé à la configuration d’Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="6aca6-174">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="6aca6-175">Cela permet de rediriger le trafic web vers votre site via l’instance d’Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="6aca6-175">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="6aca6-176">Pour ajouter le domaine personnalisé (par exemple, `www.fabrikam.com`), vous devez configurer un nom canonique (CNAME) pour le domaine.</span><span class="sxs-lookup"><span data-stu-id="6aca6-176">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="6aca6-177">L’illustration suivante présente la boîte de dialogue **Configuration CNAME** à Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="6aca6-177">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Boîte de dialogue Configuration CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="6aca6-179">Vous pouvez utiliser Azure Front Door Service pour gérer le certificat, ou vous pouvez utiliser votre propre certificat pour le domaine personnalisé.</span><span class="sxs-lookup"><span data-stu-id="6aca6-179">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="6aca6-180">L’illustration suivante présente la boîte de dialogue **HTTPS domaine personnalisé** à Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="6aca6-180">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Boîte de dialogue HTTPS domaine personnalisé](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="6aca6-182">Pour obtenir des instructions détaillées sur l’ajout d’un domaine personnalisé à votre Azure Front Door, voir [Ajouter un domaine personnalisé à votre Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="6aca6-182">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="6aca6-183">Votre CDN doit être maintenant correctement configuré de sorte qu’il puisse être utilisé avec votre site Commerce.</span><span class="sxs-lookup"><span data-stu-id="6aca6-183">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6aca6-184">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6aca6-184">Additional resources</span></span>

[<span data-ttu-id="6aca6-185">Options de mise en œuvre d’un réseau de diffusion de contenu</span><span class="sxs-lookup"><span data-stu-id="6aca6-185">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
