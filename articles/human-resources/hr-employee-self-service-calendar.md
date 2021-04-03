---
title: Créer un calendrier d’équipe
description: Affichezr et créez des calendriers d’équipe dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ca7ccb7959eab6f8a9bdc0292e28c3126cb0364c
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466446"
---
# <a name="view-team-and-company-calendars"></a>Afficher les calendriers des équipes et de la société

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez afficher les calendriers des équipes et des entreprises dans Dynamics 365 Human Resources. Les calendriers d’équipe affichent uniquement les subordonnés directs, tels que définis dans la hiérarchie des lignes.

## <a name="view-your-team-calendar-as-an-employee"></a>Afficher votre calendrier d’équipe en tant qu’employé

1. Dans l’espace de travail **Libre-service employé**, sélectionnez **Calendrier des absences de l’équipe** sous **Résumé**.

## <a name="view-your-team-calendar-as-a-manager"></a>Afficher votre calendrier d’équipe en tant que responsable

1. Dans l’espace de travail **Libre-service employé**, sélectionnez **Mon équipe**.

2. Sélectionnez **Congé et absence**, puis sélectionnez **Afficher le calendrier des absences du responsable**.

Les responsables peuvent également accéder au calendrier de l’équipe à partir de **Demandes de congés en attente pour mon équipe**, **Congés approuvés** et **Demandes de congés**. 

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

>[!IMPORTANT]
>L’affichage des congés et des absences dans les entreprises est actuellement en version préliminaire. Vous devrez l’activer dans votre environnement de **bac à sable**. Pour plus d’informations sur l’activation des fonctionnalités d’évaluation, voir [Gérer les fonctionnalités](hr-admin-manage-features.md).<br><br>
>Ensuite, vous devez activer la fonctionnalité dans **Paramètres partagés des ressources humaines** pour afficher le filtre d’entité juridique dans les calendriers. Pour plus d’informations, voir [Configurer les paramètres de congé et d’absence](hr-leave-and-absence-parameters.md).<br><br>
>Vous pouvez filtrer le calendrier par entité juridique. Si vous voulez voir tous les employés quelle que soit l’entité juridique, décochez la case de filtre et sélectionnez Entrée. 

Pour plus d’informations sur les paramètres du calendrier, voir [Configurer les paramètres du calendrier](hr-leave-and-absence-parameters.md?configure-calendar-parameters).



[!INCLUDE[footer-include](../includes/footer-banner.md)]