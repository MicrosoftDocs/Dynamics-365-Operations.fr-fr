--- 
title: "Créer des règles avancées pour les journaux"
description: "Cette procédure consiste à créer des règles avancées pour les journaux."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 36f4edd6fa9711022e291ea5ceffbcc9ef55b2a9
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="0fc85-103">Créer des règles avancées pour les journaux</span><span class="sxs-lookup"><span data-stu-id="0fc85-103">Create advanced rules for journals</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0fc85-104">Cette procédure consiste à créer des règles avancées pour les journaux.</span><span class="sxs-lookup"><span data-stu-id="0fc85-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="0fc85-105">Cela inclut de définir un contrôle des journaux et des restrictions de validation utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0fc85-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="0fc85-106">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="0fc85-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="0fc85-107">Paramétrer le contrôle des journaux</span><span class="sxs-lookup"><span data-stu-id="0fc85-107">Set up journal control</span></span>
1. <span data-ttu-id="0fc85-108">Accédez à Comptabilité > Paramétrage du journal > Noms des journaux.</span><span class="sxs-lookup"><span data-stu-id="0fc85-108">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="0fc85-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0fc85-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="0fc85-110">Cliquez sur Contrôle des journaux.</span><span class="sxs-lookup"><span data-stu-id="0fc85-110">Click Journal control.</span></span>
4. <span data-ttu-id="0fc85-111">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0fc85-111">Click Add.</span></span>
5. <span data-ttu-id="0fc85-112">Dans le champ Comptes société, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="0fc85-112">In the Company accounts field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="0fc85-113">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0fc85-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="0fc85-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0fc85-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="0fc85-115">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0fc85-115">Click Add.</span></span>
9. <span data-ttu-id="0fc85-116">Dans le champ Structure de compte, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="0fc85-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="0fc85-117">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0fc85-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="0fc85-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0fc85-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="0fc85-119">Dans le champ Segment, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="0fc85-119">In the Segment field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="0fc85-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0fc85-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="0fc85-121">Dans le champ Valeur de début, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="0fc85-121">In the From value field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="0fc85-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0fc85-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="0fc85-123">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0fc85-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="0fc85-124">Dans le champ Valeur de fin, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="0fc85-124">In the To value field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="0fc85-125">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0fc85-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="0fc85-126">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0fc85-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="0fc85-127">Paramétrage des restrictions de validation</span><span class="sxs-lookup"><span data-stu-id="0fc85-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="0fc85-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0fc85-128">Close the page.</span></span>
2. <span data-ttu-id="0fc85-129">Cliquez sur Restrictions de validation.</span><span class="sxs-lookup"><span data-stu-id="0fc85-129">Click Posting restrictions.</span></span>
3. <span data-ttu-id="0fc85-130">Dans le champ Comment voulez-vous paramétrer des restrictions de validation ?, sélectionnez par Groupe d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0fc85-130">In the How do you want to set up posting restrictions, select By user group.</span></span>
4. <span data-ttu-id="0fc85-131">Dans l'arborescence, activez « Le groupe pour lequel vous souhaitez autoriser la validation pour ce nom de journal. ».</span><span class="sxs-lookup"><span data-stu-id="0fc85-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="0fc85-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0fc85-132">Click OK.</span></span>


