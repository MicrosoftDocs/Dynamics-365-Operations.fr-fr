---
title: Salaire basé sur les enregistrements
description: Cette rubrique explique comment le salaire est calculé sur la base des enregistrements des collaborateurs.
author: johanhoffmann
manager: tfehr
ms.date: 03/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgCalcApproveWeekView, JmgProdStatusListPagePayrollCostDetails, JmgPayCountTable, JmgPayStatConfig, JmgOvertimeSlize, JmgPayAgreementOverride, JmgPayCountSum, JmgPayAdjustSetup, JmgPayAdjustCostType, JmgPayEmployee, JmgMESBreak, JmgPayAddTable, JmgPayAddTransSelectTransId, JmgPayrollCostDetailsPart, jmgProdStatusListPagePayrollCosts, JmgPayrollCostPart, JmgPayEvents, JmgTermRegPayStatSetup, JmgPayStatGroup, JmgPayAddTrans, JmgPayStatTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-03-20
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 98ca6f7713b2f605a49a97d391fb8485bea78c4b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966378"
---
# <a name="pay-based-on-registrations"></a>Salaire basé sur les enregistrements

[!include [banner](../includes/banner.md)]

Cette rubrique explique, en détail, comment le salaire est calculé sur la base des enregistrements des collaborateurs. Elle contient des exemples qui montrent la manière dont les différentes combinaisons d'options de paramétrage disponibles pour le calcul affectent le résultat. Voici quelques-uns des points qui seront abordés :

- Heures flexibles
- Heures supplémentaires
- Pauses
- Codes de report
- Articles de salaire
- Accords salariaux
- Paramètres de calcul du pointage
- Absence

## <a name="the-use-of-flex-time"></a>Utilisation des heures flexibles

Les périodes d'heures flexibles sont paramétrées dans les profils de temps utilisés dans le module Pointage. Il existe deux types de profils flexibles : **Flex+** et **Flex-**. Lorsqu'un collaborateur enregistre le temps dans une période Flex+, son solde flexible est augmenté du nombre d'heures travaillées. Il ne reçoit pas de rémunération pour les heures travaillées pendant la période Flex+. Toutefois, il peut prendre des congés pendant les périodes Flex- et être rémunéré avec les heures de son solde flexible. Par conséquent, les congés pendant les périodes flexibles sont considérés comme une absence par le système.

## <a name="scenarios-based-on-flex-periods"></a>Scénarios basés sur les périodes flexibles

Les deux scénarios qui suivent sont basés sur un profil flexible qui représente un jour de travail. Pour les deux scénarios, le salaire est calculé en fonction de la période flexible pendant laquelle le collaborateur pointe à l'arrivée et à la sortie.

### <a name="flex-profile-for-one-workday"></a>Profil flexible pour un jour de travail

| Type de profil  | Début    | Fin      | Jour     |
|---------------|----------|----------|---------|
| Heures supplémentaires     | 00h00 | 06h00 | Lundi  |
| Flex+         | 06h00 | 07h00 | Lundi  |
| Pointer à l'arrivée      | 07h00 | 07h00 | Lundi  |
| Durée standard | 07h00 | 14h30 | Lundi  |
| Flex-         | 14h30 | 15h30 | Lundi  |
| Pointer à la sortie     | 15h30 | 15h30 | Lundi  |
| Heures supplémentaires     | 15h30 | 06h00 | Mardi |

### <a name="scenario-1-a-worker-registers-clock-in-during-a-flex-period-and-clock-out-during-a-flex--period"></a>Scénario 1 : un collaborateur enregistre le pointage à l'arrivée pendant une période Flex+ et le pointage à la sortie pendant une période Flex-.

Les enregistrements du collaborateur pour ce jour se présentent comme suit :

| Type d'enregistrement de journal | Début    | Fin      |
|---------------------------|----------|----------|
| Pointer à l'arrivée                  | 06h30 | 06h30 |
| Tâche de production            | 06h30 | 14h45 |
| Pointer à la sortie                 | 14h45 | 14h45 |

Les enregistrements du collaborateur pour ce jour sont calculés et transférés vers la paie sur la page **Approbation** (**Pointage** &gt; **Révision et approbation** &gt; **Approbation**). Une fois que les enregistrements ont été calculés, le résultat du calcul peut être affiché sous l'onglet **Temps**. 

Pour comprendre ce scénario, consultez les champs ci-après.

| Flex + | Flex - | Durée | Période de rémunération |
|--------|--------|------|----------|
| 0,50   | 0,75   | 8,25 | 8,50     |

#### <a name="calculation-of-flex"></a>Calcul de Flex+

Selon le profil flexible, l'intervalle entre 06h00 et 07h00 est une période Flex+. Par conséquent, si le collaborateur pointe à 06h30, il gagne 0,5 heures. Ce temps est ajouté au compte flexible du collaborateur.

#### <a name="calculation-of-flex-"></a>Calcul de Flex-

Selon le profil flexible, la période Flex- commence à 14h30 et se termine à 15h30. Par conséquent, si le collaborateur pointe à 14h45, les 45 minutes (0,75 heures) restantes dans la période Flex- sont enregistrées comme heures rémunérées, et la même durée est déduite du compte flexible du collaborateur. Les 45 minutes sont incluses dans les heures rémunérées, car le collaborateur est rémunéré pour les 45 minutes restantes dans la période Flex-. Si le collaborateur est absent pendant la période Flex-, les 45 minutes sont déduites de son compte flexible.

#### <a name="calculation-of-time"></a>Calcul de la durée

La durée correspond au temps entre le pointage à l'arrivée et à la sortie, c'est-à-dire entre 06h30 et 14h45, soit 8,25 heures.

#### <a name="calculation-of-pay-time"></a>Calcul des heures rémunérées

Les heures rémunérées correspondent à la période pendant laquelle un collaborateur est rémunéré. Dans ce scénario, le collaborateur est au travail pendant 8,25 heures (**Durée**). Toutefois, les **Heures rémunérées** sont égales à 8,50 heures, car le collaborateur est rémunéré pendant la période Flex- après son pointage à la sortie. Les heures rémunérées correspondent aux heures de travail planifiées, car la durée Flex+ est ajoutée au compte flexible du collaborateur, pas aux heures rémunérées. Le temps d'absence pendant la période Flex- est compensé par les heures rémunérées et déduit du compte flexible du collaborateur.

| Durée              | Type d'enregistrement | Heures rémunérées (heures)      |
|-------------------|-------------------|-----------------------|
| 6h30 - 7h00 | Flex+             | 0                     |
| 7h00 – 14h45 | Durée standard     | 7,75                  |
| 14h45 – 15h30 | Flex-             | 0,75 (période d'absence) |
|                   | Total             | 8,50                  |

### <a name="scenario-2-a-worker-works-during-the-whole-flex--period-and-also-works-overtime"></a>Scénario 2 : un collaborateur travaille pendant toute la période Flex- et effectue également des heures supplémentaires

Les enregistrements du collaborateur pour ce jour se présentent comme suit :

| Type d'enregistrement de journal | Début    | Fin      |
|---------------------------|----------|----------|
| Pointer à l'arrivée                  | 06h30 | 06h30 |
| Tâche de production            | 06h30 | 17h00 |
| Pointer à la sortie                 | 17h00 | 17h00 |

Après avoir calculé les enregistrements de journal sur la page **Approbation**, vous pouvez afficher le résultat du calcul sous l'onglet **Temps**. Pour comprendre ce scénario, consultez les champs ci-après.

| Flex + | Flex - | Durée  | Période de rémunération | Heures supplémentaires rémunérées |
|--------|--------|-------|----------|--------------|
| 0,50   | 0,00   | 10,50 | 10,00    | 1,50         |

#### <a name="calculation-of-flex"></a>Calcul de Flex+

Selon le profil flexible, l'intervalle entre 06h00 et 07h00 est une période Flex+. Par conséquent, si le collaborateur pointe à 06h30, il gagne 0,5 heures Flex+ sur son solde flexible.

#### <a name="calculation-of-flex-"></a>Calcul de Flex-

Comme le collaborateur travaille pendant la période Flex-, la durée Flex- n'est pas calculée. La durée Flex- n'est calculée que si le collaborateur est absent pendant la période Flex-. D'un point de vue du paiement, si le collaborateur travaille pendant la période Flex-, il est rémunéré au taux de salaire défini pour la durée standard. Si le collaborateur est absent pendant la période Flex-, les 45 minutes sont déduites de son compte flexible.

#### <a name="calculation-of-time"></a>Calcul de la durée

La durée correspond au temps entre le pointage à l'arrivée à 06h30 et le pointage à la sortie à 17h00, soit 10,50 heures.

#### <a name="calculation-of-pay-time"></a>Calcul des heures rémunérées

Dans ce scénario, le collaborateur travaille 10,50 heures (**Durée**). Toutefois, les **Heures rémunérées** sont égales à 10,00 heures, car le collaborateur n'est pas rémunéré pendant la période Flex+.

#### <a name="calculation-of-pay-overtime"></a>Calcul des heures supplémentaires rémunérées

| Durée               | Type d'enregistrement | Heures rémunérées (heures) |
|--------------------|-------------------|------------------|
| 6h30 - 7h00  | Flex+             | 0                |
| 7h00 – 14h30  | Durée standard     | 7,50             |
| 14h30 – 15h30  | Flex-             | 1,00             |
| 15h30 – 17h00 | Heures supplémentaires          | 1,50             |
|                    | Total             | 10,00            |

### <a name="generation-of-pay-items"></a>Génération des articles de salaire

Les enregistrements du collaborateur pour ce jour peuvent être transférés vers la page **Approbation**. Pendant le processus de transfert, les articles de salaire et les enregistrements transférés sont générés. Les articles de salaire représentent une répartition des heures rémunérées en temps standard, heures supplémentaires, pauses rémunérées, etc.

Pour ouvrir la liste des articles de salaire, sélectionnez &gt; **Pointage** **Révision et approbation** &gt; **Approbation**. Sélectionnez ensuite **Recherche** &gt; **Enregistrements transférés**.

Les articles de salaire servent de base pour le salaire d'un collaborateur. Vous pouvez générer un fichier contenant les informations des articles de salaire et transférer ce fichier vers un système de paie.

Dans le cadre du processus de transfert, le temps et le coût des activités de production et de projet sont transférés vers les journaux de production et de projet pour prendre en compte le temps et les coûts engagés. Les enregistrements transférés servent de base pour le prix de revient horaire des ordres de fabrication et des projets. Vous pouvez ouvrir les enregistrements transférés à l'aide du menu **Recherche** dans la page **Approbation**.

Par exemple, pour le scénario 2, les articles de salaire suivants sont générés.

| Type de salaire     | Type de paie | Unités de salaire | Taux  | Coût total |
|---------------|----------|-----------|-------|------------|
| Durée standard | 1201     | 10,0      | 10    | 100        |
| Heures supplémentaires      | 1301     | 1,50      | 5     | 7,50       |
|               |          |           | Total | 107,50     |

L'article de salaire pour la durée standard a une unité de salaire de 10 heures qui couvre les heures standard, les heures Flex- et les heures supplémentaires. Les heures standard, les heures Flex- et les heures supplémentaires sont consolidées en un article de salaire, car tous les types sont calculés comme durée standard, selon la valeur par défaut d'un paramètre dans la page **Paramètres de calcul** (**Pointage** &gt; **Paramétrage** &gt; **Paramètres de calcul**). Les heures supplémentaires sont calculées en plus des heures standard en utilisant un taux supplémentaire de 5.

Si vous souhaitez distinguer clairement les heures standard des heures supplémentaires, afin que les unités de salaire pour les types de salaire couvrent uniquement le temps réel passé pour les heures standard et les heures supplémentaires, les unités de salaire pour les heures standard doivent être égales à 8,50, et les unités de salaire pour les heures supplémentaires doivent être égales à 1,50.

Pour configurer le système pour distinguer clairement les heures standard des heures supplémentaires, vous devez exclure les heures supplémentaires des heures standard. Vous devez également modifier le paramétrage du type de salaire pour les heures supplémentaires afin que le taux de salaire pour les heures supplémentaires couvre l'ensemble des paiements pour les heures supplémentaires.

### <a name="exclude-overtime-from-the-standard-time"></a>Exclure les heures supplémentaires des heures standard

Dans la page **Paramètres de calcul**, sélectionnez **Heures supplémentaires** comme type de spécification de profil, puis définissez l'option **Heures rémunérées** sur **Non**, comme indiqué ici.

| Spécification d'enr. | Type de spécification de profils | Calcul   |     | Payé         |     |
|--------------------|----------------------------|---------------|-----|--------------|-----|
| Temps de travail       | Heures supplémentaires                   | Durée standard | Oui | Période de rémunération     | Non  |
|                    |                            | Période de rémunération      | Oui | Heures supplémentaires rémunérées | Oui |

Après avoir ajusté les paramètres de calcul, les articles de salaire ci-après sont générés.

| Type de salaire     | Type de paie | Unités de salaire | Taux  | Coût total |
|---------------|----------|-----------|-------|------------|
| Durée standard | 1201     | 8,50      | 10    | 85,0       |
| Heures supplémentaires      | 1301     | 1,50      | 15    | 22,50      |
|               |          |           | Total | 107,50     |

> [!NOTE]
> Les paramètres de calcul ont un paramètre standard recommandé. En général, vous devez être prudent lorsque vous modifiez ces paramètres. Pour rétablir les paramètres standard recommandés, dans la page **Paramètres de calcul**, sélectionnez **Rétablir les valeurs**.

### <a name="allow-a-deviation-from-the-standard-pay-profiles"></a>Autoriser un écart par rapport aux profils de salaire standard

Dans la page **Profils** (**Pointage** &gt; **Paramétrage** &gt; **Profils de temps** &gt; **Profils**), vous pouvez paramétrer des types de profils incluant des codes de report et des pauses.

### <a name="switch-codes"></a>Codes de report

Vous pouvez utiliser des codes de report pour autoriser les collaborateurs à dévier de leur type de profil en modifiant un autre type de profil. Par exemple, vous pouvez autoriser un collaborateur à modifier les heures Flex+ en heures supplémentaires. Un collaborateur peut ajouter un code de report pendant l'enregistrement, ou vous pouvez affecter la tâche d'ajout d'un code de report à l'approbateur des enregistrements.

Avant de pouvoir utiliser un code de report, vous devez le définir comme type d'activité indirecte. Vous devez ensuite ajouter le code de report au profil de temps pour la période où vous souhaitez autoriser la modification du type de profil. Par exemple, suivez la procédure ci-après pour créer un code de report qui autorise la modification de la période Flex+ de 06h00 à 07h00 en heures supplémentaires.

1. Créez un code de report **OTBCI (Convertir les heures flexibles en heures supplémentaires avant le pointage à l'arrivée)**. Sélectionnez **Pointage** &gt; **Gérer les activités indirectes** &gt; **Activités indirectes**.
2. Dans la colonne **Code de report**, ajoutez OTBCI à la ligne Flex+ dans le profil de temps.
3. Dans la colonne **Secondaire**, ajoutez le type de profil **Heures supplémentaires**.

Prenez le profil flexible ci-après qui représente un jour de travail.

| Type de profil  | Début    | Fin      | Jour     |
|---------------|----------|----------|---------|
| Heures supplémentaires     | 00h00 | 06h00 | Lundi  |
| Flex+         | 06h00 | 07h00 | Lundi  |
| Pointer à l'arrivée      | 07h00 | 07h00 | Lundi  |
| Durée standard | 07h00 | 14h30 | Lundi  |
| Flex-         | 14h30 | 15h30 | Lundi  |
| Pointer à la sortie     | 15h30 | 15h30 | Lundi  |
| Heures supplémentaires     | 15h30 | 06h00 | Mardi |

Voici les enregistrements du collaborateur pour ce jour.

| Type d'enregistrement de journal | Début    | Fin      |
|---------------------------|----------|----------|
| Pointer à l'arrivée                  | 06h30 | 06h30 |
| Tâche de production            | 06h30 | 14h45 |
| Pointer à la sortie                 | 17h00 | 17h00 |

Les articles de salaire ci-après sont générés après le transfert.

| Type de salaire     | Type de paie | Unités de salaire | Taux  | Coût total |
|---------------|----------|-----------|-------|------------|
| Durée standard | 1201     | 8,50      | 10    | 85,0       |
| Heures supplémentaires      | 1305     | 1,50      | 15    | 22,50      |
|               |          |           | Total | 107,50     |

Dans la page **Approbation**, annulez le transfert, puis utilisez le menu **Code de report** pour appliquer le code de report **OTBCI**. Lorsque vous transférez les enregistrements une deuxième fois, les articles de salaire ci-après sont générés.

| Type de salaire     | Type de paie | Unités de salaire | Taux  | Coût total |
|---------------|----------|-----------|-------|------------|
| Durée standard | 1201     | 8,50      | 10    | 80,0       |
| Heures supplémentaires      | 1305     | 2,00      | 15    | 30,0       |
|               |          |           | Total | 107,50     |

> [!NOTE]
> Lorsque vous appliquez le code de report, les heures supplémentaires sont augmentées de 0,5 heures, de 1,50 à 2,00. Les 0,5 heures correspondent à la conversion des heures Flex+ enregistrées, de 6h30 à 7h00, en heures supplémentaires.

### <a name="breaks"></a>Pauses

Les pauses de travail affectent le calcul du salaire du collaborateur. Les pauses sont définies comme un type d'activité indirecte. Elles peuvent être définies comme **Rémunéré** pour que la pause soit ajoutée au salaire du collaborateur, ou **Non rémunéré** pour empêcher que la pause soit ajoutée au salaire du collaborateur. Une pause peut également être définie comme **Planifié** ou **Enregistré**.

#### <a name="planned-breaks"></a>Pauses planifiées

Si une société a un temps de pause fixe, comme une pause fixe pour le déjeuner, la pause peut être prédéfinie dans le profil de temps. Dans ce cas, il n'est pas nécessaire que le collaborateur enregistre la pause dans les pages des bons de travail. La pause est automatiquement prise en compte lorsque les enregistrements du collaborateur sont calculés dans la page **Approbation**.

#### <a name="registered-breaks"></a>Pauses enregistrées

Si une société n'utilise pas de pauses planifiées, les collaborateurs peuvent enregistrer les pauses durant la journée de travail. Les pauses enregistrées peuvent être utilisées, par exemple, si un collaborateur utilise un profil de temps flexible dont les heures de pointage à l'arrivée et à la sortie ne sont pas définies. Les pauses enregistrées sont un type d'activité indirecte. Le collaborateur enregistre la pause sur la page **Bon de travail** ou sur la page **Périphérique de bon de travail**. Sur ces deux pages, l'utilisateur peut sélectionner le type de pause dans une liste d'activités de pause prédéfinies.

#### <a name="paid-and-unpaid-breaks"></a>Pauses rémunérées et non rémunérées

Les activités de pause peuvent être paramétrées comme **Rémunéré** ou **Non rémunéré**. Une pause rémunérée est incluse dans le calcul des heures rémunérées, et le système utilise le type de salaire défini dans l'accord salarial pour le type d'enregistrement **Pause**.

### <a name="example-of-a-planned-break"></a>Exemple de pause planifiée

Prenez le profil de temps ci-après qui inclut une pause non rémunérée pour le déjeuner.

| Type de profil  | Début    | Fin      | Jour     |
|---------------|----------|----------|---------|
| Heures supplémentaires     | 00h00 | 06h00 | Lundi  |
| Flex+         | 06h00 | 07h00 | Lundi  |
| Pointer à l'arrivée      | 07h00 | 07h00 | Lundi  |
| Durée standard | 07h00 | 12h00 | Lundi  |
| Pause         | 12h00 | 12h30 | Lundi  |
| Durée standard | 12h30 | 14h30 | Lundi  |
| Flex-         | 14h30 | 15h30 | Lundi  |
| Pointer à la sortie     | 15h30 | 15h30 | Lundi  |
| Heures supplémentaires     | 15h30 | 06h00 | Mardi |

Voici les enregistrements du collaborateur pour ce jour.

| Type d'enregistrement de journal | Début    | Fin      |
|---------------------------|----------|----------|
| Pointer à l'arrivée                  | 06h30 | 06h30 |
| Tâche de production            | 06h30 | 14h45 |
| Pointer à la sortie                 | 17h00 | 17h00 |

Après avoir calculé les enregistrements de journal sur la page **Approbation**, vous pouvez afficher le résultat du calcul sous l'onglet **Temps**. Pour comprendre ce scénario, consultez les champs ci-après.

| Flex + | Flex - | Durée  | Période de rémunération | Pause non rémunérée | Heures supplémentaires rémunérées |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | 10,50 | 9,50     | 0,5                 | 1,50         |

> [!NOTE] 
> Le système a calculé 0,5 heures de pause non rémunérée, qui ne fait pas partie des heures rémunérées.

### <a name="example-of-a-registered-break"></a>Exemple de pause enregistrée

Prenez le profil de temps ci-après qui n'inclut pas de pauses planifiées.

| Type de profil  | Début    | Fin      | Jour     |
|---------------|----------|----------|---------|
| Heures supplémentaires     | 00h00 | 06h00 | Lundi  |
| Flex+         | 06h00 | 07h00 | Lundi  |
| Pointer à l'arrivée      | 07h00 | 07h00 | Lundi  |
| Durée standard | 07h00 | 14h30 | Lundi  |
| Flex-         | 14h30 | 15h30 | Lundi  |
| Pointer à la sortie     | 15h30 | 15h30 | Lundi  |
| Heures supplémentaires     | 15h30 | 06h00 | Mardi |

Voici les enregistrements du collaborateur pour ce jour.

| Type d'enregistrement de journal | Début    | Fin      |
|---------------------------|----------|----------|
| Pointer à l'arrivée                  | 06h30 | 06h30 |
| Tâche de production            | 06h30 | 17h00 |
| Pause                     | 12h03 | 12h32 |
| Pointer à la sortie                 | 17h00 | 17h00 |

Lorsque les enregistrements sont calculés, la durée des activités est calculée.

| Type d'enregistrement de journal | Début    | Fin      | Durée  |
|---------------------------|----------|----------|-------|
| Pointer à l'arrivée                  | 06h30 | 06h30 |       |
| Tâche de production            | 06h30 | 17h00 | 10,00 |
| Pause                     | 12h03 | 12h32 | 0,50  |
| Pointer à la sortie                 | 17h00 | 17h00 |       |

> [!NOTE]
> Le temps de pause s'exécute en parallèle avec la durée de l'activité (une tâche de production, dans cet exemple). Ce comportement est toujours utilisé pour les activités de pause. Lorsque les enregistrements sont calculés, le temps de pause est soustrait de la durée de l'activité. Dans ce cas, la tâche de production a une durée de 10,50 heures, mais la valeur est définie sur 10, car 0,5 heures de pause sont soustraites de la durée de l'activité.

Après avoir calculé les enregistrements de journal sur la page **Approbation**, vous pouvez afficher le résultat du calcul sous l'onglet **Temps**. Pour comprendre ce scénario, consultez les champs ci-après.

| Flex + | Flex - | Durée  | Période de rémunération | Pause non rémunérée | Heures supplémentaires rémunérées |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | 10,50 | 9,50     | 0,5                 | 1,50         |

Si la pause planifiée avait été rémunérée au lieu d'être non rémunérée, le résultat du calcul se présenterait comme suit :

| Flex + | Flex - | Durée  | Période de rémunération | Pause rémunérée | Heures supplémentaires rémunérées |
|--------|--------|-------|----------|-----------------|--------------|
| 0,50   | 0,00   | 10,50 | 10,00    | 0,5             | 1.50         |

### <a name="pay-items-and-paid-breaks"></a>Articles de salaire et pauses rémunérées

Lorsque vous transférez les enregistrements sur la page **Approbation**, les articles de salaire sont générés. Un article de salaire distinct est généré pour les pauses rémunérées.

Le taux de salaire pour une pause rémunérée est déterminé par le type de salaire paramétré dans les accords salariaux pour la pause. Au lieu d'utiliser un type de salaire, vous pouvez paramétrer le prix de revient horaire de la pause pour un intervalle de dates défini.

Prenez le profil de temps ci-après.

| Type de profil  | Début    | Fin      | Jour     |
|---------------|----------|----------|---------|
| Heures supplémentaires     | 00h00 | 06h00 | Lundi  |
| Flex+         | 06h00 | 07h00 | Lundi  |
| Pointer à l'arrivée      | 07h00 | 07h00 | Lundi  |
| Durée standard | 07h00 | 14h30 | Lundi  |
| Flex-         | 14h30 | 15h30 | Lundi  |
| Pointer à la sortie     | 15h30 | 15h30 | Lundi  |
| Heures supplémentaires     | 15h30 | 06h00 | Mardi |

Voici les enregistrements du collaborateur pour ce jour.

| Type d'enregistrement de journal | Début    | Fin      | Durée |
|---------------------------|----------|----------|------|
| Pointer à l'arrivée                  | 07h00 | 07h00 |      |
| Tâche de production            | 07h00 | 15h00 | 7,5  |
| Pause (rémunérée)              | 12h00 | 12h30 | 0,5  |
| Pointer à la sortie                 | 15h00 | 15h00 |      |

Pour cet exemple, le type de salaire pour la durée standard est défini sur **1201**, et un taux de salaire de **10** est paramétré dans l'accord salarial. La pause rémunérée a un type de salaire de **1301** et un taux de salaire de **8**. Lorsque les enregistrements sont transférés, les articles de salaire ci-après sont générés.

| Type de salaire     | Type de paie | Unités de salaire | Taux |
|---------------|----------|-----------|------|
| Durée standard | 1201     | 7,50      | 10   |
| Flex-         | 1201     | 0,50      | 10   |
| Pause (rémunérée)  | 1301     | 0,50      | 8    |

## <a name="how-the-cost-of-paid-breaks-is-allocated-to-projects-and-production-orders"></a>Mode d'affectation du coût des pauses rémunérées aux projets et aux ordres de fabrication

Le coût horaire des activités de projet et des tâches de production peut être paramétré de manière à être déterminé par les taux de salaire calculés dans le module Pointage ou par les catégories de coûts définies pour les activités.

Pour paramétrer la catégorie de coûts, sélectionnez **Contrôle de la production** &gt; **Paramétrage** &gt; **Contrôle et suivi de la production** &gt; **Valeurs par défaut de l'ordre de fabrication**, puis définissez le champ **Catégorie de coûts** sur **Oui** ou **Non**.

- **Non** – Le coût est calculé sur la base des taux de salaire définis pour les types d'enregistrements Pointage.
- **Oui** – Le coût est calculé sur la base des catégories de coûts pour les activités de production et de projet.

### <a name="cost-calculation-based-on-pay-rates-that-are-calculated-in-time-and-attendance"></a>Calcul des coûts basé les taux de salaire calculés dans le module Pointage

L'exemple suivant montre comment le coût horaire est calculé lorsque le coût est paramétré pour être calculé sur la base des taux de salaire.

Le taux de coût horaire utilisé pour les ordres de fabrication et les projets est calculé pendant le processus de transfert. Pour afficher le taux horaire par activité, ouvrez la page **Approbation** dans le module Pointage, puis sélectionnez &gt; **Recherche** **Enregistrements transférés**. Le taux de coût horaire par enregistrement est disponible sous l'onglet **Prix de revient**.

Prenez les enregistrements suivants qui utilisent le même profil de temps que l'exemple précédent.

| Type d'enregistrement de journal | Début    | Fin      | Durée |
|---------------------------|----------|----------|------|
| Pointer à l'arrivée                  | 07h00 | 07h00 |      |
| Traiter (commande : 4711)     | 07h00 | 11h00 | 4    |
| Traiter (commande : 4712)     | 11h00 | 15h00 | 3,50 |
| Pause (rémunérée)              | 12h00 | 12h30 | 0,50 |
| Pointer à la sortie                 | 15h00 | 15h00 |      |

Une fois les enregistrements transférés, les enregistrements transférés ci-après sont générés.

| Type d'enregistrement     | Durée | Prix de revient par heure |
|-----------------------|------|---------------------|
| Pointage à l'arrivée              | 0,00 | 0,00                |
| Traiter (commande : 4711) | 4,00 | 10,00               |
| Traiter (commande : 4712) | 3,50 | 11,14               |
| Pause (rémunérée)          | 0,50 | 0,00                |
| Pointer à la sortie             | 0,00 | 0,00                |

Le calcul du prix de revient horaire de la pause rémunérée dépend du paramètre des coûts des salaires directs. Sélectionnez **Pointage** &gt; **Paramétrage** &gt; **Paramètres de pointage**. Sous l'onglet **Prix de revient**, sous **Coûts des salaires directs**, dans le champ **Durée standard**, vous pouvez sélectionner **Oui**, **Non** ou **Répartition**.

- **Oui** – Cette valeur est utilisée pour l'exemple précédent. Le coût est affecté à l'activité de production ou de projet qui s'exécute en parallèle avec l'activité de pause rémunérée. Dans l'exemple, cette activité est la tâche de production pour la commande 4712. Comme vous pouvez le voir, le prix de revient horaire de la pause rémunérée est 0 (zéro). Il est affecté à la tâche qui s'exécute en parallèle avec la pause.

    La pause rémunérée a une durée de 0,5 heures, et le taux de salaire est 8. Par conséquent, le coût total de la pause rémunérée est 4. Le coût total est ensuite affecté à la tâche de traitement de 3,5 heures. Par conséquent, la pause rémunérée contribue à 1,14 par heure au coût (4 ÷ 3,5 = 1,14).

- **Répartition** – La pause rémunérée est équitablement répartie entre les tâches enregistrées pour ce jour. Si cette valeur est utilisée pour l'exemple précédent, les enregistrements transférés ci-après sont générés.

    | Type d'enregistrement     | Durée | Prix de revient par heure |
    |-----------------------|------|---------------------|
    | Pointage à l'arrivée              | 0,00 | 0,00                |
    | Traiter (commande : 4711) | 4,00 | 10,53               |
    | Traiter (commande : 4712) | 3,50 | 10,53               |
    | Pause (rémunérée)          | 0,50 | 0,00                |
    | Pointer à la sortie             | 0,00 | 0,00                |

    Le temps de traitement total pour les deux tâches de production est 7,5 heures, et le coût total de la pause rémunérée est 4. Par conséquent, le coût de la pause est égal à 0,53 (= 4 ÷ 7,5).

- **Non** – Le coût de la pause rémunérée n'augmente pas le coût horaire des activités de traitement.

    | Type d'enregistrement     | Durée | Prix de revient par heure |
    |-----------------------|------|---------------------|
    | Pointage à l'arrivée              | 0,00 | 0,00                |
    | Traiter (commande : 4711) | 4,00 | 10,00               |
    | Traiter (commande : 4712) | 3,50 | 10,00               |
    | Pause (rémunérée)          | 0,50 | 0,00                |
    | Pointer à la sortie             | 0,00 | 0,00                |

## <a name="absence"></a>Absence

Un code absence est utilisé pour enregistrer la période d'absence d'un collaborateur. À l'instar des pauses et des codes de report, un code absence est un type d'activité indirecte. Le temps d'absence peut être planifié ou enregistré, et l'absence peut être légale ou illégale. Une absence légale est, par exemple, un rendez-vous chez un médecin, un séminaire ou une participation à un jury. Une absence illégale est une absence sans motif valable, par exemple lorsqu'un collaborateur arrive en retard au travail. Généralement, une absence légale n'entraîne pas une retenue salariale pour le collaborateur, contrairement à l'absence illégale.

### <a name="planned-absence"></a>Absence prévue

Vous pouvez créer une absence planifiée pour les collaborateurs dans la page **Créer une absence prévue** (**Pointage** &gt; **Créer une absence prévue**). L'absence planifiée est enregistrée comme une tâche d'absence pour une date et un intervalle spécifiés.

La tâche est basée sur une requête. Par conséquent, vous pouvez créer une absence planifiée pour plusieurs collaborateurs, par exemple les collaborateurs appartenant au même groupe de calcul. Si l'absence planifiée concerne un collaborateur unique, l'enregistrement peut être entré à partir de la page **Présence** ou de la page **Enregistrement du temps des collaborateurs**.

- Pour entrer un enregistrement d'absence à partir de la page **Présence**, sélectionnez **Pointage** &gt; **Recherches et états** &gt; **Présence** &gt; **Présence**, puis sélectionnez **Enregistrement d'absence**.
- Pour entrer un enregistrement d'absence à partir de la page *<strong><em>Enregistrement du temps des collaborateurs</em></strong>*, sélectionnez <strong>Pointage</strong> &gt; <strong>Paramétrage</strong> &gt; <strong>Enregistrement du temps des collaborateurs</strong>, puis sous l'onglet <strong>Temps</strong>, sous <strong>Attribution du temps</strong>, sélectionnez <strong>Enregistrements d'absence</strong>.

Vous pouvez utiliser l'état **Absences planifiées** pour afficher une vue d'ensemble des absences planifiées des collaborateurs. Pour ouvrir cet état, sélectionnez **Pointage** &gt; **Recherches et états** &gt; **États des absences** &gt; **Absences planifiées**.

### <a name="registered-absence"></a>Absence enregistrée

En général, les collaborateurs sont considérés comme absents s'ils ne sont pas au travail pendant une période comprise entre les heures de pointage prévues à l'arrivée et à la sortie. Si les collaborateurs pointent à l'arrivée plus tard que prévu ou s'ils pointent à la sortie plus tôt que prévu, ils sont invités à sélectionner un code absence pour indiquer le motif de leur absence. Un code absence peut être paramétré pour s'appliquer à l'enregistrement. Seuls les codes applicables peuvent être sélectionnés dans la liste.

## <a name="scenarios-based-on-various-combinations-of-work-hour-registrations"></a>Scénarios basés sur différentes combinaisons d'enregistrements des heures de travail

Les scénarios ci-après présentent les articles de salaire et les entrées pour approbation qui sont générés pour les collaborateurs sur la base de leurs enregistrements. Tous les scénarios sont basés sur le profil de temps ci-après.

| Type de profil  | Début    | Fin      | Jour     |
|---------------|----------|----------|---------|
| Heures supplémentaires     | 00h00 | 06h00 | Lundi  |
| Flex+         | 06h00 | 07h00 | Lundi  |
| Pointer à l'arrivée      | 07h00 | 07h00 | Lundi  |
| Durée standard | 07h00 | 14h30 | Lundi  |
| Flex-         | 14h30 | 15h30 | Lundi  |
| Pointer à la sortie     | 15h30 | 15h30 | Lundi  |
| Heures supplémentaires     | 15h30 | 06h00 | Mardi |

### <a name="scenario-1-the-worker-clocks-in-later-than-planned"></a>Scénario 1 : le travailleur pointe à l'arrivée plus tard que prévu

Le collaborateur pointe à 08h30. Comme son heure de pointage à l'arrivée prévue est 07h00, il a 1,50 heure de retard. Comme les 1,50 heures sont considérées comme un temps d'absence, le collaborateur est invité à sélectionner un code absence. Le collaborateur quitte le travail à 15h30, qui est l'heure de pointage à la sortie prévue. Lorsque les enregistrements du collaborateur sont calculés et approuvés, l'enregistrement d'absence et le code absence sélectionné par le collaborateur à l'arrivée, s'affichent pour la période comprise entre 07h00 et 08h30.

Dans le profil de temps, vous pouvez configurer le type d'enregistrement **Pointage à l'arrivée** afin de définir une tolérance lorsque les collaborateurs arrivent en retard au travail. Par exemple, si vous paramétrez une tolérance de 5, le collaborateur est invité à entrer un code absence uniquement s'il pointe à l'arrivée après 07h05.

Dans ce cas, comme le collaborateur n'a pas de motif de retard valable, il sélectionne un code absence défini pour l'absence illégale. Un code absence est considéré comme applicable à l'absence illégale si le paramètre de déduction des heures supplémentaires est activé pour le groupe d'absences auquel le code absence appartient. Pour définir le paramètre, sélectionnez **Pointage** &gt; **Paramétrage** &gt; **Groupes** &gt; **Groupes d'absence**, puis activez la case à cocher **Déduire les heures supplémentaires**.

Voici comment les enregistrements du collaborateur pour ce jour s'affichent sur la page **Approbation** après calcul.

| Type d'enregistrement de journal         | Début    | Fin      | Durée |
|-----------------------------------|----------|----------|------|
| Absence (illégale - retard au travail) | 07h00 | 08h30 | 1,5  |
| Pointer à l'arrivée                          | 08h30 | 08h30 |      |
| Tâche de production                    | 07h30 | 15h30 | 7,0  |
| Pointer à la sortie                         | 15h30 | 15h30 |      |

Voici l'article de salaire obtenu après le transfert des enregistrements.

| Type de salaire     | Type de paie | Unités de salaire | Taux |
|---------------|----------|-----------|------|
| Durée standard | 1201     | 7h00      | 10   |

### <a name="scenario-2-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-standard-time-period"></a>Scénario 2 : le collaborateur pointe avant l'heure de pointage à la sortie prévue pendant une période de temps standard

Le collaborateur pointe à l'arrivée à 07h00, puis pointe tôt à la sortie à 13h00. Comme 13h00 est antérieur à l'heure de pointage à la sortie prévue à 13h30, et 01h00 est dans une période de temps standard, le collaborateur est invité à sélectionner un code absence. Le collaborateur sélectionne un code absence pour un rendez-vous chez un médecin, qui est défini comme une absence légale. Le taux de salaire pour l'absence légale est défini dans les accords salariaux pour le type d'enregistrement **Absence** (**Pointage** &gt; **Paramétrage** &gt; **Paie** &gt; **Accords salariaux**).

Voici comment les enregistrements du collaborateur pour ce jour s'affichent sur la page **Approbation** après calcul.

| Type d'enregistrement de journal              | Début    | Fin      | Durée |
|----------------------------------------|----------|----------|------|
| Pointer à l'arrivée                               | 07h00 | 07h00 |      |
| Tâche de production                         | 07h00 | 13h00 | 4,0  |
| Pointer à la sortie                              | 13h00 | 13h00 |      |
| Absence (légale – rendez-vous chez le médecin) | 13h00 | 15h30 | 3,5  |

Voici l'article de salaire obtenu après le transfert des enregistrements.

| Type de salaire     | Type de paie | Unités de salaire | Taux |
|---------------|----------|-----------|------|
| Durée standard | 1201     | 7,50      | 10   |

### <a name="scenario-3-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-flex--period"></a>Scénario 3 : le collaborateur pointe avant l'heure de pointage à la sortie prévue pendant une période Flex-

Le collaborateur pointe à l'arrivée à 07h00 et à la sortie à 14h15, qui est dans la période Flex- planifiée. La période entre l'heure de pointage à la sortie réelle et l'heure de pointage à la sortie prévue n'est pas considérée comme une absence, et le collaborateur n'est pas invité à sélectionner un code absence. Le montant est déduit du compte flexible du collaborateur, et le collaborateur est rémunéré pendant la partie restante de la période Flex-, de 14h15 à 15h30.

Voici comment les enregistrements du collaborateur pour ce jour s'affichent sur la page **Approbation** après calcul.

| Type d'enregistrement de journal | Début    | Fin      | Durée |
|---------------------------|----------|----------|------|
| Pointer à l'arrivée                  | 07h00 | 07h00 |      |
| Tâche de production            | 07h00 | 14h15 | 7,25 |
| Pointer à la sortie                 | 14h15 | 14h15 |      |

Voici l'article de salaire obtenu après le transfert des enregistrements.

| Type de salaire     | Type de paie | Unités de salaire | Taux |
|---------------|----------|-----------|------|
| Durée standard | 1201     | 8,50      | 10   |

### <a name="scenario-4-the-worker-clocks-in-late-and-clocks-out-after-the-planned-clock-out-time-during-an-overtime-period"></a>Scénario 4 : le collaborateur pointe à l'arrivée en retard et pointe à la sortie après l'heure de pointage prévue pendant une période d'heures supplémentaires

Le collaborateur pointe à l'arrivée à 09h30 et, pour compenser son retard, il effectue des heures supplémentaires et pointe à la sortie à 17h00. Comme le collaborateur est arrivé en retard et a compensé en travaillant plus longtemps, la société ne souhaite pas lui payer des heures supplémentaires pour les heures travaillées entre l'heure de pointage à la sortie prévue à 15h30 et son heure de pointage à la sortie réelle à 17h00, même si cette période est définie comme des heures supplémentaires dans le profil de temps.

Pour gérer ce scénario, le code absence peut être paramétré pour réduire les heures supplémentaires des heures d'absence illégale du collaborateur ce même jour. Sélectionnez **Pointage** &gt; **Paramétrage** &gt; **Groupes** &gt; **Groupes d'absence**, puis activez la case à cocher **Déduire les heures supplémentaires** pour déduire les heures supplémentaires des heures d'absence illégale.

Voici comment les enregistrements du collaborateur pour ce jour s'affichent sur la page **Approbation** après calcul.

| Type d'enregistrement de journal         | Début    | Fin      | Durée |
|-----------------------------------|----------|----------|------|
| Absence (illégale - retard au travail) | 07h00 | 09h30 | 1,5  |
| Pointer à l'arrivée                          | 09h30 | 09h30 |      |
| Tâche de production                    | 09h30 | 17h00 | 7,5  |
| Pointer à la sortie                         | 17h30 | 17h30 |      |

Si la case à cocher **Déduire les heures supplémentaires** est activée pour le code absence sélectionné, le paiement des heures supplémentaires est déduit des heures d'absence illégale du collaborateur. Dans ce cas, les articles de salaire ci-après sont générés après le transfert des enregistrements.

| Type de salaire     | Type de paie | Unités de salaire | Taux |
|---------------|----------|-----------|------|
| Durée standard | 1201     | 9h00      | 10   |
| Heures supplémentaires      | 1301     | 0,5       | 15   |

Ici, les 1,5 heures d'absence illégale, de 07h00 à 09h30, déduisent les 2,0 heures supplémentaires, de 15h30 à 17h30. Le résultat de l'enregistrement est 1,5 heures standard et 0,5 heures supplémentaires.

En revanche, si la case à cocher **Déduire les heures supplémentaires** est désactivée pour le code absence sélectionné, les heures supplémentaires sont payées au collaborateur, même s'il est arrivé en retard et que son absence était illégale. Dans ce cas, les articles de salaire ci-après sont générés après le transfert des enregistrements.

| Type de salaire     | Type de paie | Unités de salaire | Taux |
|---------------|----------|-----------|------|
| Durée standard | 1201     | 7,50      | 10   |
| Heures supplémentaires      | 1301     | 2,0       | 15   |

### <a name="scenario-5-the-worker-clocks-out-before-the-planned-clock-out-time-and-can-convert-the-absence-period-to-a-flex--period"></a>Scénario 5 : le collaborateur pointe à la sortie avant l'heure de pointage prévue et peut convertir la période d'absence en période Flex-

L'exemple suivant montre comment le compte flexible d'un collaborateur peut être réduit en convertissant la période d'absence en période Flex-.

Le collaborateur pointe à l'arrivée à 07h00, puis à la sortie à 13h00. Il a conclu un accord avec son superviseur pour pouvoir rentrer chez lui pendant le week-end s'il déduit ces heures de son compte flexible. Lorsque le collaborateur pointe à la sortie à 13h00, il est invité à sélectionner un code absence, car la période d'absence pour la partie restante de la journée de travail concernée n'est pas dans une période Flex- planifiée. Pour convertir la partie restante de la journée de travail en période Flex-, le collaborateur peut sélectionner un code absence paramétré pour réduire son compte flexible.

Pour réduire le solde des heures flexibles pour les collaborateurs qui enregistrent une absence pendant une journée de travail, sélectionnez &gt; **Pointage** **Paramétrage** &gt; **Groupes** &gt; **Groupes d'absence**, puis activez la case à cocher **Réduire horaire flexible**.

Voici comment les enregistrements du collaborateur pour ce jour s'affichent sur la page **Approbation** avant calcul.

| Type d'enregistrement de journal | Début    | Fin      | Durée |
|---------------------------|----------|----------|------|
| Pointer à l'arrivée                  | 07h00 | 07h00 |      |
| Tâche de production            | 07h00 | 13h00 | 6,0  |
| Pointer à la sortie                 | 13h00 | 13h00 |      |

Si le collaborateur sélectionne un code absence pour l'absence illégale, l'article de salaire obtenu se présente comme suit après le transfert de l'enregistrement.

| Type de salaire     | Type de paie | Unités de salaire | Taux |
|---------------|----------|-----------|------|
| Durée standard | 1201     | 6,00      | 10   |

Si le collaborateur sélectionne un code absence pour l'absence légale et si le code absence est paramétré pour réduire son compte flexible, les articles de salaire obtenus se présentent comme suit après le transfert des enregistrements.

| Type de salaire     | Type de paie | Unités de salaire | Taux |
|---------------|----------|-----------|------|
| Durée standard | 1201     | 8,50      | 10   |

Dans ce cas, le solde flexible du collaborateur est réduit des heures entre l'heure de pointage à la sortie réelle et l'heure de pointage à la sortie prévue (c'est-à-dire, les 2,5 heures entre 13h00 et 15h30).

> [!NOTE]
> Il n'est pas recommandé d'activer la case à cocher **Déduire les heures flexibles** et la case à cocher **Déduire les heures supplémentaires** pour le code absence, car ce paramétrage déduit les heures illégales des heures supplémentaires du collaborateur tout en réduisant le compte flexible du collaborateur.

### <a name="scenario-6-there-is-no-planned-absence-for-the-day-and-no-worker-attendance-for-the-day"></a>Scénario 6 : aucune absence n'est planifiée pour ce jour et le collaborateur n'est pas présent ce jour

Si le collaborateur ne va pas au travail pendant un jour de travail et si aucune absence n'est planifiée pour le collaborateur ce jour, le code absence par défaut est utilisé pour le calcul des enregistrements du collaborateur. Pour définir les codes absence par défaut, sélectionnez &gt; **Pointage** **Paramètres de pointage**. Vous pouvez ensuite sélectionner un code absence dans les champs suivants :

- Insertion auto. Flex-
- Insertion auto. absence

Lorsque les enregistrements quotidiens sont calculés pour un collaborateur qui est activé pour les heures flexibles, le code absence spécifié dans le champ **Insertion auto. Flex-** est utilisé comme code absence par défaut. Si le collaborateur n'est pas activé pour les heures flexibles, le code absence spécifié dans le champ **Insertion auto. absence** est utilisé. Si une société a une combinaison de collaborateurs qui sont activés pour les heures flexibles et de collaborateurs qui ne sont pas activés pour les heures flexibles, les deux paramètres doivent être configurés.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]