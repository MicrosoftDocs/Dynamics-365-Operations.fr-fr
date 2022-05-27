---
title: Options de transactions d’immobilisations
description: Cette rubrique décrit les différentes méthodes disponibles pour créer des transactions d’immobilisation.
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: kfend
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 507e263e7267fe96cdf9ed78a84924839c2de982
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "8719746"
---
# <a name="fixed-asset-transaction-options"></a>Options de transactions d’immobilisations

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les différentes méthodes disponibles pour créer des transactions d’immobilisation.

Vous pouvez paramétrer le module Immobilisations pour qu’il s’intègre avec les modules Comptabilité, Achats, Ventes et Approvisionnements. Vous pouvez également transférer des articles du module Gestion des stocks dans le module Immobilisations si vous souhaitez utiliser ces articles en interne.

## <a name="accounts-payable"></a>Module Comptabilité fournisseur
Vous pouvez entrer les transactions d’immobilisation dans la page N° document de journal. Cette page est accessible à partir de la page Journal des factures. Vous pouvez également ouvrir la page N° document de journal dans la page du journal des approbations de facture. Dans le champ Type de compte de contrepartie, sélectionnez Immobilisations. Ensuite, dans le champ Compte de contrepartie, sélectionnez un numéro d’immobilisation. Sous l’onglet Immobilisations, entrez les valeurs dans les champs Type de transaction et Registre.

## <a name="accounts-receivable"></a>Module Comptabilité client
Vous pouvez entrer des transactions d’immobilisations dans la page Facture financière.  Dans la page Facture financière, dans la grille Lignes de facture, sélectionnez une ligne. Cliquez sur l’organisateur Détails de ligne. Entrez le numéro de l’immobilisation et le registre pour la transaction de cession. Pour les factures financières, le type de transaction d’immobilisation est toujours Cession – vente.

## <a name="procurement-and-sourcing"></a>Approvisionnements
Vous pouvez entrer les transactions d’immobilisation dans la page Commande fournisseur. Entrez les informations requises pour créer une commande fournisseur, puis cliquez sur OK. Dans la page Commande fournisseur, cliquez sur l’organisateur Détails de ligne. Puis, sous l’onglet Immobilisations, entrez des informations sur l’immobilisation. 

Pour valider une transaction d’acquisition pour une immobilisation existante, spécifiez le numéro de l’immobilisation, le registre et le type de transaction. L’immobilisation ne peut pas être validée si certaines de ces informations sont manquantes. Pour valider une transaction d’acquisition pour une nouvelle immobilisation, sélectionnez l’option Nouvelle immobilisation ?, puis sélectionnez le groupe d’immobilisations auquel attribuer la nouvelle immobilisation. Toutefois, aucun champ d’immobilisation pour une ligne n’est disponible si l’article se trouve dans un groupe de modèles de stock qui utilise un modèle de stock de coûts standard. En outre, les options définies dans la page Paramètres des immobilisations déterminent également si vous pouvez valider les transactions d’acquisition à partir des modules Achats. 

Lorsque le journal Commande fournisseur ou le journal Stock vers immobilisations est utilisé pour acquérir des immobilisations, la valeur du stock est affectée.

## <a name="general-ledger"></a>Comptabilité
Vous pouvez valider tout type de transaction d’immobilisation dans la page Journal des opérations diverses. Vous pouvez également utiliser les journaux dans le module Immobilisations pour valider les transactions d’immobilisation.

### <a name="options-for-entering-fixed-asset-transaction-types"></a>Options de saisie des types de transactions d’immobilisation


| Type de transaction                    | Module                   | Options                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Acquisition, Ajustement d’acquisition | Immobilisations             | Immobilisations, stock vers immobilisation   |
|                                     | Comptabilité           | Journal des opérations diverses                           |
|                                     | Module Comptabilité fournisseur         | Journal des factures, journal d’approbation des factures |
|                                     | Approvisionnements | Commande fournisseur                            |
| Amortissement                        | Immobilisations             | Immobilisations                              |
|                                     | Comptabilité           | Journal des opérations diverses                           |
| Cession                            | Actifs             | Actifs                              |
|                                     | Comptabilité           | Journal des opérations diverses                           |
|                                     | Module Comptabilité client      | Facture financière                         |

La valeur restante n’est pas mise à jour pour les périodes d’amortissement d’une immobilisation lorsqu’une ligne de journal de type transaction d’amortissement est créée manuellement ou importée via une entité des données. Cette valeur restante est mise à jour lorsque le processus de proposition d’amortissement est utilisé pour créer la ligne de journal.

Pour plus d’informations, voir [Intégration des immobilisations](fixed-asset-integration.md).

Le système empêche de comptabiliser deux fois l’amortissement sur la même période. Par exemple, si deux utilisateurs créent des propositions d’amortissement séparément pour janvier, l’amortissement du premier utilisateur est enregistré dans le premier journal. Lorsque le deuxième utilisateur comptabilise l’amortissement dans le deuxième journal, le système vérifie la date à laquelle l’amortissement a été exécuté pour la dernière fois et ne comptabilise pas l’amortissement pour la même période une deuxième fois.

### <a name="transactions-that-require-a-different-voucher-number"></a>Transactions qui nécessitent un N° document différent

Les transactions d'immobilisations suivantes utiliseront des N° documents différents :

- Une acquisition supplémentaire est effectuée sur une immobilisation et l’amortissement de « rattrapage » est calculé.
- Une immobilisation est fractionnée.
- Un paramètre pour calculer l’amortissement sur la cession est activé et l’immobilisation est ensuite cédée.
- Une date de mise en service d’immobilisation est antérieure à la date d’acquisition. Par conséquent, un ajustement d’amortissement est validé.

> [!NOTE]
> Lorsque vous entrez des transactions, assurez-vous que toutes les transactions s’appliquent à la même immobilisation. Un N° document ne sera pas validé s’il contient plus d’une immobilisation, même si le champ **Nouveau N° document** est défini sur **Un N° document uniquement** sur la page **Noms de journal** dans la comptabilité. Si vous incluez plusieurs immobilisations dans le N° document, vous recevrez le message « Il ne peut y avoir qu’une transaction d’immobilisation par N° document » et vous ne pourrez pas publier le N° document.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
