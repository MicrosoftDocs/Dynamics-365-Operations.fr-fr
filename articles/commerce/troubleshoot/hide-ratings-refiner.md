---
title: L'affinement des évaluations apparaît sur les résultats de recherche et les pages de catégorie lorsque la solution d'évaluations et d'avis n'est pas activée
description: Cet article fournit des conseils de résolution de problème sur la façon de masquer l'affinement des évaluations sur les pages de résultats de recherche et de catégorie lorsque la solution d'évaluations et d'avis Microsoft Dynamics 365 Commerce n'est pas activée pour un site de commerce électronique.
author: gvrmohanreddy
manager: annbe
ms.date: 09/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c35e176fc5673de194a81a3a4694a83f7bc9aa00
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885056"
---
# <a name="ratings-refiner-appears-on-search-results-and-category-pages-when-the-ratings-and-reviews-solution-isnt-enabled"></a>L'affinement des évaluations apparaît sur les résultats de recherche et les pages de catégorie lorsque la solution d'évaluations et d'avis n'est pas activée

[!include [banner](../includes/banner.md)]

Cet article fournit des conseils de résolution de problème sur la façon de masquer l'affinement des évaluations sur les pages de résultats de recherche et de catégorie lorsque la solution d'évaluations et d'avis Microsoft Dynamics 365 Commerce n'est pas activée pour un site de commerce électronique.

## <a name="description"></a>Description

L'affinement des évaluations apparaît sur les pages de résultats de recherche et de catégories dans un canal de commerce électronique qui n'utilise pas la solution d'évaluations et d'avis.

## <a name="resolution"></a>Résolution

### <a name="enable-the-hide-rating-setting-in-commerce-site-builder"></a>Activer le paramètre Masquer l'évaluation dans le générateur de site Commerce

Pour activer le paramètre **Masquer les évaluations** dans le générateur de site Commerce, afin que l'affinement des évaluations soit masqué dans les pages de résultats de recherche et de catégorie, procédez comme suit.

1. Accédez à **Paramètres du site \> Extensions**.
1. Sous **Évaluations et avis**, cochez la case **Masquer les évaluations**.
1. Sélectionnez **Enregistrer et publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des évaluations et avis](../ratings-reviews-overview.md)

[Choix d’utilisation des évaluations et avis](../opt-in-ratings-reviews.md)
