---
title: Conformité des cookies
description: Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/21/2021
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
ms.openlocfilehash: 8eb610eb819dee09a30368257e36dc88f855e985
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2021
ms.locfileid: "6088385"
---
# <a name="cookie-compliance"></a>Conformité des cookies

[!include [banner](includes/banner.md)]

Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.

La confidentialité est un facteur important lorsque les technologies de suivi affectent les clients e-commerce. En raison des normes de respect de la vie privée telles que le Règlement général sur la protection des données (RGPD) dans l’Union européenne (UE), les directives de confidentialité électroniques doivent être prises en compte pour tout site actif aujourd’hui. Étant donné que de nombreux sites de commerce électronique sont accessibles par défaut à l’échelle mondiale, il est important que vous examiniez les normes de conformité de votre site de commerce électronique.

Pour en savoir plus sur les principes de base utilisés par Microsoft pour la conformité des cookies, visitez le [Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center). Sur ce site, vous pouvez également obtenir plus d’informations sur les domaines de conformité et de gestion de la confidentialité.

Le tableau suivant montre la liste de référence actuelle des cookies placés par les sites Dynamics 365 Commerce.

| Nom du cookie                               | Utilisation                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| .AspNet.Cookies                             | Cookies d’authentification Store Microsoft Azure Active Directory (Azure AD) pour l’authentification unique (SSO). Stocke les informations chiffrées de l’utilisateur principal (nom, prénom, e-mail). |
| &#95;msdyn365___cart&#95;                           | ID du panier de magasin utilisé pour obtenir la liste des produits ajoutés à l’instance du panier. |
| &#95;msdyn365___ucc&#95;                            | Suivi du consentement de conformité des cookies.                          |
| ai_session                                  | Détecte le nombre de sessions d’activité de l’utilisateur qui ont inclus certaines pages et fonctionnalités de l’application. |
| ai_user                                     | Détecte le nombre de personnes qui ont utilisé l’application et ses fonctionnalités. Les utilisateurs sont comptés à l’aide d’ID anonymes. |
| b2cru                                       | Stocke l’URL de redirection de manière dynamique.                              |
| JSESSIONID                                  | Utilisé par le connecteur de paiement Adyen pour stocker la session utilisateur.       |
| OpenIdConnect.nonce.&#42;                       | Authentification                                               |
| x-ms-cpim-cache:.&#42;                          | Utilisé pour maintenir l’état de la demande.                      |
| x-ms-cpim-csrf                              | Jeton de falsification de requête intersites (CRSF) utilisé pour la protection contre CRSF.     |
| x-ms-cpim-dc                                | Utilisé pour acheminer les demandes vers l’instance de serveur d’authentification de production appropriée. |
| x-ms-cpim-rc.&#42;                              | Utilisé pour acheminer les demandes vers l’instance de serveur d’authentification de production appropriée. |
| x-ms-cpim-slice                             | Utilisé pour acheminer les demandes vers l’instance de serveur d’authentification de production appropriée. |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Utilisé pour maintenir la session SSO.                        |
| x-ms-cpim-trans                             | Utilisé pour le suivi des transactions (le nombre d’onglets ouverts s’authentifiant sur un site B2C), y compris la transaction en cours. |
| \_msdyn365___muid_                            | Utilisé si l'expérimentation est activée pour l'environnement ; utilisé comme userId à des fins d'expérimentation. |
| \_msdyn365___exp_                             | Utilisé si l'expérimentation est activée pour l'environnement ; utilisé pour mesurer l'équilibrage de charge des performances.         |
| d365mkt                                       | Utilisé si la détection basée sur l’emplacement pour suivre l’adresse IP d’un utilisateur pour les suggestions d’emplacement du magasin est activée dans le générateur de site de Commerce sous **Paramètres du site > Général > Activer la détection du magasin selon l’emplacement**.      |

Si un utilisateur du site sélectionne des liens de réseaux sociaux dans un site, les cookies du tableau suivant seront également suivis sur son navigateur.


| Domaine                      | Cookie               | Description                                                  | Source                                          |
| --------------------------- | ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| .linkedin.com                | UserMatchHistory         | Synchronisation des identifiants d'annonces LinkedIn                                      | Balise de flux LinkedIn et LinkedIn Insights                                |
| .linkedin.com               | li_sugr                  | Identificateur du navigateur                                           | Balise LinkedIn Insight si l'adresse IP ne se trouve pas dans un pays désigné |
| .linkedin.com               | BizographicsOptOut       | Détermine le statut de désactivation du suivi par des tiers.              | Contrôles des invités LinkedIn et pages de désactivation du secteur           |
| .linkedin.com               | \_guid                    | Identificateur de navigateur pour Google Ads.                            | Flux LinkedIn                                                |
| .linkedin.com               | li_oatml                 | Identificateur de membre indirect pour le suivi des conversions, le reciblage et l'analyse. | Balise d'annonces LinkedIn et LinkedIn Insights                                |
| Divers domaines propriétaires | li_fat_id                | Identificateur de membre indirect pour le suivi des conversions, le reciblage et l'analyse. | Balise d'annonces LinkedIn et LinkedIn Insights                                |
| .adsymptotic.com            | H                        | Identificateur du navigateur                                           | Balise LinkedIn Insight si l'adresse IP ne se trouve pas dans un pays désigné |
| .linkedin.com                | bcookie                  | Cookie d'identification du navigateur                                            | Requêtes vers LinkedIn                                         |
| .linkedin.com                | bscookie                 | Cookie de navigateur sécurisé                                        | Requêtes vers LinkedIn                                         |
| .linkedin.com               | lang                     | Définit les paramètres régionaux et la langue par défaut.                                 | Requêtes vers LinkedIn                                         |
| .linkedin.com                | lidc                     | Utilisé pour l'acheminement.                                             | Requêtes vers LinkedIn                                         |
| .linkedin.com               | aam_uuid                 | Cookie d'Adobe Audience Manager                                                     | Défini pour la synchronisation des identificateurs                                              |
| .linkedin.com               | \_ga                      | Cookie de Google Analytics                                            | Google Analytics                                             |
| .linkedin.com               | \_gat                     | Cookie de Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | liap                     | Cookie de Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | lissc                    |                                                              |                                                              |
| .facebook.com               | c_user                   | Le cookie contient l'ID utilisateur de l'utilisateur actuellement connecté.  |   Facebook                                                           |
| .facebook.com               | datr                     | Utilisé pour identifier le navigateur Web utilisé pour se connecter à Facebook indépendamment de l'utilisateur connecté. | Facebook                                                             |
| .facebook.com               | wd                       | Stocke les dimensions de la fenêtre du navigateur et est utilisé par Facebook pour optimiser le rendu de la page. | Facebook                                                             |
| .facebook.com               | xs                       | Numéro à deux chiffres représentant le numéro de session. La deuxième partie de la valeur est un secret de session. |  Facebook                                                            |
| .facebook.com               | fr                       | Contient un identificateur de navigateur et d'utilisateur uniques, utilisés pour la publicité ciblée. |  Facebook                                                            |
| .facebook.com               | sb                       | Utilisé pour améliorer les suggestions d'amis de Facebook.                                |  Facebook                                                            |
| .facebook.com               | spin                     |                                                              |  Facebook                                                            |
| .twitter.com                | guest_id                 |                                                              |  Twitter                                                            |
| .twitter.com                | kdt                      |                                                              |  Twitter                                                             |
| .twitter.com                | personalization_id       | Le cookie contient l'ID utilisateur de l'utilisateur actuellement connecté.  |  Twitter                                                             |
| .twitter.com                | remember_checked_on      |                                                              | Twitter                                                              |
| .twitter.com                | twid                     |                                                              |  Twitter                                                             |
| .pinterest.com              | \_auth                    | Le cookie contient l'ID utilisateur de l'utilisateur actuellement connecté.  |   Pinterest                                                           |
| .pinterest.com              | \_b                       |                                                              |   Pinterest                                                           |
| .pinterest.com              | \_pinterest_pfob          |                                                              |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_referrer      | Le cookie contient des pages lorsque l'utilisateur sélectionne le bouton Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_sess          | Le cookie contient des pages lorsque l'utilisateur sélectionne le bouton Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_routing_id              |                                                              |  Pinterest                                                            |
| .pinterest.com              | bei                      |                                                              |  Pinterest                                                            |
| .pinterest.com              | cm_sub                   | Contient un ID utilisateur et l'horodatage de la création du cookie. |  Pinterest                                                            |
| .pinterest.com              | csrftoken                | Le cookie contient des pages lorsque l'utilisateur sélectionne le bouton Pinterest.      | Pinterest                                                             |
| .pinterest.com              | sessionFunnelEventLogged | Le cookie contient des pages lorsque l'utilisateur sélectionne le bouton Pinterest.      | Pinterest                                                             |
| .pinterest.com              | Stockage local            |                                                              |  Pinterest                                                            |
| .pinterest.com              | Agents de service          |                                                              |  Pinterest                                                            |


## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Consentement aux cookies de l’utilisateur du site sur un site d’e-commerce 

Si une fonctionnalité ou un module de site d’e-commerce utilise un cookie non essentiel, le consentement de l’utilisateur du site doit être obtenu avant que le cookie ne soit suivi. Pour permettre aux utilisateurs du site de donner leur consentement aux cookies sur le site d’e-commerce, un auteur de site doit ajouter et configurer un module de consentement aux cookies dans le module d’en-tête de la page pour s’assurer que le consentement est demandé et reçu. Le consentement de l’utilisateur du site doit être donné avant qu’une fonctionnalité ou un module utilisant un cookie non essentiel puisse être affiché sur une page du site.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctionnalités d’accessibilité](accessibility.md)

[Vue d’ensemble de la conformité](compliance-overview.md)

[Ajouter une page de stratégie de confidentialité](add-privacy-page.md)

[Remplacer les ID utilisateur associés aux modifications de contenu suivies](replace-IDs-tracked-changes.md)

[Module de consentement aux cookies](cookie-consent-module.md) 
 
[Module En-tête](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
