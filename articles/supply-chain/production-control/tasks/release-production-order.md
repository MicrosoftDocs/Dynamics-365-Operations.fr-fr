---
title: Lancer un ordre de fabrication
description: Cette procédure permet d’indiquer comment lancer un ordre de fabrication.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f5c5ca5ebf51d0722318c455e6ca59d3a893793
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831960"
---
# <a name="release-a-production-order"></a><span data-ttu-id="86068-103">Lancer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="86068-103">Release a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="86068-104">Cette procédure permet d’indiquer comment lancer un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="86068-104">This procedure shows how to release a production order.</span></span> <span data-ttu-id="86068-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="86068-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="86068-106">Il s’agit de la quatrième des sept procédures expliquant le cycle de vie de l’ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="86068-106">This is the fourth procedure out of seven which explains the production order lifecycle.</span></span>

1. <span data-ttu-id="86068-107">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="86068-107">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="86068-108">Dans la grille, sélectionnez un ordre de fabrication dont le statut est Planifié.</span><span class="sxs-lookup"><span data-stu-id="86068-108">In the grid, select a production order that has the Scheduled status.</span></span>  
2. <span data-ttu-id="86068-109">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="86068-109">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="86068-110">Cliquez sur Lancement.</span><span class="sxs-lookup"><span data-stu-id="86068-110">Click Release.</span></span>
    * <span data-ttu-id="86068-111">Dans cette page, vous pouvez confirmer le lancement des ordres de fabrication sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="86068-111">On this page, you can confirm the release of the selected range of production orders.</span></span> <span data-ttu-id="86068-112">Cliquez sur Sélectionner pour ajouter des commandes.</span><span class="sxs-lookup"><span data-stu-id="86068-112">Click Select if you want to add orders.</span></span>  
    * <span data-ttu-id="86068-113">L’étape Lancement indique quand l’ordre de fabrication est lancé dans l’atelier de production afin que les opérateurs d’atelier puissent signaler la progression pour la tâche de fabrication.</span><span class="sxs-lookup"><span data-stu-id="86068-113">The Release step indicates when the production order is released to the production shop floor so that the shop floor operators can report progress on the production jobs.</span></span> <span data-ttu-id="86068-114">Les documents de production contenant les informations importantes sur le traitement des tâches peuvent être émis.</span><span class="sxs-lookup"><span data-stu-id="86068-114">Production papers that contain relevant information about processing the jobs can be issued.</span></span> <span data-ttu-id="86068-115">Le travail d’entrepôt pour le prélèvement de matière première est généré pour les articles configurés pour le processus d’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="86068-115">The warehouse work for raw material picking is generated for the items that are set up for the warehouse process.</span></span>  
4. <span data-ttu-id="86068-116">Cliquez sur l’onglet Général.</span><span class="sxs-lookup"><span data-stu-id="86068-116">Click the General tab.</span></span>
    * <span data-ttu-id="86068-117">Sélectionnez les états de production à imprimer.</span><span class="sxs-lookup"><span data-stu-id="86068-117">Select which production reports should be printed.</span></span> <span data-ttu-id="86068-118">L’état des bons de travail imprime une page pour chaque tâche prévue et requiert que l’ordre de fabrication soit planifié au niveau des tâches.</span><span class="sxs-lookup"><span data-stu-id="86068-118">The Job card report prints a page for each scheduled job and requires the production order to be scheduled at the job level.</span></span> <span data-ttu-id="86068-119">L’état contient des informations sur les dates et heures de début et de fin prévues, la quantité à produire et que la ressource qui traite la tâche.</span><span class="sxs-lookup"><span data-stu-id="86068-119">The report contains information about the scheduled start and end time, the quantity to produce, and which resource processes the job.</span></span> <span data-ttu-id="86068-120">L’état Tâche de gamme collecte les mêmes informations sur la même page, mais n’imprime pas une page pour chaque tâche.</span><span class="sxs-lookup"><span data-stu-id="86068-120">The Route job report collects the same information on the same page, but does not print a page for each job.</span></span> <span data-ttu-id="86068-121">L’état Fiche production indique uniquement les opérations, pas les tâches.</span><span class="sxs-lookup"><span data-stu-id="86068-121">The Route card report only shows the operations but not the jobs.</span></span> <span data-ttu-id="86068-122">Par conséquent, cet état ne nécessite pas de planification des tâches, mais il peut être utilisé lorsque des ordres de fabrication sont planifiés au niveau de l’opération.</span><span class="sxs-lookup"><span data-stu-id="86068-122">Therefore, this report does not require job scheduling, but can be used when production orders are scheduled at the operation level.</span></span>  
5. <span data-ttu-id="86068-123">Cochez la case Imprimer la fiche production.</span><span class="sxs-lookup"><span data-stu-id="86068-123">Click the Print route card checkbox.</span></span>
6. <span data-ttu-id="86068-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="86068-124">Click OK.</span></span>
7. <span data-ttu-id="86068-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="86068-125">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]