---
title: Entités de création de voyages
description: Cet article fournit des informations sur les entités de données de création de voyage, qui regroupent les entités de données requises pour créer un voyage de travail.
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
ms.openlocfilehash: 6234dfa61a5859e2ecaca75594c69c49ba326629
ms.sourcegitcommit: 5b34b41ae74269ba639e2876bc5862ef468da1cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2022
ms.locfileid: "9167669"
---
# <a name="voyage-creation-entities"></a>Entités de création de voyage

[!include [banner](../includes/banner.md)]

Les entités de données de création de voyage regroupent les entités de données requises pour créer un voyage de travail. Vous ou votre transitaire pouvez utiliser ces entités de données pour créer des enregistrements de voyage, de conteneur d’expédition, de folio et de ligne de voyage qui font référence à des lignes de commande d’acheteur ou de commande de transfert existantes.

## <a name="voyages-itmtableentity"></a>Voyages (ITMTableEntity)

Le trajet représente le trajet des marchandises entrantes et constitue la zone de coût de niveau le plus élevé dans le coût au débarquement. Il contient des informations au niveau de l’en-tête relatives au navire, au port d’origine et au port de destination. Cette fonctionnalité est prise en charge par l’entité `ITMTableEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Mode de livraison | ITMTable.DlvModeId | Nvarchar(10) | N° | N° |
| Courtier avisé | ITMTable.ITMBrokerAdvised | Date et heure | N° | N° |
| Rendez-vous client | ITMTable.ITMCustomerAppointment | Date et heure | N° | N° |
| Livraison à l’entrepôt | ITMTable.ITMDelAtWarehouse | Date et heure | N° | N° |
| Instructions de livraison | ITMTable.ITMDeliveryInstructions | Date et heure | N° | N° |
| Date de départ | ITMTable.ITMDepartureDate | Date et heure | N° | N° |
| Mise en circulation des marchandises | ITMTable.ITMGoodsReleased | Date et heure | N° | N° |
| Date du transport local | ITMTable.ITMLocalTransportDate | Date et heure | N° | N° |
| Heure du transport local | ITMTable.ITMLocalTransportTime | Int | N° | N° |
| Feuille de chargement initiale envoyée | ITMTable.ITMOriginalBOLSebt | Date et heure | N° | N° |
| Documents originaux reçus | ITMTable.ITMOriginalDocsReceived | Date et heure | N° | N° |
| Statut de la commande fournisseur | ITMTable.ITMPurchStatus | Int | N° | N° |
| Date de vérification | ITMTable.ITMVerificationDate | Date et heure | N° | N° |
| Identificateur de déclaration en douane | ITMTable.ShipCustomsEntryId | Nvarchar(20) | N° | N° |
| Date d’expédition | ITMTable.ShipDate | Date et heure | N° | N° |
| Description | ITMTable.ShipDescription | Nvarchar(60) | N° | N° |
| Documents reçus | ITMTable.ShipDocReceived | Int | N° | N° |
| Date de livraison estimée | ITMTable.ShipEstDlvDate | Date et heure | N° | N° |
| HAE au port d’expédition | ITMTable.ShipEstPortDate | Date et heure | N° | N° |
| Port de départ | ITMTable.ShipFromPort | Nvarchar(20) | N° | N° |
| Feuille de route aérienne/Feuille de chargement | ITMTable.ShipHAWB | Nvarchar(20) | N° | N° |
| Voyage | ITMTable.ShipId | Nvarchar(20) | **Oui** | **Oui** |
| Référence de réservation | ITMTable.ShipIdExternal | Nvarchar(20) | N° | N° |
| Modèle de parcours | ITMTable.ShipJourneyId | Nvarchar(20) | N° | N° |
| Transitaire local | ITMTable.ShipLocalForwarder | Nvarchar(20) | N° | N° |
| Feuille de route aérienne principale/Feuille de chargement | ITMTable.ShipMAWB | Nvarchar(20) | N° | N° |
| Mesure | ITMTable.ShipMeasurement | Numeric(32, 6) | N° | N° |
| Unité de mesure | ITMTable.ShipMeasurementUnit | Int | N° | N° |
| Nombre actuel de palettes | ITMTable.ShipNoOfPallets | Int | N° | N° |
| Voyage en attente | ITMTable.ShipPending | Int | N° | N° |
| Remarques | ITMTable.ShipRemarks | Nvarchar(MAX) | N° | N° |
| Location | ITMTable.ShipRental | Int | N° | N° |
| Statut du voyage | ITMTable.ShipStatusId | Nvarchar(20) | N° | N° |
| Correspond au numéro | ITMTable.ShipTallyInNumber | Nvarchar(20) | N° | N° |
| Port d’arrivée | ITMTable.ShipToPort | Nvarchar(20) | N° | N° |
| Date d’évaluation | ITMTable.ShipValuationDate | Date et heure | N° | N° |
| Société d’expédition | ITMTable.ShipVendAccount | Nvarchar(20) | N° | N° |
| Bateau | ITMTable.ShipVesselId | Nvarchar(20) | N° | **Oui** |
| ID voyage externe | ITMTable.ShipVoyage | Nvarchar(20) | N° | N° |

### <a name="number-sequences-for-voyages"></a>Nombre de souches pour les voyages

La souche de numéros partagés pour les voyages contrôle l’attribution des identifiants de voyage.

La valeur transmise à l’entité de données en tant que **ID voyage** (`ShipId`) est utilisée pour identifier un enregistrement existant à mettre à jour. Si cet enregistrement n’existe pas, le comportement dépend si la souche de numéros attribuée est configurée pour autoriser la saisie manuelle :

- Si la saisie manuelle est activée, un nouvel enregistrement est créé qui utilise la valeur transmise.
- Si la saisie manuelle n’est pas activée, le numéro suivant dans la souche de numéros attribuée est utilisé à la place de la valeur transmise.

Pendant la session d’importation, la valeur d’espace réservé qui est importée en tant qu’ID de voyage est conservée. Ce comportement garantit que le conteneur d’expédition et les lignes de voyage qui font référence à l’espace réservé sont inclus dans le voyage et qu’ils sont mis à jour pour refléter la valeur attribuée à partir de la souche de numéros.

### <a name="automatic-cost-transactions"></a>Transactions de coût automatiques

Des frais automatiques peuvent être ajoutés à un voyage à partir de la page **Frais automobiles** dans Microsoft Dynamics 365 Supply Chain Management (**Prix au débarquement \> Configuration des coûts \> Frais automobiles**). Des enregistrements pour les coûts automatiques peuvent également être créés à l’aide d’entités de données de transaction de coût pour chaque zone de coût prise en charge par le coût final.

Les coûts automatiques configurés dans Supply Chain Management sont appliqués au voyage lorsqu’une ligne de voyage est créée. Aucun coût ne sera visible dans l’enregistrement tant que l’enregistrement d’en-tête n’est pas associé aux informations de ligne.

## <a name="shipping-containers-itmcontainersentity"></a>Expédition de conteneurs (ITMContainersEntity)

Un conteneur maritime représente un conteneur physique dans lequel les marchandises sont transportées. Ce conteneur physique peut être un conteneur de fret pour le fret maritime ou une seule palette pour le fret aérien. Le conteneur d’expédition comprend des informations au niveau de l’en-tête liées à l’ID du conteneur d’expédition, au numéro de scellé et au type de conteneur d’expédition. (Le type de conteneur d’expédition fournit des informations sur les dimensions.) Cette fonctionnalité est prise en charge par l’entité `ITMContainersEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Date de départ | ITMContainers.ITMDepartureDate | Date et heure | N° | N° |
| Date du transport local | ITMContainers.ITMLocalTransportDate | Date et heure | N° | N° |
| Heure du transport local | ITMContainers.ITMLocalTransportTime | Int | N° | N° |
| Voyage d’origine | ITMContainers.OrigShipId | Nvarchar(20) | N° | N° |
| Poids réel | ITMContainers.ShipActualWeight | Numeric(32, 6) | N° | N° |
| Courtier avisé | ITMContainers.ShipBrokerAdvised | Date et heure | N° | N° |
| Conteneur d’expédition | ITMContainers.ShipContainerId | Nvarchar(20) | **Oui** | **Oui** |
| Type de conteneur d’expédition | ITMContainers.ShipContainerTypeId | Nvarchar(20) | N° | N° |
| Type d’unité | ITMContainers.ShipContainerUnitTypeId | Nvarchar(10) | N° | N° |
| Converti en location | ITMContainers.ShipConvertedToRental | Int | N° | N° |
| Rendez-vous client | ITMContainers.ShipCustomerAppointment | Date et heure | N° | N° |
| Date d’expédition | ITMContainers.ShipDate | Date et heure | N° | N° |
| Livraison à l’entrepôt | ITMContainers.ShipDelAtWarehouse | Date et heure | N° | N° |
| Instructions de livraison | ITMContainers.ShipDeliveryInstructions | Date et heure | N° | N° |
| Date d’application du certificat d’examen | ITMContainers.ShipECAppliedDate | Date et heure | N° | N° |
| Date d’expiration du certificat d’examen | ITMContainers.ShipECExpiryDate | Date et heure | N° | N° |
| Numéro du certificat d’examen | ITMContainers.ShipECNum | Nvarchar(20) | N° | N° |
| Date de réception du certificat d’examen | ITMContainers.ShipECReceivedDate | Date et heure | N° | N° |
| Date de livraison estimée | ITMContainers.ShipEstDlvDate | Date et heure | N° | N° |
| HAE au port d’expédition | ITMContainers.ShipEstPortDate | Date et heure | N° | N° |
| Date de chargement prévue | ITMContainers.ShipExpectedLoadingDate | Date et heure | N° | N° |
| Port de départ | ITMContainers.ShipFromPort | Nvarchar(20) | N° | N° |
| Description des marchandises | ITMContainers.ShipGoodsDesc | Nvarchar(60) | N° | N° |
| Mise en circulation des marchandises | ITMContainers.ShipGoodsReleased | Date et heure | N° | N° |
| Unité de suivi GPS | ITMContainers.ShipGPSUnit | Nvarchar(30) | N° | N° |
| Feuille de route aérienne/Feuille de chargement | ITMContainers.ShipHAWB | Nvarchar(20) | N° | N° |
| Voyage | ITMContainers.ShipId | Nvarchar(20) | **Oui** | **Oui** |
| Modèle de parcours | ITMContainers.ShipJourneyId | Nvarchar(20) | N° | N° |
| Transitaire local | ITMContainers.ShipLocalForwarder | Nvarchar(20) | N° | N° |
| Mesure | ITMContainers.ShipMeasurement | Numeric(32, 6) | N° | N° |
| Unité de mesure | ITMContainers.ShipMeasurementUnit | Int | N° | N° |
| Nombre de cartons | ITMContainers.ShipNoOfCartons | Numeric(32, 6) | N° | N° |
| Feuille de chargement initiale envoyée | ITMContainers.ShipOriginalBOLSebt | Date et heure | N° | N° |
| Documents originaux reçus | ITMContainers.ShipOriginalDocsReceived | Date et heure | N° | N° |
| Notre numéro de sceau | ITMContainers.ShipOurSealNum | Nvarchar(20) | N° | N° |
| Utilisé(e) | ITMContainers.ShipPendingUsed | Int | N° | N° |
| Statut de la commande fournisseur | ITMContainers.ShipPurchStatus | Int | N° | N° |
| Type de réfrigération | ITMContainers.ShipRefrigerationTypeId | Nvarchar(10) | N° | N° |
| Remarques | ITMContainers.ShipRemarks | Nvarchar(MAX) | N° | N° |
| Location | ITMContainers.ShipRental | Int | N° | N° |
| Pouvant faire l’objet d’un retour | ITMContainers.ShipReturnable | Int | N° | N° |
| Statut du voyage | ITMContainers.ShipStatusId | Nvarchar(20) | N° | N° |
| Numéro de sceau de la société d’expédition | ITMContainers.ShipTheirSealNum | Nvarchar(20) | N° | N° |
| Port d’arrivée | ITMContainers.ShipToPort | Nvarchar(20) | N° | N° |
| Date de vérification | ITMContainers.ShipVerificationDate | Date et heure | N° | N° |
| Bateau | ITMContainers.ShipVesselId | Nvarchar(20) | N° | **Oui** |

### <a name="voyage-id-validation"></a>Validation de l’ID de voyage

L’ID du conteneur d’expédition n’est pas contrôlé par une séquence de chiffres. Il n’est unique que dans le contexte du voyage pour lequel il est utilisé.

Si l’entité de conteneur maritime (`ITMContainersEntity`) est utilisé indépendamment de l’entité du voyage (`ITMTableEntity`), la valeur **Identifiant du voyage** (`ShipId`) doit correspondre à un enregistrement existant dans la table des voyages. Sinon, l’importation échouera.

Si l’entité de conteneur maritime (`ITMContainersEntity`) et l’entité voyage (`ITMTableEntity`) sont utilisées dans le cadre d’une même session d’import, l’entité voyage doit précéder la création d’un conteneur maritime. Sinon, l’**ID voyage** (`ShipId`) la valeur ne peut pas être validée avec succès. Si une valeur d’espace réservé est utilisée pour la valeur **ID voyage** (`ShipId`), l’association ne peut être créée que si le même espace réservé est utilisé comme la valeur **ID voyage** (`ShipId`) dans l’entité conteneur d’expédition.

### <a name="other-field-validations"></a>Autres validations de champ

Le tableau suivant présente les champs de la table des conteneurs d’expédition (`ITMContainers`) qui sont validés par rapport aux tables de configuration des coûts d’approche. Il affiche également les entités de données de coût au débarquement qu’un transitaire peut utiliser pour lire les valeurs existantes et s’assurer que des valeurs valides sont reçues dans votre environnement.

| Champ de la table ITMContainers | Entité de données sur le coût au débarquement |
|---|---|
| Type de conteneur d’expédition | ITMShippingContainerTypeEntity |
| Description des marchandises | ITMGoodsDescriptionEntity |
| Type de réfrigération | ITMShippingContainerRefrigerationTypeEntity |

## <a name="folios-itmfolioentity"></a>Folios (ITMFolioEntity)

Un folio représente un regroupement d’articles dans un conteneur d’expédition aux fins des déclarations en douane. Le folio comprend des informations au niveau de l’en-tête relatives au courtier en douane et une description des marchandises. Cette fonctionnalité est prise en charge par l’entité `ITMFolioEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Courtier avisé | ITMFolioTable.ShipBrokerAdvised | Date et heure | N° | N° |
| Numéro de contrôle de la cargaison | ITMFolioTable.ShipCargoControlNumber | Nvarchar(20) | N° | N° |
| Rendez-vous client | ITMFolioTable.ShipCustomerAppointment | Date et heure | N° | N° |
| Courtier en douane | ITMFolioTable.ShipCustomsBroker | Nvarchar(20) | N° | N° |
| ID douanes | ITMFolioTable.ShipCustomsId | Nvarchar(60) | N° | N° |
| Société | ITMFolioTable.ShipDataArea | Nvarchar(4) | N° | **Oui** |
| Livraison à l’entrepôt | ITMFolioTable.ShipDelAtWarehouse | Date et heure | N° | N° |
| Instructions de livraison | ITMFolioTable.ShipDeliveryInstructions | Date et heure | N° | N° |
| Documents reçus | ITMFolioTable.ShipDocReceived | Int | N° | N° |
| Date de livraison estimée | ITMFolioTable.ShipEstDlvDate | Date et heure | N° | N° |
| HAE au port d’expédition | ITMFolioTable.ShipEstPortDate | Date et heure | N° | N° |
| Exportateur | ITMFolioTable.ShipExporterId | Nvarchar(20) | N° | N° |
| Name | ITMFolioTable.ShipExporterName | Nvarchar(60) | N° | N° |
| Date du folio | ITMFolioTable.ShipFolioDate | Date et heure | N° | N° |
| Folio | ITMFolioTable.ShipFolioId | Nvarchar(20) | **Oui** | **Oui** |
| Port de départ | ITMFolioTable.ShipFromPort | Nvarchar(20) | N° | N° |
| Description des marchandises | ITMFolioTable.ShipGoodsDesc | Nvarchar(60) | N° | N° |
| Mise en circulation des marchandises | ITMFolioTable.ShipGoodsReleased | Date et heure | N° | N° |
| Feuille de route aérienne/Feuille de chargement | ITMFolioTable.ShipHAWB | Nvarchar(20) | N° | N° |
| Voyage | ITMFolioTable.ShipId | Nvarchar(20) | N° | **Oui** |
| Mesure | ITMFolioTable.ShipMeasurement | Numeric(32, 6) | N° | N° |
| Unité de mesure | ITMFolioTable.ShipMeasurementUnit | Int | N° | N° |
| Nombre de cartons | ITMFolioTable.ShipNoOfCartons | Numeric(32, 6) | N° | N° |
| Feuille de chargement initiale envoyée | ITMFolioTable.ShipOriginalBOLSebt | Date et heure | N° | N° |
| Documents originaux reçus | ITMFolioTable.ShipOriginalDocsReceived | Date et heure | N° | N° |
| Statut de la commande fournisseur | ITMFolioTable.ShipPurchStatus | Int | N° | N° |
| Remarques | ITMFolioTable.ShipRemarks | Nvarchar(MAX) | N° | N° |
| Statut du voyage | ITMFolioTable.ShipStatusId | Nvarchar(20) | N° | N° |
| Code Tarif | ITMFolioTable.ShipTariffCode | Nvarchar(10) | N° | N° |
| Port d’arrivée | ITMFolioTable.ShipToPort | Nvarchar(20) | N° | N° |
| Date d’évaluation | ITMFolioTable.ShipValuationDate | Date et heure | N° | N° |
| Date de vérification | ITMFolioTable.ShipVerificationDate | Date et heure | N° | N° |
| Compte fournisseur | ITMFolioTable.VendAccount | Nvarchar(20) | N° | N° |

### <a name="number-sequences-for-folios"></a>Souches de numéros pour folios

La souche de numéros pour les folios contrôle l’attribution des identifiants de folio.

La valeur transmise à l’entité de données en tant que **ID folio** (`FolioId`) est utilisée pour identifier un enregistrement existant à mettre à jour. Si cet enregistrement n’existe pas, le comportement dépend si la souche de numéros attribuée est configurée pour autoriser la saisie manuelle :

- Si la saisie manuelle est activée, un nouvel enregistrement est créé qui utilise la valeur transmise.
- Si la saisie manuelle n’est pas activée, le numéro suivant dans la souche de numéros attribuée est utilisé à la place de la valeur transmise.

Pendant la session d’importation, la valeur d’espace réservé qui est importée en tant qu’ID de folio est conservée. Ce comportement garantit que le conteneur d’expédition et les lignes de voyage qui font référence à l’espace réservé sont correctement associés et qu’ils sont mis à jour pour refléter la valeur attribuée à partir de la souche de numéros.

### <a name="field-validations"></a>Validations de champ

Le champ **Description des marchandises** dans la table des folios (`ITMFolioTable`) est validé par rapport à la table de configuration des coûts dédouanés du même nom. Un transitaire peut utiliser l’entité de données de coût au débarquement `ITMGoodsDescriptionEntity` pour lire les valeurs existantes et s’assurer que des valeurs valides sont reçues dans votre environnement.

## <a name="voyage-lines-for-purchase-orders-itmpurchaselineentity"></a>Lignes de voyage pour les bons de commande (ITMPurchaseLineEntity)

La ligne de voyage représente une seule ligne de bon de commande incluse dans le voyage. Cette relation s’établit via les champs **Numéro de commande** et **Numéro de ligne d’achat**. La ligne de voyage fait référence à chaque enregistrement précédent qui a été créé pour le voyage, le conteneur d’expédition et le folio. Cette fonctionnalité est prise en charge par l’entité `ITMPurchaseLineEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Devise | ITMLine.CurrencyCode | Nvarchar(3) | N° | N° |
| Montant HT | ITMLine.LineAmountMST | Numeric(32, 6) | N° | N° |
| Numéro de ligne de commande | ITMLine.RefRecId | Numeric(32, 6) | **Oui** | N° |
| Conteneur d’expédition | ITMLine.ShipContainerId | Int | N° | N° |
| Société | ITMLine.ShipDataArea | Nvarchar(20) | **Oui** | N° |
| Quantité déclarée | ITMLine.ShipDeclaredQty | Nvarchar(4) | N° | N° |
| Folio | ITMLine.ShipFolioId | Numeric(32, 6) | N° | N° |
| Voyage | ITMLine.ShipId | Nvarchar(20) | **Oui** | N° |
| Numéro d’article | ITMLine.ShipItemId | Nvarchar(20) | N° | N° |
| Mesure | ITMLine.ShipMeasurement | Nvarchar(20) | N° | N° |
| Unité de mesure | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | N° | N° |
| Nombre de cartons | ITMLine.ShipNoOfCartons | Int | N° | N° |
| Emplacement | ITMLine.ShipPosition | Numeric(32, 6) | N° | N° |
| Quantity | ITMLine.ShipQty | Int | N° | N° |
| Numéro commande fournisseur | ITMLine.TransRefId | Numeric(32, 6) | **Oui** | N° |
| Unité | ITMLine.UnitId | Int | N° | N° |
| Volume | ITMLine.Volume | Nvarchar(10) | N° | N° |
| Poids | ITMLine.Weight | Numeric(32, 6) | N° | N° |

## <a name="voyage-lines-for-transfer-orders-itmtransferlineentity"></a>Lignes de voyage pour les ordres de transfert (ITMTransferLineEntity)

La ligne de voyage représente une seule ligne d’ordre de transfert incluse dans le voyage. Cette relation s’établit via les champs **Numéro d’ordre de transfert** et **Numéro de ligne de transfert**. La ligne de voyage fait référence à chaque enregistrement précédent qui a été créé pour le voyage, le conteneur d’expédition et le folio. Cette fonctionnalité est prise en charge par l’entité `ITMTransferLineEntity`. Le tableau suivant répertorie les champs et les mappages qui composent cette entité.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Devise | ITMLine.CurrencyCode | Nvarchar(3) | N° | N° |
| Montant HT | ITMLine.LineAmountMST | Numeric(32, 6) | N° | N° |
| Conteneur d’expédition | ITMLine.ShipContainerId | Int | N° | N° |
| Société | ITMLine.ShipDataArea | Nvarchar(20) | **Oui** | N° |
| Quantité déclarée | ITMLine.ShipDeclaredQty | Nvarchar(4) | N° | N° |
| Folio | ITMLine.ShipFolioId | Numeric(32, 6) | N° | N° |
| Voyage | ITMLine.ShipId | Nvarchar(20) | **Oui** | N° |
| Numéro d’article | ITMLine.ShipItemId | Nvarchar(20) | N° | N° |
| Mesure | ITMLine.ShipMeasurement | Nvarchar(20) | N° | N° |
| Unité de mesure | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | N° | N° |
| Nombre de cartons | ITMLine.ShipNoOfCartons | Int | N° | N° |
| Emplacement | ITMLine.ShipPosition | Numeric(32, 6) | N° | N° |
| Quantity | ITMLine.ShipQty | Int | N° | N° |
| Numéro de ligne de transfert | ITMLine.TransferLineNumber | Numeric(32, 6) | **Oui** | N° |
| Numéro d’ordre de transfert | ITMLine.TransRefId | Numeric(32, 6) | **Oui** | N° |
| Unité | ITMLine.UnitId | Int | N° | N° |
| Volume | ITMLine.Volume | Nvarchar(10) | N° | N° |
| Poids | ITMLine.Weight | Numeric(32, 6) | N° | N° |

### <a name="reference-table"></a>Table de référence

Les lignes de voyage sont créées via une association avec une ligne de commande entrante ouverte. Cette ligne peut être sur un bon de commande, ou il peut s’agir de la transaction de réception sur un ordre de transfert. Le champ `RefTableId` dans la table des lignes de voyage (`ITMLine`) spécifie le type de commande auquel la ligne est associée en faisant référence au numéro de table. Si des numéros de table spécifiques sont référencés dans la table dans laquelle les données sont créées, les entités sont divisées en fonction de ces valeurs.

Les valeurs de la table de référence (`RefTableId`) et le type de transaction (`TransType`) sont implicites dans la sélection de l’entité de ligne d’achat au coût d’approche ou de l’entité de ligne de transfert du coût d’approche.

### <a name="validation"></a>Validation

Une ligne de voyage fait directement référence à un enregistrement de voyage, un enregistrement de conteneur d’expédition et un enregistrement de folio. Si l’entité de la ligne d’achat (`ITMPurchaseLinesEntity`) ou l’entité de la ligne de transfert (`ITMPurchaseLinesEntity`) est utilisé indépendamment des entités qui sont utilisées pour créer ces enregistrements de référence, les valeurs **ID voyage** (`ShipId`), **Conteneur d’expédition** (`ShipContainerId`) et **Folio** (`ShipFolioId`) doivent correspondre à un enregistrement existant dans les tables correspondantes. Sinon, l’importation échouera.

Si l’une ou l’autre des entités de ligne est utilisée dans le cadre de la même session d’importation, ces autres entités doivent précéder la création d’une ligne de voyage. Sinon, les valeurs ne peuvent pas être validées avec succès. Si une valeur d’espace réservé est utilisée pour le numéro de voyage ou de folio, l’association ne peut être créée que si le même espace réservé est utilisé pour le numéro de voyage ou de folio dans l’entité de ligne de voyage.

Si la ligne de bon de commande ou d’ordre de transfert est déjà affectée à une ligne de voyage existante, la nouvelle ligne de voyage ne sera pas créée. Avant que la ligne de commande puisse être affectée à un nouveau voyage, elle doit être retirée de son voyage en cours.

### <a name="order-line-identification"></a>Identification de la ligne d’ordre

Les lignes de voyage font directement référence aux valeurs de référence **ID d’enregistrement** (`RefRecId`), **ID de dimension de stock** (`InventDimId`) et **ID de mouvement de stock** (`InventTransId`). Ces valeurs ne doivent plus être incluses lorsque l’entité de données est utilisée. Au lieu de cela, le numéro de ligne de commande doit maintenant être inclus. Ensemble, le numéro de ligne de commande et le numéro de commande permettent d’identifier chacune de ces valeurs de référence.

### <a name="voyage-line-quantity"></a>Quantité de lignes de voyage

Comme une ligne de voyage est directement associée à une ligne de commande, la valeur **Quantité** (`ShipQty`) qui est entrée à l’aide de l’entité nécessite que les valeurs correspondent. La validation est exécutée par rapport à la quantité sur la ligne de commande fournisseur ou sur la ligne de transfert. Si la validation échoue, l’enregistrement ne sera pas traité.

### <a name="calculated-fields"></a>Champs calculés

Les champs calculés **Poids** et **Volume** acceptent les valeurs reçues via l’entité de données. Si aucune valeur n’est fournie, les valeurs système sont utilisées pour mettre à jour ces champs, si des valeurs système sont disponibles. Pour le coût au débarquement, les valeurs sont calculées de la manière suivante :

- *Poids* = *Quantité* × *Poids brut de l’article*
- *Volume* = *Quantité* × (*Profondeur brute de l’article* × *Hauteur brute de l’article* × *Largeur brute de l’article*)

## <a name="sequencing"></a>Séquençage

En raison des dépendances entre les tables, l’enregistrement du voyage doit être créé en premier. La ligne de voyage ne peut être créée qu’après la création du voyage, du conteneur d’expédition et des folios.

Pour créer un voyage sans avis de validation, le système doit traiter les entités dans l’ordre suivant :

1. Voyages (`ITMTableEntity`)
1. Conteneurs d’expédition (`ITMContainersEntity`)
1. Folios (`ITMFolioTableEntity`)
1. Lignes de voyage (`ITMPurchaseLinesEntity` ou `ITMTransferLinesEntity`)
