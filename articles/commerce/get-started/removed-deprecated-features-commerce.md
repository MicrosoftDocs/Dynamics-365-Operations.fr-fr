---
title: Fonctions supprimées ou déconseillées dans Dynamics 365 Commerce
description: Cet article décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer de Dynamics 365 Commerce.
author: josaw
ms.date: 07/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: a59d62ad846eed659fa4e70390ebafc40127df0f
ms.sourcegitcommit: ef56b5d0ed26e373add5dec63168e08ade40573e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9138584"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Fonctions supprimées ou déconseillées dans Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

Cet article décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer de Dynamics 365 Commerce.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification. 

> [!NOTE]
> Des informations détaillées sur les objets dans les applications de finances et d’opérations peuvent être consultés dans les [États de référence technique](/dynamics/s-e/). Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés de chaque version des applications de finances et d’opérations.

## <a name="feature-deprecation-effective-july-2022"></a>Notification d’abandon de fonctionnalités à compter de juillet 2022

### <a name="commerce-analytics-preview"></a>Commerce Analytics (version préliminaire)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’équipe Dynamics 365 Commerce a analysé l’utilisation et l’adoption de la fonctionnalité Commerce Analytics (version préliminaire), et la décision a été prise de ne plus avancer dans la mise à disposition générale de la fonctionnalité.   |
| **Remplacé par une autre fonctionnalité ?**   | Pour le moment, Commerce Analytics (version préliminaire) ne sera pas remplacé par une autre fonctionnalité ou solution. L’exportation des transactions brutes et des données de base des applications de finances et d’opérations vers Azure Data Lake reste disponible, comme expliqué dans [Exporter vers Data Lake dans les applications de finances et d’opérations](../../fin-ops-core/dev-itpro/data-entities/finance-data-azure-data-lake.md). Les partenaires et les clients peuvent tirer parti de ce flux de données pour créer des rapports d’analyse destinés à leurs besoins commerciaux.
| **Zones de produit affectées**         | Commerce Analytics (version préliminaire) |
| **Option de déploiement**              | Tout |
| **Status**                         | Nous envisagerons de désactiver cette fonctionnalité d’ici le 30 août 2022.  À partir de cette date, aucune actualisation n’aura lieu dans les rapports Power BI fournis par Commerce Analytics (version préliminaire).     |


## <a name="features-removed-or-deprecated-in-the-commerce-10025-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.25

### <a name="modern-point-of-sale-mpos"></a>Modern POS (MPOS)

L’application Modern Point of Sale (MPOS) sera obsolète dans la version 10.0.25 de Commerce et remplacée par l’application Store Commerce.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les applications en magasin sont la pierre angulaire de l’offre omnicanale Dynamics 365 Commerce. Nous innovons en permanence pour offrir des expériences de magasin modernes et intelligentes, et pour moderniser davantage notre solution, nous déployons de nouveaux ensembles de changements qui amélioreront considérablement les opérations informatiques et les expériences des utilisateurs avec nos applications en magasin existantes sur Windows. La nouvelle application Store Commerce est une mise à niveau technologique du MPOS existant. Il offre des performances, une fiabilité et une prise en charge à long terme améliorées sur la plateforme Windows et élimine le besoin de reconditionner l’application à chaque mise à jour. |
| **Remplacé par une autre fonctionnalité ?**   |  [Store Commerce](../dev-itpro/store-commerce.md) |
| **Zones de produit affectées**         | Modern POS |
| **Option de déploiement**              | Tout |
| **Status**                         | Obsolète : À partir de la version 10.0.25 de Commerce, le programme d’installation MPOS fourni via les machines virtuelles (VM) LCS sera supprimé en octobre 2023. |

## <a name="features-removed-or-deprecated-in-the-commerce-10021-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.21

[!include [banner](../includes/preview-banner.md)]

### <a name="overlapping-discounts-handling-setting-in-commerce-parameters"></a>Configuration de la gestion des remises qui se chevauchent dans les paramètres Commerce

Le paramètre **Gestion des remises qui se chevauchent** sur la page **Paramètres commerciaux** est obsolète dans la version Commerce version 10.0.21. À l’avenir, le moteur de tarification Commerce utilisera un seul algorithme pour déterminer la combinaison optimale de remises qui se chevauchent.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | <p>Le paramètre **Gestion des remises qui se chevauchent** dans les paramètres Commerce contrôle la manière dont le moteur de tarification Commerce recherche et détermine la combinaison optimale de remises qui se chevauchent. Il propose actuellement trois options :<p><ul><li> **Meilleure performance** – Cette option utilise un algorithme heuristique avancé et une méthode [classement de la valeur marginale](../optimal-combination-overlapping-discounts.md) pour hiérarchiser, évaluer et déterminer la meilleure combinaison de remises en temps opportun.</li><li>**Calcul équilibré** – Dans la base de code actuelle, cette option fonctionne exactement comme l’option **Meilleure performance**. Par conséquent, il s’agit essentiellement d’une option dupliquée.</li><li>**Calcul exhaustif** – Cette option utilise un ancien algorithme qui passe en revue toutes les combinaisons de remises possibles au moment du calcul du prix. Pour les commandes comportant des lignes et des quantités importantes, cette option peut entraîner des problèmes de performances.</li></ul><p>Pour simplifier la configuration, améliorer les performances et réduire les incidents causés par l’ancien algorithme, nous supprimerons complètement le paramètre **Gestion des remises qui se chevauchent** et mettre à jour la logique interne du moteur de tarification Commerce afin qu’il utilise désormais uniquement l’algorithme avancé (c’est-à-dire l’algorithme à l’origine de l’option **Meilleure performance**).</p> |
| **Remplacé par une autre fonctionnalité ?**   | Non. Nous recommandons aux organisations qui utilisent le commutateur d’option **Calcul équilibré** ou **Calcul exhaustif** à l’option **Meilleure performance** avant que cette fonctionnalité ne soit supprimée. |
| **Zones de produit affectées**         | Tarification et remises |
| **Option de déploiement**              | Tout |
| **État**                         | Depuis la version 10.0.21, le paramètre **Gestion des remises qui se chevauchent** sera supprimé des paramètres Commerce en octobre 2022. |

### <a name="retail-sdk-distributed-by-using-lifecycle-services"></a>SDK Retail distribué à l’aide de Lifecycle Services

Le SDK Retail est livré dans Lifecycle Services (LCS). Ce mode de distribution est déconseillé dans la version 10.0.21. À l’avenir, les packages de référence, bibliothèques et exemples du SDK Retail seront publiés dans des référentiels publics sur GitHub.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Le SDK Retail est livré dans LCS. Le processus LCS prend quelques heures et doit être répété pour chaque mise à jour. À l’avenir, les packages de référence, bibliothèques et exemples du SDK Retail seront publiés dans des référentiels publics sur GitHub. Les échantillons d’extension et les packages de référence peuvent être consommés facilement et les mises à jour se terminent en quelques minutes. |
| **Remplacé par une autre fonctionnalité ?**   |  [Télécharger les exemples et les packages de référence du SDK Retail depuis GitHub et NuGet](../dev-itpro/retail-sdk/sdk-github.md) |
| **Zones de produit affectées**         | Kit de développement logiciel (SDK) Retail |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : à partir de la version 10.0.21, le SDK fourni via les machines virtuelles LCS sera supprimé en octobre 2023. |

### <a name="retail-deployable-package-and-combined-pos-hardware-station-and-cloud-scale-unit-installers"></a>Package déployable Retail et programmes d’installation combinés de points de vente, de stations matérielles et d’unité d’échelle Cloud

Les packages déployables pour la vente au détail générés à l’aide du SDK Retail MSBuild sont obsolètes dans la version 10.0.21. À l’avenir, utilisez le package Cloud Scale Unit (CSU) pour les extensions d’unité Cloud Scale (Commerce Runtime, base de données de canaux, API Commerce sans affichage, paiements et point de vente (PDV) Cloud). Utilisez des programmes d’installation d’extension uniquement pour le point de vente, la station matérielle et l’unité d’échelle Cloud auto-hébergée.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Un package déployable Retail est un package combiné qui contient un ensemble complet de packages d’extension et de programmes d’installation. Ce package combiné rend le déploiement complexe, car les extensions CSU vont à l’unité d’échelle Cloud et les programmes d’installation sont déployés dans les magasins. Les programmes d’installation incluent l’extension et le produit de base, ce qui rend les mises à jour difficiles. À chaque mise à niveau, une fusion de code et une génération de package sont nécessaires. Pour simplifier ce processus, les packages d’extension sont désormais séparés en composants pour un déploiement et une gestion faciles. Avec la nouvelle approche, les programme d’installation d’extensions et de produits de base sont séparés et peuvent être gérés et mis à niveau indépendamment sans fusion de code ni reconditionnement.|
| **Remplacé par une autre fonctionnalité ?**   | Extensions CSU, programmes d’installation d’extension PDV, programmes d’installation d’extension de station matérielle |
| **Zones de produit affectées**         | Déploiement et extension Dynamics 365 Commerce |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : à partir de la version 10.0.21, la prise en charge du déploiement de RetailDeployablePackage dans LCS sera supprimée en octobre 2022. |

Pour plus d’informations, voir :

+ [Générer un package distinct pour Commerce Cloud Scale Unit (CSU)](../dev-itpro/retail-sdk/retail-sdk-packaging.md#generate-a-separate-package-for-commerce-cloud-scale-unit-csu)
+ [Créer un package d’extension Modern POS](../dev-itpro/pos-extension/mpos-extension-packaging.md)
+ [Intégrer le PDV à un nouveau périphérique matériel](../dev-itpro/hardware-device-extension.md)
+ Exemples de code
    + [Cloud Scale Unit](https://github.com/microsoft/Dynamics365Commerce.ScaleUnit)
    + [PDV, CSU et station matérielle](https://github.com/microsoft/Dynamics365Commerce.InStore)

### <a name="modernpossln-and-cloudpossln-in-the-retail-sdk"></a>ModernPos.Sln et CloudPos.sln dans le SDK Retail

Le développement d’extensions PDV à l’aide de ModernPos.sln, CloudPos.sln, POS.Extension.csproj et du dossier POS est obsolète dans la version 10.0.21. À l’avenir, utilisez le SDK de conditionnement indépendant du PDV pour les extensions PDV.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Dans les versions antérieures du SDK Retail, s’il existe des extensions PDV, une fusion de code et un reconditionnement sont nécessaires pour mettre à jour vers la dernière version du PDV. La fusion de code était un processus de mise à niveau fastidieux et vous deviez tenir à jour le SDK Retail complet dans le référentiel. Vous deviez également compiler le projet de base POS.App. En utilisant le modèle de conditionnement indépendant, vous ne devez tenir à jour que votre extension. Le processus de mise à jour vers la dernière version des extensions PDV est aussi simple que la mise à jour de la version du package NuGet que votre projet consomme. Les extensions peuvent être déployées indépendamment et les services utilisent les programmes d’installation d’extensions. Le point de vente de base peut être déployé et tenu à jour séparément, et aucune fusion de code ou reconditionnement avec le programme d’installation ou le code de base n’est requis. |
| **Remplacé par une autre fonctionnalité ?**   | [Kit de développement logiciel (SDK) de conditionnement indépendant du PDV](../dev-itpro/pos-extension/pos-extension-getting-started.md) |
| **Zones de produit affectées**         | Déploiement et extension PDV Dynamics 365 Commerce |
| **Option de déploiement**              | Tous |
| **État**                         | Obsolète : à partir de la version 10.0.21, la prise en charge des packages de point de vente combinés et du modèle d’extension utilisant ModernPos.Sln, CloudPOs.sln et POS.Extensons.csproj dans le SDK Retail sera supprimée en octobre 2023. |

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.17

### <a name="full-dataset-generation-interval-is-deprecated"></a>L’intervalle de génération complet de l’ensemble de données est obsolète

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | À partir de cette version, dans le formulaire **Paramètres du planificateur Commerce** dans Dynamics 365 Headquarters, le champ **Intervalle de génération de l’ensemble de données complet en jours** sera obsolète. À partir de cette version également, le champ sera supprimé visuellement afin que la valeur ne puisse pas être modifiée. Cela restera comme la valeur **0**. |
| **Remplacé par une autre fonctionnalité ?**   | Non |
| **Zones de produit affectées**         | Dynamics 365 Commerce |
| **Option de déploiement**              | Tous|
| **État**                         | Obsolète. N’utilisez pas ce champ et ne modifiez pas sa valeur.|

## <a name="features-removed-or-deprecated-in-the-commerce-10015-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La prise en charge d’Internet Explorer 11 pour Dynamics 365 est obsolète

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Depuis décembre 2020, la prise en charge de tous les produits Dynamics 365 dans Microsoft Internet Explorer 11 est obsolète et Internet Explorer 11 ne sera plus pris en charge après août 2021.<br><br>Cela aura un impact sur les clients qui utilisent des produits Dynamics 365 conçus pour être utilisés via une interface Internet Explorer 11. Après août 2021, Internet Explorer 11 ne sera pas pris en charge pour ces produits Dynamics 365. |
| **Remplacé par une autre fonctionnalité ?**   | Nous recommandons aux clients de passer à Microsoft Edge.|
| **Zones de produit affectées**         | Tous les produits Dynamics 365 |
| **Option de déploiement**              | Tout|
| **État**                         | Obsolète. Internet Explorer 11 ne sera plus pris en charge après août 2021.|

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.11
### <a name="data-action-hooks"></a>Crochets d’action de données
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La fonction de raccordement des actions de données est déconseillée en raison de problèmes de performances. |
| **Remplacé par une autre fonctionnalité ?**   | Nous recommandons d’utiliser le [remplacement des actions sur les données](../e-commerce-extensibility/data-action-overrides.md) pour modifier la logique métier dans la couche d’action de données.|
| **Zones de produit affectées**         | Actions de données d’extensibilité du commerce électronique |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Prise en charge du SDK Retail pour Visual Studio 2015, msbuild 14.0 et les bibliothèques et outils Retail SDK\Référence
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | La prise en charge du SDK Retail pour Visual Studio 2015 est obsolète et a été mise à jour pour prendre en charge VS 2017, msbuild 15.0 et toutes les bibliothèques de référence et les outils de génération de proxy de commerce dans le dossier RetailSDK\Références qui ont été déplacés dans des packages NuGet pour simplifier le modèle d’extension et le processus de mise à niveau du SDK.|
| **Remplacé par une autre fonctionnalité ?**   | Nous vous recommandons de suivre les instructions de la section [Migrer le SDK Retail de Visual Studio 2015 à Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) pour mettre à jour votre système. |
| **Zones de produit affectées**         | Extensions du SDK Retail |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Extension Retail Server utilisant IEdmModelExtender et CommerceController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’extension Retail Server utilisant IEdmModelExtender et CommerceController est déconseillée pour fournir un modèle d’extension simplifié. La nouvelle implémentation n’aura que la classe Controller sans implémentation de classe IEdmModelExtender supplémentaire. Cela évite également la dépendance à une version OData particulière (si la version OData est mise à jour, elle peut empêcher le fonctionnement des extensions.) |
| **Remplacé par une autre fonctionnalité ?**   |  Nous vous recommandons d’utiliser le modèle d’extension de classe IController en important le package NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Zones de produit affectées**         | Extensions de Retail Server |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Extension de la station matérielle utilisant IHardwareStationController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | L’extension de station matérielle utilisant IHardwareStationController est déconseillée pour fournir un modèle d’extension simplifié. La nouvelle implémentation n’aura que la classe IController sans aucune implémentation de classe supplémentaire et pour éviter la dépendance aux bibliothèques de station matérielle de base ; l’extension nécessitait auparavant de faire référence à plusieurs bibliothèques. |
| **Remplacé par une autre fonctionnalité ?**   | Il est recommandé d’utiliser le modèle d’extension de classe IController en important le package NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Zones de produit affectées**         | Extensions de station matérielle |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Fonctionnement PDV 803 - Prélèvement et réception
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Les opérations de prélèvement et de réception sont obsolètes en raison de la nouvelle conception de l’opération. |
| **Remplacé par une autre fonctionnalité ?**   | Oui. Il est remplacé par deux nouvelles opérations PDV : l’opération entrante (804) et l’opération sortante (805).|
| **Zones de produit affectées**         | Application Point De Vente (PDV) |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à partir de la version 10.0.10, l’opération de prélèvement et de réception ne recevra plus de nouvelles mises à jour de fonctionnalités. Seules les corrections de bogues critiques seront effectuées pour cette opération dans les versions futures. Tous les clients sont encouragés à passer aux nouvelles [Opérations entrantes](../pos-inbound-inventory-operation.md) et [Opérations sortantes](../pos-outbound-inventory-operation.md), qui continueront à faire partie de notre feuille de route des produits à long terme. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Fonctions supprimées ou obsolètes dans Commerce version 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API Commerce GetProductAvailabilities et GetAvailableInventoryNearby
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motif de l’abandon/de la suppression** | Ces nouvelles API optimisées ont été créées pour remplacer les API GetProductAvailabilities et GetAvailableInventoryNearby. |
| **Remplacé par une autre fonctionnalité ?**   | Oui : remplacement par les API GetEstimatedAvailabilty et GetEstimatedProductWarehouseAvailability. |
| **Zones de produit affectées**         | SDK d’application e-Commerce |
| **Option de déploiement**              | Tout |
| **État**                         | Obsolète : à compter de la version 10.0.7, il n’y aura plus d’investissement d’ingénierie pour GetProductAvailabilities et GetAvailableInventoryNearby. Les organisations qui utilisent ces API dans leurs déploiements de commerce électronique doivent passer aux nouvelles API GetEstimatedAvailabilty et GetEstimatedProductWarehouseAvailability et activer la [fonction de calcul de la disponibilité des produits optimisée](../calculated-inventory-retail-channels.md).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annonces précédentes sur les fonctions supprimées ou obsolètes
Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

