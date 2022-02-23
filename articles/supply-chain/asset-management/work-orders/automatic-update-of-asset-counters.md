---
title: Mise à jour automatique des compteurs d'actifs
description: Cette rubrique décrit les mises à jour automatiques des compteurs d'actifs dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d3e8619439545cf3ea42f84a6dd7ee6ffdf1026e
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021928"
---
# <a name="automatic-update-of-asset-counters"></a>Mise à jour automatique des compteurs d'actifs

[!include [banner](../../includes/banner.md)]

Pour plus d'informations sur l'enregistrement manuel des compteurs d'actifs, voir [Mise à jour manuelle des compteurs d'actifs](../work-orders/manual-update-of-asset-counters.md). Pour plus d'informations sur la configuration des compteurs d'actifs, voir [Compteurs](../setup-for-objects/counters.md).

Des contre valeurs peuvent également être automatiquement mises à jour à partir des enregistrements de production, selon les heures de production ou la quantité produite. Cette mise à jour est effectuée sur la page **Mettre à jour les compteurs d'actifs**. Vous pouvez mettre à jour un ou plusieurs actifs en définissant un paramètre, **Date de début**. Ce paramètre spécifie la date de début des enregistrements de production (heures ou quantités de production). En d'autres termes, il spécifie la date à partir de laquelle des contre-valeurs doivent être mises à jour.

Tous les actifs associés à une ressource *et* ayant des compteurs d'actifs qui sont paramétrés pour être mis à jour selon la quantité produite et les heures de production, sont inclus dans une mise à jour automatique. Des contre-valeurs sont créées.

Pour les compteurs basés sur la quantité de production, le nombre inclut la quantité correcte et la quantité erronée qui sont enregistrées. Si l'unité utilisée pour l'enregistrement de la quantité en production est différente de celle utilisée sur le compteur, la quantité est convertie afin de correspondre à l'unité du compteur.

Comme mentionné ci-dessus, les compteurs automatiques peuvent être mis à jour à partir des enregistrements de production. Par conséquent, l'actif pour lequel vous souhaitez mettre à jour automatiquement les compteurs doit être lié à une ressource (machine). Lorsque des quantités produites ou des heures de production ont été enregistrées dans la ressource, vous pouvez mettre les compteurs d'actifs associés à jour.

1. Sélectionnez **Gestion des actifs** > **Périodique** > **Actifs** > **Mise à jour des compteurs d'actifs**.

2. Dans le champ **Date de début**, sélectionnez la date de début de la mise à jour automatique.

    >[!NOTE]
    >La date de ce champ est la date des « travaux en cours » des **Transactions de gamme** (champ **Contrôle de la production** > **Recherches et états** > **Production** > **Transactions de gamme** > **Date physique**).

3. Dans l'organisateur **Enregistrements à inclure**, vous pouvez sélectionner les actifs, les types d'actifs ou les ressources spécifiques pour la mise à jour automatique. Sélectionnez **Filtrer**, puis effectuez les sélections appropriées.

4. Sous le raccourci **Exécuter à l'arrière-plan**, vous pouvez configurer la mise à jour automatique comme traitement par lots comme vous le souhaitez.

    L'illustration suivante présente un exemple de la boîte de dialogue **Mise à jour des compteurs d'actifs**.

    ![Figure 1](media/12-work-orders.png)

5. Cliquez sur **OK**. 

Après la mise à jour automatique du compteur d'actifs, vous pouvez afficher les enregistrements du compteur associés à l'actif sur la page **Compteurs d'actifs**. Sélectionnez **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**, sélectionnez l'actif, puis, dans le volet Actions, sous l'onglet **Actif**, dans le groupe **Préventif**, sélectionnez **Compteurs**.

Sur la page **Valeur agrégée de l'actif**, vous pouvez obtenir une vue d'ensemble du dernier enregistrement effectué sur tous les types de compteurs sur tous les actifs. Sélectionnez **Gestion des actifs** > **Recherches** > **Actifs** > **Valeur agrégée de l'actif**. Cette page est semblable à la page **Compteurs d'actifs**, mais vous ne pouvez ni ajouter ni modifier des enregistrements. Elle est uniquement destinée à la vue d'ensemble.

L'illustration suivante présente un exemple de la boîte de dialogue **Valeur agrégée de l'actif**.

![Figure 2](media/13-work-orders.png)

Notez les points suivants :

- Vous pouvez toujours créer des enregistrements manuels de contre-valeur pour les types de compteurs qui sont automatiquement mis à jour. Pour plus d'informations, voir [Mise à jour manuelle des compteurs d'actifs](../work-orders/manual-update-of-asset-counters.md).

- Vous pouvez paramétrer les compteurs associés à un autre compteur. Dans ce cas, lorsqu'un compteur est mis à jour, les compteurs associés sont automatiquement mis à jour simultanément. Pour plus d'informations sur la configuration des compteurs associés, voir [Compteurs](../setup-for-objects/counters.md).

