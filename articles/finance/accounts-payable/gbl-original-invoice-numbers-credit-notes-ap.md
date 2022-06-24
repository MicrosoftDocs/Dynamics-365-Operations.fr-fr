---
title: Référence aux factures originales dans les notes de crédit (factures fournisseurs)
description: Cet article décrit comment créer une référence à une facture originale lorsque vous créez une note de crédit.
author: v-oloski
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e05dddf056d86513d86ea925349f60ca25f191ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901487"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Référence aux factures originales dans les notes de crédit (factures fournisseurs)

[!include [banner](../includes/banner.md)]

Cet article décrit comment créer une référence à une facture originale lorsque vous créez une note de crédit.

## <a name="prerequisites"></a>Conditions préalables

Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Activer la facturation par crédit pour les factures fournisseurs**. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La fonctionnalité décrite dans cet article s’applique aux documents commerciaux suivants.

**Comptabilité fournisseur :**

- Commande fournisseur
- Journal des factures
- Registre des factures

**Comptabilité :**

- Journal des opérations diverses

## <a name="define-a-reference-to-an-original-invoice"></a>Définir une référence à une facture d’origine

Utilisez les procédures suivantes pour définir une référence à une facture originale dans les types de documents commerciaux spécifiés.

### <a name="vendor-credit-note-purchase-order"></a>Avoir fournisseur (commande fournisseur)

1. Accédez à **Comptabilité fournisseur** \> **Commandes fournisseur** \> **Toutes les commandes fournisseur**.
2. Créez une nouvelle commande d’achat ou utilisez une commande existante pour créer un avoir.
3. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Présenter**, sélectionnez **Facturation de crédit**.
4. Saisissez le motif de la correction et la référence à la facture originale.

### <a name="vendor-credit-note-ledger-journals"></a>Avoir fournisseur (journaux comptables)

1. Utilisez l’une des procédures suivantes :

    - Accédez à **Comptabilité fournisseur** \> **Journal des factures**.
    - Accédez à **Comptabilité fournisseur** \> **Registre des factures**.
    - Accédez à **Comptabilité** \> **Entrées de journal** \> **Journaux des opérations diverses**.

2. Créez un nouveau journal et de nouvelles lignes de journal.
3. Dans le volet Actions, sélectionnez **Fonctions** \> **Créer un avoir**.
4. Saisissez le motif de la correction et la référence à la facture originale.

> [!NOTE]
> La commande **Facturation de crédit** est visible dans une pièce justificative du journal général si le champ **Type de compte** est défini sur **Fournisseur**.
