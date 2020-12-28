---
title: Dépannage des états analytiques
description: Cet article explique comment procéder si les modifications des données d'un client n'apparaissent pas dans les espaces de travail du client.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 99d9eb3a16e6470820a2eb0a19c1d50e89bd3d36
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418533"
---
# <a name="troubleshoot-analytic-reports"></a>Dépannage des états analytiques

**Sortie**

Les modifications des données d'un client n'apparaissent pas dans les onglets **Analyses** des espaces de travail du client.

**Cause**

Par défaut, les états Microsoft Power BI sont actualisés toutes les quatre heures, selon le programme de traitement par lots de mesure du déploiement.

**Résolution**

Ce problème peut seulement être une question de temps. Procédez comme suit pour démarrer le traitement par lots et mettre à jour les espaces de travail d'analyses.

1. Ouvrez la page **Traitements par lots** dans **Administration du système \> Liens \> Traitements par lots \> Traitements par lots**. Sinon, utilisez la recherche, et entrez **Traitements par lots**.
1. Recherchez la tâche **Mesure du déploiement** dans la liste.
1. Sélectionnez **Modifier** en haut de la page, puis définissez le date/heure de début prévue sur une valeur qui actualise les analyses au plus près de l'heure actuelle.

![Traitements par lots](media/batch-jobs.png)
