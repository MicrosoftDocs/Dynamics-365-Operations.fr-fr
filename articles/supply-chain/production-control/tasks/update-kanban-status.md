---
title: Mettre à jour le statut d’opération kanban
description: Lorsqu’un kanban est vidé par erreur ou qu’un kanban reçu doit être vidé, vous devez mettre le statut du kanban à jour.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a0e03da4671ffec4ecf4835b20a00ef87971c94
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831815"
---
# <a name="update-kanban-status"></a>Mettre à jour le statut d’opération kanban

[!include [banner](../../includes/banner.md)]

Lorsqu’un kanban est vidé par erreur ou qu’un kanban reçu doit être vidé, vous devez mettre le statut du kanban à jour. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au responsable de magasin.


## <a name="find-the-kanban"></a>Recherchez le kanban.
1. Accédez à Contrôle de la production > Kanban > Kanbans.
2. Ouvrez le filtre de colonnes Statut de l’unité de manutention.
3. Cliquez sur Effacer.
    * Cela réinitialise les filtres.  
4. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Numéro de carte avec une valeur de « 000149 ».

## <a name="change-emptied-status-to-received-status"></a>Remplacer le statut vidé par le statut reçu
1. Cliquez sur Contrepasser l’unité de manutention vide.
2. Cliquez sur OK.
    * Notez que le statut de l’unité de manutention est Reçu.  

## <a name="change-received-status-to-emptied-status"></a>Remplacer le statut reçu par le statut vidé
1. Cliquez sur Kanban vide.
2. Dans la liste, marquez la ligne sélectionnée.
    * Notez que le statut de l’unité de manutention est Vidé.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]