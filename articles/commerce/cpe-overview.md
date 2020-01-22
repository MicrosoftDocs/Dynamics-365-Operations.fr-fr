---
title: Vue d'ensemble d'un environnement d'évaluation Commerce
description: Cette rubrique fournit une vue d'ensemble de l'environnement d'aperçu Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 901583afde4739be5313fa129ff0e52f11326881
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906068"
---
# <a name="commerce-preview-environment-overview"></a>Vue d'ensemble d'un environnement d'évaluation Commerce

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d'ensemble de l'environnement d'aperçu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

L'environnement de prévisualisation Commerce est un environnement de prévisualisation de bout en bout facultatif de Dynamics 365 Commerce qui permet aux clients potentiels d'essayer le produit Commerce avant sa sortie générale.

Mis à part quelques limitations mineures qui n'affectent pas les fonctionnalités, l'environnement de prévisualisation Commerce fournit l'expérience Commerce complète et peut être utilisé par les clients et les partenaires de mise en œuvre pour évaluer le produit, fournir des commentaires et effectuer une analyse d'ajustement/des écarts.

## <a name="limitations-of-the-commerce-preview-environment"></a>Limitations de l'environnement d'aperçu de Commerce

Bien que l'environnement d'aperçu de Commerce fournisse l'ensemble complet des fonctionnalités de Commerce, il existe quelques limitations mineures :

- Bien que l'environnement de prévisualisation Commerce lui-même n'ait aucune limitation géographique, des composants de l'environnement, tels que Retail Cloud Scale Unit (RCSU) et les applications de commerce électronique, ne peuvent être fournies qu'aux États-Unis.
- L'utilisation de l'environnement de prévisualisation Commerce est limitée à 30 jours à compter de la date de mise en service du commerce électronique.
- L'environnement de prévisualisation Commerce ne peut être déployé et initialisé avec succès que dans un environnement qui utilise la topologie de démonstration, où tous les composants d'un environnement sont déployés sur une seule machine virtuelle. La principale limitation de cette topologie de machine virtuelle OneBox est le nombre d'utilisateurs simultanés que l'environnement d'aperçu peut prendre en charge.
- L'environnement de prévisualisation Commerce ne peut être évalué que jusqu'à la disponibilité générale (DG) du produit Commerce. De nouveaux environnements de démonstration seront disponibles après la DG.

## <a name="get-started"></a>Mise en route

Pour mettre en service l'environnement d'aperçu Commerce, voir [Mise en service d'un environnement d'aperçu Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Mettre en service un environnement d'évaluation Commerce](provisioning-guide.md)

[Configurer un environnement d'évaluation Commerce](cpe-post-provisioning.md)

[Configurer des fonctionnalités facultatives pour un environnement d'évaluation Commerce](cpe-optional-features.md)

[FAQ relative à l'environnement d'évaluation Commerce](cpe-faq.md)
