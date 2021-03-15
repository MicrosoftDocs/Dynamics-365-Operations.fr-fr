---
title: Vue d'ensemble de réapprovisionnement
description: Cette rubrique décrit les stratégies de réapprovisionnement disponibles pour les entrepôts qui utilisent la fonctionnalité qui est disponible dans Gestion des entrepôts.
author: Mirzaab
manager: tfehr
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSReplenishmentTemplates, WHSInventFixedLocation, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 90043
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d554a6d415ca3e720c71387e218e50215c288991
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996071"
---
# <a name="replenishment-overview"></a>Vue d'ensemble de réapprovisionnement

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les stratégies de réapprovisionnement disponibles pour les entrepôts qui utilisent la fonctionnalité qui est disponible dans Gestion des entrepôts. Ces informations dans cette rubrique ne s'appliquent pas à la solution de stockage disponible dans la Gestion des stocks.

Les stratégies de réapprovisionnement suivantes sont disponibles :

- **Réapprovisionnement de la demande de vague** : Cette stratégie crée un travail de réapprovisionnement pour les commandes ou les charges sortantes si le stock n'est pas disponible lorsque le travail est créé par la vague. Par exemple, le travail de réapprovisionnement peut être créé si la quantité requise pour une commande client n'est pas disponible lors du traitement d'une vague.
- **Réapprovisionnement minimal et maximal** : Cette stratégie utilise les limites de stockage minimales et maximales pour déterminer quand réapprovisionner les emplacements. Les critères d'article et d'emplacement définissent le stock qui est évalué pour le réapprovisionnement. Les modèles de réapprovisionnement minimal et maximal constituent le mécanisme principal tenir maintenir des niveaux optimaux dans les emplacements d'enlèvement. Pour garantir la disponibilité du stock d'enlèvement pour répondre à la demande de vague, vous pouvez utiliser le réapprovisionnement comme complément entre les cycles de réapprovisionnement Min/Max.
- **Réapprovisionnement de demande de chargement** : Cette stratégie additionne la demande de plusieurs chargements et crée le travail de réapprovisionnement qui est nécessaire pour stocker les emplacements d'enlèvement correspondants. Cette stratégie permet de garantir que les chargements qui sont créés peuvent être enlevés dans l’entrepôt une fois qu’ils sont disponibles.
- **Réapprovisionnement immédiat** – Cette stratégie réapprovisionne le stock avant l'exécution d'une vague si l'allocation échoue pour une ligne d'introduction d'emplacement disposant d'un modèle de réapprovisionnement. 

Ces quatre stratégies créent un travail de réapprovisionnement, basé sur un modèle de réapprovisionnement.

## <a name="wave-demand-replenishment"></a>Réapprovisionnement de la demande de vague
Le réapprovisionnement de la demande de vague crée un travail de réapprovisionnement basé sur la demande, si la quantité requise pour les ordres de fabrication, les kanbans, les commandes ou les chargements sortants n'est pas disponible lorsque le travail est créé par la vague. Le modèle de réapprovisionnement contient des informations sur les critères de l’article, l’unité de mesure, l’incrément de la demande et l’emplacement. 

Des directives d’emplacement permettent de déterminer l’emplacement à réapprovisionner. Vous liez ces directives d’emplacement au modèle de réapprovisionnement à l’aide du champ **Code instructions**. Si le champ **Code instructions** n’est pas défini, des requêtes sont utilisées pour déterminer à quel emplacement loa directive doit être utilisée. Notez que si un code instructions n’est pas spécifié dans le modèle de réapprovisionnement, et que la directive d’emplacement a un code instructions, la directive d’emplacement sera ignorée, même si la requête sur la directive de l’emplacement est correcte. Les directives d'emplacement d'enlèvement permettent de déterminer où obtenir des stocks pour le réapprovisionnement. 

En plus de créer un modèle, vous devez spécifier certains paramètres de réapprovisionnement dans le modèle de vague. Le modèle de vague doit contenir une étape de vague pour le réapprovisionnement qui s’exécute uniquement si l’allocation d’un article n’est pas réussie. Cette étape de vague de réapprovisionnement utilise un code d’étape de vague pour déterminer quel modèle de réapprovisionnement utiliser. En plus d’avoir une étape de vague de réapprovisionnement, vous devez vous assurer que **Réapprovisionner** est sélectionné dans la section **Méthodes** du modèle de vague. 

La page **Modèle de réapprovisionnement** inclut une case à cocher **Autoriser la demande de vague pour utiliser des quantités non réservées**. Celle-ci doit être activée si vous souhaitez que le réapprovisionnement de demande déduise les quantités non réservées du travail généré à partir du modèle de réapprovisionnement sélectionné. Pour autoriser les modèles de réapprovisionnement de demande à utiliser cette logique, activez cette case à cocher pour chaque modèle de réapprovisionnement existant. Lorsque le réapprovisionnement de demande est lancé dans l'entrepôt, le système déduira la demande du travail de réapprovisionnement existant avec des quantités non réservées, si l'option **Autoriser la demande de vague à utiliser les quantités non réservées** est activée dans le travail issu des modèles de réapprovisionnement.

**Unité de réapprovisionnement** est l'unité minimale à réapprovisionner. Ce doit être un nombre entier qui est un multiple de l'unité. Le système arrondira à l'unité la plus élevée possible lors de la création du travail.

Le réapprovisionnement de demande est pris en charge pour les commandes client, les ordres de transfert, les ordres de fabrication et les kanbans. 

## <a name="minmax-replenishment"></a>Réapprovisionnement minimal/maximal
Dans Réapprovisionnement minimal/maximal, le stock est réapprovisionné afin qu’il soit entre les limites maximales et minimales qui ont été définies. En général, ce processus se produit une fois par jour pour garantir que tous les emplacements d'enlèvement soient remplis au maximum avant que l'enlèvement commence. 

Les montants minimaux et maximaux sont définis dans un modèle de réapprovisionnement. De nombreux autres paramètres du modèle sont semblables aux paramètres des modèles qui sont utilisés dans le réapprovisionnement de la demande de vague. Le modèle doit contenir une ligne pour chaque article et chaque emplacement. Lorsque vous exécutez le réapprovisionnement à l'aide du traitement par lots, le système évalue si le réapprovisionnement est requis dans l'ordre dans lequel les lignes sont organisées. 

Notez que la stratégie de réapprovisionnement minimal/maximal ne peut pas réapprovisionner un emplacement vide, sauf si l’emplacement est défini comme emplacement fixe pour l’article. Si l’emplacement qui doit être réapprovisionné n’est pas un emplacement fixe, le système ne peut pas déterminer quel article doit être réapprovisionné. Par conséquent, au moins une partie de la quantité disponible est nécessaire avant le réapprovisionnement.

## <a name="load-demand-replenishment"></a>Réapprovisionnement de demande de chargement
Le réapprovisionnement de demande de chargement additionne la demande de plusieurs chargements et crée le travail de réapprovisionnement qui est nécessaire pour stocker les emplacements d'enlèvement correspondants. Le réapprovisionnement de demande de chargement ressemble au réapprovisionnement de demande de vague de nombreuses façons. La principale différence est la manière et lieu où le réapprovisionnement de la demande de chargement et le réapprovisionnement de la demande de vague sont exécutés. Comme le réapprovisionnement minimal/maximal, le réapprovisionnement de la demande de chargement est exécuté à l’aide d’un traitement par lots. Pour configurer le traitement par lots, sur la page **Réapprovisionnement de la demande de chargement**, sélectionnez le modèle de réapprovisionnement à utiliser et définissez une requête de filtre pour indiquer les chargements utilisés pour déterminer la demande. La requête d’emplacement définit les emplacements dont toutes les quantités disponibles seront soustraites pour satisfaire la demande agrégée de chargements.

## <a name="immediate-replenishment"></a>Réapprovisionnement immédiat
Au lieu de devoir ajouter la demande à la fin d'un processus de répartition et effectuer le réapprovisionnement sur la base de la quantité récapitulative, vous pouvez appliquer la stratégie de réapprovisionnement automatique. Lorsque vous utilisez cette stratégie, le stock peut être réapprovisionné immédiatement après qu'une ligne d'instruction d'emplacement échoue. Par conséquent, vous pouvez configurer le réapprovisionnement afin qu'il soit limité par des unités spécifiques et qu'il utilise des quantités définies pour des emplacements spécifiques.

## <a name="replenishment-prerequisites"></a>Conditions prérequises du réapprovisionnement

|      Logiciel requis       |                                                                                                                                Description                                                                                                                                 |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          Article           |                                                                                                        L'article doit être activé pour les processus de gestion des entrepôts.                                                                                                        |
|        Entrepôt        | L'entrepôt doit être activé pour les processus de gestion des entrepôts. Pour activer un entrepôt pour les processus de gestion des entrepôts, dans la page <strong>Entrepôts</strong>, sélectionnez l'entrepôt, puis activez l'option <strong>Utiliser les processus de gestion des entrepôts</strong>. |
| Modèles de réapprovisionnement |                                                                   Au moins un modèle de réapprovisionnement doit être configuré pour le réapprovisionnement minimal/maximal, le réapprovisionnement de la demande de vague ou le réapprovisionnement de la demande de chargement.                                                                   |
|        Lieux        |                                                                                                       Les emplacements doivent être créés et associés à un profil d’emplacement.                                                                                                       |
|    Profils d'emplacement    |                                                                                                        Les profils d’emplacement sont nécessaires pour créer des emplacements.                                                                                                        |
|   Instructions d'emplacement   |                                                       Les instructions d’emplacement sont nécessaires pour guider le travail vers les emplacements où le réapprovisionnement est requis et vers les emplacements d'où est tiré le stock.                                                        |
|     Modèles de travail      |                                                   Les modèles de travail du type <strong>Réapprovisionnement</strong> sont requis pour créer le travail de réapprovisionnement afin que le stock puisse être déplacé vers les emplacements souhaités.                                                    |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]