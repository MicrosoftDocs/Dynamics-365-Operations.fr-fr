---
title: Validation des ventes et des paiements en ligne
description: Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13839bbe6ca03f3cfc7036fce87477bf7d5af2a7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550206"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="b8fa0-103">Validation des ventes et des paiements en ligne</span><span class="sxs-lookup"><span data-stu-id="b8fa0-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="b8fa0-104">Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="b8fa0-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="b8fa0-106">Accédez à Tous les espaces de travail > Finances du magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="b8fa0-107">Cliquez sur Synchroniser les commandes.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="b8fa0-108">Dans le champ Hiérarchie d'organisation, sélectionnez « Magasins de vente au détail par région ».</span><span class="sxs-lookup"><span data-stu-id="b8fa0-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="b8fa0-109">Sélectionnez un magasin en ligne spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="b8fa0-110">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="b8fa0-111">Cliquez sur l'onglet Exécuter à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="b8fa0-112">Activez ou désactivez la case à cocher Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="b8fa0-113">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-113">Click Recurrence.</span></span>
7. <span data-ttu-id="b8fa0-114">Sélectionnez l'option Pas de date de fin.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-114">Select the No end date option.</span></span>
8. <span data-ttu-id="b8fa0-115">Dans le champ Nombre, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="b8fa0-116">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-116">Click OK.</span></span>
10. <span data-ttu-id="b8fa0-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="b8fa0-117">Click OK.</span></span>

