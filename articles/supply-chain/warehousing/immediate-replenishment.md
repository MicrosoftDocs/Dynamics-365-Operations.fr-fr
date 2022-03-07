---
title: Réapprovisionnement immédiat
description: Cette rubrique décrit comment utiliser le réapprovisionnement immédiat pour réapprovisionner le stock lorsque une instruction d’emplacement échoue à affecter le stock.
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSReplenishmentTemplates
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 15a3cc4c50e49a50c354834761425cd107c23a9d79677e022cb1d339bb48c918
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741930"
---
# <a name="immediate-replenishment"></a>Réapprovisionnement immédiat

[!include [banner](../includes/banner.md)]

Le réapprovisionnement immédiat vous permet de réapprovisionner immédiatement le stock lorsqu’une ligne d’instruction d’emplacement échoue à affecter le stock. Le réapprovisionnement est basé sur une ligne unique dans le paramétrage de l’instruction d’emplacement. Si le stock n’est pas disponible dans l’unité de mesure spécifiée par cette ligne, le réapprovisionnement de cette unité de mesure se produit immédiatement.

Le réapprovisionnement immédiat fournit une alternative à la méthode où la répartition du stock est basée sur plusieurs lignes de l’instruction d’emplacement, et où la demande est additionnée à la fin de la répartition et réapprovisionnée dans l’unité de mesure spécifiée par la dernière ligne de l’instruction d’emplacement.

Les avantages à utiliser le réapprovisionnement immédiat sont que le réapprovisionnement peut être limité par des unités spécifiques et la quantité peut être dirigée vers des emplacements spécifiques.

## <a name="business-scenario"></a>Scénario d’entreprise

Par exemple, vous avez un entrepôt avec des secteurs de prélèvement distincts pour les unités de mesure « caisse » et « chaque ». Vous souhaitez optimiser le processus de prélèvement en prélèvement autant de caisses que possible puis en prélevant n’importe quelle quantité restante inférieure à une caisse de « chaque » zone.

Dans ce cas, vous pouvez utiliser le réapprovisionnement immédiat. Dans l’instruction d’emplacement, vous pouvez paramétrer le réapprovisionnement immédiat pour les caisses de sorte que le réapprovisionnement de la demande soit utilisé dès qu’il existe une pénurie de caisses pouvant être prélevées pour la quantité de la demande. Ainsi, vous optimisez le processus de prélèvement afin que le prélèvement inclue autant de caisses que possible. Le réapprovisionnement immédiat génère le réapprovisionnement des caisses, et la demande ne sera pas transmise afin que les quantités soient prélevées dans « chaque » unité de mesure. En d’autres termes, seules les quantités qui sont destinées être prélevées dans « chaque » unité de mesure (autrement dit, les quantités inférieures à une caisse) sont prélevées dans « chaque » zone. Si une pénurie a lieu dans la zone « caisse », vous pouvez prélever autant de caisses que possible de la demande totale. Les quantités restantes seront alors prélevées dans la zone « chaque ».

## <a name="where-it-applies"></a>Dans ce cas

Le réapprovisionnement immédiat est utilisé pendant une exécution de vague si l’allocation échoue pour une ligne d’instruction d’emplacement pour laquelle un modèle de réapprovisionnement est défini.

## <a name="set-up-immediate-replenishment"></a>Paramétrer le réapprovisionnement immédiat

- Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Instructions d’emplacement**, puis, dans l’onglet **Lignes**, dans la liste **Modèle de réapprovisionnement immédiat**, sélectionnez un modèle de réapprovisionnement pour la demande de vague.

Le modèle de réapprovisionnement est appliqué si la ligne d’instruction d’emplacement échoue à affecter une unité de mesure dédiée.

## <a name="troubleshooting"></a>Dépannage

Si le réapprovisionnement immédiat est sélectionné pour une ligne d’instruction d’emplacement, mais qu’aucun travail de réapprovisionnement n’est généré lorsque vous utilisez des modèles de réapprovisionnement de demande pour cette ligne d’instruction d’emplacement, deux causes principales doivent être étudiées :

- Assurez-vous que le modèle de réapprovisionnement de demande appliqué est paramétré pour utiliser les modèles d’emplacement corrects et les modèles de travail de type **Réapprovisionnement**.
- Assurez-vous que le stock disponible est suffisant aux emplacements où les recherches de modèle de réapprovisionnement de demande de stock disponible pour le réapprovisionnement.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]