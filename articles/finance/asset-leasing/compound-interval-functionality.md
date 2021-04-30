---
title: Fonctionnalité d’intervalle composé
description: Cette rubrique fournit des informations qui vous aideront à choisir parmi les intervalles composés mensuels, trimestriels, semestriels et annuels.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f8c19a523251b0f1c90de746e380f58be4851ddd
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881298"
---
# <a name="compounding-interval-functionality"></a>Fonctionnalité d’intervalle composé

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique fournit des informations qui vous aideront à choisir parmi les intervalles composés mensuels, trimestriels, semestriels et annuels. La fonctionnalité d’intervalle composé est utilisée pour déterminer le nombre de périodes de composition par an dans l’échéancier de paiement d’un bail. Chacun des quatre exemples de cette rubrique montre à quoi ressemblera l’échéancier de paiement d’un bail pour un intervalle différent.

Vous ne pouvez pas sélectionner un intervalle composé moins fréquent que la fréquence de paiement du bail. Par exemple, un intervalle composé trimestriel ne peut pas être utilisé avec une fréquence de paiement mensuelle, et un intervalle composé annuel ne peut pas être utilisé avec une fréquence de paiement semestrielle. Si vous essayez de sélectionner un intervalle composé moins fréquent que la fréquence de paiement du bail, vous recevez un message d’erreur.

> [!NOTE]
> Dans les quatre exemples de cette rubrique, l’intervalle composé correspond à la fréquence de paiement.

## <a name="examples"></a>Exemples

### <a name="setup-for-all-four-leases"></a>Configuration pour les quatre baux

Les tableaux suivants présentent les valeurs définies sur les onglets **Général** et **Lignes de l’échéancier de paiement** pour les quatre baux utilisés dans les exemples.

**Onglet Général**

| Champ                      | Valeur                        |
|----------------------------|------------------------------|
| Taux d’emprunt marginal | **5 %%**                       |
| Type d’annuité               | **Annuité ordinaire**         |
| Intervalle de composition       | Voir les exemples individuels. |
| Fréquence de paiement          | **Tous les mois**                  |
| Date d’entrée en vigueur          | **01/01/2020**                 |

**Onglet Lignes d’échéancier de paiement**

| Champ             | Valeur                        |
|-------------------|------------------------------|
| Date de début        | **01/01/2020**                 |
| Périodes           | **120**                      |
| Intervalle de périodes   | **Mois**                   |
| Date de fin          | **31/12/2029**               |
| Fréquence de paiement | Voir les exemples individuels. |
| Montant du paiement    | **50,000**                   |

### <a name="lease-1-monthly-compounding-interval-and-monthly-payment-frequency"></a>Bail 1 : Intervalle composé mensuel et fréquence de paiement mensuelle

Le tableau suivant répertorie les 12 premiers mois de l’échéancier de paiement. Notez les informations suivantes :

- La valeur de la colonne « Période » augmente de 1 chaque mois, car chaque mois est un nouvel intervalle composé.
- Dans la formule de la colonne « Valeur actuelle », le taux est divisé par 12, car il y a 12 périodes de composition par an. L’exposant (c’est-à-dire le chiffre en exposant) est égal à la valeur de la colonne « Période ».

| Période | Mois | Date       | Montant du paiement | Valeur actuelle                                       |
|--------|-------|------------|----------------|-----------------------------------------------------|
| 1      | 1     | 31/01/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>1</sup> = 49 792,53  |
| 2      | 2     | 29/02/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>2</sup> = 49 585,92  |
| 3      | 3     | 31/03/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>3</sup> = 49 380,17  |
| 4      | 4     | 30/04/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>4</sup> = 49 175,28  |
| 5      | 5     | 31/05/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>5</sup> = 48 971,23  |
| 6      | 6     | 30/06/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>6</sup> = 48 768,03  |
| 7      | 7     | 31/07/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>7</sup> = 48 565,67  |
| 8      | 8     | 31/08/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>8</sup> = 48 364,15  |
| 9      | 9     | 30/09/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>9</sup> = 48 163,47  |
| 10     | 10    | 31/10/2020 | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>10</sup> = 47 963,62 |
| 11     | 11    | 30/11/2020 | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>11</sup> = 47 764,61 |
| 12     | 12    | 31/12/2020 | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 12\])<sup>12</sup> = 47 566,41 |

### <a name="lease-2-quarterly-compounding-interval-and-quarterly-payment-frequency"></a>Bail 2 : Intervalle composé trimestriel et fréquence de paiement trimestrielle

Le tableau suivant répertorie les 12 premiers mois de l’échéancier de paiement. Notez les informations suivantes :

- La valeur de la colonne « Période » augmente de 1 chaque trimestre, car chaque trimestre est un nouvel intervalle composé.
- Dans la formule de la colonne « Valeur actuelle », le taux est divisé par 4, car il y a quatre périodes de composition par an. L’exposant est égal à la valeur dans la colonne « Période ».

| Période | Mois | Date       | Montant du paiement | Valeur actuelle                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/01/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 2     | 29/02/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 3     | 31/03/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 4\])<sup>1</sup> = 49 382,72 |
| 2      | 4     | 30/04/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 5     | 31/05/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 6     | 30/06/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 4\])<sup>2</sup> = 48 773,05 |
| 3      | 7     | 31/07/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 8     | 31/08/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 9     | 30/09/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 4\])<sup>3</sup> = 48 170,92 |
| 4      | 10    | 31/10/2020 | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 11    | 30/11/2020 | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 12    | 31/12/2020 | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 4\])<sup>4</sup> = 47 576,21 |

> [!NOTE]
> Si le type de rente est changé sur la valeur **Rente due**, le paiement se fera au début du trimestre au lieu de la fin du trimestre.

### <a name="lease-3-semiannual-compounding-interval-and-semiannual-payment-frequency"></a>Bail 3 : Intervalle composé semestriel et fréquence de paiement semestrielle

Le tableau suivant répertorie les 12 premiers mois de l’échéancier de paiement. Notez les informations suivantes :

- La valeur de la colonne « Période » augmente de 1 tous les six mois, car chaque semestre est un nouvel intervalle composé.
- Dans la formule de la colonne « Valeur actuelle », le taux est divisé par 2, car il y a deux périodes de composition par an. L’exposant est égal à la valeur dans la colonne « Période ».

| Période | Mois | Date       | Montant du paiement | Valeur actuelle                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/01/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 2     | 29/02/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 3     | 31/03/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 4     | 30/04/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 5     | 31/05/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 6     | 30/06/2020  | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 2\])<sup>1</sup> = 48 780,49 |
| 2      | 7     | 31/07/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 8     | 31/08/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 9     | 30/09/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 10    | 31/10/2020 | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 11    | 30/11/2020 | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 12    | 31/12/2020 | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 2\])<sup>2</sup> = 47 590,72 |

> [!NOTE]
> Si le type de rente passe sur la valeur **Rente due**, le paiement se fera en janvier et juillet au lieu de juin et décembre.

### <a name="lease-4-annual-compounding-interval-and-annual-payment-frequency"></a>Bail 4 : Intervalle composé annuel et fréquence de paiement annuelle

Le tableau suivant répertorie les 12 premiers mois de l’échéancier de paiement. Notez les informations suivantes :

- La valeur de la colonne « Période » augmente de 1 tous les 12 mois, car chaque année est un nouvel intervalle composé.
- Dans la formule de la colonne « Valeur actuelle », le taux est divisé par 1, car il y a une période de composition par an. L’exposant est égal à la valeur dans la colonne « Période ».

| Période | Mois | Date       | Montant du paiement | Valeur actuelle                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/01/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 2     | 29/02/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 3     | 31/03/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 4     | 30/04/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 5     | 31/05/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 6     | 30/06/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 7     | 31/07/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 8     | 31/08/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 9     | 30/09/2020  | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 10    | 31/10/2020 | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 11    | 30/11/2020 | 0,00           | 0,00 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 12    | 31/12/2020 | 50,000.00      | 50 000 ÷ (1 + \[5 %% ÷ 1\])<sup>1</sup> = 47 619,05 |

> [!NOTE]
> Si le type de rente passe sur la valeur **Rente due**, le paiement se fera en janvier plutôt qu’en décembre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
