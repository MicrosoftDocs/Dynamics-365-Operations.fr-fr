---
title: Identifier une hypothèse et déterminer les métriques pour une expérience
description: Cette rubrique décrit comment identifier l'hypothèse et les métriques de réussite d'une expérience que vous exécuterez sur un site web d'e-commerce dans Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 99642861d69b7545f03c6ed2c2650eadeb377534
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930194"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a>Identifier une hypothèse et déterminer les métriques de réussite pour une expérience
La première phase du cycle de vie de l'expérimentation comprend l'identification de l'hypothèse de l'expérience et la détermination des métriques que vous suivrez pour évaluer la réussite. Le diagramme suivant montre toutes les étapes impliquées dans [la configuration et l'exécution d'une expérience](experimentation-overview.md) sur un site web d'e-commerce dans Dynamics 365 Commerce. Les étapes supplémentaires sont traitées dans d'autres rubriques. 

[ ![Expérimentation parcours utilisateur - Identifier](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)

Une hypothèse est une déclaration dans laquelle vous prédisez le résultat de l'expérience. De nombreux facteurs entrent dans la définition d'une hypothèse, par exemple, la recherche sur le comportement des utilisateurs et les données de site web que vous avez collectées. Avec l'hypothèse, vous définirez l'hypothèse ou la théorie que vous souhaitez valider avec votre expérience. Un exemple d'hypothèse pour votre expérience peut être "*une photo d'un t-shirt blanc sur ma page d'accueil entraînera un taux de clics plus élevé que celle d'un pull bleu marine pendant les mois d'été, car les gens veulent porter quelque chose de léger et de couleur claire en été.*" Dans ce cas, vous allez créer des variantes comprenant un t-shirt blanc et un pull bleu marine, et publier les deux en même temps.

Pour valider une hypothèse, la réussite ou l'échec d'une expérience doit être directement lié aux actions de l'utilisateur ; par exemple, si l'utilisateur du site web clique sur un lien ou un bouton. Ces actions doivent correspondre aux événements qui seront signalés au service tiers qui effectue le suivi de l'expérience. Au fil du temps, le pourcentage d'utilisateurs qui exécutent l'action sera comptabilisé comme une métrique que vous pouvez utiliser pour générer des rapports et effectuer des analyses. Reportez-vous à la rubrique [Événements des composants Commerce pour les diagnostics et le dépannage](dev-itpro/retail-component-events-diagnostics-troubleshooting.md) pour passer en revue tous les événements et attributs disponibles.

## <a name="previous-step"></a>Étape précédente
[Expérimentation dans Dynamics 365 Commerce](experimentation-overview.md)


## <a name="next-step"></a>Étape suivante
[Configurer une expérience](experimentation-setup.md)