---
title: Hiérarchie d'organisation dans Common Data Service
description: Cette rubrique décrit l'intégration des données organisationnelles entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9efc63c385c31a6d8848d016c1a8689460908dcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769658"
---
# <a name="organization-hierarchy-in-common-data-service"></a>Hiérarchie d'organisation dans Common Data Service

[!include [banner](../includes/banner.md)]

Comme Dynamics 365 Finance est un système financier, l'*organisation* est un concept de base, et le système commence par la configuration d'une hiérarchie d'organisation. Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l'organisation et également à tous les niveaux de la hiérarchie d'organisation.

Bien que Common Data Service ne dispose pas du concept de hiérarchie d'organisation, il dispose de certains concepts flous, tels que le total du produit des ventes. Dans le cadre de l'intégration de Common Data Service, la structure de données de la hiérarchie d'organisation est ajoutée à Common Data Service.

## <a name="data-flow"></a>Flux de données

Écosystème commercial composé des applications Finance and Operations et Common Data Service continue d'avoir une hiérarchie d'organisation. Cette hiérarchie d'organisation repose sur les applications Finance and Operations, mais elle est exposée dans Common Data Service à des fins d'informations et d'extensibilité. L'illustration suivante présente les informations de la hiérarchie d'organisation exposées dans Common Data Service comme un flux unidirectionnel entre les applications Finance and Operations et Common Data Service.

![Image de l'architecture](media/dual-write-data-flow.png)

## <a name="templates"></a>Modèles

Des mises en correspondance de l'entité Hiérarchie d'organisation sont disponibles pour la synchronisation unidirectionnelle des données entre les applications Finance and Operations et Common Data Service.

## <a name="templates"></a>Modèles

Les informations de produit contiennent toutes les informations associées au produit et à sa définition, comme les dimensions du produit ou les dimensions de suivi et de stockage. Lorsque le tableau suivant s'affiche, un ensemble de cartes d'entité est créé pour synchroniser les produits et les informations associées.

Finance and Operations | Autres applications Dynamics 365 | Description
-----------------------|--------------------------------|---
Objectifs de la hiérarchie d'organisation | msdyn_internalorganizationhierarchypurposes | Ce modèle fournit une synchronisation unidirectionnelle de l'entité Objectif de la hiérarchie d'organisation.
Type de la hiérarchie d'organisation | msdyn_internalorganizationhierarchytypes | Ce modèle fournit une synchronisation unidirectionnelle de l'entité Type de la hiérarchie d'organisation.
Hiérarchie d'organisation - publiée | msdyn_internalorganizationhierarchies | Ce modèle fournit une synchronisation unidirectionnelle de l'entité Hiérarchie d'organisation publiée.
Unité opérationnelle | msdyn_internalorganizations | 
Entités juridiques | msdyn_internalorganizations | 
Entités juridiques | cdm_companies | Fournit la synchronisation bidirectionnelle d'informations sur l'entité juridique (société).


[!include [banner](../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](dual-write/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](dual-write/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](dual-write/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Organisation interne

Les informations d'organisation internes dans Common Data Service proviennent de deux entités, **unité opérationnelle** et **entités juridiques**.

[!include [Operating unit](dual-write/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-Companies.md)]

