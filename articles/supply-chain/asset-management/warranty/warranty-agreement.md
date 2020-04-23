---
title: Contrats de garantie
description: Cette rubrique explique les contrats de garantie dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e9cbb9068101f3004179f338da18af0369190807
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215376"
---
# <a name="warranty-agreements"></a><span data-ttu-id="4bf9f-103">Contrats de garantie</span><span class="sxs-lookup"><span data-stu-id="4bf9f-103">Warranty agreements</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="4bf9f-104">Dans le module Gestion des actifs, vous pouvez configurer les conditions de la garantie à associer à un actif ou à un type d'actif.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-104">In Asset Management, you can set up warranty terms that can be connected to an asset or an asset type.</span></span> <span data-ttu-id="4bf9f-105">Les conditions de garantie sont créées pour une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-105">Warranty terms are created for a specific period.</span></span> <span data-ttu-id="4bf9f-106">La garantie peut être configurée pour offrir une couverture totale ou partielle et vous pouvez configurer les conditions associées aux heures, dépenses et articles.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-106">Warranty can be set up to provide full coverage or partial coverage, and you can set up terms that are related to hours, expenses, and items.</span></span>

<span data-ttu-id="4bf9f-107">La première étape consiste à créer des contrats de garantie fournisseur que vous avez pour votre équipement.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-107">The first step is to create any vendor warranty agreements that you have for your equipment.</span></span> <span data-ttu-id="4bf9f-108">Ensuite, vous joignez les contrats de garantie aux actifs ou types d'actif.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-108">You then attach warranty agreements to assets or asset types.</span></span> <span data-ttu-id="4bf9f-109">Les contrats de garantie fournisseur sont utilisés uniquement à titre informatif.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-109">Vendor warranty agreements are used only for informational purposes.</span></span> <span data-ttu-id="4bf9f-110">Si la garantie fournisseur est configurée sur un actif, vous pouvez voir la période de couverture de garantie sur l'actif.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-110">If vendor warranty is set up on an asset, you can see the warranty coverage period on the asset.</span></span>

## <a name="create-a-warranty-agreement"></a><span data-ttu-id="4bf9f-111">Créer un contrat de garantie</span><span class="sxs-lookup"><span data-stu-id="4bf9f-111">Create a warranty agreement</span></span>

<span data-ttu-id="4bf9f-112">Un contrat de garantie peut inclure plusieurs lignes de contrat pour couvrir la garantie pour les heures ouvrées, les dépenses et les articles.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-112">A warranty agreement can include several agreement lines to cover the warranty for work hours, expenses, and items.</span></span>

1. <span data-ttu-id="4bf9f-113">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Garantie**.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-113">Select **Asset management** \> **Setup** \> **Assets** \> **Warranty**.</span></span>
2. <span data-ttu-id="4bf9f-114">Sélectionnez **Nouveau** pour créer un produit.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-114">Select **New** to create a product.</span></span>
3. <span data-ttu-id="4bf9f-115">Dans le champ **Garantie**, entrez un ID de garantie.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-115">In the **Warranty** field, enter a warranty ID.</span></span>
4. <span data-ttu-id="4bf9f-116">Dans le champ **Nom**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="4bf9f-117">Dans l'organisateur **Détails**, le champ **Actifs** présente le nombre d'actifs actifs qui utilisent le contrat de garantie.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-117">On the **Details** FastTab, the **Assets** field shows the number of active assets that use the warranty agreement.</span></span>

5. <span data-ttu-id="4bf9f-118">Dans les organisateurs **Garantie des heures** et **Garantie des articles**, procédez comme suit pour ajouter les lignes à inclure dans un contrat de garantie qui concerne les heures ou les articles :</span><span class="sxs-lookup"><span data-stu-id="4bf9f-118">On the **Hour warranty** and **Item warranty** FastTabs, follow these steps to add lines that should be included in a warranty agreement that pertains to hours or items:</span></span>

    1. <span data-ttu-id="4bf9f-119">Sélectionnez **Ajouter une ligne** pour ajouter une nouvelle condition à la garantie.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-119">Select **Add line** to add a new condition to the warranty.</span></span> <span data-ttu-id="4bf9f-120">Un numéro de ligne séquentiel est automatiquement entrée dans le champ **Ligne** .</span><span class="sxs-lookup"><span data-stu-id="4bf9f-120">A sequential line number is automatically entered in the **Line** field.</span></span>
    2. <span data-ttu-id="4bf9f-121">Dans le champ **Période**, sélectionnez le type de période de garantie.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-121">In the **Period** field, select the type of warranty period.</span></span>
    3. <span data-ttu-id="4bf9f-122">Entrez un nombre dans le champ **Intervalle**.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-122">In the **Interval** field, enter a number.</span></span> <span data-ttu-id="4bf9f-123">Ce champ définit le nombre de périodes pour lesquelles la garantie doit être valide.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-123">This field defines the number of periods that the warranty should be valid for.</span></span>
    4. <span data-ttu-id="4bf9f-124">Dans le champ **Pourcentage**, entrez le pourcentage de couverture pour la ligne de garantie.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-124">In the **Percent** field, enter the coverage percentage for the warranty line.</span></span> <span data-ttu-id="4bf9f-125">Le pourcentage indique l'étendue de la couverture par votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="4bf9f-125">The percentage indicates how much is covered by your company.</span></span>

![Page de garantie](media/01-warranty.png)
