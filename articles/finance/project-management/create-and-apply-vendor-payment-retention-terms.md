---
title: Créer et appliquer des conditions de rétention de paiement fournisseur
description: Cette rubrique fournit des informations sur le paramétrage et le maintien à jour des conditions de rétention des paiements fournisseur.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410221"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a><span data-ttu-id="b9423-103">Créer et appliquer des conditions de rétention de paiement fournisseur</span><span class="sxs-lookup"><span data-stu-id="b9423-103">Create and apply vendor payment retention terms</span></span>

[!include [banner](../includes/banner.md)] 

<span data-ttu-id="b9423-104">La configuration des conditions de rétention des paiements fournisseur pour un projet est utile lorsque votre organisation souhaite retenir une partie des paiements effectués à un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9423-104">Setting up vendor payment retention terms for a project is useful when your organization wants to retain part of the payments made to a vendor.</span></span> <span data-ttu-id="b9423-105">Par exemple, lorsque vous souhaitez reporter le paiement à un fournisseur jusqu'à ce que les produits livrés répondent à vos attentes.</span><span class="sxs-lookup"><span data-stu-id="b9423-105">For example, when you want to hold payment to a vendor until the products delivered meet your expectations.</span></span> <span data-ttu-id="b9423-106">Les conditions de rétention des paiements fournisseur peuvent être stipulées au moment de la négociation d'un contrat avec le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9423-106">Vendor payment retention terms can be specified when you negotiate a vendor contract.</span></span>

## <a name="create-vendor-payment-retention-terms"></a><span data-ttu-id="b9423-107">Créer des conditions de rétention de paiement fournisseur</span><span class="sxs-lookup"><span data-stu-id="b9423-107">Create vendor payment retention terms</span></span>

<span data-ttu-id="b9423-108">Vous pouvez entrer le pourcentage du paiement fournisseur à retenir et le pourcentage des montants retenus précédemment à débloquer.</span><span class="sxs-lookup"><span data-stu-id="b9423-108">You can enter the percentage of vendor payment for retention and the percentage of the previously retained amounts to be released.</span></span> <span data-ttu-id="b9423-109">Les montants sont automatiquement retenus sur les factures fournisseur jusqu'à ce que le contrat atteigne le niveau d'achèvement désigné.</span><span class="sxs-lookup"><span data-stu-id="b9423-109">Amounts are automatically retained on vendor invoices until the contract reaches the specified state of completion.</span></span> <span data-ttu-id="b9423-110">Une fois les conditions de rétention définies pour un fournisseur, vous pouvez les appliquer à n'importe quel projet concernant ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9423-110">After you set up the retention terms, you can apply them to any project for that vendor.</span></span>

<span data-ttu-id="b9423-111">Procédez comme suit pour paramétrer et tenir à jour les conditions de rétention des paiements fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9423-111">Use the following steps to set up and maintain retention terms for vendor payments.</span></span> 

1. <span data-ttu-id="b9423-112">Accédez à **Gestion de projet et comptabilité** > **Rétention** > **Conditions de rétention des paiements fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="b9423-112">Go to **Project management and accounting** > **Retention** > **Vendor payment retention terms**.</span></span>
2. <span data-ttu-id="b9423-113">Sélectionnez **Nouveau** pour ajouter de nouvelles conditions de rétention fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9423-113">Select **New** to add a new vendor retention term.</span></span> <span data-ttu-id="b9423-114">La valeur de l'**ID de règle** des nouvelles conditions est entrée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b9423-114">The **Rule ID** value for the new term is automatically entered.</span></span> 
3. <span data-ttu-id="b9423-115">Entrez une brève description dans le champ **Description** et, dans le raccourci **Conditions**, sélectionnez **Ajouter une ligne** pour saisir des valeurs de condition pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b9423-115">Enter a brief description in the **Description** field, and on the **Terms** FastTab, select **Add line** to enter term values for the following:</span></span>

   - <span data-ttu-id="b9423-116">**Pourcentage d'unités livrées** : entrez un pourcentage d'achèvement pour la condition.</span><span class="sxs-lookup"><span data-stu-id="b9423-116">**Percentage of units delivered**: Enter a percentage of completion for the term.</span></span> <span data-ttu-id="b9423-117">Les montants sont automatiquement retenus sur les factures fournisseur jusqu'à ce que l'état d'avancement du projet soit égal au pourcentage spécifié.</span><span class="sxs-lookup"><span data-stu-id="b9423-117">Amounts are automatically retained on vendor invoices until the project stage of completion is equal to the specified percentage.</span></span> <span data-ttu-id="b9423-118">Par exemple, si vous entrez 50,00, les paiements sont retenus tant que le projet n'est pas terminé à 50 %.</span><span class="sxs-lookup"><span data-stu-id="b9423-118">For example, if you enter 50.00, amounts are retained until the project is 50 percent completed.</span></span>
   - <span data-ttu-id="b9423-119">**Pourcentage à retenir** : entrez le pourcentage du montant de la facture fournisseur à retenir.</span><span class="sxs-lookup"><span data-stu-id="b9423-119">**Percentage to retain**: Enter a percentage of the vendor invoice amount to be retained.</span></span> <span data-ttu-id="b9423-120">Par exemple, si vous entrez 10,00 dans ce champ, 10 % du montant de la facture fournisseur sera retenu jusqu'à ce que le projet atteigne le pourcentage d'achèvement sélectionné dans le champ **Pourcentage d'unités livrées**.</span><span class="sxs-lookup"><span data-stu-id="b9423-120">For example, if you enter 10.00, then 10 percent of the amount on a vendor invoice is retained until the project reaches the percentage of completion as set in the **Percentage of units delivered field**.</span></span>
   - <span data-ttu-id="b9423-121">**Pourcentage à débloquer** : sélectionnez **Ajouter une ligne** le pourcentage des montants précédemment retenus à débloquer au niveau d'achèvement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b9423-121">**Percentage to release**: Select **Add line** to enter a percentage of any previously retained amounts to be released for the selected level of project completion.</span></span>

> [!NOTE]
> <span data-ttu-id="b9423-122">Si vous avez plusieurs jalons pour différents niveaux d'achèvement du projet, entrez une ligne de conditions de rétention fournisseur distincte pour chaque règle de rétention.</span><span class="sxs-lookup"><span data-stu-id="b9423-122">If you have more than one milestone for different levels of project completion, enter a separate vendor retention term line for each retention rule.</span></span> <span data-ttu-id="b9423-123">Chaque ligne peut préciser un pourcentage différent à retenir ou à débloquer pour chaque niveau d'achèvement de projet désigné.</span><span class="sxs-lookup"><span data-stu-id="b9423-123">Each line can specify a different retention percentage and a different release percentage for each designated level of project completion.</span></span>

<span data-ttu-id="b9423-124">Une fois les conditions de rétention définies pour un fournisseur, vous pouvez les appliquer à un projet.</span><span class="sxs-lookup"><span data-stu-id="b9423-124">After you create vendor retention terms for a vendor, you can apply the terms to a project.</span></span>

## <a name="apply-vendor-retention-terms-to-a-project"></a><span data-ttu-id="b9423-125">Appliquer les conditions de rétention de paiement fournisseur à un projet</span><span class="sxs-lookup"><span data-stu-id="b9423-125">Apply vendor retention terms to a project</span></span>

1. <span data-ttu-id="b9423-126">Accédez à **Gestion de projet et comptabilité** > **Projets** > **Tous les projets** et ouvrez un projet à partir de la page de liste des projets.</span><span class="sxs-lookup"><span data-stu-id="b9423-126">Go to **Project management and accounting** > **Projects** > **All projects** and open a project from the project list page.</span></span>
2. <span data-ttu-id="b9423-127">Dans l'organisateur **Accords fournisseur**, cliquez sur **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="b9423-127">On the **Vendor agreements** FastTab, select **Add line**.</span></span>
3. <span data-ttu-id="b9423-128">Dans le champ **Code compte**, sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9423-128">In the **Account code field**, select one of the following options:</span></span> 

   - <span data-ttu-id="b9423-129">**Tableau** : Les conditions de rétention fournisseur s'appliquent à un seul fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9423-129">**Table**: The vendor retention terms apply to a single vendor.</span></span>
   - <span data-ttu-id="b9423-130">**Groupe** : Les conditions de rétention fournisseur s'appliquent à tous les fournisseurs du groupe de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="b9423-130">**Group**: The vendor retention terms apply to all vendors in a vendor group.</span></span>
   - <span data-ttu-id="b9423-131">**Tous** : Les conditions de rétention fournisseur s'appliquent à tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="b9423-131">**All**: The vendor retention terms apply to all vendors.</span></span>

4. <span data-ttu-id="b9423-132">Dans le champ **Fournisseur/Groupe de fournisseurs**, sélectionnez le fournisseur ou le groupe de fournisseurs auxquels les conditions de rétention fournisseur s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="b9423-132">In the **Vendor/Vendor group field**, select the vendor or vendor group to which the vendor retention terms apply.</span></span> <span data-ttu-id="b9423-133">Si vous avez sélectionné **Tous** à l'étape précédente, ce champ n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b9423-133">If you selected **All** in the previous step, this field is unavailable.</span></span>
5. <span data-ttu-id="b9423-134">Dans le champ **Conditions de rétention fournisseur**, sélectionnez les conditions de rétention que vous avez créées dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="b9423-134">In the **Vendor retention terms** field, select the retention terms that you created in the previous procedure.</span></span>
6. <span data-ttu-id="b9423-135">Si le projet a également une clause Payer quand payé paramétrée pour le fournisseur, entrez le pourcentage seuil du projet dans le champ **Pourcentage minimal de mise en œuvre de la clause Payer quand payé**.</span><span class="sxs-lookup"><span data-stu-id="b9423-135">If the project also has pay-when-paid (PWP) terms set up for the vendor, enter the threshold percentage for the project in the **PWP threshold percentage** field.</span></span>

<span data-ttu-id="b9423-136">Les conditions de rétention fournisseur sont également affichées dans les commandes fournisseur créées pour le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9423-136">The vendor retention terms are also displayed on purchase orders that you create for the vendor.</span></span>
