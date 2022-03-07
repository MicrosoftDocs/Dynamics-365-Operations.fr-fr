---
title: Ensembles de dimensions financières
description: Cette rubrique décrit les ensembles de dimensions financières et fournit quelques conseils pour optimiser leur utilisation.
author: yukonpeegs
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ba11be028ebeea140df93e2a07dbb463402e3ef0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021826"
---
# <a name="financial-dimension-sets"></a>Ensembles de dimensions financières

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les ensembles de dimensions financières et fournit quelques conseils pour optimiser leur utilisation.

Un ensemble de dimensions est une liste ordonnée de dimensions financières qui peut être utilisée pour résumer les données de comptabilité d'une manière définie par l'utilisateur. Une des principales utilisations des ensembles de dimensions consiste à définir une balance comptable.

Le seul ensemble de dimensions standard est l'ensemble de dimensions qui contient uniquement le compte principal.

Vous utilisez la page **Ensembles de dimensions financières** pour créer et gérer des ensembles de dimensions financières.

## <a name="dimension-set-balances"></a>Soldes des ensembles de dimensions

Un ensemble de dimensions peut avoir des soldes basés sur ses dimensions financières. Les soldes existent dans la comptabilité et sont basés sur la définition de l'ensemble de dimensions. Les soldes sont résumés à partir des données de la comptabilité pour améliorer les performances de leur extraction (par exemple, lorsqu'une balance comptable est générée).

## <a name="create-balances"></a>Créer des soldes

Utilisez le bouton **Créer des soldes** pour initialiser les soldes pour un ensemble de dimensions qui ne dispose pas actuellement de soldes.

> [!NOTE]
> Nous vous recommandons de limiter le nombre d'ensembles de dimensions qui ont des soldes, car les mises à jour des soldes affectent toutes les activités de validation de la comptabilité.

## <a name="update-balances"></a>Mettre à jour les soldes

Utilisez le bouton **Mettre à jour les soldes** pour inclure la dernière activité de validation de la comptabilité dans les soldes. Les mises à jour des soldes sont des opérations légères. Elles ne doivent traiter que l'activité de validation de la comptabilité qui s'est produite depuis la dernière mise à jour.

> [!NOTE]
> L'affichage de la balance comptable force une mise à jour, pour s'assurer que les soldes affichés sont à jour. Pensez à implémenter un traitement par lots récurrent afin que les mises à jour de vos ensembles de dimensions les plus fréquemment utilisés soient rapides. De cette manière, vous réduirez le temps d'attente des utilisateurs de la balance comptable.

## <a name="rebuild-balances"></a>Recréer les soldes

Utilisez le bouton **Reconstruire les soldes** pour recréer les soldes à partir de zéro. De cette manière, vous vous assurez qu'ils correspondent aux données de la comptabilité. Une reconstruction des soldes nécessite beaucoup de traitement et ne devrait généralement pas être nécessaire.

> [!NOTE]
> Si vous avez un scénario qui nécessite de reconstruire les soldes régulièrement, nous vous recommandons de contacter le support client. Il pourra vous aider à déterminer pourquoi les soldes ne correspondent pas aux données de la comptabilité.

## <a name="clear-balances"></a>Effacer les soldes

Utilisez le bouton **Effacer les soldes** pour supprimer les soldes et arrêter toute mise à jour ultérieure. L'ensemble de dimensions n'aura plus d'impact sur les activités de validation de la comptabilité.

Pour plus d'informations, voir [Dimensions financières](financial-dimensions.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
