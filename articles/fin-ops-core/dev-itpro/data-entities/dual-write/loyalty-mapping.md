---
title: Cartes de fidélité et points de fidélité
description: Cette rubrique décrit l'intégration des données sur les cartes de fidélité client et les points de récompense entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: e7e67946930404ab7ba0c7fccf468722f723d675
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172967"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="d55fc-103">Cartes de fidélité et points de fidélité</span><span class="sxs-lookup"><span data-stu-id="d55fc-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d55fc-104">Les entreprises classent les clients et fournissent des services sophistiqués, basés sur les habitudes d'achat et les dépenses des clients.</span><span class="sxs-lookup"><span data-stu-id="d55fc-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="d55fc-105">Dans la suite d'applications Microsoft Dynamics 365, Dynamics 365 Commerce possède l'infrastructure et les fonctions nécessaires pour faciliter et gérer les cartes de fidélité des clients, les points de récompense, les prix basés sur la fidélité et les expériences d'achat basées sur les récompenses.</span><span class="sxs-lookup"><span data-stu-id="d55fc-105">In the Microsoft Dynamics 365 suite of applications, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="d55fc-106">Lorsque les données sur les cartes de fidélité des clients et les points de récompense dans Commerce sont synchronisées avec le service Common Data, les applications basées sur des modèles dans Dynamics 365 peuvent utiliser ces données.</span><span class="sxs-lookup"><span data-stu-id="d55fc-106">When data about customer loyalty cards and reward points in Commerce is synced to Common Data service, model-driven apps in Dynamics 365 can use that data.</span></span> <span data-ttu-id="d55fc-107">Par exemple, les utilisateurs de Dynamics 365 Customer Service peuvent utiliser les données pour fournir les mêmes services sophistiqués via le service d'assistance.</span><span class="sxs-lookup"><span data-stu-id="d55fc-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="d55fc-108">Modèles</span><span class="sxs-lookup"><span data-stu-id="d55fc-108">Templates</span></span>

| <span data-ttu-id="d55fc-109">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d55fc-109">Finance and Operations apps</span></span> | <span data-ttu-id="d55fc-110">Applications pilotées par modèle dans Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d55fc-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="d55fc-111">Description </span><span class="sxs-lookup"><span data-stu-id="d55fc-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="d55fc-112">Carte de fidélité</span><span class="sxs-lookup"><span data-stu-id="d55fc-112">Loyalty card</span></span>                | <span data-ttu-id="d55fc-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="d55fc-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="d55fc-114">Ce modèle synchronise les informations concernant les cartes de fidélité des clients.</span><span class="sxs-lookup"><span data-stu-id="d55fc-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="d55fc-115">Points de récompense de fidélité</span><span class="sxs-lookup"><span data-stu-id="d55fc-115">Loyalty reward points</span></span>       | <span data-ttu-id="d55fc-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="d55fc-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="d55fc-117">Ce modèle synchronise les informations concernant les points de fidélité des clients.</span><span class="sxs-lookup"><span data-stu-id="d55fc-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
