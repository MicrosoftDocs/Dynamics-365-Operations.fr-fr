---
title: Affichage des frais pour un article fabriqué
description: Les coûts constants d'un article fabriqué reflètent les temps de réglage de l'opération et les composants pour lesquels la quantité est constante ou la quantité de rebut est constante.
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: b8fcfc1a9386d05c2adbcb4208e7ef5d01644430
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "316669"
---
# <a name="display-charges-for-a-manufactured-item"></a><span data-ttu-id="ddac4-103">Affichage des frais pour un article fabriqué</span><span class="sxs-lookup"><span data-stu-id="ddac4-103">Display charges for a manufactured item</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ddac4-104">Les coûts constants d'un article fabriqué reflètent les temps de réglage de l'opération et les composants pour lesquels la quantité est constante ou la quantité de rebut est constante.</span><span class="sxs-lookup"><span data-stu-id="ddac4-104">The constant costs of a manufactured item reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span>

<span data-ttu-id="ddac4-105">Le montant calculé des frais d'un article peut être affiché avec les coûts unitaires de l'article.</span><span class="sxs-lookup"><span data-stu-id="ddac4-105">The calculated amount of an item's charges can be displayed with the item's unit costs.</span></span> <span data-ttu-id="ddac4-106">Toutefois, les frais s'affichent parfois dans des champs distincts et ne sont pas inclus dans les coûts unitaires de l'article.</span><span class="sxs-lookup"><span data-stu-id="ddac4-106">However, the charges are sometimes displayed as separate fields, and they are not included in the item's unit costs.</span></span> <span data-ttu-id="ddac4-107">Lorsque les frais s'affichent dans des champs distincts, un premier champ affiche le montant total des frais et un second champ affiche la taille du lot d'évaluation des coûts utilisée pour amortir le montant.</span><span class="sxs-lookup"><span data-stu-id="ddac4-107">When the charges appear as separate fields, one field displays the total amount of charges, and another field displays the costing lot size that is used to amortize the amount.</span></span> <span data-ttu-id="ddac4-108">Par exemple, la page Prix de l'article affiche les frais dans deux champs séparés.</span><span class="sxs-lookup"><span data-stu-id="ddac4-108">The Item price page, for example, displays the charges as two separate fields.</span></span> <span data-ttu-id="ddac4-109">En revanche, la page Complet affiche le coût total de l'article par unité, et les coûts amortis sont inclus dans les coûts unitaires.</span><span class="sxs-lookup"><span data-stu-id="ddac4-109">However, the Complete page displays the item's total cost per unit, and the amortized costs are included in the unit costs.</span></span>

<span data-ttu-id="ddac4-110">Les frais d'un article fabriqué sont toujours inclus dans le coût unitaire à des fins de coûts standard.</span><span class="sxs-lookup"><span data-stu-id="ddac4-110">The charges for a manufactured item are always included in the item's unit cost for standard cost purposes.</span></span> <span data-ttu-id="ddac4-111">Ils peuvent éventuellement être inclus à des fins de coûts planifiés.</span><span class="sxs-lookup"><span data-stu-id="ddac4-111">They can optionally be included for planned cost purposes.</span></span> <span data-ttu-id="ddac4-112">Une stratégie dans la version d'évaluation des coûts applique l'inclusion des frais dans le coût d'un article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="ddac4-112">A policy in the costing version enforces the inclusion of charges in the cost of a manufactured item.</span></span> <span data-ttu-id="ddac4-113">Lorsque vous activez l'enregistrement des coûts d'un article, les frais pour les informations de coût de base de l'article sont mis à jour, comme affiché dans la page Prix de l'article.</span><span class="sxs-lookup"><span data-stu-id="ddac4-113">When you activate an item's cost record, you update the charges for the item's base cost information, which is displayed in the Item price page.</span></span> <span data-ttu-id="ddac4-114">Les frais s'affichent dans deux champs distincts et ne sont pas inclus dans le coût unitaire de l'article.</span><span class="sxs-lookup"><span data-stu-id="ddac4-114">The charges are displayed as two separate fields, and they are not included in the item's unit cost.</span></span> <span data-ttu-id="ddac4-115">Chaque activation met à jour les informations de coût de base de l'article, même si l'activation reflète différents sites.</span><span class="sxs-lookup"><span data-stu-id="ddac4-115">Each activation updates the item's base cost information, even if the activation reflects different sites.</span></span> <span data-ttu-id="ddac4-116">Vous devez donc considérer les informations de coût de base comme des informations de référence.</span><span class="sxs-lookup"><span data-stu-id="ddac4-116">Therefore, you should view the base cost information as reference information.</span></span>





