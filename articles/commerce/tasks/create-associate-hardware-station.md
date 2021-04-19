---
title: Créer et associer une station matérielle
description: Cette procédure décrit comment créer une station matérielle.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4402e8d1179499512034e7deb8b3eb78f12096f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798583"
---
# <a name="create-and-associate-a-hardware-station"></a><span data-ttu-id="3a073-103">Créer et associer une station matérielle</span><span class="sxs-lookup"><span data-stu-id="3a073-103">Create and associate a hardware station</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a073-104">Cette procédure décrit comment créer une station matérielle.</span><span class="sxs-lookup"><span data-stu-id="3a073-104">This procedure walks through how to create a new hardware station.</span></span> <span data-ttu-id="3a073-105">Un profil de station matérielle est créé et utilisé pour ajouter de nouvelles stations matérielles à un magasin prédéfini (canal).</span><span class="sxs-lookup"><span data-stu-id="3a073-105">A new hardware profile will be created and used to add new hardware stations to a pre-defined store (channel).</span></span> <span data-ttu-id="3a073-106">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="3a073-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="3a073-107">Accédez à Essentiel du commerce > Canaux > ..</span><span class="sxs-lookup"><span data-stu-id="3a073-107">Go to Commerce essentials > Channels > ..</span></span> <span data-ttu-id="3a073-108">> ..</span><span class="sxs-lookup"><span data-stu-id="3a073-108">> ..</span></span> <span data-ttu-id="3a073-109">> ..</span><span class="sxs-lookup"><span data-stu-id="3a073-109">> ..</span></span> <span data-ttu-id="3a073-110">> Profils de la station matérielle.</span><span class="sxs-lookup"><span data-stu-id="3a073-110">> Hardware station profiles.</span></span>
2. <span data-ttu-id="3a073-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3a073-111">Click New.</span></span>
3. <span data-ttu-id="3a073-112">Dans le champ ID station matérielle, tapez « TestHWProfile ».</span><span class="sxs-lookup"><span data-stu-id="3a073-112">In the Hardware station ID field, type 'TestHWProfile'.</span></span>
4. <span data-ttu-id="3a073-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="3a073-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="3a073-114">Dans le champ Numéro de port, saisissez un nombre.</span><span class="sxs-lookup"><span data-stu-id="3a073-114">In the Port number field, enter a number.</span></span>
6. <span data-ttu-id="3a073-115">Dans le champ Profil matériel, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3a073-115">In the Hardware profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="3a073-116">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3a073-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="3a073-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3a073-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="3a073-118">Dans le champ Nom du package, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3a073-118">In the Package name field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="3a073-119">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3a073-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3a073-120">Il s’agit du package standard fourni avec un nouvel environnement.</span><span class="sxs-lookup"><span data-stu-id="3a073-120">This is the standard package that comes with a new environment.</span></span> <span data-ttu-id="3a073-121">Le numéro de version peut varier.</span><span class="sxs-lookup"><span data-stu-id="3a073-121">The version number may vary.</span></span>  
11. <span data-ttu-id="3a073-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3a073-122">Click Save.</span></span>
12. <span data-ttu-id="3a073-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3a073-123">Close the page.</span></span>
13. <span data-ttu-id="3a073-124">Accédez à Retail et Commerce > Canaux > Tous les magasins.</span><span class="sxs-lookup"><span data-stu-id="3a073-124">Go to Retail and Commerce > Channels > All stores.</span></span>
14. <span data-ttu-id="3a073-125">Sélectionnez la ligne 17 dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3a073-125">In the list, select row 17.</span></span>
    * <span data-ttu-id="3a073-126">Si vous utilisez la société fictive USRT, il s’agit du magasin de Houston.</span><span class="sxs-lookup"><span data-stu-id="3a073-126">If you are using the USRT demo data company, this is the Houston store.</span></span>  
15. <span data-ttu-id="3a073-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3a073-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="3a073-128">Activez ou désactivez l’extension de la section Stations matérielles.</span><span class="sxs-lookup"><span data-stu-id="3a073-128">Toggle the expansion of the Hardware stations section.</span></span>
17. <span data-ttu-id="3a073-129">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="3a073-129">Click Add.</span></span>
18. <span data-ttu-id="3a073-130">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3a073-130">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="3a073-131">Dans le champ ID profil, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="3a073-131">In the Profile ID field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="3a073-132">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3a073-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3a073-133">Il doit s’agir du profil de la station matérielle que vous avez créé dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="3a073-133">This must be the new hardware station profile that was created in the previous steps.</span></span>  
21. <span data-ttu-id="3a073-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3a073-134">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="3a073-135">Dans le champ Nom de l’hôte, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3a073-135">In the Host name field, type a value.</span></span>
23. <span data-ttu-id="3a073-136">Dans le champ ID du terminal TEF, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3a073-136">In the EFT terminal ID field, type a value.</span></span>
24. <span data-ttu-id="3a073-137">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3a073-137">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]