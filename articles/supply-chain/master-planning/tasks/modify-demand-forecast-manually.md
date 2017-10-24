--- 
title: "Modifier une prévision de la demande manuellement"
description: "Cette procédure permet d'indiquer comment modifier la prévision pour un article."
author: YuyuScheller
manager: AnnBe
ms.date: 11/15/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2e269ef7b33b4d7e171d284d68d28c825c2fe86c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="c3f14-103">Modifier une prévision de la demande manuellement</span><span class="sxs-lookup"><span data-stu-id="c3f14-103">Modify a demand forecast manually</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3f14-104">Cette procédure permet d'indiquer comment modifier la prévision pour un article.</span><span class="sxs-lookup"><span data-stu-id="c3f14-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="c3f14-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="c3f14-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c3f14-106">Cet enregistrement est destiné au gestionnaire de production.</span><span class="sxs-lookup"><span data-stu-id="c3f14-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="c3f14-107">Modifier la prévision pour un article</span><span class="sxs-lookup"><span data-stu-id="c3f14-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="c3f14-108">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="c3f14-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="c3f14-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c3f14-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c3f14-110">Sélectionnez l'article dont vous souhaitez modifier la prévision.</span><span class="sxs-lookup"><span data-stu-id="c3f14-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="c3f14-111">Par exemple, vous pouvez sélectionner l'article D0001.</span><span class="sxs-lookup"><span data-stu-id="c3f14-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="c3f14-112">Cliquez sur Planifier dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c3f14-112">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="c3f14-113">Cliquez sur Prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="c3f14-113">Click Demand forecast.</span></span>
5. <span data-ttu-id="c3f14-114">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c3f14-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c3f14-115">S'il n'existe aucune ligne de prévision, créez une ligne</span><span class="sxs-lookup"><span data-stu-id="c3f14-115">If there are no forecast lines, create a new line by  .</span></span> <span data-ttu-id="c3f14-116">en cliquant sur Nouveau dans la barre d'application.</span><span class="sxs-lookup"><span data-stu-id="c3f14-116">clicking New on the app bar.</span></span>  
6. <span data-ttu-id="c3f14-117">Entrez un nombre dans le champ Quantité vendue.</span><span class="sxs-lookup"><span data-stu-id="c3f14-117">In the Sales quantity field, enter a number.</span></span>
    * <span data-ttu-id="c3f14-118">Ce chiffre représente la quantité prévue pour l'article.</span><span class="sxs-lookup"><span data-stu-id="c3f14-118">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="c3f14-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c3f14-119">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="c3f14-120">Modifier la prévision dans Excel</span><span class="sxs-lookup"><span data-stu-id="c3f14-120">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="c3f14-121">Cliquez sur Ouvrir dans Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="c3f14-121">Click Open in Microsoft Office.</span></span>
2. <span data-ttu-id="c3f14-122">Cliquez sur Modifier la prévision de la demande dans Excel.</span><span class="sxs-lookup"><span data-stu-id="c3f14-122">Click Edit Demand forecast in Excel.</span></span>
    * <span data-ttu-id="c3f14-123">Dans Excel, vous pouvez ajouter, supprimer et modifier des lignes de prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="c3f14-123">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="c3f14-124">Si vous ne pouvez pas afficher les données dans Excel, vous devez vous connecter à Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition avec l'option « Maintenir la connexion » activée et vous devez approuver l'application de connexion de données.</span><span class="sxs-lookup"><span data-stu-id="c3f14-124">If you are not able to see the data in Excel, you need to sign in to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  


