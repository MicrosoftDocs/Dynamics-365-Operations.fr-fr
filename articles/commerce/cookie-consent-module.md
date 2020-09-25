---
title: Module de consentement aux cookies
description: Cette rubrique couvre les modules de consentement aux cookies et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 842096c6e3045e434aced9642c86690e2ff7483a
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761390"
---
# <a name="cookie-consent-module"></a>Module de consentement aux cookies

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de consentement aux cookies et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Le module de consentement des cookies invite les utilisateurs du site à donner explicitement leur consentement pour autoriser les cookies pour toute fonctionnalité ou module qui suit les cookies du navigateur. Le consentement est requis la première fois qu’un utilisateur du site navigue sur un site dans une nouvelle session de navigateur. Lorsque le consentement est reçu, il est suivi et l’utilisateur du site ne sera plus invité à donner son consentement. Pour plus d’informations, voir [Conformité des cookies](cookie-compliance.md).

Si le consentement aux cookies de l’utilisateur du site n’est pas obtenu, les fonctionnalités ou modules qui nécessitent le consentement aux cookies ne seront pas affichés sur la page. Par exemple, le module de paiement, le module de partage social et la fonctionnalité de magasin préféré nécessitent tous le consentement aux cookies et ne seront pas affichés si le consentement de l’utilisateur du site n’est pas obtenu. 

Un module de consentement aux cookies peut être configuré sur le fragment d’en-tête d’une page afin qu’il puisse être appliqué lors du chargement de la page. Le module de consentement aux cookies doit comporter un message clair informant l’utilisateur du site de l’utilisation des cookies sur le site et doit fournir un lien vers la page de protection des données personnelles du site.

L’illustration suivante met en évidence un exemple de message de consentement aux cookies avec un lien vers la page de politique de protection des données personnelles du site affiché sur l’en-tête d’une page de site.
![Exemple de module de consentement aux cookies](./media/ecommerce-cookieconsent.png)

## <a name="cookie-consent-module-properties"></a>Propriétés du module de consentement aux cookies

| Nom de la propriété             | Valeur                 | Description |
|---------------------------|-----------------------|-------------|
| Texte enrichi                  | Texte enrichi | Spécifie une notification de texte enrichi aux utilisateurs du site indiquant que le site utilise des cookies de navigateur et que les utilisateurs doivent accepter l’utilisation de cookies pour que le site soit pleinement fonctionnel. |
| Liens | URL | Un ou plusieurs liens peuvent être ajoutés à la page de protection des données personnelles d’un site qui décrit les types de cookies suivis sur le site. |

## <a name="add-a-cookie-consent-module-to-site-pages"></a>Ajouter un module de consentement aux cookies aux pages du site

Pour ajouter efficacement un module de consentement aux cookies à plusieurs pages du site, il peut être ajouté à un fragment d’en-tête de page partagé. Une fois le fragment d’en-tête ajouté à toutes les pages du site, une notification de consentement aux cookies sera automatiquement affichée la première fois qu’un utilisateur du site accède à une page du site.

Pour plus d’informations sur les fragments d’en-tête et les modules, voir [Module En-tête](author-header-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble du kit de démarrage](starter-kit-overview.md)

[Module En-tête](author-header-module.md) 

[Conformité des cookies](cookie-compliance.md)