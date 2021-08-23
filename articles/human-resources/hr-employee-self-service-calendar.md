---
title: Créer un calendrier d’équipe
description: Affichezr et créez des calendriers d’équipe dans Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ccbf12d4dcc75e22fc62c356653a91b9a8a8d1761ccefb18c93e65f343250830
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744224"
---
# <a name="view-team-and-company-calendars"></a>Afficher les calendriers des équipes et de la société

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez afficher les calendriers des équipes et des entreprises dans Dynamics 365 Human Resources. Les calendriers d’équipe affichent uniquement les subordonnés directs, tels que définis dans la hiérarchie des lignes.

## <a name="view-your-team-calendar-as-an-employee"></a>Afficher votre calendrier d’équipe en tant qu’employé

- Dans l’espace de travail **Libre service employé**, sélectionnez **Calendrier des absences de l’équipe** sous **Résumé**.

## <a name="view-your-team-calendar-as-a-manager"></a>Afficher votre calendrier d’équipe en tant que responsable

1. Dans l’espace de travail **Libre service employé**, sélectionnez **Mon équipe**.

2. Sélectionnez **Congé et absence**, puis sélectionnez **Afficher le calendrier des absences du responsable**.

Les responsables peuvent également accéder au calendrier de l’équipe à partir de **Demandes de congés en attente pour mon équipe**, **Congés approuvés** et **Demandes de congés**. 

## <a name="view-your-absence-manager-calendar-as-the-absence-manager"></a>Afficher votre calendrier de gestionnaire des absences en tant que gestionnaire des absences

> [!NOTE]
> Pour afficher le calendrier du gestionnaire des absences, vous devez d'abord activer la fonctionnalité **(Version préliminaire) Gestionnaire des absences pour gérer les congés** dans la gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités d’évaluation, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

Les utilisateurs ayant le rôle de gestionnaire des absences peuvent afficher les demandes de congés dans leur calendrier. Procédez comme suit pour accéder au calendrier des congés.

1. Dans l’espace de travail **Libre service employé**, sélectionnez **Gestion des congés**, puis **Calendrier du gestionnaire des absences**.

2. Dans le champ **Date**, saisissez les dates souhaitées.

3. Mettez à jour les options d'affichage si nécessaire.

Le calendrier du gestionnaire des absences affiche tous les enregistrements des employés qui relèvent du gestionnaire des absences dans la hiérarchie des congés.

## <a name="view-a-company-calendar"></a>Afficher un calendrier d’entreprise

Les personnes qui travaillent aux ressources humaines peuvent afficher les calendriers de l’entreprise. Les calendriers de l’entreprise affichent tous les employés. Par défaut, le calendrier affiche la date du jour plus 28 jours, mais vous pouvez modifier la plage de dates. Vous pouvez également filtrer le calendrier par **Nom**, **Numéro personnel**, et **Type de congé**.

1. Dans l’espace de travail **Congé et absence**, sélectionnez **Liens**.

2. Sélectionnez **Calendrier des congés et des absences**.

Les rôles des ressources humaines peuvent également accéder au calendrier de l’entreprise à partir de **Demandes de congé et d’absence**, **Congés approuvés** et **Demandes de congés**. 

Les calendriers contiennent désormais des filtres et des options supplémentaires. Tous les calendriers incluent des options d’affichage pour :

- Les demandes approuvées
- Les demandes en attente
- Les employés avec des demandes de congé
- Les employés sans demandes de congé
- Les anniversaires des employés
- Les demandes de congés 
- Demandes d’absence

La configuration du calendrier dans les paramètres de congé et d’absence détermine les options d’affichage disponibles.

Vous pouvez également filtrer les calendriers par responsable ou service. L’affectation du poste principal détermine les employés affichés lorsque ces filtres sont définis. 

> [!IMPORTANT]
> Vous pouvez activer la fonctionnalité **Vue des congés intersociétés** dans la Gestion des fonctionnalités. Ensuite, vous devez activer la fonctionnalité dans la page **Paramètres partagés des ressources humaines** pour afficher le filtre d’entité juridique dans les calendriers. Pour plus d’informations, voir [Configurer les paramètres de congé et d’absence](hr-leave-and-absence-parameters.md).
> 
> Vous pouvez filtrer le calendrier par entité juridique. Pour afficher tous les employés, quelle que soit l’entité juridique, décochez la case de filtre et sélectionnez **Entrée**. 

Pour plus d’informations sur les paramètres du calendrier, voir [Configurer les paramètres du calendrier](hr-leave-and-absence-parameters.md?configure-calendar-parameters).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
