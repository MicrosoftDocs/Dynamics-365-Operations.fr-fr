--- 
title: "Configurer le partage de données financières entre sociétés"
description: "Cette procédure indique comment configurer, activer, valider, et résoudre des conflits en partageant des données entre des sociétés."
author: aprilolson
manager: AnnBe
ms.date: 06/22/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 5ae6b30d2d0948efbf86f2c2693e643b383f8406
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="configure-cross-company-financial-data-sharing"></a><span data-ttu-id="9d8a7-103">Configurer le partage de données financières entre sociétés</span><span class="sxs-lookup"><span data-stu-id="9d8a7-103">Configure cross-company financial data sharing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9d8a7-104">Cette procédure indique comment configurer, activer, valider, et résoudre des conflits en partageant des données entre des sociétés.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="9d8a7-105">Elle utilise la société USMF et le modèle de partage de données financières.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-105">It uses the USMF company and the Financial data sharing template.</span></span>



<span data-ttu-id="9d8a7-106">La plateforme Dynamics AX 7.1 ou ultérieure est requise pour ce guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="9d8a7-107">Accédez à Administration système > Espaces de travail > Gestion des données.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-107">Go to System administration > Workspaces > Data management.</span></span>
2. <span data-ttu-id="9d8a7-108">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-108">Click Import.</span></span>
3. <span data-ttu-id="9d8a7-109">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="9d8a7-110">Sélectionnez le type de package dans le champ Format des données source.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-110">In the Source data format field, select the Package type.</span></span>
    * <span data-ttu-id="9d8a7-111">Cliquez sur Charger.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-111">Click Upload.</span></span> <span data-ttu-id="9d8a7-112">Allez dans l'emplacement du fichier de package du modèle de partage de données financières et sélectionnez ce fichier.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>  
5. <span data-ttu-id="9d8a7-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-113">Click Save.</span></span>
6. <span data-ttu-id="9d8a7-114">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9d8a7-115">Sélectionnez la stratégie de partage de données qui vient d'être créée.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="9d8a7-116">Cliquez sur Importer.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-116">Click Import.</span></span>
8. <span data-ttu-id="9d8a7-117">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-117">Click Close.</span></span>
9. <span data-ttu-id="9d8a7-118">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-118">Refresh the page.</span></span>
10. <span data-ttu-id="9d8a7-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-119">Close the page.</span></span>
11. <span data-ttu-id="9d8a7-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-120">Close the page.</span></span>
12. <span data-ttu-id="9d8a7-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-121">Close the page.</span></span>
13. <span data-ttu-id="9d8a7-122">Accédez à Administration système > Paramétrage > Configurer le partage de données entre sociétés.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-122">Go to System administration > Setup > Configure cross-company data sharing.</span></span>
14. <span data-ttu-id="9d8a7-123">Dans la liste, recherchez et sélectionnez Jours de paiement.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-123">In the list, find and select Payment days.</span></span>
15. <span data-ttu-id="9d8a7-124">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-124">Click Add.</span></span>
16. <span data-ttu-id="9d8a7-125">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="9d8a7-126">Tapez USSI dans le champ Société.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-126">In the Company field, type 'USSI'.</span></span>
18. <span data-ttu-id="9d8a7-127">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-127">Click Add.</span></span>
19. <span data-ttu-id="9d8a7-128">Tapez USMF dans le champ Société.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-128">In the Company field, type 'USMF'.</span></span>
20. <span data-ttu-id="9d8a7-129">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-129">Click Save.</span></span>
21. <span data-ttu-id="9d8a7-130">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-130">Click Enable.</span></span>
22. <span data-ttu-id="9d8a7-131">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-131">Click Yes.</span></span>
23. <span data-ttu-id="9d8a7-132">Cliquez sur Rechercher les problèmes de partage.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-132">Click Find sharing issues.</span></span>
24. <span data-ttu-id="9d8a7-133">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-133">Click Yes.</span></span>
25. <span data-ttu-id="9d8a7-134">Cliquez sur la valeur du champ Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-134">Click Update field value.</span></span>
26. <span data-ttu-id="9d8a7-135">Cliquez sur Valeur utilisée dans Société 1.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-135">Click Use value from company 1.</span></span>
27. <span data-ttu-id="9d8a7-136">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-136">Refresh the page.</span></span>
28. <span data-ttu-id="9d8a7-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9d8a7-137">Close the page.</span></span>


