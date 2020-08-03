---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (11 juin 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 6/16/2020
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
ms.author: dkrame
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cba6e48899ec39fc4de6656f8151a42b8aa43261
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555193"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (11 juin 2020)

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s'appliquent au numéro de version 8.1.3316. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a>Le formulaire simplifié des employés provoque parfois l'arrêt des boutons de fermeture du formulaire enfant (X) (442369)

Lorsque le nouveau formulaire **Collaborateur** était activé, le bouton de fermeture (**X**) ne fonctionnait parfois pas sur les formulaires enfants. Ce problème était intermittent. Vous pouvez fermer le formulaire après l'avoir quitté et y revenir. Par exemple, vous pouvez sélectionner un élément de menu sur la gauche et revenir au formulaire **Collaborateur**, puis le fermer. La version de cette semaine résout ce problème. 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a>L'entité Personne de contact personnelle du collaborateur n'exporte pas les contacts personnels avec un type de relation parent

Avec cette version, l'entité **Personne de contact personnelle du collaborateur** exporte tous les types de relations.

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a>Par défaut, l'entité HcmPositionWorkerAssignmentV2Entity devrait faire partie du package d'intégration de paie Ceridian (448506)

Avec ce changement, l'entité **HcmPositionWorkerAssignmentV2Entity** est incluse dans le package d'intégration de la paie Ceridian.

## <a name="in-preview"></a>En mode aperçu

## <a name="database-logging"></a>Connexion à la base de données

La fonctionnalité de journalisation de la base de données vous permet de déterminer quelles tables et quels champs doivent être surveillés. Elle vous permet également de déterminer les événements qui doivent déclencher le suivi des modifications. Vous utilisez les capacités de journalisation de la base de données pour voir ces changements au fil du temps. Pour plus d'informations, voir [Configurer et gérer la journalisation de la base de données](hr-admin-database-logging.md).

## <a name="human-resources-application-in-teams"></a>Application Human Resources de Teams

Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams. Ils peuvent interagir avec un bot pour créer des demandes de congé. Pour plus d'informations, voir [Application Human Resources dans Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entités DMF (Data Management Framework) pour la gestion des avantages
 
Les entités de gestion des avantages publient. Les entités DMF permettent d'importer et d'exporter des données pour configurer facilement la gestion des avantages. Un modèle de gestion des avantages sera disponible pour déplacer les données. Le modèle exporte et importe les données de manière séquentielle pour respecter les dépendances des données.

## <a name="buy-and-sell-leave"></a>Achat et vente de congés 

Certaines organisations offrent un avantage qui permet aux employés d'acheter ou de vendre des congés. Ce processus est souvent géré manuellement. Cette fonctionnalité automatise la gestion des stratégies et des demandes pour le service RH. Il rationalise le processus de gestion des congés et aide à éliminer les erreurs. Pour plus d'informations, voir :

- [Gérer les stratégies d'achat et de vente de congés](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Achat et vente de congés](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Provisions de congés pour une seule entreprise ou un seul plan

Les clients peuvent traiter les charges à payer pour une seule entreprise ou un seul plan de congé et d'absence. Cette capacité permet de clarifier le processus d'accumulation pour les clients avec différentes années de congé ou politiques d'accumulation de congé. Pour plus d'informations, voir [Accumulation de congés par entreprise ou par plan de congés](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).

## <a name="add-attachments-to-time-off-requests"></a>Ajouter des pièces jointes aux demandes de congé

La possibilité d'ajouter des pièces jointes aux demandes de congé approuvées est essentielle dans l'environnement COVID-19 actuel. Les employés peuvent désormais ajouter ces pièces jointes. Ils ont également plus d'informations sur la façon dont les mises à jour sont effectuées pour les demandes de congés. Pour plus d'informations, voir [Ajouter une pièce jointe à une demande existante](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Ajouter un code de motif aux suspensions de cumul 

Des codes de motif ont été ajoutés à la suspension de la comptabilité d'exercice.

## <a name="carry-forward-rules"></a>Règles de report 

Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés. Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours. Pour plus d'informations, voir [Configurer les types de congé et d'absence](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Suspendre l'accumulation de congés pour certains types de congés

Vous pouvez créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés. Le congé sans solde peut être un type, mais ce n'est pas obligatoire. Vous pouvez suspendre tout congé basé sur un autre type de congé.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Entité DMF disponible pour les suspensions de régularisation 

Une entité DMF est désormais disponible pour les suspensions de régularisation.

## <a name="coming-soon"></a>Prochainement

## <a name="new-platform-capabilities"></a>Nouvelles capacités de plateforme 

Vous pourrez rendre les champs obligatoires en utilisant la personnalisation. Cette fonctionnalité vous obligera à activer les **Vues enregistrées**.

## <a name="configure-the-name-of-employee-self-service"></a>Configurer le nom du libre service employé

Une nouvelle option sera disponible dans les paramètres des Ressources humaines pour mettre à jour le nom de l'espace de travail Libre-service Employé en Libre-service. 

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)