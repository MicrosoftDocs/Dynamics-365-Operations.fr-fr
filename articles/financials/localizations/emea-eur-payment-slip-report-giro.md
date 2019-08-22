---
title: État du bordereau de paiement pour l'Europe
description: Cette rubrique fournit des informations sur les états de bordereau de paiement pour l'Europe.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMLegalEntities, ProjFormletterParameters, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264604
ms.search.region: Belgium, Denmark, Finland, Norway, Switzerland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cbbfa25252074cd371b271be2f0f03ad2a687944
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852263"
---
# <a name="payment-slip-report-for-europe"></a>État du bordereau de paiement pour l'Europe

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les états de bordereau de paiement pour l'Europe.

La fonctionnalité pour les états de bordereau de paiement est disponible pour les entités juridiques dont l'adresse principale est située au Danemark, en Belgique, en Norvège, en Suisse ou en Finlande. Les entreprises associent souvent les bordereaux de paiement imprimés aux factures pour fournir une référence de paiement pour la validation et le règlement. Les bordereaux de paiement peuvent être utilisés pour les factures de projet ou de service, les lettres de relance, les notes d'intérêt et les relevés de compte, en plus des factures client et des factures financières.

## <a name="set-up-a-creditor-id-number-denmark-only"></a>Paramétrage d'un ID créditeur (Danemark uniquement)
Suivez les étapes ci-après pour entrer l'ID créditeur de votre société. Votre institution financière fournit ce numéro. Il sert de référence lorsque les paiements client sont reçus via les institutions financières.

1.  Cliquez sur **Administration d'organisation** &gt; **Paramétrage** &gt; **Organisation** &gt; **Entités juridiques**.
2.  Dans l'organisateur **Informations sur le compte en banque**, dans le champ **ID créditeur financier**, entrez votre ID créditeur à huit chiffres.
3.  Fermez l'écran pour enregistrer vos modifications.

## <a name="set-up-a-payment-slip-attachment-format-for-invoices-interest-notes-collection-letters-and-account-statements"></a>Paramétrage d'un format de bordereau de paiement associé aux factures, notes d'intérêt, lettres de relance et relevés de compte
Suivez les étapes ci-après pour paramétrer un format pour les bordereaux de paiement associés aux factures client, aux factures financières, aux notes d'intérêt, aux lettres de relance et aux relevés de compte.

1.  Cliquez sur **Comptabilité client** &gt; **Paramétrage** &gt; **Écrans** &gt; **Paramétrage d'écran**.
2.  Sous l'onglet **Facture**, dans le champ **Document de paiement associé de facture client**, sélectionnez le format du bordereau de paiement associé.
3.  Sous les onglets **Facture financière**, **Note d'intérêt**, **Lettre de relance** et **Relevé de compte**, sélectionnez un format de bordereau de paiement associé pour chaque type de document.
4.  Fermez l'écran pour enregistrer vos modifications.

Suivez les étapes ci-après pour paramétrer un format pour les bordereaux de paiement associés aux factures de projet.

1.  Cliquez sur **Gestion de projet et comptabilité** &gt; **Paramétrage** &gt; **Écrans** &gt; **Paramétrage d'écran**.
2.  Dans le champ **Document de paiement associé**, sélectionnez le format du bordereau de paiement associé.

## <a name="assign-a-payment-slip-attachment-format-to-a-customer-account"></a>Affectation d'un format de bordereau de paiement associé à un compte client
Après avoir paramétré le format du bordereau de paiement associé aux factures client, aux factures financières, aux notes d'intérêt, aux lettres de relance, aux relevés de compte et aux factures de projet, vous pouvez affecter des formats spécifiques au client sélectionné.

1.  Cliquez sur **Comptabilité client** &gt; **Commun** &gt; **Clients** &gt; **Tous les clients**.
2.  Créez un client ou sélectionnez-en un.
3.  Dans l'organisateur **Facture et livraison**, dans les champs **Sur une facture client**, **Sur une facture financière**, **Sur une note d'intérêt**, **Sur une lettre de relance**, **Sur une facture de projet** et **Sur un relevé de compte**, sélectionnez le format des bordereaux de paiement associés aux documents de chaque type qui sont envoyés au client sélectionné.
4.  Fermez l'écran pour enregistrer vos modifications.




