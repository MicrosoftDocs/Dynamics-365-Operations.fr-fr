---
title: Planifier un ordre de travail à une date et une heure spécifiques
description: Cette rubrique explique comment planifier un ordre de travail à une date et une heure spécifiques dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 634bbb4326d560848d36f579a1179187d8369087
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652032"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Planifier un ordre de travail à une date et une heure spécifiques

[!include [banner](../../includes/banner.md)]

 

Si un ordre de travail doit être programmé à une date *et* à une heure spécifiques, vous pouvez remplacer le processus de planification standard dans le module Gestion des actifs et créer un programme spécifique pour un ordre de travail.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Dans la liste des ordres de travail, cliquez sur l'ID de l'ordre de travail dans la colonne **Ordre de travail**.

3. Cliquez sur **Modifier**.

4. Dans l'organisateur **En-tête de l'ordre de travail**, saisissez les dates et heures de début et de fin dans les champs **Début prévu** et **Fin prévue**.

    ![Figure 1](media/05-work-order-scheduling.png)

5. Dans l'onglet **Général**, cliquez sur **Planifier** pour utiliser le processus de planification standard, ou cliquez sur **Répartir** si vous souhaitez affecter l'ordre de travail à un agent spécifique.

6. Afin de remplacer les réservations de capacité existantes pour vous assurer que l'ordre de travail est planifié dans la période prévue, effectuez vos sélections comme illustré sur la figure ci-dessous dans la boîte de dialogue **Planifier un ordre de travail** > section **Capacité finie**. Cela signifie que le processus de planification ignorera les réservations de capacité existantes, car l'ordre de travail doit démarrer à l'heure de début prévue.

    ![Figure 2](media/06-work-order-scheduling.png)

7. Cliquez sur **OK** pour démarrer la planification.

8. Si le processus de planification génère un doublon en matière de réservation, un message apparaît à l'écran, et vous pouvez ajuster les ordres de travail associés.

>[!NOTE]
>Afin de planifier un agent de maintenance pour l'ordre de travail, cet agent de maintenance doit être disponible aux dates de début et de fin prévues. La disponibilité de l'agent est paramétrée dans [calendrier de l'agent](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 
