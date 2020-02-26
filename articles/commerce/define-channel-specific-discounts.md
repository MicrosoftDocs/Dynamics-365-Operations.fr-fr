---
title: Définir les remises spécifiques à un canal
description: Les détaillants définissent souvent des remises dans différents canaux. Cette rubrique passe en revue les concepts que vous devez connaître pour créer une remise à un canal spécifique.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 539a6f2df46450c5e0fd18ba69501432d6f3fbdd
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022478"
---
# <a name="define-channel-specific-discounts"></a>Définir les remises spécifiques à un canal

[!include [banner](includes/banner.md)]

Cette rubrique passe en revue les concepts que vous devez connaître pour créer une remise à un canal spécifique.

## <a name="channel-specific-discounts"></a>Remises spécifiques à un canal

Les détaillants offrent souvent des remises dans différents canaux afin de répondre à des conditions de marché locales ou pour faire face à la concurrence.

Commerce utilise des groupes de prix pour définir des remises spécifiques aux canaux. Les groupes de prix peuvent être affectés à une ou plusieurs des entités suivantes : canaux, catalogues, affiliations et programmes de fidélité. Cet article présente les canaux, mais les mêmes concepts s'appliquent aux remises de catalogue, aux remises d'affiliations, et aux remises pour fidélité.

## <a name="price-groups"></a>Groupes de prix

[![Groupes de prix](./media/price-groups-1024x608.png)](./media/price-groups.png)

Le diagramme ci-dessus illustre la relation entre les entités pouvant être sur une transaction (canal, catalogue, affiliation, client, carte de fidélité) et les différents types de remise qui peuvent être configurés. Toutes les transactions ont lieu dans un canal, celui-ci a donc la garantie d'être présent dans une transaction. Les entités restantes sont facultatives. Sur chaque page de données principales, il existe un lien vers une page de groupes de prix associée où vous pouvez afficher et ajouter des groupes de prix si nécessaire. Un groupe de prix permet d'associer quatre types d'entités avec des remises, des ajustements de prix et des accords commerciaux. Il est recommandé de planifier une stratégie pour savoir comment nommer vos groupes de prix pour les tenir à jour. Une option consiste à utiliser un préfixe ou un suffixe sous forme de lettre ou de numéro pour distinguer les différents types. Par exemple, 1 xxxxx pour des groupes de prix de canal et 2 xxxxx pour des groupes de prix de catalogue. Il existe quatre pages de recherche qui se concentrent sur chacune des entités de Commerce qui peuvent avoir des remises associées.

- **Groupes de prix de canal** : cette page affiche la liste des canaux et des remises associés pour chaque groupe de prix.
- **Groupes de prix du catalogue** : Cette page affiche la liste des catalogues et des remises associés pour chaque groupe de prix.
- **Groupes de prix de fidélité** : Cette page affiche la liste des programmes de fidélité et des remises associés pour chaque groupe de prix.
- **Groupes de prix d'affiliation** : Cette page affiche la liste des affiliations et des remises associés pour chaque groupe de prix.

## <a name="example-channel-discount-set-up"></a>Exemple de paramétrage de remise de canal

L'exemple suivant illustre les tâches impliquées dans le paramétrage d'une remise de canal.

1. Pour cet exemple, vous avez un canal appelé **Houston**, et vous allez créer une remise appelée **Back-to-School**.
2. Comme la stratégie de prix et de remise inclut la possibilité de remises de canal, vous devez toujours créer un groupe de prix spécifique au canal lorsque vous créez un canal.
3. Vous avez le groupe de prix **Houston-PG** et il est affecté au canal **Houston**.
4. Une fois la nouvelle remise **Back-to-School** créée, vous devez cliquer sur **Groupes de prix** en haut de la page **Remise**. La page **Groupes de prix après remise** s'ouvre. Cliquez ensuite sur **Nouveau** et sélectionnez le groupe de prix **Houston-PG**.
5. Vous pouvez désormais activer la remise et la transférer vers le canal.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajustements de prix et remises](price-adjustments-discounts.md)
