---
title: États financiers de balance comptable
description: Cet article décrit les états par défaut des balances comptables. Il décrit également les blocs élémentaires associés à ces états et comment il est possible de modifier ces états pour les adapter à vos exigences métier.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b48510febf5a5f9f4a01728b242d9750b3c62c2
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771726"
---
# <a name="trial-balance-financial-reports"></a>États financiers de balance comptable

[!include [banner](../includes/banner.md)]

Cet article décrit les états par défaut des balances comptables. Il décrit également les blocs élémentaires associés à ces états et comment il est possible de modifier ces états pour les adapter à vos exigences métier. 

<a name="default-trial-balance-reports"></a>États de la balance comptable par défaut
-----------------------------

Trois états de balance comptable sont disponibles dans les états financiers.

| Rapport par défaut                                 | Fonction                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Balance comptable détaillée – Par défaut               | Fournit les informations de solde pour tous les comptes, et comprend les soldes de débit et de crédit, et le net de ces soldes, avec la date de la transaction, le N° document et la description de journal.                  |
| Synthèse de balance comptable– Par défaut                | Fournit les informations du solde pour tous les comptes et comprend les soldes d'ouverture et de clôture, et les soldes de débit et de crédit avec leur différence nette.                                        |
| Synthèse de balance comptable d'une année à l'autre – Par défaut | Fournit les informations du solde pour tous les comptes, et comprend des soldes d'ouverture et de clôture, et les soldes de débit et de crédit avec leur différence nette pour l'année en cours et l'année passée. |

## <a name="building-blocks"></a>Éléments constitutifs
Les états financiers de balance comptable utilisent les éléments constitutifs suivants.

| État par défaut                                 | Définition de ligne          | Définition de colonne                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| Balance comptable détaillée – Par défaut               | Balance comptable - Par défaut | Balance comptable détaillée – Par défaut               |
| Synthèse de balance comptable– Par défaut                | Balance comptable - Par défaut | Synthèse de balance comptable - Par défaut                |
| Synthèse de balance comptable d'une année à l'autre – Par défaut | Balance comptable - Par défaut | Synthèse de balance comptable d'une année à l'autre - Par défaut |

### <a name="row-definition"></a>Définition de ligne

La définition de ligne, balance comptable – Par défaut, contient une seule ligne qui rassemble tous les comptes principaux. Par conséquent, n'importe qui peut générer le rapport sans avoir à apporter de modifications. Lorsque vous affichez l'état, vous explorez la ligne unique pour afficher les détails de chaque compte. Vous pouvez modifier la définition de ligne afin qu'elle comprenne plus de détails. Pour modifier la définition de ligne Balance comptable - Par défaut afin qu'elle inclue les lignes pour tous les comptes, procédez comme suit.

1.  Cliquez sur **Modifier**, puis sur **Insérer des lignes à partir des dimensions**. La commande **Insérer des lignes à partir des dimensions** permet de sélectionner les dimensions que vous voulez avoir dans votre définition de ligne. Pour cette définition de ligne, vous allez utiliser **Compte principal**.
2.  Vérifiez que **Compte principal** contient toutes les esperluettes (&) et cliquez sur **OK**.

La définition de ligne contient désormais tous les comptes principaux pour votre entité juridique par défaut.

### <a name="column-definition"></a>Définition de colonne

Chaque état de balance comptable utilise une définition de colonne différente. Ces définitions de colonne contiennent différents types de colonnes afin d'offrir différents niveaux de détails et de données financières.

-   **Balance comptable détaillée – Types de colonne par défaut :**
    -   **DESC** : Description de la définition de ligne.
    -   **ACCT** : Codes compte
    -   **ATTR (3)** : Attributs :
        -   Date de transaction
        -   N° document
        -   Description du journal
    -   **FD** : Données financières qui contiennent uniquement des débits
    -   **FD** : Données financières qui contiennent uniquement des crédits
    -   **CALC** : Différence nette
-   **Synthèse de balance comptable – Types de colonne par défaut :**
    -   **ACCT** : Codes compte
    -   **DESC** : Description de la définition de ligne.
    -   **ATTR** : Attribut :
        -   N° document
    -   **FD** : Données financières de solde d'ouverture
    -   **FD** : Données financières qui contiennent uniquement des débits
    -   **FD** : Données financières qui contiennent uniquement des crédits
    -   **CALC** : Différence nette
    -   **CALC** : Solde de clôture
-   **Synthèse de balance comptable d'une année à l'autre - Par défaut :**
    -   **ACCT** : Codes compte
    -   **DESC** : Description de la définition de ligne.
    -   **ATTR** : Attribut
        -   N° document
    -   **FD** – Données financières de solde d'ouverture pour l'année actuelle
    -   **FD** : Données financières qui contiennent uniquement des débits pour l'année en cours
    -   **FD** : Données financières qui contiennent uniquement des crédits pour l'année en cours
    -   **CALC** : Différence nette
    -   **CALC** : Solde de clôture
    -   **FD** : Données financières qui contiennent uniquement des débits pour l'année dernière
    -   **FD** : Données financières qui contiennent uniquement des crédits pour l'année dernière



<a name="additional-resources"></a>Ressources supplémentaires
--------

[Vue d'ensemble des états financiers](financial-reporting-getting-started.md)

[Afficher les états financiers](view-financial-reports.md)

[États financiers Dynamics (blog)](https://blogs.msdn.com/b/dynamics_financial_reporting/)



