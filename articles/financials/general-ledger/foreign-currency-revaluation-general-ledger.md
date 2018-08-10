---
title: "Réévaluation des comptes en devises pour la comptabilité"
description: "Cette rubrique fournit une vue d'ensemble des fonctionnalités du processus de réévaluation des comptes en devises de la comptabilité : paramétrage, exécution du processus, calcul du processus, et contrepassation des transactions de réévaluation, si nécessaire."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fe87d76de257d12a5042ee13244b5cda8e965ff3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="foreign-currency-revaluation-for-general-ledger"></a>Réévaluation des comptes en devises pour la comptabilité

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des fonctionnalités du processus de réévaluation des comptes en devises de la comptabilité : paramétrage, exécution du processus, calcul du processus, et contrepassation des transactions de réévaluation, si nécessaire. 

Dans le cadre d'une fin de période, les conventions comptables nécessitent que les soldes de compte général dans des devises étrangères soient réévalués à l'aide des différents types de taux de change (actuel, historique, moyen, et ainsi de suite.). Par exemple, une convention comptable nécessite que les actifs et passifs soient réévalués au taux de change actuel, les immobilisations, au taux de change historique, et les comptes de résultat, à la moyenne mensuelle. La réévaluation des comptes en devises dans la comptabilité peut être utilisée pour réévaluer le bilan et les comptes de résultat. 

> [!NOTE]
> La réévaluation des comptes en devises est également disponible dans la Comptabilité client et la Comptabilité fournisseur. Si vous utilisez ces modules, les transactions en souffrance doivent être réévaluées à l'aide de la réévaluation des comptes en devises de ces modules. La réévaluation des comptes en devises de la Comptabilité client et de la Comptabilité fournisseur crée une écriture comptable dans la comptabilité pour refléter les pertes et les profits non réalisés, de sorte que les comptabilités auxiliaires et la comptabilité puissent être rapprochées. Comme la réévaluation des comptes en devises de la Comptabilité client et la Comptabilité fournisseur créent des écritures comptables dans la comptabilité, les comptes principaux de la Comptabilité client et la Comptabilité fournisseur doivent être exclus de la réévaluation des comptes en devises dans la comptabilité. 

Lorsque vous exécutez le processus de réévaluation, le solde de chaque compte principal validé dans une devise étrangère est réévalué. Les transactions de perte ou de profit non réalisé créées lors du processus de réévaluation sont générées par le système. Deux transactions peuvent être créées, l'une pour la devise comptable et l'autre pour la devise de déclaration, le cas échéant. Chaque écriture comptable sera validée dans les pertes ou profits non réalisés et le compte principal en cours de réévaluation.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Préparer le traitement de la réévaluation des comptes en devises
Avant d'exécuter le processus de réévaluation, le paramétrage suivant est nécessaire.

-   Sur la page **Compte principal** :
-   Si le compte principal doit être réévalué dans la comptabilité, sélectionnez **Réévaluation des comptes en devises**. Si le compte principal ne doit pas être réévalué (par exemple pour la Comptabilité client et la Comptabilité fournisseur si elles sont réévaluées dans les comptabilités auxiliaires), désactivez cette option.
-   Si le compte principal est marqué pour la réévaluation, entrez le **Type de taux de change**. Ce type de taux de change sera utilisé pour réévaluer le compte principal. Un champ distinct, **Type de taux de change des états financiers**, est disponible pour les états financiers. Ces deux champs ne sont pas synchronisés, ce qui permet d'utiliser différents types de taux de change pour la réévaluation et les états financiers.

-   Sur la page **Comptabilité** :
-   Spécifiez **Type de taux de change**. Si le type de taux de change n'est pas défini sur le compte principal, ce type de taux de change sera utilisé au cours de la réévaluation des comptes en devises.
-   Précisez les comptes de profit réalisé, de perte réalisée, de profit non réalisé et de perte non réalisée pour la réévaluation en devises. Les comptes de profit réalisé et de perte réalisée sont utilisés lors du règlement des transactions de la Comptabiité client et de la Comptabiité fournisseur. Tandis que les comptes de profit non réalisé et de perte non réalisée sont utilisés pour réévaluer les transactions en cours et les comptes principaux de la comptabilité.

-   Sur la page **Comptes de réévaluation de devise** :
-   Sélectionnez différents comptes de réévaluation de devise pour chaque devise et chaque société. Si aucun compte n'est défini, les comptes de la page **Comptabilité** sont utilisés.

## <a name="process-foreign-currency-revaluation"></a>Réévaluer des comptes en devises
Après le paramétrage, utilisez la page **Réévaluation des comptes en devises** pour réévaluer les soldes des comptes principaux. Vous pouvez exécuter le processus en temps réel ou le replanifier à l'aide d'un traitement par lots. 

La page **Réévaluation des comptes en devises** affiche l'historique de chaque réévaluation, notamment le moment où le processus a été exécuté, les critères qui ont été définis, un lien vers le document créé pour la réévaluation, et un enregistrement si une réévaluation précédente a été contrepassée. Pour exécuter le processus de réévaluation, sélectionnez le bouton **Réévaluation des comptes en devises**. 

Les valeurs **Date de début** et **Date de fin** définissent l'intervalle de dates du calcul du solde en devise étrangère qui est réévalué. Lorsque vous réévaluez les comptes de résultat, la somme de toutes les transactions survenant dans l'intervalle de dates est réévaluée. Lorsque vous réévaluez des comptes de bilan, la date de début est ignorée. Au lieu de cela, le solde à réévaluer est déterminé depuis le début de l'exercice jusqu'à la date de fin. 

**Date du taux** permet de définir la date à laquelle le taux de change doit se transférer. Par exemple, vous pouvez réévaluer les soldes entre la plage de dates du 1er janvier au 31 janvier, mais utiliser le taux de change défini pour le 1er février. 

Sélectionnez les comptes principaux à réévaluer : Tous, Bilan, ou Compte de résultat. Seuls les comptes principaux marqués pour la réévaluation (sur la page Compte principal) sont réévalués. Pour restreindre davantage la plage des comptes principaux, utilisez l'onglet Enregistrements à **inclure** pour définir une plage de comptes principaux, ou des comptes principaux individuels. 

Le processus de réévaluation peut être exécuté pour une ou plusieurs entités juridiques. La recherche affiche uniquement les entités juridiques auxquelles vous avez accès. Sélectionnez les entités juridiques pour lesquelles vous voulez exécuter le processus de réévaluation. 

La réévaluation peut être exécutée pour une ou plusieurs devises étrangères. La recherche inclut toutes les devises validées dans la plage de dates appropriées pour le type de compte principal (Bilan ou Compte de résultat), pour les entités juridiques sélectionnées à réévaluer. La devise comptable est incluse dans la liste, mais rien n'est réévalué si la devise comptable est sélectionnée. 

Définissez **Aperçu avant validation** sur **Oui** si vous souhaitez consulter le résultat de la réévaluation de la comptabilité. L'aperçu dans la comptabilité est différent de la simulation dans la réévaluation des comptes en devises de la Comptabilité client et de la Comptabilité fournisseur. La simulation dans la Comptabilité client et la Comptabilité fournisseur est un état, mais la comptabilité dispose d'un aperçu pouvant être validé, sans devoir réexécuter le processus de réévaluation. Les résultats de l'aperçu peuvent être exportés vers Microsoft Excel pour conserver l'historique de la manière dont les montants ont été calculés. Vous ne pouvez pas utiliser le traitement par lots si vous souhaitez afficher l'aperçu des résultats de la réévaluation. Dans l'aperçu, l'utilisateur dispose de l'option de valider les résultats de toutes les entités juridiques à l'aide du bouton **Valider**. En cas de problème avec les résultats d'une entité juridique, l'utilisateur dispose également de l'option de valider un sous-ensemble d'entités juridiques à l'aide du bouton **Sélectionner les entités juridiques à valider**. 

Une fois le processus de réévaluation des comptes en devises terminé, un enregistrement est créé pour effectuer le suivi de l'historique de chaque exécution.  Un enregistrement distinct est créé pour chaque entité juridique et couche de validation.

## <a name="calculate-unrealized-gainloss"></a>Calculer les profits non réalisés/pertes
Les transactions de profits non réalisés/pertes sont créées différemment entre le processus de réévaluation de la comptabilité et le processus de réévaluation de la Comptabilité client et de la Comptabilité fournisseur. Dans la Comptabilité client et la Comptabilité fournisseur, la réévaluation précédente est totalement contrepassée (en considérant que la transaction n'est pas encore réglée) et une transaction de réévaluation est créée pour les profits non réalisés/pertes sur la base du nouveau taux de change. Cela est dû au fait que nous réévaluons chaque transaction individuelle dans la Comptabilité client et la Comptabilité fournisseur. Dans la comptabilité, la réévaluation précédente n'est pas contrepassée. Au lieu de cela, une transaction est créée pour le delta entre le solde du compte principal, notamment les montants de réévaluation précédents, et la nouvelle valeur basée sur le taux de change de la Date du taux. 

**Exemple** Les soldes suivants existent pour le compte principal 110110.

|            |                    |                        |                       |
|------------|--------------------|------------------------|-----------------------|
| **date ;**   | **Compte général** | **Montant de la transaction** | **Valeur comptable** |
| Janvier 20 | 110110 (disponibilités)      | 500 EUR (Débit)        | 1 000 USD (Débit)      |

Le compte principal est réévalué le 31 janvier.  Le profit non réalisé/perte est calculé comme suit.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Solde actuel dans la devise de transaction** | **Solde actuel en devise comptable** | **Taux de change au moment de la réévaluation** | **Nouveau montant en devise comptable** | **Profit non réalisé/perte**    |
| 500 EUR                                     | 1 000 USD                                   | 166.6667                         | 833,33 EUR (500 x 1,666667)        | Perte de 166,67 (833,33 – 1 000) |

L'écriture comptable suivante est créée.

|            |                          |           |            |
|------------|--------------------------|-----------|------------|
| **date ;**   | **Compte général**       | **Débit** | **Crédit** |
| 1er janvier | 110110 (disponibilités)            |           | 166.67     |
| 1er janvier | 801400 (Perte non réalisée) | 166.67    |            |

Aucune nouvelle transaction n'est validée pour le mois de février.  Le compte principal est réévalué le 28 février.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Solde actuel dans la devise de transaction** | **Solde actuel en devise comptable** | **Taux de change au moment de la réévaluation** | **Nouveau montant en devise comptable** | **Profit non réalisé/perte**    |
| 500 EUR                                     | 833,33 USD (1 000 - 166,67)                 | 250.0000                         | 1250 USD (500 x 2,5)               | Profit de 416,67 (1 250 – 833,33) |

L'écriture comptable suivante est créée.

|             |                          |           |            |
|-------------|--------------------------|-----------|------------|
| **date ;**    | **Compte général**       | **Débit** | **Crédit** |
| 28 février | 110110 (disponibilités)            | 416.67    |            |
| 28 février | 801600 (Profit non réalisé) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>Réévaluation des comptes en devises contrepassée
Si vous devez contrepasser la transaction de réévaluation, sélectionnez le bouton **Transaction de contrepassation** sur la page **Réévaluation des comptes en devises**. Un enregistrement historique de réévaluation des comptes en devises est créé pour tenir à jour le suivi d'audit historique du moment où la réévaluation s'est produite ou a été contrepassée. 

Vous pouvez contrepasser les résultats de l'ordre obsolète de réévaluation, mais vous devez contrepasser également une réévaluation plus récente pour garantir les soldes corrects de chaque compte principal réévalué. Les contrepassations peuvent être exécutées dans un ordre obsolète car il n'y a aucune façon de contrôler quels comptes principaux sont réévalués et la fréquence à laquelle ils sont réévalués. Par exemple, une organisation peut choisir de réévaluer les comptes principaux de disponibilités chaque trimestre, et tous les autres comptes principaux chaque mois.




