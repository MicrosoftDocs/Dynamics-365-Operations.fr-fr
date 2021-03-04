---
title: Créer automatiquement des commandes de service
description: Vous pouvez générer des commandes de service en fonction d'un accord de service pour la période de validité de l'accord de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08fb7363ab87fd6a7f3d38406e72b1f542dc2c2a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428067"
---
# <a name="automatically-create-service-orders"></a>Créer automatiquement des commandes de service 

[!include [banner](../includes/banner.md)]


Vous pouvez générer des commandes de service en fonction d'un accord de service pour la période de validité de l'accord de service.

Les commandes de service générées à partir d'un accord de service y sont toutes associées.

Les commandes de service sont générées automatiquement à partir des paramètres suivants :

  - l'intervalle de l'accord de service défini dans les lignes de l'accord de service. Il indique la fréquence de création des lignes de commande de service. Pour plus d'informations, voir [Intervalles de services](service-intervals.md).

  - la période spécifiée pour définir la période de service dans les champs **Date de début** et **Date de fin** de l'écran **Créer des commandes de service**. Pour plus d'informations, voir [Création de commandes de service automatiquement](create-service-orders-automatically.md).

  - l'option **Combiner les commandes de service** de l'en-tête d'accord de service. Cette option définit si des lignes de commande de service générées à partir d'un accord de service combinent les commandes de service sur la base de l'employé, de la tâche de service, de l'objet de service ou de l'accord de service. Pour plus d'informations, voir [Combiner les commandes de service](combine-service-orders.md).

  - l'option **Fenêtre Délai** de la ligne d'accord de service. La fenêtre Délai définit le déplacement d'une commande de service en relation avec sa date calculée. Pour plus d'informations, voir [Fenêtre Délai](time-windows.md).


> [!NOTE]
> <P>Si le jour spécifié pour une commande de service n'est pas en cours dans la calendrier sélectionné dans l'écran <STRONG>Paramètres de gestion des services</STRONG>, un message vous informe d'un conflit de calendrier. Vous pouvez ignorer le message. La commande de service est créée même si le jour est fermé sur la calendrier.</P>

## <a name="example-1"></a>Exemple 1

L'accord de service s'étend du 1er janvier 2012 au 31 décembre 2012. Si l'accord de service spécifié dans l'écran **Créer des commandes de service** s'étend du 1er novembre 2012 au 1er février 2013, les commandes de service sont créées du 1er novembre 2012 au 31 décembre 2012.

## <a name="example-2"></a>Exemple 2

L'accord de service s'étend du 1er janvier 2012 au 31 décembre 2012. Deux lignes d'accord de service y sont associées. La date de début de la première ligne d'accord de service est le 2 janvier 2012 et sa date de fin est le 1er mars 2012. La date de début de la deuxième ligne d'accord de service est le 1er avril 2012 et sa date de fin est le 31 décembre 2012. Vous spécifiez une période dans l'écran **Créer des commandes de service** qui s'étend du 1er octobre 2012 au 31 décembre 2012. Par conséquent, les commandes de service ne sont générées que pour la deuxième ligne d'accord car les dates de début et de fin de la première ligne d'accord sont antérieures à la période spécifiée pour la commande de service.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]