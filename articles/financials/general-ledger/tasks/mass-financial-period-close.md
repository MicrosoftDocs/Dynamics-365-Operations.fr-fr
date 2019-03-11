---
title: Secteur de clôture de période comptable
description: Cette procédure indique comment mettre une période en attente ou clôturer définitivement une période ou plusieurs entités juridiques simultanément.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2988b7ab0837cc9a3e4f1c4eaf3fe6e219fa721
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "311379"
---
# <a name="mass-financial-period-close"></a>Secteur de clôture de période comptable

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment mettre une période en attente ou clôturer définitivement une période ou plusieurs entités juridiques simultanément. En outre, la tâche indique comment limiter la validation de groupe d'utilisateurs à des modules spécifiques.

1. Accédez à Comptabilité > Clôturer la période > Calendriers de comptabilité.
    * Notez que la liste des entités juridiques affichées dépend du calendrier fiscal sélectionné dans la page. Seules les entités juridiques qui utilisent le calendrier fiscal sélectionné sont affichées.  
2. Cliquez sur Modifier.
3. Sélectionnez la période dont vous souhaitez modifier le statut.
4. Sélectionnez les entités juridiques dont vous souhaitez mettre à jour le statut.
    * Vous pouvez sélectionner rapidement toutes les entités juridiques en activant la case à cocher dans la partie supérieure gauche de la grille.  
5. Sélectionnez Mettre à jour l'accès au module pour définir l'accès de validation à un module sélectionné.
    * Le statut du module peut également être mis à jour un par un en modifiant les enregistrements de la grille. Le bouton est utile lorsque vous souhaitez mettre à jour rapidement plusieurs enregistrements d'entité juridique.  
6. Dans le champ Module d'application, sélectionnez le module dont vous souhaitez mettre à jour le statut. Cliquez sur Sélectionner.
7. Dans le champ Niveau d'accès, sélectionnez Tous, Aucun ou un groupe d'utilisateurs spécifique. Cliquez sur Sélectionner.
    * Tout indique que tous les utilisateurs ayant un accès en modification au module peuvent valider si la période est En cours. Aucun indique que les utilisateurs ne peuvent pas effectuer une validation dans le module si la période est En cours. Un groupe d'utilisateurs spécifique indique que seuls les utilisateurs du groupe peuvent effectuer une validation dans le module si la période est En cours.  
8. Cliquez sur Mise à jour.
9. Sélectionnez une autre période pour mettre à jour le statut.
10. Sélectionnez les entités juridiques dont vous souhaitez mettre à jour le statut de la période.
11. Sélectionnez Mettre à jour le statut de la période et définissez le statut sur En attente, En cours ou Clôturé définitivement.
    * En cours indique la période pendant laquelle la validation est possible, pour autant que l'utilisateur ait accès. En attente signifie que la période ne peut faire l'objet d'aucune validation, mais elle peut être rouverte. Clôturé définitivement signifie que la période est clôturée et ne peut jamais être ouverte. Les ajustements ne peuvent pas être validés. Il n'est pas recommandé de définir une période comme définitivement clôturée avant que tous les ajustements et audits soient terminés.  
12. Cliquez sur Mise à jour.

