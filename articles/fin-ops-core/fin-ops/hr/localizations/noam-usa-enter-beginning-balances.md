---
title: Saisir des soldes d’ouverture de salaire
description: L’article décrit les étapes pour entrer des soldes d’ouverture pour les codes de rémunération, les déductions, les avantages et les taxes.
author: andreabichsel
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d14e7e0772c5b365818d3a8a230abe9f674a077e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850016"
---
# <a name="enter-payroll-beginning-balances"></a>Saisir des soldes d’ouverture de salaire

[!include [banner](../../includes/banner.md)]

L’article décrit les étapes pour entrer des soldes d’ouverture pour les codes de rémunération, les déductions, les avantages et les taxes. Ces informations sont précieuses pour les partenaires qui transfèrent des données pour une nouvelle implémentation du salaire à partir d’un autre système. Pour commencer à entrer les soldes d’ouverture de salaires, nous vérifions les informations suivantes :

- Les enregistrements employé sont entrés et disponibles dans le système
- Les données suivantes sont configurées et attribuées aux employés :

    - Cycles de paie et périodes de rémunération
    - Codes de rémunérations
    - Taxes
    - Avantages et déductions

- La société doit avoir sélectionné une date à laquelle les soldes d’ouverture de salaire peuvent être définies.
- Les informations recueillies ont été collectées à partir de tous les bénéfices, avantages/déductions, contributions pour les avantages, cotisations de l’employé et cotisations de l’employeur, ainsi que de leurs montants de cumul annuel issus du système hérité.

Comme vous envisagez d’entrer des soldes d’ouverture, déterminez le contenu des données. La plupart des entreprises entre un seul montant consolidé de l’année en cours. Cependant si des informations plus détaillées sont nécessaires, les soldes peuvent être entrés en incréments trimestriels. Déterminer le niveau de détail qui est nécessaire indique le nombre de bordereaux de paie manuels devant être créés pour chaque collaborateur. Pour un seul montant de l’année en cours, un seul relevé manuel est nécessaire pour chaque employé. Pour ce faire, utilisez les montants cumulés depuis le bordereau de paie final issu du système précédent lorsque vous saisissez le montant dans le nouveau système de paie.

L’exemple suivant montre comment vous pouvez entrer des soldes d’ouverture de salaire d’un employé, notamment les codes de rémunération, les avantages/déductions et les taxes. Dans un cas réel, vous auriez une ligne pour chaque code de rémunération, déduction d’avantage, contribution pour les avantages, cotisation de l’employé et cotisation de l’employeur avec le montant saisi correspondant au montant de l’année en cours. Grâce à cette liste de codes et de montants, suivez les étapes pour créer une rémunération et un bordereau de paie manuellement avec la fonction de comptabilité désactivée pour indiquer les soldes d’ouverture à des fins de salaire. Désactivez la comptabilité car vous ne souhaitez pas valider ce bordereau de paie de solde d’ouverture dans votre comptabilité. Cela a été effectué dans le système hérité et passera dans le nouveau système lorsque vous définirez les soldes d’ouverture dans votre comptabilité.

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a>A. Procédure de paramétrage des codes non répartis à utiliser dans les soldes d’ouverture de salaire

Lorsque vous entrez des soldes d’ouverture de salaire, assurez-vous que les codes de rémunération que vous utiliserez sont configurés avec l’option « Autoriser la modification des taux de relevés de rémunération » activée. Cela vous permet d’entrer manuellement le montant du système hérité. 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a>B. Créer l’état des revenus pour qu’un employé ait un solde d’ouverture

Cette étape permet de créer manuellement un état des revenus pour chaque collaborateur pour la dernière période de rémunération du système hérité, qui crée les lignes du relevé de rémunération dans le nouveau système de paie. Entrez une ligne par code de rémunération, ainsi que le montant et les heures de cumul annuel. Les exemples d’étape sont les suivantes :

1. Ouvrez la page **Tous les états des revenus** et cliquez sur **Nouveau**.

    Entrez les éléments suivants : 

    | Champ      | Valeur                 |
    |------------|-----------------------|
    | Collaborateur     | Michael Redmond       |
    | Cycle de paie  | sm                    |
    | Période de rémunération | 16/06/2017 – 30/06/2017 |

2. Dans l’onglet **Ligne de l’état des revenus**, entrez les informations suivantes :

    Ligne 1 : onglet **Lignes de relevés de rémunération**

    | Champ            | Valeur       |
    |------------------|-------------|
    | Codes de rémunération    | Salaire normal |
    | Quantité         | 1.00        |
    | Taux             | 30,000      |
    | Onglet Détails de ligne |             |
    | Manuel           | (marqué)    |

    Ligne 2 : onglet **Lignes de relevés de rémunération**

    | Champ            | Valeur    |
    |------------------|----------|
    | Codes de rémunération    | Prime    |
    | Quantité         | 1.0000   |
    | Taux             | 4250.00  |
    | Onglet Détails de ligne |          |
    | Manuel           | (marqué) |

    Ligne 3 : onglet **Lignes de relevés de rémunération**

    | Champ           | Valeur      |
    |-----------------|------------|
    | Codes de rémunération   | commission |
    | Quantité        | 1.0000     |
    | Taux            | !,299.00   |
    | Taux            | 1,299.00   |
    | Onglet Détails de ligne |            |
    | Manuel          | (Marqué)   |

    > [!NOTE]
    > Définir le curseur **Manuel** sur **Oui** dans l’onglet **Détails de ligne** pour chaque ligne de l’état des revenus est important pour obtenir les soldes d’ouverture de salaire entrés pour chaque collaborateur.

3. Dans le volet **Action**, cliquez sur **Débloquer l’état des revenus** USA-FED-ER-FICA.
4. Dans le volet **Action**, cliquez sur **Bordereau de paie** pour ouvrir la page **Générer les bordereaux de paie** et définir les éléments suivants :

    | Champ              | Valeur     |
    |--------------------|-----------|
    | Date de paiement       | 6/30/2017 |
    | Type du cycle de paiement   | Manuel    |
    | Désactiver la comptabilité |   Oui     |

    > [!NOTE] 
    > Ceci est uniquement disponible lorsque le type d’exécution de paiement est Manuel et si l’utilisateur souhaite désactiver la comptabilité dans le cycle de paie.

    Cliquez sur **OK**, puis fermez la page **Infos**.

#### <a name="why-the-disable-accounting-slider-needs-to-set-to-yes-when-generating-pay-statements"></a>Pourquoi le curseur Désactiver la comptabilité doit-il être défini sur Oui lors de la génération des bordereaux de paye ?

Définir le curseur sur **Oui** empêche toutes les lignes du bordereau de paie d’être distribuées dans la comptabilité. Les montants des comptes généraux ont été mis à jour précédemment lorsque les soldes de compte du système hérité ont été entrés. Entrer des soldes d’ouverture pour les salaires permet de générer des états qui comprennent les informations des exercices précédents, ainsi que pour identifier les limites à des fins d’avantages et fiscales.

### <a name="c-create-pay-statements-for-employees"></a>C. Créer les bordereaux de paie pour les employés

Après avoir généré les bordereaux de paie avec des soldes d’ouverture, vous devez vérifier que les bordereaux de paie reflètent précisément les données salariales. Vous devez également mettre à jour manuellement les avantages et les informations fiscales pour qu’elles correspondent aux valeurs du système de paie précédent. Après avoir vérifié que les montants du système de paie précédent correspondent aux montants sur les bordereaux de paie actuels, vous devez finaliser les bordereaux de paie.

1. Ouvrez la page **Tous les bordereaux de paie**.
2. Mettre le dernier bordereau de paie en surbrillance généré pour Michael Redmond
3. Cliquez sur **Modifier** pour ouvrir la page **Bordereau de paie**.
4. Ouvrez l’onglet **Déductions des avantages** et entrez les informations suivantes :

    | Champ             | Valeur            |
    |-------------------|------------------|
    | Avantage           | Montant de la déduction |
    | 401K              | Participer      |
    | assurance pour les soins dentaires.            | SubSp            |
    | Dépenses liées aux soins au niveau du département | Participer      |
    | Vision            | SupSp            |

5. Dans l’onglet **Contributions pour les avantages**, entrez les informations suivantes :

    | Champ   | Valeur               |
    |---------|---------------------|
    | Avantage | Montant de la contribution |
    | 401K    | Participer         |
    | assurance pour les soins dentaires.  | SubSp               |
    | Vision  | SubSp               |

6. Dans l’onglet **Retenues fiscales**, entrez les informations suivantes :

    | Champ           | Valeur            |
    |-----------------|------------------|
    | Code taxe        | Montant de la déduction |
    | USA-FED-ER-FICA | 1600.00          |
    | USA-FED-ER-MEDI | 825.75           |

7. Dans l’onglet **Contributions fiscales**, entrez les informations suivantes :
8. Cliquez sur **Calculer.**

    > [!IMPORTANT] 
    > Validez les totaux du bordereau de paie pour qu’ils correspondent au cumul annuel du système hérité pour le collaborateur. Vous voudrez peut-être empêcher la finalisation à l’étape suivante pour effectuer une validation globale de tous les bordereaux de paie dans l’ensemble. Une fois validé, exécutez tous les bordereaux de paie et finalisez-les.

Le même processus peut être effectué par incréments trimestriels, si nécessaire, pour tous les trimestres antérieurs, chaque année. Cela n’est nécessaire que si le client doit voir les données par trimestre sans revenir au système existant.

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a>En cas d’erreur lors de la saisie des soldes d’ouverture pour un employé

Il est possible de contrepasser et d’entrer de nouveau les transactions. Pour contrepasser la transaction, tout ce que vous devez faire est de suivre les étapes de la page **Tous les bordereaux de paie**.

1. Cliquez sur **Contrepasser**.
2. Cliquez sur **Oui** lorsque le message « Lorsque vous contrepassez ce bordereau de paie, un bordereau de paie de contrepassation est créé pour contrebalancer ce bordereau de paie Aucun bordereau de paie ne peut être modifié. Voulez-vous contrepasser ce bordereau de paie ? s’affiche. 

Après avoir contrepassé le bordereau de paie, vous pouvez générer un nouveau bordereau de paie pour le travailleur avec l’état des revenus que vous avez créé précédemment. Veillez à résoudre toutes les lignes incorrectes dans l’état des revenus avant de générer le nouveau bordereau de paie, puis générez de nouveaux bordereaux de paie avec les montants appropriés. 


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]