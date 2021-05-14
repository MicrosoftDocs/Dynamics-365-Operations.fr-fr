---
title: Paramétrer des périodes de règlement fiscal
description: Cette rubrique explique comment paramétrer les périodes de règlement fiscal dans Dynamics 365 Finance.
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83587df3963d215fec020150e6b707e431c1b6eb
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944775"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="1a3e0-103">Paramétrer des périodes de règlement fiscal</span><span class="sxs-lookup"><span data-stu-id="1a3e0-103">Set up sales tax settlement periods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1a3e0-104">Cette rubrique explique comment paramétrer les périodes de règlement fiscal.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-104">This topic explains how to set up sales tax settlement periods.</span></span> <span data-ttu-id="1a3e0-105">Les périodes de règlement fiscal contiennent des informations sur l’intervalle pour lequel les taxes doivent être déclarées et payées.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-105">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="1a3e0-106">Un processus de règlement peut être exécuté pour une période de règlement pour un intervalle de dates spécifique.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-106">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="1a3e0-107">Tous les codes taxe associés à la période de règlement seront fixés.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-107">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="1a3e0-108">Selon la configuration de l’administration fiscale associée, l’impôt à payer est validé soit dans un fournisseur soit dans un compte général.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-108">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>

<span data-ttu-id="1a3e0-109">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="1a3e0-110">Dans le volet de navigation, accédez à **Modules > Taxes > Taxes indirectes > Taxe > Périodes de règlement fiscal**.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-110">In the navigation pane, go to **Modules > Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.</span></span>
2. <span data-ttu-id="1a3e0-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-111">Select **New**.</span></span>
3. <span data-ttu-id="1a3e0-112">Dans le champ **Période de règlement**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-112">In the **Settlement period** field, type a value.</span></span>
4. <span data-ttu-id="1a3e0-113">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="1a3e0-114">Dans le champ **Administration**, sélectionnez l’administration fiscale qui reçoit les états et les règlements créés pour la période de règlement.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-114">In the **Authority** field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="1a3e0-115">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="1a3e0-116">Dans le champ **Conditions de paiement**, sélectionnez l’enregistrement souhaité dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-116">In the **Terms of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="1a3e0-117">L’administration fiscale associée peut être paramétrée comme fournisseur et le règlement fiscal va créer une facture fournisseur en cours.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="1a3e0-118">Les conditions de paiement définissent la date d’échéance pour la facture fournisseur en cours.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
8. <span data-ttu-id="1a3e0-119">Sélectionnez un type pour les intervalles des périodes de règlement.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-119">Select a type for the settlement period intervals.</span></span>
9. <span data-ttu-id="1a3e0-120">Entrez le nombre d’unités de l’intervalle par période.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-120">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="1a3e0-121">Un trimestre a 3 mois, par exemple.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-121">For example, a quarter has 3 months.</span></span>
10. <span data-ttu-id="1a3e0-122">Activez ou désactivez la case à cocher **Utiliser le traitement par lots pour le règlement de la taxe**.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-122">Select or clear the **Use batch processing for sales tax settlement** check box.</span></span> <span data-ttu-id="1a3e0-123">Le processus de règlement pour la période de règlement peut être traité en tant que traitement par lots en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-123">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="1a3e0-124">Cette opération est recommandée pour un grand nombre de transactions de taxe dans un intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-124">This is recommended for a large number of tax transactions within a period interval.</span></span>
11. <span data-ttu-id="1a3e0-125">Activez ou désactivez la case à cocher **Empêcher la génération des transactions de taxe de contrepartie**.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-125">Select or clear the **Prevent generating offset tax transactions** check box.</span></span> <span data-ttu-id="1a3e0-126">Par défaut, le système génère des transactions de taxe de contrepartie au cours de le processus de règlement, ce qui peut entraîner des problèmes de performances s’il existe un grand nombre de transactions de taxe au sein d’un intervalle de périodes.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-126">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="1a3e0-127">Activez cette case à cocher pour empêcher la génération des transactions de taxe de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-127">Select this check box to prevent generating offset tax transactions.</span></span>
12. <span data-ttu-id="1a3e0-128">Développez l’onglet **Intervalles de périodes**.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-128">Expand the **Period intervals** tab.</span></span>
13. <span data-ttu-id="1a3e0-129">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-129">Select **Add**.</span></span>
14. <span data-ttu-id="1a3e0-130">Dans le champ **Date de début** dans la nouvelle ligne, saisissez une date.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-130">In the **From date** field in the new row, enter a date.</span></span>
15. <span data-ttu-id="1a3e0-131">Entrez une date dans le champ **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-131">In the **To date** field, enter a date.</span></span>
16. <span data-ttu-id="1a3e0-132">Sélectionnez **Nouvel intervalle de périodes**.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-132">Select **New period interval**.</span></span> <span data-ttu-id="1a3e0-133">Une fois que le premier intervalle de périodes a été entré, de nouvelles périodes peuvent être créées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-133">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="1a3e0-134">Si nécessaire, vous pouvez revenir et ajouter de nouveaux intervalles de périodes.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-134">You can come back and add new period intervals as required.</span></span>  
17. <span data-ttu-id="1a3e0-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1a3e0-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
