---
title: "Paramétrer et traiter des factures récurrentes"
description: "Cet article explique comment paramétrer et traiter les factures récurrentes. Vous pouvez utiliser des factures récurrentes si vous devez facturer des clients pour le même montant régulièrement."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 96a9075294c1f2a9cfde03be1aaaa26af90de4c2
ms.openlocfilehash: ac9e836b0baa24c40554844ea4f3288b80e0c654
ms.contentlocale: fr-fr
ms.lasthandoff: 09/04/2018

---

# <a name="set-up-and-process-recurring-invoices"></a><span data-ttu-id="61d44-104">Paramétrer et traiter des factures récurrentes</span><span class="sxs-lookup"><span data-stu-id="61d44-104">Set up and process recurring invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61d44-105">Cet article explique comment paramétrer et traiter les factures récurrentes.</span><span class="sxs-lookup"><span data-stu-id="61d44-105">This article explains how to set up and process recurring invoices.</span></span> <span data-ttu-id="61d44-106">Vous pouvez utiliser des factures récurrentes si vous devez facturer des clients pour le même montant régulièrement.</span><span class="sxs-lookup"><span data-stu-id="61d44-106">You can use recurring invoices if you must invoice customers for the same amount on a regular basis.</span></span>

<a name="create-a-recurring-free-text-invoice-template"></a><span data-ttu-id="61d44-107">Création d'un modèle de facture financière récurrente</span><span class="sxs-lookup"><span data-stu-id="61d44-107">Create a recurring free text invoice template</span></span>
---------------------------------------------

<span data-ttu-id="61d44-108">Pour facturer régulièrement des clients pour les mêmes services, vous devez définir un modèle de facture financière pouvant être réutilisé pour créer les factures.</span><span class="sxs-lookup"><span data-stu-id="61d44-108">To invoice customers for the same services on a regular basis, you must define a free text invoice template that can be reused to create the invoices.</span></span> <span data-ttu-id="61d44-109">Ce modèle contient les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="61d44-109">This template contains the following information:</span></span>

-   <span data-ttu-id="61d44-110">Les informations d'en-tête, telles que les groupes de taxe, les conditions de paiement et le mode de paiement</span><span class="sxs-lookup"><span data-stu-id="61d44-110">Header information, such as tax groups, terms of payment, and the method of payment</span></span>
-   <span data-ttu-id="61d44-111">Les informations de ligne, telles que la description des services, les comptes de produit, le prix unitaire et le montant de la facture</span><span class="sxs-lookup"><span data-stu-id="61d44-111">Line information, such as the service description, revenue accounts, unit price, and invoice amount</span></span>
-   <span data-ttu-id="61d44-112">Les frais d'expédition ou de gestion</span><span class="sxs-lookup"><span data-stu-id="61d44-112">Charges for shipping or handling</span></span>
-   <span data-ttu-id="61d44-113">Les répartitions comptables avec les informations de dimension financière, par exemple les centres de coût et les unités commerciales</span><span class="sxs-lookup"><span data-stu-id="61d44-113">Accounting distributions together with financial dimension information, such as cost centers and business units</span></span>

<span data-ttu-id="61d44-114">En réalité, vous créez une facture entière et l'enregistrez comme modèle.</span><span class="sxs-lookup"><span data-stu-id="61d44-114">In effect, you're creating an entire invoice and saving it as a template.</span></span> <span data-ttu-id="61d44-115">Vous pouvez paramétrer les modèles à l'aide de la page **Factures récurrentes**.</span><span class="sxs-lookup"><span data-stu-id="61d44-115">You can set up the templates using the **Recurring invoices** page.</span></span>

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a><span data-ttu-id="61d44-116">Affectation d'un modèle de facture financière à un client et saisie des détails récurrents</span><span class="sxs-lookup"><span data-stu-id="61d44-116">Assign a free text invoice template to a customer and enter recurrence details</span></span>
<span data-ttu-id="61d44-117">Une fois le modèle créé, vous devez affecter le modèle aux clients à facturer.</span><span class="sxs-lookup"><span data-stu-id="61d44-117">After the template is created, you must assign the template to the customers that you want to invoice.</span></span> <span data-ttu-id="61d44-118">En outre, vous devez spécifier quand et la fréquence à laquelle la facture est utilisée.</span><span class="sxs-lookup"><span data-stu-id="61d44-118">Additionally, you must specify when and how often the invoice will be used.</span></span> <span data-ttu-id="61d44-119">Vous pouvez affecter des modèles dans l'onglet **Facture** de la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="61d44-119">You can assign the templates on the **Invoice** tab of the **Customers** page.</span></span> <span data-ttu-id="61d44-120">Ajoutez le modèle à la liste et mettez à jour les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="61d44-120">Add the template to the list, and update the following information:</span></span>

-   <span data-ttu-id="61d44-121">La date de début et, éventuellement, la date de fin de la facturation récurrente</span><span class="sxs-lookup"><span data-stu-id="61d44-121">The start date and, optionally, the end date for the recurring billing</span></span>
-   <span data-ttu-id="61d44-122">La fréquence de la facturation récurrente (par exemple, chaque jour ou une fois par mois)</span><span class="sxs-lookup"><span data-stu-id="61d44-122">The frequency of the recurring billing (for example, every day or once a month)</span></span>
-   <span data-ttu-id="61d44-123">Le montant maximal de facturation (si cette information est requise)</span><span class="sxs-lookup"><span data-stu-id="61d44-123">The maximum billing amount (if this information is required)</span></span>

<span data-ttu-id="61d44-124">Un client peut avoir plusieurs modèles qui ont différentes fréquences.</span><span class="sxs-lookup"><span data-stu-id="61d44-124">A customer can have multiple templates that have different frequencies.</span></span>

## <a name="generate-the-recurring-invoices"></a><span data-ttu-id="61d44-125">Générer les factures répétitives</span><span class="sxs-lookup"><span data-stu-id="61d44-125">Generate the recurring invoices</span></span>
<span data-ttu-id="61d44-126">Dans la page **Factures récurrentes**, il existe une tâche qui traite les modèles de factures récurrentes.</span><span class="sxs-lookup"><span data-stu-id="61d44-126">On the **Recurring invoices** page, there is a task that processes recurring invoice templates.</span></span> <span data-ttu-id="61d44-127">Vous spécifiez la date de facture et le modèle à partir duquel générer les factures.</span><span class="sxs-lookup"><span data-stu-id="61d44-127">You specify the invoice date and the template to generate the invoices from.</span></span> <span data-ttu-id="61d44-128">Les factures sont générées et un même numéro d'identification de récurrence est affecté pour chaque groupe de factures traité.</span><span class="sxs-lookup"><span data-stu-id="61d44-128">Invoices will be generated and assigned a single recurrence ID number for each group of invoices that is processed.</span></span>

<a name="post-recurring-free-text-invoices"></a><span data-ttu-id="61d44-129">Validation de factures financières récurrentes</span><span class="sxs-lookup"><span data-stu-id="61d44-129">Post recurring free text invoices</span></span>
---------------------------------

<span data-ttu-id="61d44-130">Une fois les factures récurrentes générées, les ID de récurrence de facture s'affichent dans une tâche de validation dans la page **Factures récurrentes**.</span><span class="sxs-lookup"><span data-stu-id="61d44-130">After recurring invoices are generated, the invoice recurrence IDs appear in a posting task on the **Recurring invoices** page.</span></span> <span data-ttu-id="61d44-131">Vous pouvez afficher toutes les factures pour un ID de récurrence en cliquant sur le lien.</span><span class="sxs-lookup"><span data-stu-id="61d44-131">You can view all of the invoices for a recurrence ID by clicking the link.</span></span> <span data-ttu-id="61d44-132">Lors de la révision des factures pour l'ID de récurrence, vous pouvez supprimer les factures individuelles.</span><span class="sxs-lookup"><span data-stu-id="61d44-132">During your review of the invoices for the recurrence ID, you can delete individual invoices.</span></span> <span data-ttu-id="61d44-133">Les paramètres de récurrence du client seront réinitialisés pour ce modèle, afin qu'il puisse être régénéré ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="61d44-133">The customer's recurrence settings will be reset for that template, so that it can be regenerated later.</span></span> <span data-ttu-id="61d44-134">Vous pouvez valider une, plusieurs ou toutes les factures pour un ID de récurrence.</span><span class="sxs-lookup"><span data-stu-id="61d44-134">You can post one, many, or all of the invoices for a recurrence ID.</span></span> <span data-ttu-id="61d44-135">Si des workflows sont activés, vous devez cliquer sur **Envoyer** avant de pouvoir valider les factures.</span><span class="sxs-lookup"><span data-stu-id="61d44-135">If workflows are enabled, you must click **Submit** before you can post the invoices.</span></span>

<a name="print-recurring-free-text-invoices"></a><span data-ttu-id="61d44-136">Impression de factures financières récurrentes</span><span class="sxs-lookup"><span data-stu-id="61d44-136">Print recurring free text invoices</span></span>
----------------------------------

<span data-ttu-id="61d44-137">Une fois les factures récurrentes validées, vous pouvez imprimer les factures à partir de la page de liste des factures financières.</span><span class="sxs-lookup"><span data-stu-id="61d44-137">After recurring invoices are posted, you can print the invoices from the free text invoice list page.</span></span> <span data-ttu-id="61d44-138">Vous pouvez imprimer les factures sélectionnées ou sélectionner une plage de factures à imprimer.</span><span class="sxs-lookup"><span data-stu-id="61d44-138">You can print the invoices that are selected, or you can select a range of invoices to print.</span></span>




