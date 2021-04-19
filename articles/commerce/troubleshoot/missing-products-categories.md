---
title: Produits et catégories manquants après la copie de l’environnement
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque des produits et des catégories sont manquants après la copie d’un site d’un environnement à un autre ou dans le même environnement.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 527fd0fa62775f65f61b538474b1d45d1a0155ed
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801721"
---
# <a name="products-and-categories-missing-after-environment-copy"></a><span data-ttu-id="07459-103">Produits et catégories manquants après la copie de l’environnement</span><span class="sxs-lookup"><span data-stu-id="07459-103">Products and categories missing after environment copy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="07459-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque des produits et des catégories sont manquants après la copie d’un site d’un environnement à un autre ou dans le même environnement.</span><span class="sxs-lookup"><span data-stu-id="07459-104">This topic provides troubleshooting guidance that can help when products and categories are missing after a site is copied between environments or within the same environment.</span></span>

## <a name="description"></a><span data-ttu-id="07459-105">Description</span><span class="sxs-lookup"><span data-stu-id="07459-105">Description</span></span>

<span data-ttu-id="07459-106">Une fois qu’un site a été copié d’un environnement à un autre, ou dans le même environnement, des produits et des catégories sont manquants.</span><span class="sxs-lookup"><span data-stu-id="07459-106">After a site is copied from one environment to another, or within the same environment, the products and categories are missing from the site.</span></span> <span data-ttu-id="07459-107">Les produits et catégories ne sont pas présents dans la vitrine e-commerce ni dans l’onglet **Produits** du générateur de site Commerce.</span><span class="sxs-lookup"><span data-stu-id="07459-107">The products and categories will be missing from the e-commerce storefront and from the **Products** tab in Commerce site builder.</span></span>

## <a name="resolution"></a><span data-ttu-id="07459-108">Résolution</span><span class="sxs-lookup"><span data-stu-id="07459-108">Resolution</span></span>

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a><span data-ttu-id="07459-109">Mapper le numéro d’unité opérationnelle du canal à un site nouvellement copié dans le générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="07459-109">Map the channel operating unit number to a newly copied site in Commerce site builder</span></span>

<span data-ttu-id="07459-110">Pour mapper le numéro d’unité opérationnelle du canal à un site nouvellement copié dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="07459-110">To map the channel operating unit number (OUN) to a newly copied site in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="07459-111">Sélectionnez le site nouvellement copié.</span><span class="sxs-lookup"><span data-stu-id="07459-111">Select the newly copied site.</span></span>
1. <span data-ttu-id="07459-112">Sous **Paramètres du site**, sélectionnez **Canaux**.</span><span class="sxs-lookup"><span data-stu-id="07459-112">Under **Site settings**, select **Channels**.</span></span>
1. <span data-ttu-id="07459-113">À côté du nom du canal, sélectionnez les points de suspension (**...**), puis sélectionnez **Changer le canal de la boutique en ligne**.</span><span class="sxs-lookup"><span data-stu-id="07459-113">Next to the channel name, select the ellipsis (**...**), and then select **Change online store channel**.</span></span>
1. <span data-ttu-id="07459-114">Dans la boîte de dialogue **Changer le canal de la boutique en ligne**, sélectionnez le canal à mapper sur le site nouvellement copié, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="07459-114">In the **Change online store channel** dialog box, select the channel to map to the newly copied site, and then select **OK**.</span></span>
1. <span data-ttu-id="07459-115">Sélectionnez **Enregistrer et publier**.</span><span class="sxs-lookup"><span data-stu-id="07459-115">Select **Save and publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="07459-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="07459-116">Additional resources</span></span>

[<span data-ttu-id="07459-117">Associer un site Dynamics 365 Commerce avec un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="07459-117">Associate a Dynamics 365 Commerce site with an online channel</span></span>](../associate-site-online-store.md)
