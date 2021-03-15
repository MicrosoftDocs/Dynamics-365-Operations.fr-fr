---
title: Synchroniser les transferts et les ajustements de stock depuis Field Service vers Supply Chain Management
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements de stock et les transferts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: a598f0356034a22ee7fc0902360b8862a1944558
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010970"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>Synchroniser les transferts et les ajustements de stock depuis Field Service vers Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ajustements de stock et les transferts depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Field Service.

[![Synchronisation des processus d'entreprise entre Supply Chain Management et Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Modèles et tâches
Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les ajustements de stock et les transferts depuis Field Service vers Supply Chain Management.

**Modèles dans l'intégration de données**
- Ajustement de stock (Field Service vers Supply Chain Management)
- Transferts de stock (Field Service vers Supply Chain Management)

**Tâches des projets d'intégration des données**
- Ajustements de stock
- Transferts de stock

## <a name="table-set"></a>Ensemble de tables
| Field Service                     | Gestion de la chaîne d'approvisionnement                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts | En-têtes et lignes du journal d'ajustement de stock de Dataverse |
| msdyn_inventoryadjustmentproducts | En-têtes et lignes du journal de transfert de stock de Dataverse   |

## <a name="table-flow"></a>Flux de table
Les ajustements et les transferts de stock effectués dans Field Service se synchronisent sur Supply Chain Management, une fois que le **Statut de validation** passe de **Créé** à **Validé**. Dans ce cas, l'ajustement ou l'ordre de transfert est verrouillé et passe en lecture seule. Cela signifie que les ajustements et les transferts peuvent être validés dans Supply Chain Management, mais ne peuvent pas être modifiés. Dans Supply Chain Management, vous pouvez paramétrer un traitement par lots pour valider automatiquement les journaux d'ajustements et de transferts de stock générés par l'intégration. Voir les prérequis ci-dessous pour plus d'informations sur la procédure d'activation du traitement par lots.

## <a name="field-service-crm-solution"></a>Solution Field Service CRM 
La colonne **Unité de stock** a été ajoutée à la table **Produit**. Cette colonne est nécessaire, car l'unité de vente et de stock n'est pas toujours la même dans Supply Chain Management, et l'unité de stock est nécessaire pour le stock de l'entrepôt dans Supply Chain Management.
Lorsque vous définissez le produit sur un produit d'ajustement de stock pour les ajustements de stock et les transferts de stock, l'unité est extraite de la valeur du produit de stock. Si une valeur est trouvée, la colonne **Unité** est verrouillée sur le produit d'ajustement de stock.

La colonne **Statut de validation** a été ajoutée à la table **Ajustement de stock** et à la table **Transfert de stock**. Cette colonne est utilisée comme filtre lorsqu'un ajustement ou un transfert est envoyé à Supply Chain Management. La valeur par défaut pour cette colonne est Créé (1), mais elle n'est pas envoyée à Supply Chain Management. Lorsque vous mettez à jour la valeur sur Validé (2), il est envoyé à Supply Chain Management, mais vous ne pourrez ensuite plus rien modifier dans Ajustement ou Transfert, ni ajouter aucune ligne à celui-ci.

La colonne **Souche de numéros** a été ajoutée à la table **Produit d'ajustement de stock**. Cette colonne garantit que l'intégration a un numéro unique, et que l'intégration peut créer et mettre à jour l'ajustement. Lorsque vous créez votre premier produit d'ajustement de stock, un enregistrement sera créé dans la table **P2C AutoNumber** pour tenir à jour la souche de numéros et le préfixe utilisé.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

### <a name="supply-chain-management"></a>Gestion de la chaîne d'approvisionnement
Les journaux de stock d'intégration générés par l'intégration peuvent être automatiquement validés avec un traitement par lots. Pour cela, accédez à : **Gestion des stocks > Tâches périodiques > Intégration de Dataverse > Valider les journaux de stock pour l'intégration**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>Ajustement de stock (Field Service vers Supply Chain Management) : ajustement de stock

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>Transfert de stock (Field Service vers Supply Chain Management) : transfert de stock

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSTrans1.png)](./media/FSTrans1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]