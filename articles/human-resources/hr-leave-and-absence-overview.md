---
title: Vue d'ensemble
description: Dans Dynamics 365 Human Resources, l'espace de travail Congés et absences fournit un cadre flexible pour la création de nouveaux plans de congé, de workflows pour la gestion des demandes et une page intuitive en libre-service permettant aux employés de demander des congés.
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
ms.openlocfilehash: ec72d2d741f7f8428a7daa97bb982e9fc00b8c3f
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428965"
---
# <a name="overview"></a>Vue d'ensemble

Dynamics 365 Human Resources vous aide à offrir des avantages sociaux importants à vos employés. L'espace de travail **Congé et absence** fournit un cadre flexible pour la création de nouveaux plans de congé, de workflows pour la gestion des demandes et une page intuitive en libre-service permettant aux employés de demander des congés. Les analyses aident votre organisation à mesurer et à surveiller les soldes de congés et l'utilisation de vos plans de congés.

## <a name="set-up-leave-and-absence"></a>Configuration des congés et absences

Avant de pouvoir créer des plans de congés pour vos employés, vous devez effectuer quelques étapes de configuration :

- [Configuration des paramètres de congé et d'absence](hr-leave-and-absence-parameters.md)
- [Création d'un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md)
- [Créer un workflow de demande d'absence](hr-leave-and-absence-workflow.md)

## <a name="create-and-manage-leave-plans"></a>Création et gestion des plans de congés

Avant de créer des plans de congé pour vos employés, vous devez créer des types de congé et d'absence. Une fois que vous avez créé un plan de congé, vous pouvez ensuite inscrire les employés au plan. Vous pouvez également exécuter le processus de régularisation, créer des alertes et afficher des analyses pour vos plans.

- [Configuration des types de congé et d'absence](hr-leave-and-absence-types.md)
- [Création d'un plan de congé et d'absence](hr-leave-and-absence-plans.md)
- [Affecter des collaborateurs à un plan de congé](hr-leave-and-absence-enroll.md)
- [Provisionner les plans de congé et d'absence](hr-leave-and-absence-accrue.md)
- [Affichage des analyses des congés et des absences](hr-leave-and-absence-analytics.md)

## <a name="request-time-off-and-manage-requests"></a>Demande de congés et gestion des demandes

Vos employés peuvent soumettre des demandes de congés et vous pouvez les gérer dans l'espace de travail **Libre-service employé**.

- [Demander un congé](hr-employee-self-service-request-time-off.md)
- [Gérer les demandes de congé et d'absence](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-known-issues"></a>Problèmes connus liés aux congés et aux absences

### <a name="rounding-precision"></a>Précision de l'arrondi

Vous ne pouvez pas définir de **Précision d'arrondi** lorsque vous définissez un **Type d'arrondi**. Vous pouvez définir une **Précision d'arrondi** uniquement via l'entité **Types de congé et d'absence**. 

1. Depuis **Types de congé et d'absence**, sélectionnez **Ouvrir dans Excel** pour ouvrir l'entité **Types de congé et d'absence**.

2. Une fois le fichier ouvert et activé, sélectionnez **Conception**.

3. Sur la table **Types de congé et d'absence**, sélectionnez l'option Crayon pour modifier.

4. Sélectionnez **RoundingPrecision** et **RoundingType**, puis sélectionnez **Ajouter** pour l'ajouter à la liste des champs.

5. Sélectionnez **Mettre à jour**, puis **Terminé**.

6. Entrez ou sélectionnez le **Type d'arrondi** pour chaque type de congé s'ils n'ont pas déjà été définis. 

7. Entrez la **Précision d'arrondi** pour les types appropriés.

8. Sélectionnez **Publier** pour intégrer les modifications dans Human Resources.

## <a name="leave-and-absence-preview-features"></a>Fonctionnalités d'aperçu des congés et absences

Vous pouvez essayer de nouvelles fonctionnalités d'aperçu des congés et des absences dans un environnement de **Bac à sable**. Pour en savoir plus sur l'activation des fonctionnalités d'aperçu, voir [Gestion des fonctionnalités](hr-admin-manage-features.md). 

[!include [banner](includes/preview-feature.md)]

Les fonctionnalités d'aperçu incluent :

- **Régulariser les congés par société ou par plan** - Vous pouvez exécuter le processus de régularisation pour toutes les sociétés ou pour une seule société. Vous pouvez également exécuter le processus de régularisation pour un seul plan de congé et d'absence pour une entreprise spécifique. 

- **Acheter un congé** - Vous pouvez activer et créer des stratégies d'achat de congés pour permettre aux employés de soumettre des demandes d'achat. Les employés peuvent soumettre des demandes d'achat et voir leur solde mis à jour automatiquement pour refléter les demandes.  

- **Ajouter des pièces jointes aux demandes de congé approuvées** - Vous pouvez ajouter une pièce jointe à une demande de congé déjà approuvée. 

