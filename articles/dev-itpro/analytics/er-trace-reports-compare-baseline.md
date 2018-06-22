---
title: "Suivre les résultats de rapport généré et les comparer avec des valeurs de base"
description: "Cette rubrique fournit des informations sur la comparaison des résultats des états ER générés avec des valeurs d'état de base."
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: 1a598d0bd053c60c3f8df6b05ecb7ff15addfaa3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2018

---

# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Suivre les résultats de rapport généré et les comparer avec des valeurs de base

[!include[banner](../includes/banner.md)]

Vous pouvez suivre les résultats des formats ER qui génèrent les documents électroniques sortants. Lorsque la génération du suivi est activée (paramètre utilisateur ER **Exécuter en mode débogage**), un nouvel enregistrement de suivi est généré dans le journal d'exécution du format ER chaque fois qu'un état ER est exécuté. Les détails suivants sont enregistrés dans chaque suivi généré :

- Tous les avertissements générés par les règles de validation
- Toutes les erreurs générées par les règles de validation 
- Tous les fichiers générés qui sont enregistrés en tant que pièces jointes de l'enregistrement de suivi

Vous pouvez enregistrer plusieurs fichiers d'application de base pour un format ER. Les fichiers sont considérés comme des fichiers de base lorsqu'ils décrivent les résultats attendus des états exécutés. Si un fichier de base est disponible pour un format ER qui a été exécuté alors que la génération du suivi a été activée, le suivi enregistre, en plus des détails mentionnés précédemment, le résultat de la comparaison du document électronique généré au fichier de base. En un clic, vous pouvez également obtenir le document électronique généré et son fichier de base dans un fichier zip unique. Vous pouvez ensuite effectuer une comparaison détaillée à l'aide d'un outil externe tel que Windiff.

Vous pouvez évaluer le suivi pour analyser si les documents électroniques générés comprennent le contenu attendu. Vous pouvez effectuer cette évaluation dans un environnement de test d'acceptation par l'utilisateur (UAT) lorsque la base du code a été modifiée (par exemple, lorsque vous avez migré vers une nouvelle instance de l'application, installé des correctifs logiciels ou déployé des modifications du code). De cette manière, vous pouvez vérifier que l'évaluation n'affecte pas l'exécution des états ER utilisés. Pour la plupart des états ER, l'évaluation peut être effectuée en mode sans assistance.

Pour plus d'informations sur cette fonction, lisez les guides de tâches **ER Générer des états et comparer les résultats (partie 1)** et **ER Générer des états et comparer les résultats (partie 2)**, qui font partie du processus d'entreprise **7.5.4.3 Tester les solutions/services informatiques (10679)** et qui peuvent être téléchargés à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Ces guides de tâches vous guident tout au long du processus de configuration de la structure ER pour utiliser les fichiers de base pour évaluer les documents électroniques générés.

