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
ms.openlocfilehash: 272c3a13b68e2b862faf20cc269ca790322b61de
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367290"
---
# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="91f45-103">Confirmation de produit pour la sélection du groupement</span><span class="sxs-lookup"><span data-stu-id="91f45-103">Product confirmation for cluster picking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91f45-104">La sélection du groupement vous permet de regrouper des articles pour plusieurs commandes simultanément.</span><span class="sxs-lookup"><span data-stu-id="91f45-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="91f45-105">Lorsque la sélection du groupement est appliqué, la confirmation d'article est cruciale pour vérifier les articles qui sont ajoutés aux clusters.</span><span class="sxs-lookup"><span data-stu-id="91f45-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="91f45-106">Vous pouvez vérifier les articles de la sélection du groupement lors du processus de sélection du groupement.</span><span class="sxs-lookup"><span data-stu-id="91f45-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="91f45-107">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="91f45-107">Where it applies</span></span>

<span data-ttu-id="91f45-108">La vérification d'article pour la sélection du groupement fonctionne de la même manière que pour la vérification des articles dans les processus de non sélection du groupement.</span><span class="sxs-lookup"><span data-stu-id="91f45-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="91f45-109">Le paramétrage est basé sur le paramétrage de code-barres de produit.</span><span class="sxs-lookup"><span data-stu-id="91f45-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="91f45-110">Paramétrage de la vérification d'article avec la sélection du groupement</span><span class="sxs-lookup"><span data-stu-id="91f45-110">Set up item verification with cluster picking</span></span>

1. <span data-ttu-id="91f45-111">Dans une option de menu de l'appareil mobile, ouvrez l'écran de paramétrage pour la confirmation du travail : **Gestion des entrepôts** > **Gestion des entrepôts** > **Paramétrage** > **Appareil mobile** > **Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="91f45-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
1. <span data-ttu-id="91f45-112">Dans l'option de menu de l'appareil mobile, ouvrez **Paramétrage de la confirmation du travail**.</span><span class="sxs-lookup"><span data-stu-id="91f45-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

|        <span data-ttu-id="91f45-113">Option</span><span class="sxs-lookup"><span data-stu-id="91f45-113">Option</span></span>        |                                    <span data-ttu-id="91f45-114">Description</span><span class="sxs-lookup"><span data-stu-id="91f45-114">Description</span></span>                                    |
|----------------------|-----------------------------------------------------------------------------------|
| <span data-ttu-id="91f45-115">Confirmation du produit</span><span class="sxs-lookup"><span data-stu-id="91f45-115">Product confirmation</span></span> | <span data-ttu-id="91f45-116">Permet de confirmer chaque pièce du stock de l'appareil mobile lors de la lecture.</span><span class="sxs-lookup"><span data-stu-id="91f45-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span> |
