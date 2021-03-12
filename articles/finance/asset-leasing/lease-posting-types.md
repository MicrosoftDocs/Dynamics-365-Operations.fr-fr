---
title: Types de validations de baux
description: Cette rubrique décrit les types de validation utilisés pour les transactions de crédit-bail.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b79b02f7e241783d19a315ccff5bb6874a238c38
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995416"
---
# <a name="lease-posting-types"></a>Types de validations de baux

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les types de validation utilisés pour les transactions de crédit-bail.

## <a name="lease-asset"></a>Actif loué

Le compte est associé au droit d’utilisation de l’actif (ROU). Ce compte est débité lors de la comptabilisation initiale d’un contrat de location selon les nouvelles normes comptables des contrats de location, les normes comptables Codification Topic 842 (ASC 842) et l’International Financial Reporting Standard 16 (IFRS 16). Pour un bail modifié, ce compte peut être soit débité, soit crédité, selon que la modification augmente ou diminue la dette locative.

**Exemples d’écritures de journal :** Reconnaissance initiale<br>
**Débit :** Actif de location XXX<br>
**Crédit :** Passif locatif XXX

## <a name="lease-liability"></a>Passif locatif

Le compte est associé au passif locatif qui survient lorsque les paiements sont actualisés selon les nouvelles normes IFRS 16 et ASC 842. Ce compte est crédité lorsqu’un contrat de location est initialement reconnu selon les nouvelles normes. Il est débité pour les paiements de location et crédité pour les intérêts courus.

**Exemples d’écritures de journal :** Reconnaissance initiale<br>
**Débit :** Actif de location XXX<br>
**Crédit :** Passif locatif XXX

**Exemples d’écritures de journal :** Intérêts courus<br>
**Débit :** Dépenses d’intérêts XXX<br>
**Crédit :** Passif locatif XXX

**Exemples d’écritures de journal :** Paiement de location<br>
**Débit :** Passif locatif XXX<br>
**Crédit :** Fournisseur payable/paiement de location XXX

## <a name="short-term-lease-liability"></a>Passif locatif à court terme

Le compte est associé au passif de location à court terme lorsque l’écriture de journal de reclassement de passif locatif à court terme est comptabilisée. Ce compte est crédité du passif à court terme à partir du tableau d’amortissement du dernier jour du mois. Cependant, le même montant est débité le premier jour du mois suivant.

**Exemples d’écritures de journal :** Reclassement du passif locatif à court terme<br>
**Débit :** Passif locatif XXX<br>
**Crédit :** Passif locatif à court terme XXX<br>
**Débit :** Passif locatif à court terme XXX<br>
**Crédit :** Passif locatif XXX

## <a name="depreciation-expense"></a>Dépenses d’amortissement

Le compte est associé à la charge liée à l’amortissement du droit d’utilisation de l’actif selon IFRS 16, ASC 842 et aux contrats de location-financement selon IAS 17 et ASC 840. Ce compte est débité lorsqu’un droit d’utilisation de l’actif est amorti chaque mois.

**Exemples d’écritures de journal :** régularisation d’amortissement<br>
**Débit :** Dépenses d’amortissement XXX<br>
**Crédit :** Amortissement cumulé XXX

## <a name="gainloss-on-lease-modification"></a>Profit/perte suite à la modification du bail

Le compte est associé à tous les gains ou pertes résultant de modifications du bail. Un gain peut survenir lors d’une modification de contrat de location si la modification diminue le passif de location d’un montant qui dépasse la valeur comptable du droit d’utilisation de l’actif.

Par exemple, un contrat de location a une valeur comptable actuelle du passif de location de 150 000 $ et une valeur comptable du droit d’utilisation de l’actif de 100 000 $. Le bail est modifié, et cette modification produit une nouvelle valeur actuelle des futurs paiements minimaux de location (PVFMLP) de 40 000 $. Par conséquent, le passif locatif sera débité de 110 000 $ (150 000 $ – 40 000 $). Étant donné que le droit d’utilisation de l’actif est uniquement de 100 000 $, la diminution de 110 000 $ diminuera l’actif au-delà de 0 (zéro). Par conséquent, les directives comptables indiquent que le solde doit être comptabilisé dans un compte de gain. Dans ce cas, l’écriture de journal finale sera un débit du passif locatif pour 110 000 $, un crédit sur l’actif de location pour 100 000 $ et un crédit sur le compte de gain pour 10 000$.

**Exemples d’écritures de journal :** Modification de location<br>
**Débit :** Passif locatif XXX<br>
**Crédit :** Actif de location XXX<br>
**Crédit :** Gain XXX

## <a name="accumulated-depreciation"></a>Amortissement cumulé

Le compte est associé au compte de contre-actif du droit d’utilisation de l’actif. Ce compte est crédité lorsqu’une dépense d’amortissement est validée.

**Exemples d’écritures de journal :** régularisation d’amortissement<br>
**Débit :** Dépenses d’amortissement XXX<br>
**Crédit :** Dépense d’amortissement XXX

## <a name="retained-earnings"></a>Bénéfices non répartis

Compte associé à la facture aux bénéfices non répartis. Ce compte peut être débité ou crédité dans une écriture de journal d’ajustement de transition en utilisant la méthode rétrospective complète ou la méthode de l’option de rattrapage cumulatif A. La différence entre le droit d’utilisation de l’actif initial et le passif locatif est comptabilisée en bénéfices non répartis. Dans de rares cas, les bénéfices non répartis peuvent également être affectés lors de la modification du contrat de location, si la classification d’un contrat de location est modifiée de financement en exploitation pour déprécier le droit d’utilisation de l’actif à la hausse ou à la baisse de sorte qu’il équivaut au passif de location.

**Exemples d’écritures de journal :** Ajustement de transition (méthode rétrospective complète ou de rattrapage cumulatif option A)<br>
**Débit :** Passif locatif XXX<br>
**Crédit :** Actif de location XXX<br>
**Crédit :** Bénéfices non répartis XXX

## <a name="variable-payment"></a>Paiement variable

Le compte est associé à des loyers variables qui sont produits par une réévaluation d’indice selon les contrats de location ASC 842, ASC 840 et IAS 17. Dans l’échéancier des paiements de location, les paiements variables sont inclus dans la colonne **Paiement variable**. Ce compte est débité lorsqu’une facture est créée sur une ligne d’échéancier de paiement qui contient un paiement variable.

**Exemples d’écritures de journal :** Paiement de location<br>
**Débit :** Passif locatif XXX<br>
**Débit :** Paiement variable XXX<br>
**Crédit :** Fournisseur payable/paiement de location XXX

## <a name="deferred-rent-asset-liability"></a>Actif du loyer reporté (passif)

Le compte est associé à l’actif ou au passif locatif différé qui est produit par un contrat de location-traitement différé. Ce compte est débité lorsqu’une facture est imputée à un bail de traitement de loyer différé, si le montant du paiement du loyer est supérieur à la charge de loyer linéaire de la période. Il est crédité si le paiement du loyer est inférieur au loyer linéaire de la période.

**Exemples d’écritures de journal :** Paiement de location (bail de traitement de loyer différé)<br>
**Débit :** Frais de location XXX<br>
**Crédit :** Actif du loyer reporté XXX<br>
**Crédit :** Fournisseur payable/paiement de location XXX

## <a name="lease-expense"></a>Dépense de bail

Le compte est associé à la charge de location si le contrat de location est classé comme contrat de location avec traitement de loyer différé. Ce compte est débité lorsqu’une facture est imputée à un bail de traitement à loyer différé.

**Exemples d’écritures de journal :** Paiement de location (bail de traitement de loyer différé)<br>
**Débit :** Frais de location XXX<br>
**Crédit :** Actif du loyer reporté XXX<br>
**Crédit :** Fournisseur payable/paiement de location XXX

## <a name="impairment-expense"></a>Dépense de dépréciation

Le compte est comptabilisé lorsqu’un bail est déprécié. Ce compte est débité, tandis que le compte de droit d’utilisation de l’actif est directement crédité.

**Exemples d’écritures de journal :** Paiement de location<br>
**Débit :** Dépense de dépréciation XXX<br>
**Crédit :** Droit d’utilisation de l’actif XXX

## <a name="lease-payment"></a>Paiement de loyer

Le compte est validé si le paramètre **Payer au fournisseur** est désactivé. Ce compte est crédité à la place du montant payable au fournisseur si le paramètre est désactivé.

**Exemples d’écritures de journal :** Paiement de location<br>
**Débit :** Passif locatif XXX<br>
**Crédit :** Paiement de location XXX

## <a name="expense-type-postings"></a>Écritures de type de dépense

Le compte sélectionné pour chaque type de dépense est débité lorsqu’un paiement pour ce type de dépense est généré. Par exemple, le compte spécifié pour le type de dépense **Assurance** est débité chaque fois qu’une facture ou une écriture de journal de paiement est créée à partir du barème des coûts exécutoire pour les dépenses d’assurance.

**Exemples d’écritures de journal :** Paiement de l’assurance<br>
**Débit :** Compte de type de dépenses d’assurance XXX<br>
**Crédit :** Compte de compensation XXX

> [!NOTE]
> Le compte de contrepartie est sélectionné au niveau du contrat de location sur les lignes de l’échéancier de paiement des coûts exécutoires. Ce compte de contrepartie peut être associé au fournisseur ou à un compte général.
