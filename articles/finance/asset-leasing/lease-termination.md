---
title: Proposition de résiliation de bail
description: Cette rubrique explique comment proposer la résiliation d’un bail.
author: moaamer
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e303821bd41751cb0a07442613b8b20e8061b052
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819864"
---
# <a name="propose-a-lease-for-termination"></a>Proposer la résiliation d’un bail

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Si un bail est résilié prématurément, le leasing d’actifs peut enregistrer une écriture de journal de résiliation pour radier le passif de location, l’actif de droit d’utilisation (ROU) et l’amortissement cumulé, et comptabiliser un gain ou une perte. Le processus de résiliation anticipée met fin à un bail et aux registres associés. Il ne met pas fin aux registres des baux individuels. Cette rubrique décrit la fonctionnalité qui vous permet de proposer un bail pour résiliation et de traiter l’écriture de journal de résiliation de bail.

Si un bail n’est pas classé comme un contrat de location avec traitement de loyer différé et n’est pas associé à une immobilisation, le leasing d’actifs produit l’écriture de journal de résiliation suivante.

| Transaction                           | Débit (Dr.) | Crédit (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. Passif locatif                   | O           |              |
| Dr. Amortissement cumulé          | O           |              |
| Dr. Profit (perte) suite à la modification du bail | O           |              |
| Cr. Actif loué                       |             | O            |
| Cr. Profit (perte) suite à la modification du bail |             | O            |

Si le registre des baux est classé comme un registre de loyers différés, l’écriture annule le solde du loyer différé avant la résiliation dans le compte de gains ou de pertes, comme indiqué ici.

| Transaction                           | Débit (Dr.) | Crédit (Cr.) | 
|---------------------------------------|-------------|--------------|
| Dr. Loyer reporté                     | O           |              |
| Cr. Profit (perte) suite à la modification du bail |             | O            |
| Cr. Loyer reporté                     |             | O            |
| Dr. Profit (perte) suite à la modification du bail | O           |              |

Si le registre des baux est lié à une immobilisation, l’immobilisation ROU est comptabilisée dans les immobilisations. Cette comptabilité comprend la comptabilisation des résiliations anticipées. Le leasing d’actifs produit l’écriture de journal suivante pour radier le passif locatif.

| Transaction                           | Débit (Dr.) | Crédit (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. Passif locatif                   | O           |              |
| Cr. Profit (perte) suite à la modification du bail |             | O            |

Pour plus d’informations sur la manière correcte d’éliminer un droit d’utilisation de l’actif, voir [Céder des immobilisations en tant que rebut](../fixed-assets/dispose-of-a-fixed-asset-as-scrap.md).

## <a name="propose-a-lease-for-termination"></a>Proposer la résiliation d’un bail

1. Accédez au bail qui doit être résilié, puis, dans le volet Actions, sélectionnez **Proposition de résiliation**.

    > [!NOTE]
    > Le bouton **Proposition de résiliation** n’est pas disponible s’il existe des écritures de journal non comptabilisées dans un livre. Avant de pouvoir résilier le bail, vous devez enregistrer ou supprimer toutes les écritures de journal qui ont été créées pour le bail.

2. Dans la boîte de dialogue qui apparaît, définissez les champs **Date d’effet** et **Date de validation** pour l’écriture de journal de résiliation.
3. Sélectionnez **Proposition de résiliation** pour proposer la résiliation du bail.
4. Sélectionnez **Après la résiliation du bail** pour enregistrer automatiquement l’écriture de journal de résiliation de bail.
5. Sur la page **Résiliations de bail**, sélectionnez l’ID du bail que vous avez proposé pour la résiliation pour afficher les lignes de résiliation. Les lignes de résiliation indiquent les valeurs comptables du droit d’utilisation de l’actif, du passif locatif, de l’amortissement cumulé, du loyer reporté (le cas échéant) et du gain ou de la perte qui doit être comptabilisé à la résiliation du contrat de location.

Le bail est maintenant prêt à être résilié. La valeur du champ **Statut de résiliation** du registre des baux est remplacée par **Prêt pour la résiliation**. À ce stade, vous ne pouvez plus valider les écritures de journal sur le bail, ni les ajuster. 

## <a name="process-leases-that-are-ready-for-termination"></a>Traiter les baux prêts à être résiliés

Pour traiter les baux prêts pour la résiliation et valider l’écriture de journal de résiliation, procédez comme suit.

1. Sur la page **Résiliations de bail**, sélectionnez le bail à traiter, puis sélectionnez **Mettre un terme**.
2. Dans la boîte de dialogue qui apparaît, sélectionnez **OK**.

Le système impute l’écriture au journal de résiliation. Le champ **Statut du bail** du registre des baux est défini sur **Résilié**, et le champ **Statut de la proposition de résiliation** est défini sur **Terminé**.

## <a name="reverse-a-lease-termination"></a>Annuler une résiliation de bail

Pour annuler une écriture de journal de résiliation de bail et ouvrir un bail résilié, procédez comme suit.

- Sur la page **Résiliations de bail**, sélectionnez la résiliation de bail à annuler, puis sélectionnez **Annuler la résiliation**.

Le système annule l’écriture au journal de résiliation. Le champ **Statut du bail** du registre des baux est défini sur **Ouvert**. Le bail n’apparaît plus sur la page **Résiliations de bail** et peut être proposé à nouveau pour résiliation.

## <a name="example-of-a-lease-termination"></a>Exemple de résiliation de bail

Pour cet exemple, le bail est associé à un actif non spécialisé qui ne transfère pas la propriété ou n’accorde pas l’option d’achat au locataire.

### <a name="setup"></a>Paramétrage

Les tableaux suivants présentent les valeurs définies sur les onglets **Général** et **Lignes de l’échéancier de paiement** pour la location utilisée dans cet exemple.

**Onglet Général**

| Champ                      | Valeur            |
|----------------------------|------------------|
| Juste valeur de l’actif    | 600,000          |
| Devise                   | USD              |
| Coûts directs initiaux       | 1 000            |
| Taux d’emprunt marginal | 7 %               |
| Intervalle de composition       | Année         |
| Durée de vie utile de l’actif (mois) | 600              |
| Type d’annuité               | Annuité ordinaire |
| Date d’entrée en vigueur          | 1/1/2019         |

**Onglet Lignes d’échéancier de paiement**

| Champ             | Valeur      |
|-------------------|------------|
| Date de début        | 1/1/2019   |
| Intervalle de périodes   | Tous les mois    |
| Périodes           | 120        |
| Date de fin          | 31/12/2028 |
| Fréquence de paiement | Année   |
| Montant du paiement    | 10,000     |

### <a name="steps-for-terminating-the-lease"></a>Étapes de résiliation du bail

1. Après avoir créé le contrat de location comme décrit précédemment dans cette rubrique, accédez au registre de location et confirmez l’échéancier de paiement. Enregistrez ensuite l’écriture de journal de reconnaissance initiale. Le droit d’utilisation de l’actif initial est de 71 235,81 $ et le passif de location doit être 70 235,81 $. Pour cet exemple, le contrat de location a été classé comme contrat de location simple conformément à l’Article 842 sur la codification des normes comptables (ASC 842).
2. Exécutez le processus de journal par lots trois fois pour simuler l’écoulement de trois ans pour les paiements de location, les frais d’intérêts et les dépenses d’amortissement.
3. Une fois que vous avez terminé d’exécuter les trois traitements par lots, revenez au registre de location et ouvrez les tableaux de transactions de passif et d’actif pour afficher la valeur comptable actuelle du droit d’utilisation de l’actif et du passif locatif. Après trois ans, la valeur du passif devrait être d’environ -53 893,00 $, et la valeur de l’actif devrait être d’environ 54 593,00 $.

    Au bout des trois ans, l’entreprise et le bailleur conviennent d’un commun accord de résilier le bail. Par conséquent, vous devez maintenant résilier le bail.

4. Accédez au bail qui doit être résilié, puis, dans le volet Actions, sélectionnez **Proposition de résiliation**. 
5. Dans la boîte de dialogue qui apparaît, dans le champ **Date effective** et **Date de validation**, entrez **01/01/2021**.
6. Sélectionnez **Proposition de résiliation** pour proposer la résiliation du bail.

    La page **Résiliations de bail** apparaît et affiche le bail qui sera résilié.

7. Pour afficher les lignes de résiliation, sélectionnez l’ID du bail que vous avez proposé pour la résiliation. Les lignes de résiliation indiquent les valeurs comptables du bail. Le tableau suivant montre quelles devraient être ces valeurs pour cet exemple. 

    | Champ                                                 | Valeur      |
    |-------------------------------------------------------|------------|
    | Solde comptable du passif dans la devise de la transaction | 53 892,89 $ |
    | Droit d’utilisation de l’actif dans la devise de la transaction            | 71 235,81 $ |
    | Amortissement cumulé dans la devise de transaction      | 16 642,92 $ |
    | Gain (perte) dans la devise de transaction                   | -700,00 $   |

8. Pour imputer l’écriture dans le journal de résiliation, sélectionnez le bail sur la page **Résiliations de bail**, puis sélectionnez **Mettre un terme**.
9. Dans la boîte de dialogue qui apparaît, sélectionnez **OK**.
10. Pour afficher l’écriture de journal de résiliation qui a été créée et validée, accédez au journal de location de l’immobilisation dans le registre des baux. Le tableau suivant montre à quoi doit ressembler cette entrée pour cet exemple.

    | Transaction                           | Débit (Dr.) | Crédit (Cr.) |
    |---------------------------------------|-------------|--------------|
    | Dr. Passif locatif                   | 53,892.89   |              |
    | Amortissement cumulé dr.          | 16,642.92   |              |
    | Dr. Profit (perte) suite à la modification du bail | 700.00      |              |
    | Cr. Actif loué                       |             | 71,235.81    |

11. Pour voir l’effet net de la résiliation, où l’actif et le passif de location de ROU seront de 0 (zéro), ouvrez les tableaux des transactions de passif et d’actif.

Le statut du bail doit maintenant être **Résilié**. Aucune écriture de journal supplémentaire ne sera imputée à ce bail à moins que la résiliation ne soit annulée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]