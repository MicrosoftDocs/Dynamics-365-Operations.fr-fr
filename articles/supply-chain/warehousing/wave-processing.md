---
title: Création et traitement des vagues
description: Cette rubrique décrit comment créer, traiter, et lancer une vague pour créer un travail de prélèvement pour une charge, une expédition, un ordre de fabrication, ou une commande kanban.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, WHSParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage, WHSProdWaveTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 4bf47b15b668a37f12edb3dbb842d19655fac97a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019025"
---
# <a name="wave-creation-and-processing"></a>Création et traitement des vagues

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer, traiter, et lancer une vague pour créer un travail de prélèvement pour une charge, une expédition, un ordre de fabrication, ou une commande kanban. Vous pouvez créer des vagues pour les types de commandes suivants :

- **Commandes client** – Utilisez des vagues d’expédition pour inclure les lignes des commandes client. Lorsqu’une commande client est lancée dans l’entrepôt, les lignes de commande client peuvent être incluses dans la vague.
- **Ordres de fabrication** – Utilisez des vagues de production pour inclure les lignes de la nomenclature pour un produit.
- **Commandes kanban** – Les vagues kanban incluent les lignes de prélèvement des commandes kanban.

Pour les commandes client et des commandes kanban, le stock doit être réservé avant que la commande ne soit libérée dans l’entrepôt. Sinon, les articles ou les lignes de répartition ne pourront pas être traités dans une vague. Toutefois, les ordres de fabrication sont légèrement plus flexibles. Pour les ordres de fabrication, vous pouvez choisir l’une des options suivantes :

- Exiger que toutes les matières premières soient réservées avant qu’une commande puisse être libérée dans l’entrepôt.
- Autoriser la libération des ordres de fabrication dans l’entrepôt, même si toutes les matières premières ne peuvent être réservées. Si vous sélectionnez cette option, vous devez répéter manuellement le processus de libération dans l’entrepôt lorsque des matières premières supplémentaires deviennent disponibles. Par exemple, cela peut s’avérer utile si vous disposez des matières premières nécessaires pour démarrer une production, et si pouvez attendre jusqu’à ce que les matières premières supplémentaires deviennent disponibles.

Vous pouvez spécifier laquelle de ces options d’ordre de fabrication utiliser par défaut à l’aide du champ **Exigence de réservation de matière** sur la page **Paramètres de contrôle de la production**. Toutefois, vous pouvez modifier le paramètre pour chaque ordre de fabrication selon les besoins. Pour plus d’informations, voir [Paramètres d’entrepôt pour le traitement des vagues](wave-warehouse-parameters.md).

## <a name="create-and-process-a-wave"></a>Créer et traiter une vague

Le schéma suivant montre le flux de création, de traitement et de libération des vagues d’expédition. Les numéros correspondent aux sections ultérieures de la présente section.

![Processus de création d’une vague](media/wave-processing-diagram.png "Processus de création d’une vague")

### <a name="prerequisites"></a>Conditions préalables

Avant de commencer, un modèle de vague doit être disponible pour le type de vague que vous souhaitez créer (expédition, production ou kanban). Le modèle de vague établit de nombreux paramètres pour la façon dont la vague sera générée et traitée. Cela comprend les étapes qui doivent être effectuées manuellement et celles qui sont effectuées automatiquement. Pour plus d’informations, voir [Modèles de vague](wave-templates.md).

### <a name="create-a-wave"></a>Créer une vague

#### <a name="automatically-create-waves-based-on-warehouse-and-order-type"></a>Créer automatiquement des vagues en fonction de l’entrepôt et du type de commande

Pour créer des vagues automatiquement, configurez des [Modèles de vagues](wave-templates.md) qui s’appliquent à chaque type de commande et entrepôt pertinent. Assurez-vous que chaque modèle a l’option **Automatiser la création de vagues** définie sur *Oui*.

#### <a name="manually-create-waves"></a>Créer des vagues manuellement

Pour créer manuellement une vague, procédez comme suit :

1. Assurez-vous que les [Modèles de vagues](wave-templates.md) ne sont pas configurés pour créer automatiquement une vague pour l’entrepôt et les types de commande pour lesquels vous souhaitez le faire manuellement.
1. Selon le type de vague à créer, effectuez l’une des actions suivantes :

    - Accédez à **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues d’expédition** \> **Toutes les vagues**. Dans le volet Actions, sélectionnez **Vague**.
    - Accédez à **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues de production** \> **Toutes les vagues de production**. Dans le volet Actions, sélectionnez **Vague de production**.
    - Accédez à **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues kanban** \> **Toutes les vagues kanban**. Dans le volet Actions, sélectionnez **Créer une vague**.

1. Dans le champ **Description**, entrez une brève description de la vague. Elle doit indiquer ce que vous traitez dans la vague.

1. Dans le champ **Nom du modèle de vague**, sélectionnez le modèle de vague pour le type de vague à créer. Le modèle de vague contient les méthodes de vague qui exécuteront des actions comme la création d’un travail pour la vague. Par exemple, le modèle de vague pour les vagues d’expédition peut contenir des méthodes de création de charges, d’allocation de lignes aux vagues, de réapprovisionnement, et de création d’un travail de prélèvement pour la vague.

1. Si vous voulez utiliser des attributs de vague comme critères supplémentaires pour la vague, sélectionnez les attributs dans les champs **Attributs de la vague**.

### <a name="specify-what-to-include-in-a-wave"></a>Spécifier ce que doit inclure une vague

Une fois qu’une vague a été créée, vous êtes prêt à commencer à y ajouter du contenu.

> [!NOTE]
> Si nécessaire, vous pouvez ajouter des lignes à une vague même après qu’elle a été traitée, tant qu’elle n’a pas été libérée.

#### <a name="automatically-specify-what-to-include-in-a-wave"></a>Spécifier automatiquement ce que doit inclure une vague

Pour créer des vagues automatiquement, configurez des [Modèles de vagues](wave-templates.md) qui s’appliquent à chaque type de commande et entrepôt pertinent. Assurez-vous que chaque modèle a l’option **Automatiser la création de vagues** définie sur *Oui*. Sinon, votre modèle peut attribuer automatiquement des lignes à toute vague ouverte qualifiée si l’option **Attribuer aux vagues ouvertes** est définie sur *Oui*.

#### <a name="manually-specify-what-to-include-in-a-wave"></a>Spécifier manuellement ce que doit inclure une vague

Lorsqu’une vague a été créée mais pas encore publiée, vous pouvez spécifier manuellement ce qu’il faut y inclure. Pour ajouter manuellement des lignes à une vague :

1. Selon le type de vague auquel vous voulez ajouter des lignes, effectuez l’une des actions suivantes :

    - Accédez à **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues d’expédition** \> **Toutes les vagues**. Dans le volet Actions, sélectionnez **Vague**.
    - Accédez à **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues de production** \> **Toutes les vagues de production**. Dans le volet Actions, sélectionnez **Vague de production**.
    - Accédez à **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues kanban** \> **Toutes les vagues kanban**. Dans le volet Actions, sélectionnez **Créer une vague**.

1. Sélectionnez la vague. Sur le volet Actions, sélectionnez l’un des éléments suivants :

      - **Mettre à jour les expéditions**
      - **Tenir à jour les productions**
      - **Tenir à jour les prélèvements de tâche de kanban**

1. Dans la partie supérieure de la fenêtre, sélectionnez la ligne à ajouter à la vague, puis sélectionnez **Ajouter à la vague**. La ligne est déplacée vers le raccourci **Lignes de vague**.

    Répétez cette étape pour chaque ligne à ajouter. Pour ajouter toutes les lignes, sélectionnez **Tout ajouter**.

    > [!TIP]
    > Pour les vagues d’expédition, vous pouvez rechercher rapidement une commande spécifique en sélectionnant un filtre personnalisé dans le champ **Code de filtre de vague**. Les codes de filtre de vague contiennent des critères de requête pour les expéditions, qui sont créés dans l’écran **Filtres de vague**. Ce champ n’est pas disponible pour les vagues de production ou les vagues kanban.
    > Une coche verte dans la colonne **En vague** indique que l’expédition a été ajoutée à la vague.

### <a name="process-the-wave-to-create-the-picking-work"></a>Traitement de la vague pour créer le travail de prélèvement

Une fois qu’une vague a été créée et contient toutes ses lignes requises, vous êtes prêt à la traiter pour créer le travail de prélèvement correspondant.

#### <a name="automatically-process-a-wave"></a>Traiter automatiquement une vague

Pour traiter automatiquement une vague, configurez les [Modèles de vagues](wave-templates.md) pertinents avec les options de traitement automatique requises.

#### <a name="manually-process-a-wave"></a>Traiter manuellement une vague

Vous pouvez traiter une vague uniquement lorsque son **Statut de vague** est *Créé*. Après avoir traité une vague, le **Statut de vague** passera à *Retenu*.

Pour traiter manuellement une vague comportant tout le contenu requis, procédez comme suit :

1. Selon le type de vague à traiter, effectuez l’une des actions suivantes :

    - Sélectionnez **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues d’expédition** \> **Toutes les vagues**. Dans le volet Actions, sélectionnez **Vague**.
    - Sélectionnez **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues de production** \> **Toutes les vagues de production**. Dans le volet Actions, sélectionnez **Vague de production**.
    - Sélectionnez **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues kanban** \> **Toutes les vagues kanban**. Dans le volet Actions, sélectionnez **Créer une vague**.

1. Sélectionnez la vague à traiter. Dans le volet Actions, sélectionnez **Processus**.

### <a name="release-the-wave-to-the-warehouse-to-start-picking-and-packing"></a>Lancement de la vague dans l’entrepôt pour commencer le prélèvement et le conditionnement

Vous devez traiter une vague avant de pouvoir la lancer. Lorsque vous lancez la vague, le travail de prélèvement est disponible dans l’entrepôt. Vous pouvez annuler une vague après son lancement, et ajouter d’autres lignes, mais vous ne pouvez pas modifier les lignes.

#### <a name="automatically-release-a-wave"></a>Lancer automatiquement une vague

Pour traiter automatiquement une vague, configurez les [Modèles de vagues](wave-templates.md) pertinents avec les options de traitement automatique requises.

#### <a name="manually-release-a-wave"></a>Lancer manuellement une vague

Pour lancer une vague manuellement, procédez comme suit :

1. Selon le type de vague à lancer, effectuez l’une des actions suivantes :

      - Sélectionnez **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues d’expédition** \> **Toutes les vagues**. Dans le volet Actions, sélectionnez **Vague**.
      - Sélectionnez **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues de production** \> **Toutes les vagues de production**. Dans le volet Actions, sélectionnez **Vague de production**.
      - Sélectionnez **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues kanban** \> **Toutes les vagues kanban**. Dans le volet Actions, sélectionnez **Créer une vague**.

1. Sélectionnez la vague à lancer. Dans le volet Actions, sélectionnez **Lancer une vague**.

## <a name="containerize-a-wave"></a>Mettre une vague en conteneur

La mise en conteneur automatisée crée des conteneurs et le travail de prélèvement pour les expéditions lorsqu’une vague est traitée. Pour plus de détails sur la façon de la configurer, consultez [Mise en conteneur](wave-containerization.md).

## <a name="work-with-the-scheduled-work-creation"></a>Utilisation de la création de travail planifiée

Quand la fonctionnalité *Planifier la création de travail* est activée, le traitement de vague créera un travail planifié, qui sera éventuellement utilisé par le nouveau processus de création de travail. Lors de la création de travail, le travail est bloqué à l’aide de la fonctionnalité *Blocage des tâches à l’échelle de l’organisation*. Pour plus d’informations, voir [Planifier la création du travail pendant la vague](configure-wave-schedule-work-creation.md).

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

## <a name="cancel-a-wave"></a>Annulation d’une vague

Si nécessaire, vous pouvez annuler une vague qui a été traitée. Pour annuler une vague, ainsi que le travail de prélèvement créé, procédez comme suit :

1. Selon le type de vague à annuler, effectuez l’une des actions suivantes :

      - Accédez à **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues d’expédition** \> **Toutes les vagues**.
      - Accédez à **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues de production** \> **Toutes les vagues de production**.
      - Accédez à **Gestion des entrepôts** \> **Commun** \> **Vagues** \> **Vagues kanban** \> **Toutes les vagues kanban**.

1. Sélectionnez la vague à annuler. Dans le volet Actions, sous l’onglet **Travail**, sélectionnez **Annuler**.

## <a name="review-wave-batch-job-details"></a>Examiner les détails du traitement par lots de la vague

Utilisez la page **Détails du traitement par lots de la vague** pour inspecter les traitements par lots et les tâches associées à n’importe quelle vague. Ceci est particulièrement utile pour résoudre les problèmes d’une vague qui a échoué. Sans cette fonctionnalité, seuls les administrateurs auront généralement accès aux détails des traitements par lots. La page **Détails du traitement par lots de la vague** peut être mise à la disposition des utilisateurs non administrateurs et fournit une vue en lecture seule des traitements par lots et des tâches associées.

### <a name="enable-the-wave-batch-job-details-page"></a>Activer la page Détails du traitement par lots de la vague

Si votre système n’inclut pas déjà la page **Détails du traitement par lots de la vague**, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Détails du traitement par lots de la vague*.

### <a name="use-the-wave-batch-job-details-page"></a>Utiliser la page Détails du traitement par lots de la vague

La page **Détails du traitement par lots de la vague** combine des travaux par lots et les tâches de traitement par lots, ce qui vous permet d’étudier toutes les étapes de la vague sans avoir à naviguer entre un traitement par lots et la liste des tâches des traitements par lots. La page donne également accès au journal du lot et, si vous disposez des autorisations requises, fournit un lien vers la page **Traitements par lots**.

Pour ouvrir cette page, sélectionnez une vague sur l’une des différentes pages de vague, puis sélectionnez **Détails du traitement par lots de la vague** dans le volet Actions.

## <a name="review-load-validation-and-error-messages"></a>Examiner la validation du chargement et les messages et d’erreur

Pendant le traitement de la vague, le système valide et affiche le statut de chaque ligne de chargement dans la vague. Si aucun avertissement n’apparaît, il passe à l’étape de vague suivante. Si des avertissements apparaissent, le système affiche l’erreur suivante après avoir terminé la validation de la vague entière :

> Lignes de chargement non valides trouvées dans la vague. Veuillez supprimer les lignes de chargement non valides.

Vous êtes alors en mesure de passer en revue le statut final de chaque ligne de chargement dans la vague et de corriger tous les avertissements avant de réessayer. Cela vous permet de traiter tous les avertissements en même temps avant de retraiter la vague. (Dans les versions précédentes, le système arrêtait de traiter la vague après le premier avertissement, vous ne pouviez donc corriger les avertissements que l’un après l’autre.)

La façon dont le système affiche vos messages de statut de traitement de la vague dépend de la façon dont vous avez défini l’option **Créer un journal d’historique de traitement des vagues** sur la page **Paramètres de gestion de l’entrepôt**.

- Lorsque l’option **Créer un journal d’historique de traitement des vagues** est définie sur *Non*, les messages de statut de la ligne de chargement sont affichés dans le fichier **Infolog**.
- Lorsque l’option **Créer un journal d’historique de traitement des vagues** est définie sur *Oui*, les messages de statut de la ligne de chargement sont affichés sur la page **Journal d’historique de traitement des vagues**. Pour afficher le journal, accédez à **Gestion d’entrepôt \> Vagues sortantes \> Journal d’historique de traitement des vagues**.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Exemple de configuration de traitement des vagues](tasks/configure-wave-processing.md)
- [Modèles de vague](wave-templates.md)
- [Mise en conteneur](wave-containerization.md)