---
title: "Paramétrer un profil de vue d'ensemble des arrivées"
description: "Cette tâche se concentre sur le paramétrage d'un profil de vue d'ensemble des arrivées."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: b971e72febbd78ff7c27ad2029e5061b978dc44e
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="180b3-103">Paramétrer un profil de vue d'ensemble des arrivées</span><span class="sxs-lookup"><span data-stu-id="180b3-103">Set up an item arrival overview profile</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="180b3-104">Cette tâche se concentre sur le paramétrage d'un profil de vue d'ensemble des arrivées.</span><span class="sxs-lookup"><span data-stu-id="180b3-104">This task focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="180b3-105">Le profil de vue d'ensemble des arrivées est une collection de règles qui sont appliquées lorsque la page de vue d'ensemble des arrivées est ouverte par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="180b3-105">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="180b3-106">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="180b3-106">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="180b3-107">Cette procédure est généralement effectuée par la personne qui s'occuper de la réception.</span><span class="sxs-lookup"><span data-stu-id="180b3-107">This procedure would typically be carried out by a receiving clerk.</span></span>





1. <span data-ttu-id="180b3-108">Accédez à Gestion des stocks > Configuration > Distribution > Profils de vue d'ensemble des arrivées.</span><span class="sxs-lookup"><span data-stu-id="180b3-108">Go to Inventory management > Setup > Distribution > Arrival overview profiles.</span></span>
2. <span data-ttu-id="180b3-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="180b3-109">Click New.</span></span>
    * <span data-ttu-id="180b3-110">Étant donné que vous travaillerez presque toujours dans le même entrepôt lors du déchargement de camions pleins, vous devez créer un profil de vue d'ensemble des arrivées pour simplifier le processus d'enregistrer les articles reçus.</span><span class="sxs-lookup"><span data-stu-id="180b3-110">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="180b3-111">Dans le champ Nom du profil de vue d'ensemble des arrivées, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="180b3-111">In the Arrival overview profile name field, type a value.</span></span>
4. <span data-ttu-id="180b3-112">Dans le champ Afficher les lignes, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="180b3-112">In the Show lines field, select an option.</span></span>
    * <span data-ttu-id="180b3-113">Sélectionnez les lignes à afficher pour les réceptions : Toutes (afficher toutes les lignes, quel que soit leur statut).</span><span class="sxs-lookup"><span data-stu-id="180b3-113">Select which lines to show for the receipts:   All – Show all lines, regardless of status.</span></span>   <span data-ttu-id="180b3-114">En cours (affiche les lignes des réceptions dans lesquelles la progression est Complète ou Partielle).</span><span class="sxs-lookup"><span data-stu-id="180b3-114">In progress – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="180b3-115">Ceci signifie que, pour chaque ligne, la totalité ou une partie de la quantité a été enregistrée dans un journal des arrivées.</span><span class="sxs-lookup"><span data-stu-id="180b3-115">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   <span data-ttu-id="180b3-116">Incomplète (Affiche les lignes des réceptions dans lesquelles la progression est Aucune ou Partielle).</span><span class="sxs-lookup"><span data-stu-id="180b3-116">Not complete – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="180b3-117">Ceci signifie que, pour chaque ligne, soit la quantité n'a pas été enregistrée ou seule une partie l'a été dans un journal des arrivées.</span><span class="sxs-lookup"><span data-stu-id="180b3-117">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  
5. <span data-ttu-id="180b3-118">Développez ou réduisez la section Options des arrivées.</span><span class="sxs-lookup"><span data-stu-id="180b3-118">Expand or collapse the Arrival options section.</span></span>
6. <span data-ttu-id="180b3-119">Dans le champ Jours après, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="180b3-119">In the Days forward field, type a value.</span></span>
    * <span data-ttu-id="180b3-120">Ceci définit un filtre pour afficher les lignes de réception devant être reçues dans les prochains jours (selon le nombre que vous définissez).</span><span class="sxs-lookup"><span data-stu-id="180b3-120">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="180b3-121">Dans le champ Jours avant, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="180b3-121">In the Days back field, type a value.</span></span>
    * <span data-ttu-id="180b3-122">Ceci définit un filtre pour afficher les lignes de réception devant être reçu il y a un certain nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="180b3-122">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="180b3-123">Dans le champ Entrepôts , tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="180b3-123">In the Warehouses field, type a value.</span></span>
    * <span data-ttu-id="180b3-124">Filtrez sur un ou plusieurs entrepôts.</span><span class="sxs-lookup"><span data-stu-id="180b3-124">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="180b3-125">Sélectionnez une valeur dans le champ Mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="180b3-125">In the Mode of delivery field, select a value.</span></span>
    * <span data-ttu-id="180b3-126">Ceci définit un filtre pour afficher uniquement les lignes de réception avec ce mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="180b3-126">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="180b3-127">Sélectionnez WHS dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="180b3-127">In the Name field, select WHS.</span></span>
11. <span data-ttu-id="180b3-128">Dans le champ Entrepôt, sélectionnez l'entrepôt 24.</span><span class="sxs-lookup"><span data-stu-id="180b3-128">In the Warehouse field, select warehouse 24.</span></span>
    * <span data-ttu-id="180b3-129">Il s'agit de l'entrepôt par défaut utilisé pour les lignes de réception enregistrées qui utilisent ce profil.</span><span class="sxs-lookup"><span data-stu-id="180b3-129">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="180b3-130">Dans le champ Emplacement, sélectionnez Baydoor.</span><span class="sxs-lookup"><span data-stu-id="180b3-130">In the Location field, select Baydoor.</span></span>
    * <span data-ttu-id="180b3-131">Il s'agit de l'emplacement par défaut utilisé pour les lignes de réception enregistrées qui utilisent ce profil.</span><span class="sxs-lookup"><span data-stu-id="180b3-131">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="180b3-132">Développez ou réduisez la section Détails des requêtes des arrivées.</span><span class="sxs-lookup"><span data-stu-id="180b3-132">Expand or collapse the Arrival query details section.</span></span>
14. <span data-ttu-id="180b3-133">Sélectionnez site 2 dans le champ Limiter au site.</span><span class="sxs-lookup"><span data-stu-id="180b3-133">In the Restrict to site field, select site 2.</span></span>
    * <span data-ttu-id="180b3-134">Ceci définit un filtre pour afficher uniquement les lignes de réception avec ce site.</span><span class="sxs-lookup"><span data-stu-id="180b3-134">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="180b3-135">Définissez l'option Commandes fournisseur sur Oui.</span><span class="sxs-lookup"><span data-stu-id="180b3-135">Set the Purchase orders option to Yes.</span></span>
    * <span data-ttu-id="180b3-136">Sélectionnez des lignes de réception à partir de commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="180b3-136">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="180b3-137">Définissez l'option Ordres de transfert sur Oui.</span><span class="sxs-lookup"><span data-stu-id="180b3-137">Set the Transfer orders option to Yes.</span></span>
    * <span data-ttu-id="180b3-138">Sélectionnez des lignes de réception à partir d'ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="180b3-138">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="180b3-139">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="180b3-139">Click Save.</span></span>
18. <span data-ttu-id="180b3-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="180b3-140">Close the page.</span></span>
