---
title: Impossible de créer un environnement dans le centre d'administration Power Apps
description: Cet article explique comment procéder si l'administrateur ne peut pas créer d'environnement dans le Centre d'administration Microsoft Power Apps.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 664c644c9b34e3489b4134040e165d26202dbd38
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112521"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="7eac6-103">Impossible de créer un environnement dans le centre d'administration Power Apps</span><span class="sxs-lookup"><span data-stu-id="7eac6-103">Can't create an environment in the Power Apps Admin center</span></span>

<span data-ttu-id="7eac6-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="7eac6-104">**Issue**</span></span>

- <span data-ttu-id="7eac6-105">Le client/administrateur d'environnement ne peut pas créer d'environnement dans le Centre d'administration Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="7eac6-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="7eac6-106">L'utilisateur n'a pas de licence qui donne le droit de créer des environnements.</span><span class="sxs-lookup"><span data-stu-id="7eac6-106">The user doesn't have a license that gives the right to create environments.</span></span>

<span data-ttu-id="7eac6-107">**Solution**</span><span class="sxs-lookup"><span data-stu-id="7eac6-107">**Solution**</span></span>

<span data-ttu-id="7eac6-108">Assurez-vous que l'administrateur du client a attribué une Licence P2 Power Apps à l'utilisateur créant l'environnement.</span><span class="sxs-lookup"><span data-stu-id="7eac6-108">Make sure the tenant admin has assigned a valid Power Apps P2 license to the user creating the environment.</span></span> <span data-ttu-id="7eac6-109">Les plans de service Microsoft Dynamics suivants fournissent des autorisations pour créer des environnements :</span><span class="sxs-lookup"><span data-stu-id="7eac6-109">The following Microsoft Dynamics service plans provide permissions to create environments:</span></span>

| <span data-ttu-id="7eac6-110">Unité de gestion de stock (SKU) de produit général</span><span class="sxs-lookup"><span data-stu-id="7eac6-110">Overall product stockkeeping unit (SKU)</span></span>       | <span data-ttu-id="7eac6-111">Plan de services Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="7eac6-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="7eac6-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="7eac6-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="7eac6-113">Power Apps pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7eac6-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="7eac6-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7eac6-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="7eac6-115">Power Apps pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7eac6-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="7eac6-116">Notez que différentes références Microsoft Office fournissent également le droit, ainsi que les références Power Apps Plan 2 autonomes.</span><span class="sxs-lookup"><span data-stu-id="7eac6-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="7eac6-117">L'aspect important est que l'une de ces UGS doit être présente.</span><span class="sxs-lookup"><span data-stu-id="7eac6-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="7eac6-118">Atteindre [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="7eac6-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="7eac6-119">Créez les environnements en suivant les instructions dans [Mettre en service Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="7eac6-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
