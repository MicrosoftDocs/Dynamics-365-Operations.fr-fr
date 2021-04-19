---
title: Synchroniser les informations sur le niveau de stock depuis Supply Chain Management vers Field Service
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les informations au niveau du stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 05/07/2019
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
ms.openlocfilehash: c0db0c143abb8ce26a4a3007845050e4ddb02363
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840579"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a>Synchroniser les informations sur le niveau de stock depuis Supply Chain Management vers Field Service 

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les informations au niveau du stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.

[![Synchronisation des processus d’entreprise entre Supply Chain Management et Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Modèles et tâches
Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les niveaux disponibles en stock et les transferts depuis Supply Chain Management vers Field Service.

**Modèle dans l’intégration de données**
- Stock de produit (Supply Chain Management vers Field Service)
  
**Tâche du projet d’intégration des données**
- Produit de stock

Les tâches de synchronisation suivantes sont requises avant que la synchronisation des niveaux de stock puisse avoir lieu :
- Entrepôts (Supply Chain Management vers Field Service) 
- Produits Field Service avec unité de stock (Supply Chain Management vers Sales) 

## <a name="entity-set"></a>Ensemble d’entités

| Field Service                      | Gestion de la chaîne d’approvisionnement                |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Stock de Dataverse disponible par entrepôt     |

## <a name="entity-flow"></a>Flux d’entité
Les informations sur le niveau de stock sont envoyées de Finance and Operations vers Field Service pour certains produits. Les informations de niveau de stock comprennent : 
- La quantité disponible (quantité physique actuelle enregistrée dans l’entrepôt)
- Quantité en commande (quantité totale en commande enregistrée - c’est-à-dire commandes client)
- Quantité commandée (quantité totale commandée enregistrée - c’est-à-dire commandes fournisseur)

Ces informations sont capturées par produit lancé pour chaque entrepôt et synchronisées selon le suivi des modifications, lorsque le niveau de stock change.

Dans Field Service, la solution d’intégration crée des journaux de stock pour le delta, pour obtenir les niveaux dans Field Service pour faire correspondre les niveaux dans Supply Chain Management.

Supply Chain Management agira comme base pour les niveaux de stock. Il est donc important de paramétrer l’intégration pour les ordres d’exécution, les transferts et les ajustements entre Field Service et Supply Chain Management si cette fonctionnalité est utilisée dans Field Service, ainsi qu’avec la synchronisation des niveaux de stock de Supply Chain Management.

Les produits et les entrepôts dans lesquels les niveaux de stock sont basés sur Supply Chain Management peuvent être contrôlés avec Requête et filtrage avancés (Power Query).

> [!NOTE]
> Vous pouvez créer plusieurs entrepôts dans Field Service (avec **Géré en externe = Non**), puis les mapper à un seul entrepôt dans Supply Chain Management, avec la fonctionnalité de requête et de filtrage avancée. Cela est utile dans les situations où vous souhaitez que Field Service serve de base au niveau de stock détaillé et n’envoyer que des mises à jour à Supply Chain Management. Dans ce cas, Field Service ne reçoit pas les mises à jour de niveau de stock de Supply Chain Management. Pour en savoir plus, voir [Synchroniser les ajustements de stock entre Field Service et Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) et [Synchroniser des bons de travail de Field Service sur des commandes client de Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Solution Field Service CRM
L’entité **Stock de produits externe** est une nouvelle entité utilisée uniquement pour la partie principale dans l’intégration. Elle reçoit les valeurs de niveau de stock de Supply Chain Management dans l’intégration puis les transforme en journaux de stock manuel, qui modifie ensuite les produits de stock dans l’entrepôt.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

### <a name="data-integration"></a>Intégration de données
Pour que le projet fonctionne, vous devez vous assurer que la Clé d’intégration est mise à jour pour msdynce_externalproductinventories.
1.  Accédez à **Intégration de données > Ensembles de connexions**.
2.  Sélectionnez l’Ensemble de connexions utilisé.
3.  Dans l’onglet **Clé d’intégration**, assurez-vous que les clés suivantes sont ajoutées à msdynce_externalproductinventories :
      - msdynce_productnumber (numéro de produit)
      - msdynce_warehouseid (ID entrepôt)
      
### <a name="data-integration-project"></a>Projet d’intégration des données
Vous pouvez appliquer des filtres avec Requête et filtrage avancés afin de contrôler que seuls les produits et entrepôts souhaités envoient des informations de niveau de stock de Supply Chain Management vers Field Service.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l’intégration de données

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a>Stock de produit (Supply Chain Management vers Field Service) : stock de produit

[![Mise en correspondance de modèles dans l’intégration de données](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]