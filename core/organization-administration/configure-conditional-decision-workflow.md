---
title: "Configuration d&quot;une décision conditionnelle dans un workflow"
description: "La procédure suivante permet de configurer les propriétés d&quot;une décision conditionnelle."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 3bba3d849d02cd84c2c0e0c5c15f7b649b3e125c
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-conditional-decision-in-a-workflow"></a>Configuration d'une décision conditionnelle dans un workflow

La procédure suivante permet de configurer les propriétés d'une décision conditionnelle.

Une décision conditionnelle est un point où le workflow se divise en deux branches. Pour configurer une décision conditionnelle, dans l'éditeur de workflow, cliquez avec le bouton droit sur la décision conditionnelle, puis cliquez sur **Propriétés** pour ouvrir l'écran **Propriétés**.

## <a name="name-a-decision"></a>Nommer une décision
Procédez comme suit pour entrer un nom pour une décision conditionnelle.
1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Dans le champ **Nom**, entrez un nom unique pour la décision conditionnelle.

## <a name="set-conditions"></a> Définition des conditions
Le système détermine la branche utilisée en évaluant si le document soumis répond à des conditions spécifiques.
1.  Dans le volet gauche, cliquez sur **Paramètres de base**.
2.  Click **Add condition**.
3.  Permet d'entrer une condition.
4.  Entrez des conditions supplémentaires, si nécessaire.
5.  Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :
    1.  Cliquez sur **Test** pour ouvrir l'écran **Condition de workflow de test**.
    2.  Sélectionnez un enregistrement dans la zone **Contrôler la condition** de l'écran.
    3.  Cliquez sur **Tester**. Le système évalue l'enregistrement pour déterminer s'il répond aux conditions que vous avez spécifiées.
    4.  Cliquez sur **OK** ou sur **Annuler** pour revenir à l'écran **Propriétés**.




