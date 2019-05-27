---
title: Paramétrer des périodes de règlement fiscal
description: Les périodes de règlement fiscal contiennent des informations sur l'intervalle pour lequel les taxes doivent être déclarées et payées.
author: twheeloc
manager: AnnBe
ms.date: 10/15/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1087ed78e91b487ca7157bfdac1d72ae3f477875
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569584"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="eb973-103">Paramétrer des périodes de règlement fiscal</span><span class="sxs-lookup"><span data-stu-id="eb973-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eb973-104">Les périodes de règlement fiscal contiennent des informations sur l'intervalle pour lequel les taxes doivent être déclarées et payées.</span><span class="sxs-lookup"><span data-stu-id="eb973-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="eb973-105">Un processus de règlement peut être exécuté pour une période de règlement pour un intervalle de dates spécifique.</span><span class="sxs-lookup"><span data-stu-id="eb973-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="eb973-106">Tous les codes taxe associés à la période de règlement seront fixés.</span><span class="sxs-lookup"><span data-stu-id="eb973-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="eb973-107">Selon la configuration de l'administration fiscale associée, l'impôt à payer est validé soit dans un fournisseur soit dans un compte général.</span><span class="sxs-lookup"><span data-stu-id="eb973-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="eb973-108">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="eb973-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="eb973-109">Accédez à Taxes > Taxes indirectes >Taxe > Périodes de règlement fiscal.</span><span class="sxs-lookup"><span data-stu-id="eb973-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="eb973-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="eb973-110">Click New.</span></span>
3. <span data-ttu-id="eb973-111">Tapez une valeur dans le champ Période de règlement.</span><span class="sxs-lookup"><span data-stu-id="eb973-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="eb973-112">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="eb973-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="eb973-113">Dans le champ Administration, sélectionnez l'administration fiscale qui reçoit les états et les règlements créés pour la période de règlement.</span><span class="sxs-lookup"><span data-stu-id="eb973-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="eb973-114">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="eb973-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="eb973-115">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="eb973-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="eb973-116">Dans le champ Conditions de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="eb973-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="eb973-117">L'administration fiscale associée peut être paramétrée comme fournisseur et le règlement fiscal va créer une facture fournisseur en cours.</span><span class="sxs-lookup"><span data-stu-id="eb973-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="eb973-118">Les conditions de paiement définissent la date d'échéance pour la facture fournisseur en cours.</span><span class="sxs-lookup"><span data-stu-id="eb973-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="eb973-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="eb973-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="eb973-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="eb973-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="eb973-121">Sélectionnez un type pour les intervalles des périodes de règlement.</span><span class="sxs-lookup"><span data-stu-id="eb973-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="eb973-122">Entrez le nombre d'unités de l'intervalle par période.</span><span class="sxs-lookup"><span data-stu-id="eb973-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="eb973-123">Un trimestre a 3 mois, par exemple.</span><span class="sxs-lookup"><span data-stu-id="eb973-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="eb973-124">Activez ou désactivez la case à cocher Utiliser le traitement par lots pour le règlement de la taxe.</span><span class="sxs-lookup"><span data-stu-id="eb973-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="eb973-125">Le processus de règlement pour la période de règlement peut être traité en tant que traitement par lots en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="eb973-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="eb973-126">Cette opération est recommandée pour un grand nombre de transactions de taxe dans un intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="eb973-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="eb973-127">Activez ou désactivez la case à cocher Empêcher la génération des transactions de taxe de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="eb973-127">Select or clear the Prevent generating offset tax transactions check box.</span></span>
    * <span data-ttu-id="eb973-128">Par défaut, le système génère des transactions de taxe de contrepartie au cours de le processus de règlement, ce qui peut entraîner des problèmes de performances s'il existe un grand nombre de transactions de taxe au sein d'un intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="eb973-128">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="eb973-129">Activez cette case à cocher pour empêcher la génération des transactions de taxe de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="eb973-129">Select this check box to prevent generating offset tax transactions.</span></span>
15. <span data-ttu-id="eb973-130">Développez l'onglet Intervalles de périodes.</span><span class="sxs-lookup"><span data-stu-id="eb973-130">Expand the Period intervals tab.</span></span>
16. <span data-ttu-id="eb973-131">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="eb973-131">Click Add.</span></span>
17. <span data-ttu-id="eb973-132">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="eb973-132">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="eb973-133">Entrez une date dans le champ Date de début.</span><span class="sxs-lookup"><span data-stu-id="eb973-133">In the From date field, enter a date.</span></span>
19. <span data-ttu-id="eb973-134">Entrez une date dans le champ Date de fin.</span><span class="sxs-lookup"><span data-stu-id="eb973-134">In the To date field, enter a date.</span></span>
20. <span data-ttu-id="eb973-135">Cliquez sur Nouvel intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="eb973-135">Click New period interval.</span></span>
    * <span data-ttu-id="eb973-136">Une fois que le premier intervalle de périodes a été entré, de nouvelles périodes peuvent être créées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="eb973-136">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="eb973-137">Si nécessaire, vous pouvez revenir et ajouter de nouveaux intervalles de périodes.</span><span class="sxs-lookup"><span data-stu-id="eb973-137">You can come back and add new period intervals as required.</span></span>  
21. <span data-ttu-id="eb973-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="eb973-138">Close the page.</span></span>

