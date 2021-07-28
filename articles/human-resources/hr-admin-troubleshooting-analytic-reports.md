---
title: Dépannage des états analytiques
description: Cet article explique comment procéder si les modifications des données d’un client n’apparaissent pas dans les espaces de travail du client.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 382780405b2496cc655451790ef4a99ef60ba129
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354250"
---
# <a name="troubleshoot-analytic-reports"></a>Dépannage des états analytiques

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Sortie**

Les modifications des données d’un client n’apparaissent pas dans les onglets **Analyses** des espaces de travail du client.

**Cause**

Par défaut, les états Microsoft Power BI sont actualisés toutes les quatre heures, selon le programme de traitement par lots de mesure du déploiement.

**Résolution**

Ce problème peut seulement être une question de temps. Procédez comme suit pour démarrer le traitement par lots et mettre à jour les espaces de travail d’analyses.

1. Ouvrez la page **Traitements par lots** dans **Administration du système \> Liens \> Traitements par lots \> Traitements par lots**. Sinon, utilisez la recherche, et entrez **Traitements par lots**.
1. Recherchez la tâche **Mesure du déploiement** dans la liste.
1. Sélectionnez **Modifier** en haut de la page, puis définissez le date/heure de début prévue sur une valeur qui actualise les analyses au plus près de l’heure actuelle.

![Traitements par lots.](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]