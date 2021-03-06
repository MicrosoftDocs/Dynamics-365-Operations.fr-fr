---
title: Configurer des décisions conditionnelles dans un workflow
description: La procédure suivante permet de configurer les propriétés d’une décision conditionnelle.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed53eeb26e1b4b1df1647739ce1d115c7dd169f8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747929"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a>Configurer des décisions conditionnelles dans un workflow

[!include [banner](../includes/banner.md)]

La procédure suivante permet de configurer les propriétés d’une décision conditionnelle.

Une décision conditionnelle est un point où le workflow se divise en deux branches. Pour configurer une décision conditionnelle, dans l’éditeur de workflow, cliquez avec le bouton droit sur la décision conditionnelle, puis cliquez sur **Propriétés** pour ouvrir l’écran **Propriétés**.

## <a name="name-a-decision"></a>Nommer une décision

Procédez comme suit pour entrer un nom pour une décision conditionnelle.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Dans le champ **Nom**, entrez un nom unique pour la décision conditionnelle.

## <a name="set-conditions"></a>Définition des conditions

Le système détermine la branche utilisée en évaluant si le document soumis répond à des conditions spécifiques.

1. Dans le volet gauche, cliquez sur **Paramètres de base**.
2. Cliquez sur **Ajouter une condition**.
3. Permet d’entrer une condition.
4. Entrez des conditions supplémentaires, si nécessaire.
5. Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :

    1. Cliquez sur **Test** pour ouvrir l’écran **Condition de workflow de test**.
    2. Sélectionnez un enregistrement dans la zone **Contrôler la condition** de l’écran.
    3. Cliquez sur **Tester**. Le système évalue l’enregistrement pour déterminer s’il répond aux conditions que vous avez spécifiées.
    4. Cliquez sur **OK** ou sur **Annuler** pour revenir à l’écran **Propriétés**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]