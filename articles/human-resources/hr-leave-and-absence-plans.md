---
title: Création d’un plan de congé et d’absence
description: Créez des plans de congé dans Dynamics 365 Human Resources pour différents types de congés.
author: andreabichsel
manager: AnnBe
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb42860292c5e3e654917cf2f62b525993aa795a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418553"
---
# <a name="create-a-leave-and-absence-plan"></a>Création d’un plan de congé et d’absence

Définissez les plans de congé et d’absence dans Dynamics 365 Human Resources pour chaque type de congé que vous offrez. Les plans de congé et d’absence peuvent se provisionner à différentes fréquences, notamment annuellement, mensuellement ou semestriellement. Vous pouvez également définir un plan comme subvention, où une seule régularisation se produit à une date spécifique. Par exemple, vous pouvez créer un plan qui accorde des congés flottants chaque année.

Les plans de congés échelonnés permettent aux employés de recevoir des avantages en fonction du temps qu’ils ont passé au sein d’une organisation. Les plans échelonnés permettent l’inscription automatique à des heures d’avantage supplémentaires.

Vous pouvez spécifier des montants de report maximum ou des soldes minimums pour vous assurer que les employés n’utilisent que les heures d’avantage qu’ils ont cumulées.

Par exemple, avec un plan échelonné, vous pouvez accorder un avantage de 80 heures de congés payés aux nouveaux employés. Ensuite, vous pouvez accorder 120 heures pour 60 mois de service.

Vous pouvez également créer des avantages liés de congés basés sur le poste, tels que les heures d’avantage réservées aux cadres.

## <a name="create-a-leave-plan"></a>Création d’un plan de congé

1. Dans la page **Plans de congé et d’absence**, sélectionnez **Créer un plan**.

2. Sous **Détails**, entrez le **Nom**, la **Date de début**, la **Description** et le **Type de congé** pour votre plan.

Si la fonction **Configurer plusieurs types de congés pour un seul plan de congés et d’absences** est activée, les types de congés sont configurés dans le **Programme de régularisation** plutôt que sous **Détails**. Pour chaque enregistrement dans le tableau du programme de régularisation, vous pouvez définir un type de congé. De plus, lorsque cette fonctionnalité est activée, vous devrez utiliser de nouvelles entités de données pour les intégrations ou d’autres scénarios dans lesquels vous devez utiliser des entités. 

Les nouvelles entités sont :

- Transaction bancaire de congé et d’absence V2
- Inscription de congé et d’absence V2
- Niveau de plan de congé et d’absence V2
- Plan de congé et d’absence V2
- Demande de congés V2

 > [!IMPORTANT]
   > Après avoir activé cette fonctionnalité, il est impossible de la désactiver.

3. Définissez les régularisations dans l’onglet **Régularisations**. Les régularisations déterminent quand et à quelle fréquence un employé bénéficie d’un congé. Au cours de cette étape, vous définissez des politiques sur le moment où les régularisations doivent être attribuées ainsi que sur la répartition proportionnelle des avantages de congés.

   1. Sélectionnez une valeur dans la liste déroulante **Fréquence de régularisation** :

      - Quotidiennement
      - Hebdomadairement
      - Bihebdomadaire
      - Bimensuel
      - Mensuellement
      - Trimestriel
      - Semestriel
      - Année
      - Aucune

   2. Sélectionnez une option dans la liste déroulante **Base de la période de régularisation** pour déterminer la date de début utilisée pour le calcul des périodes de régularisation :

      | Base de la période de régularisation | Description |
      | --- | --- |
      | **Date de début du plan** | La date de début de la période de régularisation est la date à laquelle le plan est disponible. |
      | **Date spécifique à l’employé** | La date de début de la période de régularisation dépend de l’événement d’un employé :</br><ul><li>Personnalisé (vous devez spécifier une base de date de régularisation pour chaque inscription individuelle)</li><li>Date anniversaire</li><li>Date d’embauche d’origine</li><li>Date d’ancienneté</li><li>Date de début ajustée du collaborateur</li><li>Date de début du collaborateur</li></ul> |

   3. Sélectionnez une option dans la liste déroulante **Date de régularisation** :

      - **Date de fin de la période de régularisation** – Des congés sont attribués à l’employé le dernier jour de la période d’application. Pour provisionner le montant correct, le processus de régularisation doit inclure toute la période. Par exemple, si la période de régularisation s’étend du 1er janvier 2020 au 31 janvier 2020, vous devez exécuter la régularisation pour le 1er février 2020 pour inclure janvier.

      - **Date de début de la période de régularisation** – Des congés sont attribués à l’employé le premier jour de la période d’application.

   4. Sélectionnez une option dans la liste déroulante **Stratégie de régularisation à l’inscription** : Cette valeur définit comment calculer la régularisation lorsqu’un employé s’inscrit au milieu d’une période de régularisation.

      - **Au prorata** – La plage de dates entre la date d’inscription et la date de début sert à déterminer la différence en jours. Cette différence est appliquée lorsque des régularisations sont traitées.

      - **Régularisation complète** – Le montant total de régularisation, selon le niveau, est attribué au premier traitement de régularisation.

      - **Aucune régularisation** – Aucune régularisation n’est attribuée jusqu’à la prochaine période de régularisation.

   5. Sélectionnez une option dans la liste déroulante **Stratégie de régularisation à la désinscription** : Cette valeur définit comment calculer la régularisation lorsqu’un employé se désinscrit au milieu d’une période de régularisation.

      - **Au prorata** – La plage de dates entre la date d’inscription et la date de début sert à déterminer la différence en jours. Cette différence est appliquée lorsque des régularisations sont traitées.

      - **Régularisation complète** – Le montant total de régularisation, selon le niveau, est attribué au premier traitement de régularisation.

      - **Aucune régularisation** – Aucune régularisation n’est attribuée jusqu’à la prochaine période de régularisation.

4. Définissez le programme de régularisation dans l’onglet **Programme de régularisation =**. Le programme de régularisation détermine :

   - Comment un employé provisionne des congés
   - Le nombre de jours que l’employé provisionne
   - Le nombre de jours qui sera reporté

   Vous pouvez créer des niveaux pour attribuer des congés selon différents niveaux.

   Si vous avez des employés rémunérés à l’heure, vous pouvez accorder des congés sur la base des heures travaillées au lieu de l’ancienneté dans votre organisation. Les données sur les heures travaillées sont généralement stockées dans un système de pointage. Vous pouvez importer des heures normales et des heures supplémentaires travaillées à partir du système de gestion des heures et des présences et les utiliser comme base pour l’attribution d’une prime à un employé.
   
    1. Sélectionnez une option dans la liste déroulante **Type de régularisation** :

      - **Mois de service** - Basez le calendrier de régularisation sur les mois de service.

      - **Heures travaillées** - Basez le calendrier de régularisation sur les heures travaillées. Pour plus d’informations sur les régularisations des heures travaillées, voir [Accorder des congés sur la base des heures travaillées](hr-leave-and-absence-plans.md?accrue-time-off-based-on-hours-worked).

      Pour plus d’informations sur les régularisations des avantages, voir [Accorder des congés sur la base des heures travaillées](hr-leave-and-absence-plans.md?enrollments-and-balances).

    2. Entrez des valeurs dans le tableau du programme de régularisation :

      - **Mois de service** - Nombre de mois minimal que les employés doivent travailler pour avoir droit aux régularisations. Si vous n’avez pas besoin d’un minimum, définissez la valeur sur 0.

      - **Heures travaillées** - Nombre d’heures minimal que les employés doivent travailler par période de régularisation pour avoir droit aux régularisations. Si vous n’avez pas besoin d’un minimum, définissez la valeur sur 0.

      - **Montant de régularisation** - Nombre d’heures ou de jours que les employés provisionneront par période. La période est basée sur la fréquence de régularisation.

      - **Solde minimum** - Vous pouvez utiliser une valeur négative pour le solde minimal si les employés peuvent demander davantage de congés que ceux dont ils disposent.

      - **Reports maximaux** - Le processus de régularisation ajuste les soldes d’absence qui dépassent le solde de report maximal sur l’anniversaire de la date de début.

      - **Montant accordé** - Nombre d’heures ou de jours initial accordé aux employés lorsqu’ils s’inscrivent pour la première fois au plan de congé. Le montant ne provisionne pas pour chaque période de régularisation.
      
Si la fonction **Configurer plusieurs types de congé pour un seul plan de congé et d’absence** est activée, sélectionnez une option depuis **Type de congé**. 

   > [!IMPORTANT]
   > Après avoir activé cette fonctionnalité, il est impossible de la désactiver.

Si la fonction **Utiliser l’équivalence temps plein** est activée, Human Resources utilise l’équivalence temps plein (ETP) définie pour le poste afin de répartir au prorata la régularisation d’un employé. Par exemple, si l’ETP est de 0,5 et que le montant de la régularisation est de 10, l’employé régularisera 5. Vous ne pouvez utiliser cette fonction que si vous activez plusieurs types de congés.  

5. Sélectionnez **Enregistrer**.

## <a name="accrue-time-off-based-on-hours-worked"></a>Cumuler des congés sur la base des heures travaillées

Si vous avez des employés rémunérés à l’heure, vous pouvez accorder des congés sur la base des heures travaillées au lieu de l’ancienneté dans votre organisation. Les données sur les heures travaillées sont généralement stockées dans un système de pointage. Vous pouvez importer des heures normales et des heures supplémentaires travaillées à partir de votre système de gestion des heures et des présences et les utiliser comme base pour l’attribution d’une prime à un employé.

Lorsque vous sélectionnez les heures travaillées comme type de régularisation, vous pouvez utiliser deux types d’heures pour la régularisation : heures normales et supplémentaires. Le processus de régularisation pour les plans d’heures travaillées utilise la fréquence de régularisation, ainsi que la base de la période de régularisation, pour déterminer les heures à régulariser.

### <a name="annual-accrual-frequency"></a>Fréquence de régularisation annuelle

| Date de régularisation    | Niveau d’heures travaillées    | Montant de régularisation        | Dates des heures travaillées   | Heures réelles travaillées| Prime               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 31/12/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2085                | 144                 |        
| 31/12/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2 000                | 0                 |


### <a name="monthly-accrual-frequency"></a>Fréquence de régularisation mensuelle

| Date de régularisation    | Niveau d’heures travaillées    | Montant de régularisation        | Dates des heures travaillées   | Heures réelles travaillées| Prime               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 31/8/2018             | 160                  | 12                    | 1/8/2018-31/8/2018   | 184                 | 12                  |        
| 31/8/2018             | 160                  | 3                     | 1/8/2018-31/8/2018   | 184                 | 3                   |

### <a name="semi-monthly-accrual-frequency"></a>Fréquence de régularisation bimensuelle

| Date de régularisation    | Niveau d’heures travaillées    | Montant de régularisation        | Dates des heures travaillées   | Heures réelles travaillées| Prime               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 31/8/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 81                  | 6                  |        
| 31/8/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 75                  | 0                   |

### <a name="weekly-accrual-frequency"></a>Fréquence de régularisation hebdomadaire

| Date de régularisation    | Niveau d’heures travaillées    | Montant de régularisation        | Dates des heures travaillées   | Heures réelles travaillées| Prime               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 31/8/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 42                  | 3                  |        
| 31/8/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 35                  | 0                   |

### <a name="employee-assigned-leave-plans"></a>Plans de congés affectés à l’employé

Dans les plans de congés de l’employé, la base de niveau et le type d’heures s’affichent pour les plans d’heures travaillées. Le nombre réel d’heures travaillées pour les périodes de régularisation à la date actuelle s’affichent également pour les plans actifs.

### <a name="loading-data"></a>Chargement de données

Vous pouvez importer les heures réelles à l’aide de l’entité **Heures de congé et d’absence travaillées** dans la gestion des données. Si vous utilisez des calendriers de temps de travail, l’importation valide que les heures normales travaillées ne dépassent pas les heures planifiées dans un jour défini par le calendrier. L’importation valide également que les heures travaillées pour un jour donné ne dépassent pas 24 heures. 

Vous avez besoin des informations suivantes pour importer les heures réelles à utiliser dans le processus de régularisation des congés :

- Numéro personnel 
- Date travaillée
- Type
- Heures

Un seul type peut être associé à une date.

| Numéro personnel       | Date travaillée           | Type                  | Heures                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 6/8/2018             | Régulier               | 8                    |       
| 000337                | 7/8/2018             | Régulier               | 8                    |
| 000337                | 7/8/2018             | Heures supplémentaires              | 3                    |
| 000337                | 8/8/2018             | Régulier               | 8                    |
| 000337                | 7/8/2018             | Régulier               | 8                    |
| 000337                | 9/8/2018             | Régulier               | 8                    |

## <a name="enrollments-and-balances"></a>Inscriptions et soldes

### <a name="enrollment-date"></a>Date d’inscription

La date d’inscription détermine quand un employé peut commencer à provisionner des congés. Par exemple, une employée est inscrite dans un plan de congés le 15 juin 2018, 2018 ne peut pas provisionner de congés avant le 15 juin 2018.

### <a name="current-balance"></a>Solde actuel

Le solde actuel est le montant de congés disponible pour les demandes de congés. Ce montant inclut des régularisations, des demandes approuvées et des ajustements à la date actuelle.

### <a name="current-balance-examples"></a>Exemples de soldes actuels

#### <a name="annual-plan"></a>Plan annuel

**Paramétrage du plan**

| Date de début du plan | Date d’inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Annuel            | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 1er janvier 2019 (1/1/2019) afin d’inclure toute la période.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Montant demandé | Solde actuel (au 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 200            | 0               | 120                   | 40             | 160                              |

Solde actuel (160) = Montant de régularisation (200) – Montant demandé (40)

#### <a name="semimonthly-plan"></a>Plan bimensuel

**Paramétrage du plan**

| Date de début du plan | Date d’inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensuel       | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 1er mai 2018 (1/5/2018) afin d’inclure toute la période.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Montant demandé | Solde actuel (au 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 22                               |

Solde actuel (22) = Montant de régularisation (5 × 6) – Montant demandé (8)

#### <a name="monthly-plan"></a>Plan mensuel

**Paramétrage du plan**

| Date de début du plan | Date d’inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensuel       | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 1er mai 2018 (1/5/2018) afin d’inclure toute la période.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Montant demandé | Solde actuel (au 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Solde actuel (7) = Montant de régularisation (5 × 3) – Montant demandé (8)

### <a name="forecasted-balance"></a>Solde prévu

Le *solde prévu* est le montant de congés disponible à une date ultérieure. Les régularisations et les ajustements de report sont prévus jusqu’à cette date.

Human Resources utilise la formule suivante :

Solde prévu lundi = Solde actuel – Demandes + Régularisations – Ajustement de report

### <a name="forecasted-balance-examples"></a>Exemples de soldes prévus

#### <a name="annual-plan"></a>Plan annuel

**Paramétrage du plan**

| Date de début du plan | Date d’inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Annuel            | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 15 février 2019 (15/2/2019) afin d’inclure toute la période.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Solde actuel | Solde prévu (au 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 20             | 0               | 20                    | 40              | 40                                   |

Solde prévu (40) = Montant de régularisations (20) + Solde actuel (40) – Ajustement de report (20)

#### <a name="semimonthly-plan"></a>Plan bimensuel

**Paramétrage du plan**

| Date de début du plan | Date d’inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensuel       | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 15 février 2019 (15/2/2019) afin d’inclure toute la période.

**Résultats**

| Montant de régularisation | Solde minimum | Reports maximaux | Solde actuel | Solde prévu (au 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 5              | 0               | 20                    | 40              | 35                                   |

Solde prévu (35) = Montant de régularisations (5 × 3) + Solde actuel (40) – Ajustement de report (20)

#### <a name="monthly-plan"></a>Plan mensuel

**Paramétrage du plan**

| Date de début du plan | Date d’inscription | Fréquence de régularisation | Base de la période de régularisation | Date de régularisation    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensuel       | Date de début du plan      | Fin de la période de régularisation |

Les régularisations sont traitées le 15 février 2019 (15/2/2019) afin d’inclure toute la période.

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

| Employé            | Mois de service | Date d’inscription | Date de début | Montant de régularisation | Régularisation de traitement | Bilan |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 2.53    |

#### <a name="full-accrual-monthly-plan"></a>Plan mensuel de régularisation complet

**Paramétrage du plan**

| Date de début du plan | Fréquence de régularisation | Base de la période de régularisation |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensuel           | Date de début du plan      |

**Résultats**

| Employé            | Mois de service | Date d’inscription | Date de début | Montant de régularisation | Régularisation de traitement | Bilan |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 3,00    |

#### <a name="no-accrual-monthly-plan"></a>Aucun plan mensuel de régularisation

**Paramétrage du plan**

| Date de début du plan | Fréquence de régularisation | Base de la période de régularisation |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensuel           | Date de début du plan      |

**Résultats**

| Employé            | Mois de service | Date d’inscription | Date de début | Montant de régularisation | Régularisation de traitement | Bilan |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3.00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1.00           | 9/1/2018        | 2.00    |

## <a name="see-also"></a>Voir également :

- [Vue d’ensemble des congés et des absences](hr-leave-and-absence-overview.md)
- [Configurer les types de congé et d’absence](hr-leave-and-absence-types.md)
- [Provisionner les plans de congé et d’absence](hr-leave-and-absence-accrue.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]