---
title: Configurer le rôle de gestionnaire des absences
description: Cette rubrique explique comment configurer le rôle Gestionnaire des absences pour la gestion des congés des employés.
author: hasrivas
ms.date: 07/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace, LeaveAbsenceManager
audience: Application User
ms.search.scope: Human Resources
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8a8250b36d2774ac308637253b780592df316cd
ms.sourcegitcommit: 86d38cf57abe768e5bccde48b28280bc2224080c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2021
ms.locfileid: "6639604"
---
# <a name="configure-the-absence-manager-role"></a>Configurer le rôle de gestionnaire des absences

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

Dans certaines organisations, les responsables du personnel peuvent ne pas gérer les congés de leur équipe. Au lieu de cela, un gestionnaire des absences peut gérer ce processus pour les membres des équipes dans plusieurs services et équipes. Les gestionnaires des absences ont les possibilités suivantes dans le domaine de la gestion des congés :

- Examiner et approuver les congés en fonction d'une autre hiérarchie.
- Afficher les soldes des membres de l'équipe.
- Consulter le calendrier des absences.

## <a name="turn-on-the-feature"></a>Activer la fonctionnalité

1. Dans l'espace de travail **Administration système**, sélectionnez **Gestion des fonctionnalités**.

2. Sur l'onglet **Gestion des fonctionnalités**, activez la fonctionnalité **(Version préliminaire) Gestionnaire des absences pour gérer les congés**.

## <a name="define-a-custom-hierarchy"></a>Définir une hiérarchie personnalisée

La fonctionnalité de gestionnaire des absences utilise une hiérarchie personnalisée qui doit être configurée.

1. Dans l'espace de travail **Administration d’organisation**, sélectionnez **Types de hiérarchie des postes**.

2. Créez un type de hiérarchie de postes nommé **Congé**.

3. Dans l'espace de travail **Congés et absences**, sous **Liens**, sélectionnez **Paramètres des congés et absences**.

4. Sur l'onglet **Général**, dans la liste déroulante **Hiérarchie des absences**, sélectionnez le type de hiérarchie **Congé** que vous avez créé précédemment. Cette association de hiérarchie des congés doit être renseignée pour chaque entité juridique où la fonctionnalité de gestionnaire des absences sera utilisée.

Une fois le type de hiérarchie défini, la liaison hiérarchique du poste doit être affectée à celui-ci.

1. Dans l'espace de travail **Administration d’organisation**, sélectionnez **Tous les postes**.

2. Sélectionnez le poste auquel ajouter la hiérarchie Congés.

3. Dans l’onglet **Relations**, sélectionnez **Ajouter**.

4. Dans le champ **Nom de la hiérarchie**, sélectionnez **Congés**.

5. Dans le champ **Liaisons du poste**, sélectionnez un poste. Le nom du collaborateur est automatiquement renseigné une fois que vous avez sélectionné un poste.

## <a name="assign-the-absence-manager-role-to-a-user"></a>Attribuer le rôle de gestionnaire des absences à un utilisateur

Le rôle Gestionnaire des absences doit être attribué à des employés pour leur permettre d'approuver ou de refuser les demandes de congé.

1. Dans l'espace de travail **Administrateur système**, sélectionnez **Liens**.

2. Dans la section **Utilisateurs**, sélectionnez le lien **Utilisateurs**.

3. Dans la liste des utilisateurs, sélectionnez l'utilisateur auquel attribuer le rôle de gestionnaire des absences.

4. Dans l'onglet **Rôle de l’utilisateur**, sélectionnez **Affecter des rôles**.

5. Dans la liste, sélectionnez le rôle **Gestionnaire des absences**. Puis sélectionnez **OK**.

    > [!IMPORTANT]
    > Assurez-vous que le rôle Employé a également été attribué à l'utilisateur auquel vous attribuez le rôle Gestionnaire des absences. Sinon, le collaborateur ne pourra pas utiliser la fonctionnalité.

6. Après avoir créé la hiérarchie Congés, vous pouvez l'afficher en procédant comme suit :

    1. Dans l'espace de travail **Administration d’organisation**, sélectionnez **Hiérarchie des postes**.
    
    2. Dans le champ **Type de hiérarchie**, sélectionnez **Congés**.

## <a name="absence-manager-workspace"></a>Espace de travail du gestionnaire des absences

Dans l'espace de travail **Libre service employé**, l'onglet **Gestionnaire des absences** affiche les informations d'absence sur les employés qui sont affectés au gestionnaire des absences dans la hiérarchie Congés.

Sur l'onglet **Congés et absences**, les options suivantes sont disponibles pour chaque employé :

- **Congé** : affiche les soldes, les congés approuvés et les demandes de congés pour l'employé sélectionné.
- **Soldes de congés** : affiche la liste des soldes des différents plans de congés de l'employé sélectionné.

## <a name="approve-time-off-requests"></a>Approuver des demandes de congé

Les gestionnaires des absences peuvent approuver ou refuser les demandes de congés pour les employés. Ils peuvent également créer des demandes au nom des employés, selon les besoins.

> [!IMPORTANT]
> Avant que les gestionnaires des absences ne puissent approuver ou refuser des demandes de congé, le workflow de demande de congé doit être configuré de manière à leur attribuer des éléments de travail de demande de congé aux fins d'examen.
>
> 1. Sur la page **Flux de travail des ressources humaines**, sélectionnez ou créez le workflow de demande de congé.
> 2. Sélectionnez l'option **Associer une hiérarchie** puis, dans le champ **Nom de la hiérarchie**, sélectionnez **Congé**.
> 3. Mettez à jour le workflow dans le concepteur de workflow. Sous **Type d'affectation**, sélectionnez l'option **Hiérarchie** puis, sur l'onglet **Sélection de hiérarchie**, sélectionnez **Hiérarchie configurable**.
>
> Pour plus d’informations sur la création d'un workflow de demande de congé, voir [Créer un workflow de demande de congé](hr-leave-and-absence-workflow.md).

1. Dans l'espace de travail **Libre service employé**, sélectionnez l'onglet **Gestionnaire des absences**.

2. Sur l'onglet **Gestionnaire des absences**, sélectionnez l'employé souhaité.

3. Sélectionnez **Détails**, puis **Congé**.

4. Recherchez la demande de congé et sélectionnez l'option **Approbation**. Vous pouvez ensuite sélectionner une option pour approuver ou annuler la demande de congé.

Un statut **Annuler** indique que la demande a été refusée. Un statut **Terminé** indique que la demande a été approuvée.

## <a name="view-time-off-in-the-calendar"></a>Afficher les congés dans le calendrier

Les utilisateurs ayant le rôle de gestionnaire des absences peuvent afficher les demandes de congés dans leur calendrier. Procédez comme suit pour accéder au calendrier des congés.

> [!IMPORTANT]
> Un administrateur système doit configurer les options d'affichage du calendrier du gestionnaire des absences. Sur la page **Paramètres des congés et absences**, sur l'onglet **Calendrier**, il existe des options pour masquer ou afficher les dates de naissance, les absences sans détails, les congés et les demandes de congé en attente. Il existe également une option pour filtrer l'option d'affichage du calendrier par type de collaborateur.

1. Dans l'espace de travail **Libre service employé**, sélectionnez **Gestionnaire des absences** puis **Calendrier de gestion des absences**.

2. Dans le champ **Date**, saisissez les dates souhaitées.

3. Mettez à jour les options d'affichage si nécessaire.

Le calendrier du gestionnaire des absences affiche tous les enregistrements des employés qui relèvent du gestionnaire des absences dans la hiérarchie des congés.

## <a name="see-also"></a>Voir également :

- [Vue d'ensemble des congés et des absences](hr-leave-and-absence-overview.md)
- [Créer un flux de travail de demande de congé](hr-leave-and-absence-workflow.md)
- [Afficher les calendriers des équipes et de la société](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
