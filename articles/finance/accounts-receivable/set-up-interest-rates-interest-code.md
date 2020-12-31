---
title: Paramétrage des taux d’intérêt pour un code intérêt
description: Les codes intérêt contiennent des paramètres qui déterminent quand les intérêts sont facturés et comment ils sont calculés sur les comptes qui présentent des retards.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a3ca43503ecbe8e814958576e46ced10bfe9ad49
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443071"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a>Paramétrage des taux d’intérêt pour un code intérêt

[!include [banner](../includes/banner.md)]

Les codes intérêt contiennent des paramètres qui déterminent quand les intérêts sont facturés et comment ils sont calculés sur les comptes qui présentent des retards.

Vous pouvez paramétrer un seul code intérêt et l’appliquer à plusieurs profils de validation client, codes de facturation ou à des lignes de factures spécifiques. Lorsque les détails du code intérêt sont modifiés, toutes les fonctionnalités qui utilisent le code appliquent automatiquement les modifications aux nouvelles transactions. Vous pouvez paramétrer deux types de taux pour chaque code intérêt :
-   Taux pour les intérêts créditeurs − Ils représentent des revenus gagnés en facturant des intérêts sur les factures ou les notes d’intérêt.
-   Taux pour les intérêts payés − Ils représentent un coût payé pour les intérêts sur les avoirs.

Ces deux types de taux peuvent exister simultanément et dans le même code intérêt. Les taux d’intérêt peuvent être basés sur trois types de calcul :
-   Intérêts par pourcentage.
-   Intérêts par montant.
-   Intérêts par tranche, qui résulte en un pourcentage ou montant unique.

Lorsqu’un code intérêt est utilisé pour calculer des intérêts, une note d’intérêt séparée est créée pour chaque taux d’intérêt qui prend effet lorsque le paiement est effectué après la date d’échéance de la transaction. L’onglet **Rémunérations** de la page **Code intérêt** vous permet de paramétrer les taux d’intérêt pour les intérêts que vous obtenez en facturant un intérêt. L’onglet **Paiements** vous permet de paramétrer les taux d’intérêt pour les intérêts que vous payez.

## <a name="interest-rates-based-on-a-percentage"></a>Taux d’intérêt basés sur un pourcentage
Vous pouvez paramétrer des taux d’intérêt qui calculent un pourcentage spécifié.

- Le montant des intérêts s’applique à toutes les devises.
- Vous pouvez spécifier des limites du montant des intérêts facultatives.
- L’option <strong>Pourcentage</strong> est sélectionnée** <strong>dans le champ **Calculer les intérêts sur base de</strong> de la page <strong>Paramétrer les codes intérêt</strong>.

Par exemple, pour paramétrer un code intérêt qui évalue 5 % d’intérêts pour chaque période de deux mois après la date d’échéance de la transaction pour le paiement de la facture, entrez 2 dans le champ **Calculer les intérêts tous les** et sélectionnez **Mois**.

## <a name="interest-rates-based-on-amounts"></a>Taux d’intérêt basés sur des montants
Vous pouvez paramétrer des taux d’intérêt qui calculent un montant spécifié par devise.
- Un montant des intérêts est spécifié pour chaque devise dans le code intérêt.
- Vous pouvez spécifier des limites du montant des intérêts facultatives.
- L’option **Montant** est sélectionnée dans le champ **Calculer les intérêts sur base de** de la page **Paramétrer les codes intérêt**.

Par exemple, pour paramétrer un code intérêt qui évalue un intérêt de 25,00 pour chaque période de 20 jours après la date d’échéance de la transaction pour le paiement de la facture, entrez 20 dans le champ **Calculer les intérêts tous les** et sélectionnez **Jour**.

## <a name="interest-rates-based-on-ranges"></a>Taux d’intérêt basés sur des plages
Vous pouvez paramétrer des taux d’intérêt qui varient selon le montant en retard, le nombre de jours de retard de paiement, ou le nombre de mois de retard de paiement.
-   L’onglet **Bénéfices par devise** permet de définir des paramètres d’intérêt spécifiques pour chaque devise. Il vous permet également de définir la tranche.
-   Utilisez le bouton **Plages** pour ajouter des lignes qui représentent les plages à paramétrer. La valeur **De** représente le début de la plage et le nombre **Valeur des intérêts** représente soit un pourcentage soit un montant, en fonction de la sélection du champ **Calculer les intérêts sur base de** de la page **Paramétrer les codes intérêt**.

## <a name="example-1-interest-by-range--amount"></a>Exemple 1 : Intérêts par tranche = montant
Vous paramétrez un code intérêt qui évalue un intérêt une fois pour chaque période de trois mois après la date d’échéance de la transaction pour le paiement de la facture. Vous souhaitez baser le calcul sur une valeur d’intérêts par pourcentage, selon des intervalles de montants par paliers. La valeur des intérêts est 1 % pour les montants de facture jusqu’à 1 000,00, 2 % pour les montants compris entre 1 001,00 et 5 000,00, et 3 % pour les montants supérieurs à 5 000,00. Vous paramétrez les valeurs du champ Code intérêt comme suit.

| **Nom de champ**                  | **Valeur de champ** |
|---------------------------------|-----------------|
| **Code intérêt**               | 3M%ByAmt        |
| **Calculer chaque intérêt**    | 3/Mois         |
| **Intérêts par tranche**           | Montant          |
| **Calculer les intérêts sur base de** | Pourcentage      |

Vous devez paramétrer les informations de tranches comme suit.

| **Valeur de début** | **Valeur des intérêts** |
|----------------|--------------------|
| 0              | 1                  |
| 1,001          | 2                  |
| 5,001          | 3                  |


## <a name="example-2-interest-by-range--days"></a>Exemple 2 : Intérêts par tranche = jours
--------------------------------------------------

Vous paramétrez un code intérêt qui évalue un intérêt une fois pour chaque période de 15 jours après la date d’échéance de la transaction pour le paiement de la facture. Vous souhaitez baser le calcul sur une valeur d’intérêts par montant, selon des intervalles de jours par paliers. La valeur des intérêts est 10,00 par période de 15 jours pendant les 60 premiers jours, 15,00 par période de 15 jours pendant les jours 61 à 90 et 20,00 par période de 15 jours après le 91e jour. Vous paramétrez les valeurs du champ Code intérêt comme suit.

| **Nom de champ**                  | **Valeur de champ** |
|---------------------------------|-----------------|
| **Code intérêt**               | 15DAmtXDay      |
| **Calculer chaque intérêt**    | 15/Jour          |
| **Intérêts par tranche**           | Jours            |
| **Calculer les intérêts sur base de** | Montant          |

Vous devez paramétrer les informations de tranches comme suit.

| **Valeur de début** | **Valeur des intérêts** |
|----------------|--------------------|
| 0              | 10                 |
| 61             | 15                 |
| 91             | 20                 |


## <a name="example-3-interest-by-range--months"></a>Exemple 3 : Intérêts par tranche = mois
----------------------------------------------------

Vous paramétrez un code intérêt qui évalue un intérêt une fois pour chaque mois après la date d’échéance de la transaction pour le paiement de la facture. Vous souhaitez baser le calcul sur une valeur d’intérêts par pourcentage, selon des intervalles de mois par paliers. La valeur des intérêts sera de 1,5 % par mois pendant les trois premiers mois de retard, 2,0 % par mois pour les trois mois suivants, et 2,5 % par mois au delà des six premiers mois. Vous paramétrez les valeurs du champ Code intérêt comme suit.

| **Nom de champ**                  | **Valeur de champ** |
|---------------------------------|-----------------|
| **Code intérêt**               | 1M%ByMth        |
| **Calculer chaque intérêt**    | 1/Mois         |
| **Intérêts par tranche**           | Mois          |
| **Calculer les intérêts sur base de** | Pourcentage      |

Vous devez paramétrer les informations de tranches comme suit.

| **Valeur de début** | **Valeur des intérêts** |
|----------------|--------------------|
| 0              | 1.5                |
| 4              | 2                  |
| 7              | 2,5                |

## <a name="new-versions"></a>Nouvelles versions
Les codes intérêt sont soumis à la date d’effet. Si vous souhaitez modifier le taux d’intérêt, vous pouvez créer une **nouvelle version** effective à une date ultérieure.

Pour afficher des versions différentes, vous pouvez utiliser la sélection de menu **À partir du** pour sélectionner la date limite. Vous pouvez également sélectionner **Afficher tous les enregistrements** pour afficher tous les codes intérêt sur la page.



