---
title: Vue d'ensemble
description: Dans Dynamics 365 Human Resources, l'espace de travail Congés et absences fournit un cadre flexible pour la création de nouveaux plans de congé, de workflows pour la gestion des demandes et une page intuitive en libre-service permettant aux employés de demander des congés.
author: andreabichsel
manager: AnnBe
ms.date: 04/03/2020
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
ms.openlocfilehash: 5f7ba32b31a67d81ee5be568b0e64842f343f96b
ms.sourcegitcommit: 9940ca772807d3c4e1ff3bf47f45b7251c4469ac
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/04/2020
ms.locfileid: "3226228"
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

Vous pouvez essayer de nouvelles fonctionnalités d'aperçu des congés et des absences dans un environnement de **Bac à sable**. Pour en savoir plus sur l'activation des fonctionnalités d'aperçu, voir [Gestion des fonctionnalités](hr-admin-manage-features.md). Les fonctionnalités d'aperçu incluent :

- **Suspension des congés** - Vous pouvez suspendre les congés et les absences d'un employé dans Human Resources. La suspension des congés arrête les régularisations de congés pour les types de congé sélectionnés. Si la suspension survient après le traitement d'une régularisation, la suspension du congé crée un ajustement au prorata du solde des congés de l'employé. 

- **Règles de report** - Vous pouvez spécifier un type de congé de report pour les soldes de report dans lesquels les ajustements de report sont transférés. Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours. 