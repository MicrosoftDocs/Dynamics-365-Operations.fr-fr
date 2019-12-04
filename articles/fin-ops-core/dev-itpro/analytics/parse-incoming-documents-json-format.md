---
title: Analyser les documents entrants au format JSON
description: Cette rubrique explique comment configurer des formats de génération d'états électroniques (ER) pour analyser des documents entrants au format JSON (JavaScript Object Notation).
author: kfend
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 8be4e225507a18a92d642ff0f3a6ca3d0ff68564
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772533"
---
# <a name="parse-incoming-documents-in-json-format"></a>Analyser les documents entrants au format JSON

[!include[banner](../includes/banner.md)]

Vous pouvez créer des formats de génération d'états électroniques (ER) pour analyser les documents électroniques entrants qui représentent des données dans un format texte Javascript (autrement dit, des fichiers au format \[JSON\] (JavaScript Object Notation)).

Pour en savoir plus sur cette fonction, téléchargez les fichiers du tableau suivant, puis lisez le guide de tâche ER Créer une configuration de format pour importer des données à partir d'un fichier JSON externe. Ce guide de tâche montre comment utiliser un format ER pour analyser un fichier JSON entrant pour mettre à jour des données d'application.

| Titre                                  | Nom de fichier |
|----------------------------------------|-----------|
| Configuration de format ER                | [Format pour l'importation de fournisseurs trans_JSON.xml](https://go.microsoft.com/fwlink/?linkid=874111) |
| Exemple de fichier entrant au format .csv | [1099entries_JSON.txt](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a>Configuration requise

Avant de suivre le guide de tâche ER Créer une configuration de format pour importer des données à partir d'un fichier JSON externe, vous devez remplir les conditions suivantes :

- Les éléments parent dans le fichier JSON peuvent être uniquement des éléments objets.
- Les éléments imbriqués d'un objet doivent être des éléments de propriété, afin de créer une structure JSON valide.
- Les tableaux JSON ne peuvent être que des éléments imbriqués d'éléments de propriété d'un objet.
- Les tableaux JSON ne peuvent contenir que des objets JSON. Ils ne peuvent pas contenir de valeurs de chaîne ou numériques directes ni de tableaux imbriqués. Les éléments de ces tableaux sont analysés dans l'ordre, comme ils sont spécifiés dans le format. Les paramètres de multiplicité de chaque objet de JSON sont pris en compte.

En outre, vous devez compléter le guide de tâche [ER Créer des configurations requises pour importer des données à partir d'un fichier externe](tasks/er-required-configurations-import-data.md) si ce n'est déjà fait. Téléchargez le fichier suivant pour exécuter le guide de tâches.

| Titre                  | Nom de fichier |
|------------------------|-----------|
| Configuration du modèle ER | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=874111) |
