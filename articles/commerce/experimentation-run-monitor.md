---
title: Exécuter et surveiller une expérience
description: Cet article décrit comment exécuter et surveiller une expérience dans un service tiers. Elle décrit également comment apporter des modifications aux variantes après le début de l’expérience.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: c9f62c97b46fa00791de52b2804dad5edde7f625
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909581"
---
# <a name="run-and-monitor-an-experiment"></a>Exécuter et surveiller une expérience

Cet article décrit comment exécuter et surveiller votre expérience dans une application tierce et modifier les variantes si nécessaire. Avant d’effectuer les étapes de cet article, vous devez tout d’abord [publier](experimentation-preview-publish.md) votre expérience dans Commerce. 

Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l’exécution d’une expérience sur un site web d’e-commerce dans Dynamics 365 Commerce. Les étapes supplémentaires sont traitées dans d’autres articles.

[ ![Expérimentation parcours utilisateur - Exécuter et surveiller.](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)

Une fois que vous avez publié vos variantes, toutes les étapes à suivre dans Commerce pour exécuter votre expérience sont terminées. L’étape suivante consiste à déterminer la variante à montrer à chaque utilisateur lorsqu’il demande une page. Le service tiers effectue cette détermination, mais vous devez d’abord activer l’expérience dans le service. Étant donné que les étapes d’activation d’une expérience varient d’un service à l’autre, vous devrez suivre les instructions fournies avec votre service ou fournisseur. Si l’expérience n’est pas activée, les utilisateurs ne verront que la version par défaut de la page (aucune variante ne sera affichée).

Vous devrez prolonger l’expérience suffisamment longtemps pour collecter des données et obtenir des résultats statistiquement valides. Utilisez le service tiers pour surveiller les données et les analyses liées à l’expérience pendant l’exécution de l’expérience.

## <a name="adjust-your-variations"></a>Ajuster vos variantes
Si vous devez modifier vos variantes, suivez les étapes ci-dessous.

> [!IMPORTANT]
> Si vous apportez des modifications à une expérience en cours dans Commerce ou dans le service tiers, vos résultats peuvent être considérablement affectés. Envisagez de laisser l’expérience suivre son cours, puis de créer une nouvelle expérience pour les changements majeurs.

1. Dans le générateur de site Commerce, sélectionnez **Expériences** dans le volet de navigation de gauche, puis sélectionnez l’expérience. 
1. Sélectionnez la variante que vous souhaitez mettre à jour dans le menu déroulant.
1. Apportez les modifications nécessaires, puis affichez un aperçu et publiez les variantes. Pour plus d’informations, consultez [Afficher un aperçu et publier une expérience](experimentation-preview-publish.md).
1. Accédez au service tiers pour apporter des modifications liées à la configuration de l’expérience.
    
## <a name="previous-step"></a>Étape précédente
[Afficher un aperçu et publier une expérience](experimentation-preview-publish.md)

## <a name="next-step"></a>Étape suivante
[Promouvoir une variante et terminer une expérience](experimentation-review-complete.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]