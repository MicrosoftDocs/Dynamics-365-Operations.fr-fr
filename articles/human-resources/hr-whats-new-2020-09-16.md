---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (16 septembre 2020)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 16 septembre 2020.
author: jcart1106
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cd3424db6bf918b4041f6d12e5d840bc3a8dfef7
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061571"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (16 septembre 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.3557. Les numéros entre parenthèses en regard de certaines fonctionnalités se rapportent aux numéros de support Lifecycle Services (LCS) pour référence.

## <a name="included-in-this-release"></a>Incluses dans cette version

-  [Vues enregistrées – disponibilité générale](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br>- Pour plus d’informations, voir [Vues enregistrées](../fin-ops-core/fin-ops/get-started/saved-views.md). 

- L’écran **Actions liées aux postes** a une grille de dimensions mise à jour et une nouvelle boîte de dialogue (469495).

- Si vous définissez **Restreindre l’accès aux informations sur les collaborateurs** sur Oui dans **Accès avancé** dans **Paramètres partagés Human Resources**, les écrans des avantages n’indiquent plus que les collaborateurs appropriés (393384).

- Nouvelles options de génération de calendrier dans l’entité **WorkCalendar** (477055) :<br>- Heure de fin par défaut<br>- Heure de démarrage par défaut<br>- Est le vendredi jour ouvrable<br>- Est le lundi jour ouvrable<br>- Est le samedi jour ouvrable<br>- Est le dimanche jour ouvrable<br>- Est le jeudi jour ouvrable<br>- Est le mardi jour ouvrable<br>- Est le vendredi jour ouvrable<br>- ID Congés du calendrier de travail

- L’entité **LeaveBankTransactionV1** inclut désormais le code motif (477823).

- Vous pouvez maintenant sauvegarder les enregistrements de tâches (492923).

- Les données sont maintenant publiées avec succès depuis **HCMWorkerContactEntity** (427620).

- le raccourci **Rémunération** s’affiche maintenant pour le type de travailleur Fournisseur dans l’écran **Actions de collaborateur** (482494).

- Les champs **Niveau** et **Plan** sont désormais obligatoires si vous définissez **Rémunération fixe**. Un message d’erreur s’affiche si vous laissez ces champs vides (482497).

- Le champ **Type de plan** dans **Avantages** est maintenant une liste déroulante (488768).

- Les administrateurs système reçoivent désormais une notification si un champ personnalisé est supprimé de Human Resources (481408).

- Pendant le processus de licenciement des employés, Human Resources se comporte comme prévu et ne modifie pas l’entreprise sélectionnée après avoir semblé se verrouiller (479877). 

- Les managers ne peuvent plus ajouter de colonne numérique via la personnalisation (485317).

- Les managers ne peuvent plus supprimer le filtre de plage de données des numéros d’identification arrivant à expiration (485321).

- Quand le champ **Supérieur hiérarchique** est vide, les détails du poste s’affichent toujours lorsque vous survolez le poste (433328).

- Les employés peuvent désormais afficher les informations relatives au régime de prestations dans le libre-service des employés (481676).

- Les employés peuvent désormais voir tous les cours enregistrés (429048).

- Vous pouvez désormais restreindre les options d’affichage pour la page **Certificats professionnels**. Vous pouvez restreindre les options d’affichage à l’entité juridique actuelle, par statut de collaborateur et par type de collaborateur (451501). 


## <a name="in-preview"></a>En version préliminaire

### <a name="human-resources-app-in-teams"></a>Application Human Resources de Teams

Les collaborateurs peuvent consulter et demander des absences dans Microsoft Teams. Ils peuvent interagir avec un bot pour créer des demandes de congé. Pour plus d’informations, voir :

- [Expérience des employés en congé et absence Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) dans la 1ère partie du lancement 2020 de Dynamics 365
- [Application Human Resources dans Teams](./hr-admin-teams-leave-app.md) dans la documentation Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Application Human Resources dans les fonctionnalités d’évaluation Teams
 
-  **Notifications** : Les demandeurs et les approbateurs des demandes de congés seront informés dans l’application Human Resources de Teams. Les approbateurs peuvent approuver ou refuser les demandes de congé. Les demandeurs seront informés si la demande a été approuvée ou refusée. Pour plus d’informations, voir :
   - [Expérience de congé et d’absence des employés dans Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) dans la 2e partie du lancement 2020 de Dynamics 365
   - [Activer les notifications de l’application Human Resources dans Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) dans la documentation Human Resources
   - [Activer ou désactiver les notifications Teams pour les utilisateurs individuels](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) dans la documentation Human Resources
   - [Notifications Teams](./hr-teams-leave-app.md#respond-to-teams-notifications) dans la documentation Human Resources
   - [Afficher le calendrier des congés de votre équipe](./hr-teams-leave-app.md#view-your-teams-leave-calendar) dans la documentation Human Resources
 
- **Calendrier des congés du responsable** : Les responsables peuvent afficher les congés approuvés et en attente pour leurs subordonnés directs dans une vue du calendrier. Cette vue permet de comprendre facilement quand les membres de leur équipe sont absents du travail. Pour plus d’informations, voir :
   - [Expérience de congé et d’absence des employés dans Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) dans la 2e partie du lancement 2020 de Dynamics 365
   - [Afficher le calendrier des congés de votre équipe](./hr-teams-leave-app.md#view-your-teams-leave-calendar) dans la documentation Human Resources

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Option de configuration pour positionner la liste des éléments de travail qui m’ont été assignés (477004)

Une nouvelle option est désormais disponible pour positionner la liste **Éléments de travail qui m’ont été attribués** dans la colonne de droite du tableau de bord. Avec cette modification, tous les éléments de travail et les listes de tâches s’affichent dans la même zone. Activez cette fonctionnalité en activant **Aperçu – Améliorations de l’expérience de workflow** dans la gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités d’évaluation, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

Cette fonctionnalité favorise également les options de workflow qui apparaissent dans les formulaires d’actions du personnel. Les options de workflow apparaissent également au-dessus de l’onglet Action rapide pour un accès rapide. Pour plus d’informations, voir : 

- [Améliorations de l’expérience du workflow de gestion de l’organisation et du personnel](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) dans la 2e partie du lancement2020 de Dynamics 365

![Éléments de travail qui me sont affectés.](./media/hr-workflow-work-items-assigned-to-me.png)

![Accès rapide aux éléments du workflow.](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a>Calendrier des congés et des absences

Cette version comprend des options de calendrier supplémentaires pour les calendriers de congé et d’absence. Pour plus d’informations, voir [Afficher les calendriers des équipes et des sociétés](./hr-employee-self-service-calendar.md).

## <a name="coming-soon"></a>Prochainement

### <a name="checklist-entities-included-in-dataverse"></a>Entités de liste de contrôle incluses dans Dataverse

Les entités de liste de contrôle pour les processus d’intégration, de départ, de transfert et d’entreprise seront bientôt disponibles dans Dataverse.

### <a name="benefits-management-reason-codes"></a>Codes de motif de la gestion des avantages

Les codes de motif de gestion des avantages seront bientôt combinés aux codes de motif existants dans Human Resources. Si vous avez créé des codes raison dans la gestion des avantages de plus de 15 caractères, vous devez modifier le nom du code motif dans le formulaire **Codes motif** de la gestion des avantages sur 15 caractères ou moins. Une fois le nom mis à jour, le code motif apparaîtra sous le formulaire de code motif existant dans la gestion du personnel. Ce changement sera disponible à l’avenir et n’affectera pas les fonctionnalités existantes.

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de la 2e partie du lancement 2019 de Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
