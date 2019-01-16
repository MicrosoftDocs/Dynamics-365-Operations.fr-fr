---
title: Synchroniser les transferts et les ajustements de stock entre Field Service et Finance and Operations
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements et transferts de stock de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: fr-fr
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Synchroniser les ajustements de stock entre Field Service et Finance and Operations

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements et transferts de stock de Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Field Service.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Modèles et tâches
Les modèle et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des ajustements et transferts de stock de Microsoft Dynamics 365 for Field Service vers Microsoft Dynamics 365 for Finance and Operations.

**Nom des modèles dans l'intégration des données :**
- Ajustement de stock (Field Service vers Finance and Operations)
- Transferts de stock (Field Service vers Finance and Operations)

**Noms des tâches dans les projets d'intégration de données :**
- Ajustements de stock
- Transferts de stock

## <a name="entity-set"></a>Ensemble d'entités
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   En-têtes et lignes du journal d'ajustement de stock CDS |
| msdyn_inventoryadjustmentproducts | En-têtes et lignes du journal de transfert de stock CDS   |

## <a name="entity-flow"></a>Flux d'entité
Les ajustements et les transferts de stock effectués dans Field Service se synchronisent sur Finance and Operations, une fois que le **Statut de validation** passe de Créé à Validé. Dans ce cas, l'ordre d'ajustement ou de transfert est verrouillé et passe en lecture seule, car les ajustements et les transferts peuvent être validés dans Finance and Operations, et par conséquent ne peuvent pas être modifiés.
Dans Finance and Operations, vous pouvez paramétrer un traitement par lots pour valider automatiquement les journaux d'ajustements et de transferts de stock générés par l'intégration. Voir les prérequis ci-dessous pour plus d'informations sur la procédure d'activation du traitement par lots.

## <a name="field-service-crm-solution"></a>Solution Field Service CRM 
Le champ Unité de stock a été ajouté à l'entité Produit. Ce champ est nécessaire, car unité de vente et l'unité de stock ne sont pas toujours les mêmes dans Operations, et pour le stock de l'entrepôt dans les opérations nous avons besoin de l'unité de stock.
Lorsque vous définissez le produit sur un produit d'ajustement de stock pour les ajustements de stock et les transferts de stock, l'unité est extraite de la valeur du produit de stock de produits. Si une valeur est trouvée, le champ Unité est verrouillé sur le produit d'ajustement de stock

Le champ Statut de validation a été ajouté à l'entité Ajustement de stock et à l'entité Transfert de stock. Ce champ est utilisé comme filtre lorsqu'un ajustement ou un transfert est envoyé à Operations. La valeur par défaut du champ est Créé (1) et n'est ensuite pas envoyé à Operations. Une fois que vous le modifiez avec Validé (2), il est envoyé à Operations, mais vous ne pourrez ensuite plus rien modifier dans Ajustement ou Transfert, ni ajouter aucune ligne à celui-ci.
Le champ Souche de numéros a été ajouté à l'entité Produit d'ajustement de stock. Ce champ permet à l'intégration de disposer d'un numéro unique, afin qu'elle sache quand effectuer des créations et quand effectuer des mises à jour. Lorsque vous créez votre premier produit d'ajustement de stock, cela entraîne la création d'un enregistrement dans l'entité P2C AutoNumber afin de tenir à jour la souche de numéros et le préfixe utilisé.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

### <a name="in-finance-and-operations"></a>Dans Finance and Operations
Les journaux de stock d'intégration générés par l'intégration peuvent être automatiquement validés avec un traitement par lots. Pour cela, accédez à : Gestion des stocks > Tâches périodiques > Intégration CDS > Valider les journaux de stock pour l'intégration

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a>Ajustement de stock (Field Service vers Finance and Operations) : Ajustement de stock

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a>Transfert de stock (Field Service vers Finance and Operations) : Transfert de stock

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSTrans1.png)](./media/FSTrans1.png)

