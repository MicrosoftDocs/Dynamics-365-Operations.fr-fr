---
title: Régulariser les plans de congé et d’absence
description: Vous pouvez provisionner les congés et les absences dans Dynamics 365 Human Resources pour plusieurs employés ou pour un employé individuel.
author: twheeloc
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 58f8fb26c851aeabe7438846e23625644b68d033
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908828"
---
# <a name="accrue-leave-and-absence-plans"></a>Régulariser les plans de congé et d’absence

>[!Important]
>La fonctionnalité indiquée dans cet article est actuellement disponible pour les clients sur Dynamics 365 Human Resources autonome. Certaines ou toutes les fonctionnalités seront disponibles dans le cadre d’une future version de l’infrastructure Finance après la version 10.0.26 de Finance.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez provisionner les congés et les absences dans Dynamics 365 Human Resources pour plusieurs employés ou pour un employé individuel.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Provisionner les congés et les absences pour plusieurs employés

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Gérer les congés**, sélectionnez **Provisionner les plans de congé et d’absence**.

3. La boîte de dialogue **Régulariser les plans de congé et d’absence** apparaît. Dans **Provisionner pour le**, sélectionnez **Date du jour** ou **Date personnalisée** et entrez une date personnalisée.

4. Si vous souhaitez exécuter des régularisations pour toutes les sociétés, sélectionnez **Toutes les entreprises**. Si vous souhaitez traiter les régularisations pour un plan de congé unique, sélectionnez **Non** pour **Tous les plans**, puis sélectionnez un **Plan de congé**. Si vous sélectionnez toutes les sociétés, vous ne pouvez pas sélectionner un plan de congé individuel.

5. Si vous souhaitez exécuter le processus de provision en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :

    1. Entrez les informations pour le processus de provision.
    2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence, puis sélectionnez **OK**.
    3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.
    4. Cliquez sur **OK**. Le processus de provisionnement s’exécutera avec les paramètres que vous définissez. 

## <a name="accrue-leave-and-absence-for-an-employee"></a>Provisionner les congés et les absences pour un employé

1. Dans le dossier de l’employé, sélectionnez **Congé**.

2. Sélectionnez **Provisionner les congés et les absences**.

3. La boîte de dialogue **Régulariser les plans de congé et d’absence** apparaît. Dans **Provisionner pour le**, sélectionnez **Date du jour** ou **Date personnalisée** et entrez une date personnalisée.

4. Si vous souhaitez exécuter des régularisations pour toutes les sociétés, sélectionnez **Toutes les entreprises**. Si vous souhaitez traiter les régularisations pour un plan de congé unique, sélectionnez **Non** pour **Tous les plans**, puis sélectionnez un **Plan de congé**. Si vous sélectionnez toutes les sociétés, vous ne pouvez pas sélectionner un plan de congé individuel.

5. Si vous souhaitez exécuter le processus de provision en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus de provision.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus de provisionnement s’exécutera avec les paramètres que vous définissez.

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>Supprimer les régularisations de congé et d’absence pour plusieurs employés

Supprimez les enregistrements de provisions pour un plan et une plage de dates spécifiques. Les dates de provision doivent correspondre à la date du jour ou au lendemain.

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Gérer les congés**, sélectionnez **Supprimer les provisions de plans de congé et d’absence**.

3. Dans la boîte de dialogue **Supprimer les provisions de plans de congé et d’absence**, sélectionnez **Plan de congé**.

4. Le cas échéant, choisissez **Supprimer les ajustements de solde**.

5. Saisissez ou sélectionnez une **Date de provision de congés**. Cette date doit être soit aujourd’hui soit une date à venir.

6. Cliquez sur **OK**. Le processus de régularisation supprimera les provisions et les paramètres que vous définissez.

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>Supprimer les provisions de congés et d’absences pour un seul employé

1. Dans le dossier de l’employé, sélectionnez **Congé**.

2. Sélectionnez **Supprimer les provisions de plans de congés et d’absences**.

3. Dans la boîte de dialogue **Supprimer les provisions de plans de congé et d’absence**, sélectionnez **Plan de congé**.

4. Le cas échéant, choisissez **Supprimer les ajustements de solde**.

5. Saisissez ou sélectionnez une **Date de provision de congés**. Cette date doit être soit aujourd’hui soit une date à venir.

6. Cliquez sur **OK**. Le processus de régularisation supprimera les provisions et les paramètres que vous définissez.

## <a name="review-leave-accrual-and-deletion-processes"></a>Examiner les processus de régularisation et de suppression des congés

**Audit des provisions de congés** s’affiche chaque fois que vous exécutez ou supprimez une provision pour un ou tous les employés. La date et la personne qui ont effectué l’action s’affichent également.

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.
2. Sous **Gérer les congés**, sélectionnez **Supprimer l’audit de provision de congés**.

## <a name="leave-accrual-rounding"></a>Arrondi de la régularisation des congés
Quand un employé est inscrit ou non inscrit, l’arrondi des congés accumulés sera calculé au prorata. Auparavant, l’arrondi n’était autorisé que quand un plan de congé était défini au prorata et qu’un employé était inscrit/désinscrit au milieu de la période. Les accumulations de congés seront désormais arrondies indépendamment de l’inscription/de la désinscription à mi-période ou au début d’une période.

## <a name="leave-accrual-transaction-auditing"></a>Audit des transactions de régularisation de congés

Cette fonctionnalité aide les responsables des congés et absences à comprendre les transactions de provision de congés et d’absences liées aux soldes de congés d’un employé pour un type de congé spécifique.

Pour afficher les détails de la transaction :

1. Dans le dossier de l’employé, sélectionnez **Congé**.

2. Sélectionnez **Afficher les congés**, puis sélectionnez l’onglet **Soldes**.

Pour afficher les transactions de provision associées à un type de congé spécifique, sélectionnez la valeur numérique dans la colonne **Solde actuel**.

Pour afficher les détails de la transaction pour un montant de provision spécifique, sélectionnez une ligne de provision, ouvrez le volet **Informations associées** à droite, puis ouvrez la section **Détails de la transaction**. La section Détails de la transaction affiche :

- Les modifications du solde du type de congé de l’employé
- Les détails de l’emploi pour la période de provision spécifiée
- Les détails sur la période de provision et les taux
- Les modifications apportées aux configurations du plan de congés

![Afficher l’audit des transactions de provision de congés.](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a>Voir également :

[Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)</br>
[Créer un plan de congé et d’absence](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
