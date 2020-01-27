---
title: Les états analytiques ne sont pas mis à jour
description: Cette rubrique explique comment procéder si les modifications des données d'un client n'apparaissent pas dans les espaces de travail du client.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: fc2e6259a8f9d17dc0f7652f207acfa53da76a8d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898571"
---
# <a name="analytic-reports-are-not-updated"></a>Les états analytiques ne sont pas mis à jour

**Problème**

Les modifications des données d'un client n'apparaissent pas dans les onglets **Analyses** des espaces de travail du client.

**Cause**

Par défaut, les états Microsoft Power BI sont actualisés toutes les quatre heures, selon le programme de traitement par lots de mesure du déploiement.

**Résolution**

Ce problème peut seulement être une question de temps. Procédez comme suit pour démarrer le traitement par lots et mettre à jour les espaces de travail d'analyses.

1. Ouvrez la page **Traitements par lots** dans **Administration du système \> Liens \> Traitements par lots \> Traitements par lots**. Sinon, utilisez la recherche, et entrez **Traitements par lots**.
1. Recherchez la tâche **Mesure du déploiement** dans la liste.
1. Sélectionnez **Modifier** en haut de la page, puis définissez le date/heure de début prévue sur une valeur qui actualise les analyses au plus près de l'heure actuelle.

![Traitements par lots](media/batch-jobs.png)
