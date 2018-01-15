--- 
title: "Paramétrer des périodes de règlement fiscal"
description: "Les périodes de règlement fiscal contiennent des informations sur l'intervalle pour lequel les taxes doivent être déclarées et payées."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: ab7d3a00a327f42a9f70c954d9b64a360a7f9163
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="02c85-103">Paramétrer des périodes de règlement fiscal</span><span class="sxs-lookup"><span data-stu-id="02c85-103">Set up sales tax settlement periods</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="02c85-104">Les périodes de règlement fiscal contiennent des informations sur l'intervalle pour lequel les taxes doivent être déclarées et payées.</span><span class="sxs-lookup"><span data-stu-id="02c85-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="02c85-105">Un processus de règlement peut être exécuté pour une période de règlement pour un intervalle de dates spécifique.</span><span class="sxs-lookup"><span data-stu-id="02c85-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="02c85-106">Tous les codes taxe associés à la période de règlement seront fixés.</span><span class="sxs-lookup"><span data-stu-id="02c85-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="02c85-107">Selon la configuration de l'administration fiscale associée, l'impôt à payer est validé soit dans un fournisseur soit dans un compte général.</span><span class="sxs-lookup"><span data-stu-id="02c85-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="02c85-108">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="02c85-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="02c85-109">Accédez à Taxes > Taxes indirectes >Taxe > Périodes de règlement fiscal.</span><span class="sxs-lookup"><span data-stu-id="02c85-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="02c85-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="02c85-110">Click New.</span></span>
3. <span data-ttu-id="02c85-111">Tapez une valeur dans le champ Période de règlement.</span><span class="sxs-lookup"><span data-stu-id="02c85-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="02c85-112">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="02c85-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="02c85-113">Dans le champ Administration, sélectionnez l'administration fiscale qui reçoit les états et les règlements créés pour la période de règlement.</span><span class="sxs-lookup"><span data-stu-id="02c85-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="02c85-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="02c85-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="02c85-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="02c85-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="02c85-116">Dans le champ Conditions de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="02c85-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="02c85-117">L'administration fiscale associée peut être paramétrée comme fournisseur et le règlement fiscal va créer une facture fournisseur en cours.</span><span class="sxs-lookup"><span data-stu-id="02c85-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="02c85-118">Les conditions de paiement définissent la date d'échéance pour la facture fournisseur en cours.</span><span class="sxs-lookup"><span data-stu-id="02c85-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="02c85-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="02c85-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="02c85-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="02c85-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="02c85-121">Sélectionnez un type pour les intervalles des périodes de règlement.</span><span class="sxs-lookup"><span data-stu-id="02c85-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="02c85-122">Entrez le nombre d'unités de l'intervalle par période.</span><span class="sxs-lookup"><span data-stu-id="02c85-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="02c85-123">Un trimestre a 3 mois, par exemple.</span><span class="sxs-lookup"><span data-stu-id="02c85-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="02c85-124">Activez ou désactivez la case à cocher Utiliser le traitement par lots pour le règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="02c85-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="02c85-125">Le processus de règlement pour la période de règlement peut être traité en tant que traitement par lots en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="02c85-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="02c85-126">Cette opération est recommandée pour un grand nombre de transactions de taxe dans un intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="02c85-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="02c85-127">Développez l'onglet Intervalles de périodes.</span><span class="sxs-lookup"><span data-stu-id="02c85-127">Expand the Period intervals tab.</span></span>
15. <span data-ttu-id="02c85-128">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="02c85-128">Click Add.</span></span>
16. <span data-ttu-id="02c85-129">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="02c85-129">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="02c85-130">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="02c85-130">In the From date field, enter a date.</span></span>
18. <span data-ttu-id="02c85-131">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="02c85-131">In the To date field, enter a date.</span></span>
19. <span data-ttu-id="02c85-132">Cliquez sur Nouvel intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="02c85-132">Click New period interval.</span></span>
    * <span data-ttu-id="02c85-133">Une fois que le premier intervalle de périodes a été entré, de nouvelles périodes peuvent être créées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="02c85-133">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="02c85-134">Si nécessaire, vous pouvez revenir et ajouter de nouveaux intervalles de périodes.</span><span class="sxs-lookup"><span data-stu-id="02c85-134">You can come back and add new period intervals as required.</span></span>  
20. <span data-ttu-id="02c85-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="02c85-135">Close the page.</span></span>

