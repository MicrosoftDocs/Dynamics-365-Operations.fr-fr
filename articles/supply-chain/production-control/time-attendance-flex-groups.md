---
title: Groupes flexibles
description: Cette rubrique décrit la manière dont les groupes flexibles sont utilisés dans le module Pointage.
author: johanhoffmann
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgFlexGroup, JmgFlexCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 7628f2fc3d3a7e5bb1175edf59f856bc40f9b987
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102828"
---
# <a name="flex-groups"></a>Groupes flexibles

[!include[banner](../includes/banner.md)]

Les heures de travail flexibles permettent aux sociétés de minimiser les paiements des heures supplémentaires en offrant aux collaborateurs des congés supplémentaires pendant les périodes de charge de travail basse. Cette fonction est utile, par exemple, dans des segments qui rencontrent des changements saisonniers dans la charge de travail.

Vous pouvez utiliser les groupes flexibles pour définir les règles et principes suivants pour les heures flexibles d’un collaborateur :

- Règles pour les réglementations flexibles
- Principe de calcul du solde flexible du collaborateur

## <a name="set-up-flexible-working-hours-in-flex-groups"></a>Paramétrer des heures de travail flexibles dans des groupes flexibles

- Sélectionnez **Pointage** \> **Paramétrage** \> **Groupes** \> **Groupes flexibles** pour paramétrer les groupes flexibles pour des heures flexibles.

## <a name="associate-workers-with-flex-groups"></a>Associer les collaborateurs à des groupes flexibles

- Sélectionnez **Pointage** \> **Paramétrage** \> **Enregistrement du temps des collaborateurs**.

## <a name="rules-for-flex-regulations"></a>Règles pour les réglementations flexibles

Vous pouvez utiliser des règles pour les réglementations flexibles afin de définir des limites flexibles, ou le nombre minimal et maximal d’heures autorisées dans le compte flexible du collaborateur. Les limites flexibles sont paramétrées dans le groupe flexible. Lorsque les limites flexibles sont dépassées, le solde flexible et le salaire d’un collaborateur peuvent être ajustés.

Si le minimum flexible autorisé d’un collaborateur est dépassé (c’est-à-dire, si le nombre d’heures du compte flexible est inférieur au minimum spécifié), vous pouvez utiliser ces méthodes pour ajuster le solde flexible du collaborateur en créant une réglementation flexible :

- Le compte flexible du collaborateur peut être ajusté en fonction du minimum autorisé spécifié, mais sans déduire du salaire du collaborateur le nombre d’heures auquel le compte flexible est inférieur au minimum autorisé.
- Le salaire du collaborateur peut être déduit du nombre d’heures auquel le compte flexible est inférieur au minimum autorisé. Cette déduction est effectuée en générant des éléments de salaire pour un type de salaire spécifique avec une unité de salaire négative ou positive.

Si le maximum flexible autorisé du collaborateur est dépassé, vous pouvez utiliser ces méthodes pour ajuster le solde flexible du collaborateur en créant une réglementation flexible :

- Le compte flexible du collaborateur peut être réajusté en fonction du maximum autorisé spécifié, mais sans compenser le salaire du collaborateur du nombre d’heures auquel le collaborateur a travaillé au-dessus du maximum autorisé.
- Le nombre d’heures pendant lesquelles le collaborateur a travaillé au-dessus de la valeur maximale autorisée peut être converti en salaire. Cette conversion est effectuée en générant des éléments de salaire pour un type de salaire spécifique.

Vous pouvez ajuster un solde flexible dans les situations suivantes :

- Lorsqu’un fichier de paiement basé sur des données de paie est exporté à l’aide de la tâche **Transférer le salaire**. Les données de paie sont générées lorsque vous transférez l’enregistrement du collaborateur depuis la page **Approuver**.
- Lorsque la tâche **Ajuster le solde flexible** est traitée.

> [!NOTE]
> Les réglementations flexibles ne se produisent lors de l’approbation et du transfert des enregistrements d’opérations diverses quotidiens du collaborateur sur la page **Approuver**.

## <a name="principle-for-calculating-a-workers-flex-balance"></a>Principe de calcul du solde flexible d’un collaborateur

Le principe de calcul des heures selon lequel le solde flexible du collaborateur est ajusté est paramétré dans le groupe flexible. Sélectionnez **Pointage** \> **Paramétrage** \> **Groupes** \> **Groupes flexibles**. 

Vous pouvez utiliser les deux principes suivants :

- **Heure** – Les heures flexibles du collaborateur sont calculées uniquement à l’aide de l’heure d’enregistrement du jour du collaborateur. Lorsque les enregistrements quotidiens du collaborateur sont calculés, le nombre d’heures Flexibles+ et Flexibles- du jour est calculé à l’aide des zones Flexibles+ et Flexibles- définies dans le profil d’heure du collaborateur.
- **Types de salaire** – Les heures flexibles du collaborateur sont basées sur les revenus des types de salaire Flexibles+ et Flexibles- définis dans l’accord salarial du collaborateur. L’accord salarial est associé au collaborateur qualifié pour l’enregistrement des heures. Vous pouvez utiliser des types de salaire pour gérer des comptes flexibles si, par exemple, vous souhaitez augmenter le compte flexible d’un collaborateur d’un facteur spécifique dans une ou plusieurs zones flexibles.

### <a name="scenario-1-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-minimum-is-exceeded"></a>Scénario 1 : Ajustement du salaire et du compte flexible d’un collaborateur car le minimum flexible autorisé est dépassé

Un collaborateur pouvant effectuer des heures flexibles a un compte flexible négatif.

- **Compte flexible :** -4

Le collaborateur est associé à un groupe flexible qui a la configuration suivante :

- **Minimum flexible :** -0,5
- **Type de salaire minimal :** 1302
- **Facteur de type de salaire :** -1,00

Comme la différence entre le compte flexible du collaborateur et son minimum flexible autorisé l’indiquent, le collaborateur a dépassé son minimum flexible autorisé de 3,5 heures.

Lorsque l’administrateur de salaire transfère les données de salaire du collaborateur en exécutant la tâche **Transférer dans la paye** ou **Ajustement flexible**, les ajustements suivants sont effectués :

- Le compte flexible du collaborateur est ajusté de 3,5 heures. Par conséquent, le solde flexible de -4,0 heure est ajusté au minimum flexible autorisé du collaborateur de -0,5 heures.
- Un élément de salaire pour le type de salaire 1302 est créé. Cet élément de salaire a une unité de salaire de -3,5 heures qui seront déduites du salaire du collaborateur. Dans ce cas, l’unité de salaire est un nombre négatif, car l’ajustement positif de 3,5 heures est multiplié par le facteur négatif de type de salaire de -1,0 défini dans le groupe flexible. Cet élément de salaire fait partie du fichier de salaire généré par la tâche **Transférer dans la paye**.

### <a name="scenario-2-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-maximum-is-exceeded"></a>Scénario 2 : Ajustement du salaire et du compte flexible d’un collaborateur car le maximum flexible autorisé est dépassé

Un collaborateur pouvant effectuer des heures flexibles a un compte flexible positif.

- **Compte flexible :** 6

Le collaborateur est associé à un groupe flexible qui a la configuration suivante :

- **Maximum flexible :** 2,0
- **Type de salaire minimal :** 1302
- **Facteur de type de salaire :** -1,0

Comme la différence entre le compte flexible du collaborateur et son maximum flexible autorisé l’indique, le collaborateur a dépassé son maximum flexible autorisé de 4,0 heures.

Lorsque l’administrateur de salaire transfère les données de salaire du collaborateur en exécutant la tâche **Transférer dans la paye** ou **Ajustement flexible**, les ajustements suivants sont effectués :

- Le compte flexible de la collaboratrice est ajusté de -4,0 heures. Par conséquent, le solde flexible de 6,0 heure est ajusté au maximum flexible autorisé de la collaboratrice de 2,0 heures.
- Un élément de salaire pour le type de salaire 1302 est créé. Cet élément de salaire a une unité de salaire de 4,0 heures qui seront ajoutées du salaire da la collaboratrice. Dans ce cas, l’unité de salaire est un nombre positif, car l’ajustement négatif de 4,0 heures est multiplié par le facteur négatif de type de salaire de -1,0 défini dans le groupe flexible. Cet élément de salaire fait partie du fichier de salaire généré par la tâche **Transférer dans la paye**.

### <a name="scenario-3-managing-a-workers-flex-balance-based-on-pay-types"></a>Scénario 3 : Gestion du solde flexible d’un collaborateur selon les types de salaire

Comme expliqué plus tôt, les comptes flexibles peuvent être gérés selon le temps enregistré dans les zones de Flexible+ et Flexible- définies dans le profil d’heures du collaborateur, ou selon les types de salaire définis dans les accords salariaux du collaborateur. Si les types de salaires sont utilisés, le compte flexible d’un collaborateur est ajusté selon les éléments de paie générés lorsque vous transférez l’enregistrement du collaborateur depuis la page **Approuver**. Vous pouvez utiliser des types de salaire pour gérer des comptes flexibles si, par exemple, vous souhaitez augmenter le compte flexible d’un collaborateur d’un facteur spécifique dans une ou plusieurs zones flexibles.

Ce scénario utilise le profil flexible suivant qui représente un jour de travail.

| Type de profil  | Commencement    | Terminer      |
|---------------|----------|----------|
| Flex+         | 00 h 00 | 08 h 00 |
| Pointer à l’arrivée      | 08 h 00 | 08 h 00 |
| Flex-         | 08 h 00 | 09 h 00 |
| Durée standard | 09 h 00 | 11 h 30 |
| Pause rémunérée    | 11 h 30 | 12h00 |
| Flex-         | 12h00 | 16 h 00 |
| Pointer à la sortie     | 16 h 00 | 16 h 00 |
| Flex+         | 16 h 00 | 00 h 00 |

Dans ce cas, vous souhaitez pouvoir gérer le solde flexible du collaborateur selon les types de salaire. Par conséquent, vous devez définir l’option **Sur la base des types de salaire** sur **Oui** sur le groupe flexible du collaborateur.

Pour prendre en compte les heures flexibles, vous devez également définir un type de salaire. Pour ce scénario, le type de salaire est appelé **FlexCnt**.

| Type de paie | Description  |
|----------|--------------|
| FlexCnt  | Compteur flexible |

Ensuite, procédez comme suit pour paramétrer un type de salaire et ajouter des lignes au nouveau type dans un profil de salaire.

1. Sélectionnez **Pointage** \> **Paramétrage** \> **Groupes** \> **Groupes flexibles**, puis **Nouveau**.
2. Dans les champs **Flex+** et **Flex-**, spécifiez le nouveau type de salaire, **FlexCnt**.
3. Sélectionnez **Pointage** \> **Paramétrage** \> **Accords salariaux**, puis **Lignes d’accord**.
4. Pour **Lundi**, pour le type de profil **Flex+**, ajoutez les trois lignes suivantes.

    | Type de paie | Description  | Heure de début | Heure de fin  | Minimum | Maximum | Facteur |
    |----------|--------------|-----------|----------|---------|---------|--------|
    | FlexCnt  | Compteur flexible | 00 h 00  | 18 h 00 | 00h00   | 00h00   | 1,00   |
    | FlexCnt  | Compteur flexible | 18 h 00  | 00 h 00 | 00h00   | 02,00   | 1,50   |
    | FlexCnt  | Compteur flexible | 18 h 00  | 00 h 00 | 02,00   | 06,00   | 2.00   |

    > [!NOTE]
    > Chaque ligne est utilisée pour un intervalle de temps différent et avec un facteur différent. Les heures flexibles que le collaborateur effectue dans l’intervalle de temps sont multipliées par le facteur de cette ligne. Par exemple, les heures de travail entre 18 h 00 et 20 h 00 sont multipliées par 1,50. Le facteur est spécifié dans le champ **Facteur** sur l’onglet **Général** de la page **Lignes d’accord salarial**.

Le collaborateur entre les enregistrements suivants pour ce jour.

| Type d’enregistrement de journal | Commencement    | Terminer      |
|---------------------------|----------|----------|
| Pointer à l’arrivée                  | 07h00 | 07h00 |
| Tâche de production            | 07h00 | 21 h 00 |
| Pointer à la sortie                 | 21 h 00 | 21 h 00 |

Le montant à payer est calculé sur la page **Approuver**, selon l’enregistrement du collaborateur. Une fois l’enregistrement calculé, vous pouvez afficher le résultat sur l’onglet **Heures**. Pour ce scénario, les champs suivants vous intéressent.

| Flex + | Flex - | Durée  | Période de rémunération |
|--------|--------|-------|----------|
| 6,00   | 0,00   | 13,50 | 08,00    |

La durée Flex+ est de six heures, et le calcul est basé sur les zones flexibles du profil de temps. Ce montant est constitué d’une heure de temps Flex+ de 7 h 00 à 8 h 00 et de cinq heures de temps Flex+ de 16 h 00 à 21 h 00.

Lorsque vous transférerez les enregistrements, vous remarquerez que le temps Flex+ est modifié de 6,0 heures à 8,0 heures.

| Flex + | Flex - | Durée  | Période de rémunération |
|--------|--------|-------|----------|
| 8,00   | 0,00   | 13,50 | 08,00    |

Cette modification se produit après le transfert car les heures flexibles ont été calculées selon les types de salaire au lieu des heures. Le tableau suivant indique comment les huit heures sont calculées.

| Début     | Fin       | Durée | Facteur    | Compte flexible |
|----------|----------|------|-----------|--------------|
| 07h00 | 08 h 00 | 1    | 1         | 1            |
| 16 h 00 | 18 h 00 | 2    | 1         | 2            |
| 18 h 00 | 20 h 00 | 2    | 1,5       | 3            |
| 20 h 00 | 21 h 00 | 1    | 2         | 2            |
|          |          |      | **Total** | **8**        |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]