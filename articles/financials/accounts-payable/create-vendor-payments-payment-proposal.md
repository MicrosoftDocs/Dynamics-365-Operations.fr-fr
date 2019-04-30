---
title: Création de paiements fournisseur via une proposition de paiement
description: Cette rubrique fournit une vue d'ensemble des options de proposition de paiement et il inclut quelques exemples qui indiquent comment les propositions de paiement sont exécutées.
author: abruer
manager: AnnBe
ms.date: 04/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14312
ms.assetid: 585d5b0b-1b79-4a03-ab18-528918070377
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 54c3d2b6ecae1481fd9b979e5d4ced217a67f5aa
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2019
ms.locfileid: "896854"
---
# <a name="create-vendor-payments-by-using-a-payment-proposal"></a>Création de paiements fournisseur via une proposition de paiement

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des options de proposition de paiement et il inclut quelques exemples qui indiquent comment les propositions de paiement sont exécutées. Les propositions de paiement sont souvent utilisées pour créer des paiements fournisseurs car la demande de proposition de paiement peut être utilisée pour sélectionner rapidement les factures fournisseur pour le paiement, en fonction de critères tels que la date d'échéance et l'escompte de règlement. 

Les organisations utilisent souvent des propositions de paiement pour créer des paiements fournisseurs, car la demande de proposition de paiement peut être utilisée pour sélectionner rapidement les factures fournisseur pour paiement, en fonction de la date d'échéance, de l'escompte de règlement et de tout autre critère. 

La demande de proposition de paiement contient différents onglets, chacun ayant leurs options pour sélectionner les factures à payer. L'onglet **Paramètre** contient les options que la majorité des organisations utilisent le plus souvent. Dans l'organisateur **Enregistrements à inclure**, vous pouvez spécifier les factures ou les fournisseurs à inclure pour le paiement en définissant des plages de caractéristiques. Par exemple, si vous souhaitez payer une seule plage spécifique de fournisseurs, vous pouvez définir un filtre pour la plage de fournisseurs. Cette fonctionnalité est souvent utilisée pour sélectionner des factures pour un mode de paiement spécifique. Par exemple, si vous définissez un filtre où **Mode de paiement** = **Chèque**, seules les factures associées à ce mode de paiement sont sélectionnées pour le paiement, à condition qu'elles répondent également à d'autres critères spécifiés dans la requête. L'onglet **Paramètres avancés** contient des options supplémentaires (certaines d'entre elles peuvent ne pas concerner votre organisation). Par exemple, cet onglet contient les options pour payer les factures des paiements centralisés.

## <a name="parameters"></a>Paramètres
-   **Sélectionner les factures par** – Les factures se situant dans la période spécifiée par les champs **Date de début** et **Date de fin** peuvent être sélectionnées par date d'échéance, date d'escompte de règlement, ou les deux. Si vous utilisez la date d'escompte de règlement, le système recherche d'abord les factures dont la date d'escompte de règlement se situe entre la date de début et la date de fin. Le système détermine ensuite si la facture est éligible pour l'escompte de règlement à l'aide de la date de la session pour garantir que la date d'escompte de règlement n'est pas déjà passée.
-   **Date de début** et **Date de fin** – Les factures dont la date d'échéance ou d'escompte de règlement se situe dans cette période sont sélectionnées pour le paiement.
-   **Date de paiement minimal** – Permet d'entrer la date de paiement minimal. Par exemple, les champs **Date de début** et **Date de fin** précisent une plage du 1er au 10 septembre, et la date de paiement minimal est le 5 septembre. Dans ce cas, toutes les factures dont la date d'échéance se situe entre le 1er et le 5 septembre ont une date de paiement au 5 septembre. Toutefois, toutes les factures dont la date d'échéance se situe entre le 5 et le 10 septembre ont une date de paiement qui est égale à la date d'échéance de chaque facture.
-   **Montant limite** – Saisissez le montant total maximal pour tous les paiements.
-   **Créer des paiements sans prévisualiser la facture** – Si cette option est définie sur **Oui**, les paiements seront créés immédiatement sur la page **Paiements fournisseur**. La page **Proposition de paiement** sera ignorée. Par conséquent, les paiements seront créés plus rapidement. Les paiements peuvent encore être modifiés à partir de la page **Paiements fournisseur**. Sinon, vous pouvez revenir sur la page **Proposition de paiement** à l'aide du bouton **Modifier les factures du paiement sélectionné**.

## <a name="advanced-options"></a>Options avancées
- **Vérifier le solde fournisseur** – Si cette option est définie sur **Oui**, le système vérifie qu'un fournisseur n'a pas de solde débiteur avant le règlement de n'importe quelle facture. Si un fournisseur a un solde débiteur, aucun paiement n'est créé. Par exemple, le fournisseur peut avoir des avoirs ou des paiements qui ont été validés, mais qui n'ont pas encore été réglés. Dans ces cas, le fournisseur ne doit pas être payé. Au lieu de cela, les avoirs ou les paiements doivent être réglés par rapport aux factures en attente.
- **Supprimer les paiements négatifs** – Cette option fonctionne différemment, selon les paiements effectués pour les factures individuelles ou pour la somme des factures qui répondent aux critères de paiement. Ce comportement est défini sur la méthode de paiement.
- **Paiement pour chaque facture** – Si l'option **Supprimer les paiements négatifs** est définie sur **Oui**, et si une facture et un paiement non réglés existent pour un fournisseur, seule la facture est sélectionnée pour paiement. Le paiement existant n'est pas réglé avec la facture. Si l'option **Supprimer les paiements négatifs** est définie sur **Non** et si une facture et un paiement ne sont pas réglés, la facture et le paiement sont sélectionnés pour paiement. Un paiement est créé pour paiement, puis un remboursement (paiement négatif) est créé pour le paiement.
- **Paiement de la somme des factures** – Si l'option **Supprimer les paiements négatifs** est définie sur **Oui**, et si une facture et un paiement non réglés existent pour un fournisseur, les deux sont sélectionnés pour paiement et les montants sont ajoutés pour générer montant total du paiement. La seule exception se produit si la somme entraîne un remboursement. Dans ce cas, ni la facture ni le paiement n'est sélectionné. Si l'option **Supprimer les paiements négatifs** est définie sur **Non** et si une facture et un paiement ne sont pas réglés, les deux sont sélectionnés pour paiement et les montants sont ajoutés pour générer le montant total du paiement.
- **Imprimer l'état uniquement** – Définissez cette option sur **Oui** pour voir les résultats de la proposition de paiement sur un état, mais sans créer de paiement.
- **Inclure les factures fournisseur d'autres entités juridiques** – Si votre organisation a un processus centralisé pour le paiement, et si la proposition de paiement doit inclure les factures d'autres entités juridiques incluses dans les critères de recherche, définissez cette option sur **Oui**.
- **Proposer un paiement fournisseur séparé par entité juridique** – Si cette option est définie sur **Oui**, un paiement distinct est créé pour chaque entité juridique par fournisseur. Le fournisseur du paiement est le fournisseur de la facture de chaque entité juridique. Si cette option est définie sur **Non**, et si des factures doivent être payées à un fournisseur dans plusieurs entités juridiques, un paiement est créé pour le montant total des factures sélectionnées de toutes les sociétés sélectionnées. Le fournisseur pour le paiement correspond à l'entité juridique active. Si ce compte n'existe pas dans l'entité juridique active, le compte fournisseur de la première facture à payer est utilisé.
- **Devise de paiement** – Ce champ permet de spécifier la devise dans laquelle tous les paiements sont créés. Si une devise n'est pas définie, chaque facture est payée dans la devise de la facture.
- **Jour de paiement** – Permet d'entrer le jour de la semaine où le paiement doit être effectué. Ce champ n'est utilisé que si le mode de paiement est défini sur toutes les factures pour que le paiement survienne un jour précis de la semaine.
- **Type de compte de contrepartie** et **Compte de contrepartie** – Ces champs permettent de définir un type de compte spécifique (tel que **Comptabilité** ou **Banque**) et le compte de contrepartie (tel qu'un compte bancaire spécifique). Le mode de paiement pour la facture définit le type de compte de contrepartie par défaut et le compte de contrepartie, mais vous pouvez utiliser ces champs pour remplacer les valeurs par défaut.
- **Date de paiement récapitulative** : N'est utilisée que lorsque le champ **Période** du mode de paiement est défini sur **Total**. Si aucune date n'est définie, tous les paiements sont créés à cette date. Le champ **Date de paiement minimal** est ignoré.
- **Filtres supplémentaires** – Dans l'organisateur **Enregistrements à inclure**, vous pouvez définir des plages supplémentaires de critères. Par exemple, si vous souhaitez payer une seule plage de fournisseurs, vous pouvez définir un filtre pour la plage de fournisseurs. Cette fonctionnalité est souvent utilisée pour sélectionner des factures pour un mode de paiement spécifique. Par exemple, si vous définissez un filtre où **Mode de paiement** = **Chèque**, seules les factures associées à ce mode de paiement sont sélectionnées pour le paiement, à condition qu'elles répondent également à d'autres critères spécifiés dans la requête.

## <a name="scenarios"></a>Scénarios

| Fournisseur | Facture | Date de facture | Montant de la facture | Date d'échéance | Date d'escompte de règlement | Montant de l'escompte de règlement |
|--------|---------|--------------|----------------|----------|--------------------|----------------------|
| 3050   | 1 001    | 15 juin      | 500,00         | 15 juillet  | 29 juin            | 10,00                |
| 3050   | 1 002    | 20 juin      | 600,00         | 20 juillet  | 4 juillet             | 12,00                |
| 3075   | 1003    | 15 juin      | 250,00         | 29 juin  |                    | 0,00                 |
| 3100   | 1004    | 17 juin      | 100,00         | 17 juillet  | 1 juillet             | 1,00                 |

Le 1er juillet, April a payé les fournisseurs. Elle utilise une proposition de paiement pour effectuer cette tâche plus efficacement.

### <a name="option-1-by-cash-discount"></a>Option 1 : Par escompte de règlement

April sélectionne **Escompte de règlement** comme type de proposition. Pour la plage de dates de paiement, elle saisit la plage du 26 juin au 10 juillet. Les factures suivantes sont incluses dans la proposition :

-   1002, car la date de remise du 4 juillet est comprise dans la plage de dates de paiement.
-   1004, car la date de remise du 1er juillet est comprise dans la plage de dates de paiement.

Les factures suivantes ne sont pas incluses dans la proposition :

-   1001, car la date de remise du 29 juin a déjà expiré, aussi cette facture n'est plus éligible pour l'escompte de règlement.
-   1003, car la facture n'a pas de date de remise.

### <a name="option-2-by-due-date"></a>Option 2 : Par date d'échéance

April sélectionne **Par date d'échéance** comme type de proposition. Pour la plage de dates de paiement, elle saisit la plage du 26 juin au 10 juillet. Les factures suivantes sont incluses dans la proposition :

-   1003, car la date d'échéance du 29 juin est comprise dans la plage de dates de paiement.

Les factures suivantes ne sont pas incluses dans la proposition :

-   1001, car la date d'échéance du 15 juillet n'est pas comprise dans la plage de dates de paiement.
-   1002, car la date d'échéance du 20 juillet n'est pas comprise dans la plage de dates de paiement.
-   1004, car la date d'échéance du 17 juillet n'est pas comprise dans la plage de dates de paiement.

### <a name="option-3-by-due-date-and-cash-discount"></a>Option 3 : Par échéance et escompte de règlement

April sélectionne **Échéance et escompte de règlement** comme type de proposition. Pour la plage de dates de paiement, elle saisit la plage du 26 juin au 10 juillet. Les factures suivantes sont incluses dans la proposition :

-   1003, car la date d'échéance du 29 juin est comprise dans la plage de dates de paiement.
-   1002, car la date de remise du 4 juillet est comprise dans la plage de dates de paiement.
-   1004, car la date de remise du 1er juillet est comprise dans la plage de dates de paiement.

Les factures suivantes ne sont pas incluses dans la proposition :

-   1001, car la date de remise du 29 juin a déjà expiré, aussi cette facture n'est plus éligible à l'escompte de règlement, et la date d'échéance du 15 juillet est également en dehors de la période.

## <a name="country-specific-considerations"></a>Considérations spécifique au pays
### <a name="norway"></a>Norvège

#### <a name="dimension-control"></a>Contrôle de la dimension

Le contrôle des dimensions vous permet de contrôler le regroupement de lignes générées par la proposition de paiement et de définir par défaut des dimensions en fonction des dimensions financières utilisées pour les factures appliquées. Dans le contexte de la Norvège, pour chaque mode de paiement il existe un onglet de dimension financière dans lequel vous pouvez activer le contrôle des dimensions ainsi qu'activer le regroupement de chaque dimension. Les options disponibles sont :

-   Le champ **Contrôle de dimension** est désactivé. La proposition de paiement se comporte comme pour tout autre pays.
-   Le champ **Contrôle de dimension** est activé sans définir davantage les dimensions. La proposition de paiement est créée sans prendre en considération les dimensions. La transaction créée n'hérite d'aucune dimension de l'entrée appliquée.
-   Le champ **Contrôle de dimension** est activé et d'autres dimensions sont activées. Maintenant vous définissez comment les dimensions seront copiées dans le journal. Par exemple : • Activez la case à cocher **BusinessUnit** pour créer une proposition de paiement par unité commerciale pour le mode de paiement, • Activez la case à cocher **CostCenter** pour créer une proposition de paiement par centre de coût pour le mode de paiement

> [[!NOTE]
> Si vous sélectionnez plusieurs dimensions dans la troisième option, une proposition de paiement est créée pour une combinaison de dimensions.

#### <a name="bank-account-selection"></a>Sélection de compte bancaire

Vous pouvez définir un compte de paiement de débit standard par mode de paiement quel que soit le contexte du pays. Cela est défini dans les lignes de paiement générées par une proposition. Avec la fonctionnalité du compte bancaire, vous pouvez définir plusieurs comptes bancaires de débit gérés par dimension et par devise ou une combinaison de ces éléments pour utiliser différents comptes bancaires de débit, en fonction de chaque combinaison. Vous pouvez paramétrer ces combinaisons sur la page **Modes de paiement** à l'aide du bouton  **Comptes bancaires** disponible pour chaque mode de paiement avec **Type de compte de validation** = **Banque**.



