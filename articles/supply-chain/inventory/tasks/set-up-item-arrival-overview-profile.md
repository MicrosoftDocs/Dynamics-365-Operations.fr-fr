---
title: Paramétrer un profil de vue d’ensemble des arrivées
description: Cette rubrique se concentre sur le paramétrage d’un profil de vue d’ensemble des arrivées.
author: ShylaThompson
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49670e4287faf3e50a824a5cbedd83ea7dbb8152
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244349"
---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="d4f2f-103">Paramétrer un profil de vue d’ensemble des arrivées</span><span class="sxs-lookup"><span data-stu-id="d4f2f-103">Set up an item arrival overview profile</span></span>

<span data-ttu-id="d4f2f-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="d4f2f-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="d4f2f-105">Cette rubrique se concentre sur le paramétrage d’un profil de vue d’ensemble des arrivées.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-105">This topic focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="d4f2f-106">Le profil de vue d’ensemble des arrivées est une collection de règles qui sont appliquées lorsque la page de vue d’ensemble des arrivées est ouverte par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-106">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="d4f2f-107">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="d4f2f-108">Cette procédure est généralement effectuée par la personne qui s’occuper de la réception.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-108">This procedure would typically be carried out by a receiving clerk.</span></span>

1. <span data-ttu-id="d4f2f-109">Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Paramétrage > Distribution > Profils de vue d’ensemble des arrivées**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-109">In the navigation pane, go to **Modules > Inventory management > Setup > Distribution > Arrival overview profiles**.</span></span>
2. <span data-ttu-id="d4f2f-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-110">Select **New**.</span></span> <span data-ttu-id="d4f2f-111">Étant donné que vous travaillerez presque toujours dans le même entrepôt lors du déchargement de camions pleins, vous devez créer un profil de vue d’ensemble des arrivées pour simplifier le processus d’enregistrer les articles reçus.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-111">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="d4f2f-112">Dans le champ **Nom du profil de vue d’ensemble des arrivées**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-112">In the **Arrival overview profile name** field, type a value.</span></span>
4. <span data-ttu-id="d4f2f-113">Dans le champ **Afficher les lignes**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-113">In the **Show lines** field, select an option.</span></span> <span data-ttu-id="d4f2f-114">Permet de sélectionner les lignes à afficher pour les réceptions :</span><span class="sxs-lookup"><span data-stu-id="d4f2f-114">Select which lines to show for the receipts:</span></span>  

    - <span data-ttu-id="d4f2f-115">**Tout** - Permet d’afficher toutes les lignes, quel que soit leur statut.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-115">**All** – Show all lines, regardless of status.</span></span>   
    - <span data-ttu-id="d4f2f-116">**En cours** - Affiche les lignes des réceptions dans lesquelles la progression est Complète ou Partielle.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-116">**In progress** – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="d4f2f-117">Ceci signifie que, pour chaque ligne, la totalité ou une partie de la quantité a été enregistrée dans un journal des arrivées.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-117">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   
    - <span data-ttu-id="d4f2f-118">**Incomplète** - Affiche les lignes des réceptions dans lesquelles la progression est Aucune ou Partielle.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-118">**Not complete** – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="d4f2f-119">Ceci signifie que, pour chaque ligne, soit la quantité n’a pas été enregistrée ou seule une partie l’a été dans un journal des arrivées.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-119">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  

5. <span data-ttu-id="d4f2f-120">Développez ou réduisez la section **Options des arrivées**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-120">Expand or collapse the **Arrival options** section.</span></span>
6. <span data-ttu-id="d4f2f-121">Dans le champ **Jours après**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-121">In the **Days forward** field, type a value.</span></span> <span data-ttu-id="d4f2f-122">Ceci définit un filtre pour afficher les lignes de réception devant être reçues dans les prochains jours (selon le nombre que vous définissez).</span><span class="sxs-lookup"><span data-stu-id="d4f2f-122">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="d4f2f-123">Dans le champ **Jours avant**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-123">In the **Days back** field, type a value.</span></span> <span data-ttu-id="d4f2f-124">Ceci définit un filtre pour afficher les lignes de réception devant être reçu il y a un certain nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-124">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="d4f2f-125">Dans le champ **Entrepôts**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-125">In the **Warehouses** field, type a value.</span></span> <span data-ttu-id="d4f2f-126">Filtrez sur un ou plusieurs entrepôts.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-126">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="d4f2f-127">Sélectionnez une valeur dans le champ **Mode de livraison**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-127">In the **Mode of delivery** field, select a value.</span></span> <span data-ttu-id="d4f2f-128">Ceci définit un filtre pour afficher uniquement les lignes de réception avec ce mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-128">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="d4f2f-129">Sélectionnez WHS dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-129">In the **Name** field, select WHS.</span></span>
11. <span data-ttu-id="d4f2f-130">Dans le champ **Entrepôt**, sélectionnez l’entrepôt 24.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-130">In the **Warehouse** field, select warehouse 24.</span></span> <span data-ttu-id="d4f2f-131">Il s’agit de l’entrepôt par défaut utilisé pour les lignes de réception enregistrées qui utilisent ce profil.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-131">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="d4f2f-132">Dans le champ **Emplacement**, sélectionnez **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-132">In the **Location** field, select **Baydoor**.</span></span> <span data-ttu-id="d4f2f-133">Il s’agit de l’emplacement par défaut utilisé pour les lignes de réception enregistrées qui utilisent ce profil.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-133">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="d4f2f-134">Développez ou réduisez la section **Détails des requêtes des arrivées**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-134">Expand or collapse the **Arrival query details** section.</span></span>
14. <span data-ttu-id="d4f2f-135">Sélectionnez site 2 dans le champ **Limiter au site**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-135">In the **Restrict to site** field, select site 2.</span></span> <span data-ttu-id="d4f2f-136">Ceci définit un filtre pour afficher uniquement les lignes de réception avec ce site.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-136">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="d4f2f-137">Définissez l’option **Commandes fournisseur** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-137">Set the **Purchase orders** option to **Yes**.</span></span> <span data-ttu-id="d4f2f-138">Sélectionnez des lignes de réception à partir de commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-138">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="d4f2f-139">Définissez l’option Ordres de **transfert** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-139">Set the **Transfer** orders option to **Yes**.</span></span> <span data-ttu-id="d4f2f-140">Sélectionnez des lignes de réception à partir d’ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-140">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="d4f2f-141">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-141">Select **Save**.</span></span>
18. <span data-ttu-id="d4f2f-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d4f2f-142">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]