---
title: Création d’ordres de travail
description: Cette rubrique explique comment créer des ordres de travail dans le module Gestion des actifs.
author: johanhoffmann
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 76306fb31e7e5297e6a5d64b97b5bd09b64349ee
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500572"
---
# <a name="creating-work-orders"></a>Création d’ordres de travail

[!include [banner](../../includes/banner.md)]

Lorsque vous avez planifié des tâches de maintenance préventive, l’étape suivante consiste à créer des ordres de travail pour ces tâches. Vous pouvez effectuer cette étape en utilisant l’un des programmes de maintenance. Les tâches prévues dans un programme de maintenance peuvent avoir des types de références différents, comme décrit dans la table suivante :

| Type de référence | Description  |
|---|---|
| Plans de maintenance | Des tâches de maintenance préventive basées sur des types de plan de maintenance *Heure* ou *Compteur*. |
| Visites de maintenance | Des tâches de maintenance préventive contenant plusieurs actifs nécessitant un type de maintenance similaire. |
| Demande de maintenance | Une demande créée manuellement pour la maintenance ou la réparation d’un actif. Cette demande peut être convertie en ordre de travail. |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a>Créer des ordres de travail en fonction de votre programme de maintenance

Pour créer des ordres de travail basés sur votre programme de maintenance, procédez comme suit.

1. Ouvrez l’une des pages suivantes, selon la manière dont vous souhaitez sélectionner les éléments de planification pour vos ordres de travail :

    - Tout le programme de maintenance (**Gestion des actifs \> Programme de gestion \> Tout le programme de maintenance**)
    - Ouvrir les lignes du programme de maintenance (**Gestion des actifs \> Programme de gestion \> Ouvrir les lignes du programme de maintenance**)
    - Ouvrir les regroupements du programme de maintenance (**Gestion des actifs \> Programme de gestion \> Ouvrir les regroupements du programme de maintenance**)

1. Dans la grille, cochez la case de chaque tâche de maintenance planifiée pour laquelle vous souhaitez créer un ordre de travail. Puis, dans le volet Actions, sélectionnez **Ordre de travail**.

    La boîte de dialogue **Créer des ordres de travail** apparaît. Le champ **Heures de prévision en matière de maintenance** affiche le nombre total d’heures prévues pour les lignes sélectionnées.

    ![Boîte de dialogue Créer des ordres de travail](media/18-preventive-maintenance.png)

1. Dans la section **Paramètres**, spécifiez le nombre d’ordres de travail à créer. Permet de sélectionner l’une des options suivantes :

    - **Un ordre de travail par ligne** : créez un ordre de travail par ligne du programme de maintenance.
    - **Un ordre de travail par** : créez des ordres de travail regroupés en fonction des paramètres des autres options disponibles lorsque vous sélectionnez cette option.

1. Dans le champ **Type d’ordre de travail**, sélectionnez le type d’ordre de travail à utiliser pour tous les ordres de travail que vous créez.
1. Sélectionnez **OK** pour créer les ordres de travail selon vos paramètres.

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a>Regrouper les lignes d’ordre de travail qui sont automatiquement créées lors de l’exécution d’un plan de maintenance

[!INCLUDE [preview-banner-section](../../../includes/preview-banner-section.md)]

Cette fonction vous permet de définir des règles de regroupement des lignes d’ordre de travail sous un seul ordre de travail lorsque le système est configuré pour générer automatiquement des ordres de travail, en fonction d’un plan de maintenance. Auparavant, les ordres de travail générés automatiquement ne pouvaient contenir qu’une seule ligne. Cependant, vous pouvez désormais regrouper les ordres de travail par exemple, par actif, par type d’actif ou par emplacement fonctionnel. (Les ordres de travail générés manuellement peuvent déjà être regroupés de cette manière, comme décrit dans la section précédente de cette rubrique.)

### <a name="enable-grouping-for-automatically-generated-work-orders"></a>Activer le regroupement pour les ordres de travail générés automatiquement

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des actifs*
- **Nom de fonctionnalité :** *(aperçu) Appliquer les règles de regroupement d’ordres de travail lors de l’exécution d’un plan de maintenance*

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a>Configurer le regroupement pour les ordres de travail générés automatiquement

Pour configurer le regroupement pour les ordres de travail générés automatiquement, procédez comme suit.

1. Accédez à **Gestion des actifs \> Paramétrage \> Maintenance préventive \> Plans de maintenance**.
1. Pour chaque plan dans lequel vous souhaitez générer des ordres de travail groupés, procédez comme suit :

    1. Dans le volet de liste, sélectionnez le plan.
    1. Sur l’organisateur **Lignes**, veillez à ce que la case **Création automatique** soit cochée sur chaque ligne.

1. Accédez à **Gestion des actifs \> Périodique \> Maintenance préventive \> Planifier les plans de maintenance**.
1. Dans la boîte de dialogue **Planifier les plans de maintenance**, dans la section **Période**, spécifiez la période du plan (jusqu’où il faut regarder vers l’avant lors de la recherche de tâches de maintenance planifiées pour lesquelles générer du travail).
1. Définissez l’option **Créer automatiquement un ordre de travail à partir du calendrier** sur *Oui*.
1. Dans la section **Ordre de travail**, sélectionnez l’une des options suivantes :

    - **Un ordre de travail par ligne** : créez un ordre de travail par ligne du programme de maintenance. (Cette option fournit les mêmes fonctionnalités disponibles lorsque la fonctionnalité *Appliquer les règles de regroupement d’ordres de travail lors de l’exécution d’un plan de maintenance* est désactivée.)
    - **Un ordre de travail par** : créez des ordres de travail regroupés en fonction des paramètres des autres options disponibles lorsque vous sélectionnez cette option.

1. Si vous souhaitez que les options s’appliquent lorsque vous n’exécutez que certains de vos plans de maintenance, sur l’organisateur **Enregistrements à inclure**, ajoutez des filtres selon vos besoins, comme vous pourriez le faire pour d’autres tâches de traitement par lots dans Microsoft Dynamics 365 Supply Chain Management.
1. Sur l’organisateur **Exécuter à l’arrière-plan**, configurez les options de traitement par lots et de planification selon vos besoins, comme vous le feriez pour d’autres tâches de traitement par lots dans Supply Chain Management.
1. Sélectionnez **OK** pour exécuter et/ou planifier les plans de maintenance sélectionnés.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]