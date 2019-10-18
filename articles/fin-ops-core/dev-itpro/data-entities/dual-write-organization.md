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
ms.openlocfilehash: fd159b38f69305dcaecb364ba0ccb3befabb3582
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182023"
---
## <a name="organization-hierarchy-in-common-data-service"></a>Hiérarchie d'organisation dans Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Comme Dynamics 365 Finance est un système financier, l'*organisation* est un concept de base, et le système commence par la configuration d'une hiérarchie d'organisation. Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l'organisation et également à tous les niveaux de la hiérarchie d'organisation.

Bien que Common Data Service ne dispose pas du concept de hiérarchie d'organisation, il dispose de certains concepts flous, tels que le total du produit des ventes. Dans le cadre de l'intégration de Common Data Service, la structure de données de la hiérarchie d'organisation est ajoutée à Common Data Service.

## <a name="data-flow"></a>Flux de données

Écosystème commercial composé des applications Finance and Operations et Common Data Service continue d'avoir une hiérarchie d'organisation. Cette hiérarchie d'organisation repose sur les applications Finance and Operations, mais elle est exposée dans Common Data Service à des fins d'informations et d'extensibilité. L'illustration suivante présente les informations de la hiérarchie d'organisation exposées dans Common Data Service comme un flux unidirectionnel entre les applications Finance and Operations et Common Data Service.

![Image de l'architecture](media/dual-write-data-flow.png)

## <a name="templates"></a>Modèles

Des mises en correspondance de l'entité Hiérarchie d'organisation sont disponibles pour la synchronisation unidirectionnelle des données entre les applications Finance and Operations et Common Data Service.

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a>Objectif de la hiérarchie d'organisation interne

Ce modèle fournit une synchronisation unidirectionnelle de l'entité Objet de la hiérarchie d'organisation entre Finance and Operations et d'autres applications Dynamics 365.

<!-- ![architecture image](media/dual-write-purpose.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
HIERARCHYTYPE | \> | msdyn\_hierarchypurposetypename
HIERARCHYTYPE | \> | msdyn\_hierarchytype.msdyn\_name
HIERARCHYPURPOSE | \>\> | msdyn\_hierarchypurpose
IMMUTABLE | \>\> | msdyn\_immutable
SETASDEFAULT | \>\> | msdyn\_setasdefault

## <a name="internal-organization-hierarchy-type"></a>Type de hiérarchie d'organisation interne

Ce modèle fournit une synchronisation unidirectionnelle de l'entité Type de la hiérarchie d'organisation entre Finance and Operations et d'autres applications Dynamics 365.

<!-- ![architecture image](media/dual-write-type.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
NOM | \> | msdyn\_name

## <a name="internal-organization-hierarchy"></a>Hiérarchie d'organisation interne

Ce modèle fournit une synchronisation unidirectionnelle de l'entité publiée de la hiérarchie d'organisation entre Finance and Operations et d'autres applications Dynamics 365.

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

Les informations d'organisation internes dans Common Data Service proviennent de deux entités, **unité opérationnelle** et **entités juridiques**.

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

Fournit la synchronisation bidirectionnelle d'informations sur l'entité juridique (société) entre Finance and Operations et d'autres applications Dynamics 365.

<!-- ![architecture image](media/dual-write-company.png) -->

Champ source | Type de mise en correspondance | Champ de destination
---|---|---
NOM | = | cdm\_name
LEGALENTITYID | = | cdm\_companycode
