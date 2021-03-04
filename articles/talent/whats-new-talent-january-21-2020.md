---
title: Nouveautés ou modifications dans Dynamics 365 Talent (21 janvier 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e9dee64e94c904cfe07c6a7766f6a60b1d60a2db
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528120"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-21-2020"></a>Nouveautés ou modifications dans Dynamics 365 Talent (21 janvier 2020)

[!include [banner](includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract. Nous avons ajouté des fonctionnalités à l'application Attract suite à notre récente annonce, [Construire des équipes plus performantes avec Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources/).

### <a name="download-environment-data"></a>Télécharger les données d'environnement

Les administrateurs peuvent télécharger les données de leur environnement. Les données sont exportées au format JSON standard et toutes les tâches, tous les candidats et la configuration sont exportés dans un fichier zip. Pour plus d'informations, voir [Exporter les données à partir d'Attract et Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

### <a name="restricting-access-to-environments-for-non-admin-users"></a>Restriction de l'accès aux environnements pour les utilisateurs non administrateurs

Les administrateurs peuvent désormais restreindre l'accès à l'environnement pour les utilisateurs non administrateurs. Cette action ne peut pas être annulée. Pour plus d'informations, voir [Restriction de l'accès à Attract](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data#restrict-access-to-attract).

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

### <a name="exporting-onboarding-guides"></a>Exportation des guides d'intégration

Les utilisateurs peuvent désormais exporter tous leurs guides et modèles d'intégration au format Word. Pour plus d'informations, voir [Exporter les données à partir d'Attract et Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2726. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="most-recent-annual-compensation-field-in-verify-employment-form-isnt-consistent-392092"></a>Le champ de rémunération annuelle le plus récent dans le formulaire de vérification d'emploi n'est pas cohérent (392092)

Cette version inclut une modification qui affichera la dernière devise en fonction du sélecteur de société dans le formulaire **Vérifier l'emploi**.

### <a name="known-as-field-added-to-the-feedback-recipient-lookup-407789"></a>Connu en tant que champ ajouté à la recherche de destinataire de commentaires (407789)

Lors de la fourniture de commentaires en matière de performances, la recherche de collaborateurs n'a pas fourni suffisamment d'informations pour déterminer si les commentaires sont envoyés à la bonne personne. Nous avons ajouté une colonne **Connu sous** pour faciliter l'identification du nom unique de l'employé.
 
### <a name="hcmworkerpayrollinfo-record-is-created-without-an-association-to-a-worker-394526"></a>L'enregistrement HcmWorkerPayrollInfo est créé sans association avec un collaborateur (394526)

Cette version inclut une modification pour ne pas écrire les enregistrements HCMWorkerPayrollInfo sans référence à un employé.

### <a name="able-to-edit-department-when-navigating-from-position-hierarchy-341001"></a>Capable de modifier le service lors de la navigation à partir de la hiérarchie des postes (341001)

Lorsque la sécurité est configurée pour refuser l'accès aux services d'édition, l'édition est désactivée lors de la navigation vers le formulaire **Services** dans tous les scénarios.

## <a name="coming-soon"></a>Prochainement

Une nouvelle solution Common Data Service sera bientôt disponible avec les modifications suivantes :

| Description | Monnaie |
| --- | --- |
| Modifications de l’entité **Poste** | <ul><li>**Région de rémunération** ajoutée</li><li>**Dimensions financières** ajoutées</li></ul> |
| Modifications de l’entité **Collaborateur** | <ul><li>**Séquence de noms** ajoutée</li><li>**Télétravaille** ajouté</li><li>**Langue** ajoutée</li><li>**Date d’ancienneté** ajoutée</li><li>**Date anniversaire** ajoutée</li><li>**Date d’embauche d’origine** ajoutée</li></ul> |
| Modifications de l’entité **Emploi** | <ul><li>**Dimensions financières** ajoutées</li><li>**Motif de la fin du contrat** ajouté</li><li>**Date de résiliation** renommée à partir de **Date de transition**</li><li>**Période d’essai** ajoutée</li></ul> |
| Modifications de l’entité **Adresse du collaborateur** | <ul><li>**Nom de la rue** ajouté</li><li>**Ligne d’adresse 1**, **Ligne d’adresse 2** et **Ligne d’adresse 3** marquées pour suppression</li></ul> |
| Nouvelles entités de configuration de la rémunération variable | <ul><li>**Type de régime variable de rémunération**</li><li>**Régime variable de rémunération**</li><li>**Règles d’acquisition**</li><li>**Niveau de régime variable de rémunération**</li></ul> |
| Nouvelle entité **Emploi du calendrier du collaborateur** | <ul><li>**Entité de calendrier de travail** ajoutée</li></ul> |


[!INCLUDE[footer-include](../includes/footer-banner.md)]