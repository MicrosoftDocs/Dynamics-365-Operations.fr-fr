---
title: Synchroniser les informations sur le niveau de stock entre Finance and Operations et Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les informations au niveau du stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 6b2bdf1ca6f6ae43cd85c8a1353ee8305052761d
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "842554"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a>Synchroniser les informations sur le niveau de stock entre Finance and Operations et Field Service 

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les informations au niveau du stock depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Modèles et tâches
Le modèle suivant et les tâches sous-jacentes sont utilisées pour exécuter la synchronisation aux niveaux du stock disponible de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.

**Modèle dans l'intégration de données**
- Stock produit (Fin and Ops vers Field Service)
  
**Tâche du projet d'intégration des données**
- Produit de stock

Les tâches de synchronisation suivantes sont requises avant que la synchronisation des niveaux de stock puisse avoir lieu :
- Entrepôts (Fin and Ops vers Field Service) 
- Produits Field Service avec unité de stock (Fin and Ops vers Sales) 

## <a name="entity-set"></a>Ensemble d'entités

| Field Service                      | Finance and Operations                 |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Stock CDS disponible par entrepôt     |

## <a name="entity-flow"></a>Flux d'entité
Les informations sur le niveau de stock sont envoyées de Finance and Operations vers Field Service pour certains produits. Les informations de niveau de stock comprennent : 
- La quantité disponible (quantité physique actuelle enregistrée dans l'entrepôt)
- Quantité en commande (quantité totale en commande enregistrée - c'est-à-dire commandes client)
- Quantité commandée (quantité totale commandée enregistrée - c'est-à-dire commandes fournisseur)

Ces informations sont capturées par produit lancé pour chaque entrepôt et synchronisées selon le suivi des modifications, lorsque le niveau de stock change.

Dans Field Service, la solution d'intégration crée des journaux de stock pour le delta, pour obtenir les niveaux dans Field Service pour faire correspondre les niveaux dans Finance and Operations.

Finance and Operations agira comme base pour les niveaux de stock. Il est donc important de paramétrer l'intégration pour les ordres d'exécution, les transferts et les ajustements entre Field Service et Finance and Operations si cette fonctionnalité est utilisée dans Field Service, ainsi qu'avec la synchronisation des niveaux de stock de Finance and Operations.

Les produits et les entrepôts dans lesquels les niveaux de stock sont basés sur Finance and Operations peuvent être contrôlés avec Requête et filtrage avancés (Power Query).

> [!NOTE]
> Vous pouvez créer plusieurs entrepôts dans Field Service (avec **Géré en externe = Non**), puis les mapper à un seul entrepôt dans Finance and Operations, avec la fonctionnalité de requête et de filtrage avancée. Cela est utile dans les situations où vous souhaitez que Field Service serve de base au niveau de stock détaillé et n'envoyer que des mises à jour à Finance and Operations. Dans ce cas, Field Service ne reçoit pas les mises à jour de niveau de stock de Finance and Operations. Pour en savoir plus, voir [Synchroniser les ajustements de stock entre Field Service et Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) et [Synchroniser des bons de travail de Field Service sur des commandes client de Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Solution Field Service CRM
L'entité **Stock de produits externe** est une nouvelle entité utilisée uniquement pour la partie principale dans l'intégration. Elle reçoit les valeurs de niveau de stock de Finance and Operations dans l'intégration puis les transforme en journaux de stock manuel, qui modifie ensuite les produits de stock dans l'entrepôt.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

### <a name="data-integration-project"></a>Projet d'intégration des données
Vous pouvez appliquer des filtres avec Requête et filtrage avancés afin de contrôler que seuls les produits et entrepôts souhaités envoient des informations de niveau de stock de Finance and Operations vers Field Service.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

### <a name="product-inventory-fin-and-ops-to-field-service-product-inventory"></a>Stock produit (Fin and Ops vers Field Service) : Stock produit

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)
