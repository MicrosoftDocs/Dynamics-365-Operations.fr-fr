---
title: Entités de transaction de coût
description: Cet article fournit des informations sur les entités de transaction de coût, qui permettent de répartir la valeur d’un coût entre le contenu d’une zone de coût via la sélection d’une méthode de répartition.
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
ms.openlocfilehash: 3aabc1356eba27de797fa696dd928cb401d8501b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860810"
---
# <a name="cost-transaction-entities"></a>Entités de transaction de coût

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

## <a name="apportionment"></a>Répartition

Le coût au débarquement permet de répartir la valeur d’un coût entre le contenu d’une zone de coût (voyage, conteneur d’expédition, etc.) via la sélection d’une méthode de répartition. La méthode de répartition est définie dans le cadre de la configuration des coûts automatiques basée sur des règles métier. Cela fait partie du coût lorsqu’une ligne de voyage est créée.

### <a name="configure-the-apportionment-mapping-for-use-with-data-entities"></a>Configurer le mappage de répartition à utiliser avec les entités de données

Lorsqu’un coût est créé à partir d’une source externe telle qu’un transitaire, cette source externe ne peut pas spécifier la méthode préférée pour répartir la valeur du coût. Le mappage de répartition définit la méthode de répartition par défaut pour chaque code de type de coût. La table de mappage des répartitions est accessible à partir de la page **Mappage de répartition** dans Microsoft Dynamics 365 Supply Chain Management (**Coût au débarquement \> Configuration des coûts \> Mappage de répartition**).

Si une combinaison de mappage a été définie et qu’un coût correspondant au code de type de coût est créé à l’aide d’une entité de transaction de coût, la méthode de répartition mappée sera utilisée à la place de toute valeur fournie à l’entité.

Si aucune valeur n’est présente dans la table de mappage, mais qu’une valeur a été fournie à l’entité, la valeur fournie sera utilisée.

Si aucune valeur n’existe dans la table de mappage ou dans l’enregistrement qui a été soumis à l’entité, la création échouera.

### <a name="apportionment-mapping-itmapportionmentmapping"></a>Mise en correspondance des méthodes de répartition (ITMApportionmentMapping)

L’entité de mappage de répartition (`ITMApportionmentMapping`) crée des relations de mappage de répartition et permet aux utilisateurs de créer ou de mettre à jour des enregistrements.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Méthode de répartition | ITMApportionmentMapping.ApportionmentMethod | Int | N° | N° |
| Code de type de coût | ITMApportionmentMapping.ShipCostTypeId | Nvarchar(20) | **Oui** | N° |

## <a name="voyage-costs-itmcosttransvoyageentity"></a>Frais de déplacement (ITMCostTransVoyageEntity)

L’entité de coût du voyage (`ITMCostTransVoyageEntity`) crée des transactions de coût de voyage qui sont appliquées au niveau du voyage. Pendant le processus d’importation, le système utilise les valeurs **Catégorie** et **Méthode de répartition** qui sont incluses dans l’entité pour déterminer comment la valeur du coût est répartie sur le contenu du voyage.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Méthode de répartition | ITMCostTrans.ApportionmentMethod | Int | N° | N° |
| Coût | ITMCostTrans.CostValue | Numeric(32, 6) | N° | N° |
| Devise | ITMCostTrans.CurrencyCode | Nvarchar(3) | N° | **Oui** |
| Numéro de la ligne | ITMCostTrans.LineNum | Numeric(32, 16) | **Oui** | N° |
| Type de coût lié | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | N° | N° |
| Coût minimal | ITMCostTrans.MinCostAmount | Numeric(32, 6) | N° | N° |
| Catégorie | ITMCostTrans.ShipCostCategory | Int | N° | N° |
| Code de type de coût | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | N° | N° |
| Société | ITMCostTrans.ShipDataArea | Nvarchar(4) | N° | **Oui** |
| Voyage | ITMCostTrans.TransRecId | Nvarchar(20) | **Oui** | N° |
| Groupe de taxe d’article | ITMCostTrans.TaxItemGroup | Nvarchar(10) | N° | N° |

## <a name="shipping-container-costs-itmcosttransshippingcontainerentity"></a>Coûts du conteneur d’expédition (ITMCostTransShippingContainerEntity)

L’entité de coût du conteneur d’expédition (`ITMCostTransShippingContainerEntity`) crée des coûts de conteneur d’expédition qui sont appliqués au niveau du conteneur d’expédition. Pendant le processus d’importation, le système utilise les valeurs **Catégorie** et **Méthode de répartition** qui sont incluses dans l’entité pour déterminer comment la valeur du coût est répartie sur le contenu d’expédition.

Les champs **Agrégat**, **Étape** et **Étape liée** sont spécifiques aux enregistrements où la valeur **Zone de coût** est *Conteneur d’expédition*. Par conséquent, ils ne sont pas présents dans les entités de données pour les autres zones de coût.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Regroupement | ITMCostTrans.AggregatedCost | Int | N° | N° |
| Méthode de répartition | ITMCostTrans.ApportionmentMethod | Int | N° | N° |
| Coût | ITMCostTrans.CostValue | Numeric(32, 6) | N° | N° |
| Devise | ITMCostTrans.CurrencyCode | Nvarchar(3) | N° | **Oui** |
| Numéro de la ligne | ITMCostTrans.LineNum | Numeric(32, 16) | **Oui** | N° |
| Type de coût lié | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | N° | N° |
| Étape liée | ITMCostTrans.LinkLegId | Nvarchar(20) | N° | N° |
| Coût minimal | ITMCostTrans.MinCostAmount | Numeric(32, 6) | N° | N° |
| Conteneur d’expédition | ITMCostTrans.TransRecId | Nvarchar(20) | **Oui** | N° |
| Catégorie | ITMCostTrans.ShipCostCategory | Int | N° | N° |
| Code de type de coût | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | N° | N° |
| Société | ITMCostTrans.ShipDataArea | Nvarchar(4) | N° | **Oui** |
| Voyage | ITMCostTrans.TransRecId | Nvarchar(20) | **Oui** | N° |
| Étape | ITMCostTrans.ShipLegId | Nvarchar(20) | N° | N° |
| Groupe de taxe d’article | ITMCostTrans.TaxItemGroup | Nvarchar(10) | N° | N° |

## <a name="folio-costs-itmcosttransfolioentity"></a>Coûts folio (ITMCostTransFolioEntity)

L’entité de coût du folio (`ITMCostTransFolioEntity`) crée des enregistrements de transaction de coût qui s’appliquent au niveau du folio. Pendant le processus d’importation, le système utilise les valeurs **Catégorie** et **Méthode de répartition** qui sont incluses dans l’entité pour déterminer comment la valeur du coût est répartie sur chaque folio.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Méthode de répartition | ITMCostTrans.ApportionmentMethod | Int | N° | N° |
| Coût | ITMCostTrans.CostValue | Numeric(32, 6) | N° | N° |
| Devise | ITMCostTrans.CurrencyCode | Nvarchar(3) | N° | **Oui** |
| Numéro de la ligne | ITMCostTrans.LineNum | Numeric(32, 16) | **Oui** | N° |
| Type de coût lié | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | N° | N° |
| Coût minimal | ITMCostTrans.MinCostAmount | Numeric(32, 6) | N° | N° |
| Catégorie | ITMCostTrans.ShipCostCategory | Int | N° | N° |
| Code de type de coût | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | N° | N° |
| Société | ITMCostTrans.ShipDataArea | Nvarchar(4) | N° | **Oui** |
| Folio | ITMCostTrans.TransRecId | Nvarchar(20) | **Oui** | N° |
| Groupe de taxe d’article | ITMCostTrans.TaxItemGroup | Nvarchar(10) | N° | N° |

## <a name="purchase-order-costs-itmcosttranspurchaseentity"></a>Coûts de la commande d’achat (ITMCostTransPurchaseEntity)

L’entité de coût du bon de commande (`ITMCostTransPurchaseEntity`) crée des transactions de coût qui s’appliquent à l’en-tête de la commande de l’acheteur. Pendant le processus d’importation, le système utilise les valeurs **Catégorie** et **Méthode de répartition** qui sont incluses dans l’entité pour déterminer comment la valeur du coût est répartie sur chaque folio.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Méthode de répartition | ITMCostTrans.ApportionmentMethod | Int | N° | N° |
| Coût | ITMCostTrans.CostValue | Numeric(32, 6) | N° | N° |
| Devise | ITMCostTrans.CurrencyCode | Nvarchar(3) | N° | **Oui** |
| Numéro de la ligne | ITMCostTrans.LineNum | Numeric(32, 16) | **Oui** | N° |
| Type de coût lié | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | N° | N° |
| Coût minimal | ITMCostTrans.MinCostAmount | Numeric(32, 6) | N° | N° |
| Commande fournisseur | ITMCostTrans.TransRecId | Nvarchar(20) | **Oui** | N° |
| Catégorie | ITMCostTrans.ShipCostCategory | Int | N° | N° |
| Code de type de coût | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | N° | N° |
| Société | ITMCostTrans.ShipDataArea | Nvarchar(4) | N° | **Oui** |
| Groupe de taxe d’article | ITMCostTrans.TaxItemGroup | Nvarchar(10) | N° | N° |

## <a name="item-costs-itmcosttransitementity"></a>Coûts des articles (ITMCostTransItemEntity)

L’entité de coût de l’article (`ITMCostTransItemEntity`) crée des enregistrements de coût qui s’appliquent au niveau de l’article. Cette entité est spécifique aux articles des lignes de commande fournisseur. La valeur du coût est appliquée intégralement à la ligne.

Les champs **Montant de l’ajustement** et **Ajustement de la valeur** sont spécifiques aux zones de coûts de niveau ligne. Par conséquent, ils ne sont pas présents dans les entités de données pour les autres zones de coût.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Montant d’ajustement | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | N° | N° |
| Coût | ITMCostTrans.CostValue | Numeric(32, 6) | N° | N° |
| Devise | ITMCostTrans.CurrencyCode | Nvarchar(3) | N° | **Oui** |
| Numéro de la ligne | ITMCostTrans.LineNum | Numeric(32, 16) | **Oui** | N° |
| Type de coût lié | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | N° | N° |
| Coût minimal | ITMCostTrans.MinCostAmount | Numeric(32, 6) | N° | N° |
| Commande fournisseur | ITMCostTrans.TransRecId | Nvarchar(20) | **Oui** | N° |
| Numéro de ligne de commande fournisseur | ITMCostTrans.TransRecId | Nvarchar(20) | **Oui** | N° |
| Catégorie | ITMCostTrans.ShipCostCategory | Int | N° | N° |
| Code de type de coût | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | N° | N° |
| Société | ITMCostTrans.ShipDataArea | Nvarchar(4) | N° | **Oui** |
| Groupe de taxe d’article | ITMCostTrans.TaxItemGroup | Nvarchar(10) | N° | N° |
| Ajustement de valeur | ITMCostTrans.ValueAdjustmentMethod | Int | N° | N° |

## <a name="transfer-line-costs-itmcosttranstransferlineentity"></a>Coûts de la ligne de transfert (ITMCostTransTransferLineEntity)

L’entité de coût de la ligne de transfert (`ITMCostTransTransferLineEntity`) crée des transactions de coûts qui s’appliquent au niveau de la ligne d’ordre de transfert. La valeur de ces coûts est appliquée intégralement à la ligne d’ordre de transfert.

Les champs **Montant de l’ajustement** et **Ajustement de la valeur** sont spécifiques aux zones de coûts de niveau ligne. Par conséquent, ils ne sont pas présents dans les entités de données pour les autres zones de coût.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Montant d’ajustement | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | N° | N° |
| Coût | ITMCostTrans.CostValue | Numeric(32, 6) | N° | N° |
| Devise | ITMCostTrans.CurrencyCode | Nvarchar(3) | N° | **Oui** |
| Numéro de la ligne | ITMCostTrans.LineNum | Numeric(32, 16) | **Oui** | N° |
| Type de coût lié | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | N° | N° |
| Coût minimal | ITMCostTrans.MinCostAmount | Numeric(32, 6) | N° | N° |
| Catégorie | ITMCostTrans.ShipCostCategory | Int | N° | N° |
| Code de type de coût | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | N° | N° |
| Société | ITMCostTrans.ShipDataArea | Nvarchar(4) | N° | **Oui** |
| Ordre de transfert | ITMCostTrans.TransRecId | Nvarchar(20) | **Oui** | N° |
| Numéro de ligne d’ordre de transfert | ITMCostTrans.TransRecId | Nvarchar(20) | **Oui** | N° |
| Groupe de taxe d’article | ITMCostTrans.TaxItemGroup | Nvarchar(10) | N° | N° |
| Ajustement de valeur | ITMCostTrans.ValueAdjustmentMethod | Int | N° | N° |

### <a name="transaction-table"></a>Table de transaction

Un enregistrement de transaction de coût est associé à une zone de coût via l’attribution d’un numéro de table de transaction (`TransTableId`). Lorsque des numéros d’identification de table spécifiques sont requis, les entités sont fractionnées en fonction de ces valeurs, de sorte qu’une entité existe pour chaque zone de coût.

La valeur de la table des transactions (`TransTableId`) est implicite dans la sélection de l’entité de transaction de coût.

### <a name="calculated-fields"></a>Champs calculés

Les champs suivants ne peuvent pas être insérés ou mis à jour lorsqu’une entité de transaction de coût est utilisée, car ces champs ne sont définis que lorsque des actions spécifiques sont entreprises sur l’enregistrement du voyage :

- **Coût estimé** – Ce champ est renseigné lorsqu’une facture est enregistrée pour le voyage (bon de commande) ou qu’un virement est reçu.
- **Devise du coût estimé** – Ce champ est renseigné lorsqu’une facture est enregistrée pour le voyage (bon de commande) ou qu’un virement est reçu.
- **Prix actuel** – Ce champ est défini lorsqu’une facture fournisseur est validée. C’est lié au coût.

### <a name="find-auto-costs"></a>Rechercher des coûts auto

Un bouton **Rechercher des coûts auto** disponible pour chaque zone de coût (voyage, conteneur d’expédition, etc.) permet de mettre à jour les transactions de coût pour cette zone de coût à partir des informations des tables de configuration. Lorsque vous sélectionnez le bouton d’une zone de coût, le système efface les coûts existants pour cette zone de coût et crée de nouveaux enregistrements, en fonction de la configuration actuelle des tables de configuration des coûts automatiques.

Les enregistrements de transaction de coût créés à l’aide d’une entité de données sont marqués comme importés. Ces enregistrements ne sont pas supprimés lorsque vous sélectionnez **Trouver les frais d’automobile**, car ils ne seront pas recréés à partir des tables de configuration des coûts automatiques. Cependant, un enregistrement de transaction de coût marqué comme importé peut toujours être supprimé.

### <a name="linked-fields"></a>Champs liés

Chaque transaction de coût peut être associée à un autre enregistrement dans la même zone de coût. Cette association est constituée par le champ **Type de coût lié**. Il permet de calculer une valeur de coût en pourcentage d’un autre coût.

Le champ **Type de coût lié** ne peut être validé que si l’enregistrement référencé est traité en premier ou s’il existe déjà dans la table. La même exigence s’applique au champ **Étape liée** utilisé pour les coûts dans la zone de coût du conteneur d’expédition uniquement.
