---
title: Domaines dans Dynamics 365 Commerce
description: Cet article décrit comment les domaines sont gérés dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/08/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: f1a2de7984aad7d291b8a4dc68f5690d57ebe6cc
ms.sourcegitcommit: 2b654e60e2553a5835ab5790db4ccfa58828fae7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750678"
---
# <a name="domains-in-dynamics-365-commerce"></a>Domaines dans Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cet article décrit comment les domaines sont gérés dans Microsoft Dynamics 365 Commerce.

Les domaines sont des adresses web utilisées pour accéder aux sites Dynamics 365 Commerce dans un navigateur web. Vous contrôlez la gestion de votre domaine avec un fournisseur de serveurs de noms de domaine (DNS) choisi. Les domaines sont référencés partout dans le constructeur de site Dynamics 365 Commerce pour coordonner l’accès à un site lors de sa publication. Cet article examine la manière dont les domaines sont gérés et référencés tout au long du cycle de vie du développement et du lancement du site Commerce.

> [!NOTE]
> Depuis le 6 mai 2022, tous les environnements créés dans Dynamics 365 Commerce seront approvisionnés avec le domaine `.dynamics365commerce.ms`, remplaçant le modèle précédent de `.commerce.dynamics.com`. Environnements existants provisionnés avec le domaine `.commerce.dynamics.com` continuera à fonctionner.

## <a name="provisioning-and-supported-host-names"></a>Approvisionnement et noms d’hôte pris en charge

Lors de l’approvisionnement d’un environnement d’e-commerce dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), la zone **Noms d’hôtes pris en charge** sur l’écran d’approvisionnement d’e-commerce est utilisée pour saisir les domaines qui seront associés à l’environnement Commerce déployé. Ces domaines seront les noms de serveurs de noms de domaine (DNS) destinés aux clients sur lesquels les sites web d’e-commerce seront hébergés. La saisie d’un domaine à ce stade ne commence pas à détourner le trafic du domaine vers Dynamics 365 Commerce. Le trafic d’un domaine ne sera acheminé vers le point de terminaison Commerce que lorsque l’enregistrement CNAME du DNS est mis à jour pour utiliser le point de terminaison Commerce avec le domaine.

> [!NOTE]
> Plusieurs domaines peuvent être saisis dans la zone **Noms d’hôtes pris en charge** en les séparant par des points-virgules.

L’illustration suivante montre l’écran d’approvisionnement d’e-commerce LCS avec la zone **Noms d’hôtes pris en charge** en surbrillance. 

![Écran d’approvisionnement d’e-commerce LCS avec la zone **Noms d’hôte pris en charge** en surbrillance.](./media/Domains_ProvisioningeCommerceScreen_publish.png)

Vous pouvez créer une demande de service pour ajouter des domaines supplémentaires à un environnement si l’approvisionnement a déjà eu lieu. Pour créer une demande de service dans LCS, dans votre environnement, accédez à **Support \> Problèmes de support** et sélectionnez **Soumettre un incident**.

## <a name="commerce-generated-urls"></a>URL générées par le commerce

Lors de l’approvisionnement d’un environnement d’e-commerce Dynamics 365 Commerce, Commerce génère une URL qui sera l’adresse de travail de l’environnement. Cette URL est référencée dans le lien du site d’e-commerce affiché dans LCS après l’approvisionnement de l’environnement. Une URL générée par Commerce est au format `https://<e-commerce tenant name>.dynamics365commerce.ms`, où le nom du client e-commerce est le nom entré dans LCS pour l’environnement Commerce.

Vous pouvez également utiliser des noms d’hôte de site de production dans un environnement bac à sable. Cette option est idéale lorsque vous copiez un site d’un environnement de bac à sable vers un environnement de production.

## <a name="site-setup"></a>Paramétrage de site

Une fois votre environnement d’e-commerce approvisionné, vous devez configurer votre site dans le générateur de site Commerce pour associer votre site à l’URL de travail.

Lorsque vous configurez un site pour la première fois dans le générateur de site, la boîte de dialogue **Configurer votre site** apparaîtra.

L’illustration suivante montre la boîte de dialogue **Configurer votre site** pour un site nommé « par défaut » lorsque vous accédez au site pour la première fois dans le générateur de site.

![Boîte de dialogue **Configurer votre site**.](./media/Domains_SetupyoursiteScreen.png)

La zone **Sélectionnez un domaine** vous permet d’associer l’un des noms d’hôte pris en charge fournis pour votre site dans LCS à votre site dans le constructeur de site.

La zone **Chemin d’accès** peut être laissée vide, ou une chaîne de chemin d’accès supplémentaire peut être ajoutée qui sera reflétée dans votre URL de travail. Laisser la zone **Chemin d’accès** vide permet d’associer l’URL de base générée par Commerce au site en cours de configuration dans le générateur de site. Les chemins d’accès doivent être uniques pour chaque paire site/domaine. Dans le site et le domaine sélectionnés, un seul site de l’environnement peut utiliser le chemin d’accès vide ou être associé à une chaîne de chemin d’accès unique. Toute chaîne ajoutée au **Chemin d’accès** pendant la configuration du site deviendra un sous-chemin d’accès de l’URL de base générée par Commerce utilisée pour accéder au site dans un navigateur web.

> [!NOTE]
> Le chemin d’accès est également connu sous le nom de **Chemin d’accès correspondant** lors de l’ajout d’un canal dans la section de configuration **Paramètres du site \> Canaux** du constructeur de site.

Par exemple, si vous avez un site dans le générateur de site appelé « fabrikam » dans un client d’e-commerce nommé « xyz » et si vous configurez le site avec un chemin d’accès vide, vous accéderez au contenu du site publié dans un navigateur web en accédant directement à l’URL de base générée par Commerce :

`https://xyz.dynamics365commerce.ms`

Sinon, si vous aviez ajouté un chemin d’accès « fabrikam » lors de la configuration de ce même site, vous accéderiez au contenu du site publié dans un navigateur web à l’aide de l’URL suivante :

`https://xyz.dynamics365commerce.ms/fabrikam`

## <a name="pages-and-urls"></a>Pages et URL

Une fois que votre site est configuré avec un chemin, toutes les URL associées aux pages dans le générateur de site s’appuieront sur l’URL de travail (l’URL générée par Commerce ou l’URL générée par Commerce plus le chemin d’accès) du site. La création d’une URL dans le constructeur de site (**URLS /> +New**) en sélectionnant une page dans la liste de la boîte de dialogue **Nouvelle URL** et la saisie du chemin d’accès de l’URL de cette page associera cette URL à la page sélectionnée. La valeur du chemin d’accès de l’URL s’ajoute ensuite à l’URL de travail du site pour accéder à la page, et est étiquetée comme `./<URL path>` dans la liste d’URL de la page **URL** du constructeur de site.

L’illustration suivante montre la boîte de dialogue **Nouvelle URL** dans le générateur de site avec un exemple de chemin d’accès d’URL mis en évidence. 

![Boîte de dialogue **Nouvelle URL** dans le générateur de site.](./media/Domains_PageSetup2a.png)

L’illustration suivante montre la page **URL** dans le générateur de site avec un exemple d’URL mis en évidence dans la liste.

![Exécuter l’option Flux d’utilisateur dans le flux de stratégie.](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a>Domaines dans le générateur de site

Les valeurs de noms d’hôte prises en charge peuvent être associées en tant que domaine lors de la configuration d’un site. Lors de la sélection d’une valeur de nom d’hôte prise en charge comme domaine, vous verrez le domaine choisi référencé dans le générateur de site. Ce domaine n’est qu’une référence dans l’environnement Commerce, le trafic en direct pour ce domaine ne sera pas encore redirigé vers Dynamics 365 Commerce.

Lorsque vous travaillez avec des sites dans le générateur de site, si vous avez deux sites configurés avec deux domaines différents, vous pouvez ajouter l’attribut **?domaine=** à votre URL de travail pour accéder au contenu du site publié dans un navigateur.

Par exemple, l’environnement « xyz » a été approvisionné et deux sites ont été créés et associés dans le générateur de site : un avec le domaine `www.fabrikam.com` et l’autre avec le domaine `www.constoso.com`. Chaque site a été mis en place en utilisant un chemin d’accès vierge. Ces deux sites peuvent ensuite être accédés dans un navigateur web comme suit en utilisant l’attribut **?domaine=**  :
- `https://xyz.dynamics365commerce.ms?domain=www.fabrikam.com`
- `https://xyz.dynamics365commerce.ms?domain=www.contoso.com`

Lorsqu’une chaîne de requête de domaine n’est pas donnée dans un environnement avec plusieurs domaines fournis, Commerce utilise le premier domaine que vous avez fourni. Par exemple, si le chemin d’accès « fabrikam » a été fourni en premier lors de la configuration du site, l’URL `https://xyz.dynamics365commerce.ms` pourrait être utilisée pour accéder au site de contenu du site publié pour `www.fabrikam.com`.

Vous pouvez également ajouter des domaines personnalisés. Pour ce faire, sur la page de gestion Commerce de l’environnement pour le projet, sous le sous-titre **Commerce électronique**, sélectionnez **+ Ajouter un domaine personnalisé**. Le curseur affiche les domaines personnalisés existants et offre la possibilité d’ajouter un nouveau domaine personnalisé.

## <a name="update-which-commerce-scale-unit-is-used"></a>Mettre à jour l’instance Commerce Scale Unit utilisée

L’instance Commerce Scale Unit (CSU) utilisée par Commerce est généralement sélectionnée lors de la création initiale d’un environnement. Commerce vous permet de modifier l’instance CSU utilisée par votre environnement, ce qui vous permet de mieux gérer votre architecture via une fonctionnalité en libre-service et de réduire la nécessité de contacter le support. Pour mettre à jour votre instance CSU, accédez à la page de gestion Commerce de votre environnement pour le projet, puis sélectionnez **Mettre à jour Scale Unit**. Utilisez le curseur **Nouvelle Commerce Scale Unit** pour sélectionner une nouvelle instance CSU dans la liste des CSU disponibles pour votre environnement.

## <a name="traffic-forwarding-in-production"></a>Transfert de trafic en production

Vous pouvez simuler plusieurs domaines à l’aide des paramètres de chaîne de requête de domaine sur le point de terminaison commerce.dynamics.com lui-même. Mais lorsque vous devez passer en production, vous devez transférer le trafic de votre domaine personnalisé vers le point de terminaison `<e-commerce tenant name>.dynamics365commerce.ms`.

Le point de terminaison `<e-commerce tenant name>.dynamics365commerce.ms` ne prend pas en charge les SSL (Secure Sockets Layers) de domaine personnalisé, vous devez donc configurer des domaines personnalisés à l’aide d’un front door service ou d’un réseau de distribution de contenu (CDN). 

Pour configurer des domaines personnalisés à l’aide d’un front door service ou d’un CDN, vous avez deux options :

- Configurez un front door service tel qu’Azure Front Door pour gérer le trafic frontal et vous connecter à votre environnement Commerce, ce qui offre un meilleur contrôle sur la gestion des domaines et des certificats et des stratégies de sécurité plus granulaires.

- Utilisez l’instance Azure Front Door fournie par Commerce, qui nécessite une action de coordination avec l’équipe Dynamics 365 Commerce pour la vérification du domaine et l’obtention de certificats SSL pour votre domaine de production.

> [!NOTE]
> Si vous utilisez un CDN externe ou un service instance Front Door, assurez-vous que la demande atterrit sur la plate-forme Commerce avec le nom d’hôte fourni par Commerce, mais avec l’en-tête X-Forwarded-Host (XFH) \<custom-domain\>. Par exemple, si votre point de terminaison Commerce est `xyz.dynamics365commerce.ms` et le domaine personnalisé est `www.fabrikam.com`, l’en-tête d’hôte de la requête transférée doit être `xyz.dynamics365commerce.ms` et l’en-tête XFH doit être `www.fabrikam.com`.

Pour plus d’informations sur la configuration directe d’un service CDN, consultez [Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md).

Pour utiliser l’instance d’Azure Front Door fournie par Commerce, vous devez créer une demande de service de support pour la configuration CDN auprès de l’équipe d’intégration Commerce. 

- Vous devrez fournir le nom de votre entreprise, le domaine de production, l’ID d’environnement et le nom du client d’e-commerce de production. 
- Vous devrez confirmer si cette demande de service concerne un domaine existant (utilisé pour un site actuellement actif) ou un nouveau domaine. 
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

L’instance d’Azure Front Door fournie par Commerce ne prend pas en charge les domaines apex (domaines racine qui ne contiennent pas de sous-domaines). Les domaines apex nécessitent une adresse IP pour être résolus et l’instance Front Door de Commerce Azure existe uniquement avec des points de terminaison virtuels. Pour utiliser un domaine apex, vous disposez des options suivantes :

- **Option 1** – Utilisez votre fournisseur DNS pour rediriger le domaine apex vers un domaine « www ». Par exemple, fabrikam.com redirige vers `www.fabrikam.com` où `www.fabrikam.com` est l’enregistrement CNAME qui pointe vers l’instance d’Azure Front Door hébergée par Commerce.

- **Option 2** : si votre fournisseur DNS prend en charge les enregistrements ALIAS, vous pouvez faire pointer le domaine apex vers le point de terminaison Azure Front Door, ce qui garantit que le changement d’adresse IP par le point de terminaison est reflété. Vous devez héberger vous-même l’instance Azure Front Door.
  
- **Option 3** : si votre fournisseur DNS ne prend pas en charge les enregistrements ALIAS, vous devez remplacer votre fournisseur DNS par Azure DNS et héberger vous-même Azure DNS et l’instance Azure Front Door.

> [!NOTE]
> Si vous utilisez Azure Front Door, vous devez également configurer un Azure DNS dans le même abonnement. Le domaine apex hébergé sur Azure DNS peut pointer vers votre Azure Front Door en tant qu’enregistrement d’alias. C’est la seule solution, car les domaines apex doivent toujours pointer vers une adresse IP.
  
Si vous avez des questions concernant les domaines Apex, veuillez contacter [Assistance Microsoft ](https://support.microsoft.com/).

  ## <a name="additional-resources"></a>Ressources supplémentaires

  [Déployer un nouveau abonné e-commerce](deploy-ecommerce-site.md)

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
