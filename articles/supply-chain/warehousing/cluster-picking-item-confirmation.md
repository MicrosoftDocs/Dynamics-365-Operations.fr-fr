---
title: Confirmation de produit pour la sélection du groupement
description: Cette rubrique décrit comment vous paramétrez la vérification d'article avec la sélection du groupement.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e6493afb64acb4d7644aac8dad71a0917c76549
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205780"
---
[!include [banner](../includes/banner.md)]

# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="f31d9-103">Confirmation de produit pour la sélection du groupement</span><span class="sxs-lookup"><span data-stu-id="f31d9-103">Product confirmation for cluster picking</span></span>
<span data-ttu-id="f31d9-104">La sélection du groupement vous permet de regrouper des articles pour plusieurs commandes simultanément.</span><span class="sxs-lookup"><span data-stu-id="f31d9-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="f31d9-105">Lorsque la sélection du groupement est appliqué, la confirmation d'article est cruciale pour vérifier les articles qui sont ajoutés aux clusters.</span><span class="sxs-lookup"><span data-stu-id="f31d9-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="f31d9-106">Vous pouvez vérifier les articles de la sélection du groupement lors du processus de sélection du groupement.</span><span class="sxs-lookup"><span data-stu-id="f31d9-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="f31d9-107">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="f31d9-107">Where it applies</span></span>
<span data-ttu-id="f31d9-108">La vérification d'article pour la sélection du groupement fonctionne de la même manière que pour la vérification des articles dans les processus de non sélection du groupement.</span><span class="sxs-lookup"><span data-stu-id="f31d9-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="f31d9-109">Le paramétrage est basé sur le paramétrage de code-barres de produit.</span><span class="sxs-lookup"><span data-stu-id="f31d9-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="f31d9-110">Paramétrage de la vérification d'article avec la sélection du groupement</span><span class="sxs-lookup"><span data-stu-id="f31d9-110">Set up item verification with cluster picking</span></span>
1.  <span data-ttu-id="f31d9-111">Dans une option de menu de l'appareil mobile, ouvrez l'écran de paramétrage pour la confirmation du travail : **Gestion des entrepôts** > **Gestion des entrepôts** > **Paramétrage** > **Appareil mobile** > **Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="f31d9-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
2.  <span data-ttu-id="f31d9-112">Dans l'option de menu de l'appareil mobile, ouvrez **Paramétrage de la confirmation du travail**.</span><span class="sxs-lookup"><span data-stu-id="f31d9-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

|        <span data-ttu-id="f31d9-113">Option</span><span class="sxs-lookup"><span data-stu-id="f31d9-113">Option</span></span>        |                                    <span data-ttu-id="f31d9-114">Description</span><span class="sxs-lookup"><span data-stu-id="f31d9-114">Description</span></span>                                    |
|----------------------|-----------------------------------------------------------------------------------|
| <span data-ttu-id="f31d9-115">Confirmation du produit</span><span class="sxs-lookup"><span data-stu-id="f31d9-115">Product confirmation</span></span> | <span data-ttu-id="f31d9-116">Permet de confirmer chaque pièce du stock de l'appareil mobile lors de la lecture.</span><span class="sxs-lookup"><span data-stu-id="f31d9-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span> |

