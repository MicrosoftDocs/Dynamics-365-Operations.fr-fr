---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (14 mai 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 14 mai 2020.
author: andreabichsel
manager: tfehr
ms.date: 05/14/2020
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
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b8d65236d316035722451a871afabedc6ab73f7a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127847"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (14 mai 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3244. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support Lifecycle Services (LCS) pour référence.

## <a name="platform-changes"></a>Modifications de plateforme

Des modifications de plateforme sont incluses dans la version de cette semaine. Pour en savoir plus, consultez [Mises à jour de la plateforme pour la version 10.0.10 des applications Finance and Operations (mai 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34). Cette version inclut des corrections de bugs et des modifications des vues enregistrées.
 
## <a name="ensure-dataverse-picklists-are-consistent-with-leave-enums-436343"></a>Garantir que les listes de sélection Dataverse sont compatibles avec les énumérations relatives aux congés (436343)

Les listes de sélection Dataverse sont désormais compatibles avec les énumérations relatives aux congés.

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a>Autoriser les utilisateurs à configurer le workflow de demande de congé en fonction du montant de la demande (300044)

Les utilisateurs peuvent configurer les workflows de demande de congé en fonction des montants de la demande.
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a>Un nouveau formulaire de travail expose les données via le menu Afficher lorsque la sécurité avancée est activée (403185)

Cette version corrige le fonctionnement de l’affichage des employés dans les entités juridiques lorsque l’accès avancé est activé et que les employés d’autres entreprises sont accessibles.

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a>Autoriser les cumuls de congés pour un seul régime ou une seule entreprise (318844)

Avec cette modification, vous pouvez exécuter des régularisations pour une entreprise ou un plan.
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a>Afficher l’équivalent temps plein (ETP) du poste dans le formulaire Collaborateurs inscrits (414658)

La valeur ETP du poste d’un travailleur détermine le taux d’accumulation d’un travailleur lorsque l’option ETP est activée sur le type de congé. Ce champ est désormais inclus dans le formulaire **Collaborateurs inscrits** et la boîte de dialogue **Inscription en masse**.

## <a name="add-leave-balance-expiration-batch-job-431266"></a>Ajouter un traitement par lots d’expiration du solde de congés (431266)

Un nouveau traitement par lots est désormais disponible et s’exécute quotidiennement. Il diminue le solde de congés restant lorsque les dates d’expiration sont atteintes.

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a>L’exportation des contacts personnels d’un employé à l’aide de l’entité Personne à contacter personnelle du collaborateur n’exporte pas les contacts personnels avec le type de relation Parent (345893)

L’entité de données **Personne à contacter personnelle du collaborateur** (**HcmPersonalContactPersonEntity** dans DMF et **PersonalContactPerson** dans OData) n’a pas pu exporter les contacts personnels qui ont un type de relation **Parent**. Ce problème est résolu pour les contacts personnels créés après cette modification. Les contacts personnels existants de type **Parent** seront corrigés dans une version ultérieure.

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a>Les codes de motif s’affichent dans différents scénarios lorsqu’ils sont marqués comme Congé et absence et que le formulaire d’employé rationalisé est activé (434163)

Cette modification limite les codes de motif aux codes de congé et d’absence uniquement lorsque vous activez la saisie simplifiée des employés.

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a>La fonction d’aperçu Attribuer un plan de congés aux employés dans le future affiche une erreur (433555)

Cette modification corrige une erreur lorsqu’un plan de congé a deux types de congé affectés et que vous essayez d’affecter un employé.

## <a name="getting-started-banner-appears-for-all-users-441731"></a>La bannière de mise en route apparaît pour tous les utilisateurs (441731)

Avec cette modification, la bannière de mise en route est masquée pour les utilisateurs qui ne sont pas administrateurs système ou administrateurs de gestion des données. 

## <a name="the-dataverse-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a>L’entité Adresse du collaborateur Dataverse fonctionne différemment en termes de dates d’effet date-heure dans Human Resources (425071)

Cette modification maintient les informations d’adresse alignées dans certains scénarios, en fonction des dates de l’adresse.

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a>Impossible d’ajouter une pièce jointe à une demande de congé approuvée (425407)

Avec la version de cette semaine, vous pouvez ajouter des pièces jointes aux demandes de congé approuvées sans modifier la demande de congé.

## <a name="in-preview"></a>En mode aperçu

## <a name="leave-suspension"></a>Suspension des congés

Vous pouvez suspendre les congés et les absences d’un employé dans Human Resources. La suspension des congés arrête les régularisations de congés pour les types de congé sélectionnés. Si la suspension survient après le traitement d’une régularisation, la suspension du congé crée un ajustement au prorata du solde des congés de l’employé. Pour plus d’informations, voir la rubrique [Suspension des congés](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Mettre à jour l’expérience utilisateur pour indiquer que la comptabilité d’exercice est suspendue (429550)

L’expérience utilisateur indique désormais que la comptabilité d’exercice a été suspendue pour un plan.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Suspendre l’accumulation de congés pour certains types de congés (272447)

Dans cette version, les RH peuvent créer une règle pour suspendre les cumuls de congés pour les employés dont les demandes de congés ont été saisies pour des congés non payés. Le congé sans solde peut être un type, mais ce n’est pas obligatoire. Vous pouvez suspendre tout congé basé sur un autre type de congé.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>Entité DMF disponible pour les suspensions de régularisation (429549)

Une entité DMF est désormais disponible pour les suspensions de régularisation.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Ajouter un code de motif aux suspensions de cumul (429547)

Des codes de motif ont été ajoutés à la suspension de la comptabilité d’exercice.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Commencer la transition des paramètres des Ressources humaines vers les paramètres de congés et d’absence

Cette version commence à combiner les paramètres des Ressources humaines avec les paramètres de Congé et d’absence.

## <a name="carry-forward-rules"></a>Règles de report

Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés. Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours. Pour plus d’informations, voir [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]