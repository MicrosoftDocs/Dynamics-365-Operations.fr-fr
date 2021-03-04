---
title: Utiliser les états analytiques dans Attract
description: Cette rubrique décrit les états analytiques pour obtenir des informations sur le processus de recrutement dans Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 081988e8b8cfe1e2ddb533247b678ba38a07f5f1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461192"
---
# <a name="use-analytic-reports-in-attract"></a>Utiliser les états analytiques dans Attract

[!include [banner](includes/banner.md)]

Les états analytiques dans Microsoft Dynamics 365 Talent: Attract fournissent une solution prête à l'emploi pour obtenir des informations sur le processus de recrutement. Les fonctionnalités disponibles comprennent :

- **Analyses du poste :** Cliquez sur l'onglet **Analyses** d'un poste pour obtenir des mesures sur le candidat à un poste.
- **Concentrateur d'analyses :** Cliquez sur **Analyses** sur la navigation de gauche pour obtenir des mesures globales pour tous les postes.
- **Sécurité spécifique à l'utilisateur :** L'accès aux états est contrôlé par le [rôle](security-attract.md) Attract et le rôle de participant à la mission.
- **Filtrage croisé :** Cliquez sur les visuels d'un état pour afficher d'autres mesures filtrées par des données sélectionnées.

>[!NOTE] 
>- Cette fonctionnalité est actuellement en [mode aperçu](access-preview-feature.md). Pour l'essayer, vous devez disposer du [**Module complémentaire Recrutement complet**](attract-comprehensive-hiring.md).
>- Tous les états en aperçu public sont affichés en anglais.
>- Les états sont actualisés toutes les 3 heures. La dernière heure d'actualisation (dans le fuseau horaire local) est située en haut de l'état. Les heures d'actualisation sont approximatives et varient en fonction du volume de données et de la charge des ressources dans votre région.

## <a name="job-analytics"></a>Analyse du poste

Les états Analyses du poste sont un instantané du processus d'embauche pour une mission.  Les mesures clés sont :

- Candidats actifs par stade
- Source de candidat
- Type de candidat (interne ou externe)

## <a name="analytics-hub"></a>Concentrateur d'analyses

Les états du Concentrateur d'analyses regroupent des données entre les postes pour fournit des tendances dans le processus de recrutement. Attract inclut deux états prêts à l'emploi : Récapitulatif des opportunités et Analyse en entonnoir.

### <a name="pipeline-summary"></a>Récapitulatif des opportunités

L'état Récapitulatif des opportunités regroupe les données des postes à pourvoir. Les mesures clés sont :

- Candidats à tous les postes par stade
- Source de candidat
- Postes à pourvoir par niveau d'ancienneté

### <a name="funnel-analysis"></a>Analyse en entonnoir

L'état Analyse en entonnoir regroupe des données pour des postes Fermés comme pourvus. Les mesures clés sont :

- Délai du recrutement
- Mesures de conversion (avec pointeur)
- Taux d'acceptation d'offre

Remarque : Pour obtenir des états sur les délais de recrutement les plus précis, il est conseillé d'utiliser [Gestion des offres](offer-setup.md), fonctionnalité disponible dans le cadre du Module complémentaire Recrutement complet.

>[!TIP] 
>Essayez de passer le pointeur de votre souris sur des visuels pour obtenir des informations supplémentaires. Par exemple, si vous passez votre pointeur sur **Candidats actifs**, les visuels affichent le nombre moyen de jours dans ce stade. L'analyse de ces informations peut fournir des informations critiques permettant de réduire le délai du recrutement et permettre aux recruteurs de se concentrer sur des façons de réduire le temps passé à chaque stade.

## <a name="user-specific-security"></a>Sécurité spécifique à l'utilisateur

Les états Attract sont accessibles par les [rôles](security-attract.md) Administrateur, Tout lire, Recruteur et Responsable du recrutement. Les utilisateurs non affectés n'ont pas accès aux pages des états d'analyses (Analyses du poste ou Concentrateur d'analyses).

Les états Analyses du poste affichent des données sur le poste sélectionné. Les états du Concentrateur d'analyses regroupent des données sur tous les postes qu'un utilisateur peut afficher. Les utilisateurs qui peuvent afficher Mes postes et Tous les postes sur la page Postes ont les vues disponibles dans le Concentrateur d'analyses.

## <a name="cross-filter"></a>Filtrage croisé

L'une des fonctionnalités importantes de Power BI est la façon dont tous les visuels sur une page d'état sont interconnectés. Si vous sélectionnez un point de données sur l'un des visuels, tous les autres visuels de la page qui contiennent ces données changent, selon cette sélection. Pour en savoir plus et voir un exemple dans [Filtrage croisé des visuels dans un état Power BI](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).

## <a name="export-to-excel"></a>Exporter vers Excel

Pour afficher les données d'un état dans Excel, vous pouvez cliquer sur le menu Options (trois points) d'un visuel et sélectionner **Exporter les données sous-jacentes**. Les données exportées s'exporteront filtrées, en fonction des autorisations de l'utilisateur dans Attract. Pour plus d'informations, voir [Exporter à partir des visualisations](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).


[!INCLUDE[footer-include](../includes/footer-banner.md)]