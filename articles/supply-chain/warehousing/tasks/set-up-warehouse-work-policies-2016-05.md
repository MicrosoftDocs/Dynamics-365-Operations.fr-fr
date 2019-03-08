---
title: Paramétrer des stratégies de travail d'entrepôt (Application, mai 2016)
description: Les processus d'entrepôt n'incluent pas systématiquement les tâches d'entrepôt.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy, WMSLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 34b4255c85bb53f7e238b60559890571070953a6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "335322"
---
# <a name="set-up-warehouse-work-policies-application-may-2016"></a><span data-ttu-id="e11c2-103">Paramétrer des stratégies de travail d'entrepôt (Application, mai 2016)</span><span class="sxs-lookup"><span data-stu-id="e11c2-103">Set up warehouse work policies (Application, May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e11c2-104">Les processus d'entrepôt n'incluent pas systématiquement les tâches d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e11c2-104">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="e11c2-105">En définissant une stratégie de travail, vous pouvez empêcher la création de tâche pour le prélèvement de matières premières et le rangement de produits finis pour un ensemble de produits à des emplacements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="e11c2-105">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="e11c2-106">Les données fictives de la société USMF ont été utilisées pour créer cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e11c2-106">The USMF demo data company was used to create this recording.</span></span> <span data-ttu-id="e11c2-107">L'application Dynamics AX 7.0.1 ou ultérieure est requise pour ce guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="e11c2-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>

1. <span data-ttu-id="e11c2-108">Accédez à Gestion des entrepôts > Paramétrage > Travail > Stratégies de travail.</span><span class="sxs-lookup"><span data-stu-id="e11c2-108">Go to Warehouse management > Setup > Work > Work policies.</span></span>
2. <span data-ttu-id="e11c2-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e11c2-109">Click New.</span></span>
3. <span data-ttu-id="e11c2-110">Entrez Aucun travail de rangement dans le champ Nom de la stratégie de travail.</span><span class="sxs-lookup"><span data-stu-id="e11c2-110">In the Work policy name field, type 'No put-away work'.</span></span>
4. <span data-ttu-id="e11c2-111">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e11c2-111">Click Save.</span></span>
5. <span data-ttu-id="e11c2-112">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e11c2-112">Click Add.</span></span>
6. <span data-ttu-id="e11c2-113">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e11c2-113">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="e11c2-114">Sélectionnez Rangement des produits finis dans le champ Type d'ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e11c2-114">In the Work order type field, select 'Finished goods put away'.</span></span>
8. <span data-ttu-id="e11c2-115">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e11c2-115">Click Add.</span></span>
9. <span data-ttu-id="e11c2-116">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e11c2-116">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="e11c2-117">Sélectionnez Rangement des coproduits et des sous-produits dans le champ Type d'ordre d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e11c2-117">In the Work order type field, select 'Co-product and by-product put away'.</span></span>
11. <span data-ttu-id="e11c2-118">Développez la section Emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="e11c2-118">Expand the Inventory locations section.</span></span>
12. <span data-ttu-id="e11c2-119">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e11c2-119">Click Add.</span></span>
13. <span data-ttu-id="e11c2-120">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e11c2-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="e11c2-121">Entrez 51 dans la liste Entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e11c2-121">In the Warehouse list, enter '51'.</span></span>
15. <span data-ttu-id="e11c2-122">Saisissez ou sélectionnez 001 dans le champ Emplacement.</span><span class="sxs-lookup"><span data-stu-id="e11c2-122">In the Location field, enter or select '001'.</span></span>
16. <span data-ttu-id="e11c2-123">Développez la section Produits.</span><span class="sxs-lookup"><span data-stu-id="e11c2-123">Expand the Products section.</span></span>
17. <span data-ttu-id="e11c2-124">Sélectionnez Sélectionné dans le champ Sélection de produits.</span><span class="sxs-lookup"><span data-stu-id="e11c2-124">In the Product selection field, select 'Selected'.</span></span>
18. <span data-ttu-id="e11c2-125">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e11c2-125">Click Add.</span></span>
19. <span data-ttu-id="e11c2-126">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e11c2-126">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="e11c2-127">Entrez ou sélectionnez L0101 dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="e11c2-127">In the Item number field, enter or select 'L0101'.</span></span>
21. <span data-ttu-id="e11c2-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e11c2-128">Click Save.</span></span>

