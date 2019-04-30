---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (23 janvier 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
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
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f27698c257301f52e5c77eaa8a04ca13a0315825
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "859612"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-23-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (23 janvier 2019)

[!include [banner](includes/banner.md)]

**Version 8.1.2121**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.

## <a name="changes"></a>Modifications

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a>Importation de la rémunération fixe des employés ne fonctionnant pas lors de la création de nouveaux enregistrements de rémunération fixe
Une modification a été effectuée à l'entité de rémunération fixe des employés pour récupérer un niveau de rémunération lors de l'importation. Avant cette version, un message a été affiché, indiquant que le niveau était requis.

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a>Supprimer le champ de solde minimum depuis la boîte de dialogue de la demande de congés
Le champ **Solde minimum** a été supprimé de la boîte de dialogue **Demande de congés**. Cette modification concerne toutes les zones où des congés peuvent être demandés.

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a>Mise à niveau des données pour les niveaux de rémunération ne se mettant pas à jour dans tous les scénarios
Une modification a été apportée pour mettre à jour le niveau de rémunération sur les plans de rémunération fixe. Cette modification renseignera le niveau de rémunération sur les régimes fixes pour la tâche attribuée à l'employé.

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a>Les informations relatives aux salaires sur la page Gérer les modifications sont disponibles uniquement lorsque l'utilisateur est connecté comme administrateur système.
Cette modification permet aux employés avec un rôle Administrateur des salaires d'accéder aux informations relatives aux salaires sur la page **Calendrier des modifications > Gérer les modifications** pour le poste.

### <a name="job-fields-default-to-positions"></a>Champs de tâche par défaut à des postes
Lorsque vous changez la tâche sur un poste, les champs de tâche seront par défaut définis sur le poste. Un message d'alerte apparaîtra, vous donnant la possibilité d'accepter les valeurs par défaut ou de conserver les valeurs existantes pour ces champs.

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a>La période de probation et le calendrier ne s'affichent pas pour les futurs employés.
Avec cette modification, les champs **Période d'essai** et **Calendrier** ont été ajoutés à la page **Gestion des modifications** pour autoriser une saisie de données pour les futurs et les anciens employés.

### <a name="platform-update-23"></a>Update 23 de la plateforme
Des correctifs de bogue mineur ont été inclus dans le cadre de Platform Update 23. Pour en savoir plus, voir [Nouveautés ou modifications dans Dynamics 365 for Finance and Operations Platform Update 23 (janvier 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23). 
