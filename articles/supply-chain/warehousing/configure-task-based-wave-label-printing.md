---
title: Programmer l’impression d’étiquettes pendant la vague
description: Cet article décrit comment configurer et utiliser la fonctionnalité d’impression d’étiquettes de vague basée sur les tâches.
author: perlynne
ms.date: 12/02/2022
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e788e5a9206e46ada6490d4a0196c7ea8ca6af15
ms.sourcegitcommit: 04e42c495d018e457fb3b038cadc4fe75ecbba12
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2022
ms.locfileid: "9822360"
---
# <a name="schedule-wave-label-printing-during-wave"></a>Programmer l’impression d’étiquettes pendant la vague

[!include [banner](../../includes/banner.md)]

Utilisez la fonctionnalité *Impression d’étiquettes de vague basée sur les tâches* dans le cadre de votre processus de création de vagues pour améliorer son efficacité et pour que le système crée des étiquettes de vague et des travaux dans des tâches distinctes.

Le processus de configuration de l’impression d’étiquettes de vague est complexe et repose sur une configuration et des données principales précises. Il n’est pas rare que la génération d’enregistrements d’étiquettes de vague échoue, et lorsque c’est le cas, tout le traitement de la vague est annulé. La fonctionnalité *Impression d’étiquettes de vague basée sur les tâches* vous permet d’éviter d’avoir à recréer le travail et les lignes de travail chaque fois qu’une étiquette de vague est mal imprimée.

Lorsque vous utilisez la fonctionnalité *Impression d’étiquettes de vague basée sur les tâches*, le système crée d’abord le travail et les lignes de travail. Il crée et imprime ensuite les étiquettes de vague. Enfin, si les étiquettes de vague sont correctement créées, il libère le travail et la vague pour le prélèvement.

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a>Activer la fonction d’impression d’étiquettes de vague basée sur les tâches dans la gestion des fonctionnalités

Pour utiliser les fonctionnalités décrites dans cet article, elles doivent être activées pour votre système. Utilisez l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer les fonctionnalités dans l’ordre suivant :

1. *Blocage des tâches à l’échelle de l’organisation* : cette fonction est requise pour la configuration manuelle et automatique de la création de travail planifiée. (À partir de la version 10.0.21, de Supply Chain Management, cette fonctionnalité est obligatoire, elle est donc activée par défaut et ne peut plus être désactivée.)
1. *Impression d’étiquettes de vague basée sur les tâches* : cette fonction est requise pour séparer l’impression d’étiquettes de vague en une portée de transaction distincte.

## <a name="manually-enable-the-new-wave-step-method"></a>Activer manuellement la nouvelle méthode d’étape de vague

Vous devez d’abord créer la nouvelle méthode d’étape de vague et l’activer pour le traitement de tâche asynchrone parallèle.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**.
1. Dans le volet Actions, sélectionnez **Régénérer la méthode**. Notez que *waveLabelImpression* est ajouté à la liste des méthodes de traitement de vague utilisables dans vos modèles de vague d’expédition.
1. Sélectionnez l’enregistrement où le champ **Nom de la méthode** est défini sur *waveLabelImpression* puis, dans le volet Actions, sélectionnez **Configuration des tâches**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Entrepôt** : sélectionnez l’entrepôt que vous utiliserez pour planifier le traitement de la création de travail. (Si vous utilisez les données de démonstration à des fins de test, vous pouvez sélectionner l’entrepôt *24*.)
    - **Nombre maximum de tâches par lots** : spécifiez un nombre maximum de tâches par lots. Dans la plupart des cas, la valeur doit être comprise entre *8* et *16*. Cependant, nous vous recommandons de faire des expériences pour trouver le réglage optimal pour vos scénarios.
    - **Groupe de traitements par lots pour le traitement de la vague** : sélectionnez un groupe de traitement par lots de vague dédié pour optimiser le traitement de la file d’attente des traitements par lots.

Vous pouvez maintenant mettre à jour un modèle de vague existant afin qu’il utilise la méthode de traitement de vague *Impression d’étiquettes de vague*. Vous pouvez également créer un nouveau modèle de vague qui l’utilise.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans le volet de liste, sélectionnez le modèle de vague à mettre à jour. (Si vous utilisez les données de démonstration à des fins de test, vous pouvez sélectionner l’entrepôt *Expédition par défaut 24*.)
1. Dans le raccourci **Méthodes**, dans la colonne **Méthodes restantes**, sélectionnez la ligne où le champ **Nom** est défini sur *waveLabelPrinting*.
1. Sélectionnez **ajouter** (bouton Flèche droite) pour déplacer la ligne sélectionnée vers la colonne **Méthodes sélectionnées**.
1. Dans le champ **Code étape de vague**, entrez un code d’étape de vague qui sera utilisé pour relier le modèle de vague avec un modèle d’étiquette de vague.

## <a name="set-wave-task-processing-threshold-data"></a>Définir les données de seuil de traitement de la tâche de vague

La première fois qu’un processus de vague s’exécute en utilisant un traitement basé sur une tâche, le système créera des données de seuil de traitement de tâche de vague par défaut. Ces données sont utilisées pour contrôler si le traitement de vague s’exécutera de manière asynchrone et sera basé sur les tâches, de sorte qu’il puisse traiter et créer des étiquettes de vague en parallèle.

Les données par défaut utilisent initialement une valeur seuil de *1* pour le nombre minimum d’ID de travail (`MinimumWorkThresholdForLabelPrinting`). Par conséquent, lorsque le système traite une vague qui a plus d’un ID de travail, il utilise le traitement des étiquettes de vague basé sur les tâches dans une transaction distincte. Vous pouvez insérer ou mettre à jour manuellement ces données dans la table `WHSWaveTaskProcessingThresholdParameters` dans vos environnements de test. Pour modifier les paramètres dans un environnement de production, vous devez contacter le support Microsoft pour demander la mise à jour.

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a>Modifications de la logique de traitement de vague lorsque l’impression d’étiquettes de vague basée sur les tâches est utilisée

Si le traitement de l’étiquette de vague dépasse le seuil de traitement de la tâche de vague, le traitement basé sur la tâche est lancé. Dans le prochain traitement de vague qui correspond au modèle de vague, l’impression d’étiquettes de vague s’exécutera dans une transaction autonome *ttsbegin*/*ttscommit* immédiatement après la création du travail. Si le lancement du travail (déblocage) est configuré sur le modèle de vague pour s’exécuter automatiquement, il ne se produit qu’après que le processus d’impression d’étiquette de vague s’est terminé avec succès.

Si la génération d’étiquette de vague échoue (par exemple, si la conversion de la quantité de travail en quantité d’étiquettes de vague échoue et génère une erreur), seule la transaction appropriée échoue. Le travail créé précédemment demeure figé. Pour corriger les erreurs et imprimer les étiquettes de vague, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez la vague concernée dans la grille.
1. Dans le volet Actions, sous l’onglet **Vague**, dans le groupe **Imprimer**, sélectionnez **Étiquettes de vague**.
1. Suivez les instructions à l’écran pour envoyer les étiquettes à l’impression.
1. Dans le volet Actions, dans l’onglet **Vague**, dans le groupe **Vague**, sélectionnez **Lancer** pour libérer manuellement le travail pour la vague sélectionnée.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Impression d’étiquettes de vague](configure-wave-label-printing.md)
- [Planifier la création du travail pendant la vague](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
