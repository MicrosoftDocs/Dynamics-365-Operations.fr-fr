---
title: Utiliser leu suivi pour l'éclatement
description: Cet article décrit comment utiliser le suivi pour explorer les causes derrière les résultats d'un éclatement de commande.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19231
ms.assetid: 9bc9bfbe-a7a9-437b-a947-826229b0585a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 046d4f5270869542d33023b9b9c927e89f5ad40b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209511"
---
# <a name="use-tracing-for-explosion"></a><span data-ttu-id="23acb-103">Utiliser leu suivi pour l'éclatement</span><span class="sxs-lookup"><span data-stu-id="23acb-103">Use tracing for explosion</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23acb-104">Cet article décrit comment utiliser le suivi pour explorer les causes derrière les résultats d'un éclatement de commande.</span><span class="sxs-lookup"><span data-stu-id="23acb-104">This article explains how you can use tracing to explore the causes behind the outcome of an order explosion.</span></span>

<span data-ttu-id="23acb-105">En activant le suivi, vous pouvez afficher des informations sur les facteurs qui ont contribué aux résultats de l'éclatement d'une commande spécifique.</span><span class="sxs-lookup"><span data-stu-id="23acb-105">By enabling tracing, you can view information about the factors that contributed to the outcome of the explosion of a particular order.</span></span> <span data-ttu-id="23acb-106">Les exemples suivants illustrent la manière dont vous pouvez utiliser les informations de suivi :</span><span class="sxs-lookup"><span data-stu-id="23acb-106">The following examples show how you can use the tracing information:</span></span>

-   <span data-ttu-id="23acb-107">Afficher les relations entre les actions sur les ordres prévisionnels afin d'optimiser la chaîne d'approvisionnement et les réservations de stock.</span><span class="sxs-lookup"><span data-stu-id="23acb-107">View relations between the actions on planned orders to optimize the supply chain and inventory reservations.</span></span>
-   <span data-ttu-id="23acb-108">Afficher les relations par rapport aux commandes déjà approuvées.</span><span class="sxs-lookup"><span data-stu-id="23acb-108">View relations to orders that are already approved.</span></span> <span data-ttu-id="23acb-109">Vous pouvez vous concentrer sur la confirmation automatique des besoins déduits, puis définir la priorité des commandes plus précisément.</span><span class="sxs-lookup"><span data-stu-id="23acb-109">You can focus on automatically firming derived requirements and then prioritize orders more accurately.</span></span>
-   <span data-ttu-id="23acb-110">Simuler les résultats d'une planification pour déterminer si les paramètres de la planification sont optimaux.</span><span class="sxs-lookup"><span data-stu-id="23acb-110">Simulate planning results to determine whether the planning parameters are optimal.</span></span>
-   <span data-ttu-id="23acb-111">Identifier la manière dont des informations telles que les dates de production, les quantités et les priorités pour une commande ont été déterminées.</span><span class="sxs-lookup"><span data-stu-id="23acb-111">Identify how information such as production dates, quantities, and priorities for an order were determined.</span></span>

<span data-ttu-id="23acb-112">Vous pouvez afficher les détails sur les perspectives et les actions pour une commande sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="23acb-112">You can view details about futures and actions for a selected order.</span></span> <span data-ttu-id="23acb-113">Sur la page **Éclatement**, les informations de suivi sont disponibles sous l'onglet **Explication** du volet supérieur.</span><span class="sxs-lookup"><span data-stu-id="23acb-113">On the **Explosion** page, tracing information is available on the **Explanation** tab in the upper pane.</span></span> <span data-ttu-id="23acb-114">Le suivi se produit lorsque vous éclatez une commande.</span><span class="sxs-lookup"><span data-stu-id="23acb-114">Tracing occurs when you explode an order.</span></span> <span data-ttu-id="23acb-115">Pour démarrer le suivi pour la commande, cliquez sur **Mettre à jour**, puis cochez la case **Activer le suivi**.</span><span class="sxs-lookup"><span data-stu-id="23acb-115">To start tracing for the order, click **Update**, and then select the **Enable trace** check box.</span></span> <span data-ttu-id="23acb-116">Vous pouvez utiliser le champ **Rechercher du texte** pour rechercher des informations spécifiques dans le journal.</span><span class="sxs-lookup"><span data-stu-id="23acb-116">You can use the **Find text** field to search the log for specific information.</span></span> <span data-ttu-id="23acb-117">Les résultats de la recherche sont mis en surbrillance dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="23acb-117">Search results are highlighted in the tree.</span></span>

<a name="additional-resources"></a><span data-ttu-id="23acb-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="23acb-118">Additional resources</span></span>
--------

[<span data-ttu-id="23acb-119">Vue d'ensemble des plans généraux</span><span class="sxs-lookup"><span data-stu-id="23acb-119">Master plans overview</span></span>](master-plans.md)



