---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (08 juillet 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 8 juillet 2020.
author: andreabichsel
ms.date: 07/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7fae6089d16aa582ff18052effe8e3a69663bee67c0cceec930314eb91af9536
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761942"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (8 juillet 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3382. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="database-logging"></a>Connexion à la base de données

La journalisation de la base de données vous permet de déterminer quelles tables et quels champs doivent être surveillés. Elle vous permet également de déterminer les événements qui doivent déclencher le suivi des modifications. Vous utilisez les capacités de journalisation de la base de données pour voir ces changements au fil du temps. Pour plus d’informations, voir [Configurer et gérer la journalisation de la base de données](hr-admin-database-logging.md).

## <a name="configure-the-name-of-employee-self-service"></a>Configurer le nom du libre service employé

Dans les **Paramètres Human Resources**, vous pouvez maintenant changer le nom de l’espace de travail **Libre service des employés** en **Libre service**. Pour plus d’informations, voir [Modifier le nom de l’espace de travail en libre service des employés](hr-employee-self-service-workspace-name.md).

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a>Accès à l’inscription à la gestion des avantages ouvert en dehors de la période

Cette version corrige un bogue où les employés pouvaient accéder à l’inscription ouverte aux avantages en dehors de la période d’inscription ou sans événement dans leur vie. Par conséquent, si vous devez faire une démonstration de l’inscription ouverte dans le libre service des employés, vous devez ajuster les dates de l’inscription ouverte à la date du jour (ou à une date antérieure) pour la rendre accessible. Vous pouvez modifier ce paramètre sous **Gestion des avantages > Règles et périodes des options**.

## <a name="email-employee-enrollment-confirmation"></a>Email de confirmation de l’inscription des employés

Vous pouvez désormais envoyer des courriels aux employés une fois qu’ils ont terminé leur sélection d’avantages. Vous pouvez envoyer un message par défaut ou utiliser un modèle d’e-mail de l’organisation. Ces paramètres se trouvent sous **Paramètres Human Resources > Gestion des avantages**.

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a>Le congé annulé apparaît toujours dans le temps de congé à venir sur l’espace de travail Contacts (441358)

Le congé annulé ne s’affiche plus comme un congé à venir sur les cartes de congé dans l’espace de travail **Personnes**.

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a>Impossible d’utiliser la propriété d’entité Service dans l’entité PositionV2 (456486)

Vous pouvez désormais ajouter un service sans créer de relation en double.

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a>PayrollWorkerEnrolledBenefitDetailEntity ne doit utiliser le champ calculé que pour les régimes de retraite (459779)

Lors de l’exportation de l’entité **PayrollWorkerEnrolledBenefitDetailEntity**, l’exportation détermine s’il convient d’utiliser un champ calculé basé sur une table de taux ou utiliser le champ **ContributionAmountCur** de la table de sauvegarde. La logique utilisée par l’entité de données utilise la table des taux dans des situations où l’application ne le fait normalement pas. Cette logique fait que les exportations d’entité renvoient une valeur nulle pour cette colonne, car il n’y a pas de table de taux de calcul et le produit ne permet pas au client d’en spécifier une.
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a>Traductions confuses en langue tchèque dans la Gestion du personnel et le libre service des employés (400276)

Cette version corrige les traductions pour **Annuaire de l’entreprise**, **Prochain cours enregistré**, **Emploi**, et **Poste**.
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a>La table WorkCalendarEmployment n’a pas les champs système créés et modifiés activés (460171)

Les champs système créés et modifiés sont désormais activés sur la table **WorkCalendarEmployment** dans Human Resources.
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a>Exception de référence Null pour Embaucher et ajouter des détails pour le futur employé (455475)

Cette version corrige une erreur (une référence Null) dans l’entrée simplifiée de l’employé lors de l’embauche d’un employé en utilisant l’option **Embaucher et ajouter des détails**.

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a>Les modifications apportées à l’entité Employé de Dataverse ne sont pas répercutées dans Human Resources (455652)

Les modifications apportées aux champs suivants de l’entité **Employé** dans Dataverse apparaissent désormais dans Human Resources :

- **Travaille à domicile**
- **Date d’ancienneté**
- **Date anniversaire**
- **Date d’embauche d’origine**

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a>Le niveau de rémunération correct n’est pas défini par défaut en fonction de l’emploi affecté au poste (394136)

Avec ce changement, le niveau de compensation correct est par défaut basé sur les enregistrements **Date d’entrée en vigueur** pour le champ **Détails du poste** et **Date de début** pour l’**Affectation du plan de rémunération**.

## <a name="in-preview"></a>En mode aperçu

## <a name="mandatory-fields"></a>Champs obligatoires 

Vous pouvez maintenant rendre les champs obligatoires en utilisant les fonctionnalités de personnalisation de Human Resources. Cette fonctionnalité nécessite des **Vues enregistrées**.

## <a name="human-resources-application-in-teams"></a>Application Human Resources de Teams

Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams. Ils peuvent interagir avec un bot pour créer des demandes de congé. Pour plus d’informations, voir [Application Human Resources dans Teams](./hr-admin-teams-leave-app.md). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entités DMF (Data Management Framework) pour la gestion des avantages
 
Les entités de gestion des avantages publient. Les entités DMF permettent d’importer et d’exporter des données pour configurer facilement la gestion des avantages. Un modèle de gestion des avantages sera disponible pour déplacer les données. Le modèle exporte et importe les données de manière séquentielle pour respecter les dépendances des données.

## <a name="buy-and-sell-leave"></a>Achat et vente de congés 

Certaines organisations offrent un avantage qui permet aux employés d’acheter ou de vendre des congés. Ce processus est souvent géré manuellement. Cette fonctionnalité automatise la gestion des stratégies et des demandes pour le service RH. Il rationalise le processus de gestion des congés et aide à éliminer les erreurs. Pour plus d’informations, voir :

- [Gérer les stratégies d’achat et de vente de congés](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Achat et vente de congés](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Provisions de congés pour une seule entreprise ou un seul plan

Les clients peuvent traiter les charges à payer pour une seule entreprise ou un seul plan de congé et d’absence. Cette capacité permet de clarifier le processus d’accumulation pour les clients avec différentes années de congé ou politiques d’accumulation de congé. Pour plus d’informations, voir [Accumulation de congés par entreprise ou par plan de congés](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Ajouter des pièces jointes aux demandes de congé

La possibilité d’ajouter des pièces jointes aux demandes de congé approuvées est essentielle dans l’environnement COVID-19 actuel. Les employés peuvent désormais ajouter ces pièces jointes. Ils ont également plus d’informations sur la façon dont les mises à jour sont effectuées pour les demandes de congés. Pour plus d’informations, voir [Ajouter une pièce jointe à une demande existante](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Ajouter un code de motif aux suspensions de cumul 

Des codes de motif ont été ajoutés à la suspension de la comptabilité d’exercice.

## <a name="carry-forward-rules"></a>Règles de report 

Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés. Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours. Pour plus d’informations, voir [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Suspendre l’accumulation de congés pour certains types de congés

Vous pouvez créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés. Le congé sans solde peut être un type, mais ce n’est pas obligatoire. Vous pouvez suspendre tout congé basé sur un autre type de congé.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Entité DMF disponible pour les suspensions de régularisation 

Une entité DMF est désormais disponible pour les suspensions de régularisation.

## <a name="coming-soon"></a>Prochainement

## <a name="checklist-entities-included-in-dataverse"></a>Entités de liste de contrôle incluses dans Dataverse

Les entités de liste de contrôle pour les processus d’intégration, de départ, de transfert et d’entreprise seront bientôt disponibles dans Dataverse.

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]