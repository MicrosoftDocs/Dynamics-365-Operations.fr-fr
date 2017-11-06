--- 
title: " Valider les ventes et les paiements en ligne"
description: "Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e8c3f861a53a3f5c2de29248523ff4efd5e1d072
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="post-online-sales-and-payments"></a><span data-ttu-id="5c6d3-103"> Valider les ventes et les paiements en ligne</span><span class="sxs-lookup"><span data-stu-id="5c6d3-103">Post online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5c6d3-104">Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="5c6d3-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="5c6d3-106">Accédez à Tous les espaces de travail > Finances du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="5c6d3-107">Cliquez sur Synchroniser les commandes.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="5c6d3-108">Dans le champ Hiérarchie d'organisation, sélectionnez « Magasins de vente au détail par région ».</span><span class="sxs-lookup"><span data-stu-id="5c6d3-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="5c6d3-109">Sélectionnez un magasin en ligne spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="5c6d3-110">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="5c6d3-111">Cliquez sur l'onglet Exécuter à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="5c6d3-112">Activez ou désactivez la case à cocher Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="5c6d3-113">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-113">Click Recurrence.</span></span>
7. <span data-ttu-id="5c6d3-114">Sélectionnez l'option Pas de date de fin.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-114">Select the No end date option.</span></span>
8. <span data-ttu-id="5c6d3-115">Dans le champ Nombre, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="5c6d3-116">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-116">Click OK.</span></span>
10. <span data-ttu-id="5c6d3-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5c6d3-117">Click OK.</span></span>


