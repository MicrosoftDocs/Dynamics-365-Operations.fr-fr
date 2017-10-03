---
title: "Définir les remises spécifiques à un canal"
description: "Les détaillants définissent souvent des remises dans différents canaux. Cette rubrique passe en revue les concepts que vous devez connaître pour créer une remise à un canal spécifique."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: d40c37628f03a7605e04b95339072a67806f2fa1
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017

---

# <a name="define-channel-specific-discounts"></a>Définir les remises spécifiques à un canal

[!include[banner](includes/banner.md)]


Les détaillants définissent souvent des remises dans différents canaux. Cette rubrique passe en revue les concepts que vous devez connaître pour créer une remise à un canal spécifique. 

<a name="channel-specific-discounts"></a>Remises spécifiques à un canal
--------------------------

Les détaillants offrent souvent des remises dans différents canaux afin de répondre à des conditions de marché locales ou pour faire face à la concurrence.

Microsoft Dynamics 365 for Retail utilise des groupes de prix pour définir des remises spécifiques à un canal. Les groupes de prix peuvent être affectés à une ou plusieurs des entités suivantes : canaux, catalogues, affiliations et programmes de fidélité. Cet article présente les canaux, mais les mêmes concepts s'appliquent aux remises de catalogue, aux remises d'affiliations, et aux remises pour fidélité.

## <a name="price-groups"></a>Groupes de prix

[![Groupes de prix](./media/price-groups-1024x608.png)](./media/price-groups.png)

Le diagramme ci-dessus illustre la relation entre les entités pouvant être sur une transaction (canal, catalogue, affiliation, client, carte de fidélité) et les différents types de remise qui peuvent être configurés. Toutes les transactions ont lieu dans un canal, celui-ci a donc la garantie d'être présent dans une transaction. Les entités restantes sont facultatives. Sur chaque page de données principales, il existe un lien vers une page de groupes de prix associée où vous pouvez afficher et ajouter des groupes de prix si nécessaire. Un groupe de prix permet d'associer quatre types d'entités avec des remises, des ajustements de prix et des accords commerciaux. Il est recommandé de planifier une stratégie pour savoir comment nommer vos groupes de prix pour les tenir à jour. Une option consiste à utiliser un préfixe ou un suffixe sous forme de lettre ou de numéro pour distinguer les différents types. Par exemple, 1 xxxxx pour des groupes de prix de canal et 2 xxxxx pour des groupes de prix de catalogue. Il existe quatre pages de recherche qui se concentrent sur chacune des entités de vente au détail qui peuvent avoir des remises associées.

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

[Ajustements de prix et remises](price-adjustments-discounts.md)



