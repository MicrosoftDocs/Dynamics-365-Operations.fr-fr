---
title: Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)
description: Cette rubrique décrit la procédure d’ajout d’un réseau de diffusion de contenu (CDN) à votre environnement Microsoft Dynamics 365 Commerce.
author: brianshook
ms.date: 03/17/2021
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
ms.openlocfilehash: 59277323e0995f59d3a451395a038fa3708274eb
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936828"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Ajouter la prise en charge d’un réseau de distribution de contenu (CDN)

[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure d’ajout d’un réseau de diffusion de contenu (CDN) à votre environnement Microsoft Dynamics 365 Commerce.

Lorsque vous paramétrez un environnement d’e-commerce dans Dynamics 365 Commerce, vous pouvez le configurer pour travailler avec votre service CDN. 

Votre domaine personnalisé peut être activé lors de le processus de mise en service pour votre environnement d’e-commerce. Sinon, vous pouvez utiliser une demande de service pour le configurer une fois le processus de mise en service terminé. Le processus de mise en service de l’environnement d’e-commerce génère un nom d’hôte associé à l’environnement. Ce nom d’hôte a le format suivant, où \<*e-commerce-tenant-name*\> est le nom de votre environnement :

&lt;nom-client-e-commerce&gt;.commerce.dynamics.com

Le nom de l’hôte ou le point de terminaison généré lors de le processus de mise en service prend en charge un certificat SSL (Secure Sockets Layer) uniquement pour \*.commerce.dynamics.com. Il ne prend pas en charge le protocole SSL pour les domaines personnalisés. Par conséquent, vous devez arrêter SSL pour les domaines personnalisés dans votre CDN et transférer le trafic du CDN vers le nom d’hôte ou le point de terminaison que le commerce a généré. 

En outre, les *statistiques* (fichiers Javascript ou de feuilles de style en cascade \[CSS\]) de Commerce sont fournis par le point de terminaison que Commerce a généré (\*.commerce.dynamics.com). Les statistiques peuvent être mises en cache uniquement si le nom d’hôte ou le point de terminaison que Commerce a généré est placé après le CDN.

## <a name="set-up-ssl"></a>Paramétrer SSL

Après avoir mis votre environnement Commerce en service avec le domaine personnalisé qui est fourni, ou après que vous ayez fourni le domaine personnalisé pour votre environnement à l’aide d’une requête de service, il vous faut collaborer avec l’équipe d’intégration de Commerce pour prévoir les modifications DNS.

Comme précédemment mentionné, le nom d’hôte ou le point de terminaison généré prend en charge un certificat SSL uniquement pour \*.commerce.dynamics.com. Il ne prend pas en charge le protocole SSL pour les domaines personnalisés.

## <a name="cdn-services"></a>Services CDN

Tout service CDN peut être utilisé avec un environnement Commerce. Voici deux exemples :

- **Microsoft Azure Front Door Service** – La solution d’Azure CDN. Pour plus d’informations sur Azure Front Door Service, voir la [Documentation Azure Front Door Service](/azure/frontdoor/).
- **Accélérateur dynamique de site Akamai** – Pour plus d’informations, voir [Accélérateur de site dynamique](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>Paramétrage CDN

Le processus de paramétrage de CDN se compose de ces étapes générales :

1. Ajoutez un hôte frontal.
1. Configurez un regroupement principal.
1. Paramétrez des règles d’acheminement.

### <a name="add-a-front-end-host"></a>Ajoutez un hôte frontal

Tout service CDN peut être utilisé, mais pour l’exemple dans cette rubrique, Azure Front Door Service est utilisé. 

Pour plus d’informations sur la configuration du Azure Front Door Service, voir [Démarrage rapide : Créez une Front Door pour une application web global très disponible](/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a>Configurer un regroupement principal dans Azure Front Door Service

Pour configurer un regroupement principal dans Azure Front Door Service, procédez comme suit.

1. Ajoutez **&lt;nom-du-locataire-ecom&gt;.commerce.dynamics.com** à un pool back-end en tant qu’hôte personnalisé qui a un en-tête d’hôte back-end identique à **&lt;nom-du-locataire-ecom&gt;.commerce.dynamics.com**.
1. Sous **Équilibrage de la charge**, laissez les valeurs par défaut.
1. Désactivez les contrôles d’intégrité du pool back-end.

L’illustration suivante présente la boîte de dialogue **Ajouter un regroupement principal** dans Azure Front Door Service avec le nom d’hôte principal entré.

![Boîte de dialogue Ajouter un regroupement principal](./media/CDN_BackendPool.png)

L’illustration suivante présente la boîte de dialogue **Ajouter un regroupement principal** dans Azure Front Door Service avec les valeurs d’équilibrage de charge par défaut.

![Boîte de dialogue Ajouter un regroupement principal](./media/CDN_BackendPool_2.png)

> [!NOTE]
> Assurez-vous de désactiver les **Tests d’intégrité** lors de la configuration de votre propre service Azure Front Door pour Commerce.


### <a name="set-up-rules-in-azure-front-door-service"></a>Paramétrer des règles dans Azure Front Door Service

Pour paramétrer une règle d’acheminement dans Azure Front Door Service, procédez comme suit.

1. Ajoutez une règle d’acheminement.
1. Dans le champ **Nom**, entrez **par défaut**.
1. Dans le champ **Protocole accepté**, sélectionnez **HTTP et HTTPS**.
1. Dans le champ **Hôtes frontaux**, entrez **dynamics-ecom-tenant-name.azurefd.net**.
1. Sous **Modèles à respecter**, dans le champ supérieur, entrez **/\***.
1. Sous **Détails de l’acheminement**, définissez l’option **Type d’acheminement** sur **Suivant**.
1. Dans le champ **Regroupement principal**, sélectionnez **ecom-principal**.
1. Dans le groupe de champ **Protocole de transfert**, sélectionnez l’option **Demande de mise en correspondance**. 
1. Définissez l’option **Réécriture de l’URL** sur **Désactivé**.
1. Définissez l’option **Mise en cache** sur **Désactivé**.


> [!WARNING]
> Si le domaine que vous utilisez est déjà actif et en service, créez un ticket de support à partir de la vignette **Support** dans [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) pour obtenir de l’aide pour vos prochaines étapes. Pour plus d’informations, voir [Obtenir de l’aide sur les applications Finance and Operations ou Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

Si votre domaine est nouveau et n’est pas un domaine actif préexistant, vous pouvez ajouter votre domaine personnalisé à la configuration d’Azure Front Door Service. Cela permet de rediriger le trafic web vers votre site via l’instance d’Azure Front Door. Pour ajouter le domaine personnalisé (par exemple, `www.fabrikam.com`), vous devez configurer un nom canonique (CNAME) pour le domaine.

L’illustration suivante présente la boîte de dialogue **Configuration CNAME** à Azure Front Door Service.

![Boîte de dialogue Configuration CNAME](./media/CNAME_Configuration.png)

Vous pouvez utiliser Azure Front Door Service pour gérer le certificat, ou vous pouvez utiliser votre propre certificat pour le domaine personnalisé.

L’illustration suivante présente la boîte de dialogue **HTTPS domaine personnalisé** à Azure Front Door Service.

![Boîte de dialogue HTTPS domaine personnalisé](./media/Custom_Domain_HTTPS.png)

Pour obtenir des instructions détaillées sur l’ajout d’un domaine personnalisé à votre Azure Front Door, voir [Ajouter un domaine personnalisé à votre Front Door](/azure/frontdoor/front-door-custom-domain).

Votre CDN doit être maintenant correctement configuré de sorte qu’il puisse être utilisé avec votre site Commerce.

## <a name="additional-resources"></a>Ressources supplémentaires

[Options de mise en œuvre d’un réseau de diffusion de contenu](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]