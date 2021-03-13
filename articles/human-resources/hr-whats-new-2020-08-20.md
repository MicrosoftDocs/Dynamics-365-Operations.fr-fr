---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (20 août 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 20 août 2020.
author: andreabichsel
manager: tfehr
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b3654617b0e8bc4b586e969913d5dc355b60b882
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130057"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (20 août 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3478. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support Lifecycle Services (LCS) pour référence.

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a>Afficher les informations d’absence à venir et en attente sur les cartes dans l’espace de travail Personnes

Les options de demande de congé en attente et à venir sont désormais disponibles sur les cartes Congés et absences de l’espace de travail **Personnes**.

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a>Le champ Privé n’est pas défini sur Oui par défaut pour le rôle Employé dans le libre service Employé (477106)

Le champ **Privé** est désormais définir par défaut sur **Oui** lorsque les employés ajoutent de nouveaux enregistrements d’adresse par le biais de la page **Renseignements personnels** en libre service des employés. 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a>Le raccourci Candidats à l’embauche dans Gestion du personnel affichent un nombre de candidats incorrect (470110)

La page **Gestion du personnel** affiche désormais avec précision le nombre de candidats à embaucher. 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a>Impossible de saisir un arrêt maladie pour un employé licencié lorsque la régularisation est définie sur zéro (446195)

Les transactions de congé sont désormais autorisées pour les employés qui ont été licenciés dans le futur et la régularisation est définie sur zéro. Les transactions de congé peuvent être saisies jusqu’à la date de départ de l’employé. 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a>L’ajout de champs personnalisés au nouveau formulaire Collaborateur désactive les champs du volet Actions pour Gérer les congés (473314)

Les options du volet Actions sur le nouveau formulaire **Collaborateur** dans **Gérer les congés** ne sera plus désactivé si des champs personnalisés ont été ajoutés au nouveau formulaire **Collaborateur**.

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a>Rendre obligatoire le champ Commentaire sur le congé permet de soumettre une demande de congé lorsqu’aucun commentaire n’est saisi (473543)

Les champs de commentaires peuvent désormais être obligatoires et les demandes de congé respectent ce paramètre. Les champs obligatoires sont une fonctionnalité d’évaluation.

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Entité DMF disponible pour les suspensions de régularisation

Une entité DMF est désormais disponible pour les suspensions de régularisation.

## <a name="in-preview"></a>En mode aperçu

### <a name="mandatory-fields"></a>Champs obligatoires

Vous pouvez rendre les champs obligatoires en utilisant les fonctionnalités de personnalisation de Human Resources. Cette fonctionnalité nécessite des **Vues enregistrées**. Pour plus d’informations sur les vues enregistrées, voir :

- [Vues enregistrées – disponibilité générale](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) dans la 2e partie du lancement 2020 de Dynamics 365
- [Écrans de version utilisant entièrement des vues enregistrées](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/user-interface/understanding-saved-views)

### <a name="human-resources-application-in-teams"></a>Application Human Resources de Teams

Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams. Ils peuvent interagir avec un bot pour créer des demandes de congé. Pour plus d’informations, voir :

- [Expérience des employés en congé et absence Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) dans la 1ère partie du lancement 2020 de Dynamics 365
- [Application Human Resources de Teams](https://go.microsoft.com/fwlink/?linkid=2127841)

## <a name="coming-soon"></a>Prochainement

### <a name="human-resources-app-in-teams-preview-features"></a>Application Human Resources dans les fonctionnalités d’évaluation Teams
 
-  **Notifications** : Les demandeurs et les approbateurs des demandes de congés seront informés dans l’application Human Resources de Teams. Les approbateurs pourront approuver ou refuser les demandes de congés, et les demandeurs seront informés si la demande a été approuvée ou refusée.
 
- **Calendrier des congés du responsable** : Les responsables pourront afficher les congés approuvés et en attente pour leurs subordonnés directs dans une vue du calendrier. Cette vue permet de comprendre facilement quand les membres de leur équipe sont absents du travail.

### <a name="checklist-entities-included-in-dataverse"></a>Entités de liste de contrôle incluses dans Dataverse

Les entités de liste de contrôle pour les processus d’intégration, de départ, de transfert et d’entreprise seront bientôt disponibles dans Dataverse.

## <a name="known-issues"></a>Problèmes connus

L’espace de travail **Gestion des fonctionnalités** peut afficher des fonctionnalités désactivées en tant que fonctionnalités d’aperçu lorsqu’elles sont généralement disponibles. Vous trouverez ci-dessous une liste des fonctionnalités généralement disponibles qui indiquent un état incorrect. 

- Gestion des avantages
- Gestion des dossiers
- Journalisation de base de données (audit)
- Régularisation des congés pour une seule société ou un seul plan
- Suspension de la régularisation des congés et des absences
- Code motif d’ajustement du solde et commentaire
- Achat et vente de congés
- Calendrier des congés et des absences
- Règles de report de congés
- Audit de régularisation des congés
- Suppression de régularisations de congé
- Arrondi de la régularisation des congés
- Configurer plusieurs types de congés sur un seul plan de congé
- Mettre à jour les améliorations de période de congés
- Utiliser l’ETP d’un employé pour les régularisations
- Vue Rémunération intersociétés
- Imprimer les évaluations des performances
- Corrections des jours fériés pour la régularisation des congés

### <a name="benefit-plan-employee-entity"></a>Entité régime de prestations sociales employés 

Nous avons récemment découvert deux problèmes concernant l’entité **BenefitsPlanEmployee**. Lors de l’importation des inscriptions de collaborateurs, le **Code de couverture** et le **Code de type de régime** sont mal définis. Ce problème entraîne l’affichage incorrect des régimes d’avantages sociaux des employés dans le formulaire **Régime d’avantages sociaux des collaborateurs** et dans le formulaire **Ouvrir l’inscription** dans le libre service des employés. Ce problème peut également avoir un impact sur la capacité de l’employé à sélectionner des régimes dans le libre service des employés. Actuellement, il n’y a pas de solution. Nous traitons cela comme un correctif hautement prioritaire et déploierons celui-ci avec notre prochaine version.

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)
