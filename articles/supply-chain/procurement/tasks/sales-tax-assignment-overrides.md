--- 
title: Affectation et remplacement des taxes
description: "Cette procédure illustre comment affecter des groupes de taxe aux canaux de vente au détail."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a1907b0d0266eaa405ac2b92b40d6a2d310cf07b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="116ac-103">Affectation et remplacement des taxes</span><span class="sxs-lookup"><span data-stu-id="116ac-103">Sales tax assignment and overrides</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="116ac-104">Cette procédure illustre comment affecter des groupes de taxe aux canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="116ac-104">This procedure demonstrates how to assign sales tax groups to retail channels.</span></span> <span data-ttu-id="116ac-105">Elle décrit également le processus de création d'un nouveau remplacement de taxe et son affectation à un groupe de remplacement de taxe existant.</span><span class="sxs-lookup"><span data-stu-id="116ac-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="116ac-106">Cette procédure</span><span class="sxs-lookup"><span data-stu-id="116ac-106">This procedure</span></span>

<span data-ttu-id="116ac-107">utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="116ac-107">uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="116ac-108">Accédez à Commerce et vente au détail > Canaux > Magasins de vente au détail > Tous les magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="116ac-108">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="116ac-109">Dans la liste, cliquez sur le lien de l'ID canal de vente au détail pour « Houston. »</span><span class="sxs-lookup"><span data-stu-id="116ac-109">In the list, click the Retail Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="116ac-110">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="116ac-110">Click Edit.</span></span>
    * <span data-ttu-id="116ac-111">Le champ « Groupe de taxe » contient la liste des groupes de taxe pour la société actuelle.</span><span class="sxs-lookup"><span data-stu-id="116ac-111">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="116ac-112">Le groupe actuellement affecté est un groupe générique de taxe « Texas ».</span><span class="sxs-lookup"><span data-stu-id="116ac-112">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="116ac-113">Il y a également des groupes de taxes pour « Washington » et « Washington, comté de King »</span><span class="sxs-lookup"><span data-stu-id="116ac-113">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="116ac-114">Les groupes de taxes peuvent inclure des taxes applicables pour les différentes municipalités.</span><span class="sxs-lookup"><span data-stu-id="116ac-114">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="116ac-115">Le champ « Remplacement de taxe » est le champ où les groupes de remplacement de taxe peuvent être mis en correspondance avec le canal.</span><span class="sxs-lookup"><span data-stu-id="116ac-115">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="116ac-116">Les groupes de remplacement de taxe peuvent être employés pour regrouper les remplacements de taxe qui travaillent pour plusieurs magasins.</span><span class="sxs-lookup"><span data-stu-id="116ac-116">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="116ac-117">Plutôt que d'affecter manuellement des remplacements de taxe un par un, le groupe peut être créé et affecté directement aux canaux pour gagner du temps.</span><span class="sxs-lookup"><span data-stu-id="116ac-117">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="116ac-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="116ac-118">Click Save.</span></span>
5. <span data-ttu-id="116ac-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="116ac-119">Close the page.</span></span>
6. <span data-ttu-id="116ac-120">Allez dans Commerce et vente au détail > Paramétrage du canal > Taxes > Remplacements de taxe.</span><span class="sxs-lookup"><span data-stu-id="116ac-120">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="116ac-121">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="116ac-121">Click New.</span></span>
8. <span data-ttu-id="116ac-122">Dans le champ Remplacement de taxe, fournissez un nom pour votre nouveau dépassement.</span><span class="sxs-lookup"><span data-stu-id="116ac-122">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="116ac-123">Dans le champ Description, entrez la description du remplacement.</span><span class="sxs-lookup"><span data-stu-id="116ac-123">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="116ac-124">Définissez le statut sur « Activer ».</span><span class="sxs-lookup"><span data-stu-id="116ac-124">Set the status to "Enable."</span></span>
11. <span data-ttu-id="116ac-125">Développez ou réduisez la section Remplacer.</span><span class="sxs-lookup"><span data-stu-id="116ac-125">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="116ac-126">Sélectionnez une option dans le champ Type.</span><span class="sxs-lookup"><span data-stu-id="116ac-126">In the Type field, select an option.</span></span>
    * <span data-ttu-id="116ac-127">Les groupes de taxe d'article peuvent être employés pour remplacer des impôts pour des articles spécifiques qui appartiennent au groupe.</span><span class="sxs-lookup"><span data-stu-id="116ac-127">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="116ac-128">Par exemple, des produits alimentaires sont généralement imposés différemment des biens d'équipement, et auraient certainement leur propre groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="116ac-128">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span>     <span data-ttu-id="116ac-129">Les groupes de taxe sont des groupes qui s'appliquent à un canal particulier.</span><span class="sxs-lookup"><span data-stu-id="116ac-129">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="116ac-130">Par exemple, si un canal fait de la vente au détail et d'entreprise à entreprise, différents groupes de taxe de vente d'articles peuvent être employés.</span><span class="sxs-lookup"><span data-stu-id="116ac-130">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="116ac-131">Toutes les taxes applicables seraient mises en correspondance avec le groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="116ac-131">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="116ac-132">Maintenant vous pouvez choisir entre les taxes « De départ » et « D'arrivée » ou « Groupe de taxe de départ » et « Groupe de taxe d'arrivée » pour créer votre remplacement de taxe.</span><span class="sxs-lookup"><span data-stu-id="116ac-132">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span>    <span data-ttu-id="116ac-133">Le champ « De départ » indique l'impôt ou le groupe d'impôts à remplacer.</span><span class="sxs-lookup"><span data-stu-id="116ac-133">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="116ac-134">Le remplacement par le groupe de taxe d'article fournit des options différentes du remplacement par le groupe de taxe.</span><span class="sxs-lookup"><span data-stu-id="116ac-134">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span>    <span data-ttu-id="116ac-135">Remplacements de taxe peut être défini pour remplacer des taxes sur des transactions entières ou sur des lignes particulières de la transaction.</span><span class="sxs-lookup"><span data-stu-id="116ac-135">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="116ac-136">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="116ac-136">Click Save.</span></span>
14. <span data-ttu-id="116ac-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="116ac-137">Close the page.</span></span>
15. <span data-ttu-id="116ac-138">Allez dans Commerce et vente au détail > Paramétrage du canal > Taxes > Groupes de remplacement de taxe.</span><span class="sxs-lookup"><span data-stu-id="116ac-138">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="116ac-139">Dans cette étape, vous allez affecter le remplacement de taxe précédemment créé au groupe de remplacement de taxe affecté au canal « Houston ».</span><span class="sxs-lookup"><span data-stu-id="116ac-139">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="116ac-140">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="116ac-140">Click Edit.</span></span>
17. <span data-ttu-id="116ac-141">Développez ou réduisez la section Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="116ac-141">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="116ac-142">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="116ac-142">Click Add.</span></span>
19. <span data-ttu-id="116ac-143">Dans le champ Groupes de remplacement de taxe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="116ac-143">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="116ac-144">Choisissez le remplacement de taxe précédemment créé à partir de la liste.</span><span class="sxs-lookup"><span data-stu-id="116ac-144">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="116ac-145">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="116ac-145">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="116ac-146">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="116ac-146">Click Save.</span></span>


