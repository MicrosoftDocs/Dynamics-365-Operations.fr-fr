---
title: Hiérarchie d’organisation dans Dataverse
description: Cette rubrique décrit l’intégration des données organisationnelles entre les applications Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 30826bf69525a85bede6ec0b64ec1a579aea26a0a6c487583739ad3fcb787a28
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769243"
---
# <a name="organization-hierarchy-in-dataverse"></a>Hiérarchie d’organisation dans Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Comme Dynamics 365 Finance est un système financier, l’*organisation* est un concept de base, et le système commence par la configuration d’une hiérarchie d’organisation. Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l’organisation et également à tous les niveaux de la hiérarchie d’organisation.

Bien que Dataverse ne dispose pas du concept de hiérarchie d’organisation, il dispose de certains concepts flous, tels que le total du produit des ventes. Dans le cadre de l’intégration de Dataverse, la structure de données de la hiérarchie d’organisation est ajoutée à Dataverse.

## <a name="data-flow"></a>Flux de données

Un écosystème commercial composé des applications Finance and Operations et de Dataverse continue d’avoir une hiérarchie d’organisation. Cette hiérarchie d’organisation repose sur les applications Finance and Operations, mais elle est exposée dans Dataverse à des fins d’informations et d’extensibilité. L’illustration suivante présente les informations de la hiérarchie d’organisation exposées dans Dataverse comme un flux unidirectionnel entre les applications Finance and Operations et Dataverse.

![Image de l’architecture.](media/dual-write-data-flow.png)

Des mises en correspondance de la table Hiérarchie d’organisation sont disponibles pour la synchronisation unidirectionnelle des données entre les applications Finance and Operations et Dataverse.

## <a name="templates"></a>Modèles

Les informations de produit contiennent toutes les informations associées au produit et à sa définition, comme les dimensions du produit ou les dimensions de suivi et de stockage. Lorsque le tableau suivant s’affiche, un ensemble de cartes de tables est créé pour synchroniser les produits et les informations associées.

Applications de Finance and Operations | Applications Customer Engagement     | Description
-----------------------|--------------------------------|---
[Entités juridiques](mapping-reference.md#102) | cdm_companies | Fournit la synchronisation bidirectionnelle d’informations sur l’entité juridique (société).
[Entités juridiques](mapping-reference.md#142) | msdyn_internalorganizations |
[Unité opérationnelle](mapping-reference.md#143) | msdyn_internalorganizations |
[Hiérarchie d’organisation – publiée](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Ce modèle fournit une synchronisation unidirectionnelle de la table Hiérarchie d’organisation publiée.
[Objectifs de la hiérarchie d’organisation](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Ce modèle fournit une synchronisation unidirectionnelle de la table Objectif de la hiérarchie d’organisation.
[Type de la hiérarchie d’organisation](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Ce modèle fournit une synchronisation unidirectionnelle de la table Type de hiérarchie d’organisation.

## <a name="internal-organization"></a>Organisation interne

Les informations d’organisation internes dans Dataverse proviennent de deux tables, **Unité opérationnelle** et **Entités juridiques**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
