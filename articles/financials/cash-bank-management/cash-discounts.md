---
title: "Escomptes de règlement"
description: "Les escomptes de règlement sont paramétrés et partagés pour la Comptabilité fournisseur et la Comptabilité client.  L'escompte de règlement disponible peut être défini sur la facture client ou la facture fournisseur, et sera utilisé si la facture est payée pendant la période d'escompte de règlement."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 668e3ebdd2729efb48e2833fd5beec3cefdb17b0
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="cash-discounts"></a>Escomptes de règlement

[!INCLUDE [banner](../includes/banner.md)]

Les escomptes de règlement sont paramétrés et partagés pour la Comptabilité fournisseur et la Comptabilité client.  L'escompte de règlement disponible peut être défini sur la facture client ou la facture fournisseur, et sera utilisé si la facture est payée pendant la période d'escompte de règlement. 

<a name="cash-discounts"></a>Escomptes de règlement
--------------

Les escomptes de règlement à la fois pour les clients ou les fournisseurs peuvent être créés dans la page Escomptes de règlement. À l'aide du champ Code remise suivant, vous pouvez également définir une série d'escomptes de règlement qui se succèdent au fur et à mesure que les dates des escomptes de règlement précédentes expirent. Pour plus d'informations, voir la section « Exemple : série d'escomptes de règlement » plus loin dans cette rubrique. Si la facture, la transaction créditrice (paiement ou avoir), voire les deux, utilisent une devise autre que la devise comptable de l'entité juridique, l'escompte de règlement est calculé en fonction de la date du paiement ou de l'avoir. Si la facture et le document de crédit sont indiqués dans des entités juridiques différentes, et si les devises comptables des entités juridiques diffèrent, le taux de change est tiré de l'entité juridique de la facture, à la date du document de crédit. Pour plus d'informations, voir la section « Exemple : taux de change des escomptes de règlement » plus loin dans cette rubrique.
Commande par défaut du compte principal d'escompte de règlement
----------------------------------------------

Si une facture est réglée à temps pour justifier l'obtention d'un escompte de règlement, celui-ci est automatiquement validé sur un compte principal des escomptes de règlement, conformément à la priorité par défaut suivante :
1.  Le compte principal spécifié dans le champ Autre compte des escomptes de règlement sur la page Régler les transactions en cours - client ou la page Régler les transactions en cours - fournisseur.
2.  Le compte principal spécifié dans le champ Client - Escompte de règlement ou le champ Fournisseur - Escompte de règlement du groupe de validation dans la comptabilité affecté au code taxe de la facture. Paramétrez des groupes de validations dans la comptabilité sur la page Groupes de validations dans la comptabilité et affectez-les aux codes taxe de la page Codes taxe.
3.  Le compte de validation principal de la page Escomptes de règlement dans le champ Compte principal pour les remises client ou le champ Compte principal pour les remises fournisseur pour le code d'escompte de règlement figurant sur la facture réglée.
4.  Le compte principal pour les escomptes de règlement, tel que défini dans la page Comptes pour transactions automatiques.

## <a name="example-series-of-cash-discounts"></a> Exemple : série d'escomptes de règlement
Paramétrez trois codes escompte de règlement comme suit :
-   Code 5D10% : escompte de règlement de 10 % si le montant est réglé sous 5 jours.
-   Code 10D5% : escompte de règlement de 5 % si le montant est réglé sous 10 jours.
-   Code 14D2% : escompte de règlement de 2 % si le montant est réglé sous 14 jours.

Dans le champ Code remise suivant :
-   Pour le code 5D10%, sélectionnez 10D5%.
-   Pour le code 10D5%, sélectionnez 14D2%.
-   Pour le code 14D2%, laissez le champ Code remise suivant vide.

Les trois escomptes de règlement se succèdent lorsque la date de paiement dépasse la date d'escompte de règlement précédente sur la facture. Un seul escompte de règlement est accordé lorsque la facture est payée, en fonction de la date d'escompte de règlement qui est respectée dans la séquence d'escomptes de règlement.

## <a name="example-exchange-rates-for-cash-discounts"></a> Exemple : taux de change des escomptes de règlement
La devise comptable de votre entité juridique est EUR et les taux de change suivants sont spécifiés pour la devise USD :
-   1er février = 110
-   1er mars = 80

Une facture de 1 000 USD avec des conditions d'escompte de règlement de 20D2% est validée le 15 février. Le montant de la facture, exprimé en devise comptable, est de 1 100 EUR. Un paiement de 980 USD est réglé avec la facture le 1er mars. Le montant de l'escompte de règlement est de 20 USD. Le montant du paiement en devise comptable est de 784 EUR. Le montant de l'escompte de règlement, exprimé en devise comptable, est calculé à partir du taux de change du 1er mars : 20 \* 80 / 100 = 16 EUR.

| **Remarque**                                                                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Si l'option Calcule les escomptes de règlement pour les paiements partiels est sélectionnée dans les pages Paramètres de la comptabilité client ou Paramètres de la comptabilité fournisseur, le taux de change en vigueur à la date de chaque paiement partiel est utilisé. |

 
=

 




