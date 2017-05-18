---
title: "Configurer une activité parallèle dans un workflow"
description: "Pour configurer une activité parallèle, exécutez les procédures suivantes dans l&quot;éditeur de workflow."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: ce3fca9d2dbca046232365b1375bfd920d5b10fd
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Configurer une activité parallèle dans un workflow

[!include[banner](../includes/banner.md)]


Pour configurer une activité parallèle, exécutez les procédures suivantes dans l'éditeur de workflow.

Une activité parallèle comprend des branches de workflow qui s'exécutent simultanément.

## <a name="name-a-parallel-activity"></a>Saisie d'un nom pour une activité parallèle
Procédez comme suit pour entrer un nom pour une activité parallèle.
1.  Cliquez avec le bouton droit sur l'activité parallèle, puis cliquez sur **Propriétés** pour ouvrir l'écran **Propriétés**.
2.  Dans le volet gauche, cliquez sur **Paramètres de base**.
3.  Dans le champ **Nom**, entrez un nom unique pour l'activité parallèle.
4.  Cliquez sur **Fermer**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Configuration des branches d'une activité parallèle
Pour ajouter et configurer les branches de cette activité parallèle, procédez comme suit.
1.  Double-cliquez sur l'activité parallèle pour afficher les branches de l'activité parallèle.
2.  Pour ajouter une branche, faites glisser l'élément **Branche** de la zone **Élément de workflow** vers un point d'insertion sur le canevas. La figure suivante présente un point d'insertion.![Insertion point](./media/workflow_insertionpoint.gif)
    | **Remarque**                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------|
    | L'ordre des branches est sans importance, car toutes les branches d'une activité parallèle s'exécutent simultanément. |

3.  Pour configurer chaque branche, voir [Configuration d'une branche parallèle](configure-parallel-branch-workflow.md).






