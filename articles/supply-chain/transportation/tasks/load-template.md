---
title: Modèles de chargement
description: Cette rubrique décrit comment paramétrer des modèles de charge et comment associer un modèle de charge à une nouvelle charge.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1ea7f5244b483a1b9d6c55227c676a3878a71d83
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646388"
---
# <a name="load-templates"></a><span data-ttu-id="9a448-103">Modèles de chargement</span><span class="sxs-lookup"><span data-stu-id="9a448-103">Load templates</span></span>

<span data-ttu-id="9a448-104">Lorsque vous créez une charge, vous pouvez attribuer un modèle de charge.</span><span class="sxs-lookup"><span data-stu-id="9a448-104">When you create a new load, you can assign a load template.</span></span> <span data-ttu-id="9a448-105">Le modèle de chargement contient des informations sur l'équipement et sur des mesures telles que la hauteur, la largeur, la profondeur et le volume de la charge.</span><span class="sxs-lookup"><span data-stu-id="9a448-105">The load template contains information about equipment, and about measures such as the height, width, depth, and volume of the load.</span></span>

<span data-ttu-id="9a448-106">Cette rubrique décrit comment paramétrer des modèles de charge et comment associer un modèle de charge à une nouvelle charge.</span><span class="sxs-lookup"><span data-stu-id="9a448-106">This topic describes how to set up load templates, and how to associate a load template with a new load.</span></span>

## <a name="set-up-a-load-template"></a><span data-ttu-id="9a448-107">Définir un modèle de chargement</span><span class="sxs-lookup"><span data-stu-id="9a448-107">Set up a load template</span></span>

1. <span data-ttu-id="9a448-108">Aller à **Gestion des transports \> Configurer \> Création de charge \> Modèle de charge**.</span><span class="sxs-lookup"><span data-stu-id="9a448-108">Go to **Transportation management \> Setup \> Load Building \> Load template**.</span></span>
1. <span data-ttu-id="9a448-109">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un nouveau modèle, ou sélectionnez **Modifier** pour modifier un modèle existant.</span><span class="sxs-lookup"><span data-stu-id="9a448-109">On the Action Pane, select **New** to add a new template or **Edit** to edit an existing template.</span></span>
1. <span data-ttu-id="9a448-110">Dans la ligne du modèle nouveau ou existant, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="9a448-110">In the row for the new or existing template, set the following fields:</span></span>

    - <span data-ttu-id="9a448-111">**ID de modèle de chargement** – Entrez un identificateur (ID) unique pour la charge.</span><span class="sxs-lookup"><span data-stu-id="9a448-111">**Load template ID** – Enter a unique identifier (ID) for the load template.</span></span>
    - <span data-ttu-id="9a448-112">**Équipement** – Sélectionnez l'équipement à utiliser pour expédier le chargement.</span><span class="sxs-lookup"><span data-stu-id="9a448-112">**Equipment** – Select the equipment that should be used to ship the load.</span></span>
    - <span data-ttu-id="9a448-113">**Hauteur de chargement**, **Largeur de chargement**, et **Profondeur de chargement** – Entrez les dimensions de la charge.</span><span class="sxs-lookup"><span data-stu-id="9a448-113">**Load height**, **Load width**, and **Load depth** – Enter the dimensions of the load.</span></span>
    - <span data-ttu-id="9a448-114">**Volume de chargement autorisé max.** et **Poids de charge autorisé max.** – Entrez le volume et le poids maximum autorisés de la charge.</span><span class="sxs-lookup"><span data-stu-id="9a448-114">**Max. allowed load volume** and **Max. allowed load weight** – Enter the maximum allowed volume and weight of the load.</span></span>
    - <span data-ttu-id="9a448-115">**Poids brut autorisé maximum** – Entrez le poids brut autorisé maximum de la charge.</span><span class="sxs-lookup"><span data-stu-id="9a448-115">**Maximum allowed gross weight** – Enter the maximum allowed gross weight of the load.</span></span> <span data-ttu-id="9a448-116">Un poids brut de la charge comprend le poids de la tare et le poids de la charge.</span><span class="sxs-lookup"><span data-stu-id="9a448-116">A load's gross weight includes both its tare weight and its loading weight.</span></span>
    - <span data-ttu-id="9a448-117">**Nombre maximum de pièces de fret autorisé** – Entrez le nombre maximum de pièces de fret que le chargement peut contenir.</span><span class="sxs-lookup"><span data-stu-id="9a448-117">**Maximum number of freight pieces allowed** – Enter the maximum number of freight pieces that the load can contain.</span></span>
    - <span data-ttu-id="9a448-118">**Empiler la charge au sol**–- Cochez cette case pour utiliser le chargement au sol.</span><span class="sxs-lookup"><span data-stu-id="9a448-118">**Stack load on floor** – Select this check box to use floor loading.</span></span> <span data-ttu-id="9a448-119">Dans un scénario de chargement au sol, les boîtes sont empilées du sol au plafond et d'un mur à l'autre dans le conteneur afin de maximiser la capacité.</span><span class="sxs-lookup"><span data-stu-id="9a448-119">In a floor loading scenario, boxes are stacked floor to ceiling and wall to wall inside the container, to maximize capacity.</span></span>

1. <span data-ttu-id="9a448-120">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9a448-120">On the Action Pane, select **Save**.</span></span>

## <a name="associate-a-load-template-with-a-new-load"></a><span data-ttu-id="9a448-121">Associer un modèle de charge à une nouvelle charge</span><span class="sxs-lookup"><span data-stu-id="9a448-121">Associate a load template with a new load</span></span>

1. <span data-ttu-id="9a448-122">Accédez à **Gestion du transport \> Planning \> Console de planification des charges**.</span><span class="sxs-lookup"><span data-stu-id="9a448-122">Go to **Transportation management \> Planning \> Load planning workbench**.</span></span>
1. <span data-ttu-id="9a448-123">Dans la partie supérieure de la page, sélectionnez l'un des onglets suivants, en fonction du type de document source pour lequel vous créez une charge : **Expéditions**, **Lignes de vente**, **Lignes de transfert**, ou **Lignes de commande d'achat**.</span><span class="sxs-lookup"><span data-stu-id="9a448-123">In the upper part of the page, select one of the following tabs, depending on the type of source document that you're creating a load for: **Shipments**, **Sales lines**, **Transfer lines**, or **Purchase order lines**.</span></span> 
1. <span data-ttu-id="9a448-124">Sélectionnez le document spécifique pour lequel planifier le chargement.</span><span class="sxs-lookup"><span data-stu-id="9a448-124">Select the specific document to plan the load for.</span></span>
1. <span data-ttu-id="9a448-125">Dans le volet Actions, sous l'onglet **Approvisionnement et demande**, dans le groupe **Ajouter**, sélectionnez **Dans un nouveau chargement**.</span><span class="sxs-lookup"><span data-stu-id="9a448-125">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span>
1. <span data-ttu-id="9a448-126">Dans la boîte de dialogue **Modèle de chargement**, dans le champ **ID modèle de chargement**, sélectionnez le modèle à appliquer.</span><span class="sxs-lookup"><span data-stu-id="9a448-126">In the **Load template** dialog box, in the **Load template ID** field, select the template to apply.</span></span>
1. <span data-ttu-id="9a448-127">Sélectionnez **OK** pour appliquer le modèle.</span><span class="sxs-lookup"><span data-stu-id="9a448-127">Select **OK** to apply the template.</span></span>
