---
title: Entité Activités du conteneur
description: Cette rubrique fournit des informations sur les activités de conteneur, qui sont utilisées pour suivre la progression des conteneurs d’expédition.
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
ms.openlocfilehash: 7bb2b97e8885e3b1265f0c93585873c8a64f1dfb
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813059"
---
# <a name="container-activities-entity"></a>Entité Activités du conteneur

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Les activités de conteneur sont utilisées pour suivre la progression des conteneurs d’expédition. Un enregistrement est créé pour chaque segment affecté au modèle de parcours sélectionné au moment de la création du conteneur d’expédition. Des enregistrements sont également créés lorsque le conteneur d’expédition est créé via une entité de données.

Les informations sur la progression d’un conteneur d’expédition en transit proviennent souvent d’une source externe. L’entité des activités du conteneur permet à une source externe telle qu’un transitaire de mettre directement à jour l’enregistrement. Par conséquent, aucune mise à jour manuelle des données n’est requise.

## <a name="container-activities-itmcontaineractivityentity"></a>Activités du conteneur (ITMContainerActivityEntity)

Vous pouvez utiliser l’entité d’activités de conteneur (`ITMContainerActivityEntity`) pour créer des enregistrements d’activité supplémentaires. Alternativement, un transitaire peut transmettre des mises à jour pour une valeur **Date de fin réelle** confirmée.

| Name | Mise en correspondance | Type de données | Clé | Obligatoire |
|---|---|---|---|---|
| Date de fin réelle | ITMContainerActivityTable.ActualEndDate | Date et heure | N° | N° |
| Mode de livraison | ITMContainerActivityTable.DlvModeId | Nvarchar(10) | N° | N° |
| Date de fin estimée | ITMContainerActivityTable.EsimatedDate | Date et heure | N° | N° |
| Numéro de la ligne | ITMContainerActivityTable.LineNum | Numeric(32, 16) | **Oui** | N° |
| Notes | ITMContainerActivityTable.Notes | nvarchar(MAX) | N° | N° |
| Activité | ITMContainerActivityTable.ShipActivityId | Nvarchar(10) | N° | **Oui** |
| Conteneur d’expédition | ITMContainerActivityTable.ShipContainerId | Nvarchar(20) | **Oui** | **Oui** |
| Voyage | ITMContainerActivityTable.ShipId | Nvarchar(20) | **Oui** | **Oui** |
| Étape | ITMContainerActivityTable.ShipLegId | Nvarchar(20) | N° | **Oui** |
| Fournisseur de service | ITMContainerActivityTable.ShipServiceProvider | Nvarchar(20) | N° | N° |
| Température | ITMContainerActivityTable.ShipTemperature | Numeric(32, 6) | N° | N° |
| Bateau | ITMContainerActivityTable.ShipVesselId | Nvarchar(20) | N° | N° |
| Date de début | ITMContainerActivityTable.StartDate | Date et heure | N° | N° |

## <a name="tracking-control"></a>Contrôle de suivi

Le centre de contrôle de suivi permet de déclencher une mise à jour d’un champ source spécifié par une mise à jour d’un champ cible spécifié. Si la valeur du champ source et la valeur du champ cible sont mises à jour à l’aide de l’entité des activités du conteneur, le champ cible affichera la valeur de l’entité. Ce comportement est lié au suivi des enregistrements de contrôle qui ont une valeur **Créer un type** *Délai de mise en œuvre*.

Pour les zones de coûts qui ont une valeur **Créer un type** *Mise à jour du statut* ou *Vide* (qui est une valeur définie par l’utilisateur), le système mettra à jour le statut du voyage ou le champ cible en fonction de la configuration du contrôle de suivi.

## <a name="calculated-fields"></a>Champs calculés

Les valeurs des champs suivants dans un enregistrement d’activité de conteneur sont calculées en fonction des valeurs des autres champs. Bien que ces champs calculés ne soient pas inclus dans l’entité de données, ils seront définis si les champs sur lesquels les calculs sont basés sont fournis.

- **Jours estimés** = **Date de fin estimée** – **Date de début estimée**
- **Jours réels** = **Date de fin réelle** – **Date de début**
