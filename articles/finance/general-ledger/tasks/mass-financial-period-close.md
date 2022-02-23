---
title: Secteur de clôture de période comptable
description: Cette rubrique indique comment mettre une période en attente ou clôturer définitivement une période ou plusieurs entités juridiques simultanément.
author: aprilolson
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 598c28c2fb3dd6a13f96df81189b46c4e228da7a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968727"
---
# <a name="mass-financial-period-close"></a>Secteur de clôture de période comptable

[!include [banner](../../includes/banner.md)]

Cette rubrique indique comment mettre une période en attente ou clôturer définitivement une période ou plusieurs entités juridiques simultanément. En outre, la tâche indique comment limiter la validation de groupe d’utilisateurs à des modules spécifiques.

1. Dans le volet de navigation, accédez à **Modules > Comptabilité > Clôture de période > Calendriers de comptabilité**. Notez que la liste des entités juridiques affichées dépend du calendrier fiscal sélectionné dans la page. Seules les entités juridiques qui utilisent le calendrier fiscal sélectionné sont affichées.
2. Sélectionnez **Modifier**.
3. Sélectionnez la période dont vous souhaitez modifier le statut.
4. Sélectionnez les entités juridiques dont vous souhaitez mettre à jour le statut. Vous pouvez sélectionner rapidement toutes les entités juridiques en activant la case à cocher dans la partie supérieure gauche de la grille.  
5. Sélectionnez **Mettre à jour l’accès au module** pour définir l’accès de validation à un module sélectionné. Le statut du module peut également être mis à jour un par un en modifiant les enregistrements de la grille. Le bouton est utile lorsque vous souhaitez mettre à jour rapidement plusieurs enregistrements d’entité juridique.  
6. Dans le champ module **Application**, sélectionnez le module dont vous souhaitez mettre à jour le statut. Cliquez sur **Sélectionner**.
7. Dans le niveau **Accès**, sélectionnez **Tout**, **Aucun** ou un groupe d’utilisateurs spécifique. Cliquez sur **Sélectionner**. Tout indique que tous les utilisateurs ayant un accès en modification au module peuvent valider si la période est En cours. Aucun indique que les utilisateurs ne peuvent pas effectuer une validation dans le module si la période est En cours. Un groupe d’utilisateurs spécifique indique que seuls les utilisateurs du groupe peuvent effectuer une validation dans le module si la période est En cours.  
8. Sélectionnez **Mettre à jour**.
9. Sélectionnez une autre période pour mettre à jour le statut.
10. Sélectionnez les entités juridiques dont vous souhaitez mettre à jour le statut de la période.
11. Sélectionnez **Mettre à jour le statut de la période** et définissez le statut sur **En attente**, **En cours** ou **Clôturé définitivement**. **En cours** indique la période pendant laquelle la validation est possible, pour autant que l’utilisateur ait accès. **En attente** signifie que la période ne peut faire l’objet d’aucune validation, mais elle peut être rouverte. **Clôturé définitivement** signifie que la période est clôturée et ne peut jamais être ouverte. Les ajustements ne peuvent pas être validés. Il n’est pas recommandé de définir une période comme **Définitivement clôturée** avant que tous les ajustements et audits soient terminés.  
12. Sélectionnez **Mettre à jour**.

