---
title: Espace de travail Liste de contrôle de contrôle des données
description: L'espace de travail Liste de contrôle de contrôle des données vous permet de suivre les processus de validation des données pour les sociétés, les secteurs et les individus. La liste de contrôle peut être utilisée lors d'une implémentation, après une mise à niveau ou après une migration.
author: bking
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DataValidationWorkspace
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: bking
ms.openlocfilehash: 17d8fc2ebc626068b77725329bc6e0d5013d7dc6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191360"
---
# <a name="data-validation-checklist-workspace"></a>Espace de travail Liste de contrôle de contrôle des données

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble de l'espace de travail **Liste de contrôle de contrôle des données** et de la configuration associée.

L'espace de travail **Liste de contrôle de contrôle des données** vous permet de suivre les processus de validation des données pour les sociétés, les secteurs et les individus. La liste de contrôle peut être utilisée lors d'une implémentation, après une mise à niveau ou après une migration. Selon votre affichage de l'espace de travail **Liste de contrôle de contrôle des données**, vous verrez l'ensemble des tâches et statuts d'un projet de contrôle des données, ou seulement les tâches qui vous sont affectées.

Vous devez commencer par sélectionner un projet de contrôle des données en haut de l'espace de travail. Toutes les données qui figurent sur l'espace de travail sont ensuite filtrées pour le projet de contrôle des données sélectionné.

## <a name="summary-tiles"></a>Vignettes récapitulatives

Les vignettes **Synthèse** fournissent une vue d'ensemble du processus, et les indicateurs vous permettent d'utiliser le processus de validation de données lors du suivi. Vous pouvez voir toutes les tâches restantes, tâches terminées, tâches en cours et tâches non commencées relatives au processus. Ces informations sont destinées à toutes les sociétés incluses dans le projet de contrôle des données sélectionné.

## <a name="tasks-and-status-section"></a>Section Tâches et statuts

Dans la section **Tâches et statut**, le statut du projet général de contrôle de données s'affiche de plusieurs manières : statut par entité juridique, par zone, puis par liste de tâches. Vous pouvez également sélectionner le filtre pour afficher le statut d'une société spécifique. Chaque onglet de statut fournit une répartition en pourcentage terminé et en nombre de tâches restantes.

Le dernier onglet concerne la liste des tâches détaillée. Cette liste affiche la liste complète des tâches.
Vous pouvez filtrer la liste des tâches de plusieurs manières. Cliquez sur **Modifier la tâche** pour modifier le statut d'une tâche ou affecter une tâche. Cliquez sur **Documents joints** pour afficher les pièces jointes pour une tâche.

Le nom de la tâche est un lien hypertexte vers la page où l'utilisateur doit aller pour terminer le travail. Vous pouvez définir ce lien hypertexte à l'aide du champ **Nom de l'option de menu** lorsque vous modifiez ou créez une tâche dans l'écran **Configurer le projet de contrôle des données**.

Vous pouvez joindre des fichiers, des notes, des images et des URL à une tâche à l'aide de l'action **Documents joints**. Par exemple, vous pouvez joindre un fichier d'état imprimé pour une tâche. Une icône apparaît dans la colonne **Pièce jointe** concernant la tâche si une pièce jointe est présente.

L'option **Complété par** sera rempli automatiquement à la fin de la tâche avec le nom du collaborateur qui a effectué la tâche. Lorsqu'une tâche est marquée comme terminée, le champ **Date de fin** est automatiquement mis à jour avec la date et l'heure actuelles.

## <a name="configure-data-validation-project-page"></a>Configurer la page du projet de contrôle des données

Avant de pouvoir utiliser l'espace de travail **Liste de contrôle de contrôle des données**, vous devez configurer un processus à l'aide de la page **Configuration du projet de contrôle des données**. (Cliquez sur **Espaces de travail** \> **Liste de contrôle de contrôle des données** \> **Configurer le projet de contrôle des données**.)

## <a name="task-areas"></a>Zones des tâches

Les zones de tâches permettent de regrouper les tâches de validation des données en zones logiques de propriété au sein de votre organisation. Par exemple, la Comptabilité fournisseur, la Comptabilité client ou la Comptabilité peuvent être utilisées comme des zones de tâches.

Le **Nom de l'option de menu** est associé au travail correspondant à la tâche et peut être utilisé pour accéder directement à la page associée à partir du lien de tâche dans l'espace de travail. Par exemple, une tâche de contrôle de données pour exécuter le rapport **Balance âgée de Comptabilité fournisseur** pour la Comptabilité fournisseur peut être liée à la page de **État balance âgée de Comptabilité fournisseur**.
