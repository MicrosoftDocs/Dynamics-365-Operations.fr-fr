---
title: Générer des documents électroniques et mettre à jour des données de l’application à l’aide de la gestion des états électroniques (ER)
description: Vous pouvez concevoir des formats d’états électroniques (ER) qui peuvent être utilisés dans l’application pour générer des documents électroniques sortants.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5f78f3b36a1aebfb263d64ccf2293097eb9af6e6de1ab49de39b18e1c318950
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765806"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Générer des documents électroniques et mettre à jour les données d’application à l’aide des états électroniques

[!include [banner](../includes/banner.md)]

Vous pouvez concevoir des formats d’états électroniques (ER) qui peuvent être utilisés dans l’application pour générer des documents électroniques sortants. Vous pouvez également concevoir les formats ER qui analysent les documents électroniques entrants et utilisent le contenu de ces documents pour mettre à jour des données d’application.

Avec cette fonctionnalité, un format ER simple peut être utilisé pour générer les documents électroniques sortants, puis de mettre à jour les données de l’application. Cette fonction peut être utilisée dans les scénarios suivants :

- Pour empêcher toute utilisation répétée des données d’application dans les processus suivants, vous pouvez marquer les données d’une application immédiatement après la génération des documents électroniques. Par exemple, vous pouvez marquer les transactions de paiement comme effectué immédiatement après leur ajout à un message de paiement généré.
- Pour enregistrer les détails de traitement des documents électroniques générés à l’aide de la logique ER. Par exemple, une identification de message de paiement qui est générée avec l’expression ER. L’expression est basée sur les informations entrées dans la boîte de dialogue ER lorsque le format ER est exécuté pour générer des documents.

Pour en savoir plus sur cette fonction, consultez l’ensemble ER Générer des documents avec la mise à jour des données d’application – Guides de tâches (qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)) qui vous guidera dans les détails de la génération et l’archivage d’états de déclaration d’échanges de biens. Les fichiers suivants sont nécessaires pour exécuter certaines étapes de ces guides de tâche. Téléchargez et enregistrez ces fichiers sur votre ordinateur local.

- [Configuration du modèle de données ER : Déclaration d’échanges de biens (modèle)](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [Configuration du mappage de modèle ER : Déclaration d’échanges de biens (mappage)](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [Configuration du format ER : Déclaration d’échanges de biens (format)](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
