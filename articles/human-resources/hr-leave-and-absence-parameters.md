---
title: Configuration des paramètres de congé et d'absence
description: Définissez les paramètres des ressources humaines pour les congés et les absences dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
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
ms.openlocfilehash: eb992cbfbed33f88e125d3a8b721f8815414599a
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3197979"
---
# <a name="configure-leave-and-absence-parameters"></a>Configuration des paramètres de congé et d'absence

Avant de configurer des plans de congé et d'absence dans Dynamics 365 Human Resources, il est judicieux de vérifier la configuration de tous les paramètres des ressources humaines associés, notamment :

- Souche de numéros pour les demandes de congé
- Paramètres relatifs au Family Medical and Leave Act (FMLA)
- Paramètres en libre-service des employés pour les demandes de congé et d'absence
- Paramètres de congé et d'absence

## <a name="view-and-change-human-resources-parameters"></a>Afficher et modifier les paramètres des ressources humaines

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres des ressources humaines**.

3. Sur l'onglet **Souches de numéros**, vérifiez le **Code souche de N°** pour **ID de demande de congé** et changez si nécessaire. Ce paramètre détermine la souche utilisée pour attribuer automatiquement les ID aux demandes de congé.

4. Sur l'onglet **FMLA**, vérifiez les paramètres FMLA et modifiez-les si nécessaire.

5. Sur l'onglet **Libre-service employé**, indiquez si les gestionnaires peuvent saisir des demandes de congé et d'absence au nom de leurs employés.

6. Sur l'onglet **Types de congé et d'absence**, vérifiez les paramètres FMLA et modifiez-les si nécessaire.

7. Sélectionnez **Enregistrer**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Afficher et modifier les paramètres de congé et d'absence

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres de congé et d'absence**.

3. Dans l'onglet **Général**, définissez les paramètres suivants :
 
    - Définissez **Unités de congé et d'absence** sur des heures ou des jours. S'il s'agit de jours, vous pouvez sélectionner **Activer la définition d'une demi-journée** pour permettre aux employés de choisir la première ou la seconde partie de la journée dans leurs demandes de congés. 

    - Sélectionnez **Date d'entrée en vigueur des mois de service** pour déterminer quand les taux de régularisation entrent en vigueur pour les plans de congé avec les mois de service.

    - Sélectionnez **Calcul du solde** pour afficher les soldes à partir d'aujourd'hui ou de la période de régularisation. Si vous sélectionnez **Solde à ce jour**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à ce jour. Si vous sélectionnez **Solde à compter de la période de régularisation**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à partir de la période de régularisation définie par la fréquence dans le plan de congés. 

## <a name="configure-calendar-parameters"></a>Configurer les paramètres de calendrier

1. Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres de congé et d'absence**.

3. Sur l'onglet **Calendrier**, modifiez les paramètres de calendrier si nécessaire.

4. Sélectionnez **Enregistrer**.

## <a name="see-also"></a>Voir également :

- [Vue d'ensemble des congés et des absences](hr-leave-and-absence-overview.md)
