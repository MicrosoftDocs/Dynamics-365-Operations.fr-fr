---
title: Règles d’arrondi du calcul de la taxe
description: Cette rubrique fournit des informations sur les règles d'arrondi dans les paramètres de calcul de la taxe du service de calcul des taxes.
author: kailiang
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 167db4d836aa754509bb28677916a30901cebbbb
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694172"
---
# <a name="tax-calculation-rounding-rules"></a>Règles d’arrondi du calcul de la taxe

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur la façon dont fonctionnent les règles d'arrondi dans les paramètres de calcul de la taxe du service de calcul des taxes.

> [!NOTE] 
> Lorsque le service de calcul des taxes est activé, les règles d'arrondi sur les pages **Code taxe** et **Groupe de taxes** ne sont pas effectives.

Vous pouvez consulter la configuration de la règle d'arrondi pour le service de calcul des taxes dans la section **Règle d'arrondi des taxes** dans le raccourci **Calcul** de l'onglet **Général**, sur la page **Paramètres de calcul des taxes** (**Taxe** \> **Paramétrage** \> **Configuration de taxe** \> **Paramètres de calcul des taxes**).

[![Configuration de la règle d'arrondi sur la page Paramètres de calcul des taxes](./media/tax-calculation-parameters-calculation-1.png)](./media/tax-calculation-parameters-calculation-1.png)

Les champs **Précision de l'arrondi** et **Méthode d'arrondi** déterminent comment les montants calculés dans la charge utile à partir du service de calcul des taxes sont arrondis.

## <a name="rounding-precision"></a>Précision de l'arrondi

Le champ **Précision de l'arrondi** prend en charge une valeur comportant jusqu'à six décimales. Par exemple, si vous définissez le champ **Précision d'arrondi** sur **0,000000**, les montants calculés sont arrondis à six décimales, puis envoyés à Microsoft Dynamics 365 Finance. Par exemple, si la méthode d'arrondi **Normal** est utilisée, le montant **987,1234567** est arrondi à **987,123457**.

> [!NOTE]
> Finance arrondit les montants selon les règles d'arrondi des devises. Par conséquent, les montants de taxe qui sont affichés et enregistrés dans les transactions sont affectés à la fois par les règles d'arrondi de calcul des taxes et par les règles d'arrondi des devises.

## <a name="rounding-method"></a>Méthode d'arrondi

La méthode d'arrondi pour le calcul des taxes peut être configurée pour chaque entité juridique. Dans le champ **Méthode d'arrondi**, vous pouvez choisir parmi trois options : **Normal**, **Arrondi au chiffre inférieur** et **Arrondi au chiffre supérieur**.

### <a name="rounding-example"></a>Exemple d'arrondi

Le tableau suivant fournit un exemple qui montre comment le montant **987,345** est arrondi pour différentes combinaisons de précisions d'arrondi et de méthodes d'arrondi.

<table>
<thead>
<tr>
<th rowspan="2">Méthode d'arrondi</th>
<th colspan="8">Précision de l'arrondi</th>
</tr>
<tr>
<th>0,00</th>
<th>0.01</th>
<th>0.10</th>
<th>1.00</th>
<th>10.00</th>
<th>0.02</th>
<th>0.05</th>
<th>0.25</th>
</tr>
</thead>
<tbody>
<tr>
<td>Normal</td>
<td>987.35</td>
<td>987.35</td>
<td>987.30</td>
<td>987.00</td>
<td>990.00</td>
<td>987.34</td>
<td>987.35</td>
<td>987.25</td>
</tr>
<tr>
<td>Inférieur</td>
<td>987.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.00</td>
<td>980.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.25</td>
</tr>
<tr>
<td>Supérieur</td>
<td>988.00</td>
<td>987.35</td>
<td>987.40</td>
<td>988.00</td>
<td>990.00</td>
<td>987.36</td>
<td>987.35</td>
<td>987.50</td>
</tr>
</tbody>
</table>

La logique de calcul et d'arrondi des montants de taxe peut être paramétrée en fonction des règles de taxation.

## <a name="rounding-by"></a>Arrondi à 

Dans le champ **Arrondi par**, sélectionnez le principe d'arrondi qui s'applique aux taxes. Les options suivantes sont disponibles :

- **Codes taxe** : arrondit le montant de taxe dans chaque code taxe.
- **Combinaisons de codes taxe** : arrondit le montant de taxe dans la combinaison de codes de taxe de la ligne.

## <a name="calculation-method"></a>Méthode de calcul

Dans le champ **Méthode de calcul**, sélectionnez si les taxes sur les factures sont calculées pour chaque ligne ou pour toutes les lignes. Les options suivantes sont disponibles :

- **Ligne** : calcule le montant de taxe ligne par ligne. Le montant de taxe sur chaque ligne n'est pas affecté par le montant de taxe des autres lignes.
- **Total** : calcule le montant de taxe pour toutes les lignes d'un même document.

### <a name="rounding-calculation-example"></a>Exemple de calcul d'arrondi

Cet exemple montre les différents calculs qui peuvent être effectués pour une facture, pour différentes combinaisons de valeurs **Arrondi par** et **Méthode de calcul**. Pour cet exemple, la configuration suivante est en place :

- La facture comporte quatre lignes.
- Il existe deux codes taxe : **TVA1** (10 %) et **TVA2** (10 %).
- La précision d'arrondi est définie sur **0,01**.
- La méthode d'arrondi est définie sur **Arrondi au chiffre supérieur**.

#### <a name="rounding-by--tax-codes-and-calculation-method--line"></a>Arrondi par = Codes taxe et Méthode de calcul = Ligne

| Numéro de ligne | Montant net de la ligne | Codes taxe déterminés | Montant de la taxe avant arrondi | Montant de la taxe arrondi |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | TVA1                 | 1.111                      | 1.12               |
| 2           | 22.22           | TVA1 ; TVA2           | 2,222 ; 2,222               | 2,23 ; 2,23         |
| 3           | 33.33           | TVA1                 | 3.333                      | 3.34               |
| 4           | 44.44           | TVA1 ; TVA2           | 4,444 ; 4,444               | 4,45 ; 4,45         |

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--line"></a>Arrondi par = Combinaison codes taxe et Méthode de calcul = Ligne

| Numéro de ligne | Montant net de la ligne | Codes taxe déterminés | Montant de la taxe avant arrondi | Montant de la taxe arrondi |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | TVA1                 | 1.111                      | 1.12               |
| 2\*         | 22.22           | TVA1 ; TVA2           | 2,222 ; 2,222               | 2,23 ; 2,22         |
| 3           | 33.33           | TVA1                 | 3.333                      | 3.34               |
| 4\*\*       | 44.44           | TVA1 ; TVA2           | 4,444 ; 4,444               | 4,45 ; 4,44         |

\* Ligne 2 = Arrondi\[22,22 × (10 % + 10 %)\] = 2,23 + 2,22

\*\* Ligne 4 = Arrondi\[44,44 × (10 % + 10 %)\] = 4,45 + 4,44

#### <a name="rounding-by--tax-codes-and-calculation-method--total"></a>Arrondi par = Codes taxe et Méthode de calcul = Total

| Numéro de ligne | Montant net de la ligne | Codes taxe déterminés | Montant de la taxe avant arrondi | Montant de la taxe arrondi |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | TVA1\*               | 1.111                      | 1.12               |
| 2           | 22.22           | TVA1\* ; TVA2\*\*     | 2,222 ; 2,222               | 2,22 ; 2,23         |
| 3           | 33.33           | TVA1\*               | 3.333                      | 3.33               |
| 4           | 44.44           | TVA1\* ; TVA2\*\*     | 4,444 ; 4,444               | 4,44 ; 4,44         |

\* TVA1(Ligne 1, Ligne 2, Ligne 3, Ligne 4) = Arrondi\[(11,11 + 22,22 + 33,33 + 44,44) × 10 %\] = 1,12 + 2,22 + 3,33 + 4,44

\*\* TVA2(Ligne 2, Ligne 4) = Arrondi\[(22,22 + 44,44) × 10 %\] = 2,23 + 4,44

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--total"></a>Arrondi par = Combinaison codes taxe et Méthode de calcul = Total

| Numéro de ligne | Montant net de la ligne | Codes taxe déterminés | Montant de la taxe avant arrondi | Montant de la taxe arrondi |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1\*         | 11.11           | TVA1                 | 1.111                      | 1.12               |
| 2\*\*       | 22.22           | TVA1 ; TVA2           | 2,222 ; 2,222               | 2,23 ; 2,22         |
| 3\*         | 33.33           | TVA1                 | 3.333                      | 3.33               |
| 4\*\*       | 44.44           | TVA1 ; TVA2           | 4,444 ; 4,444               | 4,44 ; 4,45         |

\* Ligne 1, Ligne 3 = Arrondi\[(11,11 + 33,33) × 10 %\] = 1,12 + 3,33

\*\* Ligne 2, Line 4 = Arrondi\[(22,22 + 44,44) × (10 % + 10 %)\] = 2,23 + 2,22 + 4,44 + 4,45

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
