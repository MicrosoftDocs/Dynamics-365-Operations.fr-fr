---
title: Régulariser les plans de congé et d'absence
description: Vous pouvez provisionner les congés et les absences dans Dynamics 365 Human Resources pour plusieurs employés ou pour un employé individuel.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f045cb7ab9f5e7aa4259f29e1b026f110425c236
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429057"
---
# <a name="accrue-leave-and-absence-plans"></a>Régulariser les plans de congé et d'absence

Vous pouvez provisionner les congés et les absences dans Dynamics 365 Human Resources pour plusieurs employés ou pour un employé individuel.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Provisionner les congés et les absences pour plusieurs employés

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Gérer les congés**, sélectionnez **Provisionner les plans de congé et d'absence**.

3. La boîte de dialogue **Régulariser les plans de congé et d'absence** apparaît. Dans **Provisionner pour le**, sélectionnez **Date du jour** ou **Date personnalisée** et entrez une date personnalisée.

4. Si vous souhaitez exécuter le processus de provision en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus de provision.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus de provisionnement s'exécutera avec les paramètres que vous définissez.

## <a name="accrue-leave-and-absence-for-an-employee"></a>Provisionner les congés et les absences pour un employé

1. Dans le dossier de l'employé, sélectionnez **Congé**.

2. Sélectionnez **Provisionner les congés et les absences**.

3. La boîte de dialogue **Régulariser les plans de congé et d'absence** apparaît. Dans **Provisionner pour le**, sélectionnez **Date du jour** ou **Date personnalisée** et entrez une date personnalisée.

4. Si vous souhaitez exécuter le processus de provision en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus de provision.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus de provisionnement s'exécutera avec les paramètres que vous définissez.

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>Supprimer les régularisations de congé et d'absence pour plusieurs employés

Supprimez les enregistrements de provisions pour un plan et une plage de dates spécifiques. Les dates de provision doivent correspondre à la date du jour ou au lendemain.

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Gérer les congés**, sélectionnez **Supprimer les provisions de plans de congé et d'absence**.

3. Dans la boîte de dialogue **Supprimer les provisions de plans de congé et d'absence**, sélectionnez **Plan de congé**. 

4. Le cas échéant, choisissez **Supprimer les ajustements de solde**.

5. Saisissez ou sélectionnez une **Date de provision de congés**. Cette date doit être soit aujourd'hui soit une date à venir. 

6. Cliquez sur **OK**. Le processus de régularisation supprimera les provisions et les paramètres que vous définissez. 

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>Supprimer les provisions de congés et d'absences pour un seul employé

1. Dans le dossier de l'employé, sélectionnez **Congé**.

2. Sélectionnez **Supprimer les provisions de plans de congés et d'absences**.

3. Dans la boîte de dialogue **Supprimer les provisions de plans de congé et d'absence**, sélectionnez **Plan de congé**. 

4. Le cas échéant, choisissez **Supprimer les ajustements de solde**.

5. Saisissez ou sélectionnez une **Date de provision de congés**. Cette date doit être soit aujourd'hui soit une date à venir. 

6. Cliquez sur **OK**. Le processus de régularisation supprimera les provisions et les paramètres que vous définissez. 

## <a name="review-leave-accrual-and-deletion-processes"></a>Examiner les processus de régularisation et de suppression des congés

**Audit des provisions de congés** s'affiche chaque fois que vous exécutez ou supprimez une provision pour un ou tous les employés. La date et la personne qui ont effectué l'action s'affichent également.

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Gérer les congés**, sélectionnez **Supprimer l'audit de provision de congés**.

## <a name="configure-preview-features"></a>Configuration des fonctionnalités d'aperçu

[!include [banner](includes/preview-feature-leave-absence.md)]

Si vous avez activé les fonctionnalités d'aperçu pour les congés et les absences, vous devez également configurer des paramètres pour elles.

### <a name="accrue-leave-per-company-or-per-leave-plan"></a>Régulariser les congés par société ou par plan de congé

Lorsque vous régularisez des plans de congés et d'absence, vous pouvez choisir de le faire pour toutes les sociétés. Si vous choisissez toutes les sociétés, vous ne pouvez pas sélectionner de plans de congé individuels. Si vous choisissez de ne pas opérer la régularisation pour toutes les sociétés, vous pouvez l'opérer pour un plan de congé spécifique. 

Ces options sont disponibles lors de la régularisation pour tous les employés ou pour les employés individuels. 

## <a name="see-also"></a>Voir également :

[Vue d'ensemble des congés et des absences](hr-leave-and-absence-overview.md)</br>
[Créer un plan de congé et d'absence](hr-leave-and-absence-plans.md)
