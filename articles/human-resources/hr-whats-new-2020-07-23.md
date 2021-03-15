---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (23 juillet 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 23 juillet 2020.
author: andreabichsel
manager: tfehr
ms.date: 07/23/2020
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
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f5e10d6d1dedfc251a1a00110b50c9096314d75b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127519"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (23 juillet 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3416. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a>La suppression des dimensions financières d’un poste ne fonctionne pas comme prévu (445476)

La suppression des dimensions d’un poste supprime maintenant ces mêmes postes de Dataverse.

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a>Les postes en dehors de la hiérarchie affichent des postes inactifs (397257)

Les postes inactifs (dont la durée a expiré) ne s’affichent plus dans la hiérarchie des postes en tant que **Postes en dehors de la hiérarchie**. 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a>La validation entre LeaveEnrollmentEntity et HcmWorkerEntity lors de l’importation via Data Management Framework (DMF) entraîne des chargements de données lents (442324)

Les modifications apportées à cette version augmentent les performances de **LeaveEnrollmentEntity**.

## <a name="unable-to-personalize-in-organization-administration-447490"></a>Impossible de personnaliser dans le module Administration de l’organisation (447490)

Avec cette modification, vous pouvez maintenant personnaliser les liens dans **Administration de l’organisation**.

## <a name="in-preview"></a>En mode aperçu

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

Les clients peuvent traiter les charges à payer pour une seule entreprise ou un seul plan de congé et d’absence. Cette capacité permet de clarifier le processus d’accumulation pour les clients avec différentes années de congé ou politiques d’accumulation de congés. Pour plus d’informations, voir [Accumulation de congés par entreprise ou par plan de congés](hr-leave-and-absence-accrue.md).

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

## <a name="platform-changes"></a>Modifications de plateforme

Platform update 10.0.12 (36)

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]