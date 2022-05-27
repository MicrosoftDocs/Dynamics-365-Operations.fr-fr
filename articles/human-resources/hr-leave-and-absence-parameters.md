---
title: Configuration des paramètres de congé et d’absence
description: Cette rubrique décrit comment définir les paramètres des ressources humaines pour les congés et les absences dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 79052c550783dee1ba4091ad10bde4d79d7b905e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690692"
---
# <a name="configure-leave-and-absence-parameters"></a>Configuration des paramètres de congé et d’absence

>[!Important]
>La fonctionnalité indiquée dans cette rubrique est actuellement disponible pour les clients sur Dynamics 365 Human Resources autonome. Certaines ou toutes les fonctionnalités seront disponibles dans le cadre d’une future version de l’infrastructure Finance après la version 10.0.26 de Finance.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Avant de configurer des plans de congé et d’absence dans Dynamics 365 Human Resources, il est judicieux de vérifier la configuration de tous les **paramètres des ressources humaines** associés, notamment :

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
>L’affichage des congés et des absences dans les entreprises est actuellement en version préliminaire. Vous devrez l’activer dans votre environnement de **bac à sable** pour afficher l’option de congé et d’absence. Pour plus d’informations sur l’activation des fonctionnalités d’évaluation, voir [Gérer les fonctionnalités](hr-admin-manage-features.md).

## <a name="view-and-change-human-resources-shared-parameters"></a>Afficher et modifier les paramètres partagés des ressources humaines

1. Sur la page **Gestion du personnel**, sélectionnez l’onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres partagés des ressources humaines**.

3. Sur l’onglet **Accès anticipé**, sélectionnez **Oui** pour **Activer l’affichage des congés intersociétés** pour permettre la visualisation des congés dans toute l’entreprise.

4. Sélectionnez **Enregistrer**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Afficher et modifier les paramètres de congé et d’absence

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres de congé et d’absence**.

3. Dans l’onglet **Général**, définissez les paramètres suivants :
 
    - Définissez **Unités de congé et d’absence** sur des heures ou des jours. S’il s’agit de jours, vous pouvez sélectionner **Activer la définition d’une demi-journée** pour permettre aux employés de choisir la première ou la seconde partie de la journée dans leurs demandes de congés. 

    - Sélectionnez **Date d’entrée en vigueur des mois de service** pour déterminer quand les taux de régularisation entrent en vigueur pour les plans de congé avec les mois de service.

    - Sélectionnez **Calcul du solde** pour afficher les soldes à partir d’aujourd’hui ou de la période de régularisation. Si vous sélectionnez **Solde à ce jour**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à ce jour. Si vous sélectionnez **Solde à compter de la période de régularisation**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à partir de la période de régularisation définie par la fréquence dans le plan de congés. 

    - Définissez **l’heure de début** du traitement par lots du **report de l’expiration**.  
    
    - Sélectionnez **Oui** pour **Autoriser les employés à acheter des congés** et **Autoriser les employés à vendre des congés**. Si vous sélectionnez **Oui** pour ces options, vous pouvez créer des stratégies d’achat et de vente de congés et permettre aux employés de soumettre des demandes d’achat et de vente de congés.

## <a name="configure-calendar-parameters"></a>Configurer les paramètres de calendrier

1. Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.

2. Sous **Configuration**, sélectionnez **Paramètres de congé et d’absence**.

3. Sur l’onglet **Calendrier**, modifiez les paramètres de calendrier si nécessaire.

4. Sélectionnez **Enregistrer**.

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
