--- 
title: "Paramétrer l'ID de TVA"
description: "Cette procédure décrit les conditions préalables à l'enregistrement de l'ID de TVA, par exemple le paramétrage d'un type d'enregistrement et son affectation à une catégorie d'enregistrement."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ff12ab434d88471452f191cd56b630419e07b22e
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-vat-id"></a><span data-ttu-id="fc358-103">Paramétrer l'ID de TVA</span><span class="sxs-lookup"><span data-stu-id="fc358-103">Set up VAT ID</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc358-104">Cette procédure décrit les conditions préalables à l'enregistrement de l'ID de TVA, par exemple le paramétrage d'un type d'enregistrement et son affectation à une catégorie d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="fc358-104">This procedure walks you through VAT ID registration prerequisites, such as setting up a registration type and assigning it to a registration category.</span></span> <span data-ttu-id="fc358-105">Vous trouverez des informations supplémentaires sur les ID d'enregistrement et leur traitement, notamment les conditions préalables requises, dans la rubrique d'aide sur les ID d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="fc358-105">You can find additional information about registration IDs and registration ID processing, including required prerequisites, in the Registration IDs help topic.</span></span> 

<span data-ttu-id="fc358-106">Les informations ici s'appliquent à tous les pays/régions européens.</span><span class="sxs-lookup"><span data-stu-id="fc358-106">The information here applies to all European countries/regions.</span></span> <span data-ttu-id="fc358-107">La tâche a été créée avec les données de démonstration de la société fictive DEMF, avec Allemagne comme adresse principale de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="fc358-107">The task was created using the demo data company DEMF with Germany as the legal entity primary address.</span></span> <span data-ttu-id="fc358-108">Cette tâche est destinée aux administrateurs système.</span><span class="sxs-lookup"><span data-stu-id="fc358-108">This task is intended for system administrators.</span></span> <span data-ttu-id="fc358-109">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="fc358-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="fc358-110">Accédez à Administration d'organisation > Carnet d'adresse global > Types d'enregistrement > Types d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="fc358-110">Go to Organization administration > Global address book > Registration types > Registration types.</span></span>
2. <span data-ttu-id="fc358-111">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fc358-111">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="fc358-112">Dans le champ Nom, tapez « ID de TVA ».</span><span class="sxs-lookup"><span data-stu-id="fc358-112">In the Name field, type 'VAT ID'.</span></span>
4. <span data-ttu-id="fc358-113">Dans le champ Description, entrez le numéro de TVA.</span><span class="sxs-lookup"><span data-stu-id="fc358-113">In the Description field, VAT number.</span></span>
5. <span data-ttu-id="fc358-114">Dans le champ Pays/Région, entrez ou sélectionnez une valeur DEU</span><span class="sxs-lookup"><span data-stu-id="fc358-114">In the Country/region field, enter or select a value DEU</span></span>
6. <span data-ttu-id="fc358-115">Sélectionnez Oui dans le champ Unique.</span><span class="sxs-lookup"><span data-stu-id="fc358-115">Select Yes in the Unique field.</span></span>
    * <span data-ttu-id="fc358-116">Activez cette case à cocher pour vérifier si l'ID de TVA est unique.</span><span class="sxs-lookup"><span data-stu-id="fc358-116">Select this check box to verify if the VAT ID is unique.</span></span>  
7. <span data-ttu-id="fc358-117">Sélectionnez Oui dans le champ Principal pour le pays.</span><span class="sxs-lookup"><span data-stu-id="fc358-117">Select Yes in the Primary for country field.</span></span>
    * <span data-ttu-id="fc358-118">Activez cette case à cocher si l'ID de TVA doit être effectif pour toutes les adresses appartenant au pays ou à la région spécifié.</span><span class="sxs-lookup"><span data-stu-id="fc358-118">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
8. <span data-ttu-id="fc358-119">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="fc358-119">Click Create.</span></span>
9. <span data-ttu-id="fc358-120">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="fc358-120">Click Add.</span></span>
10. <span data-ttu-id="fc358-121">Dans le champ Pays/Région, entrez ou sélectionnez une valeur ITA</span><span class="sxs-lookup"><span data-stu-id="fc358-121">In the Country/region field, enter or select a value ITA</span></span>
11. <span data-ttu-id="fc358-122">Dans le champ Format, tapez « ########### ».</span><span class="sxs-lookup"><span data-stu-id="fc358-122">In the Format field, type '###########'.</span></span>
    * <span data-ttu-id="fc358-123">Lorsque vous entrez un ID d'enregistrement de ce type pour le pays ou la région sélectionné, l'ID d'enregistrement est vérifié par rapport à ce format.</span><span class="sxs-lookup"><span data-stu-id="fc358-123">When you enter a registration ID of this type for the selected country/region, the registration ID will be verified against this format.</span></span>  
12. <span data-ttu-id="fc358-124">Activez la case à cocher Unique.</span><span class="sxs-lookup"><span data-stu-id="fc358-124">Select the Unique check box.</span></span>
    * <span data-ttu-id="fc358-125">Activez cette case à cocher pour vérifier si l'ID de TVA est unique.</span><span class="sxs-lookup"><span data-stu-id="fc358-125">Select this check box to verify if the VAT ID is unique.</span></span>  
13. <span data-ttu-id="fc358-126">Activez la case à cocher Principal pour le pays.</span><span class="sxs-lookup"><span data-stu-id="fc358-126">Select the Primary for country check box.</span></span>
    * <span data-ttu-id="fc358-127">Activez cette case à cocher si l'ID de TVA doit être effectif pour toutes les adresses appartenant au pays ou à la région spécifié.</span><span class="sxs-lookup"><span data-stu-id="fc358-127">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
14. <span data-ttu-id="fc358-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc358-128">Click Save.</span></span>
15. <span data-ttu-id="fc358-129">Accédez à Administration d'organisation > Carnet d'adresse global > Types d'enregistrement > Catégories d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="fc358-129">Go to Organization administration > Global address book > Registration types > Registration categories.</span></span>
16. <span data-ttu-id="fc358-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc358-130">Click New.</span></span>
17. <span data-ttu-id="fc358-131">Dans le champ Pays/Région, entrez ou sélectionnez la valeur d'ID de TVA, DEU</span><span class="sxs-lookup"><span data-stu-id="fc358-131">In the Country/region field, enter or select a value VAT ID, DEU</span></span>
18. <span data-ttu-id="fc358-132">Dans le champ Catégorie d'enregistrement, sélectionnez « ID TVA ».</span><span class="sxs-lookup"><span data-stu-id="fc358-132">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="fc358-133">Affectez le type d'enregistrement que vous avez créé précédemment à une catégorie d'enregistrement prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="fc358-133">Assign the registration type that you created earlier to a predefined Registration category.</span></span>  
19. <span data-ttu-id="fc358-134">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc358-134">Click New.</span></span>
20. <span data-ttu-id="fc358-135">Dans le champ Pays/Région, entrez ou sélectionnez la valeur d'ID de TVA, ITA</span><span class="sxs-lookup"><span data-stu-id="fc358-135">In the Country/region field, enter or select a value VAT ID, ITA</span></span>
21. <span data-ttu-id="fc358-136">Dans le champ Catégorie d'enregistrement, sélectionnez « ID TVA ».</span><span class="sxs-lookup"><span data-stu-id="fc358-136">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="fc358-137">Affectez le type d'enregistrement que vous avez créé à une catégorie d'enregistrement prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="fc358-137">Assign the registration type that you created to a predefined registration category.</span></span>  
22. <span data-ttu-id="fc358-138">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fc358-138">Click Save.</span></span>


