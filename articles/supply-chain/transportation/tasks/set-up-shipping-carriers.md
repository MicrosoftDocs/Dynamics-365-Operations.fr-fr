---
title: Paramétrer des transporteurs
description: Cette rubrique décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison.
author: ShylaThompson
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e6a29dce877a53d125c5a151da6cfbb13d46b29
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201592"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="cdc72-103">Paramétrer des transporteurs</span><span class="sxs-lookup"><span data-stu-id="cdc72-103">Set up shipping carriers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cdc72-104">Cette rubrique décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison.</span><span class="sxs-lookup"><span data-stu-id="cdc72-104">This topic shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="cdc72-105">Un coordinateur de transport pourra ensuite affecter un transporteur à une charge entrante ou sortante.</span><span class="sxs-lookup"><span data-stu-id="cdc72-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="cdc72-106">Créer un transporteur</span><span class="sxs-lookup"><span data-stu-id="cdc72-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="cdc72-107">Accédez à **Volet de navigation > Modules > Gestion du transport > Paramétrage > Transporteurs > Transporteurs**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-107">Go to **Navigation pane > Modules > Transportation management > Setup > Carriers > Shipping carriers**.</span></span>
2. <span data-ttu-id="cdc72-108">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-108">Select **New** in the Action pane.</span></span>
3. <span data-ttu-id="cdc72-109">Dans le champ **Transporteur**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cdc72-109">In the **Shipping carrier** field, type a value.</span></span>
4. <span data-ttu-id="cdc72-110">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="cdc72-111">Dans le champ **Mode**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-111">In the **Mode** field, select an option from the drop-down menu.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="cdc72-112">Renseigner les informations générales du transporteur</span><span class="sxs-lookup"><span data-stu-id="cdc72-112">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="cdc72-113">Activez ou désactivez l'extension de la section **Vue d'ensemble**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-113">Toggle the expansion of the **Overview** section.</span></span>
2. <span data-ttu-id="cdc72-114">Activez ou désactivez la case à cocher **Activation du transporteur**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-114">Check or uncheck the **Activate shipping carrier** checkbox.</span></span>
3. <span data-ttu-id="cdc72-115">Dans le champ **Compte fournisseur**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-115">In the **Vendor account** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="cdc72-116">Sélectionnez le compte fournisseur à affecter au transporteur.</span><span class="sxs-lookup"><span data-stu-id="cdc72-116">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="cdc72-117">Dans le champ **Type d'offre de transport**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="cdc72-117">In the **Transportation tender type** field, select an option.</span></span> <span data-ttu-id="cdc72-118">Sélectionnez **Manuel** pour utiliser la page Offre de transport ou sélectionnez **EDI** pour mettre à jour l'offre à l'aide de l'échange de données informatisé (EDI).</span><span class="sxs-lookup"><span data-stu-id="cdc72-118">Select **Manual** to use the Transportation Tender page, or select **EDI** to update the tender by using Electronic Data Interchange (EDI).</span></span>  
5. <span data-ttu-id="cdc72-119">Activez ou désactivez la case à cocher **Activer le classement du transporteur**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-119">Check or uncheck the **Activate carrier rating** checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="cdc72-120">Créer les services nécessaires pour le transporteur</span><span class="sxs-lookup"><span data-stu-id="cdc72-120">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="cdc72-121">Activez ou désactivez l'extension de la section **Services**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-121">Toggle the expansion of the **Services** section.</span></span>
2. <span data-ttu-id="cdc72-122">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-122">Select **New**.</span></span>
3. <span data-ttu-id="cdc72-123">Dans le champ **Service de transporteur**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cdc72-123">In the **Carrier service** field, type a value.</span></span>
4. <span data-ttu-id="cdc72-124">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-124">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="cdc72-125">Dans le champ **Mode de transport**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-125">In the **Transportation method** field, select an option from the drop-down menu.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="cdc72-126">Paramétrer l'adresse du transporteur (facultatif)</span><span class="sxs-lookup"><span data-stu-id="cdc72-126">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="cdc72-127">Activez ou désactivez l'extension de la section **Adresses**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-127">Toggle the expansion of the **Addresses** section.</span></span>
2. <span data-ttu-id="cdc72-128">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-128">Select **New**.</span></span>
3. <span data-ttu-id="cdc72-129">Dans le champ **Nom ou description**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cdc72-129">In the **Name or description** field, type a value.</span></span>
4. <span data-ttu-id="cdc72-130">Dans le champ **Pays/Région**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-130">In the **Country/region** field, select an option from the drop-down menu.</span></span>
5. <span data-ttu-id="cdc72-131">Dans le champ **ZIP/Code postal**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-131">In the **ZIP/postal code** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="cdc72-132">Dans le champ **Rue**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cdc72-132">In the **Street** field, type a value.</span></span>
7. <span data-ttu-id="cdc72-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-133">Select **OK**.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="cdc72-134">Paramétrer le profil de classement du transporteur</span><span class="sxs-lookup"><span data-stu-id="cdc72-134">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="cdc72-135">Activez ou désactivez l'extension de la section **Profils de classement**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-135">Toggle the expansion of the **Rating profiles** section.</span></span>
2. <span data-ttu-id="cdc72-136">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-136">Select **New**.</span></span>
3. <span data-ttu-id="cdc72-137">Dans le champ **Profil de classement**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cdc72-137">In the **Rating profile** field, type a value.</span></span>
4. <span data-ttu-id="cdc72-138">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="cdc72-139">Dans le champ **Site**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-139">In the **Site** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="cdc72-140">Dans le champ **Entrepôt**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-140">In the **Warehouse** field, select an option from the drop-down menu.</span></span>
7. <span data-ttu-id="cdc72-141">Dans le champ **Moteur de frais**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-141">In the **Rate engine** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="cdc72-142">Sélectionnez le moteur de frais correspondant au contrat que vous avez avec le transporteur.</span><span class="sxs-lookup"><span data-stu-id="cdc72-142">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
8. <span data-ttu-id="cdc72-143">Dans le champ **Données principales du taux**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-143">In the **Rate master** field, select an option from the drop-down menu.</span></span>
9. <span data-ttu-id="cdc72-144">Dans le champ **Moteur de temps de transit**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="cdc72-144">In the **Transit time engine** field, select an option from the drop-down menu.</span></span>
10. <span data-ttu-id="cdc72-145">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cdc72-145">Select **Save**.</span></span>

