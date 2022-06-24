---
title: Double déclaration
description: Cet article vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseBookMaster
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9941d0bb251a95a71338c59f6eaa4bb9a505a5b5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886369"
---
# <a name="dual-reporting"></a>Double déclaration

[!include [banner](../includes/banner.md)]

Cet article vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs. Il est nécessaire d’être familiarisé avec les couches de validation dans Microsoft Dynamics 365 Finance, ce qui rendra l’exemple plus facile à comprendre.

## <a name="example"></a>Exemple

L’exemple suivant rend compte d’un contrat de location selon le reporting statutaire italien en utilisant à la fois la méthode de la comptabilité de caisse et les méthodes de reporting IFRS. L’entreprise doit établir trois registres pour tenir compte à la fois des exigences légales italiennes et des exigences d’IFRS 16. Un registre est requis pour IFRS 16, un registre est requis pour les exigences statutaires et un registre est requis pour annuler automatiquement les écritures statutaires. Les registres sont configurés comme indiqué dans les tableaux suivants.

**Registre IFRS 16**

Le registre IFRS 16 est mis en place de manière à être conforme à la norme comptable IFRS 16. Toutes les entrées publiées dans ce livre seront publiées sur une couche personnalisée.

| Nom                                    | Description    |
|-----------------------------------------|----------------|
| Type de registre                               | IFRS 16        |
| Description du registre                        | IFRS 16        |
| Couche de comptabilisation                           | Couche personnalisée 1 |
| Type de bail                              | Finances        |
| Structure comptable                    | IFRS 16        |
| Configuration Durée du bail/Durée de vie utile         | 0,00           |
| Configuration Valeur actuelle/Juste valeur de l’actif | 0,00           |
| Seuil à court terme                    | 12             |
| Seuil de faible valeur                     | 5,000.00       |
| Payer au fournisseur                           | Non             |

**Registre statutaire**

Le registre statutaire est un registre de comptabilité de caisse dans lequel la société comptabilise les frais de location comme le montant en espèces payé chaque mois pour le loyer. Ce registre ne produira pas de droit d’utilisation de l’actif (ROU) ni de passif locatif.

| Nom                                    | Description |
|-----------------------------------------|-------------|
| Type de registre                               | Statutaire   |
| Description du registre                        | GAAP local  |
| Couche de comptabilisation                           | Actuelle     |
| Type de bail                              | Automatique   |
| Structure comptable                    | Base de trésorerie  |
| Configuration Durée du bail/Durée de vie utile         | 0,00        |
| Configuration Valeur actuelle/Juste valeur de l’actif | 0,00        |
| Seuil à court terme                    | 0           |
| Seuil de faible valeur                     | 0           |
| Payer au fournisseur                           | Non          |

**Registre de contrepassation statutaire**

Le registre de contrepassation statutaire est constitué de la même manière que le registre statutaire.

| Nom                                    | Description                    |
|-----------------------------------------|--------------------------------|
| Type de registre                               | Statutaire – contrepassation           |
| Description du registre                        | Registre pour contrepasser le registre statutaire |
| Couche de comptabilisation                           | Couche personnalisée 1                 |
| Type de bail                              | Automatique                      |
| Structure comptable                    | Base de trésorerie                     |
| Configuration Durée du bail/Durée de vie utile         | 0,00                           |
| Configuration Valeur actuelle/Juste valeur de l’actif | 0,00                           |
| Seuil à court terme                    | 0                              |
| Seuil de faible valeur                     | 0                              |
| Payer au fournisseur                           | Non                             |

Pour cet exemple, un bail a été créé avec les paramètres suivants sur les onglets **Général** et **Lignes d’échéancier de paiement**.

**Onglet Général**

| Champ                      | Valeur            |
|----------------------------|------------------|
| Taux d’emprunt marginal | 5 %               |
| Date d’entrée en vigueur          | 1/1/2020         |
| Groupe de baux                | Bâtiments        |
| Fournisseur                     | 1001             |
| Juste valeur de l’actif    | 245,000          |
| Durée de vie utile de l’actif          | 120              |
| Type d’annuité               | Annuité ordinaire |
| Intervalle de composition       | Tous les mois          |

**Onglet Lignes d’échéancier de paiement**

| Champ             | Valeur      |
|-------------------|------------|
| Date de début        | 1/1/2020   |
| Intervalle de périodes   | Mois     |
| Périodes           | 24         |
| Date de fin          | 31/12/2020 |
| Fréquence de paiement | Tous les mois    |
| Montant du paiement    | 1 000      |

Pour tenir compte de ce bail sous deux structures, vous utilisez une couche de validation actuelle et une couche de validation personnalisée. Le tableau suivant montre un exemple de chaque écriture de journal nécessaire pour représenter fidèlement les données financières selon chaque norme de reporting. Une description détaillée de chaque écriture de journal pour le premier mois du bail est fournie par la suite.

<table>
<thead>
<tr>
<th rowspan='3'>Numéro de compte</th>
<th rowspan='3'>Description</th>
<th colspan='3'>Registre statutaire (couche actuelle)</th>
<th rowspan='3'>Total de la couche actuelle</th>
<th>Registre de contrepassation (couche personnalisée)</th>
<th colspan='4'>Registre IFRS 16 (couche personnalisée)</th>
<th rowspan='3'>Couche actuelle + total de la couche personnalisée</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
<th>JE-130</th>
<th>JE-140</th>
<th>JE-150</th>
<th>JE-160</th>
<th>JE-170</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Dépense de bail</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
<td>-1 000,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>2</td>
<td>Frais bancaires</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Dépenses de TVA</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Compte de compensation</td>
<td>-1 000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
<td>1,000.00</td>
<td></td>
<td>-1 000,00</td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Module Comptabilité fournisseur</td>
<td></td>
<td>+1 008,00</td>
<td>1,008.00</td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Droit d’utilisation de l’actif</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>22,794.00</td>
<td></td>
<td></td>
<td></td>
<td>22,793.90</td>
</tr>
<tr>
<td>7</td>
<td>Obligation de contrat de location-financement</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>-22 794,00</td>
<td>1,000.00</td>
<td>-94,97</td>
<td></td>
<td>-21 888,87</td>
</tr>
<tr>
<td>8</td>
<td>Dépenses d’intérêts</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td>94.97</td>
<td></td>
<td>94.97</td>
</tr>
<tr>
<td>9</td>
<td>Monétaire</td>
<td></td>
<td></td>
<td>+1 008,00</td>
<td>+1 008,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>+1 008,00</td>
</tr>
<tr>
<td>10</td>
<td>Dépenses d’amortissement</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>949.75</td>
<td>949.75</td>
</tr>
<tr>
<td>11</td>
<td>Amortissement cumulé</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-949,75</td>
<td>-949,75</td>
</tr>
</tbody>
</table>

Comme le montre le tableau précédent, trois registres sont tenus pour déclarer à la fois le reporting statutaire et le reporting IFRS.

- Le registre statutaire enregistre le paiement de location selon les règles de comptabilité de caisse sous la couche actuelle.
- Le registre de contrepassation statutaire annule les écritures au journal statutaire.
- Le registre IFRS 16 crée les écritures de journal requises en vertu d’IFRS 16.

Vous ne devez saisir un bail qu’une seule fois. Vous pouvez ensuite ouvrir la page **Registres** pour voir tous les registres associés au bail.

> [!NOTE]
> Lorsque vous créez les registres, tous les trois doivent être associés au même enregistrement de bail.

La première écriture de journal enregistre les frais de location dans le registre statutaire. Vous pouvez créer les paiements soit par lots, soit en sélectionnant l’échéancier de paiement dans le registre statutaire.

Pour cet exemple, l’écriture de journal suivante est produite pour le registre statutaire à partir de l’échéancier de paiement.

### <a name="lease-payment--1312020--je-100"></a>Paiement de location – 31/01/2020 – JE 100

| Type de compte | Numéro de compte | Couche   | Description du compte | Débit    | Crédit   |
|--------------|----------------|---------|---------------------|----------|----------|
| Registre       | 1              | Actuelle | Dépense de bail       | 1,000.00 |          |
| Registre       | 4              | Actuelle | Compte de compensation    |          | 1,000.00 |

Un commis aux comptes fournisseurs utilise la fonctionnalité standard de Dynamics 365 pour créer une facture pour payer le bail en dehors de la location d’actifs. Cependant, au lieu de sélectionner **Frais de location** comme compte de débit, le commis aux comptes fournisseurs sélectionne un compte de compensation pour générer l’écriture suivante.

### <a name="ap-process--1312020--je-110"></a>Processus AP – 31/01/2020 – JE 110

| Type de compte | Numéro de compte | Couche   | Description du compte | Débit    | Crédit   |
|--------------|----------------|---------|---------------------|----------|----------|
| Registre       | 4              | Actuelle | Compte de compensation    | 1,000.00 |          |
| Registre       | 2              | Actuelle | Frais bancaires            | 3.00     |          |
| Registre       | 3              | Actuelle | Dépenses de TVA         | 5.00     |          |
| Fournisseur       | 5              | Actuelle | Module Comptabilité fournisseur    |          | 1,008.00 |

Lorsque la déclaration est délivrée au fournisseur, vous suivez le processus de paiement régulier. Au cours de ce processus, l’écriture de journal suivante est générée.

### <a name="cash-payment--1312020--je-120"></a>Paiement en espèces – 31/01/2020 – JE 120

| Type de compte | Numéro de compte | Couche   | Description du compte | Débit    | Crédit   |
|--------------|----------------|---------|---------------------|----------|----------|
| Fournisseur       | 5              | Actuelle | Comptabilité fournisseur    | 1,008.00 |          |
| Banque         | 9              | Actuelle | Monétaire                |          | 1,008.00 |

À ce stade, vous avez pleinement pris en compte ce bail conformément aux exigences légales en matière de rapports et pouvez générer une balance comptable en utilisant la couche actuelle. Le système renvoie une balance comptable qui a les chiffres suivants.

<table>
<thead>
<tr>
<th rowspan='3'>Numéro de compte</th>
<th rowspan='3'>Description</th>
<th colspan='3'>Registre statutaire (couche actuelle)</th>
<th rowspan='3'>Total de la couche actuelle</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Dépense de bail</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
</tr>
<tr>
<td>2</td>
<td>Frais bancaires</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Dépenses de TVA</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Compte de compensation</td>
<td>-1 000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Module Comptabilité fournisseur</td>
<td></td>
<td>+1 008,00</td>
<td>1,008.00</td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Droit d’utilisation de l’actif</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>7</td>
<td>Obligation de contrat de location-financement</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>8</td>
<td>Dépenses d’intérêts</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>9</td>
<td>Monétaire</td>
<td></td>
<td></td>
<td>+1 008,00</td>
<td>+1 008,00</td>
</tr>
<tr>
<td>10</td>
<td>Dépenses d’amortissement</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>11</td>
<td>Amortissement cumulé</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
</tbody>
</table>

Si vous souhaitez utiliser les chiffres IFRS 16 pour exécuter la même balance comptable, les écritures comptables statutaires doivent être contrepassées et les écritures comptables IFRS 16 doivent être enregistrées. Pour contrepasser les écritures statutaires, cet exemple inclut un registre de contrepassation statutaire qui a la même configuration que le registre statutaire mais un profil de validation opposé. Par exemple, le registre statutaire *a débité* un compte de charges de location, mais le registre de contrepassation va *créditer* ce compte. Ces relations sont facilement définies dans les comptes de comptabilisation de la location d’actifs sur la page **Paramètres de location d’actifs** (**Location d’actifs \> Configurer \> Paramètres de location d’actifs**).

Lorsque le même processus que celui utilisé pour le registre statutaire est utilisé pour le registre de contrepassation, l’écriture de journal suivante est produite. La différence est que le registre de contrepassation comptabilise les écritures de contrepassation du registre statutaire. Les écritures de contrepassation sont également apportées à la couche personnalisée. Lorsqu’une balance comptable est exécutée au niveau de la couche actuelle, les écritures de journal de contrepassation ne sont pas incluses.

### <a name="lease-payment--1312020--je-130"></a>Paiement de location – 31/01/2020 – JE 130

| Type de compte | Numéro de compte | Couche  | Description du compte | Débit    | Crédit   |
|--------------|----------------|--------|---------------------|----------|----------|
| Registre       | 4              | Personnalisée | Compte de compensation    | 1,000.00 |          |
| Registre       | 1              | Personnalisée | Dépense de bail       |          | 1,000.00 |

Maintenant que vous avez éliminé les écritures de journal statutaires, vous allez enregistrer toutes les écritures de journal requises par IFRS 16 dans le livre IFRS 16. Ces écritures comprennent la reconnaissance initiale du droit d’utilisation de l’actif et du passif, ainsi que l’enregistrement des intérêts et des amortissements.

### <a name="initial-recognition--112020--je-140"></a>Reconnaissance initiale – 1/1/2020 – JE 140

| Type de compte | Numéro de compte | Couche  | Description du compte      | Débit     | Crédit    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| Registre       | 6              | Personnalisée | Droit d’utilisation de l’actif                | 22,793.90 |           |
| Registre       | 7              | Personnalisée | Obligation de contrat de location-financement |           | 22,793.90 |

Le paiement de location est comptabilisé comme les autres paiements de location. La raison de l’utilisation du compte de compensation est de s’assurer que les espèces ne sont créditées qu’une seule fois.

### <a name="lease-payment--1312020--je-150"></a>Paiement de location – 31/01/2020 – JE 150

| Type de compte | Numéro de compte | Couche  | Description du compte      | Débit    | Crédit   |
|--------------|----------------|--------|--------------------------|----------|----------|
| Registre       | 7              | Personnalisée | Obligation de contrat de location-financement | 1,000.00 |          |
| Registre       | 4              | Personnalisée | Compte de compensation         |          | 1,000.00 |

L’écriture de journal des charges d’intérêts est générée à partir du calendrier d’amortissement du passif.

### <a name="interest-expense--1312020--je-160"></a>Dépenses d’intérêts – 31/1/2020 – JE 160

| Type de compte | Numéro de compte | Couche  | Description du compte      | Débit | Crédit |
|--------------|----------------|--------|--------------------------|-------|--------|
| Registre       | 8              | Personnalisée | Dépenses d’intérêts         | 94.97 |        |
| Registre       | 7              | Personnalisée | Obligation de contrat de location-financement |       | 94.97  |

L’écriture de journal de dépense d’amortissement est générée à partir du programme d’amortissement du passif.

### <a name="depreciation-expense--1312020--je-170"></a>Dépenses d’amortissement – 1/31/2020 – JE 170

| Type de compte | Numéro de compte | Couche  | Description du compte      | Débit  | Crédit |
|--------------|----------------|--------|--------------------------|--------|--------|
| Registre       | 10             | Personnalisée | Dépenses d’amortissement     | 949.75 |        |
| Registre       | 11             | Personnalisée | Amortissement cumulé |        | 949.75 |

Une fois toutes ces entrées de journal créées et validées, vous verrez les valeurs de « couche personnalisée 1 » suivantes. Notez que la dernière colonne comprend les frais bancaires, les frais de taxe sur la valeur ajoutée (TVA) et la réduction des liquidités de la couche précédente, mais elle n’inclut pas les écritures de reporting statutaires. Par conséquent, vous obtenez de véritables capacités de double reporting. À ce stade, l’entreprise doit simplement exécuter sa balance comptable et combiner la couche actuelle et la couche personnalisée pour créer une balance comptable IFRS.

| N° de compte | Description              | Registre statutaire\-Couche actuelle\-JE\-100\-Dr \(Cr\) | Registre statutaire\-Couche actuelle\-JE\-110\-Dr \(Cr\) | Registre statutaire\-Couche actuelle\-JE\-120\-Dr \(Cr\) | Couche actuelle \- Totaux | - | Registre de contrepassation\-Couche personnalisée\-JE\-130\-Dr \(Cr\) | Registre IFRS 16\-Couche personnalisée\-JE\-140\-Dr \(Cr\) | Registre IFRS 16\-Couche personnalisée\-JE\-150\-Dr \(Cr\) | Registre IFRS 16\-Couche personnalisée\-JE\-160\-Dr \(Cr\) | Registre IFRS 16\-Couche personnalisée\-JE\-170\-Dr \(Cr\) | Couche personnalisée \+ Couche actuelle \- Totaux |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| 1          | Dépense de bail            | 1,000\.00                                         |                                                   |                                                   | 1,000\.00               |   | \-1 000                                         |                                                |                                                |                                                |                                                | 0\.00                                   |
| 2          | Frais bancaires                 |                                                   | 3\.00                                             |                                                   | 3\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 3\.00                                   |
| 3          | Dépenses de TVA              |                                                   | 5\.00                                             |                                                   | 5\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 5\.00                                   |
| 4          | Compte de compensation         | \-1 000\.00                                       | 1,000\.00                                         |                                                   | 0\.00                   |   | 1 000                                           |                                                | \-1 000                                        |                                                |                                                | 0\.00                                   |
| 5          | Module Comptabilité fournisseur         |                                                   | \-1 008\.00                                       | 1,008\.00                                         | 0\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 0\.00                                   |
| 6          | Droit d’utilisation de l’actif                |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | 22,794                                         |                                                |                                                |                                                | 22,793\.90                              |
| 7          | Obligation de contrat de location-financement |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | \-22 794                                       | 1 000                                          | \-94\.97                                       |                                                | \-21 888\.87                            |
| 8          | Dépenses d’intérêts         |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                | 94\.97                                         |                                                | 94\.97                                  |
| 9          | Monétaire                     |                                                   |                                                   | \-1 008\.00                                       | \-1 008\.00             |   |                                                 |                                                |                                                |                                                |                                                | \-1 008\.00                             |
| 10         | Dépenses d’amortissement     |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | 949\.75                                        | 949\.75                                 |
| 11         | Amortissement cumulé |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | \-949\.75                                      | \-949\.75                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
