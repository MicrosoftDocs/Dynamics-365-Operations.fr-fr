---
title: Créer et mettre à jour les heures d'ouverture du magasin
description: Cette rubrique décrit comment créer et mettre à jour les heures d'ouverture de magasin dans Retail Headquarters.
author: josaw1
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 1b55b91246b22951f4e1d148f59444423e1d8a3d
ms.sourcegitcommit: e54607a2c80bec4db05045825914f50947f6e31e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1917510"
---
# <a name="create-and-update-store-hours"></a><span data-ttu-id="85603-103">Créer et mettre à jour les heures d'ouverture du magasin</span><span class="sxs-lookup"><span data-stu-id="85603-103">Create and update store hours</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="85603-104">Présentation</span><span class="sxs-lookup"><span data-stu-id="85603-104">Overview</span></span>

<span data-ttu-id="85603-105">Depuis un emplacement unique, les détaillants peuvent créer, préserver et gérer les heures d'ouverture de magasin pour différents magasins dans diverses régions.</span><span class="sxs-lookup"><span data-stu-id="85603-105">From a single place, retailers can create, maintain, and manage the store hours for different stores across geographic regions.</span></span> <span data-ttu-id="85603-106">Les heures d'ouverture de magasin peuvent être indiquées sur les terminaux de point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="85603-106">The store hours can then be shown on point of sale (POS) terminals.</span></span> <span data-ttu-id="85603-107">De cette façon, les agents de caisse peuvent partager les heures d'ouverture de magasin avec les clients et mieux aider les clients intéressés par le stock d'autres magasins.</span><span class="sxs-lookup"><span data-stu-id="85603-107">In this way, cashiers can share store hours with customers and better help shoppers who are interested in inventory in other stores.</span></span> <span data-ttu-id="85603-108">Les heures d'ouverture de magasin peuvent être également imprimés sur les reçus, au cas où les clients souhaiteraient revenir ultérieurement au magasin.</span><span class="sxs-lookup"><span data-stu-id="85603-108">The store hours can also be printed on receipts, in case customers want to return to the store later.</span></span>

<span data-ttu-id="85603-109">Vous pouvez configurer plusieurs heures d'ouverture de magasin dans différents canaux.</span><span class="sxs-lookup"><span data-stu-id="85603-109">Multiple store hours can be configured across different channels.</span></span> <span data-ttu-id="85603-110">Ces canaux incluent des magasins physiques, des centres d'appel, des appareils mobiles et des sites de commerce en ligne.</span><span class="sxs-lookup"><span data-stu-id="85603-110">These channels include brick-and-mortar stores, call centers, mobile devices, and e-Commerce sites.</span></span>

<span data-ttu-id="85603-111">Si un client a un ordre de prélèvement pour un autre magasin, l'agent de caisse peut sélectionner les dates lorsque le prélèvement sera disponible dans ce magasin.</span><span class="sxs-lookup"><span data-stu-id="85603-111">If a customer has a pickup order for a different store, the cashier can select dates when the pickup will be available in that store.</span></span> <span data-ttu-id="85603-112">La recherche du magasin génère une référence aux dates et heures d'ouverture de magasin.</span><span class="sxs-lookup"><span data-stu-id="85603-112">The store lookup will provide a reference to the dates and store times.</span></span> <span data-ttu-id="85603-113">L'agent de caisse peut sélectionner une date et un emplacement, et il peut imprimer un bon de prélèvement incluant les heures d'ouverture de magasin.</span><span class="sxs-lookup"><span data-stu-id="85603-113">The cashier can select a date and location, and can also print a pickup receipt that includes the store hours.</span></span>

<span data-ttu-id="85603-114">Cette fonctionnalité est disponible dans Microsoft Dynamics 365 for Retail, versions 8.1.2 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="85603-114">This functionality is available in Microsoft Dynamics 365 for Retail versions 8.1.2 and later.</span></span>

## <a name="configure-store-hours"></a><span data-ttu-id="85603-115">Configurer les heures d'ouverture de magasin</span><span class="sxs-lookup"><span data-stu-id="85603-115">Configure store hours</span></span>

<span data-ttu-id="85603-116">Pour configurer les heures d'ouverture de magasin, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="85603-116">Follow these steps to configure store hours.</span></span>

1. <span data-ttu-id="85603-117">Accédez à **Vente au détail** \> **Paramétrage du canal** \> **Groupes d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="85603-117">Go to **Retail** \> **Channel Setup** \> **Store hours**.</span></span>
2. <span data-ttu-id="85603-118">Sélectionnez **Nouveau** pour créer un modèle d'heures d'ouverture de magasin.</span><span class="sxs-lookup"><span data-stu-id="85603-118">Select **New** to create a new store hours template.</span></span> <span data-ttu-id="85603-119">Pour utiliser un modèle existant, sélectionnez le modèle dans le volet de gauche.</span><span class="sxs-lookup"><span data-stu-id="85603-119">To use an existing template, select the template in the left pane.</span></span>
3. <span data-ttu-id="85603-120">Dans la boîte de dialogue **Ajouter une plage**, définissez la plage de dates, les heures d'ouverture de magasin et les congés requis.</span><span class="sxs-lookup"><span data-stu-id="85603-120">In the **Add range** dialog box, define the date range, the store hours, and any holidays that are required.</span></span>

    - <span data-ttu-id="85603-121">Si les heures d'ouverture de magasin ne changent pas, sélectionnez **Ne s'arrête jamais** dans le champ **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="85603-121">If store hours don't change, select **Never ends** in the **End date** field.</span></span>
    - <span data-ttu-id="85603-122">Si les heures d'ouverture de magasin sont spécifiques à un mois, une semaine ou une journée, définissez les dates appropriées dans les champs **Date de début** et **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="85603-122">If the store hours are for a specific month, week, or day, set the appropriate dates in the **Start Date** and **End date** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="85603-123">Vous pouvez créer plusieurs modèles avec des dates de début et de fin se chevauchant.</span><span class="sxs-lookup"><span data-stu-id="85603-123">You can create multiple templates that have overlapping start and end dates.</span></span> <span data-ttu-id="85603-124">Par conséquent, vous pouvez, par exemple, définir les heures d'ouverture de magasin pour les magasins dans différents fuseaux horaires.</span><span class="sxs-lookup"><span data-stu-id="85603-124">Therefore, you can, for example, define store hours for stores in different time zones.</span></span>

    <span data-ttu-id="85603-125">![Boîte de dialogue Ajouter une plage](../dev-itpro/media/Storehours1.png "Boîte de dialogue Ajouter une plage")</span><span class="sxs-lookup"><span data-stu-id="85603-125">![Add range dialog box](../dev-itpro/media/Storehours1.png "Add range dialog box")</span></span>

4. <span data-ttu-id="85603-126">Associez le modèle des heures d'ouverture de magasin avec les magasins où il est utilisé.</span><span class="sxs-lookup"><span data-stu-id="85603-126">Associate the store hours template with the stores where it will be used.</span></span> <span data-ttu-id="85603-127">Dans la boîte de dialogue **Choisir des nœuds d'organisation**, sélectionnez les magasins, les régions et les organisations auxquels le modèle doit être associé.</span><span class="sxs-lookup"><span data-stu-id="85603-127">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>

    - <span data-ttu-id="85603-128">Seul un modèle d'heures d'ouverture de magasin peut être associé à chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="85603-128">Only one store hours template can be associated with each store.</span></span>
    - <span data-ttu-id="85603-129">Utilisez les boutons de flèche pour sélectionner les magasins, les régions ou les organisations.</span><span class="sxs-lookup"><span data-stu-id="85603-129">Use the arrow buttons to select stores, regions, or organizations.</span></span> <span data-ttu-id="85603-130">Le calendrier est disponible pour les magasins ou les groupes de magasins, et il est visible au PDV pour référence.</span><span class="sxs-lookup"><span data-stu-id="85603-130">The calendar will be available to the stores or store groups, and it will be visible at the POS for reference.</span></span>

    <span data-ttu-id="85603-131">![Boîte de dialogue Choisir des nœuds d'organisation](../dev-itpro/media/Storehours2.png "Boîte de dialogue Choisir des nœuds d'organisation")</span><span class="sxs-lookup"><span data-stu-id="85603-131">![Choose organization nodes dialog box](../dev-itpro/media/Storehours2.png "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="85603-132">Sur la page **Programme de distribution**, exécutez les tâches **1070** et **1090** pour rendre les heures d'ouverture de magasin disponibles au PDV.</span><span class="sxs-lookup"><span data-stu-id="85603-132">On the **Distribution schedule** page, run the **1070** and **1090** jobs to make the store hours available to the POS.</span></span>

## <a name="add-store-hours-to-printed-receipts"></a><span data-ttu-id="85603-133">Ajouter les heures d'ouverture de magasin aux reçus imprimés</span><span class="sxs-lookup"><span data-stu-id="85603-133">Add store hours to printed receipts</span></span>

<span data-ttu-id="85603-134">Procédez comme suit pour ajouter des heures d'ouverture de magasin aux reçus du PDV imprimés.</span><span class="sxs-lookup"><span data-stu-id="85603-134">Follow these steps to add store hours to the printed POS receipts.</span></span>

1. <span data-ttu-id="85603-135">Ouvrez le concepteur de reçus.</span><span class="sxs-lookup"><span data-stu-id="85603-135">Open the receipt designer.</span></span>
2. <span data-ttu-id="85603-136">Sélectionnez **Pied de page** dans l'angle inférieur gauche.</span><span class="sxs-lookup"><span data-stu-id="85603-136">Select **Footer** in the lower-left corner.</span></span>
3. <span data-ttu-id="85603-137">Faites glisser l'élément **Heures d'ouverture de magasin** du volet gauche vers le pied de page en bas du modèle de ticket de caisse.</span><span class="sxs-lookup"><span data-stu-id="85603-137">Drag the **Store hours** element from the left pane to the footer at the bottom of the receipt template.</span></span>
4. <span data-ttu-id="85603-138">Vous pouvez modifier l'étiquette par défaut sur l'élément **Heures d'ouverture de magasin**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="85603-138">You can edit the default label on the **Store hours** element as you require.</span></span>
5. <span data-ttu-id="85603-139">Enregistrez le reçu, puis fermez le concepteur de reçus.</span><span class="sxs-lookup"><span data-stu-id="85603-139">Save the receipt, and close the receipt designer.</span></span>
6. <span data-ttu-id="85603-140">Sur la page **Programme de distribution**, exécutez les tâches **1070** et **1090**.</span><span class="sxs-lookup"><span data-stu-id="85603-140">On the **Distribution schedule** page, run the **1070** and **1090** jobs.</span></span>
7. <span data-ttu-id="85603-141">Connectez-vous au PDV.</span><span class="sxs-lookup"><span data-stu-id="85603-141">Sign in to the POS.</span></span>
8. <span data-ttu-id="85603-142">Validez la vente et sélectionnez pour imprimer un reçu.</span><span class="sxs-lookup"><span data-stu-id="85603-142">Complete a sale, and select to print a receipt.</span></span>

<span data-ttu-id="85603-143">Les reçus du PDV incluent désormais les heures d'ouverture de magasin.</span><span class="sxs-lookup"><span data-stu-id="85603-143">POS receipts now include the store hours.</span></span> <span data-ttu-id="85603-144">Si des congés sont inclus dans le modèle, ils figurent sur le ticket de caisse.</span><span class="sxs-lookup"><span data-stu-id="85603-144">If any holidays were included in the template, they are shown on the receipt.</span></span>

<span data-ttu-id="85603-145">![Exemple de reçu](../dev-itpro/media/Storehours3.png "Exemple de reçu")</span><span class="sxs-lookup"><span data-stu-id="85603-145">![Receipt example](../dev-itpro/media/Storehours3.png "Receipt example")</span></span>
