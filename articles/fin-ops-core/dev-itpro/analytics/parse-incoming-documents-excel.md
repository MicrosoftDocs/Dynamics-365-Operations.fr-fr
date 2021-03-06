---
title: Analyser les documents entrants au format Excel
description: Cette rubrique fournit des informations sur la création de formats de gestion des états électroniques pour analyser le contenu des fichiers Microsoft Excel entrants.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 0c41a062d817307adb2889d3678764f1ea4066e2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755178"
---
# <a name="parse-incoming-documents-in-excel-format"></a>Analyser les documents entrants au format Excel

[!include[banner](../includes/banner.md)]

Vous pouvez créer des formats de gestion des états électroniques pour analyser les fichiers Microsoft Excel entrants qui représentent les données des classeurs Microsoft Excel (fichiers au format XLSX). Vous pouvez ensuite utiliser le contenu de ces fichiers pour mettre à jour les données d’application. Cela est utile dans les cas suivants :

- Vous créez un modèle et un format et vous souhaitez les tester au moment de l’exécution. Dans ce cas, Excel simule les données d’application réelles.
- Vous gérez les données au-delà de votre application dans Excel et vous souhaitez importer ces données pour envoyer un état spécifique.

Pour plus d’informations sur cette fonction, lisez les guides de tâches **ER Importer des données à partir d’un fichier Microsoft Excel (Partie 1 : Créer un format)** et **ER Importer des données à partir d’un fichier Microsoft Excel (Partie 2 : Importer des données)** (parties du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)). Ces guides de tâches vous expliquent comment le fichier Excel entrant peut être analysé en utilisant le format ER pour importer les informations des documents entrants et mettre à jour les données d’application. Vous pouvez télécharger les fichiers du guide de tâches à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).

Téléchargez les fichiers suivants pour exécuter les guides de tâches mentionnés ci-dessus.

| Description du contenu                         | Fichier                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| Fichier entrant au format .XLSX – modèle    | [1099import-template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266) |
| Fichier entrant au format .XLSX – exemple de données | [1099import-data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

Si vous n’avez pas encore lu le guide de tâche suivant, [ER Créer des configurations requises pour importer des données à partir d’un fichier externe](./tasks/er-required-configurations-import-data.md), dans l’application Finance and Operations actuelle, téléchargez le fichier suivant.

| Description du contenu    | Fichier                                                            |
|------------------------|-----------------------------------------------------------------|
| Configuration du modèle ER | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]