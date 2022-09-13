---
title: Référence aux factures originales dans les notes de crédit (factures fournisseurs)
description: Cet article décrit comment créer une référence à une facture originale lorsque vous créez une note de crédit.
author: AdamTrukawka
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.search.form: ''
ms.openlocfilehash: 39cf4eb7eef1a83abeb7bd44fa7b2abefee0806e
ms.sourcegitcommit: 8eb0cafe5ad20be2c4fff684e88d7d3f2249f820
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409662"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Référence aux factures originales dans les notes de crédit (factures fournisseurs)

[!include [banner](../includes/banner.md)]

Dans certains pays et certaines régions, il existe une obligation légale selon laquelle les notes de crédit ou les routines de génération d’état imprimées incluent des références aux factures originales. Cet article décrit comment créer une référence à une facture originale lorsque vous créez une note de crédit.

## <a name="prerequisites"></a>Conditions préalables

Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Activer la facturation par crédit pour les factures des fournisseurs**. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La fonctionnalité décrite dans cet article s’applique aux documents commerciaux suivants.

**Comptabilité fournisseur :**

- Commande fournisseur
- Journal des factures
- Registre des factures

**Comptabilité :**

- Journal général

## <a name="define-a-reference-to-an-original-invoice"></a>Définir une référence à une facture originale

La définition d’une référence à une facture d’origine comprend les étapes de haut niveau suivantes :
1. Créez et validez une facture fournisseur.
2. Créez un nouvel avoir fournisseur.
3. Utilisez la fonction de facturation de crédit pour lier la facture à une note de crédit.
4. Validez l’avoir.

Utilisez les procédures suivantes pour définir une référence à une facture originale dans les types de documents commerciaux spécifiés.

### <a name="vendor-credit-note-purchase-order"></a>Note de crédit fournisseur (commande fournisseur)

1. Accédez à **Comptabilité fournisseur** > **Commandes fournisseur** > **Toutes les commandes fournisseur**.
2. Créez une nouvelle commande d’achat ou utilisez une commande existante pour créer un avoir.
3. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Présenter**, sélectionnez **Facturation de crédit**.
4. Saisissez le motif de la correction et la référence à la facture originale.

### <a name="vendor-credit-note-ledger-journals"></a>Note de crédit fournisseur (journaux de comptabilité)

1. Suivez l’une des procédures suivantes :

    - Accédez à **Comptabilité fournisseur** \> **Journaux des factures**.
    - Accédez à **Comptabilité fournisseur** \> **Registre des factures**.
    - Accédez à **Comptabilité** \> **Entrées de journal** \> **Journaux des opérations diverses**.

2. Créez un nouveau journal et de nouvelles lignes de journal.
3. Dans le volet Actions, sélectionnez **Fonctions** \> **Facturation à crédit**.
4. Entrez le motif de la correction et la référence à la facture originale.

> [!NOTE]
> La commande **Facturation de crédit** est visible dans un N° document du journal général si le champ **Type de compte** est défini sur **Fournisseur**.
