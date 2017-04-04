---
title: "État de bordereau de paiement pour Europe"
description: "Cette rubrique fournit des informations sur les états de bordereau de paiement pour Europe."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264604
ms.assetid: 551e047b-4581-4a77-b470-c4f8d395c375
ms.search.region: Belgium, Denmark, Finland, Norway, Switzerland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: c795466753ca1515790b7961b989aac6e7d63c2c
ms.lasthandoff: 03/31/2017


---

# <a name="payment-slip-report-for-europe"></a>État de bordereau de paiement pour Europe

Cette rubrique fournit des informations sur les états de bordereau de paiement pour Europe.

La fonctionnalité pour les états de bordereau de paiement est disponible pour les entités juridiques dont l'adresse principale au Danemark, en Belgique, en Norvège, en Suisse, ou en Finlande. Les entreprises connectent souvent les bordereaux de paiement imprimés aux factures pour fournir une référence de paiement pour la validation et le règlement. Les bordereaux de paiement peuvent être utilisés pour les factures de projet ou de service, les lettres de relance, les notes d'intérêt et les relevés de compte, en plus des factures client et des factures financières.

## <a name="set-up-a-creditor-id-number-denmark-only"></a>Paramétrage d'un ID créditeur (Danemark uniquement)
Procédez comme suit pour entrer le numéro d'identification (ID) du créditeur de votre société. Votre institution financière fournit ce nombre. Il l'a utilisé comme référence lorsque les paiements client sont reçus via les institutions financières.

1.  Cliquez sur ** Administration d'organisation ** &gt; ** paramétrage ** &gt; ** organisation ** &gt; ** entités juridiques **.
2.  Sous ** les informations de compte bancaire ** l'organisateur, dans ** ID de Fi- créditeur ** le champ, entrez votre numéro d'identification à huit chiffres de créditeur.
3.  Fermez l'écran pour enregistrer vos modifications.

## <a name="set-up-a-payment-slip-attachment-format-for-invoices-interest-notes-collection-letters-and-account-statements"></a>Paramétrage d'un format de bordereau de paiement associé aux factures, des notes d'intérêts, des lettres de relance, et les relevés de compte
Procédez comme suit pour paramétrer un format pour les bordereaux de paiement associé qui accompagnent les factures client, factures financières, aux notes d'intérêts, des lettres de relance, et les relevés de compte.

1.  Cliquez sur ** Ventes ** &gt; ** paramétrage ** &gt; ** écrans ** &gt; ** l'écran paramètre **.
2.  Sous ** facture ** onglet, dans ** pièce jointe relatives au paiement de la facture client ** le champ, sélectionnez le format de bordereau de paiement associé.
3.  Sous ** facture financière **, ** note d'intérêt **, ** lettre de relance **, et ** relevé de compte ** onglets, sélectionnez un format de bordereau de paiement associé pour chaque type de document.
4.  Fermez l'écran pour enregistrer vos modifications.

Procédez comme suit pour paramétrer un format pour les bordereaux de paiement associé qui accompagnent les factures de projet.

1.  Cliquez sur ** Gestion de projets et comptabilité ** &gt; ** paramétrage ** &gt; ** écrans ** &gt; ** l'écran paramètre **.
2.  Dans ** pièce jointe relatives au paiement ** le champ, sélectionnez le format de bordereau de paiement associé.

## <a name="assign-a-payment-slip-attachment-format-to-a-customer-account"></a>Affectation d'un format de bordereau de paiement associé à un compte client
Après avoir défini le format de bordereau de paiement associé aux factures client, factures financières, aux notes d'intérêts, des lettres de relance, des relevés de compte, et les factures de projet, vous pouvez affecter des formats spécifiques pour un client sélectionné.

1.  Cliquez sur ** Ventes ** &gt; ** Courant ** &gt; ** clients ** &gt; ** tous les clients **.
2.  Créez un client, ou sélectionnez -en un.
3.  Sous ** facture et livraison ** l'organisateur, dans ** Dans une facture client **, ** Dans une facture financière **, ** Dans une note d'intérêt **, ** Dans une lettre de relance **, ** Dans une facture de projet **, et ** dans un relevé de compte ** des champs, sélectionnez le format pour les bordereaux de paiement associé chargé les documents de chaque type envoyés au client sélectionné.
4.  Fermez l'écran pour enregistrer vos modifications.



