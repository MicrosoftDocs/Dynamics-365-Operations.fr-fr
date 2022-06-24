---
title: Charges de travail de fabrication pour les unités d’échelle Cloud et périphérie
description: Cet article décrit le fonctionnement des charges de travail d’exécution de la fabrication avec les unités d’échelle cloud et Edge.
author: johanhoffmann
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: johanho
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: c73c2440d8807e965e5d2d89105c2a8a6971c849
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865322"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a>Charges de travail de fabrication pour les unités d’échelle Cloud et périphérie

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> La charge de travail d’exécution de la fabrication est actuellement disponible uniquement en version préliminaire.
>
> Certaines fonctionnalités d’entreprise ne sont pas entièrement prises en charge dans la version préliminaire publique lorsque les des unités d’échelle de charge de travail sont utilisées.
>
> Vous ne pouvez pas exécuter la charge de travail d’exécution de la fabrication (version préliminaire) sur une unité d’échelle lorsque la charge de travail d’exécution de l’entrepôt est également installée.

Lors de l’exécution de la fabrication, les unités d’échelle offrent les capacités suivantes :

- Les opérateurs de machines et les superviseurs d’atelier peuvent accéder au plan de production opérationnel.
- Les opérateurs de machine peuvent maintenir le plan à jour en exécutant des tâches de fabrication discrètes et de processus.
- Le superviseur de l’atelier peut ajuster le plan opérationnel.
- Les collaborateurs peuvent accéder aux heures et aux présences pour les points d’entrée et de sortie à la périphérie, afin de garantir un calcul correct de la rémunération des collaborateurs.

Cet article décrit le fonctionnement des charges de travail d’exécution de la fabrication avec les unités d’échelle cloud et Edge.

## <a name="the-manufacturing-lifecycle"></a>Cycle de vie de fabrication

Comme le montre l’illustration suivante, le cycle de vie de fabrication est divisé en trois phases : *Planifier*, *Exécuter*, et *Finaliser*.

[![Phases d’exécution de la fabrication lorsqu’un seul environnement est utilisé](media/mes-phases.png "Phases d’exécution de la fabrication lorsqu’un seul environnement est utilisé.")](media/mes-phases-large.png)

La phase _Planification_ comprend la définition du produit, la planification, la création et l’ordonnancement des commandes et la validation. L’étape de libération indique la transition depuis la phase _Planifier_ à la phase _Exécuter_. Lorsqu’un ordre de fabrication est lancé, les travaux d’ordre de fabrication seront visibles dans l’atelier de production et prêts à être exécutés.

Lorsqu’un travail de production est marqué comme terminé, il passe de la phase _Exécuter_ à la phase _Finaliser_. Dans la phase _Finaliser_, les inscriptions de la phase *Exécuter* passent par un workflow d’approbation, où elles sont calculés, approuvés et transférés. À ce stade, l’ordre de fabrication est terminé. Par conséquent, la base de la rémunération des collaborateurs est générée.

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a>Fractionnement de la phase d’exécution en une charge de travail distincte

Comme le montre l’illustration suivante, lorsque des unités d’échelle sont utilisées, la phase _Exécuter_ est divisée en une charge de travail distincte.

[![Phases d’exécution de la fabrication lorsque des unités d’échelle sont utilisées](media/mes-phases-workloads.png "Phases d’exécution de la fabrication lorsque des unités d’échelle sont utilisées.")](media/mes-phases-workloads-large.png)

Le modèle passe désormais d’une installation à instance unique à un modèle basé sur le hub et les unités d’échelle. Les phases _Plan_ et _Finaliser_ s’exécutent comme des opérations de back-office sur le hub et la charge de travail d’exécution de la fabrication s’exécute sur les unités d’échelle. Les données sont transférées de manière asynchrone entre le hub et les unités d’échelle.

Lorsqu’un ordre de fabrication est validé sur le hub, toutes les données nécessaires au traitement des travaux de production sont transférées vers l’unité d’échelle. Ces données incluent les ordres de fabrication, les gammes de production, les nomenclatures et les produits. Les données qui ne sont pas liées à un ordre de fabrication (telles que les activités indirectes, les codes d’absence et les paramètres de production) sont également transférées du hub à l’unité d’échelle. En règle générale, les données qui proviennent du hub et qui sont transférées vers l’unité d’échelle peuvent être créées ou mises à jour uniquement sur le hub. Par exemple, un code d’absence ou une activité indirecte ne peut pas être créé sur l’unité d’échelle, ils ne peuvent être utilisés que pour l’enregistrement. Les enregistrements qui sont effectués sur l’unité d’échelle pendant l’exécution sont ensuite transférés au hub, où l’approbation du temps et des présences, l’inventaire et les mises à jour financières sont traités.

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a>Tâches d’exécution de fabrication pouvant être exécutées sur des charges de travail

Les tâches d’exécution de fabrication suivantes peuvent actuellement être exécutées sur des charges de travail lorsque des unités d’échelle sont utilisées :

- Pointage d’entrée, connexion, pointage de sortie et absence
- Commencer la tâche
- Regroupement de tâches
- Saisie de l’avancement
- Déclarer le rebut
- Activité indirecte
- Rupture
- Déclarer comme terminé et rangé (nécessite que vous exécutiez également la charge de travail d’exécution d’entrepôt sur votre unité d’échelle, voir aussi [Déclarer comme terminé et rangé sur une unité d’échelle](#RAF))

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a>Utilisation des charges de travail d’exécution de fabrication sur le hub

Habituellement, les processus requis pour exécuter les charges de travail d’exécution de la fabrication s’exécutent automatiquement pour maintenir le hub et toutes les unités d’échelle synchronisés, si nécessaire. Cependant, si vous rencontrez des problèmes, vous pouvez déclencher manuellement le traitement des enregistrements bruts reçus des charges de travail et/ou vérifier le journal de traitement des enregistrements.

### <a name="manually-process-raw-registrations"></a>Traiter manuellement les enregistrements bruts

Un traitement par lots dans Supply Chain Management s’exécute automatiquement pour traiter tous les enregistrements qui ont été reçus des charges de travail. Ce traitement crée les journaux de production et les entrées de journal requis lorsqu’un enregistrement est traité pour un travail terminé sur la charge de travail.

Bien que la tâche s’exécute généralement automatiquement, vous pouvez l’exécuter manuellement à tout moment en vous connectant au hub et en accédant à **Contrôle de production \> Tâches périodiques \> Gestion de la charge de travail backoffice \> Traiter les enregistrements bruts**.

### <a name="check-the-raw-registration-processing-log"></a>Vérifier le journal de traitement de l’enregistrement brut

Pour consulter le journal de traitement de l’enregistrement, connectez-vous au hub et accédez à **Contrôle de production \> Tâches périodiques \> Gestion de la charge de travail backoffice \> Journal de traitement d’enregistrement brut**. La page **Journal de traitement d’enregistrement brut** affiche une liste des enregistrements bruts traités et le statut de chaque enregistrement.

![Page Journal de traitement de l’enregistrement brut.](media/mes-processing-log.png "Page Journal de traitement de l’enregistrement brut")

Vous pouvez travailler sur n’importe quel enregistrement de la liste en le sélectionnant, puis en sélectionnant l’un des boutons suivants dans le volet Actions :

- **Traiter** – Traitez manuellement l’enregistrement sélectionné. Cette action peut être utile si la tâche _Traiter les enregistrements bruts_ n’a pas été exécutée ou si elle a échoué.
- **Annuler** – Annulez l’enregistrement sélectionné.

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a>Utilisation des charges de travail d’exécution de fabrication sur un unité d’échelle

Habituellement, les processus requis pour exécuter les charges de travail d’exécution de la fabrication s’exécutent automatiquement pour maintenir le hub et toutes les unités d’échelle synchronisés, si nécessaire. Cependant, si vous rencontrez des problèmes, vous pouvez vérifier l’historique des commandes qui ont été traitées sur unité d’échelle ou exécuter manuellement la tâche _Centre de fabrication pour mettre à l’échelle le processeur de messages d’unité d’échelle_.

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a>Afficher l’historique des travaux de fabrication qui ont été traités sur une unité d’échelle

Pour consulter l’historique des travaux de fabrication qui ont été traités sur une unité d’échelle, connectez-vous à la machine de l’unité d’échelle et accédez à **Contrôle de production \> Tâches périodiques \> Gestion de la charge de travail backoffice \> Historique de traitement des travaux de fabrication**. La page **Historique de traitement des travaux de fabrication** affiche l’historique de traitement des ordres de fabrication sur l’unité d’échelle. Vous pouvez travailler sur n’importe quel ordre de fabrication de la liste en le sélectionnant, puis en sélectionnant l’un des boutons suivants dans le volet Actions :

- **Traiter** – Traiter manuellement l’ordre de fabrication sélectionné.
- **Annuler** – Annuler l’ordre de fabrication sélectionné.

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a>Hub de fabrication pour la tâche du processeur de messages de l’unité d’échelle

La tâche _Hub de fabrication pour le processeur de messages de l’unité d’échelle_ traite les données du hub vers l’unité d’échelle. Ce travail est automatiquement démarré lorsque la charge de travail d’exécution de fabrication est déployée. Cependant, vous pouvez l’exécuter manuellement à tout moment en accédant à **Contrôle de production \> Tâches périodiques \> Gestion de la charge de travail backoffice \> Processeur de message du hub de fabrication vers l’unité d’échelle**.

<a name="RAF"></a>

## <a name="report-as-finished-and-putaway-on-a-scale-unit"></a>Déclarer comme terminé et rangé sur une unité d’échelle

<!-- KFM: 
This section describes how to enable the abilities to report as finished and then putaway finished items when you are using to a scale unit.

### Enable and use report as finished and putaway on a scale unit -->

Dans la version actuelle, les opérations Déclarer comme terminé et rangé (pour les produits finis, les coproduits et les sous-produits) sont prises en charge par la [charge de travail d’exécution de l’entrepôt](cloud-edge-workload-warehousing.md) (pas par la charge de travail d’exécution de la fabrication). Par conséquent, pour utiliser cette fonctionnalité lorsque vous êtes connecté à une unité d’échelle, vous devez procéder comme suit :

- Installez à la fois la charge de travail d’exécution de l’entrepôt et la charge de travail d’exécution de la fabrication sur votre unité d’échelle.
- Utilisez l’application mobile Warehouse Management pour déclarer la fin et traiter le travail de rangement. L’interface d’exécution de l’atelier de production ne prend actuellement pas en charge ces processus.

<!-- KFM: API details needed

### Customize report as finished and putaway functionality

 -->

## <a name="enable-and-use-the-start-operation-on-a-scale-unit"></a>Activer et utiliser l’opération de démarrage sur une unité d’échelle

Dans la version actuelle, l’opération de démarrage de la production et des lots de production est prise en charge par la [charge de travail d’exécution de l’entrepôt](cloud-edge-workload-warehousing.md) (pas par la charge de travail d’exécution de la fabrication). Par conséquent, pour utiliser cette fonctionnalité lorsque vous êtes connecté à une unité d’échelle, vous devez procéder comme suit :

- Installez à la fois la charge de travail d’exécution de l’entrepôt et la charge de travail d’exécution de la fabrication sur votre unité d’échelle.
- Activez la fonctionnalité *Démarrer l’ordre de fabrication sur la charge de travail de gestion d’entrepôt pour l’unité d’échelle cloud ou périphérique* dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Utilisez l’application mobile Warehouse Management pour démarrer la production ou la commande par lots.

## <a name="enable-and-use-material-consumption-on-a-scale-unit"></a>Activer et utiliser la consommation de matières sur une unité d’échelle

Dans la version actuelle, le flux de l’application mobile Warehouse Management pour l’enregistrement de la consommation de matières est pris en charge par la[charge de travail d’exécution de l’entrepôt](cloud-edge-workload-warehousing.md) (pas la charge de travail d’exécution de la fabrication). Par conséquent, pour utiliser cette fonctionnalité lorsque vous êtes connecté à une unité d’échelle, vous devez procéder comme suit :

- Installez à la fois la charge de travail d’exécution de l’entrepôt et la charge de travail d’exécution de la fabrication sur votre unité d’échelle.
- Activez la fonctionnalité *Enregistrer la consommation de matières sur l’application mobile sur une unité d’échelle* dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Utilisez l’application mobile Warehouse Management pour enregistrer la consommation de matières.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
