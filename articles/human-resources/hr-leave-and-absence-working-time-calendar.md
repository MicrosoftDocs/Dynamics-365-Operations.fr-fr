---
title: Création d’un calendrier du temps de travail
description: Définissez un calendrier du temps de travail, des jours fériés et du temps libre dans Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ea55ad7f86e0c7d5ccc6e6de0af475299b05639
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052431"
---
# <a name="create-a-working-time-calendar"></a>Création d’un calendrier du temps de travail

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Un calendrier du temps de travail Dynamics 365 Human Resources affiche les jours et les heures de travail des employés dans votre organisation. Lorsqu’un employé soumet une demande de congé, il n’a pas à se soucier des congés et des fermetures.

Pour rationaliser les demandes de congés, configurez ces éléments pour votre organisation :

- Calendrier du temps de travail
- Congés et fermetures
- Temps libre

Vous pouvez ajouter les deux derniers éléments pendant que vous configurez un calendrier du temps de travail. Vous pouvez également les configurer ou les mettre à jour séparément.

## <a name="set-up-a-working-time-calendar"></a>Paramétrage d’un calendrier de temps de travail

Configurez au moins un calendrier de temps de travail qui affiche vos jours et heures d’ouverture. Si vous avez des emplacements dans plusieurs pays et régions, vous pouvez configurer un calendrier de temps de travail pour chaque zone.

1. Dans la page **Administration d’organisation**, sélectionnez **Calendriers**.

2. Sélectionnez **Nouveau** et entrez un nom et une description pour votre calendrier.

3. Sous **Options de génération**, sélectionnez les jours ouvrables de votre organisation et saisissez les heures de travail. 
   - Pour ajouter un jour férié ou une fermeture, sélectionnez le bouton **Ajouter** à côté de **Congés et fermetures**.
   - Pour ajouter du temps libre, comme des déjeuners ou des pauses, sélectionnez **Ajouter** sous **TEMPS LIBRE** et entrez le nom et la plage horaire.

4. Sous **Jours**, sélectionnez **Générer** pour générer les jours dans votre calendrier. Saisissez la plage de dates de votre calendrier, puis sélectionnez **Générer des jours**.

5. Pour ajouter des plannings de travail, sous **Planning de travail**, sélectionnez **Ajouter**, puis entrez les heures de chaque planning de travail.

## <a name="configure-holidays-and-closures"></a>Configuration des congés et fermetures

Vous pouvez ajouter ou modifier des congés et des fermetures séparément d’un calendrier de temps de travail.

1. Dans la page **Administration d’organisation**, sélectionnez **Congés et fermetures**.

2. Sélectionnez **Nouveau** et entrez un nom et une date de congés ou de fermeture.

## <a name="configure-non-work-time"></a>Configuration du temps libre

Vous pouvez ajouter ou modifier du temps libre séparément d’un calendrier de temps de travail.

1. Dans la page **Administration d’organisation**, sélectionnez **Temps libre**.

2. Sélectionnez **Nouveau** et entrez le nom et la plage de temps pour le temps libre.

Si vous avez activé la fonction d’aperçu des corrections des jours fériés pour les congés et absences, Human Resources utilise les dates de congés et de fermeture pour déterminer le nombre de jours à ajuster pour les employés inscrits au calendrier.

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)
- [Configuration des types de congé et d’absence](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]