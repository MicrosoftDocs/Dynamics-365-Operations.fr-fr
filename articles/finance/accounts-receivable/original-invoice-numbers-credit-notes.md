---
title: Références aux factures d'origine dans les notes de crédit
description: Cette rubrique explique comment configurer et imprimer les numéros de facture d'origine dans les notes de crédit associées.
author: ilkond
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 04a4fc96cb7de60052b17e36c33ad5d5be322be4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207349"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>Références aux factures d'origine dans les notes de crédit

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Dans certains pays et certaines régions, il existe une obligation légale selon laquelle les notes de crédit imprimées incluent des références aux factures originales. Cette rubrique explique comment configurer et imprimer les numéros de facture d'origine dans les notes de crédit associées.

## <a name="prerequisites"></a>Conditions préalables

- Dans l'espace de travail **Gestion des fonctionnalités**, activez la fonction **Mise en page de la facturation de crédit aux états des facture client et de projet**. Pour plus d'informations, voir [Vue d'ensemble de la gestion des fonctionnalités](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).
- Les formats imprimables des documents requis doivent être configurés dans Gestion de l'impression.

La fonctionnalité décrite dans cette rubrique s'applique aux documents suivants :

**Comptabilité client**

- Avoir financier
- Avoir du client

**Gestion et comptabilité des projets**

- Avoir de projet

## <a name="configure-accounts-receivable-parameters"></a>Configurer les paramètres de la comptabilité client

Suivez ces étapes pour définir le paramètre qui contrôle si les références aux factures d'origine sont imprimées dans les notes de crédit associées.

1. Accédez à **Comptabilité client** \> **Configuration** \> **Paramètres de la comptabilité client**.
2. Sur l'onglet **Mises à jour**, sur le raccourci **Facture**, définissez l'option **Appliquer la mise en page de la facturation de crédit aux états des facture client et de projet** sur **Oui**.

![Configuration des paramètres de la comptabilité client](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>Définir des références aux factures originales

Utilisez les procédures suivantes pour définir des références aux factures originales, en fonction du type de document.

### <a name="free-text-credit-note"></a>Avoir financier

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Créez une nouvelle note de crédit ou sélectionnez une note de crédit existante.
3. Ouvrez la facture.
4. Dans le volet Actions, sous l'onglet **Facture**, dans le groupe **Fonctions**, sélectionnez **Facturation de crédit**.
5. Saisissez la référence à la facture d'origine et sélectionnez le motif de la correction.

![Définition de la référence pour une facture en texte libre](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>Avoir du client

1. Allez dans **Comptabilité client** \> **Commandes** \> **Toutes les commandes client**.
2. Sélectionnez et ouvrez la commande client facturée qui doit être corrigée.
3. Dans le volet Actions, sous l'onglet **Vendre**, dans le groupe **Avoir**, sélectionnez **Avoir**.
4. Entrez le motif de la correction. La référence à la facture originale est automatiquement établie.

![Définition de la référence d'une commande client](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>Avoir de projet

1. Accédez à **Gestion et comptabilité des projets** \> **Factures de projets** \> **Factures de projet**.
2. Sélectionnez et ouvrez la facture de projet qui doit être corrigée.
3. Dans le volet Actions, sous l'onglet **Facture de projet**, dans le groupe **Fonctions**, sélectionnez **Sélectionner pour l'avoir**.
4. Sélectionnez **Facturation de crédit**.
5. Entrez le motif de la correction. La référence à la facture originale est automatiquement établie.

![Définition de la référence pour une facture de projet](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>Impression d'avoirs

Lorsque vous imprimez du texte libre, des notes de crédit client et projet, elles incluront la référence à la facture d'origine et le motif de la correction.

![Note de crédit imprimée](media/credit-note-FTI.jpg)

> [!NOTE]
> Assurez-vous que les formats imprimables des documents sont correctement configurés, en supposant que les références aux factures d'origine soient imprimées.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]