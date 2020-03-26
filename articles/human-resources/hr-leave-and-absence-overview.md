---
title: Vue d'ensemble
description: Dans Dynamics 365 Human Resources, l'espace de travail **Congé et absence** fournit un cadre flexible pour la création de nouveaux plans de congé, de workflows pour la gestion des demandes et une page intuitive en libre-service permettant aux employés de demander des congés.
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
ms.openlocfilehash: 493bc3abe82103541125914896252b2eae596b38
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091746"
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

- [Demande de congés](hr-employee-self-service-request-time-off.md)
- [Gérer les demandes de congé et d'absence](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-preview-features"></a>Fonctionnalités d'aperçu des congés et absences

Vous pouvez essayer de nouvelles fonctionnalités d'aperçu des congés et des absences dans un environnement de **Bac à sable**. Pour plus d'informations sur l'activation des fonctionnalités d'aperçu, voir [Gestion des fonctionnalités](hr-admin-manage-features.md). Les fonctionnalités d'aperçu incluent :

- **Calendrier des congés et des absences** - Les paramètres de congé et d'absence passeront des **Paramètres des ressources humaines** vers un nouvel écran appelé **Paramètres de congé et d'absence**. Le nouvel écran comprend un nouvel onglet **Calendrier**. Cet aperçu n'active qu'un sous-ensemble des paramètres. Vous pouvez accéder au nouvel écran depuis l'onglet **Liens** de l'espace de travail **Congé et absence**. Les calendriers comprennent :
  - **Calendrier d'entreprise** - Affiche toutes les demandes de congé des employés. Les personnes avec le rôle **Human Resources** peuvent accéder à ce calendrier à partir de l'onglet **Liens** de l'espace de travail **Congé et absence**.
  - **Calendrier de l'équipe de gestion** - Affiche les demandes de congés de tous les subordonnés directs. Les gestionnaires peuvent accéder au calendrier à partir de l'onglet **Mon équipe** dans le Libre-service employé sous **Congé et absence**. 

- **Calendriers des jours fériés - Congé et absence** - Les types de congé incluent une nouvelle option **Jour férié**, utilisée en conjonction avec le calendrier du temps de travail. Les jours définis comme des jours fériés et de fermeture sont désormais désignés comme **Jour férie** lorsque les jours ouvrables sont générés. Lorsque les provisions sont traitées, des ajustements sont apportés aux employés affectés au calendrier pour tenir compte des jours fériés tombant un jour ouvrable.

- **Vérification des provisions de congé** - Un nouvel écran vous permet de vérifier quand les provisions ont été traitées et supprimées, à la fois pour tous les employés et pour un employé spécifique. Vous pouvez accéder à ce nouvel écran depuis l'onglet **Liens** de l'espace de travail **Congé et absence**.

- **Suppression de la provision de congé** - Vous pouvez désormais supprimer les enregistrements de provision pour des plans de congé spécifiques. Vous pouvez accéder à cette option depuis l'onglet **Liens** de l'espace de travail **Congé et absence**. Pour les employés individuels, cette option apparaît dans le regroupement **Congé et absence** dans le profil de l'employé. 

- **Arrondi de provision de congé** - De nouvelles options pour le **Type de congé** définissent le type d'arrondi à utiliser pour une provision, ainsi que la précision décimale de l'arrondi appliqué à la provision. Lorsque les provisions sont traitées, l'arrondi et la précision décimale sont appliqués aux enregistrements de provision. 

- **Configurer plusieurs types de congés sur un seul plan de congés** - Une nouvelle colonne dans le calendrier de provision des congés pour les types de congés vous permet de définir plusieurs types de congés sur un plan de congés et d'absences avec différents calendriers de provision. L'ancien champ **Type de congé** est supprimé. Lors de l'inscription des employés, les soldes des types de congés s'affichent désormais dans un tableau plutôt qu'en haut de l'écran.

  > [!IMPORTANT]
  > Vous ne pouvez pas désactiver cette fonctionnalité après l'avoir activée.

- **Utiliser l'équivalence à temps plein (ETP) d'un employé pour la provision** - Une nouvelle colonne sur le calendrier de provision des congés permet d'utiliser l'ETP pour la provision. Lorsque les provisions sont traitées, la demande utilise le poste principal de l'employé et l'ETP défini pour déterminer le montant des provisions au prorata.

  > [!NOTE]
  > Cette fonctionnalité n'est disponible que si vous activez **Configurer plusieurs types de congés par plan de congé**. 
