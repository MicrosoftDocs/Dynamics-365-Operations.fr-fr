---
title: Concepts des congés et des absences
description: Cette rubrique décrit les concepts des congé et des absences, ainsi que le mode de calcul des soldes de congés.
author: andreabichsel
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: ''
ms.openlocfilehash: 96e3aa74e513a2421b04bac049400cf71042e2c8
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "857290"
---
# <a name="leave-and-absence-concepts"></a>Concepts des congés et des absences

[!include[banner](../includes/banner.md)]

Les concepts et les termes décrits dans cette rubrique vous permettent de déterminer la manière dont les congés sont attribués à un employé, et dont les soldes de temps de cet employé sont calculés. Pour plus d'informations sur la gestion des congé et des absences, voir [Gestion des congés et des absences](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).

## <a name="leave-plan-details"></a>Détails du plan de congés

### <a name="start-date"></a>Date de début

La date de début est la date à laquelle débute le processus de régularisation. La date de début sert également de date anniversaire pour calculer les montants reportés.

## <a name="accruals"></a>Régularisations

Les régularisations déterminent le moment et la fréquence d'attribution de congés à un employé. Les stratégies sur le moment où des régularisations doivent être attribuées et celles sur le calcul au prorata sont définies dans la section **Régularisations** lors de la configuration du plan de congé et d'absence.

### <a name="accrual-frequency"></a>Fréquence de régularisation

La fréquence de régularisation définit le nombre de fois où un congé est provisionné ou attribué. Les options suivantes sont disponibles :

- Opérations diverses
- Hebdomadaire
- Bihebdomadaire
- Bimensuel
- Mensuel
- Trimestriel
- Semestriel
- Année
- Aucune

### <a name="accrual-period-basis"></a>Base de la période de régularisation

La base de la période de régularisation détermine la date servant à calculer les périodes de régularisation. Les options suivantes sont disponibles :

- **Date de début du plan**
- **Date spécifique à l'employé** – Lorsque cette option est sélectionnée, la valeur détermine la source de la valeur de date initiale utilisée pour calculer les périodes de régularisation. Les options suivantes sont disponibles :

    - Personnalisée
    - Date anniversaire
    - Date d'embauche d'origine
    - Date d'ancienneté
    - Date de début ajustée du collaborateur
    - Date de début du collaborateur

### <a name="accrual-award-date"></a>Date de régularisation

La date de régularisation détermine le moment où des congés sont attribués à un employé. Les options suivantes sont disponibles :

- **Date de fin de la période de régularisation** – Des congés sont attribués à l'employé le dernier jour de la période de prime.

    Pour provisionner le montant correct, le processus de régularisation doit inclure toute la période. Par exemple, la période de régularisation est du 1er janvier 2018 au 31 janvier 2018. Dans ce cas, pour que janvier soit inclus, la régularisation doit être effectuée pour le 1er février 2018.

- **Date de début de la période de régularisation** – Des congés sont attribués à l'employé le premier jour de la période de prime.

### <a name="accrual-policy-on-enrollment"></a>Stratégie de régularisation à l'inscription

La stratégie de régularisation à l'inscription définit la manière dont la régularisation est calculée lorsqu'un employé est inscrit au milieu d'une période de régularisation. Les options suivantes sont disponibles :

- **Au prorata** – La plage de dates entre la date d'inscription et la date de début sert à déterminer la différence en jours. Cette différence est appliquée lorsque des régularisations sont traitées.
- **Régularisation complète** – Le montant total de régularisation, selon le niveau, est attribué au premier traitement de régularisation.
- **Aucune régularisation** – Aucune régularisation n'est attribuée jusqu'à la prochaine période de régularisation.

### <a name="accrual-policy-on-unenrollment"></a>Stratégie de régularisation à la désinscription

La stratégie de régularisation à la désinscription définit la manière dont la régularisation est calculée lorsqu'un employé est désinscrit au milieu d'une période de régularisation. Les options suivantes sont disponibles :

- **Au prorata** – La plage de dates entre la date d'inscription et la date de début sert à déterminer la différence en jours. Cette différence est appliquée lorsque des régularisations sont traitées.
- **Régularisation complète** – Le montant total de régularisation, selon le niveau, est attribué au premier traitement de régularisation.
- **Aucune régularisation** – Aucune régularisation n'est attribuée jusqu'à la prochaine période de régularisation.

## <a name="accrual-schedule"></a>Programme de régularisation

Le programme de régularisation détermine comment un employé provisionne des congés, et les montants que l'employé provisionnera et reportera. Des niveaux peuvent être créés afin que les congés soient attribués selon différents niveaux.

### <a name="months-of-service"></a>Mois de service

La valeur **Mois de service** définit le nombre de mois minimal que les employés doivent travailler pour avoir droit aux régularisations. Si aucune valeur minimale n'est requise pour les employés, définissez la valeur sur **0**.

### <a name="hours-worked"></a>Heures travaillées

La valeur **Heures travaillées** définit le nombre d'heures minimal que les employés doivent travailler par période de régularisation pour avoir droit aux régularisations. Si aucune valeur minimale n'est requise pour les employés, définissez la valeur sur **0**.

### <a name="accrual-amount"></a>Montant de régularisation

Le montant de régularisation est le nombre d'heures ou de jours que les employés provisionneront par période. La période est basée sur la fréquence de régularisation.

### <a name="minimum-balance"></a>Solde minimum

Une valeur négative peut être utilisée pour le solde minimal si les employés peuvent demander davantage de congés que ceux dont ils disposent.

### <a name="maximum-carry-forward"></a>Reports maximaux

Le processus de régularisation ajustera les soldes d'absence qui dépassent le solde de report maximal sur l'anniversaire de la date de début.

### <a name="grant-amount"></a>Montant accordé

Le montant accordé est le nombre d'heures ou de jours initial accordé aux employés lorsqu'ils s'inscrivent pour la première fois au plan de congé. Le montant ne provisionne pas pour chaque période de régularisation.

## <a name="enrollments-and-balances"></a>Inscriptions et soldes

### <a name="enrollment-date"></a>Date d'inscription

La date d'inscription détermine quand un employé peut commencer à provisionner des congés. Par exemple, si une employée est inscrite dans un plan de congés le 15 juin 2018, elle ne peut pas provisionner de congés avant le 15 juin 2018.

### <a name="current-balance"></a>Solde actuel

Le solde actuel est le montant de congés disponible pour les demandes de congés. Ce montant inclut des régularisations, des demandes approuvées et des ajustements à la date actuelle.

### <a name="current-balance-examples"></a>Exemples de soldes actuels

#### <a name="annual-plan"></a>Plan annuel

**Paramétrage du plan**

| Date de début du plan | Date d'inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Annuel            | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 1er janvier 2019 (1/1/2019), afin que cette période entière soit incluse.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Montant demandé | Solde actuel (au 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 200            | 0               | 120                   | 40             | 160                              |

Solde actuel (160) = Montant de régularisation (200) – Montant demandé (40)

#### <a name="semimonthly-plan"></a>Plan bimensuel

**Paramétrage du plan**

| Date de début du plan | Date d'inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensuel       | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 1er mai 2018 (5/1/2018), afin que cette période entière soit incluse.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Montant demandé | Solde actuel (au 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 22                               |

Solde actuel (22) = Montant de régularisation (5 × 6) – Montant demandé (8)

#### <a name="monthly-plan"></a>Plan mensuel

**Paramétrage du plan**

| Date de début du plan | Date d'inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensuel       | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 1er mai 2018 (5/1/2018), afin que cette période entière soit incluse.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Montant demandé | Solde actuel (au 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Solde actuel (7) = Montant de régularisation (5 × 3) – Montant demandé (8)

### <a name="forecasted-balance"></a>Solde prévu

Le *solde prévu* est le montant de congés disponible à une date ultérieure. Les régularisations et les ajustements de report sont prévus jusqu'à cette date.

La formule utilisée est la suivante :

Solde prévu lundi = Solde actuel – Demandes + Régularisations – Ajustement de report

### <a name="forecasted-balance-examples"></a>Exemples de soldes prévus

#### <a name="annual-plan"></a>Plan annuel

**Paramétrage du plan**

| Date de début du plan | Date d'inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Annuel            | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 15 février 2019 (15/2/2019), afin que cette période entière soit incluse.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Solde actuel | Solde prévu (au 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 20             | 0               | 20                    | 40              | 40                                   |

Solde prévu (40) = Montant de régularisations (20) + Solde actuel (40) – Ajustement de report (20)

#### <a name="semimonthly-plan"></a>Plan bimensuel

**Paramétrage du plan**

| Date de début du plan | Date d'inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensuel       | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 15 février 2019 (15/2/2019), afin que cette période entière soit incluse.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Solde actuel | Solde prévu (au 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 5              | 0               | 20                    | 40              | 35                                   |

Solde prévu (35) = Montant de régularisations (5 × 3) + Solde actuel (40) – Ajustement de report (20)

#### <a name="monthly-plan"></a>Plan mensuel

**Paramétrage du plan**

| Date de début du plan | Date d'inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensuel       | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 15 février 2019 (15/2/2019), afin que cette période entière soit incluse.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Solde actuel | Solde prévu (au 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 10             | 0               | 20                    | 40              | 30                                   |

Solde prévu (30) = Montant de régularisations (10 × 1) + Solde actuel (40) – Ajustement de report (20)

### <a name="proration-balance-examples"></a>Exemples de soldes de calculs au prorata

#### <a name="prorated-monthly-plan"></a>Plan mensuel calculé au prorata

**Paramétrage du plan**

| Date de début du plan | Fréquence de régularisation | Base de la période de régularisation |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensuel           | Date de début du plan      |

**Résultats**

| Employé            | Mois de service | Date d'inscription | Date de début | Montant de régularisation | Régularisation de traitement | Bilan |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 2.53    |

#### <a name="full-accrual-monthly-plan"></a>Plan mensuel de régularisation complet

**Paramétrage du plan**

| Date de début du plan | Fréquence de régularisation | Base de la période de régularisation |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensuel           | Date de début du plan      |

**Résultats**

| Employé            | Mois de service | Date d'inscription | Date de début | Montant de régularisation | Régularisation de traitement | Bilan |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 3,00    |

#### <a name="no-accrual-monthly-plan"></a>Aucun plan mensuel de régularisation

**Paramétrage du plan**

| Date de début du plan | Fréquence de régularisation | Base de la période de régularisation |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensuel           | Date de début du plan      |

**Résultats**

| Employé            | Mois de service | Date d'inscription | Date de début | Montant de régularisation | Régularisation de traitement | Bilan |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 2.00    |
