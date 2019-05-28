---
title: Validation des ventes et des paiements en ligne
description: Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
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
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13839bbe6ca03f3cfc7036fce87477bf7d5af2a7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550206"
---
# <a name="posting-of-online-sales-and-payments"></a>Validation des ventes et des paiements en ligne

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne. Cette procédure utilise la société USRT dans les données de démonstration.

1. Accédez à Tous les espaces de travail > Finances du magasin de vente au détail.
2. Cliquez sur Synchroniser les commandes.
3. Dans le champ Hiérarchie d'organisation, sélectionnez « Magasins de vente au détail par région ».
    * Sélectionnez un magasin en ligne spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.  
    * Cliquez sur la flèche pour ajouter votre sélection.  
4. Cliquez sur l'onglet Exécuter à l'arrière-plan.
5. Activez ou désactivez la case à cocher Traitement par lots.
6. Cliquez sur Répétition.
7. Sélectionnez l'option Pas de date de fin.
8. Dans le champ Nombre, saisissez un nombre.
9. Cliquez sur OK.
10. Cliquez sur OK.

