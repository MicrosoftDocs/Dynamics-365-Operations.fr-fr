---
title: Créer des dimensions financières pour les canaux de vente au détail et configurer les valeurs de dimension pour les magasins
description: Cette procédure vous guide au cours de la création d'une dimension financière de canal Commerce avec des valeurs de dimension et des étapes pour configurer les valeurs de dimension financière dans des magasins.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86fc9c9a400bee1280b32f10b1e8f55e581e1984
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964743"
---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="a3d7d-103">Créer des dimensions financières pour les canaux de vente au détail et configurer les valeurs de dimension pour les magasins</span><span class="sxs-lookup"><span data-stu-id="a3d7d-103">Create financial dimensions for retail channels and configure dimension values on stores</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3d7d-104">Cette procédure vous guide au cours de la création d'une dimension financière de canal Commerce avec des valeurs de dimension et des étapes pour configurer les valeurs de dimension financière dans des magasins.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-104">This procedure walks through creating a commerce channel financial dimension with dimension values and steps to configure financial dimension values on stores.</span></span> <span data-ttu-id="a3d7d-105">Le sujet n'inclut pas d'autres étapes associées, telles que la création d'ensembles de dimensions et de structures de compte.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="a3d7d-106">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="a3d7d-107">Accédez à Comptabilité > Plan de comptes > Dimensions > Dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="a3d7d-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-108">Click New.</span></span>
3. <span data-ttu-id="a3d7d-109">Dans le champ Utiliser les valeurs à partir de, sélectionnez « Canaux Commerce ».</span><span class="sxs-lookup"><span data-stu-id="a3d7d-109">In the Use values from field, select 'Commerce channels'.</span></span>
4. <span data-ttu-id="a3d7d-110">Dans le champ Nom de la dimension, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="a3d7d-111">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-111">Click Activate.</span></span>
6. <span data-ttu-id="a3d7d-112">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-112">Click Close.</span></span>
7. <span data-ttu-id="a3d7d-113">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-113">Click Activate.</span></span>
8. <span data-ttu-id="a3d7d-114">Cliquez sur les valeurs de dimension.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-114">Click Dimension values.</span></span>
9. <span data-ttu-id="a3d7d-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-115">Close the page.</span></span>
10. <span data-ttu-id="a3d7d-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-116">Click Save.</span></span>
11. <span data-ttu-id="a3d7d-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-117">Close the page.</span></span>
12. <span data-ttu-id="a3d7d-118">Accédez à Retail et Commerce > Canaux > Magasins > Tous les magasins.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-118">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
13. <span data-ttu-id="a3d7d-119">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="a3d7d-120">Activez ou désactivez l'extension de la section Dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="a3d7d-121">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-121">Click Edit.</span></span>
16. <span data-ttu-id="a3d7d-122">Dans le champ Canal Commerce, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-122">In the Commerce channel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="a3d7d-123">Dans la liste, recherchez et sélectionnez la valeur de dimension correspondant au magasin en cours de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="a3d7d-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="a3d7d-125">Dans le champ Centre de coût, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="a3d7d-126">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="a3d7d-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="a3d7d-128">Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Département.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="a3d7d-129">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="a3d7d-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="a3d7d-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a3d7d-131">Click Save.</span></span>

