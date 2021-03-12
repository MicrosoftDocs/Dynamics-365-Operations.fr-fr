---
title: Paramétrer des périodes de règlement fiscal
description: Cette rubrique explique comment paramétrer les périodes de règlement fiscal dans Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8683f3b6e10efe6e975ae6bc3d7863f884bb9a0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994463"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="568f3-103">Paramétrer des périodes de règlement fiscal</span><span class="sxs-lookup"><span data-stu-id="568f3-103">Set up sales tax settlement periods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="568f3-104">Cette rubrique explique comment paramétrer les périodes de règlement fiscal.</span><span class="sxs-lookup"><span data-stu-id="568f3-104">This topic explains how to set up sales tax settlement periods.</span></span> <span data-ttu-id="568f3-105">Les périodes de règlement fiscal contiennent des informations sur l’intervalle pour lequel les taxes doivent être déclarées et payées.</span><span class="sxs-lookup"><span data-stu-id="568f3-105">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="568f3-106">Un processus de règlement peut être exécuté pour une période de règlement pour un intervalle de dates spécifique.</span><span class="sxs-lookup"><span data-stu-id="568f3-106">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="568f3-107">Tous les codes taxe associés à la période de règlement seront fixés.</span><span class="sxs-lookup"><span data-stu-id="568f3-107">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="568f3-108">Selon la configuration de l’administration fiscale associée, l’impôt à payer est validé soit dans un fournisseur soit dans un compte général.</span><span class="sxs-lookup"><span data-stu-id="568f3-108">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>

<span data-ttu-id="568f3-109">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="568f3-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="568f3-110">Dans le volet de navigation, accédez à **Modules > Taxes > Taxes indirectes > Taxe > Périodes de règlement fiscal**.</span><span class="sxs-lookup"><span data-stu-id="568f3-110">In the navigation pane, go to **Modules > Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.</span></span>
2. <span data-ttu-id="568f3-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="568f3-111">Select **New**.</span></span>
3. <span data-ttu-id="568f3-112">Dans le champ **Période de règlement**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="568f3-112">In the **Settlement period** field, type a value.</span></span>
4. <span data-ttu-id="568f3-113">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="568f3-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="568f3-114">Dans le champ **Administration**, sélectionnez l’administration fiscale qui reçoit les états et les règlements créés pour la période de règlement.</span><span class="sxs-lookup"><span data-stu-id="568f3-114">In the **Authority** field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="568f3-115">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="568f3-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="568f3-116">Dans le champ **Conditions de paiement**, sélectionnez l’enregistrement souhaité dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="568f3-116">In the **Terms of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="568f3-117">L’administration fiscale associée peut être paramétrée comme fournisseur et le règlement fiscal va créer une facture fournisseur en cours.</span><span class="sxs-lookup"><span data-stu-id="568f3-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="568f3-118">Les conditions de paiement définissent la date d’échéance pour la facture fournisseur en cours.</span><span class="sxs-lookup"><span data-stu-id="568f3-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
8. <span data-ttu-id="568f3-119">Sélectionnez un type pour les intervalles des périodes de règlement.</span><span class="sxs-lookup"><span data-stu-id="568f3-119">Select a type for the settlement period intervals.</span></span>
9. <span data-ttu-id="568f3-120">Entrez le nombre d’unités de l’intervalle par période.</span><span class="sxs-lookup"><span data-stu-id="568f3-120">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="568f3-121">Un trimestre a 3 mois, par exemple.</span><span class="sxs-lookup"><span data-stu-id="568f3-121">For example, a quarter has 3 months.</span></span>
10. <span data-ttu-id="568f3-122">Activez ou désactivez la case à cocher **Utiliser le traitement par lots pour le règlement de la taxe**.</span><span class="sxs-lookup"><span data-stu-id="568f3-122">Select or clear the **Use batch processing for sales tax settlement** check box.</span></span> <span data-ttu-id="568f3-123">Le processus de règlement pour la période de règlement peut être traité en tant que traitement par lots en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="568f3-123">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="568f3-124">Cette opération est recommandée pour un grand nombre de transactions de taxe dans un intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="568f3-124">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="568f3-125">Pour le moment, elle n’est pas prise en charge en Espagne, au Japon et aux Pays-Bas.</span><span class="sxs-lookup"><span data-stu-id="568f3-125">Currently this is not supported in Spain, Japan, and the Netherlands.</span></span>
11. <span data-ttu-id="568f3-126">Activez ou désactivez la case à cocher **Empêcher la génération des transactions de taxe de contrepartie**.</span><span class="sxs-lookup"><span data-stu-id="568f3-126">Select or clear the **Prevent generating offset tax transactions** check box.</span></span> <span data-ttu-id="568f3-127">Par défaut, le système génère des transactions de taxe de contrepartie au cours de le processus de règlement, ce qui peut entraîner des problèmes de performances s’il existe un grand nombre de transactions de taxe au sein d’un intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="568f3-127">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="568f3-128">Activez cette case à cocher pour empêcher la génération des transactions de taxe de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="568f3-128">Select this check box to prevent generating offset tax transactions.</span></span>
12. <span data-ttu-id="568f3-129">Développez l’onglet **Intervalles de périodes**.</span><span class="sxs-lookup"><span data-stu-id="568f3-129">Expand the **Period intervals** tab.</span></span>
13. <span data-ttu-id="568f3-130">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="568f3-130">Select **Add**.</span></span>
14. <span data-ttu-id="568f3-131">Dans le champ **Date de début** dans la nouvelle ligne, saisissez une date.</span><span class="sxs-lookup"><span data-stu-id="568f3-131">In the **From date** field in the new row, enter a date.</span></span>
15. <span data-ttu-id="568f3-132">Entrez une date dans le champ **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="568f3-132">In the **To date** field, enter a date.</span></span>
16. <span data-ttu-id="568f3-133">Sélectionnez **Nouvel intervalle de périodes**.</span><span class="sxs-lookup"><span data-stu-id="568f3-133">Select **New period interval**.</span></span> <span data-ttu-id="568f3-134">Une fois que le premier intervalle de périodes a été entré, de nouvelles périodes peuvent être créées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="568f3-134">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="568f3-135">Si nécessaire, vous pouvez revenir et ajouter de nouveaux intervalles de périodes.</span><span class="sxs-lookup"><span data-stu-id="568f3-135">You can come back and add new period intervals as required.</span></span>  
17. <span data-ttu-id="568f3-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="568f3-136">Close the page.</span></span>

