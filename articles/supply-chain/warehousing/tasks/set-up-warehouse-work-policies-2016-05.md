--- 
title: "Paramétrer les stratégies de travail d'entrepôt"
description: "Les processus d'entrepôt n'incluent pas systématiquement les tâches d'entrepôt."
author: johanhoffmann
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 22e359ee2ded2315c588c2dd5c3d62dee0440adf
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-warehouse-work-policies"></a><span data-ttu-id="68168-103">Paramétrer les stratégies de travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="68168-103">Set up warehouse work policies</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="68168-104">Les processus d'entrepôt n'incluent pas systématiquement les tâches d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="68168-104">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="68168-105">En définissant une stratégie de travail, vous pouvez empêcher la création de tâche pour le prélèvement de matières premières et le rangement de produits finis pour un ensemble de produits à des emplacements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="68168-105">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="68168-106">Les données fictives de la société USMF ont été utilisées pour créer cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="68168-106">The USMF demo data company was used to create this recording.</span></span> <span data-ttu-id="68168-107">L'application Dynamics AX 7.0.1 ou ultérieure est requise pour ce guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="68168-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>

1. <span data-ttu-id="68168-108">Accédez à Gestion des entrepôts > Paramétrage > Travail > Stratégies de travail.</span><span class="sxs-lookup"><span data-stu-id="68168-108">Go to Warehouse management > Setup > Work > Work policies.</span></span>
2. <span data-ttu-id="68168-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="68168-109">Click New.</span></span>
3. <span data-ttu-id="68168-110">Entrez Aucun travail de rangement dans le champ Nom de la stratégie de travail.</span><span class="sxs-lookup"><span data-stu-id="68168-110">In the Work policy name field, type 'No put-away work'.</span></span>
4. <span data-ttu-id="68168-111">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="68168-111">Click Save.</span></span>
5. <span data-ttu-id="68168-112">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="68168-112">Click Add.</span></span>
6. <span data-ttu-id="68168-113">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="68168-113">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="68168-114">Sélectionnez Rangement des produits finis dans le champ Type d'ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="68168-114">In the Work order type field, select 'Finished goods put away'.</span></span>
8. <span data-ttu-id="68168-115">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="68168-115">Click Add.</span></span>
9. <span data-ttu-id="68168-116">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="68168-116">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="68168-117">Sélectionnez Rangement des coproduits et des sous-produits dans le champ Type d'ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="68168-117">In the Work order type field, select 'Co-product and by-product put away'.</span></span>
11. <span data-ttu-id="68168-118">Développez la section Emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="68168-118">Expand the Inventory locations section.</span></span>
12. <span data-ttu-id="68168-119">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="68168-119">Click Add.</span></span>
13. <span data-ttu-id="68168-120">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="68168-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="68168-121">Entrez 51 dans la liste Entrepôt.</span><span class="sxs-lookup"><span data-stu-id="68168-121">In the Warehouse list, enter '51'.</span></span>
15. <span data-ttu-id="68168-122">Saisissez ou sélectionnez 001 dans le champ Emplacement.</span><span class="sxs-lookup"><span data-stu-id="68168-122">In the Location field, enter or select '001'.</span></span>
16. <span data-ttu-id="68168-123">Développez la section Produits.</span><span class="sxs-lookup"><span data-stu-id="68168-123">Expand the Products section.</span></span>
17. <span data-ttu-id="68168-124">Sélectionnez Sélectionné dans le champ Sélection de produits.</span><span class="sxs-lookup"><span data-stu-id="68168-124">In the Product selection field, select 'Selected'.</span></span>
18. <span data-ttu-id="68168-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="68168-125">Click Add.</span></span>
19. <span data-ttu-id="68168-126">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="68168-126">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="68168-127">Entrez ou sélectionnez L0101 dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="68168-127">In the Item number field, enter or select 'L0101'.</span></span>
21. <span data-ttu-id="68168-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="68168-128">Click Save.</span></span>


