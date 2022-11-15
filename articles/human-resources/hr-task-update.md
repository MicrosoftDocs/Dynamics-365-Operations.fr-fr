---
title: Configurer des tâches dans Gestion des tâches
description: Cet article explique comment configurer des tâches dans Gestion des tâches dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-06-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6a38cc2e36c24ddbfe0d8b2886301c108599ab25
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745386"
---
# <a name="set-up-tasks-in-task-management"></a>Configurer des tâches dans Gestion des tâches

[!INCLUDE [PEAP](../includes/peap-1.md)]

Dans les versions de Microsoft Dynamics 365 Human Resources antérieures à la version 10.0.30, les utilisateurs qui souhaitaient modifier une tâche devaient modifier individuellement cette tâche sur chaque liste de contrôle qui la contenait. Cependant, à partir de la version 10.0.30 de Human Resources, les utilisateurs peuvent sélectionner la manière dont les tâches modifiées sont gérées. Si une tâche en cours de modification figure sur une liste de contrôle, l’option **Activer la mise à niveau de la gestion des tâches** doit être sélectionnée dans l’onglet **Gestion des tâches** de la page **Paramètres partagés de Human Resources** pour permettre à la liste de contrôle d’utiliser la tâche modifiée.

[![Activez l’option de mise à niveau de la gestion des tâches sur la page des paramètres partagés de Human resources.](./media/task-update.png)](./media/task-update.png)

Si les modifications des tâches doivent être appliquées à toutes les tâches associées à la liste de contrôle, une relation doit déjà exister entre la tâche de la bibliothèque de tâches et la tâche de la liste de contrôle. Une option a été ajoutée pour créer la relation entre la tâche de la bibliothèque et la tâche de la liste de contrôle.

Vous pouvez créer des tâches individuellement, puis les réutiliser dans plusieurs listes de contrôle. Pour créer une tâche, sur la page **Configuration d’intégration**, sur l’onglet **Tâches**, sélectionnez **Nouvelle**.

## <a name="set-up-tasks"></a>Configurer des tâches

Pour affecter une tâche créée à plusieurs listes de contrôle, sélectionnez la tâche, puis sélectionnez **Appliquer aux listes de contrôle** dans le menu.

Alternativement, vous pouvez ajouter des tâches directement à une liste de contrôle. Pour ajouter une tâche à une liste de contrôle, sur la page **Configuration de l’intégration**, dans l’onglet **Liste de contrôle**, créez une liste de contrôle à laquelle ajouter la tâche ou ajoutez la tâche à une liste de contrôle existante.

Pour modifier une tâche de la bibliothèque, sélectionnez **Modifier** dans le menu de la bibliothèque de tâches. Si la tâche est associée à des listes de contrôle, ces listes de contrôle apparaîtront sur la page **Modifier la tâche**. Si vous souhaitez que les tâches des listes de contrôle soient mises à jour avec les modifications, sélectionnez ces listes de contrôle dans la section **Appliquer aux listes de contrôle**.

Pour supprimer des tâches de la bibliothèque de tâches, sélectionnez **Supprimer**. Si la tâche est associée à une liste de contrôle, cette action ne supprime pas la tâche de la liste de contrôle. Une action distincte est requise pour supprimer une tâche d’une liste de contrôle.

### <a name="set-up-checklists"></a>Configurer des listes de contrôle

Une liste de contrôle est un groupe de tâches. Vous pouvez créer autant de listes de contrôle que vous le souhaitez et vous pouvez affecter les mêmes tâches à plusieurs listes de contrôle. Lorsque vous créez une liste de contrôle, vous spécifiez un propriétaire et un calendrier.

Pour créer une tâche dans une liste de contrôle, sélectionnez **Nouveau** dans la barre de menu de la tâche. Lorsque vous créez une tâche, vous pouvez éventuellement l’ajouter à la bibliothèque de tâches, afin qu’elle puisse être partagée sur plusieurs listes de contrôle. Pour ajouter la tâche à la bibliothèque de tâches, vous devez définir l’option **Appliquer la tâche à la bibliothèque** sur **Oui**. Si vous choisissez d’ajouter la tâche à la bibliothèque de tâches, vous pouvez également l’ajouter à d’autres listes de contrôle en même temps en sélectionnant ces listes de contrôle dans la section **Appliquer aux listes de contrôle**. Si vous choisissez de ne pas ajouter la tâche à la bibliothèque de tâches, celle-ci n’existera que sur la liste de contrôle où vous la créez.

Pour modifier une tâche d’une liste de contrôle, sélectionnez **Modifier** dans le menu de la tâche. Si la tâche est associée à des listes de contrôle, ces listes de contrôle apparaîtront sur la page **Modifier la tâche**. Si vous souhaitez que les tâches d’autres listes de contrôle soient mises à jour avec les modifications, sélectionnez ces listes de contrôle dans la section **Appliquer aux listes de contrôle**.

Pour supprimer des tâches d’une liste de contrôle, sélectionnez **Supprimer**. Cette action supprimera les tâches de la liste de contrôle. Cependant, elle ne supprimera pas les tâches de la bibliothèque de tâches. Pour supprimer des tâches de la bibliothèque de tâches, ouvrez la **Bibliothèque de tâches** et sélectionnez **Supprimer**.
