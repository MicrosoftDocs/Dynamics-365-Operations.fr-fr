---
title: "Visibilité des exceptions de matières"
description: "Cette rubrique décrit comment vous pouvez obtenir une meilleure visibilité des exceptions de matières premières pour les ordres de fabrication et les lots de commandes."
author: johanhoffmann
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: AX 7.3.0, Operations, UnifiedOperations
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-03-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: 18c8b5d1d3e83259cf5dafd08bfc779161a4c916
ms.contentlocale: fr-fr
ms.lasthandoff: 12/14/2017

---
# <a name="visibility-into-material-exceptions"></a>Visibilité des exceptions de matières

Dans l'espace de travail **Gestion de l'atelier de production**, trois vignettes vous donnent une meilleure visibilité des exceptions de matières premières pour les ordres de fabrication et les lots de commandes :

- Lignes de matières non libérées nécessitant une attention
- Vagues non traitées nécessitant une attention
- Travail d'entrepôt en cours nécessitant une attention

Pour les trois vignettes, la date de consommation des matières premières des lignes de nomenclature et de formule est comparée à la date de l'espace de travail, ainsi qu'aux filtres pour **Unité de production**, **Groupe de ressources** et **Ressource** qui sont définis dans le menu **Configurer mon espace de travail**. Par défaut, la date de l'espace de travail est définie sur la date en cours, mais vous pouvez la modifier.

Une ligne de nomenclature ou de formule non lancée nécessite une attention particulière si la date de consommation des matières premières de la ligne est identique ou antérieure à la date de l'espace de travail, et si elle répond aux critères définis par les filtres de l'espace de travail.

Dans la figure suivante, la barre bleue représente une tâche de production planifiée pour une ressource. La tâche est planifiée pour démarrer le 1er mai 2017 (01/05/2017). Cette date correspond à la date de consommation des matières premières. Autrement dit, les matières affectées à la tâche sur les lignes de nomenclature et de formule doivent être prêtes à cette date. L'autre date indiquée dans la figure, le 6 mai 2017 (06/05/2017), représente la date de l'espace de travail. Dans cet exemple, la date de consommation des matières premières est antérieure à la date de l'espace de travail. Par conséquent, la date à laquelle la consommation des matières premières était supposée commencer est dépassée, et les lignes de nomenclature et de formule répondent aux critères pour nécessiter une attention particulière.

![Exemple d'une tâche de production où la date de consommation des matières premières est antérieure à la date de l'espace de travail](./media/improved-visibility.png)

## <a name="unreleased-material-lines-needing-attention"></a>Lignes de matières non libérées nécessitant une attention

Une ligne de nomenclature ou de formule peut être lancée dans l'entrepôt de trois manières :

- Dans le cadre du lancement d'un ordre de fabrication ou d'un lot de commandes
- En tant que lancement manuel
- Automatiquement via un traitement par lots

Pour plus d'informations, voir [Lancer des lignes de nomenclature et de formule dans l'entrepôt](releasing-bom-and-formula-lines-to-warehouse.md). 

Si une ligne de nomenclature ou de formule n'a pas été lancée ou a été partiellement lancée, et si les critères de date et de filtre de l'espace de travail sont remplis, la ligne est incluse dans le calcul du nombre qui apparaît sur la vignette **Lignes de matières non libérées nécessitant une attention**.

Lorsque vous sélectionnez la vignette, la page **Libérer dans l'entrepôt** est ouverte. Cette page affiche le nombre de lignes de nomenclature et de formule non lancées qui est indiqué par le nombre sur la vignette. Les lignes non lancées s'affichent dans la grille supérieure. Cette grille affiche la quantité initialement estimée pour la ligne, la quantité déjà lancée et la quantité restante qui doit encore être lancée. Vous pouvez ajouter des lignes de la grille supérieure à la grille inférieure. Dans la grille inférieure, vous pouvez lancer les lignes sélectionnées dans l'entrepôt. Dans la grille inférieure, vous pouvez également ajuster la quantité à lancer afin qu'une quantité partielle soit lancée.

## <a name="unprocessed-waves-needing-attention"></a>Vagues non traitées nécessitant une attention

Lorsqu'une ligne de nomenclature ou de formule est lancée, elle est ajoutée à une nouvelle vague de production ou à une vague en cours existante, en fonction de la configuration du modèle de vague de production. À l'aide de la configuration du modèle de vague, vous pouvez également paramétrer une vague afin qu'elle soit automatiquement traitée lorsqu'une ligne de nomenclature ou de formule est lancée. Lorsque la vague est traitée, le travail d'entrepôt pour le prélèvement des matières premières est généré. Si le modèle de vague est configuré de manière à ce que les vagues ne soient pas traités au moment du lancement, le vague reste dans un état non traité. La vignette **Vagues non traitées nécessitant une attention** affiche le nombre de lignes de nomenclature et de formule qui ont été lancées dans l'entrepôt pour les vagues non traitées et dont la date de consommation des matières premières est antérieure ou identique à la date de l'espace de travail. Les lignes doivent également être consommées par une ressource opérationnelle qui s'applique au filtre de l'espace de travail.

Lorsque la vignette est sélectionnée, la page **Toutes les vagues de production** est ouverte. Cette page est filtrée en fonction du nombre de vagues en cours contenant des lignes de vague à partir des lignes de nomenclature et de formule lancées qui répondent aux critères de la vignette. Dans la page **Toutes les vagues de production**, vous pouvez traiter manuellement la vague.

## <a name="open-warehouse-work-needing-attention"></a>Travail d'entrepôt en cours nécessitant une attention

La vignette **Travail d'entrepôt en cours nécessitant une attention** affiche le nombre de lignes de nomenclature et de formule qui ont été lancées dans l'entrepôt, dont le travail n'est pas traité et dont la date de consommation des matières premières est antérieure ou identique à la date de l'espace de travail. Les lignes doivent également être consommées par une ressource opérationnelle qui s'applique au filtre de l'espace de travail.

Lorsque la vignette est sélectionnée, la page **Tout le travail** est ouverte. Cette page est filtrée en fonction du nombre d'en-têtes de travail en cours contenant des lignes de travail à partir des lignes de nomenclature et de formule lancées qui répondent aux critères de la vignette. Dans la page **Tout le travail**, vous pouvez traiter manuellement le travail.

