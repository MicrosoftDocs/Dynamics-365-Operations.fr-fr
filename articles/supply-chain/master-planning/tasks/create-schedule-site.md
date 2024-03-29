---
title: Créer un programme pour un site
description: Cette procédure décrit comment planifier les ordres de fabrication qui n’ont pas encore commencé pour un site.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0db5095020bc14d56ae3680e7d0caa68789180e
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469280"
---
# <a name="create-a-schedule-for-a-site"></a>Créer un programme pour un site

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment planifier les ordres de fabrication qui n’ont pas encore commencé pour un site.  Les données fictives de la société USMF sont utilisées pour réaliser cette procédure.


## <a name="identify-production-orders-that-are-not-started"></a>Identifier les ordres de fabrication qui n’ont pas encore commencé
1. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Site avec une valeur de « 1 ».
    * 1 représente un site dans USMF. Si vous n’utilisez pas USMF, sélectionnez un site à partir de votre propre société.  
3. Ouvrez le filtre de colonne Statut.
4. Appliquez un filtre sur le champ « Statut » avec une valeur « Planifié », à l’aide de l’opérateur de filtre « est exactement ».

## <a name="create-a-schedule"></a>Créer un programme
1. Dans la liste, cochez ou décochez toutes les lignes.
2. Dans le volet Actions, cliquez sur Planification.
3. Cliquez sur Planifier les tâches.
4. Dans le champ Direction de la planification, sélectionnez « En arrière à partir de la date de livraison ».
5. Dans le champ Capacité finie, sélectionnez Non.
6. Dans le champ Matières limitées, sélectionnez Non.
7. Cliquez sur OK.
    * Cette opération peut prendre du temps.  

## <a name="view-the-result-of-scheduled-production-orders"></a>Afficher le résultat des ordres de fabrication planifiés
1. Dans la liste, marquez la ligne sélectionnée.
    * Vous pouvez marquer n’importe quelle ligne.  
2. Cliquez sur Ordre de fabrication dans le volet Actions.
3. Cliquez sur Toutes les tâches.
    * Dans cette page, vous pouvez afficher la liste de tâches. Sous l’onglet Planification, vous pouvez afficher la date de début et de fin d’une tâche.  
4. Cliquez sur Matériaux.
    * Dans cette page, vous pouvez voir la consommation de matériaux estimée pour les opérations sur l’ordre de fabrication et le stock disponible actuel.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]