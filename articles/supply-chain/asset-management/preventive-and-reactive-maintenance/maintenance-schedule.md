---
title: Programme de maintenance
description: Cette rubrique explique le programme de maintenance dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f7bed45ccf151a2667dcc8dddd5c0586a594ca58
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839581"
---
# <a name="maintenance-schedule"></a>Programme de maintenance

[!include [banner](../../includes/banner.md)]

 

Le programme de maintenance contient une liste de tous les plans de maintenance préventive prévus, des demandes de maintenance et des visites de maintenance à effectuer. Quelques lignes de programme peuvent avoir été converties en ordres de travail.

Les quatre vues du programme de maintenance sont légèrement différentes, selon les lignes du programme de maintenance que vous souhaitez voir.

| Option de menu                  | Description du contenu                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tout le programme de maintenance       | Toutes les lignes du programme de maintenance sont affichées.     |
| Mon programme d’actifs        | Toutes les lignes du programme de maintenance contenant les actifs installés sur les postes techniques auxquels vous êtes associé en tant qu’agent (configuré dans [Groupes d’agents et agents de maintenance](../setup-for-objects/workers-and-worker-groups.md)) sont affichées dans cette liste. |
| Ouvrir des lignes du programme de maintenance | Les lignes du programme de maintenance avec le statut « Créé », signifiant qu’elles n’ont pas encore été converties en ordre de travail ou qu’elles ont été ignorées, sont affichées dans cette ligne.                                            |
| Ouvrir les regroupements de programmes de maintenance | Les lignes du programme de maintenance associées à un regroupement d’ordres de travail sont affichées dans cette liste.                                                                                                                  |

>[!NOTE]
>Si une ligne du programme de maintenance est incluse dans plusieurs regroupements d’ordres de travail (consultez [Regroupements des ordres de travail](../work-orders/work-order-pools.md)), un enregistrement est indiqué pour chaque regroupement dans **Ouvrir les regroupements du programme de maintenance**. Cela permet d’optimiser les options de filtrage sur les regroupements des ordres de travail.

Pour ouvrir un programme de maintenance :

1. Cliquez sur **Gestion des actifs** > **Commun** > **Programme de maintenance** > **Tout le programme de maintenance** ou **Ouvrir les lignes de programme de maintenance** ou **Ouvrir le regroupement de programme de maintenance**.

2. Pour mettre le programme de maintenance à jour, cliquez sur **Plan de maintenance** ou **Visites de maintenance**. 

3. Vous pouvez modifier une ligne du programme de mise à jour en la sélectionnant et en cliquant sur **Modifier**. Par exemple, vous pouvez facilement mettre à jour le niveau de service ou l’agent responsable de la tâche. Vous pouvez modifier uniquement les lignes du programme de maintenance qui n’ont pas encore été connectées à un ordre de travail.

4. Vous pouvez supprimer une ligne du programme de maintenance en la sélectionnant dans la page de liste et en cliquant sur **Supprimer**.

5. Vous pouvez ignorer une ligne du programme de maintenance en la sélectionnant dans la page de liste et en cliquant sur **Ignorer**. Cette fonction est utile, par exemple, un actif a un plan de maintenance de 2 000 km et un plan de maintenance de 10 000 km. Puis, vous pouvez ignorer la ligne créée depuis le plan de maintenance de 2 000 km lorsque cela coïncide avec 10 000 km, 20 000 km, 30 000 km, etc. Si vous ignorez une ligne du programme de maintenance associée à un plan de maintenance, cette ligne n’apparaîtra jamais une fois le plan de maintenance planifié.

6. Vous pouvez sélectionner plusieurs lignes du programme de maintenance dans **Tout le programme de maintenance** et cliquez sur **Regroupement des ordres de travail**, si vous souhaitez que toutes les lignes sélectionnées soient incluses dans le même regroupement des ordres de travail.

7. Vous pouvez sélectionner plusieurs lignes du programme de maintenance dans **Tout le programme de maintenance** ou **Ouvrir les lignes du programme de maintenance** ou **Ouvrir les regroupements de programmes de maintenance** et cliquez sur **Ajuster un programme** si vous souhaitez apporter les mêmes ajustements à plusieurs lignes. Vous pouvez modifier les dates de début et de fin prévues, le niveau de service, et le groupe d’agents de maintenance responsable ou l’agent de maintenance responsable associé aux lignes du programme de maintenance sélectionnées.

- Lorsqu’une ligne du programme de maintenance a été associée à un ordre de travail, l’ID de l’ordre de travail sera affiché dans le champ **Ordre de travail**.  
- Dans la vue détaillée **Tous les actifs** > organisateur **Plans de maintenance des actifs**, vous pouvez sélectionner les plans de maintenance pour l’actif. Ultérieurement, si vous supprimez une ligne de plan de maintenance ou une visite de maintenance à un actif dans **Tous les actifs**, vous supprimez également automatiquement toutes les lignes du programme de maintenance avec le statut « Créé » ayant été créés en fonction de ce plan de maintenance ou de cette visite de maintenance. Consultez également [Créer un actif](../objects/create-an-object.md).

L’illustration ci-dessous présente la page de liste **Tout le programme de maintenance**.

![Figure 1](media/16-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]