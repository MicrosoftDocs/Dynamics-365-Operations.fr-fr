---
title: Modifier une prévision de la demande manuellement
description: Cette procédure permet d'indiquer comment modifier la prévision pour un article.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ca6b881bc094b68d1bbf8c7c20b65418e42b28e3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835866"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="fe4d9-103">Modifier une prévision de la demande manuellement</span><span class="sxs-lookup"><span data-stu-id="fe4d9-103">Modify a demand forecast manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fe4d9-104">Cette procédure permet d'indiquer comment modifier la prévision pour un article.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="fe4d9-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fe4d9-106">Cet enregistrement est destiné au gestionnaire de production.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="fe4d9-107">Modifier la prévision pour un article</span><span class="sxs-lookup"><span data-stu-id="fe4d9-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="fe4d9-108">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="fe4d9-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fe4d9-110">Sélectionnez l'article dont vous souhaitez modifier la prévision.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="fe4d9-111">Par exemple, vous pouvez sélectionner l'article D0001.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="fe4d9-112">Cliquez sur Planifier dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-112">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="fe4d9-113">Cliquez sur Prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-113">Click Demand forecast.</span></span>
5. <span data-ttu-id="fe4d9-114">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="fe4d9-115">S'il n'existe aucune ligne de prévision, créez une ligne</span><span class="sxs-lookup"><span data-stu-id="fe4d9-115">If there are no forecast lines, create a new line by  .</span></span> <span data-ttu-id="fe4d9-116">en cliquant sur Nouveau dans la barre d'application.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-116">clicking New on the app bar.</span></span>  
6. <span data-ttu-id="fe4d9-117">Entrez un nombre dans le champ Quantité vendue.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-117">In the Sales quantity field, enter a number.</span></span>
    * <span data-ttu-id="fe4d9-118">Ce chiffre représente la quantité prévue pour l'article.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-118">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="fe4d9-119">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-119">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="fe4d9-120">Modifier la prévision dans Excel</span><span class="sxs-lookup"><span data-stu-id="fe4d9-120">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="fe4d9-121">Cliquez sur Ouvrir dans Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-121">Click Open in Microsoft Office.</span></span>
2. <span data-ttu-id="fe4d9-122">Cliquez sur Modifier la prévision de la demande dans Excel.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-122">Click Edit Demand forecast in Excel.</span></span>
    * <span data-ttu-id="fe4d9-123">Dans Excel, vous pouvez ajouter, supprimer et modifier des lignes de prévision de la demande.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-123">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="fe4d9-124">Si vous ne pouvez pas afficher les données dans Excel, vous devez vous connecter à Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition avec l'option « Maintenir la connexion » activée et vous devez approuver l'application de connexion de données.</span><span class="sxs-lookup"><span data-stu-id="fe4d9-124">If you are not able to see the data in Excel, you need to sign in to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  

