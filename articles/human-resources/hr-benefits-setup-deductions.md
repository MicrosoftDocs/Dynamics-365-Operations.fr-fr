---
title: Configuration des déductions
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7ee9e8f3bc0e9027e41d3aa91bd097a3f046cbb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009036"
---
# <a name="configure-deductions"></a><span data-ttu-id="2b644-102">Configuration des déductions</span><span class="sxs-lookup"><span data-stu-id="2b644-102">Configure deductions</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="2b644-103">Utiliser les déductions dans Microsoft Dynamics 365 Human Resources pour déterminer combien, le cas échéant, déduire du salaire d'un employé pour chaque avantage.</span><span class="sxs-lookup"><span data-stu-id="2b644-103">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="2b644-104">Les déductions sont effectives à une certaine date, vous pouvez donc conserver un historique des informations de déductions.</span><span class="sxs-lookup"><span data-stu-id="2b644-104">Deductions are date effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="2b644-105">Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Déductions**.</span><span class="sxs-lookup"><span data-stu-id="2b644-105">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="2b644-106">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2b644-106">Select **New**.</span></span>

3. <span data-ttu-id="2b644-107">Spécifiez les valeurs les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="2b644-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="2b644-108">Champ</span><span class="sxs-lookup"><span data-stu-id="2b644-108">Field</span></span> | <span data-ttu-id="2b644-109">Description</span><span class="sxs-lookup"><span data-stu-id="2b644-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="2b644-110">Déduction</span><span class="sxs-lookup"><span data-stu-id="2b644-110">Deduction</span></span> | <span data-ttu-id="2b644-111">Identifiant unique utilisé pour identifier la déduction des avantages.</span><span class="sxs-lookup"><span data-stu-id="2b644-111">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="2b644-112">Description</span><span class="sxs-lookup"><span data-stu-id="2b644-112">Description</span></span> | <span data-ttu-id="2b644-113">Description de la déduction.</span><span class="sxs-lookup"><span data-stu-id="2b644-113">A description for the deduction.</span></span> |
   | <span data-ttu-id="2b644-114">Date d'effet</span><span class="sxs-lookup"><span data-stu-id="2b644-114">Effective</span></span> | <span data-ttu-id="2b644-115">Date de début.</span><span class="sxs-lookup"><span data-stu-id="2b644-115">The start date.</span></span> <span data-ttu-id="2b644-116">La date par défaut est la date système actuelle.</span><span class="sxs-lookup"><span data-stu-id="2b644-116">The default value is the current system date.</span></span> |
   | <span data-ttu-id="2b644-117">Expiration</span><span class="sxs-lookup"><span data-stu-id="2b644-117">Expiration</span></span> | <span data-ttu-id="2b644-118">Date de fin.</span><span class="sxs-lookup"><span data-stu-id="2b644-118">The end date.</span></span> <span data-ttu-id="2b644-119">La valeur par défaut est 12/31/2154, ce qui signifie jamais.</span><span class="sxs-lookup"><span data-stu-id="2b644-119">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="2b644-120">En-tête</span><span class="sxs-lookup"><span data-stu-id="2b644-120">Heading</span></span> | <span data-ttu-id="2b644-121">Code en-tête du système de paie que cette déduction utilisera pour la partie employé de la déduction lors du traitement des avantages dans la paie.</span><span class="sxs-lookup"><span data-stu-id="2b644-121">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="2b644-122">Ceci est utilisé lorsque vous utilisez un fournisseur de paie tiers.</span><span class="sxs-lookup"><span data-stu-id="2b644-122">This is used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="2b644-123">Référence de déduction des salaires de l'employé</span><span class="sxs-lookup"><span data-stu-id="2b644-123">Employee payroll deduction reference</span></span> | <span data-ttu-id="2b644-124">Le code de déduction du système de paie qu'utilisera cette déduction pour la partie employé de la déduction lors du traitement des avantages dans la paie.</span><span class="sxs-lookup"><span data-stu-id="2b644-124">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="2b644-125">En-tête du montant</span><span class="sxs-lookup"><span data-stu-id="2b644-125">Amount heading</span></span> | <span data-ttu-id="2b644-126">Code en-tête du système de paie que ce montant de déduction utilisera pour la partie employé de la déduction lors du traitement des avantages dans la paie.</span><span class="sxs-lookup"><span data-stu-id="2b644-126">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="2b644-127">Ceci est normalement utilisé lorsque vous utilisez un fournisseur de paie tiers.</span><span class="sxs-lookup"><span data-stu-id="2b644-127">This is normally used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="2b644-128">Suppression possible</span><span class="sxs-lookup"><span data-stu-id="2b644-128">Can delete</span></span> | <span data-ttu-id="2b644-129">Spécifie si une valeur exportée de Dynamics 365 for Finance and Operations peut entraîner la suppression de la valeur dans le système de paie.</span><span class="sxs-lookup"><span data-stu-id="2b644-129">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="2b644-130">Colonnes associées</span><span class="sxs-lookup"><span data-stu-id="2b644-130">Paired columns</span></span> | <span data-ttu-id="2b644-131">Spécifie s'il faut exporter l'en-tête et le montant des déductions dans les colonnes adjacentes associées vers le système de paie.</span><span class="sxs-lookup"><span data-stu-id="2b644-131">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="2b644-132">Modifier la date d'effet</span><span class="sxs-lookup"><span data-stu-id="2b644-132">Change effective date</span></span> | <span data-ttu-id="2b644-133">Date à laquelle le changement de déduction des avantages prendra effet.</span><span class="sxs-lookup"><span data-stu-id="2b644-133">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="2b644-134">À cette date, le système modifiera automatiquement la déduction de l'avantage et mettra à jour tous les plans d'avantage associés à cette déduction, tant que vous exécutez le traitement de mise à jour du changement de déduction.</span><span class="sxs-lookup"><span data-stu-id="2b644-134">On this date the system will automatically change the benefit deduction and update all benefit plans associated with this deduction, as long as you run Deduction change update processing.</span></span> |
   | <span data-ttu-id="2b644-135">Modification de la déduction terminée</span><span class="sxs-lookup"><span data-stu-id="2b644-135">Deduction change completed</span></span> | <span data-ttu-id="2b644-136">La case à cocher Modification de la déduction terminée sera automatiquement cochée une fois que les modifications de déduction d'avantage auront été effectuées par le traitement de mise à jour de la modification de déduction.</span><span class="sxs-lookup"><span data-stu-id="2b644-136">The Deduction change completed check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="2b644-137">Pour effectuer le suivi et conserver les modifications apportées à la configuration du taux des avantages, sélectionnez **Actions**, puis sélectionnez **Tenir les versions à jour**.</span><span class="sxs-lookup"><span data-stu-id="2b644-137">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="2b644-138">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2b644-138">Select **Save**.</span></span> 
