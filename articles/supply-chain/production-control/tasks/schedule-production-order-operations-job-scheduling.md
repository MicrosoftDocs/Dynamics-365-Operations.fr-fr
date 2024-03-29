---
title: Programmer un ordre de fabrication avec la planification d’opérations et de travaux
description: Cet article se concentre sur la planification d’un ordre de fabrication avec la planification des opérations et la planification des tâches.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d82d5439e57c02ddc9db4222a946bd15f4ed67e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903925"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Programmer un ordre de fabrication avec la planification d’opérations et de travaux

[!include [banner](../../includes/banner.md)]

Cet article se concentre sur la planification d’un ordre de fabrication avec la planification des opérations et la planification des tâches. Aucune tâche n’est créée avec la planification des opérations tandis que des travaux sont créés avec la planification des tâches. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF. Cette procédure est conçue pour le gestionnaire de production, le planificateur de production ou le superviseur d’atelier travaillant dans un environnement de fabrication discrète.


## <a name="create-a-production-order"></a>Créer un ordre de fabrication
1. Dans le volet de navigation, accédez à **Modules > Contrôle de la production > Commun > Ordres de fabrication > Tous les ordres de fabrication**.
2. Sélectionnez **Nouvel ordre de production**.
3. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**. Sélectionnez le numéro d’article **D0001**.  
4. Sélectionnez **Créer**.

## <a name="schedule-operations-for-the-production-order"></a>Planifier les opérations pour l’ordre de fabrication
1. Marquez la ligne récemment créée.      
2. Dans le volet Actions, sélectionnez **Planifier**.
3. Sélectionnez **Planifier les opérations**.
4. Dans le champ **Direction de la planification**, sélectionnez **En avant à partir de la date de planification**.
5. Dans le champ **Date de planification**, entrez une date. Sélectionnez une date future, par exemple, aujourd’hui plus une semaine. Avec la direction de planification sélectionée, l’ordre de fabrication est planifié en avant à partir de la date actuelle.  
6. Cliquez sur **OK**.
7. Dans la liste, marquer la ligne sélectionnée. Notez que le statut devient **Planifiée**. 
8. Sélectionnez **Toutes les tâches**. Notez qu’aucune tâche n’est créée avec la planification des opérations.  
9. Fermez la page.

## <a name="schedule-jobs-for-the-production-order"></a>Planifier les tâches pour l’ordre de fabrication
1. Dans le volet Actions, sélectionnez **Planifier**.
2. Sélectionnez **Planifier les tâches**.
3. Dans le champ **Direction de la planification**, sélectionnez **En avant à partir de la date de planification**.
4. Dans le champ **Date de planification**, entrez une date. Sélectionnez une date future, par exemple, aujourd’hui plus une semaine. Avec la direction de planification sélectionée, l’ordre de fabrication est planifié en avant à partir de la date actuelle.  
5. Cliquez sur **OK**.
6. Dans le volet Actions, sélectionnez **Ordre de fabrication**.
7. Sélectionnez **Toutes les tâches**. Notez qu’en fonction de la gamme active, 5 tâches sont créées avec la planification des tâches.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]