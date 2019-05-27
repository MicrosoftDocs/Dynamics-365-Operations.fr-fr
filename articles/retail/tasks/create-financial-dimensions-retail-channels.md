---
title: Créer des dimensions financières pour les canaux de vente au détail et configurer les valeurs de dimension pour les magasins
description: Cette procédure vous guide au cours de la création d'une dimension financière de canal de vente au détail avec des valeurs de dimension et des étapes pour configurer les valeurs de dimension financière dans des magasins de vente au détail.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf32d17a36fd699141ce697d23e20b2eb5cbfa54
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566454"
---
# <a name="create-financial-dimensions-for-retail-channels-and-configure-dimension-values-on-stores"></a><span data-ttu-id="ba628-103">Créer des dimensions financières pour les canaux de vente au détail et configurer les valeurs de dimension pour les magasins</span><span class="sxs-lookup"><span data-stu-id="ba628-103">Create financial dimensions for retail channels and configure dimension values on stores</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="ba628-104">Cette procédure vous guide au cours de la création d'une dimension financière de canal de vente au détail avec des valeurs de dimension et des étapes pour configurer les valeurs de dimension financière dans des magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="ba628-104">This procedure walks through creating a retail channel financial dimension with dimension values and steps to configure financial dimension values on retail stores.</span></span> <span data-ttu-id="ba628-105">Le sujet n'inclut pas d'autres étapes associées, telles que la création d'ensembles de dimensions et de structures de compte.</span><span class="sxs-lookup"><span data-stu-id="ba628-105">The topic does not include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="ba628-106">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="ba628-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="ba628-107">Accédez à Comptabilité > Plan de comptes > Dimensions > Dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="ba628-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="ba628-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ba628-108">Click New.</span></span>
3. <span data-ttu-id="ba628-109">Dans le champ Utiliser les valeurs à partir de, sélectionnez « Canaux de vente au détail ».</span><span class="sxs-lookup"><span data-stu-id="ba628-109">In the Use values from field, select 'Retail channels'.</span></span>
4. <span data-ttu-id="ba628-110">Dans le champ Nom de la dimension, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ba628-110">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="ba628-111">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="ba628-111">Click Activate.</span></span>
6. <span data-ttu-id="ba628-112">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="ba628-112">Click Close.</span></span>
7. <span data-ttu-id="ba628-113">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="ba628-113">Click Activate.</span></span>
8. <span data-ttu-id="ba628-114">Cliquez sur les valeurs de dimension.</span><span class="sxs-lookup"><span data-stu-id="ba628-114">Click Dimension values.</span></span>
9. <span data-ttu-id="ba628-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ba628-115">Close the page.</span></span>
10. <span data-ttu-id="ba628-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ba628-116">Click Save.</span></span>
11. <span data-ttu-id="ba628-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ba628-117">Close the page.</span></span>
12. <span data-ttu-id="ba628-118">Accédez à Commerce et vente au détail > Canaux > Magasins de vente au détail > Tous les magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="ba628-118">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
13. <span data-ttu-id="ba628-119">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ba628-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="ba628-120">Activez ou désactivez l'extension de la section Dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="ba628-120">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="ba628-121">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ba628-121">Click Edit.</span></span>
16. <span data-ttu-id="ba628-122">Dans le champ Canal de vente au détail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ba628-122">In the Retailchannel field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="ba628-123">Dans la liste, recherchez et sélectionnez la valeur de dimension correspondant au magasin en cours de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="ba628-123">In the list, find and select the dimension value for the store being updated.</span></span>
18. <span data-ttu-id="ba628-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ba628-124">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="ba628-125">Dans le champ Centre de coût, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="ba628-125">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="ba628-126">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ba628-126">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="ba628-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ba628-127">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="ba628-128">Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Département.</span><span class="sxs-lookup"><span data-stu-id="ba628-128">In the Department field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="ba628-129">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="ba628-129">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="ba628-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ba628-130">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="ba628-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ba628-131">Click Save.</span></span>

