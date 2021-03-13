---
title: Planifier la création de travail pendant la vague
description: Cette rubrique décrit comment configurer et utiliser la méthode de traitement de vague Planifier la création de travail.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ed8f43c7db139b7b16ac6901d5db56ba2f021690
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078260"
---
# <a name="schedule-work-creation-during-wave"></a>Planifier la création de travail pendant la vague

[!include [banner](../includes/banner.md)]

Utilisez la fonctionnalité *Planifier la création de travail* dans le cadre de votre processus de traitement de vague pour accroître le débit de traitement de vague en faisant en sorte que le système crée le travail à l’aide du traitement parallèle.

Lorsque la fonctionnalité est activée, le travail planifié est automatiquement créé, ce que le système traitera éventuellement pour créer un travail réel. Si le nombre de lignes de chargement d’onde atteint un seuil prédéterminé, le système créera un travail réel plus rapidement en appliquant un traitement parallèle et asynchrone.

## <a name="enable-the-schedule-work-creation-feature"></a>Activer la fonction Planifier la création de travail

### <a name="enable-the-feature-in-feature-management"></a>Activer la fonctionnalité dans la gestion des fonctionnalités

Avant de pouvoir utiliser la fonctionnalité *Planifier la création de travail* doit être activée sur votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Planifier la création de travail*

> [!NOTE]
> La fonctionnalité *Blocage des tâches à l’échelle de l’organisation* doit être activée avant que vous puissiez activer la fonctionnalité *Planifier la création de travail*.

### <a name="manually-enable-batch-processing-of-waves"></a>Activer manuellement le traitement par lots des vagues

Pour tirer parti d’une méthode asynchrone parallèle pour créer un travail d’entrepôt, votre processus de vague doit être exécuté par lots. Pour configurer cela :

1. Accédez à  **Gestion des entrepôts\>Configuration \> Paramètres de gestion des entrepôts**.

1. Sur l’onglet **Général**, définissez **Traiter les vagues dans des traitements par lots** sur *Oui*. En option, vous pouvez également sélectionner un **Groupe de traitements par lots pour le traitement de la vague** pour empêcher le traitement de votre file d’attente par lots de s’exécuter en même temps que d’autres processus.

1. Définissez **Attendre le verrouillage (ms)**, qui s’applique lorsque le système traite plusieurs vagues en même temps. Pour la plupart des processus de traitement par vague plus volumineux, nous recommandons une valeur de *60000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Activer manuellement la nouvelle méthode d’étape de vague pour les modèles de vague existants

Commencez par créer la nouvelle méthode d’étape de vague et activez-la pour le traitement de tâche asynchrone parallèle.

1. Accédez à  **Gestion des entrepôts \>Configuration \> Vagues \> Méthodes de traitement de la vague**.

1. Sélectionnez  **Regenérer des méthodes** et notez que *WHSScheduleWorkCreationWaveStepMethod* a été ajouté à la liste des méthodes de traitement de vague que vous pouvez utiliser dans vos modèles de vague d’expédition.

1. Sélectionnez l’enregistrement avec le **Nom de méthode** *WHSScheduleWorkCreationWaveStepMethod* et sélectionnez **Configuration des tâches**.

1. Pour ajouter une nouvelle ligne à la grille, sélectionnez **Nouveau** sur le volet Actions et utilisez les paramètres suivants :

    - **Entrepôt** : sélectionnez l’entrepôt que vous utiliserez pour planifier le traitement de la création de travail.

    - **Nombre maximum de tâches par lots** : spécifiez un nombre maximum de tâches par lots. Dans la plupart des cas, cette valeur doit être comprise entre 8 et 16, mais nous vous recommandons de tester le paramètre optimal en fonction de vos scénarios.

    - **Groupe de traitements par lots pour le traitement de la vague** : sélectionnez un groupe de traitement par lots de vague dédié pour optimiser le traitement de votre file d’attente des traitements par lots.

Vous êtes maintenant prêt à mettre à jour un modèle de vague existant (ou à en créer un nouveau) pour utiliser la méthode de traitement de vague *Planifier la création de travail*.

1. Accédez à  **Gestion des entrepôts\>Configuration \> Vagues \> Modèles de vague**.

1. Sélectionnez **Modifier** dans le volet Actions.

1. Dans le volet de listes, sélectionnez le modèle de vague que vous souhaitez mettre à jour (si vous testez à l’aide de données de démonstration, vous pouvez utiliser la fonctionnalité *Expédition par défaut 24*).

1. Développez l’organisateur **Méthodes** et sélectionnez la ligne avec le **Nom** *Planifier la création de travail* dans la grille **Méthodes restantes**.

1. Sélectionnez la flèche pointant vers la colonne **Méthodes sélectionnées** pour déplacer la ligne sélectionnée vers cette colonne. (Vous ne pouvez avoir qu’une seule méthode sélectionnée à la fois qui utilise soit *WHSScheduleWorkCreationWaveStepMethod* ou *createWork*, de telle sorte que la ligne existante avec **Nom de méthode** *createWork* soit automatiquement déplacé vers la grille **Méthodes restantes**.)

## <a name="set-wave-task-processing-threshold-data"></a>Définir les données de seuil de traitement de la tâche de vague

Le système créera des données de seuil de traitement de tâche de vague par défaut la première fois qu’un processus de vague s’exécute en utilisant un traitement basé sur une tâche. Les données sont utilisées pour contrôler le moment où le traitement de vague s’exécutera de manière asynchrone et sera basé sur les tâches, ce qui lui permet de traiter et de créer un travail en parallèle.

Les données par défaut utiliseront initialement une valeur seuil de 15 pour le nombre minimum de lignes de chargement (MINIMUMWAVELOADLINES). Cela signifie que lorsque le système traite une vague avec plus de 15 lignes de chargement, il utilisera un traitement de tâche asynchrone. Vous pouvez insérer/mettre à jour manuellement ces données dans la table **WHSWaveTaskProcessingThresholdParameters** dans vos environnements de test, mais si vous devez modifier ce paramètre dans un environnement de production, vous devez contacter le support Microsoft pour demander la mise à jour.

## <a name="work-with-the-feature"></a>Utiliser la fonctionnalité

Quand la fonctionnalité *Planifier la création de travail* est activée, le traitement de vague créera un travail planifié, qui sera éventuellement utilisé par le nouveau processus de création de travail. Lors de la création de travail, le travail est bloqué à l’aide de la fonctionnalité *Blocage des tâches à l’échelle de l’organisation*.

L’organigramme suivant montre comment le travail planifié est créé pendant le traitement de vague.

![Planifier la création du travail](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Travail planifié

La page **Détails du travail planifié** (**Gestion des entrepôts \> Travail \> Détails du travail planifié**) affiche des informations sur le travail planifié, qui est initialement créé lors du traitement de vague. Les valeurs **Statut du processus** suivantes sont disponibles :

- **En file d’attente** : le travail planifié attend d’être utilisé pour créer du travail.
- **Terminé** : le travail planifié a été utilisé pour créer du travail.
- **Échec** : le traitement de vague a échoué. Notez que le travail planifié peut avoir un état défini sur **Échec** avec ou sans travail réel connexe. En cas d’échec du processus de création de travail réel, le travail réel reste défini sur l’état *Annulé*.

### <a name="batch-job-for-the-work-creation-process"></a>Travail par lots pour le processus de création de travail

Pour afficher les travaux par lots pour le traitement des vagues, sélectionnez **Tâches de traitement par lots** dans le volet Actions sur la page **Toutes les vagues**.

À partir de là, vous pouvez afficher tous les détails de la tâche par lots pour chacun des ID de tâche de traitement par lots.
