---
title: Création de modèles de temps de travail
description: Les modèles de temps de travail définissent les heures de travail au cours d’une semaine et permettent de générer des temps de travail pour une période.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130a21d08e4e720f8bf803a5d4b03d315cefc26f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580670"
---
# <a name="create-working-time-templates"></a>Création de modèles de temps de travail

[!include [banner](../../includes/banner.md)]

Les modèles de temps de travail définissent les heures de travail au cours d’une semaine et permettent de générer des temps de travail pour une période. Cette procédure vous indique comment définir un modèle de temps de travail à l’aide des propriétés de la planification du temps de travail pour classer les intervalles de temps de travail par catégorie. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.

1. Accédez à **Espaces de travail > Gestion des cycles de vie des ressources**.
1. Sélectionnez **Modèles de temps de travail**.

## <a name="create-working-time-template"></a>Créer un modèle de temps de travail

1. Sélectionnez **Nouveau**.
1. Dans le champ **Modèle de temps de travail**, tapez une valeur.
1. Tapez une valeur dans le champ **Nom**.
1. Développez la section **Lundi**.
1. Sélectionnez **Ajouter**.
1. Dans le champ **De**, entrez une heure.
    * Spécifiez l’heure à laquelle le travail commence le matin.  
1. Dans le champ **À**, entrez une heure.
    * Spécifiez l’heure à laquelle les collaborateurs prennent leur pause déjeuner.  
1. Sélectionnez **Ajouter**.
1. Dans le champ **De**, entrez une heure.
    * Spécifiez l’heure à laquelle le travail reprend après le déjeuner.  
1. Dans le champ **À**, entrez une heure.
    * Spécifiez la fin de la journée de travail.  

## <a name="replicate-working-times-to-all-week-days"></a>Répliquer les temps de travail à tous les jours de la semaine

1. Sélectionnez **Copier jour**.
    * Copiez les définitions de temps de travail de lundi à mardi.  
1. Cliquez sur **OK**.
1. Sélectionnez **Copier jour**.
    * Copiez les définitions de temps de travail de lundi à mercredi.  
1. Dans le champ **Au**, sélectionnez une option.
1. Cliquez sur **OK**.
1. Sélectionnez **Copier jour**.
    * Copiez les définitions de temps de travail de lundi à jeudi.  
1. Dans le champ **Au**, sélectionnez une option.
1. Cliquez sur **OK**.
1. Sélectionnez **Copier jour**.
    * Copiez les définitions de temps de travail de lundi à vendredi.  
1. Dans le champ **Au**, sélectionnez une option.
1. Cliquez sur **OK**.

## <a name="define-time-slots-for-special-operations"></a>Définir des créneaux horaires pour les opérations spéciales

1. Développez la section **Vendredi**.
1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
1. Dans le champ **Propriété**, saisissez ou sélectionnez une valeur.
1. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
1. Dans le champ **Propriété**, saisissez ou sélectionnez une valeur.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Marquer les jours de week-end comme clôturés pour le prélèvement

1. Développez la section **Samedi**.
1. Sélectionnez *Oui* dans le champ **Clôturé pour prélèvement**.
1. Développez la section **Dimanche**.
1. Sélectionnez *Oui* dans le champ **Clôturé pour prélèvement**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]