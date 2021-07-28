---
title: Concevoir l’interface d’exécution de l’atelier de production
description: Cette rubrique décrit comment concevoir le contenu de l’interface utilisateur pour chaque configuration.
author: johanhoffmann
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration, JmgProductionFloorExecutionConfigurationTab
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 5bf8ce93d2c804325305672d79b633210a790cf0
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347660"
---
# <a name="design-the-production-floor-execution-interface"></a>Concevoir l’interface d’exécution de l’atelier de production

[!include [banner](../includes/banner.md)]

Vous pouvez concevoir le contenu de l’interface utilisateur pour chaque configuration utilisée par l’interface d’exécution de l’atelier de production. Par exemple, les collaborateurs d’une cellule de travail peuvent avoir besoin de pouvoir ouvrir des instructions de travail dans l’atelier de production, tandis que dans une autre cellule de travail, les instructions ne sont pas nécessaires. Dans ce cas, deux configurations doivent être créées, l’une avec un bouton pour ouvrir les pièces jointes et l’autre sans ce bouton.

## <a name="design-a-tab"></a>Concevoir un onglet

Sur la page **Configurer l’exécution de l’atelier de production**, vous pouvez créer et configurer des onglets en sélectionnant des **onglets Conception** sur le volet Actions.

Chaque onglet est divisé en quatre sections, comme indiqué dans l’illustration suivante.

![Disposition des onglets.](media/pfe-tab-layout.png "Disposition des onglets")

Les éléments suivants sont présentés dans l’illustration :

1. Barre d’outils principale
1. Barre d’outils secondaire
1. Vue principale
1. Vue détaillée

Pour créer et configurer un nouvel onglet, procédez comme suit :

1. Accédez à **Contrôle de la production \> Paramétrage \> Contrôle et suivi de la production \> Configurer l’exécution de l’atelier de production**.

1. Sélectionnez **Onglets de conception** dans le volet Actions pour ouvrir la page **Onglets de conception**.

    ![Page Onglets de conception.](media/pfe-design-tabs.png "Page Onglets de conception")

1. Sélectionnez **Nouveau** dans le volet Actions.

1. Définissez les paramètres suivants dans l’en-tête de la page :

    - **Nom de l’onglet** – Spécifiez un nom pour l’onglet.
    - **Vue principale** – Choisissez entre les deux listes de tâches prédéfinies (*Tâches actives*, *Toutes les tâches* ou *Ma machine*).
    - **Vue détaillée** – Choisissez entre une valeur vide ou **Détails de la tâche**. Si vous sélectionnez la valeur vide, il n’y aura pas de vue détaillée dans l’onglet. Si vous sélectionnez **Détails de la tâche**, la vue détaillée contiendra une description détaillée de la tâche sélectionnée dans la liste des travaux de la vue principale.

1. Dans la section **Barre d’outils principale**, choisissez les boutons qui doivent être disponibles dans la barre d’outils principale. La colonne **Actions disponibles** affiche une liste de tous les boutons qui peuvent être ajoutés. Les colonnes **Actions sélectionnées** affichent une liste de tous les boutons inclus dans la configuration actuelle. Utilisez les boutons entre les colonnes pour déplacer les éléments sélectionnés entre les colonnes selon les besoins. Utilisez les boutons haut et bas à côté de la colonne **Actions sélectionnées** pour contrôler l’ordre dans lequel les boutons sont présentés dans l’interface utilisateur.

1. Dans la section **Barre d’outils** **secondaire**, choisissez les boutons qui doivent être disponibles dans la barre d’outils secondaire. La colonne **Actions disponibles** affiche une liste de tous les boutons qui peuvent être ajoutés. Les colonnes **Actions sélectionnées** affichent une liste de tous les boutons inclus dans la configuration actuelle. Utilisez les boutons entre les colonnes pour déplacer les éléments sélectionnés entre les colonnes selon les besoins. Utilisez les boutons haut et bas à côté de la colonne **Actions sélectionnées** pour contrôler l’ordre dans lequel les boutons sont présentés dans l’interface utilisateur.

## <a name="associate-a-tab-with-a-configuration"></a>Associer un onglet à une configuration

Une fois que vous avez conçu tous les onglets dont vous avez besoin, vous pouvez les associer à une configuration.

1. Accédez à **Contrôle de la production \> Paramétrage \> Contrôle et suivi de la production \> Configurer l’exécution de l’atelier de production**.

    ![Configurer l’exécution de l’atelier de production.](media/pfe-config-prod-floor-execution.png "Configurer l’exécution de l’atelier de production")

1. Dans le raccourci **Sélection d’onglet**, sélectionnez **Ajouter**.

1. Une nouvelle ligne est ajoutée à la grille. Pour cette nouvelle ligne, sélectionnez le nom d’un onglet que vous souhaitez ajouter à la configuration.

1. Continuez à ajouter des onglets supplémentaires si nécessaire.

1. Utilisez les boutons **Déplacer vers le haut** et **Déplacer vers le bas** de la barre d’outils pour organiser les onglets selon les besoins. Les onglets seront affichés de gauche à droite dans l’ordre indiqué dans la capture d’écran ci-dessus (l’onglet en haut est affiché à gauche).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]