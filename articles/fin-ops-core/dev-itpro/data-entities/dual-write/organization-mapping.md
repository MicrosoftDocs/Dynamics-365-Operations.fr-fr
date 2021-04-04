---
title: Hiérarchie d’organisation dans Dataverse
description: Cette rubrique décrit l’intégration des données organisationnelles entre les applications Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f265d49a87383e2abf129b8d1d67567fc4b9e0de
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559577"
---
# <a name="organization-hierarchy-in-dataverse"></a>Hiérarchie d’organisation dans Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Comme Dynamics 365 Finance est un système financier, l’*organisation* est un concept de base, et le système commence par la configuration d’une hiérarchie d’organisation. Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l’organisation et également à tous les niveaux de la hiérarchie d’organisation.

Bien que Dataverse ne dispose pas du concept de hiérarchie d’organisation, il dispose de certains concepts flous, tels que le total du produit des ventes. Dans le cadre de l’intégration de Dataverse, la structure de données de la hiérarchie d’organisation est ajoutée à Dataverse.

## <a name="data-flow"></a>Flux de données

Un écosystème commercial composé des applications Finance and Operations et de Dataverse continue d’avoir une hiérarchie d’organisation. Cette hiérarchie d’organisation repose sur les applications Finance and Operations, mais elle est exposée dans Dataverse à des fins d’informations et d’extensibilité. L’illustration suivante présente les informations de la hiérarchie d’organisation exposées dans Dataverse comme un flux unidirectionnel entre les applications Finance and Operations et Dataverse.

![Image de l’architecture](media/dual-write-data-flow.png)

Des mises en correspondance de la table Hiérarchie d’organisation sont disponibles pour la synchronisation unidirectionnelle des données entre les applications Finance and Operations et Dataverse.

## <a name="templates"></a>Modèles

Les informations de produit contiennent toutes les informations associées au produit et à sa définition, comme les dimensions du produit ou les dimensions de suivi et de stockage. Lorsque le tableau suivant s’affiche, un ensemble de cartes de tables est créé pour synchroniser les produits et les informations associées.

Applications Finance and Operations | Autres applications Dynamics 365 | Description
-----------------------|--------------------------------|---
Objectifs de la hiérarchie d’organisation | msdyn_internalorganizationhierarchypurposes | Ce modèle fournit une synchronisation unidirectionnelle de la table Objectif de la hiérarchie d’organisation.
Type de la hiérarchie d'organisation | msdyn_internalorganizationhierarchytypes | Ce modèle fournit une synchronisation unidirectionnelle de la table Type de hiérarchie d’organisation.
Hiérarchie d'organisation - publiée | msdyn_internalorganizationhierarchies | Ce modèle fournit une synchronisation unidirectionnelle de la table Hiérarchie d’organisation publiée.
Unité opérationnelle | msdyn_internalorganizations |
Entités juridiques | msdyn_internalorganizations |
Entités juridiques | cdm_companies | Fournit la synchronisation bidirectionnelle d’informations sur l’entité juridique (société).

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Organisation interne

Les informations d’organisation internes dans Dataverse proviennent de deux tables, **unité opérationnelle** et **entités juridiques**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]