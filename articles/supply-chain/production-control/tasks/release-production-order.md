---
title: Lancer un ordre de fabrication
description: Cette procédure permet d'indiquer comment lancer un ordre de fabrication.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 82a8316014d28f1c31343a2e54038fc93623cd70
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966253"
---
# <a name="release-a-production-order"></a>Lancer un ordre de fabrication

[!include [banner](../../includes/banner.md)]

Cette procédure permet d'indiquer comment lancer un ordre de fabrication. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Il s'agit de la quatrième des sept procédures expliquant le cycle de vie de l'ordre de fabrication.

1. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
    * Dans la grille, sélectionnez un ordre de fabrication dont le statut est Planifié.  
2. Cliquez sur Ordre de fabrication dans le volet Actions.
3. Cliquez sur Lancement.
    * Dans cette page, vous pouvez confirmer le lancement des ordres de fabrication sélectionnés. Cliquez sur Sélectionner pour ajouter des commandes.  
    * L'étape Lancement indique quand l'ordre de fabrication est lancé dans l'atelier de production afin que les opérateurs d'atelier puissent signaler la progression pour la tâche de fabrication. Les documents de production contenant les informations importantes sur le traitement des tâches peuvent être émis. Le travail d'entrepôt pour le prélèvement de matière première est généré pour les articles configurés pour le processus d'entrepôt.  
4. Cliquez sur l'onglet Général.
    * Sélectionnez les états de production à imprimer. L'état des bons de travail imprime une page pour chaque tâche prévue et requiert que l'ordre de fabrication soit planifié au niveau des tâches. L'état contient des informations sur les dates et heures de début et de fin prévues, la quantité à produire et que la ressource qui traite la tâche. L'état Tâche de gamme collecte les mêmes informations sur la même page, mais n'imprime pas une page pour chaque tâche. L'état Fiche production indique uniquement les opérations, pas les tâches. Par conséquent, cet état ne nécessite pas de planification des tâches, mais il peut être utilisé lorsque des ordres de fabrication sont planifiés au niveau de l'opération.  
5. Cochez la case Imprimer la fiche production.
6. Cliquez sur OK.
7. Fermez la page.

