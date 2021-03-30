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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e61ed731c4040e7351e20421f6cf217ae9a4641d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222357"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="1094e-103">Créer des règles avancées pour les journaux</span><span class="sxs-lookup"><span data-stu-id="1094e-103">Create advanced rules for journals</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1094e-104">Cette procédure consiste à créer des règles avancées pour les journaux.</span><span class="sxs-lookup"><span data-stu-id="1094e-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="1094e-105">Cela inclut de définir un contrôle des journaux et des restrictions de validation utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1094e-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="1094e-106">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="1094e-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="1094e-107">Paramétrer le contrôle des journaux</span><span class="sxs-lookup"><span data-stu-id="1094e-107">Set up journal control</span></span>
1. <span data-ttu-id="1094e-108">Dans le **Volet de navigation**, allez dans **Modules > Comptabilité > Paramétrage du journal > Noms de journal**.</span><span class="sxs-lookup"><span data-stu-id="1094e-108">In the **Navigation pane**, go to **Modules > General ledger > Journal setup > Journal names**.</span></span>
2. <span data-ttu-id="1094e-109">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1094e-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1094e-110">Dans le **Volet Actions**, cliquez sur **Contrôle des journaux**.</span><span class="sxs-lookup"><span data-stu-id="1094e-110">On the **Action pane**, click **Journal control**.</span></span>
4. <span data-ttu-id="1094e-111">Dans l’organisateur **Quels types de compte peuvent être validés ?**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1094e-111">In the **Which account types can be posted** fastTab, click **Add**.</span></span>
5. <span data-ttu-id="1094e-112">Dans le champ **Comptes société**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1094e-112">In the **Company accounts** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1094e-113">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1094e-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="1094e-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1094e-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="1094e-115">Dans l’organisateur **Quelles valeurs de segment sont valides pour ce journal ?**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1094e-115">In the **Which segment values are valid for this journal** fastTab, click **Add**.</span></span>
9. <span data-ttu-id="1094e-116">Dans le champ **Structure de compte**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1094e-116">In the **Account structure** field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="1094e-117">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1094e-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="1094e-118">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1094e-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="1094e-119">Dans le champ **Segment**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1094e-119">In the **Segment** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="1094e-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1094e-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="1094e-121">Dans le champ **Valeur de début**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1094e-121">In the **From value** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="1094e-122">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1094e-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="1094e-123">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1094e-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="1094e-124">Dans le champ **Valeur de fin**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="1094e-124">In the **To value** field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="1094e-125">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1094e-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="1094e-126">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1094e-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="1094e-127">Paramétrage des restrictions de validation</span><span class="sxs-lookup"><span data-stu-id="1094e-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="1094e-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1094e-128">Close the page.</span></span>
2. <span data-ttu-id="1094e-129">Cliquez sur **Restrictions de validation**.</span><span class="sxs-lookup"><span data-stu-id="1094e-129">Click **Posting restrictions**.</span></span>
3. <span data-ttu-id="1094e-130">Dans le champ **Comment voulez-vous paramétrer des restrictions de validation ?**, sélectionnez par Groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1094e-130">In the **How do you want to set up posting restrictions** field, select 'By user group'.</span></span>
4. <span data-ttu-id="1094e-131">Dans l’arborescence, activez « Le groupe pour lequel vous souhaitez autoriser la validation pour ce nom de journal. ».</span><span class="sxs-lookup"><span data-stu-id="1094e-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="1094e-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1094e-132">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]