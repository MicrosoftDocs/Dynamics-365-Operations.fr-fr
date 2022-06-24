---
title: Facture et n° de justificatif chronologiques
description: Cet article explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client.
author: ShylaThompson
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.custom: 264514
ms.search.region: France
ms.author: ilyako
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 87bb6fdca9cdc2814c17ceb2a0f207d6572d3aa4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846509"
---
# <a name="chronological-invoice-and-voucher-numbers"></a>Facture et n° de justificatif chronologiques

[!include [banner](../includes/banner.md)]

Cet article explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client.  

Dans certains pays, il est obligatoire que toutes les factures et les documents associés émis soient numérotés dans l’ordre chronologique. La chronologie doit être prise en charge par les périodes fiscales. Tous les numéros qui appartiennent à des périodes antérieures doivent être inférieurs aux numéros qui appartiennent aux périodes ultérieures. Dans une période fiscale, l’ordre chronologique n’est pas obligatoire, mais il ne doit y avoir aucun écart dans la numérotation. Pour répondre à cette exigence, la numérotation chronologique dans le module Comptabilité client affecte les documents suivants :

-   Facture financière
-   N° document de facture financière
-   Avoir financier
-   N° document d’avoir financier
-   Facture client
-   Document de facture client
-   Avoir sur vente
-   N° document d’avoir sur vente

## <a name="prerequisites"></a>Conditions préalables

| Catégorie            | Logiciel requis                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pays/région  | L’adresse principale de l’entité juridique doit être en France.|
| Paramètres      | Définissez **Numérotation chronologique** sur **Oui** sur la page **Paramètres de la comptabilité client**, de l’onglet **Mises à jour**.                                                                                                                                                                                                |
| Tâches associées de paramétrage | Dans la page **Souches de numéros**, définissez autant de souches de numéros qu’il est nécessaire pour couvrir les périodes fiscales affectées. Vous devez spécifier une société pour chaque souche de numéros. Les segments des souches de numéros doivent être définis de manière à fournir l’ordre chronologique des périodes. Par exemple, les noms de segment peuvent contenir un préfixe spécial qui identifie une période spécifique.  |

## <a name="set-up-chronological-numbering"></a>Paramétrer la numérotation chronologique
### <a name="accounts-receivable-parameters"></a>Paramètres de la comptabilité client

Dans la page **Paramètres de la comptabilité client**, sous l’onglet **Souches de numéros**, sélectionnez l’une des références prises en charge, par exemple **Facture financière**. Cliquez ensuite sur le bouton **Paramétrage de la numérotation chronologique** qui sera disponible pour les références prises en charge. Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.

![Paramétrage des numéros chronologiques.](media/emea-chronological-numbering.jpg)

### <a name="number-sequence-groups"></a>Groupes de souches de numéros

Si différents clients utilisent différents modèles de numérotation, vous devez paramétrer la numérotation chronologique au niveau du groupe de souches de numéros. Dans la page **Paramètres de la comptabilité client**, sous l’onglet **Souches de numéros**, sélectionnez l’une des références prises en charge, puis cliquez sur **Groupe**. Dans la page **Groupe de souches de numéros**, sélectionnez un groupe existant ou créez-en un. Dans la section **Référence**, sélectionnez l’une des références prises en charge, puis cliquez sur **Paramétrage de la numérotation chronologique**. Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.

## <a name="invoice-posting"></a>Validation de facture
Lorsque vous validez une facture ou un avoir, la souche de numéros appropriée est utilisée pour générer un numéro. Cette souche de numéros est sélectionnée selon la période valide contenant la date de la facture. La numérotation chronologique spécifique au client a une priorité plus élevée que la numérotation chronologique.

### <a name="dates-control"></a>Contrôle des dates

Le système effectue un contrôle supplémentaire des dates de factures pour les factures clients : 

- La validation de nouvelles factures avec des dates antérieures à la date de la dernière facture validée est interdite si aucun code motif n’est défini. Pour activer la validation, un code motif doit être saisi soit dans un en-tête de facture/commande, soit dans l’une des lignes.
- Un avertissement est émis si la nouvelle date de facturation est postérieure à la date système.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]