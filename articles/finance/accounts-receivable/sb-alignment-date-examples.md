---
title: Scénarios de date d’alignement
description: Cet article fournit des exemples qui montrent le fonctionnement des dates d’alignement dans la facturation de l’abonnement.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 102e3a104be5be287f914172160e95aff65d0b18
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872613"
---
# <a name="alignment-date-scenarios"></a>Scénarios de date d’alignement

Cet article fournit des exemples qui montrent le fonctionnement des dates d’alignement dans la facturation de l’abonnement.

Pour ces exemples, un détail de facturation pour un échéancier de facturation a une date d’alignement au 31 octobre 2019. Le premier détail de facturation de la ligne se termine le 31 octobre 2019 et est calculé au prorata en conséquence. La ligne est automatiquement renouvelée en utilisant une date de début de renouvellement du 11 novembre.

> [!NOTE]
> L’année est pertinente car elle peut faire en sorte que la date d’alignement soit supérieure ou inférieure à un an. Pour ces exemples, la méthode de calcul du prorata est définie **Mensuel** sur la page **Paramètres de facturation des contrats récurrents**. Sil elle est réglé sur **Quotidien**, certains montants partiels seront différents.

## <a name="scenario-1-no-alignment"></a>Scénario 1 : Pas d’alignement

L’échéancier de facturation est configuré avec les données suivantes :

- **Date de début :** 1er mai 2019
- **Date de fin :** 31 décembre 2024
- **Montant :** 1 000 $

| Date de début de facturation | Date de fin de facturation | Lecture précédente | Lecture actuelle | Quantité entrée | Quantité gratuite | Quantité facturable | Prix unitaire |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 30/04/2020 | | | 1.00 | | 1.00 | 1,000.00 |
| 01/05/2020 | 30/04/2021 | | | 1.00 | | 1.00 | 1,000.00 |
| 05/01/2021 | 30/04/2022 | | | 1.00 | | 1.00 | 1,000.00 |
| 05/01/2022 | 30/04/2023 | | | 1.00 | | 1.00 | 1,000.00 |
| 05/01/2023 | 30/04/2024 | | | 1.00 | | 1.00 | 1,000.00 |
| 05/01/2024 | 31/12/2024 | | | 1.00 | | 1.00 | 666.67 |

## <a name="scenario-2-shortened-alignment"></a>Scénario 2 : Alignement raccourci

L’échéancier de facturation est configuré avec les données suivantes :

- **Date de début :** 1er mai 2019
- **Date de fin :** 31 décembre 2024
- **Montant :** 1 000 $
- **Date d’alignement :** 31 décembre 2019

Le premier montant de renouvellement est pour moins d’un an.

| Date de début de facturation | Date de fin de facturation | Lecture précédente | Lecture actuelle | Quantité entrée | Quantité gratuite | Quantité facturable | Prix unitaire |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 31/12/2019 | | | 1.00 | | 1.00 | 666.67 |
| 1/1/2020 | 31/12/2020 | | | 1.00 | | 1.00 | 1,000.00 |
| 01/01/2021 | 31/12/2021 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2022 | 31/12/2022 | | | 1.00 | | 1.00 | 1,000.00 |
| 01/01/2023 | 31/12/2023 | | | 1.00 | | 1.00 | 1,000.00 |
| 01/01/2024 | 31/12/2024 | | | 1.00 | | 1.00 | 1,000.00 |

## <a name="scenario-3-extended-alignment"></a>Scénario 3 : Alignement étendu

L’échéancier de facturation est configuré avec les données suivantes :

- **Date de début :** 1er mai 2019
- **Date de fin :** 31 décembre 2024
- **Montant :** 1 000 $
- **Date d’alignement :** 31 décembre 2020

Le premier montant de renouvellement est pour plus d’un an.

| Date de début de facturation | Date de fin de facturation | Lecture précédente | Lecture actuelle | Quantité entrée | Quantité gratuite | Quantité facturable | Prix unitaire |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 31/12/2020 | | | 1.00 | | 1.00 | 1,666.67 |
| 01/01/2021 | 31/12/2021 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2022 | 31/12/2022 | | | 1.00 | | 1.00 | 1,000.00 |
| 01/01/2023 | 31/12/2023 | | | 1.00 | | 1.00 | 1,000.00 |
| 01/01/2024 | 31/12/2024 | | | 1.00 | | 1.00 | 1,000.00 |

## <a name="scenario-4-alignment-with-a-different-end-month"></a>Scénario 4 : Alignement avec un mois de fin différent

L’échéancier de facturation est configuré avec les données suivantes :

- **Date de début :** 1er mai 2019
- **Date de fin :** 31 octobre 2024
- **Montant :** 1 000 $
- **Date d’alignement :** 31 décembre 2019

> [!NOTE]
> Ce scénario n’est pas commun.

| Date de début de facturation | Date de fin de facturation | Lecture précédente | Lecture actuelle | Quantité entrée | Quantité gratuite | Quantité facturable | Prix unitaire |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 31/12/2019 | | | 1.00 | | 1.00 | 666.67 |
| 1/1/2020 | 31/12/2020 | | | 1.00 | | 1.00 | 1,000.00 |
| 01/01/2021 | 31/12/2021 | | | 1.00 | | 1.00 | 1,000.00 |
| 1/1/2022 | 31/12/2022 | | | 1.00 | | 1.00 | 1,000.00 |
| 01/01/2023 | 31/12/2023 | | | 1.00 | | 1.00 | 1,000.00 |
| 01/01/2024 | 31/10/2024 | | | 1.00 | | 1.00 | 833.33 |

## <a name="scenario-5-single-partial-year"></a>Scénario 5 : Année partielle unique

L’échéancier de facturation est configuré avec les données suivantes :

- **Date de début :** 1er mai 2019
- **Date de fin :** 31 décembre 2019
- **Montant :** 1 000 $
- **Date d’alignement** : 31 décembre 2019

Dans ce scénario, la date d’alignement n’est pas nécessaire. Ce scénario est courant pour les renouvellements automatiques.

| Date de début de facturation | Date de fin de facturation | Lecture précédente | Lecture actuelle | Quantité entrée | Quantité gratuite | Quantité facturable | Prix unitaire |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 31/12/2019 | | | 1.00 | | 1.00 | 666.67 |

## <a name="scenario-6-calculated-dates"></a>Scénario 6 : Dates calculées

Le support et le renouvellement sont configuré avec les données suivantes :

- **Remplacer la date de début :** Non
- **Dates de début du support et du renouvellement :** Début du mois prochain
- **Date de validation de facture :** 22 juin 2019
- **Date d’alignement :** 31 décembre 2020

| Date de début de facturation | Date de fin de facturation | Lecture précédente | Lecture actuelle | Quantité entrée | Quantité gratuite | Quantité facturable | Prix unitaire |
|---|---|---|---|---|---|---|---|
| 01/07/2019 | 31/07/2019 | | | 1.00 | | 1.00 | 297.60 |
| 01/08/2019 | 31/12/2020 | | | 1.00 | | 1.00 | 6,936.00 |

## <a name="scenario-7-calculated-dates-and-future-posting"></a>Scénario 7 : Dates calculées et validation futur

Le support et le renouvellement sont configuré avec les données suivantes :

- **Remplacer la date de début :** Non
- **Dates de début du support et du renouvellement :** Début du mois prochain
- **Date de validation de facture :** 22 juin 2019
- **Date d’alignement :** 31 décembre 2020

Pour ce scénario, la date d’alignement est modifiée au 31 décembre 2021.

| Date de début de facturation | Date de fin de facturation | Lecture précédente | Lecture actuelle | Quantité entrée | Quantité gratuite | Quantité facturable | Prix unitaire |
|---|---|---|---|---|---|---|---|
| 22/06/2019 | 22/06/2019 | | | 1.00 | | 1.00 | 0,00 |
| 01/08/2019 | 31/12/2020 | | | 1.00 | | 1.00 | 4,250.00 |

## <a name="scenario-8-manual-dates-and-multiple-years"></a>Scénario 8 : Dates manuelles et plusieurs années

Le support et le renouvellement sont configuré avec les données suivantes :

- **Remplacer la date de début :** Oui
- **Date de début du renouvellement :** 1er juillet 2020
- **Date de fin du renouvellement :** 31 décembre 2024
- **Date d’alignement :** 31 décembre 2021

| Date de début de facturation | Date de fin de facturation | Lecture précédente | Lecture actuelle | Quantité entrée | Quantité gratuite | Quantité facturable | Prix unitaire |
|---|---|---|---|---|---|---|---|
| 22/06/2019 | 22/06/2019 | | | 1.00 | | 1.00 | 0,00 |
| 01/07/2020 | 31/12/2021 | | | 1.00 | | 1.00 | 375.00 |
| 1/1/2022 | 31/12/2022 | | | 1.00 | | 1.00 | 250,00 |
| 01/01/2023 | 31/12/2023 | | | 1.00 | | 1.00 | 250,00 |
| 01/01/2024 | 31/12/2024 | | | 1.00 | | 1.00 | 250,00 |

## <a name="scenario-9-manual-dates-multiple-years-and-a-different-end-month"></a>Scénario 9 : Dates manuelles, plusieurs années et un mois de fin différent

Le support et le renouvellement sont configuré avec les données suivantes :

- **Remplacer la date de début :** Oui
- **Date de début du renouvellement :** 1er juillet 2020
- **Date de fin du renouvellement :** 31 octobre 2024
- **Date d’alignement :** 31 décembre 2021

| Date de début de facturation | Date de fin de facturation | Lecture précédente | Lecture actuelle | Quantité entrée | Quantité gratuite | Quantité facturable | Prix unitaire |
|---|---|---|---|---|---|---|---|
| 22/06/2019 | 22/06/2019 | | | 1.00 | | 1.00 | 0,00 |
| 01/07/2020 | 31/12/2021 | | | 1.00 | | 1.00 | 375.00 |
| 1/1/2022 | 31/12/2022 | | | 1.00 | | 1.00 | 250,00 |
| 01/01/2023 | 31/12/2023 | | | 1.00 | | 1.00 | 250,00 |
| 01/01/2024 | 31/10/2024 | | | 1.00 | | 1.00 | 208.33 |

## <a name="scenario-10-alignment-without-proration"></a>Scénario 10 : Alignement sans prorata

Le support et le renouvellement sont configuré avec les données suivantes :

- **Remplacer la date de début :** Non
- **Date de validation de facture :** 22 juin 2019
- **Date d’alignement :** 31 décembre 2019

La date de début du renouvellement et les dates d’alignement sont ajustées de sorte que les deux dates de début soient postérieures à la date de publication.

- **Date de début du renouvellement :** 1er janvier 2020
- **Date de fin du renouvellement :** 31 décembre 2020
