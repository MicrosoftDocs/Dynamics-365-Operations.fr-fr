---
title: Les articles en rupture de stock peuvent être achetés
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider les clients à ajouter des articles en rupture de stock à leur panier et procéder au paiement.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 4fa7769044c45faffd9ff61b3de8e6217a5e0354
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018456"
---
# <a name="items-without-inventory-can-be-checked-out"></a><span data-ttu-id="c70cc-103">Les articles en rupture de stock peuvent être achetés</span><span class="sxs-lookup"><span data-stu-id="c70cc-103">Items without inventory can be checked out</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c70cc-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider les clients à ajouter des articles en rupture de stock à leur panier et procéder au paiement.</span><span class="sxs-lookup"><span data-stu-id="c70cc-104">This topic provides troubleshooting guidance that can help when customers can add out-of-stock items to their cart and proceed to checkout.</span></span>

## <a name="description"></a><span data-ttu-id="c70cc-105">Description</span><span class="sxs-lookup"><span data-stu-id="c70cc-105">Description</span></span>

<span data-ttu-id="c70cc-106">Les utilisateurs peuvent ajouter un article à leur panier, même s’il n’y a pas de stock disponible dans le magasin, puis accéder à la page de paiement.</span><span class="sxs-lookup"><span data-stu-id="c70cc-106">Users can add an item to their cart, even though there is no on-hand inventory in the store, and then proceed to the checkout page.</span></span>

## <a name="resolution"></a><span data-ttu-id="c70cc-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="c70cc-107">Resolution</span></span>

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a><span data-ttu-id="c70cc-108">Activer la propriété Afficher les erreurs de rupture de stock dans le générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="c70cc-108">Enable the Show Out Of Stock Errors property in Commerce site builder</span></span>

<span data-ttu-id="c70cc-109">Pour activer la propriété **Afficher les erreurs de rupture de stock** dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c70cc-109">To enable the **Show Out Of Stock Errors** property in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="c70cc-110">Sélectionnez le site sur lequel vous travaillez.</span><span class="sxs-lookup"><span data-stu-id="c70cc-110">Select the site that you're working on.</span></span>
1. <span data-ttu-id="c70cc-111">Dans le volet de navigation de gauche, sélectionnez **Pages**.</span><span class="sxs-lookup"><span data-stu-id="c70cc-111">In the left navigation, select **Pages**.</span></span>
1. <span data-ttu-id="c70cc-112">Sélectionnez **CartPage** pour l’ouvrir.</span><span class="sxs-lookup"><span data-stu-id="c70cc-112">Select **CartPage** to open it.</span></span>
1. <span data-ttu-id="c70cc-113">Sélectionnez l’emplacement **Panier 1**, sélectionnez **Modifier**, puis, dans le volet des propriétés, cochez la case **Afficher les erreurs de rupture de stock**.</span><span class="sxs-lookup"><span data-stu-id="c70cc-113">Select the **Cart 1** slot, select **Edit**, and then, in the properties pane, select the **Show Out Of Stock Errors** check box.</span></span>
1. <span data-ttu-id="c70cc-114">Enregistrez et publiez la page.</span><span class="sxs-lookup"><span data-stu-id="c70cc-114">Save and publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c70cc-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c70cc-115">Additional resources</span></span>

[<span data-ttu-id="c70cc-116">Appliquer les paramètres de stock</span><span class="sxs-lookup"><span data-stu-id="c70cc-116">Apply inventory settings</span></span>](../inventory-settings.md)

[<span data-ttu-id="c70cc-117">Calculer la disponibilité des stocks pour les canaux de vente au détail</span><span class="sxs-lookup"><span data-stu-id="c70cc-117">Calculate inventory availability for retail channels</span></span>](../calculated-inventory-retail-channels.md)

[<span data-ttu-id="c70cc-118">Configurer des marges de stock et des niveaux de stock</span><span class="sxs-lookup"><span data-stu-id="c70cc-118">Configure inventory buffers and inventory levels</span></span>](../inventory-buffers-levels.md)
