---
title: Affecter des icônes et des titres d’étape pour l’application mobile Warehouse Management
description: Cette rubrique décrit comment affecter des icônes et des titres d’étape pour les flux de tâches nouveaux ou personnalisés pour l’application mobile Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9523492d766669e6c38579fba7b5ddd6b3d282fc
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049362"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a>Affecter des icônes et des titres d’étape pour l’application mobile Warehouse Management

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment affecter des icônes d’étape et des titres d’étape pour les flux de tâches nouveaux ou personnalisés pour l’application mobile Warehouse Management.

Les illustrations suivantes montrent comment les icônes et les titres d’étape apparaissent dans l’application mobile Warehouse Management.

![Exemple d’une icône d’étape et d’un titre d’étape dans l’application mobile Warehouse Management](media/step-icon-example.png "Exemple d’une icône d’étape et d’un titre d’étape dans l’application mobile Warehouse Management")

## <a name="turn-on-this-feature-in-your-system"></a>Activer cette fonctionnalité dans votre système

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Paramètres utilisateur, icônes et titres des étapes de la nouvelle application d’entrepôt*

## <a name="standard-step-ids-classes-and-icons"></a>ID, classes et icônes d’étape standard

Chaque étape d’un flux de tâches est identifiée par un ID d’étape, et chaque ID d’étape a une classe d’étape correspondante. L’icône et le titre de l’étape sont spécifiés dans chaque classe d’étape.

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a>ID d’étape et classes d’étape

Le tableau suivant répertorie chaque ID d’étape actuellement disponible et sa classe d’étape correspondante. Le nom de contrôle du champ de saisie principal est utilisé comme ID d’étape.

Pour obtenir un exemple qui montre comment ces ID et classes d’étape sont utilisés, consultez l’implémentation de la méthode `WHSMobileAppStepInfoBuilder.stepId()` dans la section [Exemple : affecter des icônes et des titres d’étape pour un flux personnalisé](#example) plus loin dans cette rubrique.

| ID d’étape | Classe d’étape |
|-|-|
| BatchDisposition | WHSMobileAppStepBatchDisposition |
| Transporteur | WHSMobileAppStepCarrier |
| CatchWeight | WHSMobileAppStepCatchWeight |
| CatchWeightQtyOutboundWeight | WHSMobileAppStepCatchWeight |
| CatchWeightTag | WHSMobileAppStepCatchWeightTag |
| CatchWeightTagWeight | WHSMobileAppStepCatchWeightTagWeight |
| ChangeWarehouseSuccess | WHSMobileAppStepChangeWarehouseSuccess |
| CheckDigit | WHSMobileAppStepCheckDigit |
| ClusterId | WHSMobileAppStepClusterId |
| ClusterPickQtyVerification | WHSMobileAppStepQtyVerification |
| ClusterPosition | WHSMobileAppStepClusterPosition |
| ConfigId | WHSMobileAppStepConfigId |
| Confirmation | WHSMobileAppStepConfirmation |
| ConsolidateFromLicensePlateId | WHSMobileAppStepConsolidateFromLicensePlateId |
| ConsolidateLPConfirmation | WHSMobileAppStepConsolidateLPConfirmation |
| ConsolidateToLicensePlateId | WHSMobileAppStepConsolidateToLicensePlateId |
| ContainerType | WHSMobileAppStepContainerType |
| CountingReasonCode | WHSMobileAppStepCountingReasonCode |
| CycleCountingAddLPOrFinish | WHSMobileAppStepCycleCountingAddLPOrFinish |
| CycleCountQty1 | WHSMobileAppStepCycleCountQty |
| CycleCountQty2 | WHSMobileAppStepCycleCountQty |
| CycleCountQty3 | WHSMobileAppStepCycleCountQty |
| CycleCountQty4 | WHSMobileAppStepCycleCountQty |
| Disposition | WHSMobileAppStepDisposition |
| DriverCheckInConfirmation | WHSMobileAppStepDriverCheckInConfirmation |
| DriverCheckInId | WHSMobileAppStepDriverCheckInId |
| DriverCheckOutConfirmation | WHSMobileAppStepDriverCheckOutConfirmation |
| DriverCheckOutId | WHSMobileAppStepDriverCheckOutId |
| ExpDate | WHSMobileAppStepExpDate |
| FromBatchDisposition | WHSMobileAppStepFromBatchDisposition |
| FromInventoryStatus | WHSMobileAppStepInventoryStatusFrom |
| FullQty | WHSMobileAppStepFullQty |
| InboundPut | WHSMobileAppStepInboundPut |
| InventBatchId | WHSMobileAppStepBatch |
| InventColorId | WHSMobileAppStepInventColorId |
| InventLocation | WHSMobileAppStepInventLocation |
| InventLocationId | WHSMobileAppStepWarehouse |
| InventSerialId | WHSMobileAppStepInventSerialId |
| InventSizeId | WHSMobileAppStepInventSizeId |
| InventStatusId | WHSMobileAppStepInventStatus |
| InventStyleId | WHSMobileAppStepInventStyleId |
| InventVersionId | WHSMobileAppStepInventVersionId |
| ItemId | WHSMobileAppStepItem |
| ITMContainerID | ITMMobileAppStepContainerId |
| ITMShipmentID | ITMMobileAppStepShipmentId |
| KanbanCardId | WHSMobileAppStepKanbanCard |
| KanbanCardToEmpty | WHSMobileAppStepKanbanCardToEmpty |
| KanbanOrCardId | WHSMobileAppStepKanbanCard |
| LicensePlateId | WHSMobileAppStepLicensePlate |
| LoadId | WHSMobileAppStepLoadId |
| LocationLicensePlatePosition | WHSMobileAppStepLocationLicensePlatePosition |
| LocOrLP | WHSMobileAppStepLocOrLP |
| LocOrLP_From | WHSMobileAppStepLocOrLPFrom |
| LocOrLP_To | WHSMobileAppStepLocOrLPTo |
| LocOrLPCheck | WHSMobileAppStepLocOrLPCheck |
| LocVerification | WHSMobileAppStepLocVerification |
| LPAdjustIn | WHSMobileAppStepLPAdjustIn |
| LPBreakChildLP | WHSMobileAppStepLPBreakChildLP |
| LPBreakParentLP | WHSMobileAppStepLPBreakParentLP |
| LPBuildChildLP | WHSMobileAppStepLPBuildChildLP |
| LPBuildParentLP | WHSMobileAppStepLPBuildParentLP |
| LPVerification | WHSMobileAppStepLPVérification |
| MergeContainerId | WHSMobileAppStepMergeContainerId |
| MixedLPLineNum | WHSMobileAppStepMixedLPLineNum |
| MobileDeviceQueueMessageCollectionIdentifierId | WHSMobileAppStepSelectOrder |
| MovementConfirmCancel | WHSMobileAppStepMovementConfirmCancel |
| NewCaptureWeight | WHSMobileAppStepCatchWeight |
| NewQty | WHSMobileAppStepNewQty |
| OutboundCatchWeightTag | WHSMobileAppStepCatchWeightTag |
| OutboundPut | WHSMobileAppStepOutboundPut |
| OutboundWeight | WHSMobileAppStepCatchWeight |
| OverridePutNewLocation | WHSMobileAppStepOverridePutNewLocation |
| PieceByPieceConfirmation | WHSMobileAppStepQtyVerification |
| POLineNum | WHSMobileAppStepPOLineNum |
| N° commande | WHSMobileAppStepPONum |
| PositionFull | WHSMobileAppStepPositionFull |
| PositionFullQty | WHSMobileAppStepPositionFullQty |
| Concentration | WHSMobileAppStepPotency |
| PrinterName | WHSMobileAppStepPrinterName |
| ProdId | WHSMobileAppStepProdId |
| ProdLastPalletConfirmation | WHSMobileAppStepProdLastPalletConfirmation |
| ProductConfirmation | WHSMobileAppStepProductConfirmation |
| ProductionScrapConfirmation | WHSMobileAppStepProductionScrapConfirmation |
| Placer | WHSMobileAppStepPut |
| PutawayClusterId | WHSMobileAppStepPutawayClusterId |
| Qté | WHSMobileAppStepQty |
| QtyAdjust | WHSMobileAppStepQtyAdjust |
| QtyShort | WHSMobileAppStepQtyShort |
| QtyToConsume | WHSMobileAppStepQtyToConsume |
| QtyToPick | WHSMobileAppStepQtyToPick |
| QtyToPut | WHSMobileAppStepQtyToPut |
| QtyToScrap | WHSMobileAppStepQtyToScrap |
| QtyVerification | WHSMobileAppStepQtyVerification |
| QtyWithScanningLimit | WHSMobileAppStepQtyAdjust |
| ReasonString | WHSMobileAppStepReasonString |
| RecvLocationId | WHSMobileAppStepRecvLocationId |
| RemoveContainerId | WHSMobileAppStepRemoveContainerId |
| ReprintLabelConfirmation | WHSMobileAppStepReprintLabelConfirmation |
| RMANum | WHSMobileAppStepRMANum |
| ShortPickReason | WHSMobileAppStepShortPickReason |
| SortConOrLP | WHSMobileAppStepSortConOrLP |
| SortLicensePlateId | WHSMobileAppStepSortLicensePlateId |
| SortPositionId | WHSMobileAppStepSortPositionId |
| SortVerification | WHSMobileAppStepSortVérification |
| StartLocationId | WHSMobileAppStepStartLocationId |
| StartProdOrderConfirmation | WHSMobileAppStepStartProdOrderConfirmation |
| TargetLicensePlateId | WHSMobileAppStepTargetLicensePlateId |
| TOLineNum | WHSMobileAppStepTOLineNum |
| ToLocation | WHSMobileAppStepToLocation |
| TONum | WHSMobileAppStepTONum |
| ToWarehouse | WHSMobileAppStepWarehouseTo |
| TransportLoadId | WHSMobileAppStepTransportLoadId |
| WaveLabelId | WHSMobileAppStepWaveLabelId |
| WaveLblQty | WHSMobileAppStepWaveLblQty |
| Pondération | WHSMobileAppStepWeight |
| WeightToConsume | WHSMobileAppStepWeightToConsume |
| WHSAdjustmentType | WHSMobileAppStepWHSAdjustmentType |
| WHSReceivingException | WHSMobileAppStepWHSReceivingException |
| WHSWorkException | WHSMobileAppStepWHSWorkException |
| WHSWorkLicensePlateId | WHSMobileAppStepWorkLicensePlateId |
| WMSLocationId | WHSMobileAppStepLocation |
| WorkId | WHSMobileAppStepWorkId |
| WorkIdToCancel | WHSMobileAppStepWorkIdToCancel |
| WorkLPIdPutawayCluster | WHSMobileAppStepWorkLPIdPutawayCluster |
| WorkPoolId | WHSMobileAppStepWorkPoolId |
| ZoneId | WHSMobileAppStepZoneId |

### <a name="available-step-icons"></a><a name="step-icons"></a>Icônes d’étape disponibles

Le système comprend une collection d’icônes d’étape standard que vous pouvez également utiliser pour vos étapes personnalisées. Vous ne pouvez pas actuellement charger des icônes d’étape personnalisées. Par conséquent, vous devez toujours sélectionner l’une des icônes d’étape standard.

Le tableau suivant présente chaque icône d’étape standard actuellement disponible et son nom.

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Icône d’étape À propos"><br>À propos</td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Icône d’étape Ajouter un contenant ou un article"><br>AddLpOrItem</td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Icône d’étape Disposition de lot"><br>BatchDisposition</td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Icône d’étape Transporteur"><br>Transporteur</td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Icône d’étape Balise de poids variable"><br>CatchWeightTag</td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Icône d’étape Poids de la balise de poids variable"><br>CatchWeightTagWeight</td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Icône d’étape Chiffre de contrôle"><br>CheckDigit</td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Icône d’étape ID de vérification à l’entrée et à la sortie"><br>CheckInOutId</td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Icône d’étape Contenant enfant"><br>ChildLP</td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Icône d’étape ID de cluster"><br>ClusterId</td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Icône d’étape Position du cluster"><br>ClusterPosition</td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Icône d’étape ID de configuration"><br>ConfigId</td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Icône d’étape Champ configuré"><br>ConfiguredField</td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Icône d’étape Conteneur ou contenant"><br>ConOrLP</td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Icône d’étape Consolider à partir de l’ID de contenant"><br>ConsolidateFromLicensePlateID</td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Icône d’étape Consolider sur l’ID de contenant"><br>ConsolidateToLicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Icône d’étape Type de conteneur"><br>ContainerType</td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Icône d’étape Inventaire"><br>Comptage</td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Icône d’étape Code motif d’inventaire"><br>CountingReasonCode</td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Icône d’étape Code pays d’origine"><br>CountryOfOrigin</td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Icône d’étape Disposition"><br>Disposition</td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Icône d’étape Terminé"><br>Terminé</td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Icône d’étape Confirmation de la vérification à l’arrivée du chauffeur"><br>DriverCheckInConfirmation</td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Icône d’étape ID de vérification à l’arrivée du chauffeur"><br>DriverCheckInId</td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Icône d’étape ID de vérification au départ du chauffeur"><br>DriverCheckOutId</td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Icône d’étape Date d’expiration"><br>ExpDate</td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Icône d’étape Champ"><br>Champ</td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Icône d’étape À partir de la disposition de lot"><br>FromBatchDisposition</td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Icône d’étape À partir du statut du stock"><br>FromInventoryStatus</td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Icône d’étape ID d’attribut"><br>IdAttribute</td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Icône d’étape ID de traitement par lots du stock"><br>InventBatchID</td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Icône d’étape ID de couleur du stock"><br>InventColorID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Icône d’étape Emplacement du stock"><br>InventLocation</td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Icône d’étape ID de série du stock"><br>InventSerialID</td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Icône d’étape ID de taille du stock"><br>InventSizeID</td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Icône d’étape ID de statut du stock"><br>InventStatusID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Icône d’étape ID de style du stock"><br>InventStyleID</td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Icône d’étape ID de version du stock"><br>InventVersionID</td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Icône d’étape ID d’article"><br>ItemID</td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Icône d’étape ID de conteneur ITM"><br>ITMContainerID</td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Icône d’étape ID d’expédition ITM"><br>ITMShipmentID</td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Icône d’étape ID de carte kanban"><br>KanbanCardID</td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Icône d’étape ID de kanban ou de carte"><br>KanbanOrCardID</td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Icône d’étape ID de contenant"><br>LicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Icône d’étape ID de chargement"><br>LoadId</td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Icône d’étape Position de l’emplacement ou du contenant"><br>LocationLicensePlatePosition</td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Icône d’étape Emplacement ou contenant"><br>LocOrLP</td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Icône d’étape Vérification de l’emplacement ou du contenant"><br>LocOrLPCheck</td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Icône d’étape À partir de l’emplacement ou du contenant"><br>LocOrLPFrom</td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Icône d’étape Vers l’emplacement ou le contenant"><br>LocOrLPTo</td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Icône d’étape Long processus terminé"><br>LongProcessCompleted</td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Icône d’étape Décomposer le contenant parent en contenants"><br>LPBreakParentLP</td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Icône d’étape Fusionner l’ID de conteneur"><br>MergeContainerId</td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Icône d’étape Numéro de ligne de contenant mixte"><br>MixedLPLineNum</td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Icône d’étape Poids sortant"><br>OutboundWeight</td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Icône d’étape Propriétaire"><br>Propriétaire</td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Icône d’étape Contenant parent"><br>ParentLP</td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Icône d’étape Veuillez confirmer"><br>PleaseConfirm</td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Icône d’étape Numéro de ligne de commande fournisseur"><br>POLineNum</td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Icône d’étape Numéro de commande fournisseur"><br>N° commande</td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Icône d’étape Poste complet"><br>PositionFull</td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Icône d’étape Potence"><br>Concentration</td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Icône d’étape Nom de l’imprimante"><br>PrinterName</td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Icône d’étape ID de production"><br>ProdId</td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Icône d’étape Confirmation du produit"><br>ProductConfirmation</td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Icône d’étape Stockage"><br>Placer</td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Icône d’étape ID de cluster de stockage"><br>PutawayClusterId</td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Icône d’étape Quantité"><br>Qté</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Icône d’étape Ajuster la quantité dans"><br>QtyAdjustIn</td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Icône d’étape Quantité partielle"><br>QtyShort</td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Icône d’étape Quantité à consommer"><br>QtyToConsume</td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Icône d’étape Quantité à stocker"><br>QtyToPut</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Icône d’étape Quantité à mettre au rebut"><br>QtyToScrap</td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Icône d’étape Confirmation de la quantité"><br>QuantityConfirmation</td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Icône d’étape Déclarer la tâche comme terminée"><br>RAFEndJob</td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Icône d’étape ID de l’emplacement de réception"><br>RecvLocationID</td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Icône d’étape Supprimer l’ID de conteneur"><br>RemoveContainerID</td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Icône d’étape Numéro RMA"><br>RMANum</td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Icône d’étape Sélectionner une commande"><br>SelectOrder</td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Icône d’étape Motif de prélèvement partiel"><br>ShortPickReason</td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Icône d’étape ID de poste de tri"><br>SortPositionId</td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Icône d’étape ID de contenant cible"><br>TargetLicensePlateId</td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Icône d’étape Vers le numéro de ligne"><br>ToLineNum</td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Icône d’étape Vers l’emplacement"><br>ToLocation</td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Icône d’étape Vers le numéro"><br>ToNum</td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Icône d’étape Vers l’entrepôt"><br>ToWarehouse</td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Icône d’étape ID de chargement de transport"><br>TransportLoadId</td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Icône d’étape ID de lot fournisseur"><br>VendBatchId</td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Icône d’étape ID d’étiquette de vague"><br>WaveLabelId</td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Icône d’étape Quantité d’étiquettes de vague"><br>WaveLblQty</td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Icône d’étape Poids"><br>Pondération</td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Icône d’étape Poids à consommer"><br>WeightToConsume</td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Icône d’étape Type d’ajustement WHS"><br>WHSAdjustmentType</td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Icône d’étape Exception de réception WHS"><br>WHSReceivingException</td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Icône d’étape ID d’emplacement WMS"><br>WMSLocationID</td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Icône d’étape ID de travail"><br>WorkId</td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Icône d’étape ID de travail à annuler"><br>WorkIdToCancel</td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Icône d’étape ID de contenant de travail"><br>WorkLicensePlateId</td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Icône d’étape Cluster de stockage des ID de contenant de travail"><br>WorkLPIDPutawayCluster</td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Icône d’étape ID de groupe de travail"><br>WorkPoolID</td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Icône d’étape ID de zone"><br>ZoneID</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a>Exemple : affecter des icônes et des titres d’étape pour un flux personnalisé

Cet exemple explique comment configurer des icônes et des titres d’étape pour un flux de tâches personnalisé. Le scénario repose sur un exemple de flux de tâches personnalisé qui est présenté et exploré plus en détail dans le billet de blog suivant : [Personnalisation de l’application mobile d’entreposage](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app). Le flux de tâches fonctionne de la manière suivante :

1. L’application affiche une page qui invite le collaborateur à fournir un ID de conteneur (par exemple, en scannant un code-barres).
1. Si l’ID de conteneur est valide, l’application ouvre une nouvelle page qui invite le collaborateur à entrer le poids. (Si l’ID de conteneur n’est pas valide, le collaborateur est renvoyé vers la première page.)
1. Lorsque le collaborateur entre un poids valide, le système stocke le poids et renvoie le collaborateur vers la première page.

L’illustration suivante présente ce flux de tâches.

![Diagramme du flux de tâches](media/step-icons-example-task-flow.png "Diagramme du flux de tâches")

### <a name="create-a-step-class-for-the-container-input-page"></a>Créer une classe d’étape pour la page de saisie du conteneur

La page de saisie du conteneur permet au collaborateur de scanner ou d’entrer un ID de conteneur.

![Page de saisie du conteneur](media/step-icons-example-container-input.png "Page de saisie du conteneur")

Dans la page de saisie du conteneur, le nom de contrôle du champ de saisie est `ContainerId`. Comme ce nom de contrôle ne figure pas sur la [liste des ID d’étape](#step-ids-classes), vous ne trouverez pas d’étape existante basée sur celui-ci. Par conséquent, vous devez créer une classe d’étape qui représente l’étape. Voici un exemple :

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

L’identificateur de l’icône d’étape est stocké dans le membre de la classe `defaultStepIcon`, et le titre de l’étape est stocké dans le membre de la classe `defaultStepTitle`.

Pour affecter une icône d’étape, définissez `defaultStepIcon` sur l’un des ID d’icône répertoriés dans la section [Icônes d’étape disponibles](#step-icons) plus haut dans cette rubrique.

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a>Utiliser une icône et un titre d’étape standard ou personnalisé pour la saisie du poids

La page de saisie du poids permet au collaborateur de saisir un poids.

![Page de saisie du poids](media/step-icons-example-weight-input.png "Page de saisie du poids")

Dans la page de saisie du poids, le nom de contrôle du champ de saisie est `Weight`, qui figure dans la [liste des ID d’étape](#step-ids-classes). Par conséquent, si l’icône et le titre de l’étape définis dans la classe `WHSMobileAppStepWeight` vous conviennent, vous n’avez rien à changer pour cette étape.

Cependant, si vous préférez utiliser une autre icône ou un autre titre pour cette étape, vous pouvez remplacer la méthode `stepId()` ou la méthode `stepInfo()` dans la classe du générateur. Chaque flux de tâches a son propre générateur d’informations sur les étapes.

#### <a name="override-the-stepid-method"></a>Remplacer la méthode stepId()

L’exemple suivant montre une façon de modifier une classe de constructeur en remplaçant la méthode `stepId()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

Vous créez ensuite une classe d’étape pour l’étape `NewWeight`. Le code doit ressembler au code de l’exemple `ContainerId` présenté plus haut dans cette rubrique.

#### <a name="override-the-stepinfo-method"></a>Remplacer la méthode stepInfo()

L’exemple suivant montre une façon de modifier une classe de constructeur en remplaçant la méthode `stepInfo()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

Vous construisez ensuite un objet `WHSMobileAppStepInfo` et définissez directement l’icône et/ou le titre.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Installer et connecter l’application mobile Gestion des entrepôts](install-configure-warehouse-management-app.md)
- [Paramètres utilisateur d’appareil mobile](mobile-device-user-settings.md)
