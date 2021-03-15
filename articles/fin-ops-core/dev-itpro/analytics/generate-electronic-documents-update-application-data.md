---
title: Générer des documents électroniques et mettre à jour des données de l’application à l’aide de la gestion des états électroniques (ER)
description: Vous pouvez concevoir des formats d’états électroniques (ER) qui peuvent être utilisés dans l’application pour générer des documents électroniques sortants.
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 4ae3405a882ac37fd9758d8ff0902896562fa06b
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093871"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Générer des documents électroniques et mettre à jour les données d’application à l’aide des états électroniques

[!include [banner](../includes/banner.md)]

Vous pouvez concevoir des formats d’états électroniques (ER) qui peuvent être utilisés dans l’application pour générer des documents électroniques sortants. Vous pouvez également concevoir les formats ER qui analysent les documents électroniques entrants et utilisent le contenu de ces documents pour mettre à jour des données d’application.

Avec cette fonctionnalité, un format ER simple peut être utilisé pour générer les documents électroniques sortants, puis de mettre à jour les données de l’application. Cette fonction peut être utilisée dans les scénarios suivants :

- Pour empêcher toute utilisation répétée des données d’application dans les processus suivants, vous pouvez marquer les données d’une application immédiatement après la génération des documents électroniques. Par exemple, vous pouvez marquer les transactions de paiement comme effectué immédiatement après leur ajout à un message de paiement généré.
- Pour enregistrer les détails de traitement des documents électroniques générés à l’aide de la logique ER. Par exemple, une identification de message de paiement qui est générée avec l’expression ER. L’expression est basée sur les informations entrées dans la boîte de dialogue ER lorsque le format ER est exécuté pour générer des documents.

Pour en savoir plus sur cette fonction, consultez l’ensemble ER Générer des documents avec la mise à jour des données d’application - Guides de tâches (qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)) qui vous guidera dans les détails de la génération et l’archivage d’états de déclaration d’échanges de biens. Les fichiers suivants sont nécessaires pour exécuter certaines étapes de ces guides de tâche. Téléchargez et enregistrez ces fichiers sur votre ordinateur local.

- [Configuration du modèle de données ER : Déclaration d’échanges de biens (modèle)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configuration du mappage de modèle ER : Déclaration d’échanges de biens (mappage)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configuration du format ER : Déclaration d’échanges de biens (format)](https://go.microsoft.com/fwlink/?linkid=849038)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]