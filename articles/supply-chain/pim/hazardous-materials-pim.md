---
title: Matières dangereuses
description: Cette rubrique fournit des informations sur les documents relatifs aux matières dangereuses et les informations stockées dans votre environnement.
author: lachlancashMS
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 079c8d23250368c92e5d79f0e2624f8340db2077
ms.sourcegitcommit: c009ec75f53872272f11c92a1ce81a391e3845a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/18/2020
ms.locfileid: "3699534"
---
# <a name="hazardous-materials"></a>Matières dangereuses

[!include [banner](../includes/banner.md)]

Les informations sur les matières dangereuses sont définies dans Gestion des informations sur les produits. Ce module fournit également des documents qui peuvent être imprimés via la gestion de l’entrepôt.

Lorsque vous expédiez des matières classées comme marchandises dangereuses, des documents supplémentaires doivent être inclus avec les envois. La fonctionnalité des matières dangereuses permet aux clients de stocker les informations de classification et de les relier aux articles de sortie. Ces informations peuvent ensuite être utilisées pour préparer la documentation d’expédition.

> [!IMPORTANT]
> Les fonctionnalités sur les matières dangereuses dans Microsoft Dynamics 365 Supply Chain Management fournissent une collection de champs d’informations utiles sur le produit et des fonctionnalités associées qui peuvent vous aider à enregistrer et à référencer les informations relatives à vos produits dangereux. Ces fonctionnalités peuvent également vous aider à concevoir et à imprimer des documents d’expédition qui incluent certaines de ces mêmes informations sur les matières dangereuses que vous expédiez. Cependant, le système ne vous met pas automatiquement en conformité avec toutes les réglementations applicables dans votre pays ou région. Bien que ces outils soient destinés à vous aider à vous mettre en conformité avec les réglementations en vigueur, ils ne sont ni suffisants en eux-mêmes ni garantis de l’être. Votre organisation a la responsabilité de connaître toutes les réglementations applicables et de prendre toutes les mesures nécessaires pour vous y conformer.

Avant de pouvoir utiliser cette fonctionnalité, la configuration suivante est requise :

- **Gestion des informations produits :** configurez des codes qui peuvent être appliqués aux produits lancés.
- **Gestion d’entrepôt :** utilisez des documents d’expédition supplémentaires pour imprimer les informations d’expédition.

## <a name="product-information-management"></a>Gestion des informations sur le produit

Dans Gestion des informations sur les produits, il existe une série de tableaux de configuration dans lesquels vous pouvez ajouter les informations de référence fournies dans les listes de marchandises dangereuses pour le fret routier, aérien et maritime.

Voici certaines des réglementations qui sont souvent référencées :

- **ADR** - Règlements liés au transport international de marchandises dangereuses par route
- **CFR 49** - Réglementation aux États-Unis pour le transport de marchandises dangereuses
- **IMDG** - Le code IMDG (International Marine Dangerous Goods)
- **IATA** - Règlement sur les marchandises dangereuses de l’Association internationale du transport aérien (IATA)

Chacun de ces règlements a une liste de marchandises dangereuses qui comprend des codes de référence. Les listes pour chaque type de transport sont combinées sur des classifications internationales partagées. Supply Chain Management fournit un tableau de référence pour les codes partagés dans ces listes. Chaque liste possède également des codes uniques qui peuvent être définis.

Pour commencer à configurer ces informations, créez une réglementation que vous pouvez utiliser pour configurer les paramètres initiaux.

## <a name="warehouse-management"></a>Gestion des entrepôts

Lorsqu’un envoi est préparé, plusieurs nouveaux rapports peuvent être imprimés. Ces rapports utilisent les informations que vous avez configurées dans la gestion des informations produit.
