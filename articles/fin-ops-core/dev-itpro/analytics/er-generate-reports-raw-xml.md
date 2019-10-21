---
title: Générer des états en ajoutant du contenu au format XML brut
description: Vous pouvez créer des formats de gestion des états électroniques qui génèrent des documents sortants au format XML.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
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
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 21449b8684256c5ddf6d710175b3724c300da428
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181402"
---
# <a name="generate-reports-by-adding-content-as-raw-xml"></a>Générer des états en ajoutant du contenu en tant que XML brut

[!include[banner](../includes/banner.md)]

Vous pouvez utiliser le nouvel élément de format **XML BRUT** pour créer des formats de gestion des états électroniques qui génèrent des documents sortants au format XML. Dans certains cas, vous préférez peut-être ajouter des données XML brutes à ces états pour une ou plusieurs des raisons suivantes :

- Il est plus pratique d'utiliser le format XML brut pour la conception d'origine et la maintenance continue d'un état, car la structure XML peut être générée automatiquement en exécutant une expression au moment de l'exécution. Par conséquent, il n'est pas nécessaire de déterminer plusieurs liaisons pour plusieurs éléments de format au moment de la conception. Cela est possible lorsque les sources de données que vous utilisez contiennent des informations permettant de créer des éléments XML lors de la génération de l'état.
- Aucune autre méthode ne peut être utilisée pour renseigner l'état avec le contenu XML qui a été précédemment reçu et enregistré dans le système. Par exemple, la réponse XML générée doit contenir le contenu d'une demande XML qui a été précédemment envoyée.
- Aucune autre méthode ne peut être utilisée pour insérer des caractères dans le document généré en fonction de leurs codes numériques. Pour certaines langues et certains caractères, les codes de ce type n'existent pas. Il s'agit par exemple de la lettre grec rho (ρ) et des codes d'entité HTML tels que \&eacute; pour un *e* avec un accent aigu (é).

> [!NOTE]
> Notez que la structure ne contrôle pas si le contenu XML placé dans le document généré à l'aide de l'élément de format **XML BRUT** est correct.

Pour plus d'informations sur cette fonction, lisez les guides de tâches **ER Utiliser les données XML brutes pour générer des états XML (Partie 1 : Créer un modèle de données)** et **ER Utiliser les données XML brutes pour générer des états XML (Partie 2 : Créer et exécuter un état)**, qui font partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** et qui peuvent être téléchargés à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Ces guides de tâches vous guident tout au long du processus de configuration d'un format ER pour insérer des données XML brutes dans des fichiers générés.
