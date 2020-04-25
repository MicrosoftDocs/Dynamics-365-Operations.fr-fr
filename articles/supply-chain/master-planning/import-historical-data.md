---
title: Importer les données d'historique pour les prévisions de la demande
description: Pour obtenir des prévisions de la demande précises, les données de demande d'historique par article ou par clé de répartition par article sont requises. Cette rubrique explique comment utiliser les entités de données pour importer les données de demande d'historique à partir de n'importe quel système, afin de disposer d'un historique plus long des données de prévision de la demande.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97e84b478b8fd65313d8c3be5c9a50756d8b4924
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213837"
---
# <a name="import-historical-data-for-demand-forecasts"></a>Importer les données d'historique pour les prévisions de la demande

[!include [banner](../includes/banner.md)]

Pour garantir la précision des prévisions de la demande, vous devez disposer d'autant de données de demande d'historique que possible par article ou par clé de répartition par article. Si les données de demande d'historique ne sont pas déjà importées, utilisez l'entité de données **Demande externe d'historique** (ReqDemPlanHistoricalExternalDemandEntity) dans Dynamics 365 Supply Chain Management pour les importer.

L'espace de travail **Gestion des données** donne une vue d'ensemble de tous les champs de l'entité.

1. Ouvrez l'espace de travail **Gestion des données**.
2. Cliquez sur la vignette **Entités de données**.
3. Recherchez **Demande externe d'historique** dans la liste d'entités.
4. Cliquez sur **Champs cibles**. Les champs d'entité suivants sont obligatoires : site (**DeliveringSiteId**), date (**DemandDate**), quantité (**DemandQuantity**) et numéro d'article (**ItemNumber**) ou clé de répartition par article (**ProductAllocationKeyId**).

Pour utiliser l'entité de données, vous devez disposer d'un fichier Microsoft Excel ou d'un fichier de valeurs séparées par des virgules (CSV) contenant les données de demande d'historique. L'exemple suivant montre comment importer les données à partir d'un fichier CSV.

## <a name="example"></a>Exemple

Vous pouvez utiliser le fichier suivant comme exemple. Téléchargez le fichier [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast). Ce fichier contient les données de demande d'historique pour l'article D0001. Il contient uniquement les champs obligatoires suivants : site, quantité et date de la demande.

1. Sélectionnez la société dans laquelle importer les données de demande d'historique.
2. Ouvrez l'espace de travail **Gestion des données**.
3. Cliquez sur la vignette **Importer**.
4. Entrez un nom pour le projet d'importation, par exemple **Importer la demande d'historique pour l'article D0001**.
5. Dans le champ **Format des données source**, sélectionnez le format du fichier que vous importez. Pour importer le fichier HistoricalDemandData pour cet exemple, sélectionnez **CSV**.
6. Dans le champ **Nom d'entité**, sélectionnez **Demande externe d'historique**.
7. Enregistrez le fichier sur votre ordinateur, puis téléchargez-le.
8. Cliquez sur **Importer**.
9. La page **Synthèse de l'exécution** s'ouvre automatiquement. Vérifiez les données importées dans la page.

Après avoir importé les données de demande d'historique, vous pouvez générer une prévision de la demande.

## <a name="additional-resources"></a>Ressources supplémentaires

[Générer des prévisions de base statistiques](generate-statistical-baseline-forecast.md)
