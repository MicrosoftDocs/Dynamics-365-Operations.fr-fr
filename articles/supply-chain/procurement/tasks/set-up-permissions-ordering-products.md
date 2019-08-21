---
title: Paramétrer des autorisations permettant de commander des produits au nom d'un tiers
description: Cette procédure montre comment accorder à des collaborateurs l'autorisation de préparer des demandes d'achat au nom d'autres collaborateurs.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eea1577972879cc24a2295a0c5a8d7d3de5f4520
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837972"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a><span data-ttu-id="b4730-103">Paramétrer des autorisations permettant de commander des produits au nom d'un tiers</span><span class="sxs-lookup"><span data-stu-id="b4730-103">Set up permissions for ordering products on behalf of someone else</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b4730-104">Cette procédure montre comment accorder à des collaborateurs l'autorisation de préparer des demandes d'achat au nom d'autres collaborateurs.</span><span class="sxs-lookup"><span data-stu-id="b4730-104">This procedure shows how to grant workers permission to prepare purchase requisitions on behalf of other workers.</span></span> <span data-ttu-id="b4730-105">En d'autres termes, un « préparateur » de demande d'achat peut créer une demande pour un autre « demandeur ».</span><span class="sxs-lookup"><span data-stu-id="b4730-105">In other words, a purchase requisition “preparer” can create a requisition for another “requester.”</span></span> <span data-ttu-id="b4730-106">La procédure montre également comment accorder à un collaborateur une autorisation de commander des articles et des services dans différentes entités juridiques ou unités opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="b4730-106">The procedure also shows how to grant a worker permission to order items and services in different legal entities or operating units.</span></span> <span data-ttu-id="b4730-107">Ces tâches sont généralement effectuées par un gestionnaire des achats.</span><span class="sxs-lookup"><span data-stu-id="b4730-107">Typically, these tasks are performed by a purchasing manager.</span></span> <span data-ttu-id="b4730-108">Vous pouvez utiliser cette procédure soit dans les données fictives de la société USMF soit dans vos propres données.</span><span class="sxs-lookup"><span data-stu-id="b4730-108">You can use this procedure either on data for the USMF demo company or on your own data.</span></span>


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a><span data-ttu-id="b4730-109">Accorder des autorisations pour entrer des demandes d'achat au nom d'un autre collaborateur</span><span class="sxs-lookup"><span data-stu-id="b4730-109">Grant permission to enter purchase requisitions on behalf of another worker</span></span>
1. <span data-ttu-id="b4730-110">Allez dans Approvisionnements > Paramétrage > Stratégies > Autorisations de demande d'achat.</span><span class="sxs-lookup"><span data-stu-id="b4730-110">Go to Procurement and sourcing > Setup > Policies > Purchase requisition permissions.</span></span>
    * <span data-ttu-id="b4730-111">Assurez-vous que le champ Vue actuelle est défini sur Par préparateur.</span><span class="sxs-lookup"><span data-stu-id="b4730-111">Make sure that the Current view field is set to By preparer.</span></span>  <span data-ttu-id="b4730-112">La liste du volet gauche montre les personnes qui peuvent recevoir les autorisations pour préparer des demandes au nom d'autres personnes.</span><span class="sxs-lookup"><span data-stu-id="b4730-112">The list in the left pane shows the people who can be granted permission to prepare requisitions on behalf of other people.</span></span>  
2. <span data-ttu-id="b4730-113">Choisissez la personne à qui accorder l'autorisation (le préparateur).</span><span class="sxs-lookup"><span data-stu-id="b4730-113">Select the person to grant permission to (the preparer).</span></span>
3. <span data-ttu-id="b4730-114">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b4730-114">Click Add.</span></span>
4. <span data-ttu-id="b4730-115">Trouvez et choisissez la personne à ajouter en tant que demandeur.</span><span class="sxs-lookup"><span data-stu-id="b4730-115">Find and select the person to add as a requester.</span></span>
    * <span data-ttu-id="b4730-116">Le demandeur est la personne au nom de qui le préparateur peut créer des demandes.</span><span class="sxs-lookup"><span data-stu-id="b4730-116">The requester is the person that the preparer can create requisitions on behalf of.</span></span>  
    * <span data-ttu-id="b4730-117">Dans le champ Autorisation, sélectionnez Spécifique si le préparateur doit pouvoir créer des demandes d'achat au nom du collaborateur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b4730-117">In the Authorization field, select Specific if the preparer should be able to create purchase requisitions on behalf of the selected worker.</span></span> <span data-ttu-id="b4730-118">Choisissez Génération d'états si le préparateur doit pouvoir également créer des demandes d'achat au nom de tous les collaborateurs placés sous son autorité.</span><span class="sxs-lookup"><span data-stu-id="b4730-118">Select Reporting if the preparer should also be able to create purchase requisitions on behalf of all workers who report to that worker.</span></span>  
5. <span data-ttu-id="b4730-119">Dans le champ Effet, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="b4730-119">In the Effective field, enter a date.</span></span>
6. <span data-ttu-id="b4730-120">Dans le champ Expiration, entrer une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="b4730-120">In the Expiration field, enter a date.</span></span>

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a><span data-ttu-id="b4730-121">Afficher les préparateurs qui ont l'autorisation de créer des demandes d'achat pour un collaborateur choisi</span><span class="sxs-lookup"><span data-stu-id="b4730-121">View preparers who have permission to create purchase requisitions for a selected worker</span></span>
1. <span data-ttu-id="b4730-122">Dans le champ Vue actuelle, choisissez « Par demandeur ».</span><span class="sxs-lookup"><span data-stu-id="b4730-122">In the Current view field, select 'By requester'.</span></span>
    * <span data-ttu-id="b4730-123">Cette vue affiche la liste de préparateurs qui ont le droit de créer des demandes d'achat au nom d'un collaborateur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b4730-123">This view shows a list of preparers who have been granted permission to create purchase requisitions on behalf of a selected worker.</span></span>  
2. <span data-ttu-id="b4730-124">Utilisez le filtre rapide pour trouver le collaborateur que vous venez d'ajouter en tant que demandeur.</span><span class="sxs-lookup"><span data-stu-id="b4730-124">Use the Quick Filter to find the worker that you just added as the requester.</span></span>
3. <span data-ttu-id="b4730-125">Sélectionnez le demandeur.</span><span class="sxs-lookup"><span data-stu-id="b4730-125">Select the requester.</span></span>
    * <span data-ttu-id="b4730-126">La liste des préparateurs montre les personnes qui ont l'autorisation de commander des articles au nom du demandeur qui est choisi dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="b4730-126">The Preparer list shows the people who have permission to order items on behalf of the requester who is selected in the left pane.</span></span>   <span data-ttu-id="b4730-127">Vous pouvez ajouter des préparateurs supplémentaires ici.</span><span class="sxs-lookup"><span data-stu-id="b4730-127">You can add additional preparers here.</span></span>   <span data-ttu-id="b4730-128">Cette vue vous laisse également accorder l'autorisation au demandeur de créer des demandes dans les entités juridiques et les unités opérationnelles qui ne sont pas l'entité juridique ou l'unité opérationnelle de cette personne.</span><span class="sxs-lookup"><span data-stu-id="b4730-128">This view also lets you grant the requester permission to create requisitions in legal entities and operating units that aren't that person's primary legal entity or operating unit.</span></span>  

