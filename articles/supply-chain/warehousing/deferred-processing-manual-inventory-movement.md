---
title: Traitement différé du mouvement manuel des stocks
description: Cet article décrit comment utiliser le traitement différé du mouvement manuel des stocks dans Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-27
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9acacaddbde22d05d85ab9e11cd1d6de62337a6a
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336393"
---
# <a name="deferred-processing-of-manual-inventory-movement"></a>Traitement différé du mouvement manuel des stocks

[!include [banner](../includes/banner.md)]

Cet article décrit comment utiliser le traitement différé du mouvement manuel des stocks dans Microsoft Dynamics 365 Supply Chain Management.

La fonctionnalité de traitement différé permet aux collaborateurs de l’entrepôt de continuer à effectuer d’autres tâches pendant que l’opération de vente est traitée en arrière-plan. Il est également utile lorsque le serveur peut augmenter de façon ponctuelle ou imprévue le temps de traitement, et que le temps de traitement accru peut affecter la productivité de l’utilisateur. Le type de travail *Mouvement des stocks* a maintenant été ajouté à l’ensemble des types de travail pris en charge par cette fonction.

Le traitement en arrière-plan est réalisé en utilisant la [Fonctionnalité Traiter les événements d’application d’entrepôt](warehouse-app-events.md).

## <a name="turn-on-this-feature-for-your-system"></a>Activez cette fonctionnalité pour votre système

Pour rendre cette fonctionnalité disponible, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Vous devez les activer dans cet ordre :

1. *Blocage des tâches à l’échelle de l’organisation*<br>Depuis la version 10.0.21 de Supply Chain Management, cette fonctionnalité est obligatoire et ne peut pas être désactivée.
1. *Traiter les événements d’application d’entrepôt*<br>Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est activée par défaut. Depuis la version 10.0.29 de Supply Chain Management, cette fonctionnalité est obligatoire et ne peut pas être désactivée.)
1. *Opérations put différées*<br>(Depuis la version 10.0.29 de Supply Chain Management, cette fonctionnalité est obligatoire et ne peut pas être désactivée.)
1. *Traitement différé de l’opération manuelle de mouvement de stock*<br>(Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire et ne peut pas être désactivée.)

## <a name="configure-the-work-processing-policies"></a>Configurer les stratégies de traitement du travail

Pour utiliser le traitement différé, vous devez configurer et utiliser une stratégie de traitement du travail. Pour le traitement différé des ventes, la fonctionnalité [Traitement différé du travail d’entrepôt](deferred-put.md) prend en charge les types de travail suivants : *Commande client*, *Émission d’un ordre de transfert*, et *Réapprovisionnement*. Les fonctionnalités *Traitement différé de l’opération de mouvement manuel des stocks* ajoute un nouveau type de travail : *Mouvement des stocks*.

Pour configurer une stratégie de traitement de travail, procédez comme suit :

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Travail \> Stratégies de traitement de travail**.
1. Sélectionnez une stratégie existante dans la liste ou créez une nouvelle stratégie en sélectionnant **Nouveau** dans le volet Actions. L’en-tête de chaque stratégie comporte les champs suivants :

    - **Nom de stratégie de traitement de travail** – Nom de la stratégie de traitement de travail.
    - **Description** – Description de la stratégie de traitement de travail.

1. Sur le raccourci **Règles de traitement**, configurez la collection de règles que la stratégie appliquera. Utilisez les boutons de la barre d’outils pour ajouter et supprimer des règles selon vos besoins. Pour chaque règle, définissez les champs suivants :

    - **Type d’ordre de travail** – Sélectionnez le type de travail auquel s’applique la stratégie.
    - **Opération** – Sélectionnez l’opération que la politique utilise pour le traitement. Si vous avez sélectionné *Mouvement des stocks* dans le **Type d’ordre de travail**, vous n’avez pas à définir ce champ, car les opérations de prélèvement et les opérations de placement sont traitées comme un événement unique.
    - **Méthode de traitement du travail** – Sélectionnez la méthode utilisée pour traiter la ligne de travail. Si vous avez sélectionné *Immédiat*, le comportement est le même que quand aucune stratégie de traitement du travail n’est utilisée pour traiter la ligne. Si vous sélectionnez *Différé*, le système appliquera un traitement différé qui utilise la structure de traitement par lots.
    - **Seuil de traitement différé** – Si vous définissez ce champ sur *0* (zéro), il n’y a pas de seuil. Dans ce cas, la méthode de traitement *Différé* est utilisée si possible. Si le calcul du seuil spécifique est inférieur au seuil, la méthode *Immédiat* est utilisée. Sinon, la méthode *Différé* est utilisée si possible. Pour les travaux liés aux ventes et aux transferts, le seuil est calculé en tant que nombre de lignes de charge source associées en cours de traitement pour le travail. Pour le travail de réapprovisionnement, le seuil est calculé en tant que nombre de lignes de travail qui sont réapprovisionnées par le travail. En paramétrant un seuil de, par exemple, *5* pour les ventes, vous êtes assuré que les travaux plus petits qui ont moins de cinq lignes de charge source initiales n’utiliseront pas de traitement différé, mais que les travaux plus grands l’utiliseront. Le seuil n’a d’effet que si le champ **Méthode de traitement du travail** est défini sur *Différé*.
    - **Groupe de lots de traitement différé** – Spécifiez le groupe de lots utilisé pour le traitement. Si vous avez sélectionné *Mouvement des stocks* dans le **Type d’ordre de travail**, vous n’avez pas à définir ce champ, car le groupe de lots est sélectionné dans la boite de dialogue **Traiter les événements de l’application d’entrepôt**.

## <a name="assign-the-work-creation-policy"></a>Affecter la stratégie de création de travail

Pour plus d’informations sur l’attribution d’une stratégie de création de travail, voir [Traitement différé du travail d’entrepôt](deferred-put.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurer un traitement par lots pour traiter les événements de l’application d’entreposage

Pour utiliser le processus *Traitement différé de l’opération de mouvement manuel des stocks*, configurez un travail par lots planifié.

1. Accédez à **Gestion des entrepôts \> Tâches périodiques \> Traiter les événements de l’application d’entreposage**.
1. Dans la boîte de dialogue **Traiter les événements d’application d’entrepôt**, dans le raccourci **Exécuter en arrière-plan**, définissez l’option **Traitement par lots** sur *Oui*.
1. Sélectionnez **Récurrence** et configurez un calendrier d’exécution qui répond aux exigences de votre entreprise.
1. Dans chaque boîte de dialogue, sélectionnez **OK**.

## <a name="inquire-about-the-warehouse-app-events"></a>Demander les événements de l’application d’entreposage

Vous pouvez afficher la file d’attente et les messages d’événements générés par l’application d’entreposage en accédant à **Gestion des entrepôts \> Recherches et états \> Journaux des appareils mobiles \> Événements de l’application d’entreposage**.

Les messages d’événement *Mouvement des stocks* auront un statut *En file d’attente* quand ils sont créés pour la première fois. Ce statut indique que la tâche par lots **Traiter les événements de l’application d’entreposage** sélectionnera et traitera les messages d’événements. Lorsque l’état est mis à jour comme *Terminé*, tous les événements associés sont supprimés de la file d’attente.

Tous les événements *Mouvement des stocks* sont cumulés sous une collection par type d’événement et entrepôt.

Le travail par lots traitera les événements de l’application d’entrepôt en fonction de la récurrence configurée dans la boîte de dialogue **Traiter les événements de l’application d’entrepôt**. Par conséquent, jusqu’à ce qu’un message soit traité, vous pouvez trouver l’ID de l’entrepôt en consultant le champ **Identifiant**.

Le message contient les détails du mouvement (par exemple, les emplacements « de » et « à »).

Pour plus d’informations, voir [Traitement des événements de l’application d’entreposage](warehouse-app-events.md).

## <a name="configure-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Configurer le menu de l’appareil mobile pour ignorer la stratégie de traitement différé

Pour plus d’informations sur la configuration du menu de l’appareil mobile pour ignorer la stratégie de traitement différé, consultez [Traitement différé du travail d’entrepôt](deferred-put.md).

## <a name="impact-on-closed-work-dates"></a>Impact sur les dates de travail clôturées

Pour plus de détails sur l’impact au niveau des dates de clôture des travaux, voir [Traitement différé du travail d’entrepôt](deferred-put.md).

## <a name="additional-resources"></a>Ressources supplémentaires

- [Traitement différé du travail d’entrepôt](deferred-put.md)
- [Traitement des événements de l’application d’entrepôt](warehouse-app-events.md)
- [Configurer les appareils mobiles pour le travail d’entrepôt](configure-mobile-devices-warehouse.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
