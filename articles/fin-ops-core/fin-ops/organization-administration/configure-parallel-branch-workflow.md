---
title: Configurer des branches parallèles dans un workflow
description: Pour configurer une branche parallèle, exécutez les procédures suivantes dans l'éditeur de workflow.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196043
ms.assetid: dfdae2b8-6a4f-4760-b339-b755c66f3f89
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2339c6f901a3ef39ad4f9586b2f391b966a3df98
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190141"
---
# <a name="configure-parallel-branches-in-a-workflow"></a>Configurer des branches parallèles dans un workflow

[!include [banner](../includes/banner.md)]

Pour configurer une branche parallèle, exécutez les procédures suivantes dans l'éditeur de workflow.

Une branche parallèle est principalement un workflow qui s'exécute dans le contexte d'un workflow parent.

## <a name="name-a-branch"></a>Saisir un nom de branche

Procédez comme suit pour entrer un nom pour une branche parallèle.

1. Cliquez avec le bouton droit sur la branche parallèle, puis cliquez sur **Propriétés**. L'écran **Propriétés** s'affiche.
2. Dans le volet gauche, cliquez sur **Paramètres de base**.
3. Dans le champ **Nom**, entrez un nom unique pour la branche parallèle.
4. Cliquez sur **Fermer**.

## <a name="design-and-configure-the-elements-of-a-branch"></a>Conception et configuration des éléments d'une branche

Pour concevoir et configurer les éléments d'une branche parallèle, procédez comme suit.

1. Double-cliquez sur la branche parallèle.
2. Faites glisser les éléments de workflow sur le canevas, puis configurez les éléments, comme pour créer un autre workflow. Pour plus d'informations, voir [Création d'un workflow](create-workflow.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Création d'un workflow](create-workflow.md)