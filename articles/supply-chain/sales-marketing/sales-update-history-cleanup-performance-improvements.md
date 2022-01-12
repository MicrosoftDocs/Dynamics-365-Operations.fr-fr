---
title: Améliorations des performances du nettoyage de l’historique des ventes
description: Cette rubrique décrit la fonctionnalité d’amélioration des performances de nettoyage de l’historique des ventes et comment l’activer.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 610f0d4e0448dd21d10765400f25cd89e3c7a84b
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920271"
---
# <a name="sales-history-cleanup-performance-improvements"></a>Améliorations des performances du nettoyage de l’historique des ventes

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.24 -->

Le traitement par lots périodique du **nettoyage de l’historique des ventes** peut prendre beaucoup de temps s’il est rarement exécuté dans les environnements avec un volume important de mises à jour des ventes. Dans ces situations, la fonctionnalité *Améliorations des performances de nettoyage de l’historique des ventes* peut aider à réduire la durée d’exécution et à améliorer la fiabilité.

La fonctionnalité améliore le travail de nettoyage existant des manières suivantes :

- Il divise le nettoyage en lots (vous pouvez modifier la taille du lot via des personnalisations).
- Il fonctionnera pendant un maximum de 2 heures (vous pouvez modifier la durée via les personnalisations).
- Dans la mesure du possible, les capacités de la base de données seront exploitées pour réduire les conflits de blocage et éviter de joindre des tables transactionnelles pendant le nettoyage.

Après avoir activé la fonctionnalité, le traitement par lots **Nettoyage de l’historique des mises à jour des ventes** (**Ventes et marketing \> Tâches périodiques \> Nettoyer \> Nettoyage de l’historique des mises à jour des ventes**) fonctionnera comme avant, mais avec de meilleures performances et pour un maximum de 2 heures. Cela signifie qu’il peut avoir besoin de s’exécuter plusieurs fois pour nettoyer toutes les données pendant une période de conservation spécifique.

## <a name="turn-on-the-sales-history-cleanup-performance-improvements-feature"></a>Activer la fonctionnalité d’amélioration des performances de nettoyage de l’historique des ventes

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Ventes et marketing*
- **Nom de la fonctionnalité :** *Améliorations des performances de nettoyage de l’historique des ventes*
