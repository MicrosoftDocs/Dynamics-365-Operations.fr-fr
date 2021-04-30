---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (06 août 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 06 août 2020.
author: andreabichsel
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: edbfad387496cb3381c6298b9141129c6a878335
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891839"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-06-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (06 août 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3444. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="platform-update-1001236-is-now-available"></a>Platform update 10.0.12(36) est désormais disponible

Pour en savoir plus, consultez [Mises à jour de la plateforme pour la version 10.0.12 des applications Finance and Operations (août 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-10-0-12.md).

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entités DMF (Data Management Framework) pour la gestion des avantages
 
Les entités de gestion des avantages publient. Les entités DMF permettent d’importer et d’exporter des données pour configurer facilement la gestion des avantages. Un modèle de gestion des avantages sera disponible pour déplacer les données. Le modèle exporte et importe les données de manière séquentielle pour respecter les dépendances des données. Pour plus d’informations, voir :

- [Prise en charge des entités DMF](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/dmf-entity-support) dans la 1ère partie du lancement 2020 de Dynamics 365
- [Vue d’ensemble de la gestion des données](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)


## <a name="claire-creates-a-workflow-for-buying-and-selling-leave-requests-446557"></a>Claire crée un workflow pour l’achat et la vente de demandes de congé (446557)

Pour plus d’informations, voir :

- [Permettre aux employés d’acheter et de vendre des congés](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) dans la 2e partie du lancement 2020 de Dynamics 365
- [Gérer les stratégies d’achat et de vente de congés](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Achat et vente de congés](./hr-employee-self-service-buy-sell-leave.md)


## <a name="worker-postal-addresses-v2-entity-has-access-across-legal-entities-with-restricted-access-459126"></a>L’entité V2 des adresses postales des collaborateurs a accès à toutes les entités juridiques à accès restreint (459126)

Avec ce changement, l’entité **Adresse postale du collaborateur V2** restreindra en fonction de l’accès de l’entité juridique donné à l’utilisateur.

## <a name="workflow-email-hyperlink-fails-to-open-relevant-reviews-437398"></a>Le lien hypertexte de l’e-mail de workflow ne parvient pas à ouvrir les avis pertinents (437398)

Lorsque vous utilisez l’espace réservé pour ouvrir une évaluation des performances dans le workflow de révision, le lien hypertexte généré dans l’e-mail ouvre désormais l’enregistrement sélectionné.

## <a name="new-entities-for-buying-and-selling-leave-473180"></a>Nouvelles entités pour l’achat et la vente de congés (473180)

Les entités du cadre de gestion des données sont désormais disponibles pour l’achat et la vente de congés. Pour plus d’informations, voir [Vue d’ensemble de la gestion des données](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

## <a name="when-viewing-record-information-and-using-advanced-filters-a-user-could-gain-access-to-other-employees-records-472490"></a>Lors de l’affichage des informations d’enregistrement et de l’utilisation de filtres avancés, un utilisateur peut accéder aux enregistrements d’autres employés (472490)

Avec cette modification, les utilisateurs du libre-service des employés ne peuvent accéder qu’à leurs propres enregistrements en utilisant le libre-service des employés. L’affichage des informations d’enregistrement tout en modifiant l’option de filtrage n’expose plus de données supplémentaires.

## <a name="personnel-management-analytics-include-exited-worker-records-382893"></a>L’analyse de la gestion du personnel comprend les enregistrements des collaborateurs ayant quitté la société (382893)

Avec cette version, les analyses de gestion du personnel incluent désormais uniquement les collaborateurs actifs. 
 
## <a name="unable-to-process-a-merit-increase-for-an-employee-473125"></a>Impossible de traiter une augmentation pour mérite pour un employé (473125)

Cette modification vous permet de saisir des augmentations pour mérite lorsque vous modifiez la date d’entrée en vigueur de la nouvelle augmentation pour mérite.

## <a name="review-workflow-can-be-started-more-than-once-467541"></a>Le workflow d’évaluation peut être démarré plusieurs fois (467541)

Avec cette modification, vous ne pouvez démarrer le workflow d’évaluation des performances qu’une seule fois. Le statut du responsable n’affiche plus l’option de commencer l’évaluation.

## <a name="leave-request-work-flow-ends-in-error-when-canceling-an-approved-leave-request-472063"></a>Le workflow de demande de congé se termine par une erreur lors de l’annulation d’une demande de congé approuvée (472063)

Dans cette version, lorsque vous annulez une demande de congé approuvée, l’état de la demande ne reste plus approuvé et le workflow se poursuit.

## <a name="system-suggests-exited-workers-when-creating-a-new-review-form-the-template-460624"></a>Le système suggère des collaborateurs ayant quitté la société lors de la création d’une nouvelle évaluation à partir du modèle (460624)

Avec ce changement, les collaborateurs ayant quitté la société ne sont plus disponibles lors de la création de nouvelles évaluations à partir d’un modèle. Vous ne pouvez pas créer d’évaluation pour les employés qui sont en dehors des dates de leur emploi.

## <a name="position-hierarchy-circular-reference-detection-415879"></a>Détection de référence circulaire de hiérarchie des postes (415879)

Avec ce changement, la détection de référence circulaire de la hiérarchie des postes est limitée à un seul point dans le temps. Vous pouvez exécuter une détection de référence circulaire pour différentes dates afin de vérifier que la structure de rapport ne contient aucune référence circulaire.

## <a name="buy-and-sell-leave"></a>Achat et vente de congés 

Certaines organisations offrent un avantage qui permet aux employés d’acheter ou de vendre des congés. Ce processus est souvent géré manuellement. Cette fonctionnalité automatise la gestion des stratégies et des demandes pour le service RH. Il rationalise le processus de gestion des congés et aide à éliminer les erreurs. Pour plus d’informations, voir :

- [Permettre aux employés d’acheter et de vendre des congés](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) dans la 2e partie du lancement 2020 de Dynamics 365
- [Gérer les stratégies d’achat et de vente de congés](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Achat et vente de congés](./hr-employee-self-service-buy-sell-leave.md)

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

## <a name="in-preview"></a>En mode aperçu

### <a name="mandatory-fields"></a>Champs obligatoires

Vous pouvez rendre les champs obligatoires en utilisant les fonctionnalités de personnalisation de Human Resources. Cette fonctionnalité nécessite des **Vues enregistrées**. Pour plus d’informations sur les vues enregistrées, voir :

- [Vues enregistrées – disponibilité générale](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) dans la 2e partie du lancement 2020 de Dynamics 365
- [Écrans de version utilisant entièrement des vues enregistrées](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Application Human Resources de Teams

Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams. Ils peuvent interagir avec un bot pour créer des demandes de congé. Pour plus d’informations, voir :

- [Expérience des employés en congé et absence Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) dans la 1ère partie du lancement 2020 de Dynamics 365
- [Application Human Resources de Teams](./hr-admin-teams-leave-app.md)

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Entité DMF disponible pour les suspensions de régularisation

Une entité DMF est désormais disponible pour les suspensions de régularisation.

## <a name="coming-soon"></a>Prochainement

## <a name="checklist-entities-included-in-dataverse"></a>Entités de liste de contrôle incluses dans Dataverse

Les entités de liste de contrôle pour les processus d’intégration, de départ, de transfert et d’entreprise seront bientôt disponibles dans Dataverse.

## <a name="known-issues"></a>Problèmes connus

L’espace de travail **Gestion des fonctionnalités** peut afficher des fonctionnalités désactivées en tant que fonctionnalités d’aperçu lorsqu’elles sont généralement disponibles. Vous trouverez ci-dessous une liste des fonctionnalités généralement disponibles qui indiquent un état incorrect. 

1.  Gestion des avantages
2.  Gestion des dossiers
3.  Journalisation de base de données (audit)
4.  Régularisation des congés pour une seule société ou un seul plan
5.  Suspension de la régularisation des congés et des absences
6.  Code motif d’ajustement du solde et commentaire
7.  Achat et vente de congés
8.  Calendrier des congés et des absences
9.  Règles de report de congés
10. Audit de régularisation des congés
11. Suppression de régularisations de congé
12. Arrondi de la régularisation des congés
13. Configurer plusieurs types de congés sur un seul plan de congé
14. Mettre à jour les améliorations de période de congés
15. Utiliser l’ETP d’un employé pour les régularisations
16. Vue Rémunération intersociétés
17. Imprimer les évaluations des performances
18. Corrections des jours fériés pour la régularisation des congés

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]