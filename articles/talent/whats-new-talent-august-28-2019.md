---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (27 août 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 8/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-08-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1f19049b362070e2573db769bf7070ace0028406
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3005938"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-august-27-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent (27 août 2019)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2447. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Les fonctions d'aperçu sont uniquement activées dans les instances de bac à sable

Lorsque vous provisionnez une nouvelle instance de Talent, vous pouvez indiquer si le type d'instance est Production ou Bac à sable. Les instances du type Bac à sable permettent de tester les nouvelles fonctions en avant-première. Toutes les instances de Talent existantes seront mises à jour avec le type d'instance Production. Si vous souhaitez que l'une de vos instances existantes soit mise à jour avec le type d'instance Bac à sable (sandbox), contactez le Support pour initier la demande de modification.

Pour plus d'informations sur la manière dont les modifications sont publiées, voir [Mettre en service Talent](./provisioning-talent.md).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Afficher les informations étendues des performances dans la gestion en libre service

Une nouvelle option permet aux responsables d'afficher les performances des états directs et de leurs états étendus. Actuellement, les chefs hiérarchiques peuvent affecter et mettre à jour les objectifs de performances et publier de nouvelles révisions. En outre, les responsables directs et leurs employés peuvent gérer et tenir à jour les journaux de performances pour garantir que le processus d'examen des performances est fluide. Lorsque cette modification est mise en œuvre, les responsables peuvent afficher et tenir à jour les informations relatives aux performances pour leurs états étendus en plus de leurs états directs.

### <a name="deleting-legal-entities-isnt-allowed-if-employees-exist-within-the-company-339849"></a>La suppression d'entités juridiques n'est pas autorisée si des employés existent dans la société (339849)

Avec cette modification, vous ne pouvez pas supprimer des sociétés si des employés et d'autres données associées existent pour l'entité juridique.

### <a name="compensation-management-business-intelligence-analytics-dont-match-on-the-compensation-workspace-322493"></a>Les analyses Business Intelligence de gestion des rémunérations ne correspondent pas à l'espace de travail de rémunération (322493)

Dans cette version, les analyses de rémunération ont été ajustées pour refléter avec précision les régimes affectés aux employés.

### <a name="workflow-placeholder-company-displays-dat-when-hiring-employees-through-workflow-343905"></a>L'espace réservé %company% affiche DAT lorsque les employés sont recrutés via le workflow (343905)

Avec cette version, l'espace réservé à la société affiche l'entité juridique associée à l'emploi du nouvel employé.

### <a name="the-cdsjobposition-entity-displays-an-error-when-valid-to-date-is-set-349387"></a>L'entité CDSJobPosition affiche une erreur lorsque la date de fin de validité est définie (349387)

Dans cette version, les sources de données **Détails du poste** et **Durée du poste** de l'entité **CDSJobPosition** autorisent les modifications de Common Data Service dans les champs **Date d'effet**. 

### <a name="for-employee-termination-the-last-day-worked-is-populated-on-assignment-end-date-332496"></a>Pour la résiliation du contrat d'un employé, le dernier jour de travail est renseigné sur la date de fin de l'affectation (332496)

Cette modification définit maintenant par défaut la **Date de fin de l'affectation** sur la **Date de fin de l'emploi**. Vous pouvez modifier ces valeurs par défaut lors de la saisie de données.

### <a name="legal-entities-arent-limited-with-hire-338871"></a>Les entités juridiques ne sont pas limitées par le processus de recrutement (338871)
 
Cette modification restreint le processus de recrutement en affichant uniquement les entités juridiques auxquelles l'utilisateur a accès.  

## <a name="in-preview"></a>En mode aperçu

### <a name="streamlined-employee-entry-and-navigation"></a>Navigation et entrée d'employé simplifiées

Cette fonctionnalité est désormais disponible dans les environnements de bac à sable et d'évaluation. Pour activer cette fonctionnalité, naviguez jusqu'à **Administration du système > Liens > Paramétrage > Paramètres système > Fonctionnalités en version préliminaire**. Sélectionnez **Formulaire Collaborateur et navigation améliorés**. Ces modifications sont activées pour tous les utilisateurs. Vous pouvez désactiver cette option à tout moment.

Pour plus d'informations, voir [Navigation et entrée d'employé simplifiées](./streamlined-employee-entry.md).

## <a name="coming-soon"></a>Prochainement

### <a name="platform-update-29"></a>Update 29 de la plateforme

Pour des informations complémentaires sur Platform Update 29, voir [Fonctionnalités en version préliminaire dans Dynamics 365 for Finance and Operations Platform Update 29 (octobre 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).
