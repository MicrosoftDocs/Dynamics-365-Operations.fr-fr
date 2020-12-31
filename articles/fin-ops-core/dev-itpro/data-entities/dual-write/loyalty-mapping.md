---
title: Cartes de fidélité et points de fidélité
description: Cette rubrique décrit l’intégration des données sur les cartes de fidélité client et les points de récompense dans la double écriture.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 28872e9510394cf3d5cee151798d4130b8b6fe27
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683496"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="7c527-103">Cartes de fidélité et points de fidélité</span><span class="sxs-lookup"><span data-stu-id="7c527-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="7c527-104">Les entreprises classent les clients et fournissent des services sophistiqués, basés sur les habitudes d’achat et les dépenses des clients.</span><span class="sxs-lookup"><span data-stu-id="7c527-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="7c527-105">Par exemple, Dynamics 365 Commerce possède l’infrastructure et les fonctions nécessaires pour faciliter et gérer les cartes de fidélité des clients, les points de récompense, les prix basés sur la fidélité et les expériences d’achat basées sur les récompenses.</span><span class="sxs-lookup"><span data-stu-id="7c527-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="7c527-106">Lorsque les données sur les cartes de fidélité des clients et les points de récompense dans Commerce sont synchronisées avec Dataverse, les applications d’engagement client peuvent utiliser ces données.</span><span class="sxs-lookup"><span data-stu-id="7c527-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="7c527-107">Par exemple, les utilisateurs de Dynamics 365 Customer Service peuvent utiliser les données pour fournir les mêmes services sophistiqués via le service d’assistance.</span><span class="sxs-lookup"><span data-stu-id="7c527-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="7c527-108">Modèles</span><span class="sxs-lookup"><span data-stu-id="7c527-108">Templates</span></span>

| <span data-ttu-id="7c527-109">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7c527-109">Finance and Operations apps</span></span> | <span data-ttu-id="7c527-110">Applications pilotées par modèle dans Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7c527-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="7c527-111">Description</span><span class="sxs-lookup"><span data-stu-id="7c527-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="7c527-112">Carte de fidélité</span><span class="sxs-lookup"><span data-stu-id="7c527-112">Loyalty card</span></span>                | <span data-ttu-id="7c527-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="7c527-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="7c527-114">Ce modèle synchronise les informations concernant les cartes de fidélité des clients.</span><span class="sxs-lookup"><span data-stu-id="7c527-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="7c527-115">Points de récompense de fidélité</span><span class="sxs-lookup"><span data-stu-id="7c527-115">Loyalty reward points</span></span>       | <span data-ttu-id="7c527-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="7c527-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="7c527-117">Ce modèle synchronise les informations concernant les points de fidélité des clients.</span><span class="sxs-lookup"><span data-stu-id="7c527-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
