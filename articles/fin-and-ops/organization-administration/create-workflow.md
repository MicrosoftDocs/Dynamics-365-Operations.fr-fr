---
title: Créer des workflows
description: Cette rubrique illustre la création d'un workflow.
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 7d4a3c5e12b226a7d801d8db9abcbd15738c1ce0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "353354"
---
# <a name="create-workflows"></a>Créer des workflows

[!include [banner](../includes/banner.md)]

Cette rubrique illustre la création d'un workflow.

## <a name="open-the-workflow-editor"></a>Ouverture de l'éditeur de workflow

Le module Microsoft Dynamics 365 for Finance and Operations dans lequel vous travaillez détermine les types de workflow que vous pouvez créer. Procédez comme suit pour sélectionner le type de workflow à créer et ouvrir l'éditeur de workflow.

1. Ouvrez le module pour lequel vous souhaitez créer un workflow. Par exemple, pour créer un workflow pour les demandes d'achat, cliquez sur **Approvisionnements**.
2. Cliquez sur **Paramétrage** &gt; **\[Workflows de [nom du module\]**.
3. Sur la page de liste qui s'affiche, dans le volet Actions, cliquez sur **Nouveau**.
4. Sur la page **Créer un workflow**, sélectionnez le type de workflow à créer, puis cliquez sur **Créer un workflow**. L'éditeur de workflow s'affiche. Vous pouvez à présent utiliser les procédures suivantes pour concevoir le workflow.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Dépôt d'éléments de workflow sur le canevas

La zone **Éléments du workflow** de l'éditeur de workflow contient les éléments que vous pouvez ajouter au workflow. Pour ajouter des éléments au workflow, faites-les glisser sur le canevas.

## <a name="connect-the-elements"></a>Connexion des éléments

Pour connecter deux éléments de workflow, maintenez le pointeur sur un élément jusqu'à l'affichage des points de connexion. Cliquez sur un point de connexion et faites-le glisser sur un autre élément. Connectez bien tous les éléments.

## <a name="configure-the-properties-of-the-workflow"></a>Configuration des propriétés du workflow

Suivez la procédure suivante pour configurer les propriétés du workflow.

1. Cliquez sur le canevas pour être sûr qu'aucun élément de workflow n'est sélectionné.
2. Cliquez sur **Propriétés** pour ouvrir la page **Propriétés** du workflow.
3. Suivez les procédures de la rubrique [Configurer les propriétés d'un workflow](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Configuration des éléments du workflow

Configurez tous les éléments que vous avez déposés sur le canevas. Pour plus d'informations sur la configuration des éléments de workflow, voir les rubriques suivantes :

- [Configuration d'une tâche manuelle](configure-manual-task-workflow.md)
- [Configuration d'une tâche automatique](configure-automated-task-workflow.md)
- [Configuration d'un processus d'approbation](configure-approval-process-workflow.md)
- [Configuration d'une étape d'approbation](configure-approval-step-workflow.md)
- [Configuration d'une décision manuelle](configure-manual-decision-workflow.md)
- [Configuration d'une décision conditionnelle](configure-conditional-decision-workflow.md)
- [Configuration d'une activité parallèle](configure-parallel-activity-workflow.md)
- [Configuration d'une branche parallèle](configure-parallel-branch-workflow.md)
- [Configuration d'un workflow pour ligne](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Résolution des erreurs et des avertissements

Le volet **Erreurs et avertissements** dans la partie inférieure de l'éditeur de workflow affiche les messages générés pour le workflow. Pour localiser l'élément concerné par l'erreur ou l'avertissement, double-cliquez sur le message d'erreur ou d'avertissement. Vous devez résoudre toutes les erreurs et les avertissements avant de rendre le workflow actif.

## <a name="save-and-activate-the-workflow"></a>Enregistrement et activation du workflow

Lorsque vous êtes prêts à enregistrer et à activer le workflow, procédez comme suit.

1. Cliquez sur **Enregistrer et fermer** pour fermer l'éditeur de workflow et pour ouvrir la page **Sauvegarder le workflow**.
2. Entrez des commentaires sur les modifications apportées au workflow, puis cliquez sur **OK**.
3. Si toutes les erreurs et les avertissements ont été résolus, la page **Activer le workflow** s'affiche. Permet de sélectionner l'une des options suivantes :

    - Pour activer cette version du workflow, cliquez sur **Activer la nouvelle version**. Lorsqu'un workflow est activé, les utilisateurs peuvent y soumettre des documents pour traitement.
    - Si vous ne souhaitez pas activer cette version, cliquez sur **Ne pas activer la nouvelle version**. Vous pouvez activer le workflow ultérieurement.
