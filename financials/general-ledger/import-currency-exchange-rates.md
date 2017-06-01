---
title: Importer les taux de change des devises
description: "Si une entité juridique a reçu des factures dans des devises étrangères, il est nécessaire de convertir la devise étrangère en devise locale. Cela signifie que des taux de change à jour pour les différentes devises sont requis. Cette rubrique donne un aperçu des paramètres requis et du traitement pour l&quot;importation de taux de référence de change publiés sur Internet par les fournisseurs de taux, tels que la Banque centrale européenne et la Banque centrale de Russie."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 69a622f54581504989504a06f90d443a98ad2f63
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="import-currency-exchange-rates"></a>Importer les taux de change des devises

[!include[banner](../includes/banner.md)]


Si une entité juridique a reçu des factures dans des devises étrangères, il est nécessaire de convertir la devise étrangère en devise locale. Cela signifie que des taux de change à jour pour les différentes devises sont requis. Cette rubrique donne un aperçu des paramètres requis et du traitement pour l'importation de taux de référence de change publiés sur Internet par les fournisseurs de taux, tels que la Banque centrale européenne et la Banque centrale de Russie.

Les sections suivantes décrivent le flux global d'informations utilisé pour le paramétrage et le traitement de l'importation des taux de change étrangers.

## <a name="configure-an-exchange-rate-provider"></a>Configurer un fournisseur de taux de change
Avant de pouvoir importer des taux de change, vous devez paramétrer les informations requises par les fournisseurs qui offrent des taux de change. Utilisez la page **Configurer les fournisseurs de taux de change** pour sélectionner les fournisseurs de taux de change. Certains fournisseurs de taux de change sont inclus dans les données de démonstration dans Microsoft Dynamics for Operations. Le tableau suivant décrit les contrôles de cette page.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Champ** | **Description**                                                                                                                                                                                                             |
| **Nom**  | Nom du fournisseur de taux de change.                                                                                                                                                                                     |
| **Clé**   | Identificateur unique d'une partie des informations de configuration requise par le fournisseur. Ces informations sont automatiquement ajoutées pour chaque fournisseur de taux de change que vous ajoutez lorsque vous cliquez sur le bouton **Ajouter**. |
| **Valeur** | Informations pour chaque clé. Ces informations sont ajoutées pour chaque fournisseur de taux de change que vous ajoutez lorsque vous cliquez sur le bouton **Ajouter**.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importer les taux de change des devises
Vous pouvez importer des taux de change de la source de fournisseurs de taux de change, puis les définir dans la page **Taux de change des devises**. Utilisez la page **Importer les taux de change des devises** pour importer les taux de change. Le tableau suivant fournit des descriptions des champs nécessaires pour exécuter correctement le processus d'importation.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Champ**                              | **Description**                                                                                                                                                                                                                                                                                                                                                             |
| **Type de taux de change**                 | Type de taux de change.                                                                                                                                                                                                                                                                                                                                                      |
| **Fournisseur de taux de change**             | Fournisseur de taux de change.                                                                                                                                                                                                                                                                                                                                                  |
| **Importer à compter de**                       | Ce paramètre gère si l'importation doit s'effectuer à partir de la date du jour ou d'une plage de dates. Si vous souhaitez utiliser une plage de dates, entrez ou sélectionnez les dates de début et de fin.                                                                                                                                                                                                                |
| **Créer les paires de devises nécessaires**    | Cette case à cocher gère la création automatique de paire de devises, si les paires de devises qui sont importées n'existent pas. Cette option n'est peut-être pas disponible pour certains fournisseurs.                                                                                                                                                                                               |
| **Remplacer les taux de change existants**   | Cette case à cocher permet de gérer la mise à jour du taux de change existant pour une paire de devises lorsque le taux de change pour une date spécifique existe déjà. Si vous n'activez pas cette case à cocher, le taux de change des dates spécifiques n'est pas importé si un autre taux de change existe déjà.                                                                                       |
| **Éviter l'importation un jour de fête nationale** | Cette case à cocher gère l'importation du taux de change pour une date qui est un jour férié. Par exemple, si vous activez cette case à cocher et utilisez la banque centrale européenne comme fournisseur de taux de change, le système ne met pas le taux de change à jour sur un jour férié associé à l'entité juridique actuelle. Cette option n'est peut-être pas disponible pour certains fournisseurs. |






