---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (19 mars 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 19 mars 2020.
author: Darinkramer
manager: AnnBe
ms.date: 03/19/2020
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
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f0b961de23a76947440f6616176874dc6a86cc4c
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712518"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-19-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (19 mars 2020)

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3014. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support Lifecycle Services (LCS) pour référence.

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Les limites de l’environnement Human Resources sont désormais basées sur la mise à jour des licences (394595)

La limite du nombre d’environnements par projet dans Lifecycle Services (LCS) a changé. La limite précédente était de deux environnements. La limite du nombre d’environnements de production et de bac à sable que vous pouvez créer pour Human Resources dans LCS est désormais basée sur la mise à jour des licences. Vous pouvez désormais créer autant d’environnements que nécessaire par projet LCS, en fonction du nombre de licences achetées. La nouvelle licence, mise à jour le 1er février 2020, permet aux clients d’acheter des environnements supplémentaires. Pour plus d’informations sur les exigences de licence pour des environnements supplémentaires, consultez [Guide de licence Dynamics 365](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="provide-cross-company-viewing-of-compensation-data-for-employees-and-managers-403904"></a>Fournir une visualisation intersociétés des données de rémunération pour les employés et les responsables (403904)

Activez cette fonctionnalité dans l’espace de travail **Gestion des fonctionnalités**. Pour plus d’informations, voir [Activer ou désactiver les fonctionnalités en version préliminaire](hr-admin-manage-features.md#enable-or-disable-preview-features).

Lorsque vous activez cette fonction, les responsables peuvent voir la rémunération des subordonnés directs et étendus sans avoir à se connecter à l’entreprise qui emploie. L’historique complet de la rémunération est disponible auprès de toute entreprise connectée à laquelle le responsable peut accéder. Pour plus d’informations, voir [Vue d’ensemble du libre-service pour employés et pour responsables](hr-employee-manager-self-service-overview.md).

## <a name="enable-global-address-book-merge-functionality-427189"></a>Activer la fonctionnalité de fusion du carnet d’adresses global (427189)

Vous pouvez désormais fusionner des entrées de carnet d’adresses en double en sélectionnant les enregistrements en double et en choisissant **Fusionner** depuis la page **Carnet d’adresses global**.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-the-multiple-leave-type-feature-on-419635"></a>Impossible d’ajuster le solde des congés pour un plan sans cumul qui a été créé avec la fonction Type de congé multiple activée (419635)

Vous pouvez maintenant ajuster les soldes des plans de congés créés avec la fonctionnalité en version préliminaire **Plusieurs types de congé** activée dans Gestion des fonctionnalités.

## <a name="primary-position-field-in-the-workerpositionassignmententity-when-an-employee-is-terminated-420774"></a>Champ Poste principal dans WorkerPositionAssignmentEntity lorsqu’un employé est licencié (420774)

Pour les employés dont l’emploi a pris fin, le poste principal qui était actif au moment de la cessation d’emploi est affiché dans l’entité. Pour les intégrations, un enregistrement en double ne sera plus créé pour l’affectation de poste de collaborateur de l’employé. 

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>La solution Common Data Service est désormais disponible avec les modifications suivantes :

| Description | Monnaie |
| --- | --- |
| Modifications de l’entité **Poste** | <ul><li>**Région de rémunération** ajoutée</li>|
| Entité **Dimension du poste** ajoutée | <ul><li>**Dimensions financières** ajoutées</li>
| Modifications de l’entité **Collaborateur** | <ul><li>**Séquence de noms** ajoutée</li><li>**Télétravaille** ajouté</li><li>**Langue** ajoutée</li><li>**Date d’ancienneté** ajoutée</li><li>**Date anniversaire** ajoutée</li><li>**Date d’embauche d’origine** ajoutée</li></ul> |
| Modifications de l’entité **Emploi** | <ul><li>**Dimensions financières** ajoutées</li><li>**Motif de la fin du contrat** ajouté</li><li>**Date de résiliation** renommée à partir de **Date de transition**</li><li>**Période d’essai** ajoutée</li></ul> |
| Modifications de l’entité **Adresse du collaborateur** | <ul><li>**Nom de la rue** ajouté</li><li>**Ligne d’adresse 1**, **Ligne d’adresse 2** et **Ligne d’adresse 3** marquées pour suppression</li></ul> |
| Nouvelles entités de configuration de la rémunération variable | <ul><li>**Type de régime variable de rémunération**</li><li>**Régime variable de rémunération**</li><li>**Règles d’acquisition**</li><li>**Niveau de régime variable de rémunération**</li></ul> |
| Nouvelle entité **Emploi du calendrier du collaborateur** | <ul><li>**Entité de calendrier de travail** ajoutée</li></ul> |
| Nouvelle entité **Détails du poste de paie** | <ul><li>**Détails du poste de paie** ajoutés</li></ul> |
| Nouvelle entité **Titre** | <ul><li>**Titre** ajouté</li></ul>La nouvelle entité **Titre** est incluse dans Common Data Service, mais n’est pas référencée depuis les entités **Poste** ou **Tâche** à ce moment même. |

> [!NOTE]
> Les dimensions financières des postes et de l’emploi offrent une intégration à sens unique pour les mises à jour des ressources humaines vers Common Data Service. Les mises à jour des dimensions financières ne sont actuellement pas synchronisées à partir de Common Data Service vers les ressources humaines.

Au cours des prochaines semaines, ces modifications d’entités seront disponibles dans tous les environnements. Pour installer manuellement la dernière solution Common Data Service pour les ressources humaines :

1.  Accédez au [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com).

2.  Sélectionner **Environnements**.

3.  Recherchez l’environnement que vous souhaitez mettre à niveau. L’environnement doit correspondre à **Nom de l’environnement** dans la section **Informations relatives à Common Data Service** dans le formulaire **À propos de** dans Human Resources.

4.  Sélectionnez l’environnement pour afficher les détails de l’environnement.

5.  Dans la barre d’action située en haut, sélectionnez **Gérer les solutions**. Une nouvelle fenêtre de navigateur s’ouvrira et accédera au **Centre d’administration Dynamics 365** dans le contexte de votre environnement.

6.  Dans la liste **Solution**, sélectionnez **Ancre Dynamics 365 Human Resources**.

7.  Sélectionnez **Mettre à niveau** pour appliquer la dernière solution.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>L’aperçu SharePoint ne fonctionne pas dans certains environnements

Si l’aperçu du document pour les documents stockés dans SharePoint ne fonctionne pas, essayez la procédure suivante :

1. Vérifiez que le compte utilisateur Admin possède un e-mail associé à l’enregistrement utilisateur. Vous pouvez afficher ces informations sur la page **Utilisateur**. Si le courrier électronique n’est pas configuré, vous devez ajouter le courrier électronique et le fournisseur avec le complément OData Excel. Par défaut, l’adresse e-mail n’est pas présente dans la conception Excel. Vous devrez modifier la conception d’Excel, ajouter tous les champs, appliquer et actualiser. Une fois ces étapes exécutées, vous pouvez mettre à jour le compte administrateur.

2. Une fois que le compte administrateur a un compte de messagerie associé, connectez-vous à Human Resources avec les informations d’identification d’administrateur.

3. Accédez à une pièce jointe dans SharePoint pour lancer l’aperçu du document.

4. Connectez-vous avec un autre compte d’utilisateur qui a accès aux pièces jointes et vérifiez que l’aperçu fonctionne comme prévu.

## <a name="coming-soon"></a>Prochainement

### <a name="platform-update-33"></a>Update 33 de la plateforme

- Applications pleine page (Aperçu) - Cette fonctionnalité d’aperçu, qui vous oblige à activer la fonction Vues enregistrées, permet à Power Apps et aux applications tierces d’être ajoutées en tant qu’expériences pleine page via le tableau de bord.

- Vues enregistrées (Aperçu) - Cette fonction d’aperçu active les vues enregistrées, ce qui constitue une amélioration significative du sous-système de personnalisation. Cette fonctionnalité permet aux utilisateurs d’avoir plusieurs ensembles de personnalisations nommés par page. Vous pouvez également publier des vues sur les rôles de sécurité.

- Expérience de filtrage optimisée « fait partie de » - Cette fonctionnalité permet une expérience de filtrage optimisée « fait partie de » qui facilite la saisie de plusieurs valeurs de filtre, a un mécanisme plus simple pour supprimer une valeur de filtre individuelle ou toutes les visualisations des valeurs de filtre.

- Champs recommandés - Les utilisateurs doivent souvent ajouter des champs à une grille ou à une page. Cela peut être difficile avec autant de champs disponibles. Au lieu d’avoir à parcourir une grande liste, cette fonction permet au système de faire apparaître un ensemble de champs recommandés en fonction de ce que les autres utilisateurs ajoutent le plus souvent dans des scénarios similaires.

- Actions par défaut rémanentes dans les grilles - Cette fonctionnalité garantit que l’action par défaut dans une grille est liée à une colonne spécifique dans une grille, que cette colonne soit déplacée ou masquée.

## <a name="new-production-release-cadence"></a>Nouvelle cadence de sortie de production

À partir d’avril, le rythme de publication des versions pour Human Resources passera d’une mise à jour hebdomadaire à une mise à jour toutes les deux semaines. Cela garantira la conformité avec les pratiques de déploiement sûres et préservera des normes élevées de stabilité et de fiabilité dans le service. Nous mettons en place des tests et des moniteurs supplémentaires pour vérifier le succès du déploiement à chaque étape du processus. Pour plus d’informations sur la cadence de sortie, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

## <a name="in-preview"></a>En mode aperçu

Les fonctionnalités d’aperçu suivantes sont disponibles le 3 février 2020 :

- **Fonctionnalités d’aperçu de congé et d’absence** - Pour plus d’informations, voir [Fonctionnalités d’aperçu de congé et absence](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Fonction d’aperçu de la gestion des avantages** - Pour plus d’informations, y compris les problèmes connus, voir [Aperçu de la gestion des avantages](hr-benefits-management-overview.md).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)