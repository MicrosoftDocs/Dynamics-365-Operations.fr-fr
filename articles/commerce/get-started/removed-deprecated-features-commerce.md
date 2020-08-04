---
title: Fonctions supprimées ou obsolètes dans Dynamics 365 Commerce
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 07/07/2020
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
ms.openlocfilehash: aa18e7446a72a907fcad70f92ea529088b6cecbd
ms.sourcegitcommit: 83c7e5ab54c1cad2e21e33769cc524cfa4213f58
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2020
ms.locfileid: "3539877"
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
| **Remplacé par une autre fonctionnalité ?**   | Nous recommandons d'utiliser le [remplacement des actions sur les données](../e-commerce-extensibility/data-action-overrides.md) pour modifier la logique métier dans la couche d'action de données.|
| **Zones de produit affectées**         | Actions de données d'extensibilité du commerce électronique |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Prise en charge du SDK Retail pour Visual Studio 2015, msbuild 14.0 et les bibliothèques et outils Retail SDK\Référence
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | La prise en charge du SDK Retail pour Visual Studio 2015 est obsolète et a été mise à jour pour prendre en charge VS 2017, msbuild 15.0 et toutes les bibliothèques de référence et les outils de génération de proxy de commerce dans le dossier RetailSDK\Références qui ont été déplacés dans des packages NuGet pour simplifier le modèle d'extension et le processus de mise à niveau du SDK.|
| **Remplacé par une autre fonctionnalité ?**   | Nous vous recommandons de suivre les instructions de la section [Migrer le SDK Retail de Visual Studio 2015 à Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) pour mettre à jour votre système. |
| **Zones de produit affectées**         | Extensions du SDK Retail |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Extension Retail Server utilisant IEdmModelExtender et CommerceController
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | L'extension Retail Server utilisant IEdmModelExtender et CommerceController est déconseillée pour fournir un modèle d'extension simplifié. La nouvelle implémentation n'aura que la classe Controller sans implémentation de classe IEdmModelExtender supplémentaire. Cela évite également la dépendance à une version OData particulière (si la version OData est mise à jour, elle peut empêcher le fonctionnement des extensions.) |
| **Remplacé par une autre fonctionnalité ?**   |  Nous vous recommandons d'utiliser le modèle d'extension de classe IController en important le package NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Zones de produit affectées**         | Extensions de Retail Server |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Extension de la station matérielle utilisant IHardwareStationController
|   |  |
|------------|--------------------|
| **Motif de l'abandon/de la suppression** | L'extension de station matérielle utilisant IHardwareStationController est déconseillée pour fournir un modèle d'extension simplifié. La nouvelle implémentation n'aura que la classe IController sans aucune implémentation de classe supplémentaire et pour éviter la dépendance aux bibliothèques de station matérielle de base ; l'extension nécessitait auparavant de faire référence à plusieurs bibliothèques. |
| **Remplacé par une autre fonctionnalité ?**   | Il est recommandé d'utiliser le modèle d'extension de classe IController en important le package NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Zones de produit affectées**         | Extensions de station matérielle |
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
