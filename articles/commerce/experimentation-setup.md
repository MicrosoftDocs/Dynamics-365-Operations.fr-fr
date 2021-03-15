---
title: Configurer une expérience
description: Cette rubrique décrit comment configurer une expérience dans un service tiers.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 1a60eb459d6d6f710e43ac5418b9375420ca8387
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000780"
---
# <a name="set-up-an-experiment"></a>Configurer une expérience

Après avoir [défini une hypothèse et déterminé les métriques de réussite que vous souhaitez utiliser](experimentation-identify.md), vous devrez configurer votre expérience dans le service tiers. Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l'exécution d'une expérience sur un site web d'e-commerce dans Dynamics 365 Commerce. Les étapes supplémentaires sont traitées dans d'autres rubriques.

[ ![Expérimentation parcours utilisateur - Configurer](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Configurer votre expérience dans le service tiers
Vous devriez maintenant avoir choisi votre service tiers chargé d'exécuter et de surveiller votre expérience, et avoir configuré le connecteur d'expérimentation. Ces conditions préalables sont répertoriées dans [Expérimentation dans Dynamics 365 Commerce](experimentation-overview.md).

Suivez les étapes requises pour créer votre expérience dans le service tiers. Si le connecteur est correctement configuré, la liste complète des expériences que vous avez configurées dans le service tiers apparaîtra dans le générateur de site Commerce dans un délai d'environ 5 minutes.

## <a name="set-up-your-success-metrics"></a>Configurer vos métriques de réussite
Chaque expérience a besoin de métriques pour mesurer l'impact des variantes et valider l'hypothèse. Suivez les étapes ci-dessous pour activer le calcul des métriques dans le service tiers à l'aide des événements de télémétrie en ligne de Dynamics 365 Commerce.

Pour paramétrer vos métriques de réussite, procédez comme suit.

1. Dans le générateur de site Commerce, sélectionnez **Pages** dans le volet de navigation de gauche, puis sélectionnez la page pour laquelle vous souhaitez collecter des métriques. 
1. Accédez à la section **ID d'événement à suivre** dans le volet des propriétés situé à droite de la page ou du module dont vous souhaitez effectuer le suivi.
1. Sélectionnez **Afficher**. Une liste de tous les ID d'événement s'affiche. Copiez l'événement dont vous souhaitez effectuer le suivi et collez la clé d'événement à l'emplacement désigné dans le service tiers. Si vous avez besoin de plusieurs événements, copiez les clés une par une. 
    - Pour savoir comment afficher tous les événements et attributs disponibles, y compris les affichages de pages et le suivi des revenus, consultez [Événements des composants Commerce pour les diagnostics et le dépannage](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).
1. Prenez toutes les autres mesures requises dans le service tiers pour procéder au suivi des métriques.

## <a name="previous-step"></a>Étape précédente
[Identifier une hypothèse et déterminer les métriques pour une expérience](experimentation-identify.md) 


## <a name="next-step"></a>Étape suivante
[Connecter et modifier une expérience](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]