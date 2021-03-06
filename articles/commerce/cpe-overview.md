---
title: Vue d’ensemble d’un environnement d’évaluation Dynamics 365 Commerce
description: Cette rubrique fournit une vue d’ensemble de l’environnement d’évaluation Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c890d7c49b6607ab0cbad536bbf8a3649465a7c1
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193490"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a>Vue d’ensemble d’un environnement d’évaluation Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d’ensemble de l’environnement d’évaluation Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Les environnements d’évaluation de Commerce ne sont pas en disponibilité générale et sont accordés aux partenaires et aux clients sur demande. Pour plus d’informations, contactez votre partenaire Microsoft.

L’environnement d’évaluation de Commerce est un environnement facultatif de bout en bout de Dynamics 365 Commerce qui permet aux partenaires et aux clients potentiels d’essayer le produit Commerce.

Les environnements d’évaluation sont partiellement préconfigurés pour réduire les étapes post-mise en service requises.

Mis à part quelques limitations mineures qui n’affectent pas les fonctionnalités, l’environnement d’évaluation Commerce fournit l’expérience Commerce complète et peut être utilisé par les clients et les partenaires de mise en œuvre pour évaluer le produit, fournir des commentaires et effectuer une analyse d’ajustement/des écarts.

## <a name="limitations-of-the-commerce-evaluation-environment"></a>Limitations de l’environnement d’évaluation de Commerce

Bien que l’environnement d’évaluation de Commerce fournisse l’ensemble complet des fonctionnalités de Commerce, il existe quelques limitations mineures :

- Bien que l’environnement d’évaluation Commerce lui-même n’ait aucune limitation géographique, des composants de l’environnement, tels que Retail Cloud Scale Unit (RCSU) et les applications de commerce électronique, ne peuvent être fournies qu’aux États-Unis.
- L’utilisation de l’environnement d’évaluation Commerce est limitée à 30 jours à compter de la date de mise en service du commerce électronique.
- L’environnement d’évaluation de Commerce ne peut être déployé et initialisé avec succès que dans un environnement qui utilise la topologie de démonstration, où tous les composants d’un environnement sont déployés sur une seule machine virtuelle hébergée dans le cloud. La principale limitation de cette topologie est le nombre d’utilisateurs simultanés que l’environnement d’évaluation peut prendre en charge.

## <a name="get-started"></a>Prise en main

Pour mettre en service l’environnement d’évaluation de Commerce, voir [Mise en service d’un environnement d’évaluation de Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Mettre en service un environnement d’évaluation Dynamics 365 Commerce](provisioning-guide.md)

[Configurer un environnement d’évaluation Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce](cpe-bopis.md)

[Configurer des fonctionnalités facultatives pour un environnement d’évaluation Dynamics 365 Commerce](cpe-optional-features.md)

[FAQ des environnements d’évaluation Dynamics 365 Commerce](cpe-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
