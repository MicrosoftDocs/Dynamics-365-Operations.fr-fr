---
title: Nouveautés et modifications dans Dynamics 365 Human Resources (13 avril 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 13 avril 2020.
author: andreabichsel
ms.date: 04/13/2020
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
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 93873707703ce7148c353735ce1abce795796a5e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892007"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a>Nouveautés et modifications dans Dynamics 365 Human Resources (13 avril 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3136. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="new-production-release-cadence"></a>Nouvelle cadence de sortie de production

Avec cette publication hebdomadaire, le rythme de publication des versions pour Human Resources passe d’une mise à jour hebdomadaire à une mise à jour toutes les deux semaines. Pour garantir l’alignement avec les pratiques de déploiement sécurisées et maintenir des normes élevées de stabilité et de fiabilité du service, le processus de déploiement des mises à jour de service dans toutes les régions se déroulera sur deux semaines. Des tests et des moniteurs supplémentaires seront en place pour vérifier le succès du déploiement à chaque étape du processus. Pour plus d’informations sur la cadence de publication, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a>Le champ de précision d’arrondi n’est pas modifiable après avoir spécifié un type d’arrondi (435616)

Avec ce changement, le champ **Précision d’arrondi** est désormais disponible après la mise à jour du champ **Type d’arrondi**.

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a>Impossible de modifier la date de fin d’inscription au congé lorsque le plan de congé ne comporte pas de périodes de régularisation (413628)

Vous pouvez maintenant modifier la date de fin d’inscription sans obtenir l’erreur « La base de la date de régularisation du champ doit être renseignée ».

## <a name="employment-entity-doesnt-sync-to-dataverse-430834"></a>L’entité Emploi ne se synchronise pas avec Dataverse (430834)

Cette modification corrige un problème impliquant que les données relatives à l’emploi n’étaient pas synchronisées avec Dataverse après l’ajout de dimensions financières. 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a>Supprimer la multi-parentalité pour l’entité Intervalle de temps du calendrier de travail (431775)

Cette modification supprime la multi-parentalité pour l’entité **Intervalle de temps du calendrier de travail**.

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a>Le filtre avec la fonction CAST ne fonctionne pas sur l’entité Affectation du collaborateur au poste de l’appel OData (431699)

Cette mise à jour inclut une modification pour autoriser le filtre avec la fonction CAST dans OData pour l’entité **Affectation du collaborateur au poste**.

## <a name="in-preview"></a>En version préliminaire

## <a name="leave-suspension"></a>Suspension des congés

Vous pouvez suspendre les congés et les absences d’un employé dans Human Resources. La suspension des congés arrête les régularisations de congés pour les types de congé sélectionnés. Si la suspension survient après le traitement d’une régularisation, la suspension du congé crée un ajustement au prorata du solde des congés de l’employé. Pour plus d’informations, voir la rubrique [Suspension des congés](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Règles de report

Vous pouvez spécifier un type de congé de report pour les soldes de report où les ajustements de report sont transférés. Par exemple, si un employé reporte 10 jours, vous pouvez sélectionner un type de congé différent pour ces 10 jours. Pour plus d’informations, voir [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Problèmes connus

## <a name="employment-details-entity"></a>Entité Détails de l’emploi

L’entité **Détails de l’emploi** a été mise à jour avec les champs suivants :

- **PayFrequency**
- **ID catégorie d’emploi**
- **Type d’emploi**
- **ID EmploymentType**
- **Statut d’emploi à avantages**

Les données de configuration de ces champs reposent sur l’activation de la gestion des avantages dans l’espace de travail **Gestion des fonctionnalités**. Ne complétez pas ces champs ou ne les mettez pas à jour dans l’entité **Détails de l’emploi**, car cela entraînera des erreurs lors de l’importation.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>L’aperçu SharePoint ne fonctionne pas dans certains environnements

Si l’aperçu du document pour les documents stockés dans SharePoint ne fonctionne pas, essayez la procédure suivante :

1. Vérifiez que le compte utilisateur Admin possède un e-mail associé à l’enregistrement utilisateur. Vous pouvez afficher ces informations sur la page **Utilisateur**. Si le courrier électronique n’est pas configuré, vous devez ajouter le courrier électronique et le fournisseur avec le complément OData Excel. Par défaut, l’adresse e-mail n’est pas présente dans la conception Excel. Vous devrez modifier la conception d’Excel, ajouter tous les champs, appliquer et actualiser. Une fois ces étapes exécutées, vous pouvez mettre à jour le compte administrateur.

2. Une fois que le compte administrateur a un compte de messagerie associé, connectez-vous à Human Resources avec les informations d’identification d’administrateur.

3. Accédez à une pièce jointe dans SharePoint pour lancer l’aperçu du document.

4. Connectez-vous avec un autre compte d’utilisateur qui a accès aux pièces jointes et vérifiez que l’aperçu fonctionne comme prévu.

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]