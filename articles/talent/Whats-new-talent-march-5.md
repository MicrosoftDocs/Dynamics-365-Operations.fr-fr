---
title: Nouveautés ou modifications dans Dynamics 365 Talent (5 mars 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
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
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 855eafaca88d180997cf5a68c7f0fe975c177f88
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898917"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-5-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (5 mars 2019)

Cette rubrique décrit les fonctionnalités inédites ou ayant fait l'objet de modifications dans Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

### <a name="extending-option-sets-in-attract"></a>Extension des ensembles d'options dans Attract

Dans Attract, plusieurs champs sont des ensembles d'options dans Common Data Service. De nouvelles fonctionnalités ont été introduites pour étendre les ensembles d'options, en commençant par le champ du motif de **Rejet**, le champ **Type d'emploi** et le champ **Type d'ancienneté**.

> [!IMPORTANT]
> La fonctionnalité de publication d'annonce sur LinkedIn exige d'utiliser les champs **Type d'emploi** et **Type d'ancienneté** sur la page **Détails du poste**. Les valeurs par défaut dans ces champs sont compatibles avec LinkedIn et s'affichent lors de la publication de l'offre d'emploi. Si vous publiez des offres d'emploi sur LinkedIn et si vous modifiez les valeurs d'ensembles d'options existantes pour ces champs, l'offre d'emploi est publiée, mais LinkedIn n'affiche pas les valeurs **Type d'emploi** et **Type d'ancienneté**.

## <a name="changes-in-onboarding"></a>Modifications apportées à Onboard

### <a name="private-preview-for-onboard-teams"></a>Aperçu privé pour les équipes Onboard
Vous pouvez désormais facilement partager et collaborer sur des modèles au sein de votre organisation. Pour en savoir plus, voir [Partager les bonnes pratiques au sein de votre organisation à l'aide des équipes Onboard](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).

### <a name="private-preview-for-assignee-placeholders"></a>Aperçu privé pour les espaces réservés des destinataires
Vous pouvez enrichir vos modèles en attribuant des activités à des rôles plutôt qu'à des individus. Les rôles sont ensuite attribués aux individus lors de la création du guide. Pour en savoir plus, voir [Rationaliser l'administration du guide en attribuant des activités aux rôles](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR
**Version 8.1.2178**

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a>Configurer le workflow pour approuver automatiquement ou suivre le workflow lorsque les ressources humaines ou un responsable hiérarchique envoie ou met à jour des demandes de congés
De nouvelles conditions de workflow ont été ajoutées pour autoriser les demandes de congés afin qu'elles soient validées automatiquement si envoyées par un responsable de l'employé en question ou par les ressources humaines. Une façon d'obtenir cette validation automatique sur un workflow consiste à activer une action automatique sur l'approbation du workflow.

Parmi les conditions ajoutées figurent :

- Soumis par - Utilisée pour évaluer l'identifiant d'utilisateur système de l'utilisateur qui a envoyé la demande au workflow.
- Envoyé au nom de - Permet d'évaluer si la demande de congés a été soumise au nom de l'employé associé à la demande.
- Soumis par les ressources humaines - Utilisée pour évaluer si l'utilisateur système qui a envoyé la demande au workflow dispose d'un rôle Ressources humaines.
- Soumis par le responsable - Permet d'évaluer si l'utilisateur qui a soumis la demande de congés au workflow est un supérieur hiérarchique de l'employé associé à la requête.

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a>Activer la rémunération fixe des employés à disposition pour des futures affectations de poste
Généralement, les employés qui rejoignent une organisation ont une date de début à venir. Cette modification vous permet de définir la rémunération fixe pour les employés ayant des affectations de poste ultérieures.

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a>Champs Poste/Paie non renseignés lors de la modification du poste
Avec cette modification, lors de la demande de modifications des postes existants, les champs de paie sont définis désormais par défaut sur les valeurs actuelles.

### <a name="other-miscellaneous-bug-fixes"></a>Autres correctifs de bogues divers
Cette version comprend d'autres correctifs de bogues mineurs.

### <a name="upgrade-to-common-data-service"></a>Effectuez une mise à niveau vers Common Data Service.
Les dates butoirs pour la mise à niveau vers Common Data Service arrivent à grands pas. Connectez-vous au centre d'administration de Power Apps pour définir si votre base de données doit être mise à niveau. Pour en savoir plus sur les dates butoirs et les étapes indispensables pour la mise à niveau, voir [Mise à niveau vers Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="coming-soon"></a>Prochainement

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Sécurité avancée de la rémunération (fixe et variable)
Nombreuses sont les organisations où les responsables des bénéfices et de la rémunération ne peuvent accéder qu'à certains enregistrements de rémunération, comme les enregistrements relatifs aux cadres ou aux employés régionaux. Cette modification permet aux ressources humaines (RH) de gérer et de tenir à jour les plans de rémunération pour différentes populations d'employés au sein de l'organisation. Les plans fixes et variables peuvent être attribués à des rôles de sécurité, qui déterminent l'accès aux plans et aux données des employés par rapport aux plans, comme les enregistrements propres aux salaires ou aux primes. Seuls les rôles qui ont l'accès spécifié sont en mesure de traiter la rémunération pour ces employés.

###  <a name="platform-update-24-for-finance-and-operations"></a>Platform update 24 pour Finance and Operations
Pour en savoir plus sur Platform Update 24 pour Finance and Operations, voir [Nouveautés ou modifications dans Finance and Operations, Platform Update 24 (mars 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).
