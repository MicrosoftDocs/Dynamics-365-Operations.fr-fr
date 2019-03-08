---
title: EUR-00015 Paramétrer l'ID de TVA
description: Cette procédure décrit les conditions préalables à l'enregistrement de l'ID de TVA, par exemple le paramétrage d'un type d'enregistrement et son affectation à une catégorie d'enregistrement.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxRegistrationType, TaxRegistrationTypeCreate, TaxRegistrationLegislationTypes
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66ee7215dc21921f9d8e405c3f77d9b5e0b89a9e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "370729"
---
# <a name="eur-00015-set-up-vat-id"></a><span data-ttu-id="0614b-103">EUR-00015 Paramétrer l'ID de TVA</span><span class="sxs-lookup"><span data-stu-id="0614b-103">EUR-00015 Set up VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0614b-104">Cette procédure décrit les conditions préalables à l'enregistrement de l'ID de TVA, par exemple le paramétrage d'un type d'enregistrement et son affectation à une catégorie d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="0614b-104">This procedure walks you through VAT ID registration prerequisites, such as setting up a registration type and assigning it to a registration category.</span></span> <span data-ttu-id="0614b-105">Vous trouverez des informations supplémentaires sur les ID d'enregistrement et leur traitement, notamment les conditions préalables requises, dans la rubrique d'aide sur les ID d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="0614b-105">You can find additional information about registration IDs and registration ID processing, including required prerequisites, in the Registration IDs help topic.</span></span> 

<span data-ttu-id="0614b-106">Les informations ici s'appliquent à tous les pays/régions européens.</span><span class="sxs-lookup"><span data-stu-id="0614b-106">The information here applies to all European countries/regions.</span></span> <span data-ttu-id="0614b-107">La tâche a été créée avec les données de démonstration de la société fictive DEMF, avec Allemagne comme adresse principale de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="0614b-107">The task was created using the demo data company DEMF with Germany as the legal entity primary address.</span></span> <span data-ttu-id="0614b-108">Cette tâche est destinée aux administrateurs système.</span><span class="sxs-lookup"><span data-stu-id="0614b-108">This task is intended for system administrators.</span></span> <span data-ttu-id="0614b-109">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="0614b-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="0614b-110">Accédez à Administration d'organisation > Carnet d'adresse global > Types d'enregistrement > Types d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="0614b-110">Go to Organization administration > Global address book > Registration types > Registration types.</span></span>
2. <span data-ttu-id="0614b-111">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="0614b-111">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="0614b-112">Dans le champ Nom, tapez « ID de TVA ».</span><span class="sxs-lookup"><span data-stu-id="0614b-112">In the Name field, type 'VAT ID'.</span></span>
4. <span data-ttu-id="0614b-113">Dans le champ Description, entrez le numéro de TVA.</span><span class="sxs-lookup"><span data-stu-id="0614b-113">In the Description field, VAT number.</span></span>
5. <span data-ttu-id="0614b-114">Dans le champ Pays/Région, entrez ou sélectionnez une valeur DEU</span><span class="sxs-lookup"><span data-stu-id="0614b-114">In the Country/region field, enter or select a value DEU</span></span>
6. <span data-ttu-id="0614b-115">Sélectionnez Oui dans le champ Unique.</span><span class="sxs-lookup"><span data-stu-id="0614b-115">Select Yes in the Unique field.</span></span>
    * <span data-ttu-id="0614b-116">Activez cette case à cocher pour vérifier si l'ID de TVA est unique.</span><span class="sxs-lookup"><span data-stu-id="0614b-116">Select this check box to verify if the VAT ID is unique.</span></span>  
7. <span data-ttu-id="0614b-117">Sélectionnez Oui dans le champ Principal pour le pays.</span><span class="sxs-lookup"><span data-stu-id="0614b-117">Select Yes in the Primary for country field.</span></span>
    * <span data-ttu-id="0614b-118">Activez cette case à cocher si l'ID de TVA doit être effectif pour toutes les adresses appartenant au pays ou à la région spécifié.</span><span class="sxs-lookup"><span data-stu-id="0614b-118">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
8. <span data-ttu-id="0614b-119">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="0614b-119">Click Create.</span></span>
9. <span data-ttu-id="0614b-120">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0614b-120">Click Add.</span></span>
10. <span data-ttu-id="0614b-121">Dans le champ Pays/Région, entrez ou sélectionnez une valeur ITA</span><span class="sxs-lookup"><span data-stu-id="0614b-121">In the Country/region field, enter or select a value ITA</span></span>
11. <span data-ttu-id="0614b-122">Dans le champ Format, tapez « ########### ».</span><span class="sxs-lookup"><span data-stu-id="0614b-122">In the Format field, type '###########'.</span></span>
    * <span data-ttu-id="0614b-123">Lorsque vous entrez un ID d'enregistrement de ce type pour le pays ou la région sélectionné, l'ID d'enregistrement est vérifié par rapport à ce format.</span><span class="sxs-lookup"><span data-stu-id="0614b-123">When you enter a registration ID of this type for the selected country/region, the registration ID will be verified against this format.</span></span>  
12. <span data-ttu-id="0614b-124">Activez la case à cocher Unique.</span><span class="sxs-lookup"><span data-stu-id="0614b-124">Select the Unique check box.</span></span>
    * <span data-ttu-id="0614b-125">Activez cette case à cocher pour vérifier si l'ID de TVA est unique.</span><span class="sxs-lookup"><span data-stu-id="0614b-125">Select this check box to verify if the VAT ID is unique.</span></span>  
13. <span data-ttu-id="0614b-126">Activez la case à cocher Principal pour le pays.</span><span class="sxs-lookup"><span data-stu-id="0614b-126">Select the Primary for country check box.</span></span>
    * <span data-ttu-id="0614b-127">Activez cette case à cocher si l'ID de TVA doit être effectif pour toutes les adresses appartenant au pays ou à la région spécifié.</span><span class="sxs-lookup"><span data-stu-id="0614b-127">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
14. <span data-ttu-id="0614b-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0614b-128">Click Save.</span></span>
15. <span data-ttu-id="0614b-129">Accédez à Administration d'organisation > Carnet d'adresse global > Types d'enregistrement > Catégories d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="0614b-129">Go to Organization administration > Global address book > Registration types > Registration categories.</span></span>
16. <span data-ttu-id="0614b-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0614b-130">Click New.</span></span>
17. <span data-ttu-id="0614b-131">Dans le champ Pays/Région, entrez ou sélectionnez la valeur d'ID de TVA, DEU</span><span class="sxs-lookup"><span data-stu-id="0614b-131">In the Country/region field, enter or select a value VAT ID, DEU</span></span>
18. <span data-ttu-id="0614b-132">Dans le champ Catégorie d'enregistrement, sélectionnez « ID TVA ».</span><span class="sxs-lookup"><span data-stu-id="0614b-132">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="0614b-133">Affectez le type d'enregistrement que vous avez créé précédemment à une catégorie d'enregistrement prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="0614b-133">Assign the registration type that you created earlier to a predefined Registration category.</span></span>  
19. <span data-ttu-id="0614b-134">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0614b-134">Click New.</span></span>
20. <span data-ttu-id="0614b-135">Dans le champ Pays/Région, entrez ou sélectionnez la valeur d'ID de TVA, ITA</span><span class="sxs-lookup"><span data-stu-id="0614b-135">In the Country/region field, enter or select a value VAT ID, ITA</span></span>
21. <span data-ttu-id="0614b-136">Dans le champ Catégorie d'enregistrement, sélectionnez « ID TVA ».</span><span class="sxs-lookup"><span data-stu-id="0614b-136">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="0614b-137">Affectez le type d'enregistrement que vous avez créé à une catégorie d'enregistrement prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="0614b-137">Assign the registration type that you created to a predefined registration category.</span></span>  
22. <span data-ttu-id="0614b-138">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="0614b-138">Click Save.</span></span>

