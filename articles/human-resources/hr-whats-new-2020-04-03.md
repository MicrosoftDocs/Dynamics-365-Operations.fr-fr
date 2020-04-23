---
title: Nouveautés et modifications dans Dynamics 365 Human Resources (3 avril 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 04/03/2020
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
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ab732853a2c37338d8003c5f8911c011aa8ffc60
ms.sourcegitcommit: 724f5b400a4e7c385da9d8b22db416ebc3623b93
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "3225149"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-3-2020"></a>Nouveautés et modifications dans Dynamics 365 Human Resources (3 avril 2020)

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s'appliquent au numéro de version 8.1.3111. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support Lifecycle Services (LCS) pour référence.

## <a name="features-that-are-generally-available-the-week-of-april-6"></a>Fonctionnalités généralement disponibles la semaine du 6 avril

- **Fonctionnalités Congés et absences** - Pour en savoir plus, voir [Vue d'ensemble des congés et absences](hr-leave-and-absence-overview.md).

- **Fonctionnalités de la gestion des avantages** - Pour en savoir plus, voir [Vue d'ensemble de la gestion des avantages](hr-benefits-management-overview.md).

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Les limites de l'environnement Human Resources sont désormais basées sur la mise à jour des licences (394595)

La limite du nombre d'environnements par projet dans LCS a changé. La limite précédente était de deux environnements. La limite du nombre d'environnements de production et de bac à sable que vous pouvez créer pour Human Resources dans LCS est désormais basée sur la mise à jour des licences. Vous pouvez désormais créer autant d'environnements que nécessaire par projet LCS, en fonction du nombre de licences achetées. La nouvelle licence, mise à jour le 1er février 2020, permet aux clients d'acheter des environnements supplémentaires. Pour plus d'informations sur les exigences de licence pour des environnements supplémentaires, consultez [Guide de licence Dynamics 365](https://dynamics.microsoft.com/pricing/#HumanResources).
 
## <a name="error-when-trying-to-delete-a-questionnaire-428603"></a>Erreur lors de la tentative de suppression d'un questionnaire (428603)

La mise à jour de cette semaine corrige un problème où l'erreur suivante s'affiche lors de la tentative de suppression d'un questionnaire :

Une paire X++ TTSBEGIN/TTSCOMMIT non équilibrée a été détectée.

## <a name="performance-journal-and-professional-certificates-security-issue-428499"></a>Problème de sécurité du journal de performance et des certificats professionnels (428499)

Cette modification limite la visibilité des revues de performance et des certificats professionnels selon les entreprises auxquelles ils ont accès. 

## <a name="the-abbreviation-for-quebec-and-manitoba-387510"></a>L'abréviation de Québec et Manitoba (387510)

Les données de départ ont été mises à jour pour refléter l'abréviation correcte pour Manitoba et Québec.

## <a name="new-entities-available-in-data-management-framework"></a>Nouvelles entités disponibles dans DMF

Les entités suivantes sont maintenant disponibles. Si vous ne voyez pas ces entités répertoriées dans la liste des entités, utilisez l'option **Actualiser les entités** dans **Paramètres de l'environnement > Paramètres d'entité > Actualiser la liste d'entités**.

 - Transaction bancaire de congé et d'absence V2
 - Inscription de congé et d'absence V2
 - Niveau de plan de congé et d'absence V2
 - Plan de congé et d'absence V2

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>La solution Common Data Service est désormais disponible avec les modifications suivantes :

| Description  | Monnaie |
| --- | --- |
| Modifications de l'entité **Poste** | <ul><li>**Région de rémunération** ajoutée</li>|
| Entité **Dimension du poste** ajoutée | <ul><li>**Dimensions financières** ajoutées</li>
| Modifications de l'entité **Collaborateur** | <ul><li>**Séquence de noms** ajoutée</li><li>**Télétravaille** ajouté</li><li>**Langue** ajoutée</li><li>**Date d'ancienneté** ajoutée</li><li>**Date anniversaire** ajoutée</li><li>**Date d'embauche d'origine** ajoutée</li></ul> |
| Modifications de l'entité **Emploi** | <ul><li>**Dimensions financières** ajoutées</li><li>**Motif de la fin du contrat** ajouté</li><li>**Date de résiliation** renommée à partir de **Date de transition**</li><li>**Période d'essai** ajoutée</li></ul> |
| Modifications de l'entité **Adresse du collaborateur** | <ul><li>**Nom de la rue** ajouté</li><li>**Ligne d'adresse 1**, **Ligne d'adresse 2** et **Ligne d'adresse 3** marquées pour suppression</li></ul> |
| Nouvelles entités de configuration de la rémunération variable | <ul><li>**Type de régime variable de rémunération**</li><li>**Régime variable de rémunération**</li><li>**Règles d'acquisition**</li><li>**Niveau de régime variable de rémunération**</li></ul> |
| Nouvelle entité **Emploi du calendrier du collaborateur** | <ul><li>**Entité de calendrier de travail** ajoutée</li></ul> |
| Nouvelle entité **Détails du poste de paie** | <ul><li>**Détails du poste de paie** ajoutés</li></ul> |
| Nouvelle entité **Titre** | <ul><li>**Titre** ajouté</li></ul>La nouvelle entité **Titre** est incluse dans Common Data Service, mais n'est pas référencée depuis les entités **Poste** ou **Tâche** à ce moment même. |

> [!NOTE]
> Les dimensions financières des postes et de l'emploi offrent une intégration à sens unique pour les mises à jour des ressources humaines vers Common Data Service. Les mises à jour des dimensions financières ne sont actuellement pas synchronisées à partir de Common Data Service vers les ressources humaines.

Au cours des prochaines semaines, ces modifications d'entités seront disponibles dans tous les environnements. Pour installer manuellement la dernière solution Common Data Service pour les ressources humaines :

1.  Accédez au [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).

2.  Sélectionner **Environnements**.

3.  Recherchez l'environnement que vous souhaitez mettre à niveau. L'environnement doit correspondre à **Nom de l'environnement** dans la section **Informations relatives à Common Data Service** dans le formulaire **À propos de** dans Human Resources.

4.  Sélectionnez l'environnement pour afficher les détails de l'environnement.

5.  Dans la barre d'action située en haut, sélectionnez **Gérer les solutions**. Une nouvelle fenêtre de navigateur s'ouvrira et accédera au **Centre d'administration Dynamics 365** dans le contexte de votre environnement.

6.  Dans la liste **Solution**, sélectionnez **Ancre Dynamics 365 Human Resources**.

7.  Sélectionnez **Mettre à niveau** pour appliquer la dernière solution.

## <a name="in-preview"></a>En version préliminaire

## <a name="leave-suspension"></a>Suspension des congés

Vous pouvez suspendre les congés et les absences d'un employé dans Human Resources. La suspension des congés arrête les régularisations de congés pour les types de congé sélectionnés. Si la suspension survient après le traitement d'une régularisation, la suspension du congé crée un ajustement au prorata du solde des congés de l'employé. Pour plus d'informations, voir la rubrique [Suspension des congés](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Règles de report

Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés. Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours. Pour plus d'informations, voir [Configurer les types de congé et d'absence](hr-leave-and-absence-types.md).

## <a name="coming-soon"></a>Prochainement

## <a name="new-production-release-cadence"></a>Nouvelle cadence de sortie de production

À partir d'avril, le rythme de publication des versions pour Human Resources passera d'une mise à jour hebdomadaire à une mise à jour toutes les deux semaines. Pour garantir l'alignement avec les pratiques de déploiement sécurisées et maintenir des normes élevées de stabilité et de fiabilité du service, le processus de déploiement des mises à jour de service dans toutes les régions se déroulera sur deux semaines. Des tests et des moniteurs supplémentaires seront en place pour vérifier le succès du déploiement à chaque étape du processus. Pour plus d'informations sur la cadence de publication, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

## <a name="known-issues"></a>Problèmes connus

## <a name="employment-detail-entity"></a>Entité Détails de l'emploi

L'entité **Détail de l'emploi** a été mise à jour avec les champs suivants : **PayFrequency**, **ID de catégorie d'emploi**, **Type d'emploi**, **ID de type d'emploi** et **Statut d'emploi à avantages**. Les données de configuration de ces champs reposent sur l'activation de la gestion des avantages dans la gestion des fonctionnalités. Ces champs ne doivent pas être remplis ou mis à jour dans l'entité **Détails de l'emploi**, car cela entraînera des erreurs lors de l'importation.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>L'aperçu SharePoint ne fonctionne pas dans certains environnements

Si l'aperçu du document pour les documents stockés dans SharePoint ne fonctionne pas, essayez la procédure suivante :

1. Vérifiez que le compte utilisateur Admin possède un e-mail associé à l'enregistrement utilisateur. Vous pouvez afficher ces informations sur la page **Utilisateur**. Si le courrier électronique n'est pas configuré, vous devez ajouter le courrier électronique et le fournisseur avec le complément OData Excel. Par défaut, l'adresse e-mail n'est pas présente dans la conception Excel. Vous devrez modifier la conception d'Excel, ajouter tous les champs, appliquer et actualiser. Une fois ces étapes exécutées, vous pouvez mettre à jour le compte administrateur.

2. Une fois que le compte administrateur a un compte de messagerie associé, connectez-vous à Human Resources avec les informations d'identification d'administrateur.

3. Accédez à une pièce jointe dans SharePoint pour lancer l'aperçu du document.

4. Connectez-vous avec un autre compte d'utilisateur qui a accès aux pièces jointes et vérifiez que l'aperçu fonctionne comme prévu.