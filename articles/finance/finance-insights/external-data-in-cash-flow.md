---
title: Données externes dans les prévisions de flux de trésorerie
description: Cette rubrique décrit les étapes de configuration à effectuer pour que des données externes puissent être saisies ou importées dans les prévisions de flux de trésorerie.
author: rcarlson
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 23342114c25cd1b59d47aa7ce63f09de029fa690
ms.sourcegitcommit: 465c84eb5cdc211692e2ae09b45d1400f9a315ee
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8314697"
---
# <a name="external-data-in-cash-flow-forecasts"></a>Données externes dans les prévisions de flux de trésorerie

[!include [banner](../includes/banner.md)]

Les données externes peuvent être saisies ou importées dans les prévisions de trésorerie. Cette rubrique décrit les étapes de configuration spécifiques à l’utilisation de données externes et permettant d’inclure les données externes dans une prévision de flux de trésorerie.

## <a name="external-data-setup"></a>Configuration des données externes

Utilisez l’onglet **Source externe** sur la page **Configuration des prévisions de trésorerie** (**Gestion de la trésorerie et de la banque \> Prévisions de trésorerie \> Configuration des prévisions de flux de trésorerie**) pour saisir des paramètres prenant en charge l’utilisation de données externes dans les prévisions de flux de trésorerie.

Les données externes peuvent être saisies ou importées dans les prévisions de trésorerie. Avant de saisir ou d’importer des données externes, des sources externes doivent être configurées. Sur l’onglet **Source externe**, configurez les catégories de flux de trésorerie externes. Une catégorie peut être **Sortant** ou **Entrant**. **Liquidité** doit être sélectionné comme type de validation. Dans la grille **Paramètres de l’entité juridique**, sélectionnez les entités juridiques et les comptes principaux correspondants auxquels s’appliquent les catégories de flux de trésorerie externes.

Pour plus d’informations sur la configuration des prévisions de flux de trésorerie, voir [Prévisions de flux de trésorerie](../cash-bank-management/cash-flow-forecasting.md).

## <a name="enter-external-data"></a>Saisir des données externes

Pour saisir et modifier des données externes pour les prévisions de flux de trésorerie, vous pouvez utiliser l’expérience **Ouvrir dans Excel**. Sélectionnez le bouton **Données externes** sur la page de l’espace de travail **Configuration des prévisions de flux de trésorerie**, puis **Ajouter des données externes** ou **Modifier les données externes existantes**. Quand le fichier Microsoft Excel est ouvert, vous pouvez saisir des informations dans les champs suivants :

- **ID entrée** (unique)
- **Description** (facultative)
- **Nom de la source externe** – Sélectionnez l’une des valeurs de la liste que vous avez définie lors de la configuration de Finance Insights.
- **Entité juridique**
- **Date**
- **Montant dans la devise de transaction**
- **Code devise**
- **Dimension par défaut** (facultatif)
- **Numéro de référence** (facultatif)
- **Numéro de compte** (facultatif)
- **Nom du compte** (facultatif)

## <a name="importing-external-data-by-using-the-data-management-framework"></a>Importation de données externes à l’aide de la structure de gestion des données

Vous pouvez importer des données externes pour les prévisions de flux de trésorerie en utilisant l’espace de travail **Gestion de données** et l’entité nommée **Entrée source externe des prévisions de trésorerie**.

En outre, si vous devez déplacer des données de configuration d’un environnement à un autre, la zone d’entités suivantes est disponible pour les tables de configuration requises :

- Paramétrage de la source externe des prévisions de flux de trésorerie
- Paramétrage de l’entité juridique de la source externe des prévisions de flux de trésorerie

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
