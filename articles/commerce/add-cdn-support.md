---
title: Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)
description: Cette rubrique décrit la procédure d'ajout d'un réseau de diffusion de contenu (CDN) à votre environnement Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/02/2020
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
ms.openlocfilehash: febef3bcc06dc1b5868a0decebee33d76110c505
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533342"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)


[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure d'ajout d'un réseau de diffusion de contenu (CDN) à votre environnement Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Lorsque vous paramétrez un environnement de commerce électronique dans Dynamics 365 Commerce, vous pouvez le configurer pour travailler avec votre service CDN. 

Votre domaine personnalisé peut être activé lors de le processus de mise en service pour votre environnement de commerce électronique. Sinon, vous pouvez utiliser une demande de service pour le configurer une fois le processus de mise en service terminé. Le processus de mise en service de l'environnement de commerce électronique génère un nom d'hôte associé à l'environnement. Ce nom d'hôte a le format suivant, où *non-client-e-commerce* est le nom de votre environnement :

&lt;nom-client-e-commerce&gt;.commerce.dynamics.com

Le nom de l'hôte ou le point de terminaison généré lors de le processus de mise en service prend en charge un certificat SSL (Secure Sockets Layer) uniquement pour \*.commerce.dynamics.com. Il ne prend pas en charge le protocole SSL pour les domaines personnalisés. Par conséquent, vous devez arrêter SSL pour les domaines personnalisés dans votre CDN et transférer le trafic du CDN vers le nom d'hôte ou le point de terminaison que le commerce a généré. 

En outre, les *statistiques* (fichiers Javascript ou de feuilles de style en cascade \[CSS\]) de Commerce sont fournis par le point de terminaison que Commerce a généré (\*.commerce.dynamics.com). Les statistiques peuvent être mises en cache uniquement si le nom d'hôte ou le point de terminaison que Commerce a généré est placé après le CDN.

## <a name="set-up-ssl"></a>Paramétrer SSL

Pour garantir que le protocole SSL est paramétré, et que ces statistiques sont mises en cache, vous devez configurer votre CDN afin qu'il soit associé au nom de l'hôte que Commerce a généré pour votre environnement. Vous devez également mettre en cache le schéma suivant pour les statistiques uniquement : 

/\_msdyn365/\_scnr/\*

Après avoir mis votre environnement Commerce en service avec le domaine personnalisé qui est fourni, ou après que vous ayez fourni le domaine personnalisé pour votre environnement à l'aide d'une requête de service, indiquez votre domaine personnalisé au nom d'hôte ou au point de terminaison que Commerce a généré.

Comme précédemment mentionné, le nom d'hôte ou le point de terminaison généré prend en charge un certificat SSL uniquement pour \*.commerce.dynamics.com. Il ne prend pas en charge le protocole SSL pour les domaines personnalisés.

## <a name="cdn-services"></a>Services CDN

Tout service CDN peut être utilisé avec un environnement Commerce. Voici deux exemples :

- **Microsoft Azure Front Door Service** – La solution d'Azure CDN. Pour plus d'informations sur Azure Front Door Service, voir la [Documentation Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).
- **Accélérateur dynamique de site Akamai** – Pour plus d'informations, voir [Accélérateur de site dynamique](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>Paramétrage CDN

Le processus de paramétrage de CDN se compose de ces étapes générales :

1. Ajoutez un hôte frontal.
1. Configurez un regroupement principal.
1. Paramétrez les règles d'acheminement et de mise en cache.

### <a name="add-a-front-end-host"></a>Ajoutez un hôte frontal

Tout service CDN peut être utilisé, mais pour l'exemple dans cette rubrique, Azure Front Door Service est utilisé. 

Pour plus d'informations sur la configuration du Azure Front Door Service, voir [Démarrage rapide : Créez une Front Door pour une application web global très disponible](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a>Configurez un regroupement principal dans Azure Front Door Service

Pour configurer un regroupement principal dans Azure Front Door Service, procédez comme suit.

1. Ajoutez **&lt;nom-client-ecom&gt;.commerce.dynamics.com** à un regroupement principal comme serveur personnalisé qui a un en-tête d'hôte principal vide.
1. Sous **Tests d'intégrité**, dans le champ **Chemin d'accès**, entrez **/keepalive**.
1. Dans le champ **Intervalles (secondes)**, entrez **255**.
1. Sous **Équilibrage de la charge**, laissez les valeurs par défaut.

L'illustration suivante présente la boîte de dialogue **Ajouter un regroupement principal** à Azure Front Door Service.

![Boîte de dialogue Ajouter un regroupement principal](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a>Paramétrer des règles dans Azure Front Door Service

Pour paramétrer une règle d'acheminement dans Azure Front Door Service, procédez comme suit.

1. Ajoutez une règle d'acheminement.
1. Dans le champ **Nom**, entrez **par défaut**.
1. Dans le champ **Protocole accepté**, sélectionnez **HTTP et HTTPS**.
1. Dans le champ **Hôtes frontaux**, entrez **dynamics-ecom-tenant-name.azurefd.net**.
1. Sous **Modèles à respecter**, dans le champ supérieur, entrez **/\***.
1. Sous **Détails de l'acheminement**, définissez l'option **Type d'acheminement** sur **Suivant**.
1. Dans le champ **Regroupement principal**, sélectionnez **ecom-principal**.
1. Dans le groupe de champ **Protocole de transfert**, sélectionnez l'option **Demande de mise en correspondance**. 
1. Définissez l'option **Réécriture de l'URL** sur **Désactivé**.
1. Définissez l'option **Mise en cache** sur **Désactivé**.

Pour paramétrer une règle de mise en cache dans Azure Front Door Service, procédez comme suit.

1. Ajoutez une règle de mise en cache.
1. Dans le champ **Nom**, entrez **statistiques**.
1. Dans le champ **Protocole accepté**, sélectionnez **HTTP et HTTPS**.
1. Dans le champ **Hôtes frontaux**, entrez **dynamics-ecom-tenant-name.azurefd.net**.
1. Sous **Modèles à respecter**, dans le champ supérieur, entrez **/\_msdyn365/\_scnr/\***.
1. Sous **Détails de l'acheminement**, définissez l'option **Type d'acheminement** sur **Suivant**.
1. Dans le champ **Regroupement principal**, sélectionnez **ecom-principal**.
1. Dans le groupe de champ **Protocole de transfert**, sélectionnez l'option **Demande de mise en correspondance**.
1. Définissez l'option **Réécriture de l'URL** sur **Désactivé**.
1. Définissez l'option **Mise en cache** sur **Désactivé**.
1. Dans le champ **Comportement de mise en cache de la chaîne de requête**, sélectionnez **Mettre en cache chaque URL unique**.
1. Dans le groupe de champ **Compression dynamique**, sélectionnez l'option **Activé**.

L'illustration suivante présente la boîte de dialogue **Ajouter une règle** à Azure Front Door Service.

![Boîte de dialogue Ajouter une règle](./media/CDN_CachingRule.png)

Une fois cette première configuration déployée, vous devez ajouter votre domaine personnalisé à la configuration d'Azure Front Door Service. Pour ajouter le domaine personnalisé (par exemple, `www.fabrikam.com`), vous devez configurer un nom canonique (CNAME) pour le domaine.

L'illustration suivante présente la boîte de dialogue **Configuration CNAME** à Azure Front Door Service.

![Boîte de dialogue Configuration CNAME](./media/CNAME_Configuration.png)

> [!NOTE]
> Si le domaine que vous utiliserez est déjà actif et en direct, contactez le support pour activer ce domaine auprès d'Azure Front Door Service avant de paramétrer un test.

Vous pouvez utiliser Azure Front Door Service pour gérer le certificat, ou vous pouvez utiliser votre propre certificat pour le domaine personnalisé.

L'illustration suivante présente la boîte de dialogue **HTTPS domaine personnalisé** à Azure Front Door Service.

![Boîte de dialogue HTTPS domaine personnalisé](./media/Custom_Domain_HTTPS.png)

Votre CDN doit être maintenant correctement configuré de sorte qu'il puisse être utilisé avec votre site Commerce.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Déploiement d'un nouveau site de commerce électronique](deploy-ecommerce-site.md)

[Création d'un site de commerce électronique](create-ecommerce-site.md)

[Association d'un site en ligne avec un canal](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d'URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)
