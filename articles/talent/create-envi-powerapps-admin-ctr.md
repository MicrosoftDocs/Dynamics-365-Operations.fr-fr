---
title: Impossible de créer un environnement dans le centre d'administration Power Apps
description: Cette rubrique explique comment procéder si l'administrateur ne peut pas créer d'environnement dans le Centre d'administration Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5923c59ab5dde13fed0483972e76634031404fd8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773217"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="95066-103">Impossible de créer un environnement dans le centre d'administration Power Apps</span><span class="sxs-lookup"><span data-stu-id="95066-103">Can't create an environment in the Power Apps Admin center</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="95066-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="95066-104">**Issue**</span></span>

- <span data-ttu-id="95066-105">Le client/administrateur d'environnement ne peut pas créer d'environnement dans le Centre d'administration Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="95066-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="95066-106">Une licence qui offre aux utilisateurs le droit d'effectuer l'étape de création d'environnement n'a pas été affectée directement à l'utilisateur qui effectue cette étape.</span><span class="sxs-lookup"><span data-stu-id="95066-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="95066-107">**Solution**</span><span class="sxs-lookup"><span data-stu-id="95066-107">**Solution**</span></span>

<span data-ttu-id="95066-108">Assurez-vous que l'administrateur de client a affecté une licence Power Apps P2 valide directement à l'utilisateur qui effectuera l'étape de création d'environnement.</span><span class="sxs-lookup"><span data-stu-id="95066-108">Make sure that the tenant admin has assigned a valid Power Apps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="95066-109">Voici les plans de service Microsoft Dynamics qui fournissent ce droit.</span><span class="sxs-lookup"><span data-stu-id="95066-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="95066-110">Unité de gestion de stock (SKU) de produit général</span><span class="sxs-lookup"><span data-stu-id="95066-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="95066-111">Plan de services Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="95066-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="95066-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="95066-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="95066-113">Power Apps pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="95066-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="95066-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="95066-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="95066-115">Power Apps pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="95066-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="95066-116">Notez que différentes références Microsoft Office fournissent également le droit, ainsi que les références Power Apps Plan 2 autonomes.</span><span class="sxs-lookup"><span data-stu-id="95066-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="95066-117">L'aspect important est que l'une de ces UGS doit être présente.</span><span class="sxs-lookup"><span data-stu-id="95066-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="95066-118">Atteindre [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="95066-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="95066-119">Créez les environnements en suivant les instructions dans [Mettre en service Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="95066-119">Create the environments by following the instructions in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
