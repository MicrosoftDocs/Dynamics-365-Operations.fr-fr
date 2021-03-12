---
title: Gestion des réparations
description: Regroupez systématiquement les problèmes pour aider à la suggestion de solutions qui se sont avérées efficaces par le passé.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ebb9833be5e51fe59e9895e67cd8e55058078aa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001345"
---
# <a name="repair-management"></a>Gestion des réparations       

[!include [banner](../includes/banner.md)]


Vous pouvez regrouper systématiquement les problèmes pour la gestion des réparations. Cela permet de proposer des solutions qui se sont avérées efficaces par le passé.

Vous pouvez définir les symptômes, les diagnostics et les paramètres de résolution. Tous ces éléments peuvent ensuite être mis en œuvre lorsque vous recevez un article similaire à réparer. Vous pouvez également paramétrer des stades de réparation, qui permettent de suivre le processus de réparation.

## <a name="setting-up-repair-management"></a>Paramétrage de la gestion des réparations

Les écrans de paramétrage suivants permettent d'entrer des informations qui seront utilisées pour spécifier les symptômes, les diagnostics et la résolution de la réparation.

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Réparation** \> **Conditions**.

2.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Réparation** \> **Zones de symptôme**.

3.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Réparation** \> **Zones de diagnostic**.

4.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Réparation** \> **Résolutions**.

5.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Réparation** \> **Stades de réparation**.

## <a name="symptoms-and-conditions"></a>Symptômes et conditions

Les symptômes sont la façon dont les clients décrivent le problème. Ils incluent les observations des clients, qui signalent qu'il est nécessaire d'effectuer une réparation.

Vous pouvez paramétrer des zones de symptôme, des codes symptôme et des conditions de symptôme. La zone de symptôme couvre la zone de dysfonctionnement et le code symptôme couvre le symptôme du dysfonctionnement. La condition décrit la situation ou l'environnement dans lequel le problème se produit.

**Exemple**

Un ordinateur est apporté pour réparation en raison d'un disque dur défectueux après une longue période d'utilisation. Ce disque dur défectueux entraîne une erreur de type écran bleu. Le technicien qui reçoit l'ordinateur entre les conditions et symptômes suivants :

1.  La zone de symptôme correspond au disque dur.

2.  Le code symptôme correspond à l'erreur de type écran bleu.

3.  La condition révèle que le disque dur est défectueux suite à une utilisation prolongée.

## <a name="diagnosis-and-resolutions"></a>Diagnostic et résolutions

Les champs de diagnostic et de résolution sont les relevés relatifs à la réparation. Il s'agit des stades par lesquels est passé le technicien pour découvrir le problème.

La zone de diagnostic couvre l'opération qui doit être effectuée pour résoudre le problème. Le code diagnostic représente la façon dont le problème est géré et la résolution peut signifier que l'article a été réparé, remplacé ou que la commande a été annulée par le client. Par exemple, si l'ordinateur est réparé, la zone de diagnostic peut être « pièce défectueuse », le code diagnostic « nouvelle carte vidéo installée » et la résolution « remplacé ».

## <a name="repair-stages"></a>Stades de réparation

Les stades de réparation indiquent la progression du processus de réparation. Le stade de réparation dispose d'un paramètre de fermeture **Terminé** qui indique que la ligne de réparation est terminée et que la date et l'heure de fin ont été enregistrées.

## <a name="applying-repair-management"></a>Application de la gestion des réparations

Pour appliquer la gestion des réparations à un article, l'article doit être paramétré avec une relation d'objet de service sur une commande de service. À partir de la commande de service, vous pouvez créer une ligne de réparation avec les informations relatives au problème actuel. Sur la ligne de réparation, définissez l'objet de service en réparation et les informations relatives aux symptômes, au diagnostic et à l'exécution. Vous pouvez également créer une remarque pour la ligne de réparation.

Vous pouvez créer des lignes de réparation pour chaque étape du processus de réparation.

## <a name="create-a-repair-line-on-a-service-order"></a>Création d'une ligne de réparation sur une commande de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Sélectionnez la commande de service avec l'objet de service qui doit être réparé.

3.  Cliquez sur **Réparation** \> **Lignes de réparation** pour ouvrir l'écran **Lignes de réparation**.

4.  Appuyez sur Ctrl+N pour créer une nouvelle ligne.

5.  Sélectionnez un objet de service. Vous pouvez sélectionner tout objet de service qui a été paramétré avec une relation d'objet sur la commande de service.

6.  Sélectionnez les symptômes, le diagnostic et les valeurs d'exécution prédéfinis appropriés sur la ligne de réparation puis, au besoin, cliquez sur l'onglet **Remarque** pour créer une remarque sur la ligne de réparation.

7.  Appuyez sur Ctrl+S pour enregistrer la nouvelle ligne de réparation. Le champ **Date et heure de création** de l'onglet **Général** de l'écran **Lignes de réparation** est mis à jour avec l'heure de l'enregistrement.

## <a name="tracking-progress-and-resolving-a-repair-issue"></a>Suivi et résolution d'une réparation

Vous pouvez définir les stades de réparation d'une ligne de réparation pour en suivre la progression.

Vous pouvez fermer la ligne de réparation une fois qu'une réparation est résolue. Définissez le stade de réparation sur un stade pour lequel la propriété **Terminé** est activée. La date et l'heure actuelles sont enregistrées comme date et heure de clôture de la ligne.

## <a name="close-a-repair-line-for-a-resolved-issue"></a>Clôture d'une ligne de réparation pour un problème résolu

1.  Ouvrez l'écran **Lignes de réparation**. Suivez la procédure décrite plus haut dans cette rubrique afin de créer une ligne de réparation.

2.  Sélectionnez la ligne de réparation contenant le problème de réparation que vous souhaitez clôturer.

3.  Dans le champ **Stade de réparation**, sélectionnez un stade dont la propriété **Terminé** est activée.

  


