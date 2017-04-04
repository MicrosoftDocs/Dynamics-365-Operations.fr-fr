---
title: "Définir les remises spécifiques à un canal"
description: "Les détaillants définissent souvent des remises dans différents canaux. Cette rubrique passe en revue les concepts que vous devez connaître pour créer une remise à un canal spécifique."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: b2f59db59ea49925c3bb5e1d75beee95191220d0
ms.lasthandoff: 03/31/2017


---

# <a name="define-channel-specific-discounts"></a>Définir les remises spécifiques à un canal

Les détaillants définissent souvent des remises dans différents canaux. Cette rubrique passe en revue les concepts que vous devez connaître pour créer une remise à un canal spécifique. 

<a name="channel-specific-discounts"></a>Remises spécifiques à un canal
--------------------------

Les détaillants offrent souvent remises dans différents canaux. Il s'agit peut être effectué pour résoudre les conditions de marché locales ou pour qu'il traite avec les détaillants concurrentiels.

La vente au détail et le commerce dans Microsoft Dynamics 365 pour les opérations utilise des groupes de prix pour définir des remises canal- spécifiques. Les groupes de prix peuvent être affectés à une ou plusieurs des entités suivantes : canaux, catalogues, affiliations et programmes de fidélité. Cet article présente les canaux, mais les mêmes concepts s'appliquent aux remises de catalogue, aux remises d'affiliations, et aux remises pour fidélité.

## <a name="price-groups"></a>Groupes de prix
alignnone » width= "640 "d'align= " d'id= " légende\[pièce jointe\_256084 "\][groupes de prix![] (. /media/price-groups-1024x608.png)](. Le groupe de prix de /media/price-groups.png) en cliquant pour\[au détail /caption\]

Le diagramme ci-dessous illustre la relation entre les entités pouvant figurer sur une transaction (canal, catalogue, affiliation, client, carte de fidélité) et les différents types de remise pouvant être configurés. Toutes les transactions se produisent dans un canal, le canal est garanti pour être présents sur une transaction. Les entités restantes sont facultatives. Sur chaque page de données principales, il existe un lien vers une page de groupes de prix associée où vous pouvez afficher et ajouter des groupes de prix si nécessaire. Un groupe de prix est utilisé pour regrouper quatre types d'entités aux remises, les ajustements de prix, et les accords commerciaux. Nous vous recommandons que vous planifiez une stratégie de la manière dont vous nommerez vos groupes de prix pour les tenir à jour prévisionnels. Une option est d'utiliser une lettre ou de numéroter le préfixe ou le suffixe pour distinguer les différents types. Par exemple, 1 xxxxx pour des groupes de prix de canal et 2 xxxxx pour des groupes de prix du catalogue. Il existe quatre pages de recherche qui se concentrent sur chacune des entités de vente au détail qui peuvent avoir des remises associées.

-   **Groupes de prix de canal de vente au détail** : Cette page affiche la liste des canaux et des remises associés pour chaque groupe de prix.
-   **Groupes de prix du catalogue** : Cette page affiche la liste des catalogues et des remises associés pour chaque groupe de prix.
-   **Groupes de prix de fidélité** : Cette page affiche la liste des programmes de fidélité et des remises associés pour chaque groupe de prix.
-   **Groupes de prix d'affiliation** : Cette page affiche la liste des affiliations et des remises associés pour chaque groupe de prix.

## <a name="example-channel-discount-set-up"></a>Exemple de paramétrage de remise de canal
L'exemple suivant illustre les tâches impliquées dans le paramétrage d'une remise de canal.

1.  Pour cet exemple, vous avez un canal appelé **Houston**, et vous allez créer une nouvelle remise appelée **Back-to-School.**
2.  Comme la stratégie de prix et de remise inclut la possibilité de remises de canal, vous devez toujours créer un groupe de prix spécifique au canal lorsque vous créez un canal.
3.  Vous avez le groupe de prix **Houston-PG** et il est affecté au canal **Houston**.
4.  Une fois la nouvelle remise **Back-to-School** créée, vous devez cliquer sur **Groupes de prix** en haut de la page **Remise**. La page **Groupes de prix après remise** s'ouvre. Cliquez ensuite sur **Nouveau** et sélectionnez le groupe de prix **Houston-PG**.
5.  Vous pouvez désormais activer la remise et la transférer vers le canal.

 

<a name="see-also"></a>Voir également :
--------

[Price adjustments and discounts](price-adjustments-discounts.md)


