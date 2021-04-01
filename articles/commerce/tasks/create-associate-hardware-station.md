---
title: Créer et associer une station matérielle
description: Cette procédure décrit comment créer une station matérielle.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0c02246a20ef28c0f4f28b73dfe5ff56f38a68b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247042"
---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="7aa51-103">Créer et associer une station matérielle</span><span class="sxs-lookup"><span data-stu-id="7aa51-103">Create and associate a hardware station</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7aa51-104">Cette procédure décrit comment créer une station matérielle.</span><span class="sxs-lookup"><span data-stu-id="7aa51-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="7aa51-105">Un profil de station matérielle est créé et utilisé pour ajouter de nouvelles stations matérielles à un magasin prédéfini (canal).</span><span class="sxs-lookup"><span data-stu-id="7aa51-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="7aa51-106">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="7aa51-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="7aa51-107">Accédez à Essentiel du commerce > Canaux > ..</span><span class="sxs-lookup"><span data-stu-id="7aa51-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="7aa51-108">> ..</span><span class="sxs-lookup"><span data-stu-id="7aa51-108">> ..</span></span> <span data-ttu-id="7aa51-109">> ..</span><span class="sxs-lookup"><span data-stu-id="7aa51-109">> ..</span></span> <span data-ttu-id="7aa51-110">> Profils de la station matérielle.</span><span class="sxs-lookup"><span data-stu-id="7aa51-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="7aa51-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7aa51-111">Click New.</span></span>
3. <span data-ttu-id="7aa51-112">Dans le champ ID station matérielle, tapez « TestHWProfile ».</span><span class="sxs-lookup"><span data-stu-id="7aa51-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="7aa51-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7aa51-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7aa51-114">Dans le champ Numéro de port, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="7aa51-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="7aa51-115">Dans le champ Profil matériel, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7aa51-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7aa51-116">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7aa51-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="7aa51-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7aa51-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7aa51-118">Dans le champ Nom du package, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7aa51-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="7aa51-119">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7aa51-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7aa51-120">Il s'agit du package standard fourni avec un nouvel environnement.</span><span class="sxs-lookup"><span data-stu-id="7aa51-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="7aa51-121">Le numéro de version peut varier.</span><span class="sxs-lookup"><span data-stu-id="7aa51-121">The version number may vary.</span></span>  
11. <span data-ttu-id="7aa51-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7aa51-122">Click Save.</span></span>
12. <span data-ttu-id="7aa51-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7aa51-123">Close the page.</span></span>
13. <span data-ttu-id="7aa51-124">Accédez à Retail et Commerce > Canaux > Tous les magasins.</span><span class="sxs-lookup"><span data-stu-id="7aa51-124">Go to Retail and Commerce > Channels > All stores.</span></span>
14. <span data-ttu-id="7aa51-125">Sélectionnez la ligne 17 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="7aa51-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="7aa51-126">Si vous utilisez la société fictive USRT, il s'agit du magasin de Houston.</span><span class="sxs-lookup"><span data-stu-id="7aa51-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="7aa51-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7aa51-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="7aa51-128">Activez ou désactivez l'extension de la section Stations matérielles.</span><span class="sxs-lookup"><span data-stu-id="7aa51-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="7aa51-129">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="7aa51-129">Click Add.</span></span>
18. <span data-ttu-id="7aa51-130">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7aa51-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="7aa51-131">Dans le champ ID profil, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7aa51-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="7aa51-132">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7aa51-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7aa51-133">Il doit s'agir du profil de la station matérielle que vous avez créé dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="7aa51-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="7aa51-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7aa51-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="7aa51-135">Dans le champ Nom de l'hôte, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7aa51-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="7aa51-136">Dans le champ ID du terminal TEF, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7aa51-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="7aa51-137">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7aa51-137">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]