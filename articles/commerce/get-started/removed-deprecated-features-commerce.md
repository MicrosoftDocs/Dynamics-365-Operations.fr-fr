---
title: Fonctions supprimées ou obsolètes dans Dynamics 365 Commerce
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 64241ef1c25359c7b3b305c4e8f2b24de7e8f5e4
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2020
ms.locfileid: "3443916"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Fonctions supprimées ou obsolètes dans Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Commerce.

- Une fonction *supprimée* n'est plus disponible dans le produit.
- Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification. 

> [!NOTE]
> Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.11
### <a name="data-action-hooks"></a>Crochets d'action de données
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | La fonction de raccordement des actions de données est déconseillée en raison de problèmes de performances. |
| **Remplacé par une autre fonctionnalité ?**   | Il est recommandé d'utiliser à la place le [remplacement des actions sur les données](../e-commerce-extensibility/data-action-overrides.md) pour modifier la logique métier dans la couche d'action de données.|
| **Zones de produit affectées**         | Actions de données d'extensibilité de e-commerce |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Fonctionnement PDV 803 - Prélèvement et réception
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Les opérations de prélèvement et de réception sont obsolètes en raison de la nouvelle conception de l'opération. |
| **Remplacé par une autre fonctionnalité ?**   | Oui. Il est remplacé par deux nouvelles opérations PDV : l'opération entrante (804) et l'opération sortante (805).|
| **Zones de produit affectées**         | Application Point De Vente (PDV) |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.10, l'opération de prélèvement et de réception ne recevra plus de nouvelles mises à jour de fonctionnalités. Seules les corrections de bogues critiques seront effectuées pour cette opération dans les versions futures. Tous les clients sont encouragés à passer aux nouvelles [Opérations entrantes](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) et [Opérations sortantes](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), qui continueront à faire partie de notre feuille de route des produits à long terme. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API Commerce GetProductAvailabilities et GetAvailableInventoryNearby
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | Ces nouvelles API optimisées ont été créées pour remplacer les API GetProductAvailabilities et GetAvailableInventoryNearby. |
| **Remplacé par une autre fonctionnalité ?**   | Oui : remplacement par les API GetEstimatedAvailabilty et GetEstimatedProductWarehouseAvailability. |
| **Zones de produit affectées**         | SDK d'application e-Commerce |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à compter de la version 10.0.7, il n'y aura plus d'investissement d'ingénierie pour GetProductAvailabilities et GetAvailableInventoryNearby. Les organisations qui utilisent ces API dans leurs déploiements de commerce électronique doivent passer aux nouvelles API GetEstimatedAvailabilty et GetEstimatedProductWarehouseAvailability et activer la [fonction de calcul de la disponibilité des produits optimisée](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes
Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).
