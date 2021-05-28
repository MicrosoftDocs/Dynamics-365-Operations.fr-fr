---
title: Domaines dans Dynamics 365 Commerce
description: Cette rubrique décrit comment les domaines sont gérés dans Microsoft Dynamics 365 Commerce.
author: BrShoo
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: BrShoo
ms.search.validFrom: ''
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 0a494a36d1d8fa55521c416efd4262d860e1a708
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022834"
---
# <a name="domains-in-dynamics-365-commerce"></a>Domaines dans Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment les domaines sont gérés dans Microsoft Dynamics 365 Commerce.

Les domaines sont des adresses web utilisées pour accéder aux sites Dynamics 365 Commerce dans un navigateur web. Vous contrôlez la gestion de votre domaine avec un fournisseur de serveurs de noms de domaine (DNS) choisi. Les domaines sont référencés partout dans le constructeur de site Dynamics 365 Commerce pour coordonner l’accès à un site lors de sa publication. Cette rubrique examine la manière dont les domaines sont gérés et référencés tout au long du cycle de vie du développement et du lancement du site Commerce.

## <a name="provisioning-and-supported-host-names"></a>Approvisionnement et noms d’hôte pris en charge

Lors de l’approvisionnement d’un environnement d’e-commerce dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), la zone **Noms d’hôtes pris en charge** sur l’écran d’approvisionnement d’e-commerce est utilisée pour saisir les domaines qui seront associés à l’environnement Commerce déployé. Ces domaines seront les noms de serveurs de noms de domaine (DNS) destinés aux clients sur lesquels les sites web d’e-commerce seront hébergés. La saisie d’un domaine à ce stade ne commence pas à détourner le trafic du domaine vers Dynamics 365 Commerce. Le trafic d’un domaine ne sera acheminé vers le point de terminaison Commerce que lorsque l’enregistrement CNAME du DNS est mis à jour pour utiliser le point de terminaison Commerce avec le domaine.

> [!NOTE]
> Plusieurs domaines peuvent être saisis dans la zone **Noms d’hôtes pris en charge** en les séparant par des points-virgules.

L’illustration suivante montre l’écran d’approvisionnement d’e-commerce LCS avec la zone **Noms d’hôtes pris en charge** en surbrillance. 

![Écran d’approvisionnement d’e-commerce LCS avec la zone **Noms d’hôte pris en charge** en surbrillance](./media/Domains_ProvisioningeCommerceScreen_publish.png)

Vous pouvez créer une demande de service pour ajouter des domaines supplémentaires à un environnement si l’approvisionnement a déjà eu lieu. Pour créer une demande de service dans LCS, dans votre environnement, accédez à **Support \> Problèmes de support** et sélectionnez **Soumettre un incident**.

## <a name="commerce-generated-urls"></a>URL générées par le commerce

Lors de l’approvisionnement d’un environnement d’e-commerce Dynamics 365 Commerce, Commerce génère une URL qui sera l’adresse de travail de l’environnement. Cette URL est référencée dans le lien du site d’e-commerce affiché dans LCS après l’approvisionnement de l’environnement. Une URL générée par Commerce est au format `https://<e-commerce tenant name>.commerce.dynamics.com`, où le nom du client e-commerce est le nom entré dans LCS pour l’environnement Commerce.

Vous pouvez également utiliser des noms d’hôte de site de production dans un environnement bac à sable. Cette option est idéale lorsque vous copiez un site d’un environnement bac à sable vers la production.

## <a name="site-setup"></a>Paramétrage de site

Une fois votre environnement d’e-commerce approvisionné, vous devez configurer votre site dans le générateur de site Commerce pour associer votre site à l’URL de travail.

Lorsque vous configurez un site pour la première fois dans le générateur de site, la boîte de dialogue **Configurer votre site** apparaîtra.

L’illustration suivante montre la boîte de dialogue **Configurer votre site** pour un site nommé « par défaut » lorsque vous accédez au site pour la première fois dans le générateur de site.

![Boîte de dialogue **Configurer votre site**](./media/Domains_SetupyoursiteScreen.png)

La zone **Sélectionnez un domaine** vous permet d’associer l’un des noms d’hôte pris en charge fournis pour votre site dans LCS à votre site dans le constructeur de site.

La zone **Chemin d’accès** peut être laissée vide, ou une chaîne de chemin d’accès supplémentaire peut être ajoutée qui sera reflétée dans votre URL de travail. Laisser la zone **Chemin d’accès** vide permet d’associer l’URL de base générée par Commerce au site en cours de configuration dans le générateur de site. Les chemins d’accès doivent être uniques pour chaque paire site/domaine. Dans le site et le domaine sélectionnés, un seul site de l’environnement peut utiliser le chemin d’accès vide ou être associé à une chaîne de chemin d’accès unique. Toute chaîne ajoutée au **Chemin d’accès** pendant la configuration du site deviendra un sous-chemin d’accès de l’URL de base générée par Commerce utilisée pour accéder au site dans un navigateur web.

> [!NOTE]
> Le chemin d’accès est également connu sous le nom de **Chemin d’accès correspondant** lors de l’ajout d’un canal dans la section de configuration **Paramètres du site \> Canaux** du constructeur de site.

Par exemple, si vous avez un site dans le générateur de site appelé « fabrikam » dans un client d’e-commerce nommé « xyz » et si vous configurez le site avec un chemin d’accès vide, vous accéderez au contenu du site publié dans un navigateur web en accédant directement à l’URL de base générée par Commerce :

`https://xyz.commerce.dynamics.com`

Sinon, si vous aviez ajouté un chemin d’accès « fabrikam » lors de la configuration de ce même site, vous accéderiez au contenu du site publié dans un navigateur web à l’aide de l’URL suivante :

`https://xyz.commerce.dynamics.com/fabrikam`

## <a name="pages-and-urls"></a>Pages et URL

Une fois que votre site est configuré avec un chemin, toutes les URL associées aux pages dans le générateur de site s’appuieront sur l’URL de travail (l’URL générée par Commerce ou l’URL générée par Commerce plus le chemin d’accès) du site. La création d’une URL dans le constructeur de site (**URLS /> +New**) en sélectionnant une page dans la liste de la boîte de dialogue **Nouvelle URL** et la saisie du chemin d’accès de l’URL de cette page associera cette URL à la page sélectionnée. La valeur du chemin d’accès de l’URL s’ajoute ensuite à l’URL de travail du site pour accéder à la page, et est étiquetée comme `./<URL path>` dans la liste d’URL de la page **URL** du constructeur de site.

L’illustration suivante montre la boîte de dialogue **Nouvelle URL** dans le générateur de site avec un exemple de chemin d’accès d’URL mis en évidence. 

![Boîte de dialogue **Nouvelle URL** dans le générateur de site](./media/Domains_PageSetup2a.png)

L’illustration suivante montre la page **URL** dans le générateur de site avec un exemple d’URL mis en évidence dans la liste.

![Exécuter l’option Flux d’utilisateur dans le flux de stratégie](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a>Domaines dans le générateur de site

Les valeurs de noms d’hôte prises en charge peuvent être associées en tant que domaine lors de la configuration d’un site. Lors de la sélection d’une valeur de nom d’hôte prise en charge comme domaine, vous verrez le domaine choisi référencé dans le générateur de site. Ce domaine n’est qu’une référence dans l’environnement Commerce, le trafic en direct pour ce domaine ne sera pas encore redirigé vers Dynamics 365 Commerce.

Lorsque vous travaillez avec des sites dans le générateur de site, si vous avez deux sites configurés avec deux domaines différents, vous pouvez ajouter l’attribut **?domaine=** à votre URL de travail pour accéder au contenu du site publié dans un navigateur.

Par exemple, l’environnement « xyz » a été approvisionné et deux sites ont été créés et associés dans le générateur de site : un avec le domaine `www.fabrikam.com` et l’autre avec le domaine `www.constoso.com`. Chaque site a été mis en place en utilisant un chemin d’accès vierge. Ces deux sites peuvent ensuite être accédés dans un navigateur web comme suit en utilisant l’attribut **?domaine=**  :
- `https://xyz.commerce.dynamics.com?domain=www.fabrikam.com`
- `https://xyz.commerce.dynamics.com?domain=www.contoso.com`

Lorsqu’une chaîne de requête de domaine n’est pas donnée dans un environnement avec plusieurs domaines fournis, Commerce utilise le premier domaine que vous avez fourni. Par exemple, si le chemin d’accès « fabrikam » a été fourni en premier lors de la configuration du site, l’URL `https://xyz.commerce.dynamics.com` pourrait être utilisée pour accéder au site de contenu du site publié pour `www.fabrikam.com`.

## <a name="traffic-forwarding-in-production"></a>Transfert de trafic en production

Vous pouvez simuler plusieurs domaines à l’aide des paramètres de chaîne de requête de domaine sur le point de terminaison commerce.dynamics.com lui-même. Mais lorsque vous devez passer en production, vous devez transférer le trafic de votre domaine personnalisé vers le point de terminaison `<e-commerce tenant name>.commerce.dynamics.com`.

Le point de terminaison `<e-commerce tenant name>.commerce.dynamics.com` ne prend pas en charge les SSL (Secure Sockets Layers) de domaine personnalisé, vous devez donc configurer des domaines personnalisés à l’aide d’un front door service ou d’un réseau de distribution de contenu (CDN). 

Pour configurer des domaines personnalisés à l’aide d’un front door service ou d’un CDN, vous avez deux options :

- Configurez un front door service comme Azure Front Door pour gérer le trafic frontal et connectez-vous à votre environnement Commerce. Cela offre un meilleur contrôle sur la gestion des domaines et des certificats et des stratégies de sécurité plus granulaires.
- Utilisez l’instance d’Azure Front Door fournie par Commerce. Cela nécessite une action coordonnée avec l’équipe Dynamics 365 Commerce pour la vérification du domaine et l’obtention de certificats SSL pour votre domaine de production.

Pour plus d’informations sur la configuration directe d’un service CDN, consultez [Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md).

Pour utiliser l’instance d’Azure Front Door fournie par Commerce, vous devez créer une demande de service de support pour la configuration CDN auprès de l’équipe d’intégration Commerce. 

- Vous devrez fournir le nom de votre entreprise, le domaine de production, l’ID d’environnement et le nom du client d’e-commerce de production. 
- Vous devrez confirmer s’il s’agit d’un domaine existant (utilisé pour un site actuellement actif) ou d’un nouveau domaine. 
- Pour un nouveau domaine, la vérification du domaine et le certificat SSL peuvent être réalisés en une seule étape. 
- Pour un domaine desservant un site web existant, un processus en plusieurs étapes est requis pour établir la vérification du domaine et le certificat SSL. Ce processus comporte un contrat de niveau de service (SLA) de 7 jours ouvrables pour qu’un domaine soit mis en service, car il comprend plusieurs étapes séquentielles.

Pour créer une demande de service dans LCS, dans votre environnement, accédez à **Support \> Problèmes de support** et sélectionnez **Soumettre un incident**.

> [!NOTE]
> Les domaines personnalisés avec SSL ne sont pris en charge que sur les environnements de production. Pour les environnements hors production, tels que le bac à sable et les tests d’acceptation des utilisateurs (UAT), utilisez l’URL générée par Commerce pour accéder au contenu publié dans un navigateur web.

## <a name="ssl-certificate-process"></a>Processus de certificat SSL

Lorsqu’une demande de service est déposée, l’équipe Commerce coordonnera avec vous les étapes suivantes.

Pour les nouveaux domaines :
- L’équipe Commerce configurera l’instance d’Azure Front Door (hébergée par Commerce).
- L’équipe Commerce fournira ensuite l’enregistrement CNAME pour pointer votre domaine personnalisé.
- Une fois l’enregistrement CNAME mis à jour, l’instance d’Azure Front Door hébergée par Commerce sera en mesure de vérifier la propriété du domaine et d’obtenir le certificat SSL.

Pour les domaines existants/actifs :
- L’équipe Commerce vous demandera d’ajouter un enregistrement CNAME `afdverify.<custom-domain>` à fournir au fournisseur DNS de votre domaine.
- Une fois terminé, l’équipe Commerce ajoutera le domaine à l’instance d’Azure Front Door et fournira des enregistrements DNS TXT supplémentaires à ajouter au DNS pour le domaine.
- Une fois les enregistrements TXT terminés, l’équipe Commerce terminera les mises à jour d’Azure Front Door pour le domaine qui configurera le certificat SSL.

## <a name="apex-domains"></a>Domaines Apex

L’instance d’Azure Front Door fournie par Commerce ne prend pas en charge les domaines apex (domaines racine qui ne contiennent pas de sous-domaines). Les domaines apex nécessitent une adresse IP pour être résolus et l’instance de Commerce Azure Front Door existe uniquement avec des points de terminaison virtuels. Pour utiliser un domaine apex, vous avez deux options :

- **Option 1** – Utilisez votre fournisseur DNS pour rediriger le domaine apex vers un domaine « www ». Par exemple, fabrikam.com redirige vers `www.fabrikam.com` où `www.fabrikam.com` est l’enregistrement CNAME qui pointe vers l’instance d’Azure Front Door hébergée par Commerce.

- **Option 2** – Configurez vous-même une instance CDN/front door pour héberger le domaine apex.

> [!NOTE]
> Si vous utilisez Azure Front Door, vous devez également configurer un Azure DNS dans le même abonnement. Le domaine apex hébergé sur Azure DNS peut pointer vers votre Azure Front Door en tant qu’enregistrement d’alias. C’est la seule solution, car les domaines apex doivent toujours pointer vers une adresse IP.

  ## <a name="additional-resources"></a>Ressources supplémentaires

  [Déployer un nouveau client e-commerce](deploy-ecommerce-site.md)

  [Paramétrer un canal de magasin en ligne](./channel-setup-online.md)

  [Créer un site d’e-commerce](create-ecommerce-site.md)

  [Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

  [Gérer les fichiers robots.txt](manage-robots-txt-files.md)

  [Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

  [Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

  [Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

  [Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

  [Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

  [Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]