---
title: Vue d’ensemble de création des workflows
description: Cette rubrique illustre la création d’un workflow.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: d1402019dbaaa60827499fcb6b93ee31440cfc3d
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797650"
---
# <a name="create-workflows-overview"></a>Vue d’ensemble de création des workflows

[!include [banner](../includes/banner.md)]

Cette rubrique illustre la création d’un workflow.

## <a name="open-the-workflow-editor"></a>Ouverture de l’éditeur de workflow

Le module dans lequel vous travaillez détermine les types de workflow que vous pouvez créer. Procédez comme suit pour sélectionner le type de workflow à créer et ouvrir l’éditeur de workflow.

1. Ouvrez le module pour lequel vous souhaitez créer un workflow. Par exemple, pour créer un workflow pour les demandes d’achat, cliquez sur **Approvisionnements**.
2. Cliquez sur **Paramétrage** &gt; **\[Workflows de [nom du module]\]**.
3. Sur la page de liste qui s’affiche, dans le volet Actions, cliquez sur **Nouveau**.
4. Sur la page **Créer un workflow**, sélectionnez le type de workflow à créer, puis cliquez sur **Créer un workflow**. L’éditeur de workflow s’affiche. Vous pouvez à présent utiliser les procédures suivantes pour concevoir le workflow.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Dépôt d’éléments de workflow sur le canevas

La zone **Éléments du workflow** de l’éditeur de workflow contient les éléments que vous pouvez ajouter au workflow. Pour ajouter des éléments au workflow, faites-les glisser sur le canevas.

## <a name="connect-the-elements"></a>Connexion des éléments

Pour connecter deux éléments de workflow, maintenez le pointeur sur un élément jusqu’à l’affichage des points de connexion. Cliquez sur un point de connexion et faites-le glisser sur un autre élément. Connectez bien tous les éléments.

## <a name="configure-the-properties-of-the-workflow"></a>Configuration des propriétés du workflow

Suivez la procédure suivante pour configurer les propriétés du workflow.

1. Cliquez sur le canevas pour être sûr qu’aucun élément de workflow n’est sélectionné.
2. Cliquez sur **Propriétés** pour ouvrir la page **Propriétés** du workflow.
3. Suivez les procédures de la rubrique [Configurer les propriétés d’un workflow](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Configuration des éléments du workflow

Configurez tous les éléments que vous avez déposés sur le canevas. Pour plus d’informations sur la configuration des éléments de workflow, voir les rubriques suivantes :

- [Configurer des tâches manuelles dans un workflow](configure-manual-task-workflow.md)
- [Configurer des tâches automatiques dans un workflow](configure-automated-task-workflow.md)
- [Configurer des processus d’approbation dans un workflow](configure-approval-process-workflow.md)
- [Configurer des étapes d’approbation dans un workflow](configure-approval-step-workflow.md)
- [Configurer des décisions manuelles dans un workflow](configure-manual-decision-workflow.md)
- [Configurer des décisions conditionnelles dans un workflow](configure-conditional-decision-workflow.md)
- [Configurer des branches parallèles dans un workflow](configure-parallel-activity-workflow.md)
- [Configuration d’une branche parallèle](configure-parallel-branch-workflow.md)
- [Configuration de workflows pour ligne](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Résolution des erreurs et des avertissements

Le volet **Erreurs et avertissements** dans la partie inférieure de l’éditeur de workflow affiche les messages générés pour le workflow. Pour localiser l’élément concerné par l’erreur ou l’avertissement, double-cliquez sur le message d’erreur ou d’avertissement. Vous devez résoudre toutes les erreurs et les avertissements avant de rendre le workflow actif.

## <a name="save-and-activate-the-workflow"></a>Enregistrement et activation du workflow

Lorsque vous êtes prêts à enregistrer et à activer le workflow, procédez comme suit.

1. Cliquez sur **Enregistrer et fermer** pour fermer l’éditeur de workflow et pour ouvrir la page **Sauvegarder le workflow**.
2. Entrez des commentaires sur les modifications apportées au workflow, puis cliquez sur **OK**.
3. Si toutes les erreurs et les avertissements ont été résolus, la page **Activer le workflow** s’affiche. Permet de sélectionner l’une des options suivantes :

    - Pour activer cette version du workflow, cliquez sur **Activer la nouvelle version**. Lorsqu’un workflow est activé, les utilisateurs peuvent y soumettre des documents pour traitement.
    - Si vous ne souhaitez pas activer cette version, cliquez sur **Ne pas activer la nouvelle version**. Vous pouvez activer le workflow ultérieurement.
