---
title: Importer les données d’historique pour les prévisions de la demande
description: Pour obtenir des prévisions de la demande précises, les données de demande d’historique par article ou par clé de répartition par article sont requises. Cet article explique comment utiliser les entités de données pour importer les données de demande d’historique à partir de n’importe quel système, afin de disposer d’un historique plus long des données de prévision de la demande.
author: t-benebo
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e36ea72322c31f7e0ea3377b474cd148d78bdd3d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877593"
---
# <a name="import-historical-data-for-demand-forecasts"></a>Importer les données d’historique pour les prévisions de la demande

[!include [banner](../includes/banner.md)]

Pour garantir la précision des prévisions de la demande, vous devez disposer d’autant de données de demande d’historique que possible par article ou par clé de répartition par article. Si les données de demande d’historique ne sont pas déjà importées, utilisez l’entité de données **Demande externe d’historique** (ReqDemPlanHistoricalExternalDemandEntity) dans Dynamics 365 Supply Chain Management pour les importer.

L’espace de travail **Gestion des données** donne une vue d’ensemble de tous les champs de l’entité.

1. Ouvrez l’espace de travail **Gestion des données**.
2. Sélectionnez la vignette **Entités de données**.
3. Recherchez **Demande externe d’historique** dans la liste d’entités.
4. Sélectionnez **Champs cibles**. Les champs d’entité suivants sont obligatoires : site (**DeliveringSiteId**), date (**DemandDate**), quantité (**DemandQuantity**) et numéro d’article (**ItemNumber**) ou clé de répartition par article (**ProductAllocationKeyId**).

Pour utiliser l’entité de données, vous devez disposer d’un fichier Microsoft Excel ou d’un fichier de valeurs séparées par des virgules (CSV) contenant les données de demande d’historique. L’exemple suivant montre comment importer les données à partir d’un fichier CSV.

Pour plus d’informations sur l’importation de données, notamment le nettoyage des données après une importation, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) et ses articles associés.

Voir aussi [Générer des prévisions de base statistiques](generate-statistical-baseline-forecast.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]