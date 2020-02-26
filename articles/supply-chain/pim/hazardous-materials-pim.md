---
title: Matières dangereuses
description: Cette rubrique fournit des informations sur les documents relatifs aux matières dangereuses et les informations stockées dans votre environnement.
author: lachlancashMS
manager: AnnBe
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
ms.openlocfilehash: 76dd6539e39bb77c546e613b290fc5decba9457f
ms.sourcegitcommit: 4c60f5dccdf0b94ed110a657ef331546adc5424a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2020
ms.locfileid: "2982306"
---
# <a name="hazardous-materials"></a>Matières dangereuses

[!include [banner](../includes/banner.md)]

Les informations sur les matières dangereuses sont définies dans Gestion des informations sur les produits. Ce module fournit également des documents qui peuvent être imprimés via la gestion de l'entrepôt.

Lorsque vous expédiez des matières classées comme marchandises dangereuses, des documents supplémentaires doivent être inclus avec les envois. La fonctionnalité des matières dangereuses permet aux clients de stocker les informations de classification et de les relier aux articles de sortie. Ces informations peuvent ensuite être utilisées pour préparer la documentation d'expédition.

> [!IMPORTANT]
> Pour aider à gérer les expéditions de marchandises dangereuses, Microsoft Dynamics 365 Supply Chain Management vous permet de configurer des informations de référence supplémentaires liées aux produits. Vous pouvez également configurer des documents d'expédition supplémentaires. Cependant, le système n'est pas automatiquement conforme aux réglementations de votre pays ou région. C'est plutôt un outil qui peut aider votre programme global.

Avant de pouvoir utiliser cette fonctionnalité, la configuration suivante est requise :

- **Gestion des informations produits :** configurez des codes qui peuvent être appliqués aux produits lancés.
- **Gestion d'entrepôt :** utilisez des documents d'expédition supplémentaires pour imprimer les informations d'expédition.

## <a name="product-information-management"></a>Gestion des informations sur le produit

Dans Gestion des informations sur les produits, il existe une série de tableaux de configuration dans lesquels vous pouvez ajouter les informations de référence fournies dans les listes de marchandises dangereuses pour le fret routier, aérien et maritime.

Voici certaines des réglementations qui sont souvent référencées :

- **ADR** - Règlements liés au transport international de marchandises dangereuses par route
- **CFR 49** - Réglementation aux États-Unis pour le transport de marchandises dangereuses
- **IMDG** - Le code IMDG (International Marine Dangerous Goods)
- **IATA** - Règlement sur les marchandises dangereuses de l'Association internationale du transport aérien (IATA)

Chacun de ces règlements a une liste de marchandises dangereuses qui comprend des codes de référence. Les listes pour chaque type de transport sont combinées sur des classifications internationales partagées. Supply Chain Management fournit un tableau de référence pour les codes partagés dans ces listes. Chaque liste possède également des codes uniques qui peuvent être définis.

Pour commencer à configurer ces informations, créez une réglementation que vous pouvez utiliser pour configurer les paramètres initiaux.

## <a name="warehouse-management"></a>Gestion des entrepôts

Lorsqu'un envoi est préparé, plusieurs nouveaux rapports peuvent être imprimés. Ces rapports utilisent les informations que vous avez configurées dans la gestion des informations produit.
