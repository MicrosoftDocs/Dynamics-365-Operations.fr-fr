---
title: Modifier des formats de gestion des états électroniques en réappliquant des modèles Excel
description: Cette rubrique décrit comment modifier le format des états électroniques (ER) utilisé pour générer des documents commerciaux en réappliquant un modèle Excel modifié.
author: NickSelin
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d828412e0d804acf6e6141778512e899bc78a7d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092842"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Modifier des formats de gestion d’états électroniques en réappliquant des modèles Excel

[!include [banner](../includes/banner.md)]

L’outil d’états électroniques (ER) est utilisé pour générer les documents commerciaux dans un format électronique. Pour générer un document commercial, vous devez créer un format d’ER, puis utilisez le concepteur d’ER pour définir la mise en page du document commercial et spécifier les données à y inclure. Vous pouvez ensuite exécuter le format d’ER pour générer le document commercial.

L’outil d’ER peut être utilisé pour générer des documents commerciaux en tant que fichiers Microsoft Excel. Vous pouvez utiliser un document Excel comme modèle pour ces documents. Pour définir le modèle de document dans le concepteur d’ER, vous pouvez importer le contenu du document Excel que vous souhaitez utiliser comme modèle dans le format défini d’ER. Pour plus d’informations et pour mettre en pratique ce scénario, visionnez le guide de tâche **ER Concevoir une configuration pour générer des états au format OPENXML** (qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)).

Si vous modifiez le document Excel utilisé comme modèle pour un document commercial, la nouvelle fonctionnalité d’ER vous permet de réappliquer le modèle mis à jour dans le format d’ER. Le format d’ER est alors mis à jour de sorte qu’il s’applique au modèle mis à jour. Pour plus d’informations sur cette fonctionnalité, visionnez le guide de tâche **ER Modifier un format en réappliquant un modèle Excel** (qui fait partie du processus d’entreprise 7.5.5.3 Acquérir/Développer des composants de services/solutions informatiques (10683)). Dans le cadre de l’étape du guide de tâche au cours de laquelle vous importez un modèle mis à jour, utilisez le modèle modifié du fichier Excel d’état de paiement, SampleVendPaymWsReport2, en tant que modèle.
