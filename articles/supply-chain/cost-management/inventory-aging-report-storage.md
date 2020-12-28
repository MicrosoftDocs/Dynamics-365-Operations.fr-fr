---
title: Stockage des états de balance âgée
description: Cette rubrique décrit les fonctionnalités qui vous permettent d’exécuter un état de la balance âgée et de mettre le résultat à disposition sous la forme d’un formulaire et d’un graphique.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: c4a1480cf96a4ba753b436c04eb8f7b01379da48
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427865"
---
# <a name="inventory-aging-report-storage"></a>Stockage des états de balance âgée

[!include [banner](../includes/banner.md)]

Dans Microsoft Dynamics 365 Supply Chain Management, vous pouvez exécuter un état **Stockage des états de balance âgée** et le mettre à disposition sous la forme d’un formulaire et d’un graphique. Dans le formulaire, des colonnes et des soldes globaux sont ajustés de façon dynamique, selon la disposition configurée. Le graphique offre une vue d’ensemble qui prend en charge les filtres et vous permet de parcourir des informations détaillées. En outre, une entité de données intitulée **État - Balance âgée** vous permet d’exporter les résultats d’un état **Stockage des états de balance âgée** à un format tel qu’un fichier Microsoft Excel ou un fichier PDF.

Ce mode d’exécution d’un état **Stockage des états de balance âgée** est utile lorsque le résultat contient plusieurs lignes. Par exemple, le résultat contient plusieurs lignes si vous avez 50 000 articles et 300 magasins créés comme entrepôts, et si vous demandez la balance âgée par article, site et entrepôt.

## <a name="enable-the-inventory-value-storage-report-feature"></a>Activer la fonctionnalité d’état de stockage des valeur de stock

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. La fonctionnalité est répertoriée comme suit :

- **Module** : Gestion des coûts
- **Nom de la fonctionnalité** - Stockage des états de balance âgée

## <a name="run-an-inventory-aging-report-storage"></a>Exécuter un stockage des états de balance âgée

1. Accédez à **Gestion des coûts \> Recherches et états \> Stockage des états de balance âgée**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Identificateur de processus - Nom**, entrez un nom unique pour l’état.
1. Sélectionnez l’état **Identification – ID**, et filtrez-le comme vous le souhaitez.

    L’exécution de l’état est toujours effectuée dans un traitement par lots.

1. Lorsque le traitement par lots est terminé, le résultat est affiché sur la page **Stockage des états de la balance âgée**.
1. Pour afficher le résultat sous la forme d’un formulaire avec une disposition de grille traditionnelle, sélectionnez **Afficher les détails**. Pour afficher le résultat comme graphique regroupé, sélectionnez **Afficher le graphique**.

    > [!NOTE]
    > Le formulaire n’inclut pas les sous-totaux définis dans la disposition de l’état.

L’entité de données **État de la balance âgée** vous permet d’exporter le résultat d’un état **Stockage des états de balance âgée** en appliquant un filtre pour le champ **Identificateur de processus – Nom** à n’importe quel format pris en charge par la gestion des données.
