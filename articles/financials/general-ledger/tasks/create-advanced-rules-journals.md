---
title: Créer des règles avancées pour les journaux
description: Cette procédure consiste à créer des règles avancées pour les journaux.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3eb34ac419aeab3663a8931d022abf7bcbfddd37
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916141"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="6a195-103">Créer des règles avancées pour les journaux</span><span class="sxs-lookup"><span data-stu-id="6a195-103">Create advanced rules for journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6a195-104">Cette procédure consiste à créer des règles avancées pour les journaux.</span><span class="sxs-lookup"><span data-stu-id="6a195-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="6a195-105">Cela inclut de définir un contrôle des journaux et des restrictions de validation utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a195-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="6a195-106">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="6a195-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="6a195-107">Paramétrer le contrôle des journaux</span><span class="sxs-lookup"><span data-stu-id="6a195-107">Set up journal control</span></span>
1. <span data-ttu-id="6a195-108">Dans le **Volet de navigation**, allez dans **Modules > Comptabilité > Paramétrage du journal > Noms de journal**.</span><span class="sxs-lookup"><span data-stu-id="6a195-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="6a195-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a195-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="6a195-110">Dans le **Volet Actions**, cliquez sur **Contrôle des journaux**.</span><span class="sxs-lookup"><span data-stu-id="6a195-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="6a195-111">Dans l'organisateur **Quels types de compte peuvent être validés ?**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6a195-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="6a195-112">Dans le champ **Comptes société**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a195-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="6a195-113">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a195-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="6a195-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a195-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="6a195-115">Dans l'organisateur **Quelles valeurs de segment sont valides pour ce journal ?**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6a195-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="6a195-116">Dans le champ **Structure de compte**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a195-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="6a195-117">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a195-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="6a195-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a195-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="6a195-119">Dans le champ **Segment**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a195-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="6a195-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a195-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="6a195-121">Dans le champ **Valeur de début**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a195-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="6a195-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a195-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="6a195-123">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a195-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="6a195-124">Dans le champ **Valeur de fin**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a195-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="6a195-125">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a195-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="6a195-126">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a195-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="6a195-127">Paramétrage des restrictions de validation</span><span class="sxs-lookup"><span data-stu-id="6a195-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="6a195-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6a195-128">Close the page.</span></span>
2. <span data-ttu-id="6a195-129">Cliquez sur **Restrictions de validation**.</span><span class="sxs-lookup"><span data-stu-id="6a195-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="6a195-130">Dans le champ **Comment voulez-vous paramétrer des restrictions de validation ?**, sélectionnez par Groupe d'utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6a195-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="6a195-131">Dans l'arborescence, activez « Le groupe pour lequel vous souhaitez autoriser la validation pour ce nom de journal. ».</span><span class="sxs-lookup"><span data-stu-id="6a195-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="6a195-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a195-132">Click **OK**.</span></span>

