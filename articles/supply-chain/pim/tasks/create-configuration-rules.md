---
title: Créer des règles de configuration
description: Cette procédure crée les règles de configuration qui peuvent être utilisées pour la configuration basée sur les dimensions pour forcer ou empêcher certaines combinaisons des lignes de nomenclature.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bc0af4d95e9430d0b5c8b7fc9a4ade076802044
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427892"
---
# <a name="create-configuration-rules"></a><span data-ttu-id="404d1-103">Créer des règles de configuration</span><span class="sxs-lookup"><span data-stu-id="404d1-103">Create configuration rules</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="404d1-104">Cette procédure crée les règles de configuration qui peuvent être utilisées pour la configuration basée sur les dimensions pour forcer ou empêcher certaines combinaisons des lignes de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="404d1-104">This procedure creates configuration rules that can be used for dimension-based configuration to enforce or prevent certain combinations of BOM lines.</span></span> <span data-ttu-id="404d1-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="404d1-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="404d1-106">Il s'agit de la septième procédure (parmi les huit) qui explique comment créer des combinaisons pour la configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="404d1-106">This is the seventh procedure out of eight that explains how to build combinations for dimension-based configuration.</span></span>

1. <span data-ttu-id="404d1-107">Accédez à Gestion d'informations sur les produits > Nomenclatures et formules > Nomenclature.</span><span class="sxs-lookup"><span data-stu-id="404d1-107">Go to Product information management > Bills of materials and formulas > Bills of materials.</span></span>
2. <span data-ttu-id="404d1-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="404d1-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="404d1-109">Trouvez et sélectionnez la nomenclature pour la configuration basée sur les dimensions.</span><span class="sxs-lookup"><span data-stu-id="404d1-109">Find and select the BOM for the dimension-based configuration.</span></span>  
3. <span data-ttu-id="404d1-110">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="404d1-110">On the Action Pane, click Options.</span></span>
4. <span data-ttu-id="404d1-111">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="404d1-111">Click Change view.</span></span>
5. <span data-ttu-id="404d1-112">Cliquez sur Vue de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="404d1-112">Click Header view.</span></span>
    * <span data-ttu-id="404d1-113">Ouvrez la vue en-tête pour accéder à l'organisateur Gamme de configuration.</span><span class="sxs-lookup"><span data-stu-id="404d1-113">Open the header view to access the Configuration route FastTab.</span></span>  
6. <span data-ttu-id="404d1-114">Développez ou réduisez la section Gamme de configuration.</span><span class="sxs-lookup"><span data-stu-id="404d1-114">Expand or collapse the Configuration route section.</span></span>
    * <span data-ttu-id="404d1-115">L'organisateur Gamme de configuration doit être en mode développé.</span><span class="sxs-lookup"><span data-stu-id="404d1-115">The Configuration route FastTab must be in the expanded mode.</span></span>  
7. <span data-ttu-id="404d1-116">Cliquez sur Règles de configuration.</span><span class="sxs-lookup"><span data-stu-id="404d1-116">Click Configuration rules.</span></span>
8. <span data-ttu-id="404d1-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="404d1-117">Click New.</span></span>
9. <span data-ttu-id="404d1-118">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="404d1-118">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="404d1-119">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="404d1-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="404d1-120">Les articles présents dans le groupe de configurations actuel sont affichés.</span><span class="sxs-lookup"><span data-stu-id="404d1-120">The items in the current configuration group are displayed.</span></span> <span data-ttu-id="404d1-121">Sélectionnez celui qui représente la condition dans la règle.</span><span class="sxs-lookup"><span data-stu-id="404d1-121">Select the one that represents the condition in the rule.</span></span>  
11. <span data-ttu-id="404d1-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="404d1-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="404d1-123">Sélectionnez une option dans le champ Méthode.</span><span class="sxs-lookup"><span data-stu-id="404d1-123">In the Method field, select an option.</span></span>
    * <span data-ttu-id="404d1-124">Il est possible d'appliquer une sélection ou une « désélection » d'un article d'un autre groupe de configurations.</span><span class="sxs-lookup"><span data-stu-id="404d1-124">It is possible to enforce either a selection or a deselection of an item from another configuration group.</span></span>  
13. <span data-ttu-id="404d1-125">Dans le champ Groupe dérivé, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="404d1-125">In the Derived group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="404d1-126">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="404d1-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="404d1-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="404d1-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="404d1-128">Sélectionnez le groupe de configuration souhaité.</span><span class="sxs-lookup"><span data-stu-id="404d1-128">Select the desired configuration group.</span></span>  
16. <span data-ttu-id="404d1-129">Dans le champ Numéro d'article dérivé, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="404d1-129">In the Derived item number field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="404d1-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="404d1-130">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="404d1-131">Sélectionnez le numéro d'article à sélectionner ou à désactiver en fonction de la méthode choisie.</span><span class="sxs-lookup"><span data-stu-id="404d1-131">Select the item number that will be either selected or deselected depending on the chosen method.</span></span>  
18. <span data-ttu-id="404d1-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="404d1-132">Close the page.</span></span>

