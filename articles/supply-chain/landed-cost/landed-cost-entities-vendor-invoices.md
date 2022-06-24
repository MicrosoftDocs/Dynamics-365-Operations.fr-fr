---
title: Entités de facture fournisseur
description: Cet article fournit des informations sur les entités de facture fournisseur, qui permettent de configurer des codes de type de coût pour les coûts internes ou les coûts dérivés en externe.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 171b383e1549babd76fd18e4932436a66aa62cc1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873925"
---
# <a name="vendor-invoice-entities"></a>Entités Facture fournisseur

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Le module **Prix au débarquement** permet de configurer des codes de type de coût pour les coûts internes ou les coûts externes dérivés. Si un coût est externe à une entreprise, une facture est attendue du prestataire. Cette facture est traitée comme un journal des factures pouvant être associé à un voyage, et la valeur de la facture peut être répartie sur un ou plusieurs coûts du voyage.

Les entités de facture fournisseur permettent de répartir la valeur d’une ligne de journal sur un ou plusieurs coûts d’un voyage qui partagent le même code de type de coût.

Un coût ne peut être affecté que si l’en-tête du journal des factures et les lignes du journal des factures existent.

## <a name="vendor-voyage-cost-allocations-itmledgerjournalcostlinesvoyagesentity"></a>Répartition des coûts de voyage du fournisseur (ITMLedgerJournalCostLinesVoyagesEntity)

L’entité de données de répartition des coûts de voyage du fournisseur permet à une ligne de facture fournisseur d’être répartie sur un ou plusieurs coûts qui sont appliqués à la zone de coût du voyage. Cette fonctionnalité est prise en charge par l’entité `ITMLedgerJournalCostLinesVoyagesEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Montant réparti | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | N° | N° |
| Numéro de ligne de la transaction de coût | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Oui** | N° |
| Nombre de lignes du journal | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Oui** | N° |
| Numéro de journal | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Oui** | N° |
| Voyage | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Oui** | N° |

## <a name="vendor-shipping-container-cost-allocations-itmledgerjournalcostlinescontainersentity"></a>Répartition des coûts des conteneurs d’expédition du fournisseur (ITMLedgerJournalCostLinesContainersEntity)

L’entité de données de répartition des coûts du conteneur d’expédition du fournisseur permet à une ligne de facture fournisseur d’être répartie sur un ou plusieurs coûts qui sont appliqués à la zone de coût du conteneur d’expédition. Cette fonctionnalité est prise en charge par l’entité `ITMLedgerJournalCostLinesContainersEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Montant réparti | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | N° | N° |
| Conteneur d’expédition | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Oui** | N° |
| Numéro de ligne de la transaction de coût | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Oui** | N° |
| Nombre de lignes du journal | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Oui** | N° |
| Numéro de journal | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Oui** | N° |
| Voyage | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Oui** | N° |

## <a name="vendor-folio-cost-allocations-itmledgerjournalcostlinesfoliosentity"></a>Répartition des coûts de folio du fournisseur (ITMLedgerJournalCostLinesFoliosEntity)

L’entité de données de répartition des coûts de folio du fournisseur permet à une ligne de facture fournisseur d’être répartie sur un ou plusieurs coûts qui sont appliqués à la zone de coût du folio. Cette fonctionnalité est prise en charge par l’entité `ITMLedgerJournalCostLinesFoliosEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Montant réparti | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | N° | N° |
| Numéro de ligne de la transaction de coût | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Oui** | N° |
| Folio | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Oui** | N° |
| Nombre de lignes du journal | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Oui** | N° |
| Numéro de journal | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Oui** | N° |

## <a name="vendor-purchase-order-cost-allocations-itmledgerjournalcostlinespurchtableentity"></a>Répartition des coûts de bon de commande fournisseur (ITMLedgerJournalCostLinesPurchTableEntity)

L’entité de données de répartition des coûts de commande fournisseur permet à une ligne de facture fournisseur d’être répartie sur un ou plusieurs coûts qui sont appliqués à la zone de coût de commande fournisseur. Cette fonctionnalité est prise en charge par l’entité `ITMLedgerJournalCostLinesPurchTableEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Montant réparti | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | N° | N° |
| Numéro de ligne de la transaction de coût | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Oui** | N° |
| Nombre de lignes du journal | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Oui** | N° |
| Numéro de journal | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Oui** | N° |
| Commande fournisseur | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Oui** | N° |

## <a name="vendor-item-cost-allocations-itmledgerjournalcostlinespurchlineentity"></a>Répartition des coûts d’article du fournisseur (ITMLedgerJournalCostLinesPurchLineEntity)

L’entité de données de répartition des coûts d’article du fournisseur permet à une ligne de facture fournisseur d’être répartie sur un ou plusieurs coûts qui sont appliqués à la zone de coût d’article. La zone de coût de l’article couvre les coûts de la ligne de commande fournisseur. Cette fonctionnalité est prise en charge par l’entité `ITMLedgerJournalCostLinesPurchLineEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Montant réparti | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | N° | N° |
| Numéro de ligne de la transaction de coût | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Oui** | N° |
| Nombre de lignes du journal | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Oui** | N° |
| Numéro de journal | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Oui** | N° |
| Commande fournisseur | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Oui** | N° |
| Numéro de ligne de commande fournisseur | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Oui** | N° |

## <a name="vendor-transfer-order-line-cost-allocations-itmledgerjournalcostlinestransferlineentity"></a>Répartition des coûts de ligne d’ordre de transfert fournisseur (ITMLedgerJournalCostLinesTransferLineEntity)

L’entité de données de répartition des coûts de ligne d’ordre de transfert fournisseur permet à une ligne de facture fournisseur d’être répartie sur un ou plusieurs coûts qui sont appliqués à la zone de coût de ligne d’ordre de transfert. Cette fonctionnalité est prise en charge par l’entité `ITMLedgerJournalCostLinesTransferLineEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Montant réparti | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | N° | N° |
| Numéro de ligne de la transaction de coût | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Oui** | N° |
| Nombre de lignes du journal | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Oui** | N° |
| Numéro de journal | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Oui** | N° |
| Ordre de transfert | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Oui** | N° |
| Numéro de ligne d’ordre de transfert | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Oui** | N° |

### <a name="reference-table"></a>Table de référence

Les lignes de coût de voyage ont une association directe avec un enregistrement de transaction de coût. Ce dossier comprend la valeur **ID de la table de référence**. Cette valeur est unique pour chaque zone de coût (voyage, conteneur d’expédition, etc.). Lorsque des numéros de table spécifiques sont référencés pour des données créées à l’aide d’entités de données, les entités sont divisées en fonction des valeurs **ID de la table de référence**.

Les valeurs de la table de référence (`RefTableId`) et le type de transaction (`TransType`) sont implicites dans la sélection de l’entité de ligne d’achat au coût d’approche ou de ligne de transfert du coût d’approche.

## <a name="vendor-invoice-journal-lines-vendorinvoicejournallineentity"></a>Lignes de journal des factures fournisseur (VendorInvoiceJournalLineEntity)

Avant qu’une valeur de ligne de journal puisse être affectée à un ou plusieurs coûts dans le module **Prix au débarquement**, la ligne journal doit être associée à une zone de coût. Pour prendre en charge cette fonctionnalité, le module **Prix au débarquement** ajoute de nouveaux champs à la table des lignes de journal (`LedgerJournalTrans`).

### <a name="fields-added-to-the-vendor-invoice-journal-line-entity"></a>Champs ajoutés à l’entité de ligne de journal de facture fournisseur

Le tableau suivant répertorie les champs que le module **Prix au débarquement** ajoute à l’entité de la ligne de journal de la facture fournisseur (`VendorInvoiceJournalLineEntity`). Ces champs permettent au système de créer des lignes de journal et d’allouer des coûts à celles-ci.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Zone de coût | LedgerJournalTrans.ITMCostArea | Int | N° | N° |
| Code de type de coût | LedgerJournalTrans.ITMCostTypeId | Nvarchar(20) | N° | N° |

### <a name="mainoffset-account"></a>Compte principal/de contrepartie

Le compte principal/de contrepartie d’une ligne de journal de facture associée à un voyage à frais débarqués est déterminé par le code de type de coût. Lorsque le code type de coût est inclus sur la ligne journal facture, le compte d’attente pour le code sera utilisé comme compte principal ou compte de contrepartie, selon le scénario :

- **Journal à une seule ligne** – Si un compte principal (en d’autres termes, le compte fournisseur) est défini et qu’un code de type de coût est fourni, la valeur du compte de compensation pour ce code de type de coût sera saisie dans le compte de contrepartie.
- **Journal à plusieurs lignes** – Si un compte principal n’est pas défini, mais un code de type de coût est fourni, la valeur du compte de compensation pour ce code de type de coût sera saisie dans le compte principal. La ligne de journal qui crédite le fournisseur ne fera pas référence à un code de type de coût.

## <a name="sequencing"></a>Séquençage

En raison des dépendances entre le journal et les tables de lignes de journal, l’enregistrement du voyage doit être créé en premier. Les lignes de voyage ne peut être créée qu’après la création du voyage, du conteneur d’expédition et des folios.

Pour allouer une facture de voyage, le système doit traiter les entités dans l’ordre suivant :

1. En-tête de journal des factures (`VendInvoiceJournalHeaderEntity`)
1. Ligne de journal des factures (`VendInvoiceJournalLineEntity`)
1. Répartitions des coûts au débarquement (`ITMLedgerJournalEntities`)
