--- 
title: "Afficher le besoin prévisionnel intersociétés en sortie"
description: "Cette procédure indique comment afficher tous les ordres prévisionnels qui seront honorés par un fournisseur intersociétés."
author: YuyuScheller
manager: AnnBe
ms.date: 11/03/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 183bbba80351c19d2218c577020b1e852ab45ac4
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="ddb10-103">Afficher le besoin prévisionnel intersociétés en sortie</span><span class="sxs-lookup"><span data-stu-id="ddb10-103">View outbound planned intercompany demand</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ddb10-104">Cette procédure indique comment afficher tous les ordres prévisionnels qui seront honorés par un fournisseur intersociétés.</span><span class="sxs-lookup"><span data-stu-id="ddb10-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="ddb10-105">La société fictive de démonstration utilisée pour créer cette procédure est DEMF.</span><span class="sxs-lookup"><span data-stu-id="ddb10-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="ddb10-106">Cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="ddb10-106">Click Master planning.</span></span>
2. <span data-ttu-id="ddb10-107">Dans le champ Régime, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ddb10-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="ddb10-108">Dans le champ Plan, sélectionnez le plan 10.</span><span class="sxs-lookup"><span data-stu-id="ddb10-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="ddb10-109">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="ddb10-109">Click Run.</span></span>
4. <span data-ttu-id="ddb10-110">Entrez un nombre dans le champ Nombre de threads.</span><span class="sxs-lookup"><span data-stu-id="ddb10-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="ddb10-111">Représente le nombre de threads parallèles à utiliser pour la planification.</span><span class="sxs-lookup"><span data-stu-id="ddb10-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="ddb10-112">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ddb10-112">Click OK.</span></span>
    * <span data-ttu-id="ddb10-113">Cette opération peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="ddb10-113">This may take a while.</span></span>  
6. <span data-ttu-id="ddb10-114">Cliquez sur Besoin prévisionnel intersociétés.</span><span class="sxs-lookup"><span data-stu-id="ddb10-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="ddb10-115">Cliquez sur Besoin prévisionnel intersociétés en sortie.</span><span class="sxs-lookup"><span data-stu-id="ddb10-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="ddb10-116">Cette page fournit une vue d'ensemble de la demande planifiée qui sera honorée par un fournisseur de la chaîne d'approvisionnement interne.</span><span class="sxs-lookup"><span data-stu-id="ddb10-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="ddb10-117">Développez la section Détails du besoin en amont.</span><span class="sxs-lookup"><span data-stu-id="ddb10-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="ddb10-118">Dans cette section, vous pouvez afficher les détails sur la façon dont la demande sera honorée.</span><span class="sxs-lookup"><span data-stu-id="ddb10-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="ddb10-119">Vous devrez attendre l'exécution de la planification dans la société d'approvisionnement avant de pouvoir consulter les informations supplémentaires ici.</span><span class="sxs-lookup"><span data-stu-id="ddb10-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  


