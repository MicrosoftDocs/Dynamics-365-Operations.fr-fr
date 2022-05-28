---
title: Intégration avec des systèmes d’exécution de fabrication tiers
description: Cette rubrique explique comment vous pouvez intégrer Microsoft Dynamics 365 Supply Chain Management à un système d’exécution de la production tiers.
author: johanhoffmann
ms.date: 10/01/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-10-01
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: c7633ba32f9265aa0fd8f702552f48dbf675375d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678685"
---
# <a name="integrate-with-third-party-manufacturing-execution-systems"></a>Intégration avec des systèmes d’exécution de fabrication tiers

[!include [banner](../includes/banner.md)]

Certaines organisations de fabrication qui utilisent Microsoft Dynamics 365 Supply Chain Management utilisent la fonctionnalité native de Dynamics 365 pour contrôler leurs activités de fabrication pour les machines, les équipements et le personnel. Cependant, d’autres organisations de fabrication, en particulier celles qui ont des exigences de fabrication avancées, utilisent à la place un système d’exécution de production tiers. Les organisations peuvent choisir une solution de système d’exécution de la production tierce parce que, par exemple, elle est spécifiquement adaptée à leur secteur vertical.

Dans la solution intégrée, l’échange de données est entièrement automatisé et se produit en temps quasi réel. Par conséquent, les données sont tenues à jour dans les deux systèmes et aucune saisie manuelle de données n’est requise. Par exemple, lorsque la consommation de matière est enregistrée dans le système d’exécution de la production, l’intégration garantit que la même consommation est également enregistrée dans Dynamics 365. Par conséquent, des enregistrements de stock à jour sont disponibles pour d’autres processus importants, tels que la planification et les ventes.

La solution permet aux utilisateurs de Supply Chain Management de s’intégrer plus rapidement, plus facilement et à moindre coût aux systèmes d’exécution de la production tiers. Elle offre les fonctionnalités suivantes :

- Événements commerciaux et interfaces prenant en charge [les processus clés d’exécution de la production](#processes-available-for-mes-integration)
- Un tableau de bord centralisé où vous pouvez suivre l’historique du traitement des événements, et dépanner et corriger les processus qui échouent

L’illustration suivante montre une collection typique d’événements, de processus et de messages commerciaux qui sont échangés dans une solution intégrée.

![Scénario d’intégration classique.](media/3p-mes-scenario.png "Scénario d’intégration classique.")

## <a name="turn-on-the-mes-integration-feature"></a>Activer la fonction d’intégration de système d’exécution de la production

Avant de pouvoir utiliser cette fonctionnalité, un administrateur doit l’activer dans votre système comme décrit dans la procédure suivante.

1. Accédez à **Administration système \> Paramétrage \> Configuration des licences**.
1. Assurez-vous que la clé de licence **Pointage** est activée (affiche une coche). Cette clé de licence est requise car elle contrôle les fonctionnalités et les données du système d’exécution de fabrication. S’il n’est pas activé, procédez comme suit :
    1. Mettez votre système en mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
    1. Sur la page **Configuration de la licence**, cochez la case **Pointage**.
    1. Désactiver le mode maintenance comme décrit dans [Mode maintenance](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)
1. Accédez au **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
1. Activez la fonctionnalité répertoriée comme suit (voir également [Vue d’ensemble de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)) :
    - **Module :** *Contrôle de la production*
    - **Nom de la fonctionnalité :** *Intégration du système d’exécution de la production*

## <a name="processes-available-for-mes-integration"></a>Processus disponibles pour l’intégration de système d’exécution de la production

Vous pouvez activer tout ou partie des processus suivants pour l’intégration.

| Nom du processus | Description |
|---|---|
| Lancer les ordres de fabrication et les événements commerciaux de changement de statut des ordres de fabrication | Ce processus fournit un événement commercial que le système d’exécution de la production peut écouter, pour obtenir des informations sur les ordres de fabrication qui devraient être produits. Les données de référence liées à l’ordre de production devraient être partagées entre Supply Chain Management et le système d’exécution de la production via l’Open Data Protocol (OData) ou des entités de données. |
| Démarrer l’ordre de fabrication | Ce processus fournit à Supply Chain Management des informations sur les ordres de fabrication lancés à l’aide du système d’exécution de la production. Il garantit que les deux systèmes ont une vue à jour de toutes les activités de fabrication. |
| Rapporter la quantité produite ou mise au rebut | Ce processus fournit à Supply Chain Management des informations sur les quantités de marchandises et d’erreurs signalées sur une tâche de production à l’aide du système d’exécution de la production. Il garantit que les chefs d’atelier ont une vue à jour de l’avancement du plan de production. |
| Signaler la consommation de matières premières | Ce processus fournit à Supply Chain Management les informations du système d’exécution de la production sur les quantités de matières consommées. Des enregistrements de stock à jour sont mises à disposition pour d’autres processus importants, tels que la planification et les ventes. |
| Signaler le temps consommé pour l’opération | Ce processus fournit à Supply Chain Management des informations sur le temps utilisé pour une opération spécifique. |
| Terminer l’ordre de fabrication | Ce processus informe Supply Chain Management que le système d’exécution de la production a mis à jour un ordre de fabrication à son statut final de *Terminé*. Ce statut indique qu’aucune autre quantité ne sera produite sur l’ordre de fabrication. |

## <a name="monitor-incoming-messages"></a>Surveiller les messages entrants

Pour surveiller les messages entrants dans le système, ouvrez la page **Intégration des systèmes d’exécution de la production**. Là, vous pouvez afficher, traiter et résoudre les problèmes.

Tous les messages pour un ordre de fabrication spécifique sont traités dans l’ordre dans lequel ils sont reçus. Cependant, les messages pour différents ordres de fabrication peuvent ne pas être traités dans l’ordre reçu car les travaux par lots sont traités en parallèle. En cas d’échec, le traitement par lots tentera de traiter chaque message trois fois avant de le définir au statut *Échoué*.

## <a name="call-the-api"></a>Appeler l’API

Pour appeler l’API d’intégration de système d’exécution de la production, envoyez une demande `POST` à l’URL de point de terminaison suivante :

`/api/services/SysMessageServices/SysMessageService/SendMessage`

Le corps de la demande que vous envoyez doit ressembler à l’exemple suivant. Remplacez les valeurs de `_companyId`, `_messageType` et `_messageContent` comme demandé. Pour plus d’informations sur les différents types de messages pris en charge par l’API et sur la conception de leur contenu, consultez la section suivante.

```json
{
    "_companyId": "USMF",
    "_messageQueue": "JmgMES3P",
    "_messageType": "ProdProductionOrderReportFinished",
    "_messageContent":
    "{\"ProductionOrderNumber\": \"P000123\", \"ReportFinishedLines\": [{\"ItemNumber\": \"A0001\", \"ReportedGoodQuantity\": 10, \"ReportAsFinishedDate\": \"2021-01-01\"}]}"
}
```

## <a name="api-message-types-and-content"></a>Types de messages et contenu de l’API

Cette section décrit chaque type de message pouvant être échangé via l’API d’intégration de système d’exécution de la production.

### <a name="start-production-order-message"></a>Message Démarrer un ordre de fabrication

Pour le message *démarrer l’ordre de fabrication*, la valeur `_messageType` est `ProdProductionOrderStart`. Le tableau suivant montre les champs pris en charge par ce message.

| Nom du champ | Status | Type |
|---|---|---|
| `ProductionOrderNumber` | Obligatoire | Chaîne |
| `StartedQuantity` | Facultatif | Réel |
| `StartedDate` | Facultatif | Date |
| `AutomaticBOMConsumptionRule` | Facultatif | Enum (PrincipeEffacement \| Toujours \| Jamais) |

### <a name="report-as-finished-message"></a>Message Déclarer comme terminé

Pour le message *signaler comme terminé*, la valeur `_messageType` est `ProdProductionOrderReportFinished`. Le tableau suivant montre les champs pris en charge par ce message.

| Nom du champ | Status | Type |
|---|---|---|
| `ProductionOrderNumber` | Obligatoire | Chaîne |
| `ReportFinishedLines` | Obligatoire | Une liste de lignes (au moins une), dont chacune contient la charge utile décrite dans le tableau suivant |

Le tableau suivant montre les champs que chaque ligne de la section `ReportFinishedLines` du message `ProdProductionOrderReportFinished` prend en charge.

| Nom du champ | Status | Type |
|---|---|---|
| `LineNumber` | Facultatif | Réel |
| `ItemNumber` | Facultatif | Chaîne|
| `ProductionType` | Facultatif | Enum (MainItem \| Formule \| Nomenclature \| Co_Produit \| Sous_Produit \| Aucun), extensible |
| `ReportedErrorQuantity` | Facultatif | Réel|
| `ReportedGoodQuantity` | Facultatif | Réel|
| `ReportedErrorCatchWeightQuantity` | Facultatif | Réel |
| `ReportedGoodCatchWeightQuantity` | Facultatif | Réel |
| `AcceptError` | Facultatif | Enum (Oui \| Non) |
| `ErrorCause` | Facultatif | Enum (Aucun \| Matériel \| Machine \| PersonnelExploitation), extensible |
| `ExecutedDateTime` | Facultatif | Date et heure |
| `ReportAsFinishedDate` | Facultatif | Date |
| `AutomaticBOMConsumptionRule` | Facultatif | Enum (PrincipeEffacement \| Toujours \| Jamais) |
| `AutomaticRouteConsumptionRule` | Facultatif |Enum (DépendantGamme \| Toujours \| Jamais) |
| `RespectFlushingPrincipleDuringOverproduction` | Facultatif | Enum (Oui \| Non) |
| `ProductionJournalNameId` | Facultatif | Chaîne |
| `PickingListProductionJournalNameId` | Facultatif | Chaîne|
| `RouteCardProductionJournalNameId` | Facultatif | Chaîne |
| `FromOperationNumber` | Facultatif | Entier|
| `ToOperationNumber` | Facultatif | Entier|
| `InventoryLotId` | Facultatif | Chaîne |
| `BaseValue` | Facultatif | Chaîne |
| `EndJob` | Facultatif | Enum (Oui \| Non) |
| `EndPickingList` | Facultatif | Enum (Oui \| Non) |
| `EndRouteCard` | Facultatif | Enum (Oui \| Non) |
| `PostNow` | Facultatif | Enum (Oui \| Non) |
| `AutoUpdate` | Facultatif | Enum (Oui \| Non) |
| `ProductColorId` | Facultatif | Chaîne|
| `ProductConfigurationId` | Facultatif | Chaîne |
| `ProductSizeId` | Facultatif | Chaîne |
| `ProductStyleId` | Facultatif | Chaîne |
| `ProductVersionId` | Facultatif | Chaîne |
| `ItemBatchNumber` | Facultatif | Chaîne |
| `ProductSerialNumber` | Facultatif | Chaîne |
| `LicensePlateNumber` | Facultatif | Chaîne |
| `InventoryStatusId` | Facultatif | Chaîne |
| `ProductionWarehouseId` | Facultatif | Chaîne |
| `ProductionSiteId` | Facultatif | Chaîne |
| `ProductionWarehouseLocationId` | Facultatif | Chaîne |
| `InventoryDimension1` à `InventoryDimension12` | Facultatif | Chaîne |

Les 12 dimensions extensibles (de `InventoryDimension1` à `InventoryDimension12`) nécessitent une personnalisation et ne sont pas toujours utilisées. Pour plus d’informations à leur sujet, consultez [Ajouter de nouvelles dimensions de stock via l’extension](../../fin-ops-core/dev-itpro/extensibility/inventory-dimensions.md).

### <a name="material-consumption-picking-list-message"></a>Message de consommation de matériel (liste de prélèvement)

Pour le message *consommation de matière (liste de prélèvement)*, la valeur `_messageType` est `ProdProductionOrderPickingList`. Le tableau suivant montre les champs pris en charge par ce message.

| Nom du champ | Status | Type |
|---|---|---|
| `ProductionOrderNumber` | Obligatoire | Chaîne |
| `JournalNameId` | Facultatif | Chaîne |
| `PickingListLines` | Obligatoire | Une liste de lignes (au moins une), dont chacune contient la charge utile décrite dans le tableau suivant |

Le tableau suivant montre les champs que chaque ligne de la section `PickingListLines` du message `ProdProductionOrderPickingList` prend en charge.

| Nom du champ | Status | Type |
|---|---|---|
| `ItemNumber` | Obligatoire | Chaîne |
| `ConsumptionBOMQuantity` | Facultatif | Réel |
| `ProposalBOMQuantity` | Facultatif | Réel |
| `ScrapBOMQuantity` | Facultatif | Réel |
| `BOMUnitSymbol` | Facultatif | Chaîne |
| `ConsumptionInventoryQuantity` | Facultatif | Réel |
| `ProposalInventoryQuantity` | Facultatif | Réel |
| `ConsumptionCatchWeightQuantity` | Facultatif | Réel |
| `ProposalCatchWeightQuantity` | Facultatif | Réel |
| `ConsumptionDate` | Facultatif | Date |
| `OperationNumber` | Facultatif | Entier |
| `LineNumber` | Facultatif | Réel |
| `PositionNumber` | Facultatif | Chaîne |
| `IsConsumptionEnded` | Facultatif | Enum (Oui \| Non) |
| `ErrorCause` | Facultatif | Enum (Aucun \| Matériel \| Machine \| PersonnelExploitation), extensible |
| `InventoryLotId` | Facultatif | Chaîne |

### <a name="time-used-for-operation-route-card-message"></a>Message Temps utilisé pour l’opération (carte de gamme)

Pour le message *temps utilisé pour l’opération (carte de gamme)*, la valeur `_messageType` est `ProdProductionOrderRouteCard`. Le tableau suivant montre les champs pris en charge par ce message.

| Nom du champ | Status | Type |
|---|---|---|
| `ProductionOrderNumber` | Obligatoire | Chaîne |
| `JournalNameId` | Facultatif | Chaîne |
| `RouteCardLines` | Obligatoire | Une liste de lignes (au moins une), dont chacune contient la charge utile décrite dans le tableau suivant |

Le tableau suivant montre les champs que chaque ligne de la section `RouteCardLines` du message `ProdProductionOrderRouteCard` prend en charge.

| Nom du champ | Status | Type |
|---|---|---|
| `OperationNumber` | Obligatoire | Entier |
| `OperationPriority` | Facultatif | Enum (Primaire \| Secondaire1 \| Secondaire2 \| ... \| Secondaire20) |
| `OperationId` | Facultatif | Chaîne |
| `OperationsResourceId` | Facultatif | Chaîne |
| `Worker` | Facultatif | Chaîne |
| `HoursRouteCostCategoryId` | Facultatif | Chaîne |
| `QuantityRouteCostCategoryId` | Facultatif | Chaîne |
| `HourlyRate` | Facultatif | Réel |
| `Hours` | Facultatif | Réel |
| `GoodQuantity` | Facultatif | Réel |
| `ErrorQuantity` | Facultatif | Réel |
| `CatchWeightGoodQuantity` | Facultatif | Réel |
| `CatchWeightErrorQuantity` | Facultatif | Réel |
| `QuantityPrice` | Facultatif | Réel |
| `ProcessingPercentage` | Facultatif | Réel |
| `ConsumptionDate` | Facultatif | Date |
| `TaskType` | Facultatif | Enum (FileAttenteAvant \| Configuration \| Processus \| Chevauchement \| Transport \| FileAttenteAprès \| Charge) |
| `ErrorCause` | Facultatif | Enum (Aucun \| Matériel \| Machine \| PersonnelExploitation), extensible |
| `OperationCompleted` | Facultatif | Enum (Oui \| Non) |
| `BOMConsumption` | Facultatif | Enum (Oui \| Non) |
| `ReportAsFinished` | Facultatif | Enum (Oui \| Non) |

### <a name="end-production-order-message"></a>Message Terminer un ordre de fabrication

Pour le message *terminer l’ordre de fabrication*, la valeur `_messageType` est `ProdProductionOrderEnd`. Le tableau suivant montre les champs pris en charge par ce message.

| Nom du champ | Status | Type |
|---|---|---|
| `ProductionOrderNumber` | Obligatoire | Chaîne |
| `ExecutedDateTime` | Facultatif | Date et heure |
| `EndedDate` | Facultatif | Date |
| `UseTimeAndAttendanceCost` | Facultatif | Enum (Oui \| Non) |
| `AutoReportAsFinished` | Facultatif | Enum (Oui \| Non) |
| `AutoUpdate` | Facultatif | Enum (Oui \| Non) |

## <a name="other-production-information"></a>Autres informations sur la fabrication

Les messages prennent en charge des actions ou des événements qui se produisent dans l’atelier. Ils sont traités à l’aide de l’infrastructure d’intégration MES décrite dans cette rubrique. La conception suppose que d’autres informations de référence à partager avec le MES (telles que les informations relatives au produit, ou la nomenclature ou la gamme (avec ses temps d’installation et de configuration spécifiques) utilisées dans un ordre de fabrication spécifique) seront extraites du système en utilisant des [entités de données](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#data-entities) via transfert de fichier ou OData.

## <a name="receive-feedback-about-the-state-of-a-message"></a>Recevoir des commentaires sur l’état d’un message

Une fois que le système d’exécution de la production a envoyé un message à Supply Chain Management, il peut être pertinent pour Supply Chain Management de renvoyer des commentaires sur l’état du message. Voici quelques exemples de cas où ce comportement peut être approprié :

- Personne n’est chargé de superviser en permanence l’intégration du système d’exécution de la production.
- La personne chargée de superviser l’intégration du système d’exécution de la production souhaite être notifiée par e-mail en cas d’échec d’un message, afin qu’elle sache qu’elle doit prendre des mesures.
- Le système d’exécution de la production doit afficher un message d’erreur pour informer l’opérateur de l’atelier ou une personne du service informatique qu’il doit prendre des mesures.
- Le système d’exécution de la production doit recalculer le calendrier de commande après avoir reçu un message d’échec (par exemple, parce qu’un ordre de fabrication n’a pas pu démarrer).

Dans ces cas, vous pouvez profiter de la fonction d’alerte standard dans Supply Chain Management. Pour plus d’informations sur le fonctionnement des alertes standard, consultez les ressources suivantes :

- Rubrique d’aide : [Vue d’ensemble des alertes](../../fin-ops-core/fin-ops/get-started/alerts-overview.md)
- Vidéo : [Options de règle d’alerte dans Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=cpzimwOjicM&ab_channel=MicrosoftDynamics365)

Par exemple, vous pouvez configurer les alertes suivantes pour fournir des commentaires sur l’état d’un message :

- Créez un événement commercial (« Envoyer en externe ») utilisé lorsqu’un message a *Échoué*.
- Envoyez une notification et un e-mail à l’administrateur informatique ou au responsable de l’atelier de production.
