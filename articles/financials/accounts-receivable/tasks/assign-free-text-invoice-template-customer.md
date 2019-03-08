---
title: Affecter un modèle de facture financière à un client
description: Cette tâche montre comment affecter un modèle de facture financière à un client.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 317b3bd4c1f395987ef3dbbd268c40be5c688320
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "318923"
---
# <a name="assign-free-text-invoice-template-to-a-customer"></a><span data-ttu-id="cb733-103">Affecter un modèle de facture financière à un client</span><span class="sxs-lookup"><span data-stu-id="cb733-103">Assign free text invoice template to a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cb733-104">Cette tâche montre comment affecter un modèle de facture financière à un client.</span><span class="sxs-lookup"><span data-stu-id="cb733-104">This task demonstrates how to assign a free text invoice template to a customer.</span></span> <span data-ttu-id="cb733-105">La société fictive USMF est citée en exemple dans cette tâche qui est destinée à l'utilisateur chargé de gérer et de traiter des factures de comptes clients.</span><span class="sxs-lookup"><span data-stu-id="cb733-105">This task uses the USMF demo company and is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="cb733-106">Accédez à Comptabilité client > Clients > Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="cb733-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="cb733-107">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="cb733-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="cb733-108">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="cb733-108">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="cb733-109">Cliquez sur Factures récurrentes.</span><span class="sxs-lookup"><span data-stu-id="cb733-109">Click Recurring invoices.</span></span>
    * <span data-ttu-id="cb733-110">Cet écran permet d'affecter des modèles de facture financière à des clients et de spécifier la fréquence de l'envoi des factures au client.</span><span class="sxs-lookup"><span data-stu-id="cb733-110">Use this page to assign free text invoice templates to customers and specify how frequently invoices will be sent to the customer.</span></span>  
5. <span data-ttu-id="cb733-111">Cliquez sur Nouveau pour affecter un nouveau modèle au client.</span><span class="sxs-lookup"><span data-stu-id="cb733-111">Click New to assign a new template to the customer.</span></span>
6. <span data-ttu-id="cb733-112">Sélectionnez le modèle de facture financière à affecter au client.</span><span class="sxs-lookup"><span data-stu-id="cb733-112">Select the free text invoice template you want to assign to the customer.</span></span>
7. <span data-ttu-id="cb733-113">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="cb733-113">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="cb733-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cb733-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="cb733-115">Permet d'entrer la date de génération de la première facture.</span><span class="sxs-lookup"><span data-stu-id="cb733-115">Enter the date when the first invoice will be generated.</span></span>
    * <span data-ttu-id="cb733-116">Entrez une date de fin récurrente.</span><span class="sxs-lookup"><span data-stu-id="cb733-116">Enter a recurring end date.</span></span>  
    * <span data-ttu-id="cb733-117">Sélectionnez l'une des options suivantes : Pas de date de fin pour ne pas générer les factures avant que le modèle soit supprimé du compte client.</span><span class="sxs-lookup"><span data-stu-id="cb733-117">Select one of the following: No end date – Invoices will be generated indefinitely until the template is removed from the customer account.</span></span>  <span data-ttu-id="cb733-118">Date de fin de facturation : Sélectionnez cette option pour entrer la dernière date à laquelle la facture peut être générée.</span><span class="sxs-lookup"><span data-stu-id="cb733-118">Billing end date – Select this option and enter the last date that the invoice can be generated.</span></span>  
    * <span data-ttu-id="cb733-119">Montant cumulatif maximal après lequel la génération de factures s'arrêtera.</span><span class="sxs-lookup"><span data-stu-id="cb733-119">Maximum cumulative amount after which invoice generation will stop.</span></span>  
    * <span data-ttu-id="cb733-120">Permet d'entrer le montant cumulatif maximal pouvant être atteint à l'aide du modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="cb733-120">Enter the maximum cumulative amount that can be reached using the selected template.</span></span> <span data-ttu-id="cb733-121">Par exemple, si vous entrez 1 000,00 et que vous générez des factures mensuelles de 100,00, la génération de factures s'arrêtera après la dixième facture.</span><span class="sxs-lookup"><span data-stu-id="cb733-121">For example, if you enter 1,000.00 and generate monthly invoices for 100.00 each, invoices will stop generating after the tenth invoice is generated.</span></span>  
    * <span data-ttu-id="cb733-122">Générez des factures récurrentes à l'aide des valeurs par défaut provenant du modèle de facture financière ou du compte client.</span><span class="sxs-lookup"><span data-stu-id="cb733-122">Generate recurring invoices by using the default values from either free text invoice template or the customer account.</span></span>  
    * <span data-ttu-id="cb733-123">Permet d'indiquer si vous souhaitez utiliser le modèle de facture financière ou le compte client pour déterminer les valeurs par défaut pour la langue, le profil de validation, le groupe de taxe, le groupe de taxe d’article, le code liste, le pays/la région de la livraison, la devise, les conditions de paiement, le mode de paiement, la spécification de paiement, l'échéancier de paiement, l'escompte de règlement, les dimensions financières et le bordereau de transfert d'argent du virement lorsque des factures sont créées.</span><span class="sxs-lookup"><span data-stu-id="cb733-123">Select whether to use the free text invoice template or the customer account to determine the default values for the language, posting profile, sales tax group, item sales tax group, list code, country/region for delivery, currency, terms of payment, method of payment, payment specification, payment schedule, cash discount, financial dimensions, and giro money transfer slip when invoices are created.</span></span>  
10. <span data-ttu-id="cb733-124">Permet de sélectionner le modèle de répétition.</span><span class="sxs-lookup"><span data-stu-id="cb733-124">Select the recurrence pattern.</span></span>
    * <span data-ttu-id="cb733-125">Opérations diverses : Sélectionnez cette option et entrez le nombre de jours dans le champ Par.</span><span class="sxs-lookup"><span data-stu-id="cb733-125">Daily – Select this option and enter the number of days in the Per field.</span></span> <span data-ttu-id="cb733-126">Par exemple, si vous entrez 15, une facture est générée tous les 15 jours pour ce client.</span><span class="sxs-lookup"><span data-stu-id="cb733-126">For example, if you enter 15, an invoice will be generated every 15 days for this customer.</span></span>  <span data-ttu-id="cb733-127">Hebdomadaire : Sélectionnez cette option et entrez le nombre de semaines dans le champ Par.</span><span class="sxs-lookup"><span data-stu-id="cb733-127">Weekly - Select this option and enter the number of weeks in the Per field.</span></span> <span data-ttu-id="cb733-128">Par exemple, si vous entrez 2, une facture est générée toutes les 2 semaines pour ce client.</span><span class="sxs-lookup"><span data-stu-id="cb733-128">For example, if you enter 2, an invoice will be generated every two weeks for this customer.</span></span>  <span data-ttu-id="cb733-129">Mensuel : Sélectionnez cette option et entrez le nombre de mois dans le champ Par.</span><span class="sxs-lookup"><span data-stu-id="cb733-129">Monthly - Select this option and enter the number of months in the Per field.</span></span> <span data-ttu-id="cb733-130">Par exemple, si vous entrez 6, une facture est générée tous les 6 mois pour ce client.</span><span class="sxs-lookup"><span data-stu-id="cb733-130">For example, if you enter 6, an invoice will be generated every six months for this customer.</span></span>  <span data-ttu-id="cb733-131">Annuel : Sélectionnez cette option et entrez le nombre d'années dans le champ Par.</span><span class="sxs-lookup"><span data-stu-id="cb733-131">Yearly – Select this option and enter the number of years in the Per field.</span></span> <span data-ttu-id="cb733-132">Par exemple, si vous entrez 2, une facture est générée tous les 2 ans pour ce client.</span><span class="sxs-lookup"><span data-stu-id="cb733-132">For example, if you enter 2, an invoice will be generated every two years for this customer.</span></span>  
11. <span data-ttu-id="cb733-133">Entrez un numéro dans le champ Par.</span><span class="sxs-lookup"><span data-stu-id="cb733-133">In the Per field, enter a number.</span></span>

