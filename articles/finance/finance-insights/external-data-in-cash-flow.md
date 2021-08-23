---
title: Utiliser des données externes dans les prévisions de flux de trésorerie (version préliminaire)
description: Cette rubrique décrit les étapes de configuration que vous devez effectuer pour que des données externes puissent être saisies ou importées dans les prévisions de flux de trésorerie.
author: rcarlson
ms.date: 07/16/2021
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
ms.openlocfilehash: ff2a454b422cc4decc15339e6b328d99df85ccbc66ba3928f6c9e9f21b7b51a7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768841"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Utiliser des données externes dans les prévisions de flux de trésorerie (version préliminaire)

[!include [banner](../includes/banner.md)]

Les données externes peuvent être saisies ou importées dans les prévisions de trésorerie. Cette rubrique décrit les étapes de configuration spécifiques à l’utilisation de données externes et permettant d’inclure les données externes dans une prévision de flux de trésorerie.

## <a name="external-data-setup"></a>Configuration des données externes

Utilisez l’onglet **Source externe** sur la page **Configuration des prévisions de trésorerie** (**Gestion de la trésorerie et de la banque \> Prévisions de trésorerie**) pour saisir des paramètres prenant en charge l’utilisation de données externes dans les prévisions de flux de trésorerie.

Pour plus d’informations sur la configuration des compteurs, voir [Prévisions de flux de trésorerie](../cash-bank-management/cash-flow-forecasting.md).

Pour saisir des données externes pour les prévisions de flux de trésorerie, vous pouvez utiliser l’expérience Ouvrir dans Excel pour saisir et modifier des données externes. Sélectionnez le bouton **Données externes** puis soit **Ajouter des données externes** soit **Modifier les données externes existantes**. Quand le fichier Microsoft Excel est ouvert, vous pouvez saisir des informations dans les champs suivants :

- **ID entrée**
- **Description** (facultative)
- **Nom de la source externe** – Sélectionnez l’une des valeurs de la liste que vous avez définie lors de la configuration de Informations financières.
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
