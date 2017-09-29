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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a0286ab72d7fa6b40228dfdcabde00bee9995d74
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---

# <a name="define-channel-specific-discounts"></a><span data-ttu-id="7104b-104">Définir les remises spécifiques à un canal</span><span class="sxs-lookup"><span data-stu-id="7104b-104">Define channel-specific discounts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="7104b-105">Les détaillants définissent souvent des remises dans différents canaux.</span><span class="sxs-lookup"><span data-stu-id="7104b-105">Retailers often set different discounts in different channels.</span></span> <span data-ttu-id="7104b-106">Cette rubrique passe en revue les concepts que vous devez connaître pour créer une remise à un canal spécifique.</span><span class="sxs-lookup"><span data-stu-id="7104b-106">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span> 

<a name="channel-specific-discounts"></a><span data-ttu-id="7104b-107">Remises spécifiques à un canal</span><span class="sxs-lookup"><span data-stu-id="7104b-107">Channel-specific discounts</span></span>
--------------------------

<span data-ttu-id="7104b-108">Les détaillants offrent souvent des remises dans différents canaux</span><span class="sxs-lookup"><span data-stu-id="7104b-108">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="7104b-109">afin de répondre à des conditions de marché locales ou pour faire face à la concurrence.</span><span class="sxs-lookup"><span data-stu-id="7104b-109">This is may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="7104b-110">Microsoft Dynamics 365 for Retail utilise des groupes de prix pour définir des remises spécifiques à un canal.</span><span class="sxs-lookup"><span data-stu-id="7104b-110">Microsoft Dynamics 365 for Retail uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="7104b-111">Les groupes de prix peuvent être affectés à une ou plusieurs des entités suivantes : canaux, catalogues, affiliations et programmes de fidélité.</span><span class="sxs-lookup"><span data-stu-id="7104b-111">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="7104b-112">Cet article présente les canaux, mais les mêmes concepts s'appliquent aux remises de catalogue, aux remises d'affiliations, et aux remises pour fidélité.</span><span class="sxs-lookup"><span data-stu-id="7104b-112">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="7104b-113">Groupes de prix</span><span class="sxs-lookup"><span data-stu-id="7104b-113">Price groups</span></span>

<span data-ttu-id="7104b-114">[![Groupes de prix](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="7104b-114">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="7104b-115">Le diagramme ci-dessus illustre la relation entre les entités pouvant être sur une transaction (canal, catalogue, affiliation, client, carte de fidélité) et les différents types de remise qui peuvent être configurés.</span><span class="sxs-lookup"><span data-stu-id="7104b-115">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="7104b-116">Toutes les transactions ont lieu dans un canal, celui-ci a donc la garantie d'être présent dans une transaction.</span><span class="sxs-lookup"><span data-stu-id="7104b-116">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="7104b-117">Les entités restantes sont facultatives.</span><span class="sxs-lookup"><span data-stu-id="7104b-117">The remaining entities are optional.</span></span> <span data-ttu-id="7104b-118">Sur chaque page de données principales, il existe un lien vers une page de groupes de prix associée où vous pouvez afficher et ajouter des groupes de prix si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="7104b-118">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="7104b-119">Un groupe de prix permet d'associer quatre types d'entités avec des remises, des ajustements de prix et des accords commerciaux.</span><span class="sxs-lookup"><span data-stu-id="7104b-119">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="7104b-120">Il est recommandé de planifier une stratégie pour savoir comment nommer vos groupes de prix pour les tenir à jour.</span><span class="sxs-lookup"><span data-stu-id="7104b-120">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="7104b-121">Une option consiste à utiliser un préfixe ou un suffixe sous forme de lettre ou de numéro pour distinguer les différents types.</span><span class="sxs-lookup"><span data-stu-id="7104b-121">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="7104b-122">Par exemple, 1 xxxxx pour des groupes de prix de canal et 2 xxxxx pour des groupes de prix de catalogue.</span><span class="sxs-lookup"><span data-stu-id="7104b-122">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="7104b-123">Il existe quatre pages de recherche qui se concentrent sur chacune des entités de vente au détail qui peuvent avoir des remises associées.</span><span class="sxs-lookup"><span data-stu-id="7104b-123">There are four inquiry pages that focus on each of the retail entities that can have discounts associated to them.</span></span>

-   <span data-ttu-id="7104b-124">**Groupes de prix de canal de vente au détail** : Cette page affiche la liste des canaux et des remises associés pour chaque groupe de prix.</span><span class="sxs-lookup"><span data-stu-id="7104b-124">**Retail channel price groups** - This page shows a list of channels and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="7104b-125">**Groupes de prix du catalogue** : Cette page affiche la liste des catalogues et des remises associés pour chaque groupe de prix.</span><span class="sxs-lookup"><span data-stu-id="7104b-125">**Catalog price groups** - This page shows a list of catalogs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="7104b-126">**Groupes de prix de fidélité** : Cette page affiche la liste des programmes de fidélité et des remises associés pour chaque groupe de prix.</span><span class="sxs-lookup"><span data-stu-id="7104b-126">**Loyalty price groups** - This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="7104b-127">**Groupes de prix d'affiliation** : Cette page affiche la liste des affiliations et des remises associés pour chaque groupe de prix.</span><span class="sxs-lookup"><span data-stu-id="7104b-127">**Affiliation price groups** - This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="7104b-128">Exemple de paramétrage de remise de canal</span><span class="sxs-lookup"><span data-stu-id="7104b-128">Example channel discount set up</span></span>
<span data-ttu-id="7104b-129">L'exemple suivant illustre les tâches impliquées dans le paramétrage d'une remise de canal.</span><span class="sxs-lookup"><span data-stu-id="7104b-129">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1.  <span data-ttu-id="7104b-130">Pour cet exemple, vous avez un canal appelé **Houston**, et vous allez créer une nouvelle remise appelée **Back-to-School.**</span><span class="sxs-lookup"><span data-stu-id="7104b-130">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School.**</span></span>
2.  <span data-ttu-id="7104b-131">Comme la stratégie de prix et de remise inclut la possibilité de remises de canal, vous devez toujours créer un groupe de prix spécifique au canal lorsque vous créez un canal.</span><span class="sxs-lookup"><span data-stu-id="7104b-131">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3.  <span data-ttu-id="7104b-132">Vous avez le groupe de prix **Houston-PG** et il est affecté au canal **Houston**.</span><span class="sxs-lookup"><span data-stu-id="7104b-132">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4.  <span data-ttu-id="7104b-133">Une fois la nouvelle remise **Back-to-School** créée, vous devez cliquer sur **Groupes de prix** en haut de la page **Remise**.</span><span class="sxs-lookup"><span data-stu-id="7104b-133">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="7104b-134">La page **Groupes de prix après remise** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="7104b-134">The **Discount price groups** page will open.</span></span> <span data-ttu-id="7104b-135">Cliquez ensuite sur **Nouveau** et sélectionnez le groupe de prix **Houston-PG**.</span><span class="sxs-lookup"><span data-stu-id="7104b-135">Next, click **New** and select the **Houston-PG** price group.</span></span>
5.  <span data-ttu-id="7104b-136">Vous pouvez désormais activer la remise et la transférer vers le canal.</span><span class="sxs-lookup"><span data-stu-id="7104b-136">Now you can enable the discount and push it to the channel.</span></span>

 

<a name="see-also"></a><span data-ttu-id="7104b-137">Voir également :</span><span class="sxs-lookup"><span data-stu-id="7104b-137">See also</span></span>
--------

[<span data-ttu-id="7104b-138">Ajustements de prix et remises</span><span class="sxs-lookup"><span data-stu-id="7104b-138">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)




