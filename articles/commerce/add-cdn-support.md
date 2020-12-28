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
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0e888fca4a5401f1df6e61b10358489846ad4b0e
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517206"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="f958c-103">Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="f958c-103">Add support for a content delivery network (CDN)</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f958c-104">Cette rubrique décrit la procédure d’ajout d’un réseau de diffusion de contenu (CDN) à votre environnement Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f958c-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="f958c-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="f958c-105">Overview</span></span>

<span data-ttu-id="f958c-106">Lorsque vous paramétrez un environnement d'e-commerce dans Dynamics 365 Commerce, vous pouvez le configurer pour travailler avec votre service CDN.</span><span class="sxs-lookup"><span data-stu-id="f958c-106">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="f958c-107">Votre domaine personnalisé peut être activé lors de le processus de mise en service pour votre environnement d'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="f958c-107">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="f958c-108">Sinon, vous pouvez utiliser une demande de service pour le configurer une fois le processus de mise en service terminé.</span><span class="sxs-lookup"><span data-stu-id="f958c-108">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="f958c-109">Le processus de mise en service de l’environnement d'e-commerce génère un nom d’hôte associé à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="f958c-109">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="f958c-110">Ce nom d’hôte a le format suivant, où \<*e-commerce-tenant-name*\> est le nom de votre environnement :</span><span class="sxs-lookup"><span data-stu-id="f958c-110">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="f958c-111">&lt;nom-client-e-commerce&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="f958c-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="f958c-112">Le nom de l’hôte ou le point de terminaison généré lors de le processus de mise en service prend en charge un certificat SSL (Secure Sockets Layer) uniquement pour \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="f958c-112">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="f958c-113">Il ne prend pas en charge le protocole SSL pour les domaines personnalisés.</span><span class="sxs-lookup"><span data-stu-id="f958c-113">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="f958c-114">Par conséquent, vous devez arrêter SSL pour les domaines personnalisés dans votre CDN et transférer le trafic du CDN vers le nom d’hôte ou le point de terminaison que le commerce a généré.</span><span class="sxs-lookup"><span data-stu-id="f958c-114">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="f958c-115">En outre, les *statistiques* (fichiers Javascript ou de feuilles de style en cascade \[CSS\]) de Commerce sont fournis par le point de terminaison que Commerce a généré (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="f958c-115">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="f958c-116">Les statistiques peuvent être mises en cache uniquement si le nom d’hôte ou le point de terminaison que Commerce a généré est placé après le CDN.</span><span class="sxs-lookup"><span data-stu-id="f958c-116">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="f958c-117">Paramétrer SSL</span><span class="sxs-lookup"><span data-stu-id="f958c-117">Set up SSL</span></span>

<span data-ttu-id="f958c-118">Pour garantir que le protocole SSL est paramétré, et que ces statistiques sont mises en cache, vous devez configurer votre CDN afin qu’il soit associé au nom de l’hôte que Commerce a généré pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="f958c-118">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="f958c-119">Vous devez également mettre en cache le schéma suivant pour les statistiques uniquement :</span><span class="sxs-lookup"><span data-stu-id="f958c-119">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="f958c-120">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="f958c-120">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="f958c-121">Après avoir mis votre environnement Commerce en service avec le domaine personnalisé qui est fourni, ou après que vous ayez fourni le domaine personnalisé pour votre environnement à l’aide d’une requête de service, indiquez votre domaine personnalisé au nom d’hôte ou au point de terminaison que Commerce a généré.</span><span class="sxs-lookup"><span data-stu-id="f958c-121">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="f958c-122">Comme précédemment mentionné, le nom d’hôte ou le point de terminaison généré prend en charge un certificat SSL uniquement pour \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="f958c-122">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="f958c-123">Il ne prend pas en charge le protocole SSL pour les domaines personnalisés.</span><span class="sxs-lookup"><span data-stu-id="f958c-123">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="f958c-124">Services CDN</span><span class="sxs-lookup"><span data-stu-id="f958c-124">CDN services</span></span>

<span data-ttu-id="f958c-125">Tout service CDN peut être utilisé avec un environnement Commerce.</span><span class="sxs-lookup"><span data-stu-id="f958c-125">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="f958c-126">Voici deux exemples :</span><span class="sxs-lookup"><span data-stu-id="f958c-126">Here are two examples:</span></span>

- <span data-ttu-id="f958c-127">**Microsoft Azure Front Door Service** – La solution d’Azure CDN.</span><span class="sxs-lookup"><span data-stu-id="f958c-127">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="f958c-128">Pour plus d’informations sur Azure Front Door Service, voir la [Documentation Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="f958c-128">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="f958c-129">**Accélérateur dynamique de site Akamai** – Pour plus d’informations, voir [Accélérateur de site dynamique](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="f958c-129">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="f958c-130">Paramétrage CDN</span><span class="sxs-lookup"><span data-stu-id="f958c-130">CDN setup</span></span>

<span data-ttu-id="f958c-131">Le processus de paramétrage de CDN se compose de ces étapes générales :</span><span class="sxs-lookup"><span data-stu-id="f958c-131">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="f958c-132">Ajoutez un hôte frontal.</span><span class="sxs-lookup"><span data-stu-id="f958c-132">Add a front-end host.</span></span>
1. <span data-ttu-id="f958c-133">Configurez un regroupement principal.</span><span class="sxs-lookup"><span data-stu-id="f958c-133">Configure a backend pool.</span></span>
1. <span data-ttu-id="f958c-134">Paramétrez les règles d’acheminement et de mise en cache.</span><span class="sxs-lookup"><span data-stu-id="f958c-134">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="f958c-135">Ajoutez un hôte frontal</span><span class="sxs-lookup"><span data-stu-id="f958c-135">Add a front-end host</span></span>

<span data-ttu-id="f958c-136">Tout service CDN peut être utilisé, mais pour l’exemple dans cette rubrique, Azure Front Door Service est utilisé.</span><span class="sxs-lookup"><span data-stu-id="f958c-136">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="f958c-137">Pour plus d’informations sur la configuration du Azure Front Door Service, voir [Démarrage rapide : Créez une Front Door pour une application web global très disponible](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="f958c-137">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="f958c-138">Configurer un regroupement principal dans Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="f958c-138">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="f958c-139">Pour configurer un regroupement principal dans Azure Front Door Service, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f958c-139">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="f958c-140">Ajoutez **&lt;nom-client-ecom&gt;.commerce.dynamics.com** à un regroupement principal comme serveur personnalisé qui a un en-tête d’hôte principal vide.</span><span class="sxs-lookup"><span data-stu-id="f958c-140">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has an empty backend host header.</span></span>
1. <span data-ttu-id="f958c-141">Sous **Équilibrage de la charge**, laissez les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="f958c-141">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="f958c-142">L’illustration suivante présente la boîte de dialogue **Ajouter un regroupement principal** dans Azure Front Door Service avec le nom d’hôte principal entré.</span><span class="sxs-lookup"><span data-stu-id="f958c-142">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Boîte de dialogue Ajouter un regroupement principal](./media/CDN_BackendPool.png)

<span data-ttu-id="f958c-144">L’illustration suivante présente la boîte de dialogue **Ajouter un regroupement principal** dans Azure Front Door Service avec les valeurs d’équilibrage de charge par défaut.</span><span class="sxs-lookup"><span data-stu-id="f958c-144">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Boîte de dialogue Ajouter un regroupement principal](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="f958c-146">Paramétrer des règles dans Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="f958c-146">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="f958c-147">Pour paramétrer une règle d’acheminement dans Azure Front Door Service, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f958c-147">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="f958c-148">Ajoutez une règle d’acheminement.</span><span class="sxs-lookup"><span data-stu-id="f958c-148">Add a routing rule.</span></span>
1. <span data-ttu-id="f958c-149">Dans le champ **Nom**, entrez **par défaut**.</span><span class="sxs-lookup"><span data-stu-id="f958c-149">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="f958c-150">Dans le champ **Protocole accepté**, sélectionnez **HTTP et HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="f958c-150">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="f958c-151">Dans le champ **Hôtes frontaux**, entrez **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="f958c-151">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="f958c-152">Sous **Modèles à respecter**, dans le champ supérieur, entrez \**/\** _.</span><span class="sxs-lookup"><span data-stu-id="f958c-152">Under **Patterns to match**, in the upper field, enter \**/\** _.</span></span>
1. <span data-ttu-id="f958c-153">Sous **Détails de l’acheminement**, définissez l’option **Type d’acheminement** sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f958c-153">Under _\*Route Details\*\*, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="f958c-154">Dans le champ **Regroupement principal**, sélectionnez **ecom-principal**.</span><span class="sxs-lookup"><span data-stu-id="f958c-154">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="f958c-155">Dans le groupe de champ **Protocole de transfert**, sélectionnez l’option **Demande de mise en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="f958c-155">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="f958c-156">Définissez l’option **Réécriture de l’URL** sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="f958c-156">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="f958c-157">Définissez l’option **Mise en cache** sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="f958c-157">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="f958c-158">Pour paramétrer une règle de mise en cache dans Azure Front Door Service, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f958c-158">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="f958c-159">Ajoutez une règle de mise en cache.</span><span class="sxs-lookup"><span data-stu-id="f958c-159">Add a caching rule.</span></span>
1. <span data-ttu-id="f958c-160">Dans le champ **Nom**, entrez **statistiques**.</span><span class="sxs-lookup"><span data-stu-id="f958c-160">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="f958c-161">Dans le champ **Protocole accepté**, sélectionnez **HTTP et HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="f958c-161">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="f958c-162">Dans le champ **Hôtes frontaux**, entrez **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="f958c-162">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="f958c-163">Sous **Modèles à respecter**, dans le champ supérieur, entrez \**/\_msdyn365/\_scnr/\** _.</span><span class="sxs-lookup"><span data-stu-id="f958c-163">Under **Patterns to match**, in the upper field, \**/\_msdyn365/\_scnr/\** _.</span></span>
1. <span data-ttu-id="f958c-164">Sous **Détails de l’acheminement**, définissez l’option **Type d’acheminement** sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f958c-164">Under _\*Route Details\*\*, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="f958c-165">Dans le champ **Regroupement principal**, sélectionnez **ecom-principal**.</span><span class="sxs-lookup"><span data-stu-id="f958c-165">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="f958c-166">Dans le groupe de champ **Protocole de transfert**, sélectionnez l’option **Demande de mise en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="f958c-166">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="f958c-167">Définissez l’option **Réécriture de l’URL** sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="f958c-167">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="f958c-168">Définissez l’option **Mise en cache** sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="f958c-168">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="f958c-169">Dans le champ **Comportement de mise en cache de la chaîne de requête**, sélectionnez **Mettre en cache chaque URL unique**.</span><span class="sxs-lookup"><span data-stu-id="f958c-169">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="f958c-170">Dans le groupe de champ **Compression dynamique**, sélectionnez l’option **Activé**.</span><span class="sxs-lookup"><span data-stu-id="f958c-170">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="f958c-171">L’illustration suivante présente la boîte de dialogue **Ajouter une règle** à Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="f958c-171">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Boîte de dialogue Ajouter une règle](./media/CDN_CachingRule.png)

> [!WARNING]
> <span data-ttu-id="f958c-173">Si le domaine que vous utilisez est déjà actif et en service, créez un ticket de support à partir de la vignette **Support** dans [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) pour obtenir de l’aide pour vos prochaines étapes.</span><span class="sxs-lookup"><span data-stu-id="f958c-173">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="f958c-174">Pour plus d’informations, voir [Obtenir de l’aide sur les applications Finance and Operations ou Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="f958c-174">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="f958c-175">Si votre domaine est nouveau et n’est pas un domaine actif préexistant, vous pouvez ajouter votre domaine personnalisé à la configuration d’Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="f958c-175">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="f958c-176">Cela permet de rediriger le trafic web vers votre site via l’instance d’Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="f958c-176">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="f958c-177">Pour ajouter le domaine personnalisé (par exemple, `www.fabrikam.com`), vous devez configurer un nom canonique (CNAME) pour le domaine.</span><span class="sxs-lookup"><span data-stu-id="f958c-177">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="f958c-178">L’illustration suivante présente la boîte de dialogue **Configuration CNAME** à Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="f958c-178">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Boîte de dialogue Configuration CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="f958c-180">Vous pouvez utiliser Azure Front Door Service pour gérer le certificat, ou vous pouvez utiliser votre propre certificat pour le domaine personnalisé.</span><span class="sxs-lookup"><span data-stu-id="f958c-180">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="f958c-181">L’illustration suivante présente la boîte de dialogue **HTTPS domaine personnalisé** à Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="f958c-181">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Boîte de dialogue HTTPS domaine personnalisé](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="f958c-183">Pour obtenir des instructions détaillées sur l’ajout d’un domaine personnalisé à votre Azure Front Door, voir [Ajouter un domaine personnalisé à votre Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="f958c-183">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="f958c-184">Votre CDN doit être maintenant correctement configuré de sorte qu’il puisse être utilisé avec votre site Commerce.</span><span class="sxs-lookup"><span data-stu-id="f958c-184">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f958c-185">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f958c-185">Additional resources</span></span>

[<span data-ttu-id="f958c-186">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="f958c-186">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="f958c-187">Déployer un nouveau client e-commerce</span><span class="sxs-lookup"><span data-stu-id="f958c-187">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="f958c-188">Créer un site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="f958c-188">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="f958c-189">Associer un site Dynamics 365 Commerce avec un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="f958c-189">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="f958c-190">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="f958c-190">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="f958c-191">Importer des redirections d’URL en bloc</span><span class="sxs-lookup"><span data-stu-id="f958c-191">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="f958c-192">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="f958c-192">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="f958c-193">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="f958c-193">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="f958c-194">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="f958c-194">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="f958c-195">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="f958c-195">Enable location-based store detection</span></span>](enable-store-detection.md)
