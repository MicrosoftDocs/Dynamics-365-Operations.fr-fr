---
title: Configurer le rôle de gestionnaire des absences
description: Cet article explique comment configurer le rôle Gestionnaire des absences pour la gestion des congés des employés.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace, LeaveAbsenceManager
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 40f9607fb6fc16b96373141d8d2610538e3fdec7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886100"
---
# <a name="configure-the-absence-manager-role"></a>Configurer le rôle de gestionnaire des absences

>[!Important]
>La fonctionnalité indiquée dans cet article est actuellement disponible pour les clients sur Dynamics 365 Human Resources autonome. Certaines ou toutes les fonctionnalités seront disponibles dans le cadre d’une future version de l’infrastructure Finance après la version 10.0.26 de Finance.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dans certaines organisations, les responsables du personnel peuvent ne pas gérer les congés de leur équipe. Au lieu de cela, un gestionnaire des absences peut gérer ce processus pour les membres des équipes dans plusieurs services et équipes. Les gestionnaires des absences ont les possibilités suivantes dans le domaine de la gestion des congés :

- Examiner et approuver les congés en fonction d’une autre hiérarchie.
- Afficher les soldes des membres de l’équipe.
- Consulter le calendrier des absences.

## <a name="turn-on-the-feature"></a>Activer la fonctionnalité

1. Dans l’espace de travail **Administration système**, sélectionnez **Gestion des fonctionnalités**.

2. Sur l’onglet **Gestion des fonctionnalités**, activez la fonctionnalité **Gestionnaire des absences pour gérer les congés**.

## <a name="define-a-custom-hierarchy"></a>Définir une hiérarchie personnalisée

La fonctionnalité de gestionnaire des absences utilise une hiérarchie personnalisée qui doit être configurée.

1. Dans l’espace de travail **Administration d’organisation**, sélectionnez **Types de hiérarchie des postes**.

2. Créez un type de hiérarchie de postes nommé **Congé**.

3. Dans l’espace de travail **Congés et absences**, sous **Liens**, sélectionnez **Paramètres des congés et absences**.

4. Sur l’onglet **Général**, dans la liste déroulante **Hiérarchie des absences**, sélectionnez le type de hiérarchie **Congé** que vous avez créé précédemment. Cette association de hiérarchie des congés doit être renseignée pour chaque entité juridique où la fonctionnalité de gestionnaire des absences sera utilisée.

Une fois le type de hiérarchie défini, la liaison hiérarchique du poste doit être affectée à celui-ci.

1. Dans l’espace de travail **Administration d’organisation**, sélectionnez **Tous les postes**.

2. Sélectionnez le poste auquel ajouter la hiérarchie Congés.

3. Dans l’onglet **Relations**, sélectionnez **Ajouter**.

4. Dans le champ **Nom de la hiérarchie**, sélectionnez **Congés**.

5. Dans le champ **Liaisons du poste**, sélectionnez un poste. Le nom du collaborateur est automatiquement renseigné une fois que vous avez sélectionné un poste.

## <a name="assign-the-absence-manager-role-to-a-user"></a>Attribuer le rôle de gestionnaire des absences à un utilisateur

Le rôle Gestionnaire des absences doit être attribué à des employés pour leur permettre d’approuver ou de refuser les demandes de congé.

1. Dans l’espace de travail **Administrateur système**, sélectionnez **Liens**.

2. Dans la section **Utilisateurs**, sélectionnez le lien **Utilisateurs**.

3. Dans la liste des utilisateurs, sélectionnez l’utilisateur auquel attribuer le rôle de gestionnaire des absences.

4. Dans l’onglet **Rôle de l’utilisateur**, sélectionnez **Affecter des rôles**.

5. Dans la liste, sélectionnez le rôle **Gestionnaire des absences**. Puis sélectionnez **OK**.

    > [!IMPORTANT]
    > Assurez-vous que le rôle Employé a également été attribué à l’utilisateur auquel vous attribuez le rôle Gestionnaire des absences. Sinon, le collaborateur ne pourra pas utiliser la fonctionnalité.

6. Après avoir créé la hiérarchie Congés, vous pouvez l’afficher en procédant comme suit :

    1. Dans l’espace de travail **Administration d’organisation**, sélectionnez **Hiérarchie des postes**.
    
    2. Dans le champ **Type de hiérarchie**, sélectionnez **Congés**.

## <a name="absence-manager-workspace"></a>Espace de travail du gestionnaire des absences

Dans l’espace de travail **Libre service employé**, l’onglet **Gestionnaire des congés** affiche les informations d’absence sur les employés qui sont affectés au gestionnaire des absences dans la hiérarchie Congés. Plusieurs options sont disponibles pour le gestionnaire des absences : 
 - Examiner les demandes de congés.</br>
 - Soumettre une demande de congé au nom d’un employé.</br>
 - Afficher tous les employés qui leur sont affectés dans le cadre de la hiérarchie Congés.</br>
 - Afficher le calendrier du gestionnaire des absences.</br>

L’espace de travail **Gestion des congés** comporte deux onglets :
 - **Demandes de congés** : cet onglet répertorie toutes les demandes de congés en attente que le gestionnaire des absences peut approuver. Le gestionnaire des absences peut sélectionner plusieurs enregistrements et agir sur eux en même temps. Si la vue des congés interentreprises est activée, cette liste affiche les demandes de congés en attente dans toutes les entités juridiques auxquelles elles ont accès. Sinon, elle affiche les demandes de congés en attente pour l’entité juridique actuellement sélectionnée. </br>
 - **Tous les employés** : cet onglet répertorie tous les employés qui sont affectés au gestionnaire des absences dans la hiérarchie Congés. Plusieurs options sont disponibles pour chaque employé :
    - **Demander un congé** : soumet une nouvelle demande de congé pour l’employé sélectionné.</br>
    - **Congé** : affiche les soldes, les congés approuvés et les demandes de congés pour l’employé sélectionné.</br>

## <a name="approve-time-off-requests"></a>Approuver des demandes de congé

Les gestionnaires des absences peuvent approuver ou refuser les demandes de congés pour les employés. 

> [!IMPORTANT]
> Avant que les gestionnaires des absences ne puissent approuver ou refuser des demandes de congé, le workflow de demande de congé doit être configuré de manière à leur attribuer des éléments de travail de demande de congé aux fins d’examen.
>
> 1. Sur la page **Flux de travail des ressources humaines**, sélectionnez ou créez le workflow de demande de congé.
> 2. Sélectionnez l’option **Associer une hiérarchie** puis, dans le champ **Nom de la hiérarchie**, sélectionnez **Congé**.
> 3. Mettez à jour le workflow dans le concepteur de workflow. Sous **Type d’affectation**, sélectionnez l’option **Hiérarchie** puis, sur l’onglet **Sélection de hiérarchie**, sélectionnez **Hiérarchie configurable**.
>
> Pour plus d’informations sur la création d’un workflow de demande de congé, voir [Créer un workflow de demande de congé](hr-leave-and-absence-workflow.md).

1. Dans l’espace de travail **Libre service employé**, sélectionnez l’onglet **Gestion des congés**.

2. Dans l’onglet **Demandes de congés**, sélectionnez les demandes de congés sur lesquelles vous souhaitez agir. Vous pouvez sélectionner plusieurs enregistrements dans cette vue de liste.

3. Utilisez les boutons d’action en haut de la grille pour approuver, refuser ou déléguer la demande de congé. 

L’utilisateur peut également utiliser la vignette **Demandes de congés** sur la gauche pour accéder à la liste de tous les éléments de travail de demandes de congés. 

## <a name="view-time-off-in-the-calendar"></a>Afficher les congés dans le calendrier

Les utilisateurs ayant le rôle de gestionnaire des absences peuvent afficher les demandes de congés dans leur calendrier. Procédez comme suit pour accéder au calendrier des congés.

> [!IMPORTANT]
> Un administrateur système doit configurer les options d’affichage du calendrier du gestionnaire des absences. Sur la page **Paramètres des congés et absences**, sur l’onglet **Calendrier**, il existe des options pour masquer ou afficher les dates de naissance, les absences sans détails, les congés et les demandes de congé en attente. Il existe également une option pour filtrer l’option d’affichage du calendrier par type de collaborateur.

1. Dans l’espace de travail **Libre service des employés**, sélectionnez **Gestion des congés**, puis **Calendrier du gestionnaire des absences**.

2. Dans le champ **Date**, saisissez les dates souhaitées.

3. Mettez à jour les options d’affichage si nécessaire.

Le calendrier du gestionnaire des absences affiche tous les enregistrements des employés qui relèvent du gestionnaire des absences dans la hiérarchie des congés.

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)
- [Créer un flux de travail de demande de congé](hr-leave-and-absence-workflow.md)
- [Afficher les calendriers des équipes et de la société](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
