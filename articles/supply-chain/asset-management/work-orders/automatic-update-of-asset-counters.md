---
title: Mise à jour automatique des compteurs d'actifs
description: Cette rubrique décrit les mises à jour automatiques des compteurs d'actifs dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875658"
---
# <a name="automatic-update-of-asset-counters"></a>Mise à jour automatique des compteurs d'actifs

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

La section précédente décrivait l'enregistrement manuel des compteurs d'actifs. Le paramétrage des compteurs d'actifs est décrit dans [Compteurs](../setup-for-objects/counters.md).

Des contre valeurs peuvent également être automatiquement mises à jour à partir des enregistrements de production, selon les heures de production ou la quantité produite. Cela est effectué dans la rubrique **Mise à jour des compteurs d'actifs**. Vous pouvez mettre à jour un ou plusieurs actifs en entrant un paramètre, **Date de début**. Ce paramètre spécifie la date de début pour les enregistrements de production (heures de production ou quantité produite), à savoir la date de début à partir de laquelle les contre valeurs doivent être mises à jour.

Tous les actifs associés à une ressource *et* ayant des compteurs d'actifs, qui sont paramétrés pour être mis à jour selon la quantité produite et les heures de production, sont inclus dans une mise à jour automatique, et de nouvelles contre-valeurs sont créées.

Concernant les compteurs basés sur la quantité de production, la quantité correcte et la quantité erronée enregistrée sont incluses dans le comptage. Si l'unité utilisée pour l'enregistrement de la quantité produite est différente de celle utilisée sur le compteur, la quantité est convertie pour correspondre à l'unité du compteur.

Comme mentionné ci-dessus, les compteurs automatiques peuvent être mis à jour à partir des enregistrements de production. Par conséquent, l'actif pour lequel vous souhaitez mettre à jour automatiquement les compteurs doit être lié à une ressource (machine). Les descriptions suivantes fournissent une vue d'ensemble du paramétrage et du traitement des ordres de fabrication (dans le module **Contrôle de la production**), qui sont utilisés comme base pour la mise à jour automatique des compteurs sur un actif dans le module **Gestion des actifs**.

Lorsque des quantités produites ou des heures de production ont été enregistrées dans la ressource, vous pouvez mettre les compteurs d'actifs associés à jour.

1. Cliquez sur **Gestion des actifs** > **Périodique** > **Actifs** > **Mise à jour des compteurs d'actifs**.

2. Sélectionnez la date de début de la mise à jour automatique dans le champ **Date de début**.

>[!NOTE]
>La date de ce champ est la date des « travaux en cours » des **Transactions de gamme** (champ **Contrôle de la production** > **Recherches et états** > **Production** > **Transactions de gamme** > **Date physique**).

3. Si vous souhaitez sélectionner des actifs spécifiques, des types d'actifs ou des ressources pour la mise à jour automatique, cliquez sur **Filtre** sur l'organisateur **Enregistrements à inclure**, et faites les sélections appropriées.

4. Le cas échéant, vous pouvez configurer la mise à jour automatique comme traitement par lots sur l'organisateur **Exécuter à l'arrière-plan**.

![Figure 1](media/12-work-orders.png)

5. Cliquez sur **OK**. Lorsque la mise à jour automatique de compteurs d'actifs est effectuée, vous pouvez voir les enregistrements de compteurs liés à l'actif dans **Compteurs d'actifs** (**Gestion d'actifs** > **Commun** > **Actifs** > **Tous les actifs** > sélectionnez l'actif > le bouton **Compteurs**).

Dans **Compteurs d'actifs totaux**, vous pouvez obtenir une vue d'ensemble du dernier enregistrement effectué sur tous les types de compteurs sur tous les actifs. Cliquez sur **Gestion des actifs** > **Recherches** > **Actifs** > **Valeur agrégée de l'actif**. La vue est très similaire à **Compteurs d'actifs**, mais vous ne pouvez ni ajouter ni modifier d'enregistrements dans **Valeur agrégée de l'actif**. Ce champ est uniquement destiné à la vue d'ensemble.

![Figure 2](media/13-work-orders.png)


- Il est toujours possible de créer des enregistrements manuels de contre-valeur pour les types de compteurs qui sont automatiquement mis à jour. Reportez-vous à la section « Mise à jour manuelle des compteurs d'actifs » pour plus d'informations.
- Vous pouvez paramétrer des compteurs liés à un autre compteur, ce qui signifie que lorsqu'un compteur est mis à jour, les compteurs associés sont automatiquement mis à jour simultanément. Reportez-vous à la section [Compteurs](../setup-for-objects/counters.md) pour plus d'informations sur le paramétrage des compteurs associés.
