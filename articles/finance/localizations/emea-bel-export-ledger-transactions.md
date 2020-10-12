---
title: Exporter les écritures comptables
description: Cette rubrique donne des informations sur l'exportation des soldes de compte général dans un fichier texte brut (ASCII) au format .CED pour la Belgique.
author: anasyash
manager: AnnBe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportExtraFieldsBE
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 273103
ms.search.region: Belgium
ms.author: shylaw
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.openlocfilehash: 4db6d56d72b9c3e4c9040c791e0cca279f794633
ms.sourcegitcommit: 084eda1d5503be83e97e2e428e67ef5393535fab
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "3819997"
---
# <a name="export-ledger-transactions"></a>Exporter les écritures comptables

[!include [banner](../includes/banner.md)]

La fonctionnalité décrite dans cette rubrique permet d'exporter le solde total de chaque compte général pour une période spécifique dans un fichier texte brut (ASCII) au format .CED. Vous pouvez ensuite importer le fichier généré dans un logiciel tiers pour créer un état comptable en fonction des exigences spécifiques au pays/à la région.

Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en Belgique.

## <a name="prerequisites"></a>Conditions préalables

### <a name="create-posting-journals"></a>Créer des journaux de validation

1. Allez dans **Comptabilité** \> **Paramétrage du journal** \> **Journaux de validation**.
2. Sur la page **Paramétrage du journal**, sélectionnez **Créer**. Les journaux de validation et les souches de numéros correspondantes sont créés automatiquement.

## <a name="export-ledger-transactions-to-a-plain-text-file-in-ced-format"></a>Exporter les écritures comptables dans un fichier texte brut ASCII au format CED

1. Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), dans la bibliothèque d'actifs partagés, téléchargez les dernières versions des configurations d'états électroniques pour le format d'état suivant :

    - Format d'exportation des écritures comptables (BE)

    Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](https://docs.microsoft.com/dynamics365/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)

2. Dans Dynamics 365 Finance, allez dans **Comptabilité** \> **Tâches périodiques** \> **Exporter les écritures comptables**.
3. Dans la boîte de dialogue **Exporter les écritures comptables dans un fichier ASCII au format CED**, dans le champ **Mappage de format**, sélectionnez le format **Format d'exportation des écritures comptables (BE)** que vous venez de télécharger, puis cliquez sur **OK**.
4. Dans la boîte de dialogue **Paramètres des états électroniques**, définissez les champs suivants :

| **Champ**          | **Description**                                                             |
|--------------------|-----------------------------------------------------------------------------|
| Date de début          | Entrez le premier jour de la période de déclaration.                                |
| Au            | Entrez le dernier jour de la période de déclaration.                                 |
| Déclaration en euros | Définissez cette option sur **Oui** si la société utilise une devise autre que l'euro. |

5. Cliquez sur **OK** pour générer et télécharger le fichier .txt.

    Par exemple, vous validez les écritures comptables suivantes dans la société DEMF.

| **Date**        | **Type de transaction** | **Compte principal**          | **Compte de contrepartie**        | **Montant net** | **Montant de la TVA** | **Code taxe** |
|-----------------|----------------------|---------------------------|---------------------------|----------------|----------------|--------------------|
| 1 janvier 2020 | Facture client     | 110110 – Compte bancaire en USD |                           | 1 000          | 190            | TVA19              |
| 1 janvier 2020 | Facture fournisseur       |                           | 110120 – Compte bancaire en CNY | 1,095          | 76.65          | EU7                |
| 1 janvier 2020 | Facture client     | 110115 – Compte bancaire en CAD |                           | 800            | 0              | EUS                |

Dans ce cas, le fichier généré contient les données suivantes.

![Données des écritures comptables](media/1_Export_ledger_transactions.png)

Voici une explication des colonnes de ce fichier :

- La première colonne affiche le code compte général.
- La deuxième colonne affiche le solde débiteur du compte général.
- La troisième colonne affiche le solde créditeur du compte général.
- La quatrième colonne affiche le nom du compte général.

> [!NOTE]
> Pour valider les écritures comptables pour les factures client, allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**. Pour les factures fournisseur, allez dans **Comptabilité fournisseur** \> **Factures** \> **Journal des factures**.
