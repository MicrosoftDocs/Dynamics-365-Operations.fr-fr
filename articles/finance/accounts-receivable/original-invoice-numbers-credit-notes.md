---
title: Références aux factures d’origine dans les notes de crédit
description: Cet article explique comment configurer et imprimer les numéros de facture d’origine dans les notes de crédit associées.
author: mrolecki
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.search.form: ''
ms.openlocfilehash: f1f9ca3914aa02cc38ddfe9f8dd88eb7fc88fd4b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281233"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>Références aux factures d’origine dans les notes de crédit

[!include [banner](../includes/banner.md)]


Dans certains pays et certaines régions, il existe une obligation légale selon laquelle les notes de crédit imprimées incluent des références aux factures originales. Cet article explique comment configurer et imprimer les numéros de facture d’origine dans les notes de crédit associées.

## <a name="prerequisites"></a>Conditions préalables

- Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonction **Mise en page de la facturation de crédit aux états des facture client et de projet**. Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Les formats imprimables des documents requis doivent être configurés dans Gestion de l’impression.

La fonctionnalité décrite dans cet article s’applique aux documents suivants :

**Comptabilité client**

- Avoir financier
- Avoir du client

**Gestion et comptabilité des projets**

- Avoir de projet

## <a name="configure-accounts-receivable-parameters"></a>Configurer les paramètres de la comptabilité client

Suivez ces étapes pour définir le paramètre qui contrôle si les références aux factures d’origine sont imprimées dans les notes de crédit associées.

1. Accédez à **Comptabilité client** \> **Configuration** \> **Paramètres de la comptabilité client**.
2. Sur l’onglet **Mises à jour**, sur le raccourci **Facture**, définissez l’option **Appliquer la mise en page de la facturation de crédit aux états des facture client et de projet** sur **Oui**.

![Configuration des paramètres de la comptabilité client.](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>Définir des références aux factures originales

Utilisez les procédures suivantes pour définir des références aux factures originales, en fonction du type de document.

### <a name="free-text-credit-note"></a>Avoir financier

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Créez une nouvelle note de crédit ou sélectionnez une note de crédit existante.
3. Ouvrez la facture.
4. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Fonctions**, sélectionnez **Facturation de crédit**.
5. Saisissez la référence à la facture d’origine et sélectionnez le motif de la correction.

![Définition de la référence pour une facture en texte libre.](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>Avoir du client

1. Allez dans **Comptabilité client** \> **Commandes** \> **Toutes les commandes client**.
2. Sélectionnez et ouvrez la commande client facturée qui doit être corrigée.
3. Dans le volet Actions, sous l’onglet **Vendre**, dans le groupe **Avoir**, sélectionnez **Avoir**.
4. Entrez le motif de la correction. La référence à la facture originale est automatiquement établie.

![Définition de la référence d’une commande client.](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>Avoir de projet

1. Accédez à **Gestion et comptabilité des projets** \> **Factures de projets** \> **Factures de projet**.
2. Sélectionnez et ouvrez la facture de projet qui doit être corrigée.
3. Dans le volet Actions, sous l’onglet **Facture de projet**, dans le groupe **Fonctions**, sélectionnez **Sélectionner pour l’avoir**.
4. Sélectionnez **Facturation de crédit**.
5. Entrez le motif de la correction. La référence à la facture originale est automatiquement établie.

![Définition de la référence pour une facture de projet.](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>Impression d’avoirs

Lorsque vous imprimez du texte libre, des notes de crédit client et projet, elles incluront la référence à la facture d’origine et le motif de la correction.

![Note de crédit imprimée.](media/credit-note-FTI.jpg)

> [!NOTE]
> Assurez-vous que les formats imprimables des documents sont correctement configurés, en supposant que les références aux factures d’origine soient imprimées.

## <a name="references-to-original-invoices-in-debit-notes"></a>Références aux factures originales dans les notes de débit

Par défaut, les références aux factures originales peuvent être saisies pour les notes de crédit. Par exemple, vous pouvez saisir des références lorsque vous apportez des corrections négatives (décroissantes) aux factures originales.

Pour saisir des références lorsque vous apportez des corrections positives (augmentation) aux factures originales, vous devez activer la fonctionnalité **Références aux factures originales dans les notes de débit** dans l’espace de travail **Gestion des fonctionnalités**.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
