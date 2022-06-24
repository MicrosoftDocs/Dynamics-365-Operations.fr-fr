---
title: Considérations relatives à l’optimisation de moteur de recherche (SEO) pour le site
description: Cet article couvre des considérations sur l’optimisation du moteur de recherche (SEO) pour votre site du développement à la production.
author: psimolin
ms.date: 05/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: 6747df3c56fb05248210f78ebf2176a56ce78329
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896899"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Considérations relatives à l’optimisation de moteur de recherche (SEO) pour le site


[!include [banner](includes/banner.md)]

Cet article couvre des considérations sur l’optimisation du moteur de recherche (SEO) pour votre site du développement à la production.

## <a name="a-site-that-is-under-development"></a>Site en cours de développement

Pour s’assurer que les moteurs de recherche n’indexent pas un site en cours de développement, toutes les pages du site doivent avoir les balises méta **noindex** et **nofollow**. Une bonne pratique consiste à créer un fragment basé sur le [module MetaTags](metatags-module.md) qui contient l’entrée de balise méta suivante et assurez-vous que le fragment est ajouté à la section HTML \<head\> de tous les modèles utilisés sur votre site.

```html
<meta name="robots" content="noindex,nofollow" /> 
```

## <a name="soft-launch-of-a-site"></a>Lancement provisoire un site

Pendant « un lancement provisoire », un site web est rendu disponible à une audience ou à un marché limité avant que le lancement complet se produise. Si vous effectuez un lancement provisoire de votre site web, vous devez envisager de laisser les métabalises **noindex** en place. Ainsi, vous garantissez que le lancement provisoire reste limité à l’audience limitée que vous souhaitez atteindre.

## <a name="a-site-that-is-in-production"></a>Un site qui est en production

Lorsqu’un site est en production, vous devez vous assurer que toutes les pages du site sont correctement référencées. Microsoft Dynamics 365 Commerce utilise les informations entrées pour une page pour afficher toutes les informations SEO dans cette page. Les modules suivants fournissent cette fonctionnalité : synthèse de page de catégorie, synthèse de la page de liste, et synthèse de la page de produit.

Pour optimiser l’indexation du moteur de recherche, la zone de rendu utilise les informations des propriétés SEO configurées dans Dynamics 365 Commerce et les informations spécifiques au module. Pour un site qui est en production, vous devez vous assurer que le fichier robots.txt permet l’indexation du site entier, et qu’il contient des liens vers votre document de plan de site publié. Vous devez activer la fonctionnalité de génération de plan de site dans **Paramètres du site \> Plans de site activés**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Paramètres SEO de la page pour un aperçu interne, audiences limitées, toutes les audiences

Comme Dynamics 365 Commerce prend en charge des aperçus authentifiés « Tel écrit, tel écran » dans le générateur de page visuel, les auteurs peuvent préparer leur contenu de page sans devoir s’inquiéter que les informations deviennent visibles par les visiteurs du site. Si une page doit être validée, mais que son exposition doit être limitée, elle doit avoir la métabalise **noindex**, afin qu’elle ne soit pas indexée par les moteurs de recherche. Puis, lorsque la page est prête pour toutes les audiences, toutes les métadonnées SEO de base doivent être présentes, afin d’optimiser l’efficacité de l’indexation du moteur de recherche. En outre, la métabalise **nolimit** doit être supprimée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Gestion des utilisateurs et des rôles de commerce électronique](manage-ecommerce-users-roles.md)

[Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)

[Gérer la stratégie de sécurité de contenu (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
