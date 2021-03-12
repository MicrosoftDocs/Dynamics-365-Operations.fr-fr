---
title: Conformité des cookies
description: Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 95c5801e69396b21a36c4ae12ce17801e6f7fd88
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993498"
---
# <a name="cookie-compliance"></a>Conformité des cookies

[!include [banner](includes/banner.md)]

Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

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

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Consentement aux cookies de l’utilisateur du site sur un site d’e-commerce 

Si une fonctionnalité ou un module de site d’e-commerce utilise un cookie non essentiel, le consentement de l’utilisateur du site doit être obtenu avant que le cookie ne soit suivi. Pour permettre aux utilisateurs du site de donner leur consentement aux cookies sur le site d’e-commerce, un auteur de site doit ajouter et configurer un module de consentement aux cookies dans le module d’en-tête de la page pour s’assurer que le consentement est demandé et reçu. Le consentement de l’utilisateur du site doit être donné avant qu’une fonctionnalité ou un module utilisant un cookie non essentiel puisse être affiché sur une page du site.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctionnalités d’accessibilité](accessibility.md)

[Vue d’ensemble de la conformité](compliance-overview.md)

[Ajouter une page de stratégie de confidentialité](add-privacy-page.md)

[Remplacer les ID utilisateur associés aux modifications de contenu suivies](replace-IDs-tracked-changes.md)

[Module de consentement aux cookies](cookie-consent-module.md) 
 
[Module En-tête](author-header-module.md)
