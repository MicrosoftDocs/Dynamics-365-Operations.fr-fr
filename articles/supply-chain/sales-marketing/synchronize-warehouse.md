---
title: Synchroniser les entrepôts depuis Supply Chain Management vers Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: f302f780fa8ba3d387a71770024a1bf7ad42c4ef
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910255"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a>Synchroniser les entrepôts depuis Supply Chain Management vers Field Service

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.

[![Synchronisation des processus d’entreprise entre Supply Chain Management et Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Modèles et tâches
Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les entrepôts depuis Supply Chain Management vers Field Service.

**Modèle dans l’intégration de données**
- Entrepôts (Supply Chain Management vers Field Service)

**Tâche du projet d’intégration des données**
- Entrepôt

## <a name="table-set"></a>Ensemble de tables
| Field Service    | Gestion de la chaîne d’approvisionnement                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Entrepôts                             |

## <a name="table-flow"></a>Flux de table
Les entrepôts créés et tenus à jour dans Supply Chain Management peuvent être synchronisés avec Field Service via un projet d’intégration de données de Microsoft Dataverse. Les entrepôts souhaités qui se synchronisent sur Field Service peuvent être contrôlés avec la fonctionnalité de requête et de filtrage avancée sur le projet. Les entrepôts synchronisés depuis Supply Chain Management sont créés dans Field Service avec la colonne **Est géré en externe** définie sur **Oui** et l’enregistrement est en lecture seule.

## <a name="field-service-crm-solution"></a>Solution Field Service CRM
Pour permettre l’intégration entre Field Service et Supply Chain Management, des fonctionnalités supplémentaires de la solution Field Service CRM sont requises. Dans la solution, la colonne **Est géré en externe** a été ajoutée à la table **Entrepôt (msdyn_warehouses)**. Cette colonne aide à identifier si l’entrepôt est géré depuis Supply Chain Management ou s’il existe uniquement dans Field Service. Les paramètres de cette colonne sont :
- **Oui** – L’entrepôt provient de Supply Chain Management et n’est pas modifiable dans Sales.
- **Non** - l’entrepôt a été entré directement dans Field Service et y est géré.

La colonne **Est géré en externe** aide à contrôler la synchronisation des niveaux de stock, les ajustements, les transferts et l’utilisation sur les ordres d’exécution. Seuls les entrepôts avec **Est géré en externe** définis sur **Oui** peuvent être utilisés pour se synchroniser directement sur l’entrepôt de l’autre système. 

> [!NOTE]
> Vous pouvez créer plusieurs entrepôts dans Field Service (avec **Géré en externe** = Non), puis les mapper à un seul entrepôt, avec la fonctionnalité de requête et de filtrage avancée. Cela est utile dans les situations où vous souhaitez que Field Service serve de base au niveau de stock détaillé et d’envoyer uniquement des mises à jour à Supply Chain Management. Dans ce cas, Field Service ne reçoit pas les mises à jour de niveau de stock de Supply Chain Management. Pour en savoir plus, voir [Synchroniser les ajustements de stock entre Field Service et Finance and Operations](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) et [Synchroniser des ordres de travail de Field Service sur des commandes client de  Finance and Operations](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance
### <a name="data-integration-project"></a>Projet d’intégration des données
Avant la synchronisation des entrepôts, vérifiez de mettre à jour la fonctionnalité de requête et de filtrage avancée sur le projet pour inclure uniquement les entrepôts à transférer de Supply Chain Management vers Field Service. Notez que vous avez besoin de l’entrepôt dans Field Service pour l’appliquer aux ordres d’exécution, ajustements et transferts.  

Pour s’assurer que la **Clé d’intégration** existe pour **msdyn_warehouses** :
1. Accédez au module Intégration des données.
2. Sélectionnez l’onglet **Ensemble de connexions**.
3. Sélectionnez l’ensemble de connexions utilisé pour la synchronisation des ordres d’exécution.
4. Sélectionnez l’onglet **Clé d’intégration**.
5. Recherchez msdyn_warehouses et confirmez que la clé **msdyn_name (nom)** est ajoutée. Si elle n’est pas affichée, ajoutez-la en cliquant sur **Ajouter une clé**, puis sur **Enregistrer** en haut de la page.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l’intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a>Entrepôts (Supply Chain Management vers Field Service) : Entrepôt

[![Mise en correspondance de modèles dans l’intégration de données](./media/Warehouse1.png)](./media/Warehouse1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]