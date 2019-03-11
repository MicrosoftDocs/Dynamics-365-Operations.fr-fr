---
title: Options de transactions d'immobilisations
description: Cette rubrique décrit les différentes méthodes disponibles pour créer des transactions d'immobilisation.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6362a63bca43b5ac8da14becf6b966e459365ce1
ms.sourcegitcommit: 68df883200b5c477ea1799cc28d3ef467cd29202
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2019
ms.locfileid: "377180"
---
# <a name="fixed-asset-transaction-options"></a>Options de transactions d'immobilisations

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les différentes méthodes disponibles pour créer des transactions d'immobilisation.

Vous pouvez paramétrer le module Immobilisations pour qu'il s'intègre avec les modules Comptabilité, Achats, Ventes et Approvisionnements. Vous pouvez également transférer des articles du module Gestion des stocks dans le module Immobilisations si vous souhaitez utiliser ces articles en interne.

## <a name="accounts-payable"></a>Module Comptabilité fournisseur
Vous pouvez entrer les transactions d'immobilisation dans la page N° document de journal. Cette page est accessible à partir de la page Journal des factures. Vous pouvez également ouvrir la page N° document de journal dans la page du journal des approbations de facture. Dans le champ Type de compte de contrepartie, sélectionnez Immobilisations. Ensuite, dans le champ Compte de contrepartie, sélectionnez un numéro d'immobilisation. Sous l'onglet Immobilisations, entrez les valeurs dans les champs Type de transaction et Registre.

## <a name="accounts-receivable"></a>Module Comptabilité client
Vous pouvez entrer des transactions d'immobilisations dans la page Facture financière.  Dans la page Facture financière, dans la grille Lignes de facture, sélectionnez une ligne. Cliquez sur l'organisateur Détails de ligne. Entrez le numéro de l'immobilisation et le registre pour la transaction de cession. Pour les factures financières, le type de transaction d'immobilisation est toujours Cession - vente.

## <a name="procurement-and-sourcing"></a>Approvisionnements
Vous pouvez entrer les transactions d'immobilisation dans la page Commande fournisseur. Entrez les informations requises pour créer une commande fournisseur, puis cliquez sur OK. Dans la page Commande fournisseur, cliquez sur l'organisateur Détails de ligne. Puis, sous l'onglet Immobilisations, entrez des informations sur l'immobilisation. 

Pour valider une transaction d'acquisition pour une immobilisation existante, spécifiez le numéro de l'immobilisation, le registre et le type de transaction. L'immobilisation ne peut pas être validée si certaines de ces informations sont manquantes. Pour valider une transaction d'acquisition pour une nouvelle immobilisation, sélectionnez l'option Nouvelle immobilisation ?, puis sélectionnez le groupe d'immobilisations auquel attribuer la nouvelle immobilisation. Toutefois, aucun champ d'immobilisation pour une ligne n'est disponible si l'article se trouve dans un groupe de modèles de stock qui utilise un modèle de stock de coûts standard. En outre, les options définies dans la page Paramètres des immobilisations déterminent également si vous pouvez valider les transactions d'acquisition à partir des modules Achats. 

Lorsque le journal Commande fournisseur ou le journal Stock vers immobilisations est utilisé pour acquérir des immobilisations, la valeur du stock est affectée.

## <a name="general-ledger"></a>Comptabilité
Vous pouvez valider tout type de transaction d'immobilisation dans la page Journal des opérations diverses. Vous pouvez également utiliser les journaux dans le module Immobilisations pour valider les transactions d'immobilisation.

## <a name="options-for-entering-fixed-asset-transaction-types"></a>Options de saisie des types de transactions d'immobilisation


| Type de transaction                    | Module                   | Options                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Acquisition, Ajustement d'acquisition | Immobilisations             | Immobilisations, stock vers immobilisation   |
|                                     | Comptabilité           | Journal des opérations diverses                           |
|                                     | Module Comptabilité fournisseur         | Journal des factures, journal d'approbation des factures |
|                                     | Approvisionnements | Commande fournisseur                            |
| Amortissement                        | Immobilisations             | Immobilisations                              |
|                                     | Comptabilité           | Journal des opérations diverses                           |
| Cession                            | Immobilisations             | Immobilisations                              |
| ** **                               | Comptabilité           | Journal des opérations diverses                           |
| ** **                               | Module Comptabilité client      | Facture financière                         |


La valeur restante des périodes d'amortissement de l'immobilisation n'est pas mise à jour lorsqu'une ligne de journal de type transaction d'amortissement est créée manuellement ou importée via une entité des données. Cette valeur est mise à jour lorsque le processus de proposition d'amortissement est utilisé pour créer la ligne de journal.

Pour plus d'informations, voir [Intégration des immobilisations](fixed-asset-integration.md).
