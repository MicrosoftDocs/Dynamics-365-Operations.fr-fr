---
title: Mettre à jour le statut d'opération kanban
description: Lorsqu'un kanban est vidé par erreur ou qu'un kanban reçu doit être vidé, vous devez mettre le statut du kanban à jour.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 97b6eea4e93967dbe1eea5eac9fe3fbf6b336a49
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838461"
---
# <a name="update-kanban-status"></a>Mettre à jour le statut d'opération kanban

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

