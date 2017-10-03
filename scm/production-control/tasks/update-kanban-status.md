--- 
title: "Mettre à jour le statut d'opération kanban"
description: "Lorsqu'un kanban est vidé par erreur ou qu'un kanban reçu doit être vidé, vous devez mettre le statut du kanban à jour."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: caf7dead2da14e1ff76e205e7477b1eb11a2ca52
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="update-kanban-status"></a>Mettre à jour le statut d'opération kanban

[!include[task guide banner](../../includes/task-guide-banner.md)]

Lorsqu'un kanban est vidé par erreur ou qu'un kanban reçu doit être vidé, vous devez mettre le statut du kanban à jour. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au responsable de magasin.


## <a name="find-the-kanban"></a>Recherchez le kanban.
1. Accédez à Contrôle de la production > Kanban > Kanbans.
2. Ouvrez le filtre de colonnes Statut de l'unité de manutention.
3. Cliquez sur Effacer.
    * Cela réinitialise les filtres.  
4. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Numéro de carte avec une valeur de « 000149 ».

## <a name="change-emptied-status-to-received-status"></a>Remplacer le statut vidé par le statut reçu
1. Cliquez sur Contrepasser l'unité de manutention vide.
2. Cliquez sur OK.
    * Notez que le statut de l'unité de manutention est Reçu.  

## <a name="change-received-status-to-emptied-status"></a>Remplacer le statut reçu par le statut vidé
1. Cliquez sur Kanban vide.
2. Dans la liste, marquez la ligne sélectionnée.
    * Notez que le statut de l'unité de manutention est Vidé.  


