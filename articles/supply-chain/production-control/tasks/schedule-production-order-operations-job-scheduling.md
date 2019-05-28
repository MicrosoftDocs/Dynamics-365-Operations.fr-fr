---
title: Programmer un ordre de fabrication avec la planification d'opérations et de travaux
description: Cette procédure se concentre sur la planification d’un ordre de fabrication avec la planification des opérations et la planification des tâches.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00698e9cd2ed0481e5fed301c8a8c2e98690a5db
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562136"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Programmer un ordre de fabrication avec la planification d'opérations et de travaux

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure se concentre sur la planification d’un ordre de fabrication avec la planification des opérations et la planification des tâches. Aucune tâche n'est créée avec la planification des opérations tandis que des travaux sont créés avec la planification des tâches. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF. Cette procédure est conçue pour le gestionnaire de production, le planificateur de production ou le superviseur d'atelier travaillant dans un environnement de fabrication discrète.


## <a name="create-a-production-order"></a>Créer un ordre de fabrication
1. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
2. Cliquez sur Nouvel ordre de fabrication.
3. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Sélectionnez le numéro d'article D0001.  
4. Cliquez sur Créer.

## <a name="schedule-operations-for-the-production-order"></a>Planifier les opérations pour l'ordre de fabrication
1. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez l’ordre de fabrication que vous venez de créer. Il doit être en haut de la liste.      
2. Dans le volet Actions, cliquez sur Planification.
3. Cliquez sur Planifier les opérations.
4. Dans le champ Direction de la planification, sélectionnez « En avant à partir de la date de planification ».
5. Dans le champ Date de planification, entrez une date.
    * Sélectionnez une date future, par exemple, aujourd'hui plus une semaine. Avec la direction de planification sélectionée, l'ordre de fabrication est planifié en avant à partir de la date actuelle.  
6. Cliquez sur OK.
7. Dans la liste, marquez la ligne sélectionnée.
    * Notez que le statut devient Planifiée.  
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Cliquez sur Toutes les tâches.
    * Notez qu’aucune tâche n’est créée avec la planification des opérations.  
10. Fermez la page.

## <a name="schedule-jobs-for-the-production-order"></a>Planifier les tâches pour l'ordre de fabrication
1. Dans le volet Actions, cliquez sur Planification.
2. Cliquez sur Planifier les tâches.
3. Dans le champ Direction de la planification, sélectionnez « En avant à partir de la date de planification ».
4. Dans le champ Date de planification, entrez une date.
    * Sélectionnez une date future, par exemple, aujourd'hui plus une semaine. Avec la direction de planification sélectionée, l'ordre de fabrication est planifié en avant à partir de la date actuelle.  
5. Cliquez sur OK.
6. Cliquez sur Ordre de fabrication dans le volet Actions.
7. Cliquez sur Toutes les tâches.
    * Notez qu’en fonction de la gamme active, 5 tâches sont créées avec la planification des tâches.  

