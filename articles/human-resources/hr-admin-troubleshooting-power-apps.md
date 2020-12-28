---
title: Impossible de créer un environnement dans le centre d'administration Power Apps
description: Cet article explique comment procéder si l'administrateur ne peut pas créer d'environnement dans le Centre d'administration Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 68e6dbcbbc9811211570e968047f5faa8a2c8bd0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418479"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="3b0a4-103">Impossible de créer un environnement dans le centre d'administration Power Apps</span><span class="sxs-lookup"><span data-stu-id="3b0a4-103">Can't create an environment in the Power Apps Admin center</span></span>

<span data-ttu-id="3b0a4-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="3b0a4-104">**Issue**</span></span>

- <span data-ttu-id="3b0a4-105">Le client/administrateur d'environnement ne peut pas créer d'environnement dans le Centre d'administration Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="3b0a4-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="3b0a4-106">Une licence qui offre aux utilisateurs le droit d'effectuer l'étape de création d'environnement n'a pas été affectée directement à l'utilisateur qui effectue cette étape.</span><span class="sxs-lookup"><span data-stu-id="3b0a4-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="3b0a4-107">**Solution**</span><span class="sxs-lookup"><span data-stu-id="3b0a4-107">**Solution**</span></span>

<span data-ttu-id="3b0a4-108">Assurez-vous que l'administrateur de client a affecté une licence Power Apps P2 valide directement à l'utilisateur qui effectuera l'étape de création d'environnement.</span><span class="sxs-lookup"><span data-stu-id="3b0a4-108">Make sure that the tenant admin has assigned a valid Power Apps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="3b0a4-109">Voici les plans de service Microsoft Dynamics qui fournissent ce droit.</span><span class="sxs-lookup"><span data-stu-id="3b0a4-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="3b0a4-110">Unité de gestion de stock (SKU) de produit général</span><span class="sxs-lookup"><span data-stu-id="3b0a4-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="3b0a4-111">Plan de services Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="3b0a4-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="3b0a4-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="3b0a4-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="3b0a4-113">Power Apps pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3b0a4-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="3b0a4-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3b0a4-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="3b0a4-115">Power Apps pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3b0a4-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="3b0a4-116">Notez que différentes références Microsoft Office fournissent également le droit, ainsi que les références Power Apps Plan 2 autonomes.</span><span class="sxs-lookup"><span data-stu-id="3b0a4-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="3b0a4-117">L'aspect important est que l'une de ces UGS doit être présente.</span><span class="sxs-lookup"><span data-stu-id="3b0a4-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="3b0a4-118">Atteindre [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="3b0a4-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="3b0a4-119">Créez les environnements en suivant les instructions dans [Mettre en service Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="3b0a4-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
