---
title: Configurer les déductions
description: Utiliser les déductions dans Microsoft Dynamics 365 Human Resources pour déterminer combien, le cas échéant, déduire du salaire d’un employé pour chaque avantage.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4fac1624ce3a88b9fb4adcf303860e82f9d9165b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055554"
---
# <a name="configure-deductions"></a><span data-ttu-id="79fcf-103">Configurer les déductions</span><span class="sxs-lookup"><span data-stu-id="79fcf-103">Configure deductions</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="79fcf-104">Utiliser les déductions dans Microsoft Dynamics 365 Human Resources pour déterminer combien, le cas échéant, déduire du salaire d’un employé pour chaque avantage.</span><span class="sxs-lookup"><span data-stu-id="79fcf-104">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="79fcf-105">Les déductions sont effectives à une certaine date, vous pouvez donc conserver un historique des informations de déductions.</span><span class="sxs-lookup"><span data-stu-id="79fcf-105">Deductions are date-effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="79fcf-106">Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Déductions**.</span><span class="sxs-lookup"><span data-stu-id="79fcf-106">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="79fcf-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="79fcf-107">Select **New**.</span></span>

3. <span data-ttu-id="79fcf-108">Spécifiez les valeurs les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="79fcf-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="79fcf-109">Champ</span><span class="sxs-lookup"><span data-stu-id="79fcf-109">Field</span></span> | <span data-ttu-id="79fcf-110">Description</span><span class="sxs-lookup"><span data-stu-id="79fcf-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="79fcf-111">**Déduction**</span><span class="sxs-lookup"><span data-stu-id="79fcf-111">**Deduction**</span></span> | <span data-ttu-id="79fcf-112">Identifiant unique utilisé pour identifier la déduction des avantages.</span><span class="sxs-lookup"><span data-stu-id="79fcf-112">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="79fcf-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="79fcf-113">**Description**</span></span> | <span data-ttu-id="79fcf-114">Description de la déduction.</span><span class="sxs-lookup"><span data-stu-id="79fcf-114">A description for the deduction.</span></span> |
   | <span data-ttu-id="79fcf-115">**Date d’effet**</span><span class="sxs-lookup"><span data-stu-id="79fcf-115">**Effective**</span></span> | <span data-ttu-id="79fcf-116">Date de début.</span><span class="sxs-lookup"><span data-stu-id="79fcf-116">The start date.</span></span> <span data-ttu-id="79fcf-117">La date par défaut est la date système actuelle.</span><span class="sxs-lookup"><span data-stu-id="79fcf-117">The default value is the current system date.</span></span> |
   | <span data-ttu-id="79fcf-118">**Expiration**</span><span class="sxs-lookup"><span data-stu-id="79fcf-118">**Expiration**</span></span> | <span data-ttu-id="79fcf-119">Date de fin.</span><span class="sxs-lookup"><span data-stu-id="79fcf-119">The end date.</span></span> <span data-ttu-id="79fcf-120">La valeur par défaut est 12/31/2154, ce qui signifie jamais.</span><span class="sxs-lookup"><span data-stu-id="79fcf-120">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="79fcf-121">**En-tête**</span><span class="sxs-lookup"><span data-stu-id="79fcf-121">**Heading**</span></span> | <span data-ttu-id="79fcf-122">Code en-tête du système de paie que cette déduction utilisera pour la partie employé de la déduction lors du traitement des avantages dans la paie.</span><span class="sxs-lookup"><span data-stu-id="79fcf-122">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="79fcf-123">Ceci est utilisé lorsque vous utilisez un fournisseur de paie tiers.</span><span class="sxs-lookup"><span data-stu-id="79fcf-123">This is used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="79fcf-124">**Référence de déduction des salaires de l’employé**</span><span class="sxs-lookup"><span data-stu-id="79fcf-124">**Employee payroll deduction reference**</span></span> | <span data-ttu-id="79fcf-125">Le code de déduction du système de paie qu’utilisera cette déduction pour la partie employé de la déduction lors du traitement des avantages dans la paie.</span><span class="sxs-lookup"><span data-stu-id="79fcf-125">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="79fcf-126">**En-tête du montant**</span><span class="sxs-lookup"><span data-stu-id="79fcf-126">**Amount heading**</span></span> | <span data-ttu-id="79fcf-127">Code en-tête du système de paie que ce montant de déduction utilisera pour la partie employé de la déduction lors du traitement des avantages dans la paie.</span><span class="sxs-lookup"><span data-stu-id="79fcf-127">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="79fcf-128">Ceci est normalement utilisé lorsque vous utilisez un fournisseur de paie tiers.</span><span class="sxs-lookup"><span data-stu-id="79fcf-128">This is normally used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="79fcf-129">**Suppression possible**</span><span class="sxs-lookup"><span data-stu-id="79fcf-129">**Can delete**</span></span> | <span data-ttu-id="79fcf-130">Spécifie si une valeur exportée de Dynamics 365 for Finance and Operations peut entraîner la suppression de la valeur dans le système de paie.</span><span class="sxs-lookup"><span data-stu-id="79fcf-130">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="79fcf-131">**Colonnes associées**</span><span class="sxs-lookup"><span data-stu-id="79fcf-131">**Paired columns**</span></span> | <span data-ttu-id="79fcf-132">Spécifie s’il faut exporter l’en-tête et le montant des déductions dans les colonnes adjacentes associées vers le système de paie.</span><span class="sxs-lookup"><span data-stu-id="79fcf-132">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="79fcf-133">**Modifier la date d’effet**</span><span class="sxs-lookup"><span data-stu-id="79fcf-133">**Change effective date**</span></span> | <span data-ttu-id="79fcf-134">Date à laquelle le changement de déduction des avantages prendra effet.</span><span class="sxs-lookup"><span data-stu-id="79fcf-134">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="79fcf-135">À cette date, le système modifiera automatiquement la déduction de l’avantage et mettra à jour tous les plans d’avantage associés à cette déduction, tant que vous exécutez le traitement de **Mise à jour du changement de déduction**.</span><span class="sxs-lookup"><span data-stu-id="79fcf-135">On this date, the system automatically changes the benefit deduction and updates all benefit plans associated with this deduction, as long as you run **Deduction change update** processing.</span></span> |
   | <span data-ttu-id="79fcf-136">**Modification de la déduction terminée**</span><span class="sxs-lookup"><span data-stu-id="79fcf-136">**Deduction change completed**</span></span> | <span data-ttu-id="79fcf-137">La case à cocher **Modification de la déduction terminé** sera automatiquement cochée une fois que les modifications de déduction d’avantage auront été effectuées par le traitement de mise à jour de la modification de déduction.</span><span class="sxs-lookup"><span data-stu-id="79fcf-137">The **Deduction change completed** check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="79fcf-138">Pour effectuer le suivi et conserver les modifications apportées à la configuration du taux des avantages, sélectionnez **Actions**, puis sélectionnez **Tenir les versions à jour**.</span><span class="sxs-lookup"><span data-stu-id="79fcf-138">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="79fcf-139">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="79fcf-139">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]