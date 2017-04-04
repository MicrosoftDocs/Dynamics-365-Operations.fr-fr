---
title: Importer les taux de change des devises
description: "Si une entité juridique a reçu des factures dans des devises étrangères, il est nécessaire de convertir la devise étrangère dans la devise locale. Cela signifie que à jour les taux de change pour différentes devises sont requis. Cette rubrique fournit une vue d&quot;ensemble des paramètres requis et de traiter pour importer des taux de référence de la devise étrangère publiés sur Internet par les fournisseurs de taux de change, tels que la banque centrale européenne et la banque centrale de la Russie."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf66a1b1c9314b454223274810a21913d54b702d
ms.lasthandoff: 03/31/2017


---

# <a name="import-currency-exchange-rates"></a>Importer les taux de change des devises

Si une entité juridique a reçu des factures dans des devises étrangères, il est nécessaire de convertir la devise étrangère dans la devise locale. Cela signifie que à jour les taux de change pour différentes devises sont requis. Cette rubrique fournit une vue d'ensemble des paramètres requis et de traiter pour importer des taux de référence de la devise étrangère publiés sur Internet par les fournisseurs de taux de change, tels que la banque centrale européenne et la banque centrale de la Russie.

Les sections suivantes décrivent le flux d'informations utilisées pour paramétrer et exécuter l'importation des taux de la devise étrangère.

## <a name="configure-an-exchange-rate-provider"></a>Configuration d'un fournisseur de taux de change
Avant de pouvoir importer des taux de change, vous devez paramétrer les informations requises par les fournisseurs qui offrent des taux de change. Utilisez ** configurez les fournisseurs de taux de change ** la page permet de sélectionner les fournisseurs de taux de change. Certains fournisseurs de taux de change sont inclus dans les données de démonstration dans Microsoft Dynamics 365 pour les opérations. Le tableau suivant décrit les contrôles de cette page.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field** | **Description**                                                                                                                                                                                                             |
| **Name**  | Nom du fournisseur de taux de change.                                                                                                                                                                                     |
| ** Clé **   | Identificateur unique d'une partie des informations de configuration requise par le fournisseur. Cette information est automatiquement ajoutée pour chaque fournisseur de taux de change que vous ajoutez lorsque vous cliquez sur ** ajoutez ** le bouton. |
| **Value** | Informations pour chaque clé. Cette information est ajoutée pour chaque fournisseur de taux de change que vous ajoutez lorsque vous cliquez sur ** ajoutez ** le bouton.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importer les taux de change des devises
Vous pouvez importer des taux de change de la source de fournisseurs de taux de change, puis de les définir dans ** les taux de change ** la page. Utilisez ** des taux de change de la devise d'importation ** la page pour importer les taux de change. Le tableau suivant fournit des descriptions des champs nécessaires pour exécuter correctement le processus d'importation.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**                              | **Description**                                                                                                                                                                                                                                                                                                                                                             |
| **Exchange rate type**                 | Un type de taux de change.                                                                                                                                                                                                                                                                                                                                                      |
| **Exchange rate provider**             | Fournisseur de taux de change.                                                                                                                                                                                                                                                                                                                                                  |
| **Import as of**                       | Ce paramètre gère si importer à partir de la date du jour ou une plage de dates. Si vous souhaitez utiliser une plage de dates, entrez ou sélectionnez les dates de fin.                                                                                                                                                                                                                |
| **Create necessary currency pairs**    | Cette case à cocher gère la création automatique de paire de devises, si les paire de devises importées n'existent pas. Cette option ne soit pas disponible pour certains fournisseurs.                                                                                                                                                                                               |
| **Override existing exchange rates**   | Cette case à cocher permet de gérer la mise à jour du taux de change existant pour une paire de devises lorsque le taux de change pour une date spécifique existe déjà. Si vous n'activez pas cette case à cocher, le taux de change des dates spécifiques ne sont pas importées si un autre taux de change existe déjà.                                                                                       |
| **Prevent import on national holiday** | Cette case à cocher gère l'importation du taux de change pour une date qui est un jour férié. Par exemple, si vous activez cette case à cocher et utilisez la banque centrale européenne comme fournisseur de taux de change, le système ne met pas le taux de change à jour un jour férié associé à l'entité juridique actuelle. Cette option ne soit pas disponible pour certains fournisseurs. |




