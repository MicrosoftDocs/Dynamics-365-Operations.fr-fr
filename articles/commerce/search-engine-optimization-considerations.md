---
title: Considérations relatives à l'optimisation de moteur de recherche (SEO) pour le site
description: Cette rubrique couvre des considérations sur l'optimisation du moteur de recherche (SEO) pour votre site du développement à la production.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b35d0cb606e1b17a0258ea3fcb6287988d83091c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698209"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Considérations relatives à l'optimisation de moteur de recherche (SEO) pour le site

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les considérations sur l'optimisation du moteur de recherche (SEO) pour votre site du développement à la production.

## <a name="a-site-that-is-under-development"></a>Site en cours de développement

Lorsqu'un site est cours de développement, toutes les pages du site doivent avoir des métabalises **NOINDEX** et **NOFOLLOW**, de sorte que les moteurs de recherche n'indexent pas les pages ni ne stockent les versions de développement de votre site dans leur cache. Pour effectuer cette configuration, vous devez ajouter le module par défaut de métabalises au modèle de page du site. Les propriétés par défaut de métabalises sont alors disponibles dans la section des propriétés SEO dans l'éditeur de page. Vous pouvez utiliser ces propriétés pour gérer les métabalises.

## <a name="soft-launch-of-a-site"></a>Lancement provisoire un site

Pendant « un lancement provisoire », un site web est rendu disponible à une audience ou à un marché limité avant que le lancement complet se produise. Si vous effectuez un lancement provisoire de votre site web, vous devez envisager de laisser les métabalises **NOINDEX** en place. Ainsi, vous garantissez que le lancement provisoire reste limité à l'audience limitée que vous souhaitez atteindre.

## <a name="a-site-that-is-in-production"></a>Un site qui est en production

Lorsqu'un site est en production, vous devez vous assurer que toutes les pages du site sont correctement référencées. Microsoft Dynamics 365 Commerce utilise les informations entrées pour une page pour afficher toutes les informations SEO dans cette page. Les modules suivants fournissent cette fonctionnalité : synthèse de page de catégorie, synthèse de la page de liste, et synthèse de la page de produit.

Pour optimiser l'indexation du moteur de recherche, la zone de rendu utilise les informations des propriétés SEO configurées dans Dynamics 365 Commerce et les informations spécifiques au module. Pour un site qui est en production, vous devez vous assurer que le fichier robots.txt permet l'indexation du site entier, et qu'il contient des liens vers votre document de plan de site publié. Vous devez activer la fonctionnalité de génération de plan de site dans **Paramètres du site \> Plans de site activés**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Paramètres SEO de la page pour un aperçu interne, audiences limitées, toutes les audiences

Comme Dynamics 365 Commerce prend en charge des aperçus authentifiés « Tel écrit, tel écran », les auteurs pouvez préparer leur contenu de page sans devoir s'inquiéter que les informations deviennent visibles des visiteurs de site. Si une page doit être publiée, mais que son exposition doit être limitée, elle doit avoir la métabalise **NOINDEX**, afin qu'elle ne soit pas indexée par les moteurs de recherche. Puis, lorsque la page est prête pour toutes les audiences, toutes les métadonnées SEO de base doivent être présentes, afin d'optimiser l'efficacité de l'indexation du moteur de recherche. En outre, la métabalise **NOLIMIT** doit être supprimée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Gestion des utilisateurs et des rôles de commerce électronique](manage-ecommerce-users-roles.md)

[Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)

[Gérer la stratégie de sécurité de contenu (CSP)](manage-csp.md)
