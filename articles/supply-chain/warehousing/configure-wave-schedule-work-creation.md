---
title: Planifier la création de travail pendant la vague
description: Cette rubrique décrit comment configurer et utiliser la méthode de traitement de vague Planifier la création de travail.
author: perlynne
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5e9dc9b7cf33f9393f408d8f8a458e9b0ea47639
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778375"
---
# <a name="schedule-work-creation-during-wave"></a>Planifier la création de travail pendant la vague

[!include [banner](../../includes/banner.md)]

Utilisez la fonctionnalité *Planifier la création de travail* dans le cadre de votre processus de traitement de vague pour accroître le débit de traitement de vague en faisant en sorte que le système crée le travail à l’aide du traitement parallèle.

Lorsque la fonctionnalité est activée, le travail planifié est automatiquement créé, ce que le système traitera éventuellement pour créer un travail réel. Si le nombre de lignes de chargement d’onde atteint un seuil prédéterminé, le système créera un travail réel plus rapidement en appliquant un traitement parallèle et asynchrone.

## <a name="turn-on-the-scheduled-work-creation-features-in-feature-management"></a>Activer les fonctionnalités de création de travail planifiée dans la gestion des fonctionnalités

Pour utiliser les fonctionnalités décrites dans cette rubrique, elles doivent être activées pour votre système. Utilisez l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités suivantes dans l’ordre indiqué :

1. **Blocage des tâches à l’échelle de l’organisation** : Requis pour la configuration manuelle et automatique de la création de travail planifiée. (À partir de la version 10.0.21, de Supply Chain Management, cette fonctionnalité est obligatoire, elle est donc activée par défaut et ne peut plus être désactivée.)
1. **Planifier la création du travail** : Requis pour la configuration manuelle et automatique de la création de travail planifiée.
1. **Méthode de vague « Planifier la création du travail » à l’échelle de l’organisation** : Requis pour la configuration manuelle et automatique de la création de travail planifiée. Vous n’avez pas besoin de cette fonctionnalité si vous n’utilisez que la configuration manuelle.

<a name="Auto-enable-schedule-work-creation"></a>

## <a name="automatically-configure-scheduled-work-creation"></a>Configurer automatiquement la création de travail planifiée

Si vous activez la fonctionnalité *Méthode de vague « Planifier la création du travail » à l’échelle de l’organisation*, ce qui suit se produit automatiquement sur votre système :

- La méthode de vague *Planifier la création du travail* (`WHSScheduleWorkCreationWaveStepMethod`) est ajoutée et configurée pour s’exécuter en parallèle sur toutes les entités juridiques.
- Les modèles de vagues de toutes les entités juridiques dont les options **Type de modèle de vague** définie sur *Expédition* et **Statut du modèle** définie sur *Valide* auront la méthode *Créer un travail* remplacée par la méthode *Planifier la création du travail*. Cependant, les modèles de vague provenant d’entités juridiques où la méthode *Créer un travail* peut être répétée ne seront pas modifiés.
- Les configurations de tâche pour la méthode *Planifier la création du travail* sera créée pour tous les entrepôts de toutes les entités juridiques où l’option **Utiliser les processus de gestion d’entrepôt** est activée. Cela signifie que la méthode *Planifier la création du travail* fonctionnera désormais en parallèle par défaut. Les entrepôts existants pour lesquels vous changez l’option **Utiliser les processus de gestion d’entrepôt** de *Non* à *Oui* exécuteront également cette méthode en parallèle par défaut.
- Toutes les entités juridiques traiteront les vagues par lots et l’option **Attendre le verrouillage (ms)** sera définie sur une valeur par défaut de *60 000* ms si elle était précédemment définie sur *0* ms.
- Tous les nouveaux modèles de vagues que vous créerez auront la méthode de vague *Planifier la création du travail* au lieu de la méthode *Créer un travail*.

Les configurations existantes de traitement des tâches et des vagues seront également conservées pour toutes les entités juridiques déjà configurées pour traiter les vagues par lots, et pour tous les entrepôts déjà configurés pour utiliser la méthode *Planifier la création du travail* en parallèle.

Si nécessaire, vous pouvez rétablir manuellement tout ou partie des paramètres définis automatiquement lorsque vous avez activé la fonctionnalité *Méthode de vague « Planifier la création du travail » à l’échelle de l’organisation* en procédant comme suit :

- Pour les modèles de vague, accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**. Remplacez la méthode *Planifier la création du travail* par *Créer un travail*.
- Pour les paramètres d’entrepôt, accédez à **Gestion des entrepôts \> Paramétrage \> Paramètres de gestion des entrepôts**. Sur l’onglet **Traitement des vagues**, appliquez vos valeurs préférées pour **Traiter les vagues par lots** et **Attendre le verrouillage (ms)**.
- Pour les méthodes de vague, accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**. Sélectionnez `WHSScheduleWorkCreationWaveStepMethod` et, dans le volet Actions, sélectionnez **Configuration de tâche**. Modifiez ou supprimez le nombre de tâches de traitement par lots et le groupe de vagues affecté pour chaque entrepôt répertorié, selon vos besoins.

## <a name="manually-configure-scheduled-work-creation"></a>Configurer manuellement la création de travail planifiée

Si vous n’avez pas activé la fonctionnalité [*Méthode de vague « Planifier la création du travail » à l’échelle de l’organisation*](#Auto-enable-schedule-work-creation), vous pouvez utiliser les procédures fournies dans cette section pour configurer manuellement la création de travail planifiée selon vos besoins.

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
1. Sélectionnez la flèche pointant vers la colonne **Méthodes sélectionnées** pour déplacer la ligne sélectionnée vers cette colonne. (Vous ne pouvez avoir qu’une seule méthode sélectionnée à la fois qui utilise soit `WHSScheduleWorkCreationWaveStepMethod`, soit `createWork`, de telle sorte que la ligne existante avec **Nom de la méthode** `createWork` soit automatiquement déplacée vers la grille **Méthodes restantes**.)

## <a name="set-wave-task-processing-threshold-data"></a>Définir les données de seuil de traitement de la tâche de vague

Le système créera des données de seuil de traitement de tâche de vague par défaut la première fois qu’un processus de vague s’exécute en utilisant un traitement basé sur une tâche. Les données sont utilisées pour contrôler le moment où le traitement de vague s’exécutera de manière asynchrone et sera basé sur les tâches, ce qui lui permet de traiter et de créer un travail en parallèle.

Les données par défaut utiliseront initialement une valeur seuil de 15 pour le nombre minimum de lignes de chargement (`MINIMUMWAVELOADLINES`). Cela signifie que lorsque le système traite une vague avec plus de 15 lignes de chargement, il utilisera un traitement de tâche asynchrone. Vous pouvez insérer/mettre à jour manuellement ces données dans la table `WHSWaveTaskProcessingThresholdParameters` dans vos environnements de test. Si vous devez modifier ce paramètre dans un environnement de production, vous devez contacter le support Microsoft pour demander la mise à jour.

## <a name="work-with-the-scheduled-work-creation"></a>Utilisation de la création de travail planifiée

Pour plus d’informations sur la manière d’utiliser la création de travail planifiée, voir [Création et traitement des vagues](wave-processing.md). 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
