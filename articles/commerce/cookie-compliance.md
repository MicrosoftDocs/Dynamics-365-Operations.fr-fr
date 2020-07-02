---
title: Conformité des cookies
description: Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e1fa016dc9f46b048220f0f83e4b0783087de91e
ms.sourcegitcommit: c66c4c67a21e7d7d3a94a3fd766c3184b6e65c4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2020
ms.locfileid: "3446911"
---
# <a name="cookie-compliance"></a>Conformité des cookies

[!include [banner](includes/banner.md)]

Cette rubrique décrit les considérations relatives à la conformité des cookies et les stratégies par défaut incluses dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

La confidentialité est un facteur important lorsque les technologies de suivi affectent les clients e-commerce. En raison des normes de respect de la vie privée telles que le Règlement général sur la protection des données (RGPD) dans l'Union européenne (UE), les directives de confidentialité électroniques doivent être prises en compte pour tout site actif aujourd'hui. Étant donné que de nombreux sites de commerce électronique sont accessibles par défaut à l'échelle mondiale, il est important que vous examiniez les normes de conformité de votre site de commerce électronique.

Pour en savoir plus sur les principes de base utilisés par Microsoft pour la conformité des cookies, visitez le [Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center). Sur ce site, vous pouvez également obtenir plus d'informations sur les domaines de conformité et de gestion de la confidentialité.

Le tableau suivant montre la liste de référence actuelle des cookies placés par les sites Dynamics 365 Commerce.

| Nom du cookie                               | Utilisation                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| .AspNet.Cookies                             | Cookies d'authentification Store Microsoft Azure Active Directory (Azure AD) pour l'authentification unique (SSO). Stocke les informations chiffrées de l'utilisateur principal (nom, prénom, e-mail). |
| &#95;msdyn365___cart&#95;                           | ID du panier de magasin utilisé pour obtenir la liste des produits ajoutés à l'instance du panier. |
| &#95;msdyn365___ucc&#95;                            | Suivi du consentement de conformité des cookies.                          |
| ai_session                                  | Détecte le nombre de sessions d'activité de l'utilisateur qui ont inclus certaines pages et fonctionnalités de l'application. |
| ai_user                                     | Détecte le nombre de personnes qui ont utilisé l'application et ses fonctionnalités. Les utilisateurs sont comptés à l'aide d'ID anonymes. |
| b2cru                                       | Stocke l'URL de redirection de manière dynamique.                              |
| JSESSIONID                                  | Utilisé par le connecteur de paiement Adyen pour stocker la session utilisateur.       |
| OpenIdConnect.nonce.&#42;                       | Authentification                                               |
| x-ms-cpim-cache:.&#42;                          | Utilisé pour maintenir l'état de la demande.                      |
| x-ms-cpim-csrf                              | Jeton de falsification de requête intersites (CRSF) utilisé pour la protection contre CRSF.     |
| x-ms-cpim-dc                                | Utilisé pour acheminer les demandes vers l'instance de serveur d'authentification de production appropriée. |
| x-ms-cpim-rc.&#42;                              | Utilisé pour acheminer les demandes vers l'instance de serveur d'authentification de production appropriée. |
| x-ms-cpim-slice                             | Utilisé pour acheminer les demandes vers l'instance de serveur d'authentification de production appropriée. |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Utilisé pour maintenir la session SSO.                        |
| x-ms-cpim-trans                             | Utilisé pour le suivi des transactions (le nombre d'onglets ouverts s'authentifiant sur un site B2C), y compris la transaction en cours. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctionnalités d'accessibilité](accessibility.md)

[Vue d'ensemble de la conformité](compliance-overview.md)

[Ajouter une page de stratégie de confidentialité](add-privacy-page.md)

[Remplacer les ID utilisateur associés aux modifications de contenu suivies](replace-IDs-tracked-changes.md)
