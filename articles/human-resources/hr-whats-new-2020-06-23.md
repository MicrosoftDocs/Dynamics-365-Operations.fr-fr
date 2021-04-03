---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (25 juin 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 23 juin 2020.
author: andreabichsel
manager: tfehr
ms.date: 06/25/2020
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
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f767ad634a37b7231a7998184ef130668c8a8dc
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463620"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (23 juin 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3347. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a>Lorsqu’une inscription a expiré pour un employé dont le contrat est terminé, le type de départ, le solde et le montant sont tous effacés dans le formulaire Inscription au départ (444867)

Les valeurs des champs **Type de départ**, **Solde** et **Montant** sont maintenant conservées au lieu d’être effacées lors de cette sélection.

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a>Solde prévisionnel incorrect lorsque la nouvelle fonctionnalité (Provisions de congés pour une seule entreprise ou un seul plan) est activée (456553)

Le solde prévisionnel correct s’affiche maintenant lorsque les provisions de congés pour une seule entreprise ou un seul plan ont été activées.

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a>Les entités avec des relations génèrent des propriétés de navigation en double (456486)

Cette version corrige un problème avec les propriétés de navigation (relation) de plusieurs entités. Des relations en double sont détectées. Ces scénarios ont tous été corrigés.
 
## <a name="cross-company-comments-on-performance-review-455536"></a>Commentaires intersociétés sur l’évaluation des performances (455536)

Les commentaires intersociétés sont désormais visibles sur les évaluations des performances avec ce correctif. Cette modification corrige la vue des commentaires des réviseurs qui ont été entrés dans différentes sociétés pour la même évaluation des performances.
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a>Incohérence dans l’affichage des données de gestion des rémunérations (432562)

Une vue cohérente des données de rémunération est désormais gérée dans Libre-service pour responsables. Selon la façon dont vous accédez aux **Détails de rémunération** d’un employé, les données de rémunération s’affichent maintenant de manière cohérente pour les responsables.
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a>La date d’effet du régime de rémunération fixe affiche par défaut la date du jour (411994)

La date de début de rémunération est maintenant basée sur la date de début du poste attribué à l’employé.

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a>L’option Activer la définition d’une demi-journée dans le formulaire de congé et d’absence est désactivée à l’ouverture du formulaire (452607)

Avec cette modification, l’option **Activer la définition d’une demi-journée** sera activée jusqu’à ce que de nouvelles transactions de congé s’affichent. 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a>Impossible de publier sur HcmDiscussionEntity via Excel ; erreur de champ TotalRatingScore (453899)

Vous pouvez maintenant mettre à jour le champ **TotalRatingScore** en utilisant **HCMDiscussionEntity** dans le concepteur de classeurs Excel.

## <a name="in-preview"></a>En mode aperçu

## <a name="database-logging"></a>Connexion à la base de données

La journalisation de la base de données vous permet de déterminer quelles tables et quels champs doivent être surveillés. Elle vous permet également de déterminer les événements qui doivent déclencher le suivi des modifications. Vous utilisez les capacités de journalisation de la base de données pour voir ces changements au fil du temps. Pour plus d’informations, voir [Configurer et gérer la journalisation de la base de données](hr-admin-database-logging.md).

## <a name="mandatory-fields"></a>Champs obligatoires 

Vous pouvez maintenant rendre les champs obligatoires en utilisant les fonctionnalités de personnalisation de Human Resources. Cette fonctionnalité nécessite des **Vues enregistrées**.

## <a name="human-resources-application-in-teams"></a>Application Human Resources de Teams

Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams. Ils peuvent interagir avec un bot pour créer des demandes de congé. Pour plus d’informations, voir [Application Human Resources dans Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

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

## <a name="configure-the-name-of-employee-self-service"></a>Configurer le nom du libre service employé

Une nouvelle option sera disponible dans les **paramètres des Ressources humaines** pour mettre à jour le nom de l’espace de travail Libre-service Employé en Libre-service.

## <a name="checklist-entities-included-in-dataverse"></a>Entités de liste de contrôle incluses dans Dataverse

Les entités de liste de contrôle pour les processus d’intégration, de départ, de transfert et d’entreprise seront bientôt disponibles dans Dataverse.

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]