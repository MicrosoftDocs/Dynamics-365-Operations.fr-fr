---
title: Utiliser des données externes dans les prévisions de flux de trésorerie (version préliminaire)
description: Cette rubrique décrit les étapes de configuration que vous devez effectuer pour que des données externes puissent être saisies ou importées dans les prévisions de flux de trésorerie.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: ae0eba6d397725cf425d9781a597d904e1958d44
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009390"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Utiliser des données externes dans les prévisions de flux de trésorerie (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Les données externes peuvent être saisies ou importées dans les prévisions de trésorerie. Cette rubrique décrit les étapes de configuration spécifiques à l’utilisation de données externes et permettant d’inclure les données externes dans une prévision de flux de trésorerie.

## <a name="external-data-setup"></a>Configuration des données externes

Utilisez l’onglet **Source externe** sur la page **Configuration des prévisions de trésorerie** (**Gestion de la trésorerie et de la banque \> Prévisions de trésorerie**) pour saisir des paramètres prenant en charge l’utilisation de données externes dans les prévisions de flux de trésorerie.

Pour plus d’informations sur la configuration des compteurs, voir [Prévisions de flux de trésorerie](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).

Pour saisir des données externes pour les prévisions de flux de trésorerie, vous pouvez utiliser l’expérience Ouvrir dans Excel pour saisir et modifier des données externes. Sélectionnez le bouton **Données externes** puis soit **Ajouter des données externes** soit **Modifier les données externes existantes**. Quand le fichier Microsoft Excel est ouvert, vous pouvez saisir des informations dans les champs suivants :

- **ID entrée**
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

#### <a name="privacy-notice"></a>Avis de confidentialité
Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]