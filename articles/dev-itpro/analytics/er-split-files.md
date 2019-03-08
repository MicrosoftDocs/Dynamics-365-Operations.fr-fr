---
title: Fractionner les fichiers XML générés selon la taille et la quantité de contenu
description: Cette rubrique fournit des informations sur le fractionnement des fichiers générés selon la taille de fichier et la quantité d'éléments de contenu.
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
ms.openlocfilehash: 8c3899d5c6602b3afe13b447b40f0b4dcc701448
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "347098"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>Fractionner les fichiers XML générés selon la taille et la quantité de contenu

[!include[banner](../includes/banner.md)]

Vous pouvez créer des formats de gestion des états électroniques pour générer des documents sortants au format XML. Parfois, ces documents peuvent être acceptés uniquement s'ils répondent à des critères spécifiques, comme la taille de fichier maximale ou un nombre maximal de nœuds XML. Vous pouvez créer des formats ER pour générer des documents électroniques qui répondent aux exigences spécifiées par les destinataires de ces documents.

- Pour l'élément de format FICHIER, vous pouvez définir une limite à la taille de fichier en tant qu'expression ER. Si la limite définie est dépassée lorsqu'un état ER est généré, ER finit de créer le fichier actuel avant de passer à la création du fichier suivant.
- Pour un format ÉLÉMENT XML, vous pouvez définir une limite au nombre d'éléments en tant qu'expression ER. Si le nombre de nœuds XML dans le fichier généré dépasse la limite définie lorsqu'un état ER est exécuté, ER finit de créer le fichier actuel avant de passer à la création du fichier suivant.
- Pour un élément de format SÉQUENCE XML, vous pouvez définir une limite au nombre d'éléments enfants en tant qu'expression ER. Si le nombre de nœuds XML imbriqués de l'élément de format dans le fichier généré dépasse la limite définie lorsqu'un état ER est exécuté, ER finit de créer le fichier actuel avant de passer à la création du fichier suivant.
- Vous pouvez marquer un élément de format ÉLÉMENT XML comme insécable. Ainsi, vous pouvez conserver les éléments imbriqués des nœuds XML générés sous l'élément de format dans un fichier généré unique.

Outre l'utilisation des éléments de format ÉLÉMENT XML et SÉQUENCE XML pour ajouter des nœuds XML au fichier généré, vous pouvez utiliser l'élément de format XML BRUT. Toutefois, les nœuds ajoutés à l'aide de l'élément de format XML BRUT ne sont pas pris en compte lorsque le nombre de nœuds est calculé pour évaluer les limites du nombre d'éléments.

Si vous avez configuré les destinations de fichier d'un élément de format FICHIER qui a été configuré pour fractionner la sortie générée lorsque des limites spécifiques sont dépassées, chaque élément de la sortie générée est envoyée à la destination de fichier configurée en tant que fichier individuel. Pour nommer uniquement les fichiers créés en fractionnant la sortie, vous devez configurer une expression ER pour l'élément de format FICHIER. Si vous incluez une source de données ER du type SOUCHE DE NUMÉROS, la souche de numéros est incrémentée pour chaque élément de la sortie fractionnée.

Pour plus d'informations sur cette fonction, lisez le guide de tâches, **ER Fractionner les fichiers XML selon la taille de fichier ou la quantité d'éléments de contenu**, qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** et qui peut être téléchargé à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Ce guide de tâches vous guide tout au long du processus de configuration d'un format ER pour fractionner les fichiers générés selon la taille de fichier et la quantité d'éléments de contenu. Pour exécuter le guide de tâches, vous devez télécharger les fichiers suivants :

- [Configuration du modèle ER - XmlFilesSplittingModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [Configuration du format ER - XmlFilesSplittingFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)

## <a name="additional-resources"></a>Ressources supplémentaires
[Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)

[Concepteur de formule dans les états électroniques](general-electronic-reporting-formula-designer.md)
