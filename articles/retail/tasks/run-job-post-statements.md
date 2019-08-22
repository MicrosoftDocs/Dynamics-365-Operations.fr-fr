---
title: Configurer et exécuter la tâche de validation des déclarations
description: Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a24014f7e1b925e0fdb20b91bcc9594feb8f4c5c
ms.sourcegitcommit: fc40279d0e56f8a43c601bca6265fdde4c8c4c7e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/29/2019
ms.locfileid: "1792246"
---
# <a name="configure-and-run-job-to-post-statements"></a>Configurer et exécuter la tâche de validation des déclarations

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour valider les relevés pour un magasin ou un groupe de magasins sélectionné. Cette procédure utilise la société USRT dans les données de démonstration.

1. Accédez à Tous les espaces de travail > .. > Finances du magasin de vente au détail.
2. Cliquez sur Valider les relevés en mode de traitement par lots.
    * Sélectionnez une hiérarchie organisationnelle, puis dans l'arborescence des nœuds d'organisation, sélectionnez un magasin individuel ou un nœud. Sélectionnez un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.  
    * Cliquez sur la flèche pour ajouter votre sélection.  
3. Cliquez sur l'onglet Exécuter à l'arrière-plan. ![Exécuter à l'arrière-plan](../dev-itpro/media/runbackground.png "Exécuter à l'arrière-plan") 
4. Activez ou désactivez la case à cocher Traitement par lots.
![Traitement par lots](../dev-itpro/media/batchprocessing.png "Traitement par lots et répétition") 
5. Cliquez sur Répétition.
6. Entrez une date dans le champ Date de début.
7. Dans le champ Heure de début, saisissez une heure.
    * Choisissez si vous souhaitez terminer la répétition après un nombre spécifique d'exécutions, à une date spécifique ou jamais. Sélectionnez ensuite les différentes options pour définir la fréquence d'exécution de la tâche.  
8. Cliquez sur OK.
9. Cliquez sur OK.

