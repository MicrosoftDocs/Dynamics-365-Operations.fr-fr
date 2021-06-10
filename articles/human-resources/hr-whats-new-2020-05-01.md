---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (1 mai 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 1er mai 2020.
author: andreabichsel
ms.date: 05/01/2020
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
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8ceea10b3157fee410e5db6e1d8c9a0366e30e2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6050967"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (1 mai 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3196. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a>Nouvelles entités de gestion des performances disponibles dans Data Management Framework (DMF)

Les entités suivantes sont maintenant disponibles. Si vous ne voyez pas ces entités répertoriées dans la liste des entités, utilisez l’option **Actualiser les entités** dans **Paramètres de l’environnement > Paramètres d’entité > Actualiser la liste d’entités**.

- **Compétence de discussion**
- **Objectifs de discussion**
- **Mesure de la discussion**
- **Rubrique de discussion**
- **Journal des performances**
- **Mesure**
- **Mesure des objectifs**

En outre, **Score total** et **Score moyen** ont été ajoutés à l’entité **Discussion**.

## <a name="increase-length-of-leave-request-comments-275641"></a>Augmenter la longueur des commentaires sur les demandes de congé (275641)

Les commentaires sur les demandes de congés acceptent désormais plus de 100 caractères.

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a>Les commentaires finaux sur les avis n’apparaissent pas lorsque le responsable ou l’employé est connecté à une autre entreprise (431688)

Tous les commentaires apparaîtront désormais lors de la consultation des avis.

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a>Les liens définis par l’utilisateur ne sont pas pris en charge sur le nouveau formulaire Collaborateur (390374)

Les liens définis par l’utilisateur sont désormais activés dans le formulaire **Collaborateur** rationnalisé.

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a>HcmRatingLevelEntity provoque une panne de l’API OData (439476)

Cette modification corrige la panne liée à l’API. Un doublon a provoqué cette erreur.

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

## <a name="known-issues"></a>Problèmes connus

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