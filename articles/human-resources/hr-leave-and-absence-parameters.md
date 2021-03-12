---
title: Configuration des paramètres de congé et d’absence
description: Définissez les paramètres des ressources humaines pour les congés et les absences dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
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
ms.openlocfilehash: e1b2de94f9d9ac1ada16b6ef0e7628edbc9d683f
ms.sourcegitcommit: d02fae79d5c02a4bc4f4b16a410c2f5ce026c204
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "4997099"
---
# <a name="configure-leave-and-absence-parameters"></a>Configuration des paramètres de congé et d’absence

Avant de configurer des plans de congé et d’absence dans Dynamics 365 Human Resources, il est judicieux de vérifier la configuration de tous les paramètres des ressources humaines associés, notamment :

- Souche de numéros pour les demandes de congé
- Paramètres relatifs au Family Medical and Leave Act (FMLA)
- Paramètres en libre-service des employés pour les demandes de congé et d’absence
- Paramètres de congé et d’absence

## <a name="view-and-change-human-resources-parameters"></a>Afficher et modifier les paramètres des ressources humaines

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres des ressources humaines**.

3. Sur l’onglet **Souches de numéros**, vérifiez le **Code souche de N°** pour **ID de demande de congé** et changez si nécessaire. Ce paramètre détermine la souche utilisée pour attribuer automatiquement les ID aux demandes de congé.

4. Sur l’onglet **FMLA**, vérifiez les paramètres FMLA et modifiez-les si nécessaire.

5. Sur l’onglet **Libre-service employé**, indiquez si les gestionnaires peuvent saisir des demandes de congé et d’absence au nom de leurs employés.

7. Sélectionnez **Enregistrer**.

>[!IMPORTANT]
>L'affichage des congés et des absences dans les entreprises est actuellement en version préliminaire. Vous devrez l'activer dans votre environnement de **bac à sable** pour afficher l'option de congé et d'absence. Pour plus d’informations sur l'activation des fonctionnalités d'évaluation, voir [Gérer les fonctionnalités](hr-admin-manage-features.md).

## <a name="view-and-change-human-resources-shared-parameters"></a>Afficher et modifier les paramètres partagés des ressources humaines

1. Sur la page **Gestion du personnel**, sélectionnez l'onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres partagés des ressources humaines**.

3. Sur l'onglet **Accès anticipé**, sélectionnez **Oui** pour **Activer l'affichage des congés intersociétés** pour permettre la visualisation des congés dans toute l'entreprise.

4. Sélectionnez **Enregistrer**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Afficher et modifier les paramètres de congé et d’absence

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres de congé et d’absence**.

3. Dans l’onglet **Général**, définissez les paramètres suivants :
 
    - Définissez **Unités de congé et d’absence** sur des heures ou des jours. S’il s’agit de jours, vous pouvez sélectionner **Activer la définition d’une demi-journée** pour permettre aux employés de choisir la première ou la seconde partie de la journée dans leurs demandes de congés. 

    - Sélectionnez **Date d’entrée en vigueur des mois de service** pour déterminer quand les taux de régularisation entrent en vigueur pour les plans de congé avec les mois de service.

    - Sélectionnez **Calcul du solde** pour afficher les soldes à partir d’aujourd’hui ou de la période de régularisation. Si vous sélectionnez **Solde à ce jour**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à ce jour. Si vous sélectionnez **Solde à compter de la période de régularisation**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à partir de la période de régularisation définie par la fréquence dans le plan de congés. 

    - Définissez l’heure de début du report de la tâche par lots d’expiration.  
    
    - Sélectionnez **Oui** pour **Autoriser les employés à acheter des congés** et **Autoriser les employés à vendre des congés**. Si vous sélectionnez **Oui** pour ces options, vous pouvez créer des stratégies d’achat et de vente de congés et permettre aux employés de soumettre des demandes d’achat et de vente de congés.

## <a name="configure-calendar-parameters"></a>Configurer les paramètres de calendrier

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres de congé et d’absence**.

3. Sur l’onglet **Calendrier**, modifiez les paramètres de calendrier si nécessaire.

4. Sélectionnez **Enregistrer**.

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)
