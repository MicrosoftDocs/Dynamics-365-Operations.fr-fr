---
title: Hiérarchie d'organisation dans Common Data Service
description: Cette rubrique décrit l'intégration des données organisationnelles entre Finance and Operations et Common Data Service.
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
ms.openlocfilehash: ca2ac0f9dbb8544b12f23a271423a43b0e601272
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789188"
---
## <a name="organization-hierarchy-in-common-data-service"></a>Hiérarchie d'organisation dans Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Comme Microsoft Dynamics 365 for Finance and Operations est un système financier, l'*organisation* est un concept de base, et le système commence par la configuration d'une hiérarchie d'organisation. Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l'organisation et également à tous les niveaux de la hiérarchie d'organisation.

Bien que Common Data Service ne dispose pas du concept de hiérarchie d'organisation, il dispose de certains concepts flous, tels que le total du produit des ventes. Dans le cadre de l'intégration de Common Data Service, la structure de données de la hiérarchie d'organisation est ajoutée à Common Data Service.

## <a name="data-flow"></a>Flux de données

Écosystème commercial composé de Finance and Operations et Common Data Service continue d'avoir une hiérarchie d'organisation. Cette hiérarchie d'organisation repose sur Finance and Operations, mais elle est exposé dans Common Data Service à des fins d'informations et d'extensibilité. L'illustration suivante présente les informations de la hiérarchie d'organisation exposées dans Common Data Service comme un flux unidirectionnel entre Finance and Operations et Common Data Service.

![Image de l'architecture](media/dual-write-data-flow.png)

## <a name="templates"></a>Modèles

Des mises en correspondance de l'entité Hiérarchie d'organisation sont disponibles pour la synchronisation unidirectionnelle des données entre Finance and Operations et Common Data Service.

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a>Objectif de la hiérarchie d'organisation interne

Ce modèle fournit une synchronisation unidirectionnelle de l'entité Objet de la hiérarchie d'organisation entre Finance and Operations et Dynamics 365 for Customer Engagement.

<!-- ![architecture image](media/dual-write-purpose.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
HIERARCHYTYPE | \> | msdyn\_hierarchypurposetypename
HIERARCHYTYPE | \> | msdyn\_hierarchytype.msdyn\_name
HIERARCHYPURPOSE | \>\> | msdyn\_hierarchypurpose
IMMUTABLE | \>\> | msdyn\_immutable
SETASDEFAULT | \>\> | msdyn\_setasdefault

## <a name="internal-organization-hierarchy-type"></a>Type de hiérarchie d'organisation interne

Ce modèle fournit une synchronisation unidirectionnelle de l'entité Type de la hiérarchie d'organisation entre Finance and Operations et Customer Engagement.

<!-- ![architecture image](media/dual-write-type.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
NOM | \> | msdyn\_name

## <a name="internal-organization-hierarchy"></a>Hiérarchie d'organisation interne

Ce modèle fournit une synchronisation unidirectionnelle de l'entité Hiérarchie d'organisation publiée entre Finance and Operations et Customer Engagement.

<!-- ![architecture image](media/dual-write-organization.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
VALIDTO | \> | msdyn\_validto
VALIDFROM | \> | msdyn\_validfrom
HIERARCHYTYPE | \> | msdyn\_hierarchytypename
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentpartyid
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childpartyid
HIERARCHYTYPE | \> | msdyn\_hierarchytypeid.msdyn\_name
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childid.msdyn\_partynumber
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentid.msdyn\_partynumber

## <a name="internal-organization"></a>Organisation interne

Les informations d'organisation interne dans Common Data Service proviennent de deux entités Finance and Operations, l'**unité opérationnelle** et les **entités juridiques**.

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a>Unité opérationnelle

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
LANGUAGEID | \> | msdyn\_languageid
NAMEALIAS | \> | msdyn\_namealias
NOM | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
OPERATINGUNITTYPE | \>\> | msdyn\_type

### <a name="legal-entity"></a>Entité juridique

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
NAMEALIAS | \> | msdyn\_namealias
LANGUAGEID | \> | msdyn\_languageid
NOM | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
aucun | \>\> | msdyn\_type
LEGALENTITYID | \> | msdyn\_companycode

## <a name="company"></a>Société

Fournit la synchronisation bidirectionnelle d'informations sur l'entité juridique (société) entre Finance and Operations et Customer Engagement.

<!-- ![architecture image](media/dual-write-company.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
NOM | = | cdm\_name
LEGALENTITYID | = | cdm\_companycode
