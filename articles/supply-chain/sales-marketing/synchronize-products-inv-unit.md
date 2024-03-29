---
title: Synchroniser les produits avec l’unité de stock entre Supply Chain Management et Field Service
description: Cet article présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l’unité de stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: Henrikan
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
ms.author: henrikan
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5f7658eacd20aa69a64d6288e9d29e53b6ccb002
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887252"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Synchroniser les produits avec l’unité de stock entre Supply Chain Management et Field Service

[!include[banner](../includes/banner.md)]

Cet article présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits avec l’unité de stock depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.

[![Synchronisation des processus d’entreprise entre Supply Chain Management et Field Service.](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Le modèle **Produits Field Service avec unité de stock (Supply Chain Management vers Field Service)** est basé sur le modèle **Produits Field Service (Supply Chain Management vers Field Service)**. Pour en savoir plus, voir [Synchroniser les produits dans Supply Chain Management vers les produits dans Field Service](field-service-product.md).

Cet article décrit uniquement les différences entre les deux modèles : 
- **Produits Field Service avec unité de stock (Supply Chain Management vers Sales)**
- **Produits Field Service (Supply Chain Management vers Field Service)** 

## <a name="templates-and-tasks"></a>Modèles et tâches

**Nom du modèle dans l’intégration des données :**

- Produits Field Service avec unité de stock (Supply Chain Management vers Sales)

**Nom de la tâche dans le projet d’intégration de données :**

- Produits

Le modèle **Produits Field Service avec unité de stock (Supply Chain Management vers Field Service)** inclut une mise en correspondance qui n’est pas incluse dans le modèle **Produits Field Service (Supply Chain Management vers Field Service)**. Cette mise en correspondance garantit que l’unité de stock nécessaire pour la synchronisation de niveau de stock est incluse.

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l’intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Produits Field Service avec unité de stock (Supply Chain Management vers Field Service) : Produits

[![Mise en correspondance de modèles dans l’intégration de données.](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]