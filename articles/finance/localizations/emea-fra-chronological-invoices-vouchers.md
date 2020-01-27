---
title: Facture et n° document chronologiques
description: Cette rubrique explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264514
ms.search.region: France
ms.author: ilyako
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5e18dbb9684e9916e86b5b8a8a5b7d6cbe2f49ee
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915261"
---
# <a name="chronological-invoice-and-voucher-numbers"></a>Facture et n° document chronologiques

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client.  

Dans certains pays, il est obligatoire que toutes les factures et les documents associés émis soient numérotés dans l'ordre chronologique. La chronologie doit être prise en charge par les périodes fiscales. Tous les numéros qui appartiennent à des périodes antérieures doivent être inférieurs aux numéros qui appartiennent aux périodes ultérieures. Dans une période fiscale, l'ordre chronologique n'est pas obligatoire, mais il ne doit y avoir aucun écart dans la numérotation. Pour répondre à cette exigence, la numérotation chronologique dans le module Comptabilité client affecte les documents suivants :

-   Facture financière
-   N° document de facture financière
-   Avoir financier
-   N° document d'avoir financier
-   Facture client
-   Document de facture client
-   Avoir sur vente
-   N° document d'avoir sur vente

## <a name="prerequisites"></a>Conditions préalables
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Logiciel requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Activation des fonctionnalités</td>
<td>Dans l'espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Numérotation chronologique**. Pour plus d'informations, voir [Vue d'ensemble de la gestion des fonctionnalités](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</td>
</tr>
<tr class="even">
<td>Pays/région</td>
<td>Si l'adresse principale de l'entité juridique est en <strong>France</strong>, définissez également l'option <strong>Numérotation chronologique</strong> sur <strong>Oui</strong> sur la page <strong>Paramètres de la comptabilité client</strong> sous l'onglet <strong>Mises à jour</strong>.</td>
</tr>
<tr class="odd">
<td>Tâches associées de paramétrage</td>
<td>Dans la page <strong>Souches de numéros</strong>, définissez autant de souches de numéros qu'il est nécessaire pour couvrir les périodes fiscales affectées. Vous devez spécifier une société pour chaque souche de numéros. Les segments des souches de numéros doivent être définis de manière à fournir l'ordre chronologique des périodes. Par exemple, les noms de segment peuvent contenir un préfixe spécial qui identifie une période spécifique.</td>
</tr>
</tbody>
</table>

## <a name="set-up-chronological-numbering"></a>Paramétrer la numérotation chronologique
### <a name="accounts-receivable-parameters"></a>Paramètres de la comptabilité client

Dans la page **Paramètres de la comptabilité client**, sous l'onglet **Souches de numéros**, sélectionnez l'une des références prises en charge, par exemple **Facture financière**. Cliquez ensuite sur le bouton **Paramétrage de la numérotation chronologique** qui sera disponible pour les références prises en charge. Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.

![Paramétrage des numéros chronologiques](media/emea-chronological-numbering.jpg)

### <a name="number-sequence-groups"></a>Groupes de souches de numéros

Si différents clients utilisent différents modèles de numérotation, vous devez paramétrer la numérotation chronologique au niveau du groupe de souches de numéros. Dans la page **Paramètres de la comptabilité client**, sous l'onglet **Souches de numéros**, sélectionnez l'une des références prises en charge, puis cliquez sur **Groupe**. Dans la page **Groupe de souches de numéros**, sélectionnez un groupe existant ou créez-en un. Dans la section **Référence**, sélectionnez l'une des références prises en charge, puis cliquez sur **Paramétrage de la numérotation chronologique**. Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.

## <a name="invoice-posting"></a>Validation de facture
Lorsque vous validez une facture ou un avoir, la souche de numéros appropriée est utilisée pour générer un numéro. Cette souche de numéros est sélectionnée selon la période valide contenant la date de la facture. La numérotation chronologique spécifique au client a une priorité plus élevée que la numérotation chronologique.

### <a name="dates-control"></a>Contrôle des dates

Le système effectue un contrôle supplémentaire des dates de factures pour les factures clients : 

- La validation de nouvelles factures avec des dates antérieures à la date de la dernière facture validée est interdite si aucun code motif n'est défini. Pour activer la validation, un code motif doit être saisi soit dans un en-tête de facture/commande, soit dans l'une des lignes.
- Un avertissement est émis si la nouvelle date de facturation est postérieure à la date système.
