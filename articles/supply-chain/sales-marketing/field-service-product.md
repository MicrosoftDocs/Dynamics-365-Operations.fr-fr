---
title: Synchroniser des produits de Finance and Operations sur des produits de Field Service
description: Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 06d7ff272ecb79abded3c3d3ade1f6bc0ef1f095
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742353"
---
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a>Synchroniser des produits de Finance and Operations sur des produits de Field Service

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et la tâche sous-jacente utilisés pour synchroniser les produits depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.

Le modèle **Produits Field Service (Fin and Ops vers Field Service)** utilisé est basé sur le modèle **Produits (Fin and Ops vers Sales) – Direct** de Prospect en disponibilités. Pour plus d'informations, voir [Produits (entre Fin and Ops et Sales) - Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Cette rubrique décrit les différences entre les modèles **Produits Field Service (Fin and Ops vers Field Service)** et **Produits (Fin and Ops vers Sales) – Direct**.

## <a name="templates-and-tasks"></a>Modèles et tâches

**Nom du modèle dans l'intégration des données :**

- Produits Field Service (Fin and Ops vers Field Service)

**Nom de la tâche dans le projet d'intégration de données :**

- Produits - Produits

Le modèle **Produits Field Service (Fin and Ops vers Field Service)** inclut une mise en correspondance qui n'est pas incluse dans le modèle **Produits (Fin and Ops vers Sales) – Direct**. Cette mise en correspondance garantit que le champ spécifique à Field Service **Type de produit de service** obligatoire est défini correctement.

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

La mise en correspondance des valeurs suivante est utilisée.

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

Dans Finance and Operations, la valeur **Type de produit Field Service** dans l'entité de données **Produits lancés vendables** est calculée comme suit :

- **Inventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = True
- **NonInventory :** Type de produit = Groupe de modèles Produit et Article, Produit stocké = False
- **Service :** Type de produit = Service

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a>Produits Field Service (Fin and Ops vers Field Service) : Produits - produits

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSProduct.png)](./media/FSProduct.png)
