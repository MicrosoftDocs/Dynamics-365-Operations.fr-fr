---
title: Hiérarchie d’organisation dans Dataverse
description: Cette rubrique décrit l’intégration des données organisationnelles entre les applications Finances et Opérations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9174612743c68595d12dd223f0932ace1857c0fb
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358362"
---
# <a name="organization-hierarchy-in-dataverse"></a>Hiérarchie d’organisation dans Dataverse

[!include [banner](../../includes/banner.md)]



Comme Dynamics 365 Finance est un système financier, l’*organisation* est un concept de base, et le système commence par la configuration d’une hiérarchie d’organisation. Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l’organisation et également à tous les niveaux de la hiérarchie d’organisation.

Bien que Dataverse ne dispose pas du concept de hiérarchie d’organisation, il dispose de certains concepts flous, tels que le total du produit des ventes. Dans le cadre de l’intégration de Dataverse, la structure de données de la hiérarchie d’organisation est ajoutée à Dataverse.

## <a name="data-flow"></a>Flux de données

Écosystème commercial composé des applications Finances et Opérations et Dataverse continue d’avoir une hiérarchie d’organisation. Cette hiérarchie d’organisation repose sur les applications Finances et Opérations, mais elle est exposée dans Dataverse à des fins d’informations et d’extensibilité. L’illustration suivante présente les informations de la hiérarchie d’organisation exposées dans Dataverse comme un flux unidirectionnel entre les applications Finances et Opérations et Dataverse.

![Image de l’architecture.](media/dual-write-data-flow.png)

Des mises en correspondance de la table Hiérarchie d’organisation sont disponibles pour la synchronisation unidirectionnelle des données entre les applications Finances et Opérations et Dataverse.

## <a name="templates"></a>Modèles

Une organisation est un groupe de personnes qui travaillent ensemble pour réaliser un processus entreprise ou atteindre un objectif. Les hiérarchies organisationnelles représentent les relations entre les organisations qui composent votre entreprise. Vous pouvez définir les types suivants d’organisations internes : entités juridiques, sections et équipes. Comme le montre le tableau suivant, une collection de mises en correspondance de table est créée pour synchroniser les entités juridiques, les unités opérationnelles et les informations de hiérarchie d’organisation associées.

Applications de Finances et Opérations | Applications Customer Engagement     | Description
-----------------------|--------------------------------|---
[Entités juridiques](mapping-reference.md#102) | cdm_companies | 
[Entités juridiques](mapping-reference.md#142) | msdyn_internalorganizations |
[Unité opérationnelle](mapping-reference.md#143) | msdyn_internalorganizations |
[Hiérarchie d’organisation – publiée](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Ce modèle fournit une synchronisation unidirectionnelle de la table Hiérarchie d’organisation publiée.
[Objectifs de la hiérarchie d’organisation](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Ce modèle fournit une synchronisation unidirectionnelle de la table Objectif de la hiérarchie d’organisation.
[Type de la hiérarchie d’organisation](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Ce modèle fournit une synchronisation unidirectionnelle de la table Type de hiérarchie d’organisation.

## <a name="internal-organization"></a>Organisation interne

Les informations d’organisation internes dans Dataverse proviennent de deux tables, **Unité opérationnelle** et **Entités juridiques**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
