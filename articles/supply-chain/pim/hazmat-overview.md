---
title: Vue d’ensemble des matières dangereuses
description: Cette rubrique fournit une vue d’ensemble des fonctionnalités liées à la manipulation et à la documentation sur les matières dangereuses lors de la gestion des informations sur les produits et de la gestion des entrepôts.
author: dasani-madipalli
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 5f8c3dc084f4f260f8cc29b3957913e9bc1b762d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356997"
---
# <a name="hazardous-materials-overview"></a>Vue d’ensemble des matières dangereuses

[!include [banner](../includes/banner.md)]

Pour rester conformes aux réglementations sur l’expédition et le transport, les organisations qui expédient des matières classées comme marchandises dangereuses doivent inclure des documents supplémentaires dans leurs expéditions. La fonction relatives aux matières dangereuses permet aux clients de stocker des informations sur les articles lancés. Ces informations peuvent ensuite être utilisées pour préparer la documentation d’expédition. Une organisation qui expédie des marchandises dangereuses doit avoir ses propres processus et procédures pour gérer le processus d’expédition. Microsoft Dynamics 365 Supply Chain Management est simplement un outil qui peut aider à générer les documents requis.

Le diagramme suivant illustre les étapes nécessaires pour configurer et utiliser la fonction sur les matières dangereuses.

![Configuration et utilisation de la fonction sur les matières dangereuses.](media/hazmat-overview.png "Configuration et utilisation de la fonction sur les matières dangereuses")

La fonctionnalité sur les matières dangereuses est configurée dans la gestion des informations sur les produits et fournit des documents qui peuvent être imprimés via la gestion des entrepôts. Par conséquent, de manière générale, ces domaines sont les deux principaux domaines dans lesquels vous allez examiner, configurer et utiliser les fonctionnalités de cette fonctionnalité :

- **Gestion des informations produits** – configurez les codes qui peuvent être appliqués à un produit lancé.
- **Gestion des entrepôts** – Utilisez des documents d’expédition supplémentaires qui seront imprimés pour les expéditions.

> [!IMPORTANT]
> Les fonctionnalités sur les matières dangereuses dans Supply Chain Management fournissent une collection de champs d’informations utiles sur le produit et des fonctionnalités associées qui peuvent vous aider à enregistrer et à référencer les informations relatives à vos produits dangereux. Ces fonctionnalités peuvent également vous aider à concevoir et à imprimer des documents d’expédition qui incluent certaines de ces mêmes informations sur les matières dangereuses que vous expédiez. Cependant, le système ne vous met pas automatiquement en conformité avec toutes les réglementations applicables dans votre pays ou région. Bien que ces outils soient destinés à vous aider à vous mettre en conformité avec les réglementations en vigueur, ils ne sont ni suffisants en eux-mêmes ni garantis de l’être. Votre organisation a la responsabilité de connaître toutes les réglementations applicables et de prendre toutes les mesures nécessaires pour vous y conformer.

## <a name="product-information-management"></a>Gestion des informations sur les produits

La Gestion des informations sur les produits fournit une série de tableaux de configuration dans lesquels vous pouvez saisir des informations de référence concernant les différentes listes de marchandises dangereuses pour le fret routier, aérien et maritime.

Les réglementations communes suivantes ont été référencées lors du développement de cette fonctionnalité :

- **ADR** - Règlements liés au transport international de marchandises dangereuses par route
- **CFR 49** - Réglementation aux États-Unis pour le transport de marchandises dangereuses
- **IMDG** - Le code IMDG (International Marine Dangerous Goods)
- **IATA** - Règlement sur les marchandises dangereuses de l’Association internationale du transport aérien (IATA)

Chaque ensemble de réglementations fournit des listes normalisées de marchandises dangereuses et des codes de référence. Par conséquent, Supply Chain Management fournit un tableau de référence pour les codes communs sur ces listes. Chaque liste possède également des codes uniques que vous pouvez définir.

Pour plus d’informations sur la configuration des réglementations et des valeurs pour les matières dangereuses et sur l’attribution des valeurs aux produits concernés, consultez les rubriques suivantes :

- [Paramétrer des matières dangereuses](hazmat-setup.md)
- [Matières dangereuses dans les produits, les commandes, les expéditions et les chargements](hazmat-items.md)

## <a name="warehouse-management"></a>Gestion des entrepôts

Lorsque vous préparez une expédition dans la Gestion des entrepôts, vous pourrez imprimer plusieurs nouveaux états qui utilisent les informations que vous avez configurées dans la Gestion des informations sur les produits. Pour plus d’informations sur les états disponibles et comment les utiliser, consultez [Demandes de renseignements et déclarations sur les matières dangereuses](hazmat-reports.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]