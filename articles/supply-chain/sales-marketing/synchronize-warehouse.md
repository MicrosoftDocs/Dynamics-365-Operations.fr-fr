---
title: "Synchroniser les entrepôts entre Finance and Operations et Field Service"
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: fr-fr
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a>Synchroniser les entrepôts entre Finance and Operations et Field Service

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entrepôts entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Field Service.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Modèles et tâches
Les modèle et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des entrepôts de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Microsoft Dynamics 365 for Field Service.

**Nom du modèle dans l'intégration des données :**
- Entrepôts (Finance and Operations vers Field Service)

**Noms des tâches dans le projet d'intégration de données :**
- Entrepôt

## <a name="entity-set"></a>Ensemble d'entités
| Field Service    | Finance and Operations                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Entrepôts                             |

## <a name="entity-flow"></a>Flux d'entité
Les entrepôts qui sont créés et tenus à jour dans Finance and Operations peuvent être synchronisées sur Field Service via un projet d'intégration de données Common Data Service (CDS). Les entrepôts souhaités qui se synchronisent sur Field Service peuvent être contrôlés avec la fonctionnalité de requête et de filtrage avancée sur le projet. Les entrepôts qui se synchronisent sur Finance and Operations sont créés dans Field Service avec le champ Est géré en externe défini sur Oui et l'enregistrement est rendu en lecture seule.
Solution Field Service CRM Pour permettre l'intégration entre Field Service et Finance and Operations, des fonctionnalités supplémentaires de la solution Field Service CRM sont requises. La solution inclut les modifications suivantes.
Le champ **Est géré en externe** a été ajouté à l'entité **Entrepôt (msdyn_warehouses)**. Ce champ permet d'identifier si l'entrepôt est géré depuis Operations ou s'il existe uniquement dans Field Service.
- Oui – L'entrepôt provient de Finance and Operations et n'est pas modifiable dans Sales.
- Non - l'entrepôt a été entré directement dans Field Service et y est géré.

Le champ **Est géré en externe** permet de contrôler la synchronisation des niveaux de stock, des ajustements, des transferts et de l'utilisation sur les ordres d'exécution. Seuls les entrepôts avec **Est géré en externe** = Oui peuvent être utilisés pour se synchroniser directement sur l'entrepôt de l'autre système. 

Remarque : vous pouvez créer plusieurs entrepôts dans Field Service (avec **Géré en externe** = Non), puis les mapper à un seul entrepôt dans Finance and Operations, avec la fonctionnalité de requête et de filtrage avancée. Cela est utile dans les situations où vous souhaitez que Field Service serve de base au niveau de stock détaillé et n'envoyer que des mises à jour à Finance and Operations. Dans ce cas, Field Service ne reçoit pas les mises à jour de niveau de stock de Finance and Operations. Voir les informations supplémentaires dans Synchroniser les ajustements de stock entre Field Service et Finance and Operations et Synchroniser des bons de travail de Field Service sur des commandes client de Finance and Operations.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance
### <a name="in-the-data-integration-project"></a>Dans le projet d'intégration des données
Avant la synchronisation des entrepôts, vérifiez de mettre à jour la fonctionnalité de requête et de filtrage avancée sur le projet pour inclure uniquement les entrepôts à transférer de Finance and Operations vers Field Service. Notez que vous avez besoin de l'entrepôt dans Field Service pour l'appliquer aux ordres d'exécution, ajustements et transferts.  

Vérifiez que la **Clé d'intégration** existe pour **msdyn_warehouses**
1. Accédez au module Intégration des données
2. Sélectionnez l'onglet **Ensemble de connexions**
3. Sélectionnez l'ensemble de connexions utilisé pour la synchronisation des ordres d'exécution
4. Sélectionnez l'onglet **Clé d'intégration**
5. Recherchez msdyn_warehouses et vérifiez que la clé **msdyn_name (nom)** est ajoutée. Si elle n'est pas affichée, ajoutez-la en cliquant sur **Ajouter une clé**, puis sur **Enregistrer** en haut de la page

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a>Entrepôts (Finance and Operations vers Field Service): Entrepôt

[![Mise en correspondance de modèles dans l'intégration de données](./media/Warehouse1.png)](./media/Warehouse1.png)

