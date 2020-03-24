---
title: Régulariser les plans de congé et d'absence
description: Vous pouvez provisionner les congés et les absences dans Dynamics 365 Human Resources pour plusieurs employés ou pour un employé individuel.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba60fc2e5b17ec32aa6ad7eb104e8ae55ddee3bb
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092336"
---
# <a name="accrue-leave-and-absence-plans"></a>Régulariser les plans de congé et d'absence

Vous pouvez provisionner les congés et les absences dans Dynamics 365 Human Resources pour plusieurs employés ou pour un employé individuel.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Provisionner les congés et les absences pour plusieurs employés

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Gérer les congés**, sélectionnez **Provisionner les plans de congé et d'absence**.

3. Dans la boîte de dialogue **Provisionner les plans de congé et d'absence**, dans **Provisionner pour le**, sélectionnez la **Date du jour** ou sélectionnez une **Date personnalisée** et entrez une date personnalisée.

4. Si vous souhaitez exécuter le processus de provision en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus de provision.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus de provisionnement s'exécutera avec les paramètres que vous définissez.

## <a name="accrue-leave-and-absence-for-an-employee"></a>Provisionner les congés et les absences pour un employé

1. Dans le dossier de l'employé, sélectionnez **Congé**.

2. Sélectionnez **Provisionner les congés et les absences**.

3. Dans la boîte de dialogue **Provisionner les plans de congé et d'absence**, dans **Provisionner pour le**, sélectionnez la **Date du jour** ou sélectionnez une **Date personnalisée** et entrez une date personnalisée.

4. Si vous souhaitez exécuter le processus de provision en arrière-plan, sélectionnez **Exécuter à l'arrière-plan** et effectuez les tâches suivantes :

   1. Entrez les informations pour le processus de provision.

   2. Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.

   3. Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.

   4. Cliquez sur **OK**. Le processus de provisionnement s'exécutera avec les paramètres que vous définissez.

## <a name="preview-features-for-leave-and-absence"></a>Fonctionnalités d'aperçu pour les congés et les absences

[!include [banner](includes/preview-feature-leave-absence.md)]

Vous pouvez activer les fonctionnalités d'aperçu suivantes pour les congés et les absences :

- **Supprimer les provisions des congés et des absences**. Supprimez les enregistrements de provisions pour un plan et une plage de dates spécifiques. Les dates de provision doivent correspondre à la date du jour ou au lendemain.

- **Audit des provisions de congés**. Affiche chaque fois que quelqu'un exécute ou supprime une provision pour un ou tous les employés, avec la date et qui a effectué l'action.

## <a name="see-also"></a>Voir également :

- [Vue d'ensemble des congés et des absences](hr-leave-and-absence-overview.md)
- [Création d'un plan de congé et d'absence](hr-leave-and-absence-plans.md)