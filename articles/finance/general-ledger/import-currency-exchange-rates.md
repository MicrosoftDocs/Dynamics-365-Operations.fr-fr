---
title: Importer les taux de change des devises
description: Cette rubrique fournit des informations sur les exigences en matière d’importation des taux de référence de change publiés par les fournisseurs de taux de change.
author: EvgenyPopovMBS
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 20b8496bc3074eae6535eea4cfe0b254f2773e6a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823738"
---
# <a name="import-currency-exchange-rates"></a>Importer les taux de change des devises

[!include [banner](../includes/banner.md)]

Si une entité juridique a reçu des factures en devises étrangères, il est nécessaire de convertir la devise étrangère en devise locale. Cela signifie que des taux de change à jour pour les différentes devises sont requis. Cette rubrique donne un aperçu des paramètres et du traitement requis en matière d’importation de taux de référence de change publiés par les fournisseurs de taux, tels que la Banque centrale européenne et la Banque centrale de Russie.

Les sections suivantes décrivent le flux global d’informations utilisé pour le paramétrage et le traitement de l’importation des taux de change étrangers.

## <a name="configure-an-exchange-rate-provider"></a>Configurer un fournisseur de taux de change
Avant de pouvoir importer des taux de change, vous devez paramétrer les informations requises par les fournisseurs qui offrent des taux de change. Utilisez la page **Configurer les fournisseurs de taux de change** pour sélectionner les fournisseurs de taux de change. Certains fournisseurs de taux de change sont inclus avec les données de démonstration dans Dynamics 365 Finance. Le tableau suivant décrit les contrôles de cette page.

| Champ | Description                   |
|-----------|-----------------------------------|
| **Nom**  | Nom du fournisseur de taux de change.                                                                                                                                                                                     |
| **Clé**   | Identificateur unique d’une partie des informations de configuration requise par le fournisseur. Ces informations sont automatiquement ajoutées pour chaque fournisseur de taux de change que vous ajoutez. |
| **Value** | Informations pour chaque clé. Ces informations sont ajoutées pour chaque fournisseur de taux de change que vous ajoutez.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importer les taux de change des devises
Vous pouvez importer des taux de change à partir de la source des fournisseurs de taux de change, puis les ajouter à la page **Taux de change des devises**. Utilisez la page **Importer les taux de change des devises** pour importer les taux de change. Le tableau suivant fournit des descriptions des champs obligatoires pour exécuter correctement l’importation.

| Champ | Description                   |
|-----------|-----------------------------------|
| **Type de taux de change**                 | Type de taux de change.                                                                                                                                                                                                                                                                                                                                                      |
| **Fournisseur de taux de change**             | Fournisseur de taux de change.                                                                                                                                                                                                                                                                                                                                                  |
| **Importer à compter de**                       | Ce paramètre gère si l’importation doit s’effectuer à partir de la date actuelle ou à partir d’une plage de dates donnée. Si vous voulez utiliser une plage de dates, entrez ou sélectionnez les dates de début et de fin.                                                                                                                                                                                                                |
| **Créer les paires de devises nécessaires**    | Cette case à cocher gère la création automatique de paire de devises, si les paires de devises qui sont importées n’existent pas. Cette option n’est peut-être pas disponible pour certains fournisseurs.                                                                                                                                                                                               |
| **Remplacer les taux de change existants**   | Cette case à cocher permet de gérer la mise à jour du taux de change existant pour une paire de devises lorsque le taux de change pour une date spécifique existe déjà. Si vous n’activez pas cette case à cocher, le taux de change des dates spécifiques n’est pas importé si un autre taux de change existe déjà.                                                                                       |
| **Éviter l’importation un jour de fête nationale** | Cette case à cocher gère l’importation du taux de change pour la date du jour férié. Par exemple, si vous activez cette case à cocher et utilisez la banque centrale européenne comme fournisseur de taux de change, le système ne met pas le taux de change à jour sur un jour férié associé à l’entité juridique actuelle. Cette option n’est peut-être pas disponible pour certains fournisseurs. |
| **Taux du jour précédent** | Cette case à cocher est disponible si vous activez la fonctionnalité **Importation de la BCE à la date actuelle ou précédente** à la page **Gestion des fonctions**. Cette case à cocher n’est disponible que pour le fournisseur, *Banque centrale d’Europe*. Activez cette case à cocher pour importer le taux de change de la devise qui est publié par la Banque centrale européenne le jour ouvrable précédent vers 16h00 CET. Par défaut, cette case est cochée. Décochez cette case pour importer le taux de change de la devise publié le même jour ouvrable.  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]