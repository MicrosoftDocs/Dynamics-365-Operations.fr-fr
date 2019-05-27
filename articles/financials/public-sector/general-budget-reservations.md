---
title: Réservations budgétaires générales
description: Cette rubrique fournit des informations sur les réservations budgétaires générales pour le secteur public dans Microsoft Dynamics 365 for Finance and Operations.
author: AlexRenney
manager: AnnBe
ms.date: 04/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetReservation_PSN
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 03b2101902a8905cc5d9dd9d207c7c71cdfafb68
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1512931"
---
# <a name="general-budget-reservations"></a><span data-ttu-id="22216-103">Réservations budgétaires générales</span><span class="sxs-lookup"><span data-stu-id="22216-103">General budget reservations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22216-104">Une *réservation budgétaire générale* est un document qui est parfois également appelé un *engagement*.</span><span class="sxs-lookup"><span data-stu-id="22216-104">A *general budget reservation* is a document that is sometimes also referred to as a *commitment*.</span></span> <span data-ttu-id="22216-105">Les entités du secteur public utilisent souvent ce document pour répartir ou réserver des fonds budgétés afin qu'ils soient disponibles pour d'autres fins.</span><span class="sxs-lookup"><span data-stu-id="22216-105">Public sector entities often use this document to set aside or earmark budgeted funds so that they aren't available for other purposes.</span></span> <span data-ttu-id="22216-106">Généralement, ces réservations sont effectuées avant que des fournisseurs aient été sélectionnés pour l'achat.</span><span class="sxs-lookup"><span data-stu-id="22216-106">Typically, these reservations are made before any vendors have been selected for the purchase.</span></span> <span data-ttu-id="22216-107">En utilisant les réservations budgétaires générales, une organisation peut explicitement suivre les dépenses prévues à des fins de gestion et de génération d'états.</span><span class="sxs-lookup"><span data-stu-id="22216-107">By using general budget reservations, an organization can explicitly track planned expenditures for management and reporting purposes.</span></span> <span data-ttu-id="22216-108">Chaque demande d'achat, commande fournisseur ou facture fournisseur générée peut être associée à au moins une réservation budgétaire générale.</span><span class="sxs-lookup"><span data-stu-id="22216-108">Each purchase requisition, purchase order, or vendor invoice that is generated can be associated with at least one general budget reservation.</span></span>

<span data-ttu-id="22216-109">Les réservations budgétaires générales ne sont disponibles que si les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="22216-109">General budget reservations are available only if the following conditions are met:</span></span>

- <span data-ttu-id="22216-110">Vous avez Microsoft Dynamics 365 for Finance and Operations version 8.1 (octobre 2018) ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="22216-110">You have Microsoft Dynamics 365 for Finance and Operations version 8.1 (October 2018) or a later version.</span></span>
- <span data-ttu-id="22216-111">Les clés de configuration **Secteur public**, **Processus d'engagement** et **Processus d'engagement préalable** sont activées.</span><span class="sxs-lookup"><span data-stu-id="22216-111">The **Public sector**, **Encumbrance process**, and **Pre-encumbrance process** configuration keys are turned on.</span></span>
- <span data-ttu-id="22216-112">Vous utilisez des définitions de validation.</span><span class="sxs-lookup"><span data-stu-id="22216-112">You're using posting definitions.</span></span> <span data-ttu-id="22216-113">(Toutefois, vous n'avez pas besoin d'utiliser des définitions de validation si vous n'activez pas la comptabilité d'engagements.)</span><span class="sxs-lookup"><span data-stu-id="22216-113">(However, you don't have to use posting definitions if you don't activate commitment accounting.)</span></span>
- <span data-ttu-id="22216-114">La configuration du contrôle budgétaire est activée et configurée, et le contrôle budgétaire est activé.</span><span class="sxs-lookup"><span data-stu-id="22216-114">The Budget control configuration is activated and configured, and budget control is turned on.</span></span>

<span data-ttu-id="22216-115">Les réservations budgétaires générales contiennent des lignes qui fournissent des détails sur l'objectif de la réservation et les fonds réservés prévus.</span><span class="sxs-lookup"><span data-stu-id="22216-115">General budget reservations contain lines that provide details about the purpose of the reservation and the planned reserved funds.</span></span> <span data-ttu-id="22216-116">Ces détails incluent les dates de début et de fin de la réservation.</span><span class="sxs-lookup"><span data-stu-id="22216-116">These details include the start and end dates for the reservation.</span></span> <span data-ttu-id="22216-117">Il est possible d'ajouter, de modifier et de supprimer des lignes.</span><span class="sxs-lookup"><span data-stu-id="22216-117">You can add, change, and delete lines.</span></span> <span data-ttu-id="22216-118">Vous pouvez également spécifier plusieurs détails, tels que l'article demandé, la devise, le prix unitaire, la quantité et le montant total.</span><span class="sxs-lookup"><span data-stu-id="22216-118">You can also specify various details, such as the item that is requested, the currency, the unit price and quantity, and the total amount.</span></span> <span data-ttu-id="22216-119">Les réservations budgétaires générales sont conçues pour être utilisées par les entités du secteur public.</span><span class="sxs-lookup"><span data-stu-id="22216-119">General budget reservations are intended to be used by public sector entities.</span></span>

<span data-ttu-id="22216-120">Les entités du secteur privé utilisent l'expression *réservation budgétaire* pour parler d'engagements ou d'engagements préalables.</span><span class="sxs-lookup"><span data-stu-id="22216-120">Private sector entities use the term *budget reservation* to talk about encumbrances or pre-encumbrances.</span></span> <span data-ttu-id="22216-121">Toutefois, contrairement aux réservations budgétaires générales, ces réservations budgétaires ne sont pas des documents.</span><span class="sxs-lookup"><span data-stu-id="22216-121">However, unlike general budget reservations, those budgets reservations aren't documents.</span></span>

<span data-ttu-id="22216-122">Vous pouvez créer différents types de réservation budgétaire générale pour spécifier plusieurs caractéristiques et exigences, selon vos besoins d'achat.</span><span class="sxs-lookup"><span data-stu-id="22216-122">You can create different types of general budget reservation to specify various characteristics and requirements, based on your purchasing needs.</span></span> <span data-ttu-id="22216-123">Les caractéristiques incluent le workflow utilisé pour la réservation, et les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="22216-123">The characteristics include the workflow that is used for the reservation, and default values.</span></span> <span data-ttu-id="22216-124">Par exemple, vous pouvez créer trois types de réservations.</span><span class="sxs-lookup"><span data-stu-id="22216-124">For example, you create three reservation types.</span></span> <span data-ttu-id="22216-125">Vous utilisez un type pour les demandes d'achat, un autre type pour les commandes fournisseur, et encore un autre type pour les factures fournisseur.</span><span class="sxs-lookup"><span data-stu-id="22216-125">You use one type for purchase requisitions, another type for purchase orders, and another type for vendor invoices.</span></span>

<span data-ttu-id="22216-126">Dans la réservation budgétaire générale, vous pouvez également afficher les répartitions comptables et les lignes du journal de comptabilité auxiliaire pour la transaction.</span><span class="sxs-lookup"><span data-stu-id="22216-126">In the general budget reservation, you can also view accounting distributions and subledger journal lines for the transaction.</span></span>

<span data-ttu-id="22216-127">Si vous utilisez la comptabilité de projet, vous pouvez activer le suivi des coûts engagés pour les réservations budgétaires générales.</span><span class="sxs-lookup"><span data-stu-id="22216-127">If you use project accounting, you can turn on tracking of committed costs for general budget reservations.</span></span>

<span data-ttu-id="22216-128">Vous pouvez reporter les réservations budgétaires générales d'un exercice au suivant.</span><span class="sxs-lookup"><span data-stu-id="22216-128">You can carry over general budget reservations from one fiscal year to the next.</span></span> <span data-ttu-id="22216-129">Vous pouvez également clôturer ou finaliser une réservation budgétaire générale terminée ou expirée à la fin de l'exercice.</span><span class="sxs-lookup"><span data-stu-id="22216-129">You can also close or finalize a completed or expired general budget reservation at the end of the year.</span></span>

<span data-ttu-id="22216-130">Une réservation budgétaire générale est exonérée différemment, en fonction du document qui la référence :</span><span class="sxs-lookup"><span data-stu-id="22216-130">A general budget reservation is relieved differently, depending on the document that references it:</span></span>

- <span data-ttu-id="22216-131">Si le document est une commande fournisseur, la réservation est exonérée lorsque la commande fournisseur est *confirmée*.</span><span class="sxs-lookup"><span data-stu-id="22216-131">If the document is a purchase order, the reservation is relieved when the purchase order is *confirmed*.</span></span>
- <span data-ttu-id="22216-132">Si le document est une facture et qu'il ne référence pas une commande fournisseur ou un contrat d'achat, la réservation budgétaire générale est exonérée lorsque la facture est *validée*.</span><span class="sxs-lookup"><span data-stu-id="22216-132">If the document is an invoice, and it doesn't reference a purchase order or purchase agreement, the general budget reservation is relieved when the invoice is *posted*.</span></span>
- <span data-ttu-id="22216-133">Si le document est une demande d'achat, la réservation est exonérée lorsque la demande d'achat est *approuvée*.</span><span class="sxs-lookup"><span data-stu-id="22216-133">If the document is a purchase requisition, the reservation is relieved when the purchase requisition is *approved*.</span></span>
