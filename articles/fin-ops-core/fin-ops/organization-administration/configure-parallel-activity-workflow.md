---
title: Configurer des activités parallèles dans un workflow
description: Pour configurer une activité parallèle, exécutez les procédures suivantes dans l’éditeur de workflow.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 054d62e2ff094aee987f8c6e04e2f2e173da633d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068761"
---
# <a name="configure-parallel-activities-in-a-workflow"></a>Configurer des activités parallèles dans un workflow

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Pour configurer une activité parallèle, exécutez les procédures suivantes dans l’éditeur de workflow.

Une activité parallèle comprend des branches de workflow qui s’exécutent simultanément.

## <a name="name-a-parallel-activity"></a>Saisie d’un nom pour une activité parallèle

Procédez comme suit pour entrer un nom pour une activité parallèle.

1. Cliquez avec le bouton droit sur l’activité parallèle, puis cliquez sur **Propriétés** pour ouvrir l’écran **Propriétés**.
2. Dans le volet gauche, cliquez sur **Paramètres de base**.
3. Dans le champ **Nom**, entrez un nom unique pour l’activité parallèle.
4. Cliquez sur **Fermer**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Configuration des branches d’une activité parallèle

Pour ajouter et configurer les branches de cette activité parallèle, procédez comme suit.

1. Double-cliquez sur l’activité parallèle pour afficher les branches de l’activité parallèle.
2. Pour ajouter une branche, faites glisser l’élément **Branche** de la zone **Élément de workflow** vers un point d’insertion sur le canevas. La figure suivante présente un point d’insertion.

    ![Point d’insertion.](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > L’ordre des branches est sans importance, car toutes les branches d’une activité parallèle s’exécutent simultanément.

3. Pour configurer chaque branche, voir [Configuration de branches parallèles dans un workflow](configure-parallel-branch-workflow.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]