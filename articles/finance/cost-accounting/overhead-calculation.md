---
title: Calcul des frais généraux
description: Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443282"
---
# <a name="overhead-calculation"></a>Calcul des frais généraux

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les processus habituels pour calculer et affecter des frais généraux.

<a name="term-definition"></a>Définition des termes
---------------

Les frais généraux sont les coûts qui sont imputés afin de gérer une entreprise, mais qui ne peuvent pas être attribués directement à aucun produit, activité, ou service spécifique. Les frais généraux permettent essentiellement l’identification des activités rémunératrices. Voici quelques exemples de frais généraux :

-   Loyer
-   Électricité
-   Salaires administratifs

## <a name="overhead-calculation-overview"></a>Vue d’ensemble du calcul des frais généraux
Le calcul des frais généraux exécute les stratégies de contrôle de gestion dans l’ordre correct. Vous pouvez exécuter plusieurs fois le calcul des frais généraux pour la même période fiscale si les stratégies de contrôle de gestion ont été modifiées ou des erreurs ont été détectées. Chaque exécution du calcul des frais généraux est enregistrée et reçoit un ID de version unique qui vous permet de comparer les calculs des différentes versions. Les entrées de coût que le calcul des frais généraux génère reçoivent une date comptable. Cette date comptable correspond à la date de fin de la période fiscale utilisée dans le calcul. L’ID de version unique inclut les éléments suivants :

-   Type de version
-   Date et heure
-   Comptabilité de contrôle de gestion
-   Exercice
-   Période fiscale

Le calcul des frais généraux est effectué indépendamment de la version. Par conséquent, vous pouvez calculer la version de budget avant la version actuelle. Le calcul des frais généraux comporte quatre étapes, comme le montre l’illustration suivante. Dans chaque étape, un en-tête de journal avec des entrées de journal est créé. Cet en-tête de journal conserve les données de saisie pour chaque étape de calcul. Les stratégies et les règles s’appliquent à chaque ligne de journal, et les entrées de coût sont générées comme une sortie. Par conséquent, vous disposez toujours d’une traçabilité complète. 

[![Calcul des frais généraux](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a>Calculer et affecter les frais généraux Électricité
Dans la comptabilité financière, certaines coûts, tels que l’électricité, sont enregistrés comme montant forfaitaire. Par conséquent, l’analyse détaillée n’est pas fournie pour le contrôle de gestion. Dans le Contrôle de gestion, pour fournir une analyse correcte entre toutes les unités et tous les niveaux de l’organisation, les coûts doivent suivre les unités organisationnelles. Ce flux doit reposer sur un enregistrement précis de la consommation ou sur une évaluation juste. Dans la comptabilité, le coût de l’électricité peut être validé comme indiqué dans le tableau suivant.

<table>
<thead>
<tr>
<th>Date comptable</th>
<th colspan="2">Centre de coût</th>
<th colspan="2">Compte principal</th>
<th>Montant en devise comptable</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 janvier 2017</td>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>10 000,00</td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a>Étape 1 : Traiter le calcul du comportement de coûts

Par défaut, lorsque des entrées de coût sont importées depuis les données sources, elles reçoivent la classification de comportement de coûts **Non classifié** dans le contrôle de gestion. Lorsque vous appliquez des règles de stratégie de comportement de coûts, vous pouvez reclassifier des entrées de coûts en **Coût fixe** ou **Coût variable**.

#### <a name="define-the-cost-behavior-rule"></a>Définir la règle de comportement de coûts

Dans certains cas, une partie du coût est classifiée en frais fixes, et le coût restant est basé sur la consommation. Les factures d’électricité correspondent souvent à cette définition. Après avoir payé les frais fixes spécifiques, vous payez la consommation horaire au kilowatt (KWH). Par exemple, si les frais de coût fixe sont de 1 000,00, voici comment la règle de comportement de coûts est définie :

-   Montant fixe 1 000,00
    -   0 &lt;= 1 000,00 = Fixe
    -   1 000,01 &lt; N = Variable

##### <a name="journal"></a>Journal de saisie

<table>
<thead>
<tr>
<th>Journal de saisie</th>
<th>Type de journal</th>
<th colspan="3">Période de calendrier fiscal</th>
<th>Version</th>
</tr>
</thead>
<tbody>
<tr>
<td>00001</td>
<td>Journal de calcul de comportement de coûts</td>
<td>Exercice</td>
<td>2017</td>
<td>Période 1</td>
<td>Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Entrées du journal (pour le solde d’objet de coût)

<table>
<thead>
<tr>
<th>Date comptable</th>
<th colspan="2">Objet de coût</th>
<th colspan="2">Élément de coût</th>
<th>Comportement de coûts</th>
<th>Montant</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 janvier 2017</td>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>Non classifié</td>
<td>10 000,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Écritures de coût

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th colspan="2">Élément de coût</th>
<th>Comportement de coûts</th>
<th>Montant</th>
<th>Date comptable</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>Non classifié</td>
<td>10 000,00</td>
<td>3 janvier 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>Non classifié</td>
<td>-10 000,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>1 000,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>9 000,00</td>
<td>31 janvier 2017</td>
</tr>
</tbody>
</table>

Pour plus d’informations, voir [Créer et affecter une stratégie de comportement de coûts à une unité de contrôle des coûts](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).
### <a name="step-2-process-the-cost-distribution-calculation"></a>Étape 2 : Traiter le calcul de distribution des coûts

La distribution des coûts est utilisée pour redistribuer le coût d’un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée. La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l’élément de coût principal du coût d’origine.

#### <a name="define-the-cost-distribution-rule"></a>Définir la règle de distribution de coûts

Dans la comptabilité financière, les coûts d’électricité sont souvent enregistrés comme un montant forfaitaire. Dans le Contrôle de gestion, cette approche n’est pas assez détaillée. Le coût variable doit être attribué aux différents objets de coûts sur une base juste. La base de répartition la plus logique est la consommation de l’électricité (KWH). Un membre de dimension statistique nommé Électricité est créé, et la consommation d’électricité est enregistrée. Par défaut, tous les membres de dimension statistiques sont disponibles comme base de répartition.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Kwh</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>1 000</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>6 000</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>0</td>
</tr>
</tbody>
</table>

Le tableau suivant illustre le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Ampleur</th>
<th>Facteur de répartition</th>
<th>Montant</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>1 000</td>
<td>(1 000 ÷ 7 000) × 9 000,00</td>
<td>1,285.71</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>6 000</td>
<td>(6 000 ÷ 7 000) × 9 000,00</td>
<td>7,714.29</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>0</td>
<td>(0 ÷ 7 000) × 9 000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

Le coût fixe doivt être attribué de façon égale aux différents objets de coût qui ont consommé l’électricité. Vous pouvez obtenir ce résultat à l’aide du membre de dimension statistique Électricité dans une base de répartition de formule : (Électricité &gt; 0,00). Le tableau suivant présente le résultat lorsque la consommation d’électricité est appliquée comme base de répartition de coûts variables.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Formule</th>
<th>Ampleur</th>
<th>Facteur de répartition</th>
<th>Montant</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>(1 000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1 000,00</td>
<td>500,00</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>(6 000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1 000,00</td>
<td>500,00</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>(0 &gt; 0,00)</td>
<td>0</td>
<td>(0 ÷ 2) × 1 000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Journal de saisie

<table>
<thead>
<tr>
<th>Journal de saisie</th>
<th>Type de journal</th>
<th colspan="3">Période de calendrier fiscal</th>
<th>Version</th>
</tr>
</thead>
<tbody>
<tr>
<td>00002</td>
<td>Journal de calcul de la distribution des coûts</td>
<td>Exercice</td>
<td>2017</td>
<td>Période 1</td>
<td>Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Entrées du journal (pour le solde d’objet de coût)

<table>
<thead>
<tr>
<th>Date comptable</th>
<th colspan="2">Objet de coût</th>
<th colspan="2">Élément de coût</th>
<th>Comportement de coûts</th>
<th>Montant</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 janvier 2017</td>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>1 000,00</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>9 000,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Écritures de coût

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th colspan="2">Élément de coût</th>
<th>Comportement de coûts</th>
<th>Montant</th>
<th>Date comptable</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>-1 000,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>500,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>500,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centre de coût par défaut</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>-9 000,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>1,285.71</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>7,714.29</td>
<td>31 janvier 2017</td>
</tr>
</tbody>
</table>

Pour plus d’informations, voir [Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts](tasks/create-assign-cost-distribution-policy-cost-control-unit.md). 

### <a name="step-3-process-the-overhead-rate-calculation"></a>Étape 3 : Traitement du calcul de taux de frais généraux

Le taux de frais généraux est utilisé pour imputer un ou plusieurs objets spécifiques de coût. Les frais sont basés sur un taux de coût prédéterminé et l’ampleur de la base d’affectation de répartition. 

#### <a name="define-the-overhead-rate"></a>Définition du taux de frais généraux

L’objet de coût CC001 HR contribue à un ensemble de projets internes. Un membre de dimension statistique nommé Projets HR est créé pour mesurer l’ampleur de consommation.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Heures</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>Projet 1</td>
<td>3</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Projet 2</td>
<td>1</td>
</tr>
</tbody>
</table>

Un taux de coût prédéterminé pour la contribution des projets de coûts a été défini.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Élément de coût</th>
<th>Comportement de coûts</th>
<th>Unités</th>
<th>Taux</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>Coût variable</td>
<td>1</td>
<td>10</td>
</tr>
</tbody>
</table>

Le tableau suivant présente le résultat lorsque les projets HR sont utilisés comme base de répartition.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Ampleur</th>
<th>Élément de coût</th>
<th>Facteur de répartition</th>
<th>Montant</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>Projet 1</td>
<td>3</td>
<td>10001</td>
<td>(3 ÷ 1) × 10m00</td>
<td>30,00</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Projet 2</td>
<td>1</td>
<td>10001</td>
<td>(1 ÷ 1) × 10,00</td>
<td>10,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Journal de saisie

<table>
<thead>
<tr>
<th>Journal de saisie</th>
<th>Type de journal</th>
<th colspan="3">Période de calendrier fiscal</th>
<th>Version</th>
</tr>
</thead>
<tbody>
<tr>
<td>00003</td>
<td>Journal de calcul de taux de frais généraux</td>
<td>Exercice</td>
<td>2017</td>
<td>Période 1</td>
<td>Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a>Entrées du journal (pour le calcul du taux de frais généraux)

<table>
<thead>
<tr>
<th>Date comptable</th>
<th colspan="2">Objet de coût</th>
<th>Ampleur</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 janvier 2017</td>
<td>Proj 1</td>
<td>Projet interne 1</td>
<td>3,00</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>Proj 2</td>
<td>Projet interne 2</td>
<td>1,00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Écritures de coût

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th colspan="2">Élément de coût</th>
<th>Comportement de coûts</th>
<th>Montant</th>
<th>Date comptable</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC0001</td>
<td>RH</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>-30,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Proj 1</td>
<td>Projet interne 1</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>30,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>-10,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Projet interne 2</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>10.00</td>
<td>31 janvier 2017</td>
</tr>
</tbody>
</table>

Pour plus d’informations, voir [Exécuter le calcul des frais généraux](cost-rollup.md#perform-overhead-calculation).

### <a name="step-4-process-the-cost-allocation-calculation"></a>Étape 4 : Traiter le calcul de répartition des coûts

La répartition est utilisée pour affecter le solde d’un objet de coût à d’autres objets de coût en appliquant une base de répartition. Finance prend en charge la méthode de répartition réciproque. Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés. Le système détermine automatiquement l’ordre correct selon lequel exécuter les répartitions. Le solde d’un objet de coût est réparti par une seule base de répartition. Les répartitions entre plusieurs dimensions d’objets de coût et leurs membres respectifs sont prises en charge. L’ordre de répartition est contrôlé par l’unité de contrôle des coûts. 

[![Méthode réciproque](./media/reciprocal-method.png)](./media/reciprocal-method.png)

#### <a name="define-the-cost-allocation"></a>Définir la répartition de coût

Voici un exemple simple expliquant comment suivre le flux du coût. L’objet de coût CC001 HR contribue à plusieurs objets de coûts. Un membre de dimension statistique nommé Services HR est créé pour mesurer l’ampleur de consommation.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Services HR</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>35</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>55</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>10</td>
</tr>
</tbody>
</table>

L’objet de coût CC002 Finance contribue à plusieurs objets de coûts. Un membre de dimension statistique nommé Services Finance est créé pour mesurer l’ampleur de consommation.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Services Finance</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>65</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>35</td>
</tr>
</tbody>
</table>

L’objet de coût CC003 Assemblage contribue à plusieurs objets de coûts. Un membre de dimension statistique nommé Services Assemblage est créé pour mesurer l’ampleur de consommation.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Services Assemblage (heures)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>60</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>20</td>
</tr>
</tbody>
</table>

L’objet de coût CC004 Emballage contribue à plusieurs objets de coûts. Un membre de dimension statistique nommé Services Emballage est créé pour mesurer l’ampleur de consommation.

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Services Emballage (heures)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>80</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>15</td>
</tr>
</tbody>
</table>

> [!NOTE]
> Les mesures statistiques telles que les heures de production qu’un produit consomme peuvent être dérivées des données sources. Pour plus d’informations, voir [Modèle de fournisseur de mesures statistiques](statistical-measure-provider-template.md#statistical-measure-provider-template). Le tableau suivant présente le résultat lorsque les services RH sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Ampleur</th>
<th>Facteur de répartition</th>
<th>Montant</th>
<th>Comportement de coûts</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>35</td>
<td>(35 ÷ 100) × 500,00</td>
<td>175.00</td>
<td>Coût fixe</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>55</td>
<td>(55 ÷ 100) × 500,00</td>
<td>275.00</td>
<td>Coût fixe</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>10</td>
<td>(10 ÷ 100) × 500,00</td>
<td>50,00</td>
<td>Coût fixe</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>35</td>
<td>(35 ÷ 100) × 1 245,71</td>
<td>436.00</td>
<td>Coût variable</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>55</td>
<td>(55 ÷ 100) × 1 245,71</td>
<td>685.14</td>
<td>Coût variable</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>10</td>
<td>(10 ÷ 100) × 1 245,71</td>
<td>124.57</td>
<td>Coût variable</td>
</tr>
</tbody>
</table>

Le tableau suivant présente le résultat lorsque les services Finance sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Ampleur</th>
<th>Facteur de répartition</th>
<th>Montant</th>
<th>Comportement de coûts</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>65</td>
<td>(65 ÷ 100) × (500,00 + 175,00)</td>
<td>438.75</td>
<td>Coût fixe</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>35</td>
<td>(35 ÷ 100) × (500,00 + 175,00)</td>
<td>236.25</td>
<td>Coût fixe</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>65</td>
<td>(65 ÷ 100) × (7 714,29 + 436,00)</td>
<td>5,297.69</td>
<td>Coût variable</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>35</td>
<td>(35 ÷ 100) × (7 714,29 + 436,00)</td>
<td>2,852.60</td>
<td>Coût variable</td>
</tr>
</tbody>
</table>

Le tableau suivant présente le résultat lorsque les services Assemblage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Ampleur</th>
<th>Facteur de répartition</th>
<th>Montant</th>
<th>Comportement de coûts</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>60</td>
<td>(60 ÷ 80) × (275,00 + 438,75)</td>
<td>535.31</td>
<td>Coût fixe</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>20</td>
<td>(20 ÷ 80) × (275,00 + 438,75)</td>
<td>178.44</td>
<td>Coût fixe</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>60</td>
<td>(60 ÷ 80) × (5 297,69 + 685,14)</td>
<td>4,487.12</td>
<td>Coût variable</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>20</td>
<td>(20 ÷ 80) × (5 297,69 + 685,14)</td>
<td>1,495.71</td>
<td>Coût variable</td>
</tr>
</tbody>
</table>

Le tableau suivant présente le résultat lorsque les services Emballage sont utilisés comme base de répartition pour le coût total (coût fixe et coût variable).

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th>Ampleur</th>
<th>Facteur de répartition</th>
<th>Montant</th>
<th>Comportement de coûts</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>80</td>
<td>(80 ÷ 95) × (50,00 + 236,25)</td>
<td>241.05</td>
<td>Coût fixe</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>15</td>
<td>(15 ÷ 95) × (50,00 + 236,25)</td>
<td>45.20</td>
<td>Coût fixe</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>80</td>
<td>(80 ÷ 95) × (2 852,60 + 124,57)</td>
<td>2,507.09</td>
<td>Coût variable</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>15</td>
<td>(15 ÷ 95) × (2 852,60 + 124,57)</td>
<td>470.08</td>
<td>Coût variable</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Entrées du journal (pour le solde d’objet de coût)

<table>
<thead>
<tr>
<th>Journal de saisie</th>
<th>Type de journal</th>
<th colspan="3">Période de calendrier fiscal</th>
<th>Version</th>
</tr>
</thead>
<tbody>
<tr>
<td>00004</td>
<td>Journal de répartition des coûts</td>
<td>Exercice</td>
<td>2017</td>
<td>Période 1</td>
<td>Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a>Lignes de journal

<table>
<thead>
<tr>
<th>Date comptable</th>
<th colspan="2">Objet de coût</th>
<th colspan="2">Élément de coût</th>
<th>Comportement de coûts</th>
<th>Montant</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 janvier 2017</td>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>500,00</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>1,245.71</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>CC002</td>
<td>Finances</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>675.00</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>CC002</td>
<td>Finances</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>8,150.29</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>713.75</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>5,982.83</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>CC003</td>
<td>Emballage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>286.25</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>CC003</td>
<td>Emballage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>2,977.17</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>Prod 1</td>
<td>Produit 1</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>776.36</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>Prod 1</td>
<td>Produit 1</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>6,994.21</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>Prod 2</td>
<td>Produit 1</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>223.64</td>
</tr>
<tr>
<td>31 janvier 2017</td>
<td>Prod 2</td>
<td>Produit 1</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>1,965.79</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Écritures de coût

<table>
<thead>
<tr>
<th colspan="2">Objet de coût</th>
<th colspan="2">Élément de coût</th>
<th>Comportement de coûts</th>
<th>Montant</th>
<th>Date comptable</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>-500,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>175.00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>275.00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>50,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>-1 245,71</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>436.00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>685.14</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>124.57</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>-675,00</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>438.75</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>236.25</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finances</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>-8 150,29</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>5,297.69</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Emballage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>2,852.60</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>-713,75</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>535.31</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>178.44</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>-5 982,83</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>4,487.12</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>1,495.71</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>-286,25</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>241.05</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût fixe</td>
<td>45.20</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Assemblage</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>-2 977,17</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Prod 1</td>
<td>Produit 1</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>2,507.09</td>
<td>31 janvier 2017</td>
</tr>
<tr>
<td>Prod 2</td>
<td>Produit 2</td>
<td>10001</td>
<td>Électricité</td>
<td>Coût variable</td>
<td>470.08</td>
<td>31 janvier 2017</td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a>Conclusion
Dans la comptabilité financière, un coût de 10 000,00 pour l’électricité est imputé sur un ID de centre de coût fictif. Par conséquent, les comptables sauront que ce coût doit être affecté. Dans le Contrôle de gestion, les coûts transitent entre les unités et les niveaux de l’organisation, selon les stratégies et les règles qui sont appliquées. Chacun coût est associé à une base de répartition qui fournit les meilleures évaluation de répartition des coûts.

<table>
<thead>
<tr>
<th colspan="2" rowspan="2">Élément de coût</th>
<th colspan="9">Objet de coût</th>
<th rowspan="2">Total</th>
</tr>
<tr>
<th>CC099</th>
<th>CC001</th>
<th>CC002</th>
<th>CC003</th>
<th>CC004</th>
<th>Proj 1</th>
<th>Proj 2</th>
<th>Prod 1</th>
<th>Prod 2</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">10001 Électricité</td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"><strong>0.00</strong></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><strong>30.00</strong></td>
<td style="text-align: right;"><strong>10.00</strong></td>
<td style="text-align: right;"><strong>7,770.57</strong></td>
<td style="text-align: right;"><strong>2,189.43</strong></td>
<td style="text-align: right;"><strong>10,000.00</strong></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;">Non classifié</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Coût fixe</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;">776.36</td>
<td style="text-align: right;">223.64</td>
<td style="text-align: right;"><strong>1 000,00</strong></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Coût variable</td>
<td style="text-align: right;">000</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">30,00</td>
<td style="text-align: right;">10,00</td>
<td style="text-align: right;">6,994.21</td>
<td style="text-align: right;">1,965.79</td>
<td style="text-align: right;"><strong>9,000.00</strong></td>
</tr>
</tbody>
</table>

> [!NOTE]
> Cette rubrique explique comment un élément de coût principal, 10001 Électricité, alimente les objets de coût. Par conséquent, ce coût de frais généraux est affecté au plus bas niveau dans l’organisation. Autrement dit, les objets de coût de plus bas niveau supportent le coût. Pour obtenir un flux visuel du coût entre les objets de coût, vous pouvez utiliser les règles de stratégie de repositionnement des coûts de visualiser le flux de coûts. Pour plus d’informations, voir [Stratégie de repositionnement des coûts et calcul des frais généraux](cost-rollup.md)..





[!INCLUDE[footer-include](../../includes/footer-banner.md)]