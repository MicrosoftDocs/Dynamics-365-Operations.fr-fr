---
title: Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Field Service
description: Cet article présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: Henrikan
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 114550f01f3aed197480fb6830fe913dbfa7b570
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860549"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Field Service

[!include[banner](../includes/banner.md)]

Cet article présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.

Le modèle **Produits Field Service (Supply Chain Management vers Field Service)** utilisé est basé sur le modèle **Produits (Supply Chain Management vers Sales) – Direct** de Prospect en disponibilités. Pour plus d’informations, voir [Produits (entre Supply Chain Management et Sales) - Direct](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Cet article décrit les différences entre les modèles **Produits Field Service (Supply Chain Management vers Field Service)** et **Produits (Supply Chain Management vers Sales) – Direct**.

## <a name="templates-and-tasks"></a>Modèles et tâches

**Nom du modèle dans l’intégration des données**

- Produits Field Service (Supply Chain Management vers Field Service)

**Nom de la tâche dans le projet d’intégration de données**

- Produits - Produits

Le modèle **Produits Field Service (Supply Chain Management vers Field Service)** utilisé inclut un mappage qui n’est pas inclus dans le modèle **Produits (Supply Chain Management vers Sales) – Direct**. Cette mise en correspondance garantit que le champ spécifique à Field Service **Type de produit de service** obligatoire est défini correctement.

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

La mise en correspondance des valeurs suivante est utilisée.

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

Dans Supply Chain Management, la valeur **Type de produit Field Service** dans l’entité de données **Produits lancés vendables** est calculée comme suit :

- **Inventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = True
- **NonInventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = False
- **Service :** Type de produit = Service

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l’intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Produits Field Service (Supply Chain Management vers Field Service) : Produits - Produits

[![Mise en correspondance de modèles dans l’intégration de données.](./media/FSProduct.png)](./media/FSProduct.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]