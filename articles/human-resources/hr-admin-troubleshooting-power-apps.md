---
title: Impossible de créer un environnement dans le centre d’administration Power Apps
description: Cet article explique comment procéder si l’administrateur ne peut pas créer d’environnement dans le Centre d’administration Microsoft Power Apps.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 73c8910900ba6486a8e60a547b07ea0c82a6cb10
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053345"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="a1802-103">Impossible de créer un environnement dans le centre d’administration Power Apps</span><span class="sxs-lookup"><span data-stu-id="a1802-103">Can't create an environment in the Power Apps Admin center</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a1802-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="a1802-104">**Issue**</span></span>

- <span data-ttu-id="a1802-105">Le client/administrateur d’environnement ne peut pas créer d’environnement dans le Centre d’administration Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a1802-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="a1802-106">L’utilisateur n’a pas de licence qui donne le droit de créer des environnements.</span><span class="sxs-lookup"><span data-stu-id="a1802-106">The user doesn't have a license that gives the right to create environments.</span></span>

<span data-ttu-id="a1802-107">**Solution**</span><span class="sxs-lookup"><span data-stu-id="a1802-107">**Solution**</span></span>

<span data-ttu-id="a1802-108">Assurez-vous que l’administrateur du client a attribué une Licence P2 Power Apps à l’utilisateur créant l’environnement.</span><span class="sxs-lookup"><span data-stu-id="a1802-108">Make sure the tenant admin has assigned a valid Power Apps P2 license to the user creating the environment.</span></span> <span data-ttu-id="a1802-109">Les plans de service Microsoft Dynamics suivants fournissent des autorisations pour créer des environnements :</span><span class="sxs-lookup"><span data-stu-id="a1802-109">The following Microsoft Dynamics service plans provide permissions to create environments:</span></span>

| <span data-ttu-id="a1802-110">Unité de gestion de stock (SKU) de produit général</span><span class="sxs-lookup"><span data-stu-id="a1802-110">Overall product stockkeeping unit (SKU)</span></span>       | <span data-ttu-id="a1802-111">Plan de services Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="a1802-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="a1802-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="a1802-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="a1802-113">Power Apps pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a1802-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="a1802-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="a1802-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="a1802-115">Power Apps pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a1802-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="a1802-116">Notez que différentes références Microsoft Office fournissent également le droit, ainsi que les références Power Apps Plan 2 autonomes.</span><span class="sxs-lookup"><span data-stu-id="a1802-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="a1802-117">L’aspect important est que l’une de ces UGS doit être présente.</span><span class="sxs-lookup"><span data-stu-id="a1802-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="a1802-118">Atteindre [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="a1802-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="a1802-119">Créez les environnements en suivant les instructions dans [Mettre en service Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="a1802-119">Create the environments by following the instructions in [Provision Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]