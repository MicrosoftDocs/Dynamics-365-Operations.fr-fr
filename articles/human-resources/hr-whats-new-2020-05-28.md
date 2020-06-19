---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (28 mai 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2020
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c386025843edef83d229a42d3f2314678fadae20
ms.sourcegitcommit: beddfba095c23b3265f0004f5124c4e9dc6404cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411928"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (28 mai 2020)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s'appliquent au numéro de version 8.1.3287. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a>L'entité LeaveRequest ne fonctionne pas lorsque vous activez plusieurs types par plan de congé (447498)

Avec cette modification, l'entité **LeaveEnrollmentV2Entity** est désormais disponible pour corriger l'erreur qui se produit lorsque vous activez plusieurs types de congé.

## <a name="batch-contention-reduction-feature-preview-446619"></a>Fonction de réduction des conflits de lots (préversion) (446619)

Lorsque vous activez cette fonctionnalité, vous pouvez vous attendre à une réduction des blocages dans les tables de cadre par lots lors de la sélection des tâches et l'achèvement des tâches.

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a>UpdateConflict pendant l'enregistrement d'un collaborateur empêche de modifier un enregistrement dans Personnes (427915)

Cette modification corrige une erreur lors de l'ajout d'un nouveau collaborateur, de la mise à jour des informations d'adresse et de la modification des préférences linguistiques. Dans ce scénario unique, une erreur s'affiche indiquant que l'enregistrement n'a pas pu être mis à jour. 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a>Impossible d'ajouter une pièce jointe à une demande de congé approuvée à soumettre à nouveau (425407)

Cette modification autorise désormais de joindre des documents aux demandes de congé approuvées.

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a>L'utilisateur peut saisir la rémunération d'un collaborateur dans un formulaire d'entité juridique différent (409529)

Cette modification désactive les options de rémunération pour empêcher la saisie par inadvertance d'enregistrements de rémunération pour la mauvaise entité juridique.

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a>Erreur lorsque vous transférez un collaborateur et que la date d'affectation de poste du collaborateur est antérieure à la durée du poste (429402)

Les messages d'erreur lors du transfert d'un collaborateur dans ce scénario ont été mis à jour pour mieux décrire les modifications nécessaires pour corriger le problème.

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a>Fonctionnalités de pièces jointes dans l'adhésion aux avantages en libre service des employés
 
Vous pouvez maintenant ajouter des pièces jointes pendant le processus d'adhésion aux avantages pour chaque plan auquel le collaborateur souscrit. Vous pouvez ensuite afficher les pièces jointes dans le formulaire **Avantages inscrits du collaborateur**.

## <a name="in-preview"></a>En mode aperçu

## <a name="human-resources-application-in-teams"></a>Application Human Resources de Teams

Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams. Ils peuvent interagir avec un bot pour créer des demandes de congé. Pour plus d'informations, voir [Application Human Resources dans Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="leave-suspension"></a>Suspension des congés

Vous pouvez suspendre les congés et les absences d'un employé dans Human Resources. La suspension des congés arrête les régularisations de congés pour les types de congé sélectionnés. Si la suspension survient après le traitement d'une régularisation, la suspension du congé crée un ajustement au prorata du solde des congés de l'employé. Pour plus d'informations, voir la rubrique [Suspension des congés](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Mettre à jour l'expérience utilisateur pour indiquer que la comptabilité d'exercice est suspendue (429550)

L'expérience utilisateur indique désormais que la comptabilité d'exercice a été suspendue pour un plan.

## <a name="coming-soon"></a>Prochainement

## <a name="database-logging-in-preview-in-june"></a>Journalisation de la base de données (en préversion en juin)

La fonctionnalité de journalisation de la base de données vous permet de déterminer quelles tables et quels champs doivent être surveillés. Elle vous permet également de déterminer les événements qui doivent déclencher le suivi des modifications. Des capacités de recherche sont disponibles pour observer ces changements au fil du temps.

## <a name="buy-and-sell-leave-in-preview-june-1"></a>Achat et vente de congés (en préversion le 1er juin)

Certaines organisations offrent un avantage qui permet aux employés d'acheter ou de vendre des congés. Ce processus est souvent géré manuellement. Cette fonctionnalité offre un moyen plus automatisé de gérer les politiques et les demandes au service des ressources humaines. Elle aide également à éliminer les erreurs tout en rationalisant le processus de gestion des congés.

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entités DMF (Data Management Framework) pour la gestion des avantages
 
Les entités de gestion des avantages publient. Les entités DMF permettent d'importer et d'exporter des données pour configurer facilement la gestion des avantages. Un modèle de gestion des avantages sera également disponible pour déplacer les données. Le modèle exporte et importe les données de manière séquentielle pour respecter les dépendances des données.

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a>Ajouter un code motif aux suspensions de cumul (1er juin)

Des codes de motif ont été ajoutés à la suspension de la comptabilité d'exercice.

## <a name="carry-forward-rules-june-1"></a>Règles de report (1er juin)

Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés. Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours. Pour plus d'informations, voir [Configurer les types de congé et d'absence](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a>Suspendre l'accumulation de congés pour certains types de congés (1er juin)

Dans cette version, les RH peuvent créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés. Le congé sans solde peut être un type, mais ce n'est pas obligatoire. Vous pouvez suspendre tout congé basé sur un autre type de congé.

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a>Entité DMF disponible pour les suspensions de régularisation (1er juin)

Une entité DMF est désormais disponible pour les suspensions de régularisation.