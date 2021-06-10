---
title: Définir les paramètres de gestion des avantages et de libre service des employés pour toutes les entreprises
description: Configurer les paramètres de gestion des avantages et de libre service des employés dans Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
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
ms.openlocfilehash: d668238378e41287c7a9f845ae3e67078fc7776a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058966"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a><span data-ttu-id="0a4d1-103">Définir les paramètres de gestion des avantages et de libre service des employés pour toutes les entreprises</span><span class="sxs-lookup"><span data-stu-id="0a4d1-103">Set Benefits management and Employee self-service parameters for all companies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0a4d1-104">Avant de pouvoir configurer des plans d’avantages dans Microsoft Dynamics 365 Human Resources, vous devez configurer les paramètres de gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-104">Before you can set up benefit plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="0a4d1-105">Ces paramètres définissent les valeurs par défaut, les codes motif et d’autres options.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-105">These parameters set default values, reason codes, and other options.</span></span> 

## <a name="configure-general-parameters"></a><span data-ttu-id="0a4d1-106">Configuration des paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="0a4d1-106">Configure general parameters</span></span>

1. <span data-ttu-id="0a4d1-107">Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres partagés Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-107">In the **Benefits management** workspace, under **Setup**, select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="0a4d1-108">Dans l’onglet **Gestion des avantages**, spécifiez les valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="0a4d1-108">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="0a4d1-109">Champ</span><span class="sxs-lookup"><span data-stu-id="0a4d1-109">Field</span></span> | <span data-ttu-id="0a4d1-110">Description</span><span class="sxs-lookup"><span data-stu-id="0a4d1-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="0a4d1-111">**Pays/région**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-111">**Country/region**</span></span> | <span data-ttu-id="0a4d1-112">Le champ **Pays/région** détermine l’ordre d’affichage des codes postaux/états.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="0a4d1-113">Le pays sélectionné s’affiche en premier dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="0a4d1-114">**Code motif de l’inscription**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-114">**Enrollment reason code**</span></span> | <span data-ttu-id="0a4d1-115">Sélectionnez un code motif par défaut à utiliser lors de la création des plans d’employé pendant le traitement de l’inscription ouverte.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="0a4d1-116">**Code motif de l’annulation**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-116">**Cancellation reason code**</span></span> | <span data-ttu-id="0a4d1-117">Code motif à utiliser lorsqu’un régime de prestations des employés est annulé.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="0a4d1-118">Il s’affiche dans une boîte de dialogue pendant le processus d’annulation.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="0a4d1-119">Les utilisateurs peuvent modifier le **Code du motif de l’annulation** si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="0a4d1-120">**Rouvrir le code motif**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-120">**Reopen reason code**</span></span> | <span data-ttu-id="0a4d1-121">Code motif à utiliser lorsqu’un régime de prestations des employés est rouvert.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="0a4d1-122">Il s’affiche dans une boîte de dialogue pendant le processus d’annulation.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="0a4d1-123">Les utilisateurs peuvent modifier le **Rouvrir le code motif** si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="0a4d1-124">**Code motif de l’événement de vie**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-124">**Life event reason code**</span></span> | <span data-ttu-id="0a4d1-125">Code motif à utiliser si un événement de vie se produit.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="0a4d1-126">**Modifier le taux du code motif**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-126">**Rate change reason code**</span></span> | <span data-ttu-id="0a4d1-127">Code motif à utiliser lors de l’annulation et de la réouverture d’un régime de prestations des employés pendant le processus de mise à jour du changement de taux.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="0a4d1-128">Il indique quels enregistrements ont été modifiés par le processus de mise à jour du changement de taux.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="0a4d1-129">**Salaire annuel avec avantages**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-129">**Benefits annual salary**</span></span> | <span data-ttu-id="0a4d1-130">Cela vous permet de définir un montant de **Salaire annuel des avantages sociaux** pour un employé.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="0a4d1-131">Human Resources utilise le montant **Salaire annuel des avantages sociaux** lors de la détermination des montants de couverture, au lieu du montant annuel de la rémunération fixe.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-131">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="0a4d1-132">**Nouvelle embauche admissible**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-132">**New hire eligible**</span></span> | <span data-ttu-id="0a4d1-133">Spécifie si les nouvelles embauches sont admissibles.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="0a4d1-134">**Période d’inscription du nouvel employé**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-134">**New hire enrollment period**</span></span> | <span data-ttu-id="0a4d1-135">Période pendant laquelle la nouvelle inscription est autorisée.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="0a4d1-136">**Remarque** : ce paramètre remplace toute nouvelle période d’inscription à l’embauche que vous avez définie dans la règle d’admissibilité du plan.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-136">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="0a4d1-137">**Fréquence de paiement par défaut**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-137">**Default pay frequency**</span></span> | <span data-ttu-id="0a4d1-138">La fréquence de paie par défaut à utiliser lorsque de nouveaux employés sont ajoutés.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="0a4d1-139">**Événements de vie activés**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-139">**Life events enabled**</span></span> | <span data-ttu-id="0a4d1-140">Active les événements de vie.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-140">Enables life events.</span></span> |
   | <span data-ttu-id="0a4d1-141">**Masquer les écrans d’avantages existants**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="0a4d1-142">Vous permet de masquer les anciens écrans d’avantages.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-142">Allows you to hide legacy benefit forms.</span></span> |
   | <span data-ttu-id="0a4d1-143">**Vérification de l’avantage**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-143">**Benefit verification**</span></span> | <span data-ttu-id="0a4d1-144">Texte de vérification à utiliser lors du paiement des avantages en libre-service.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-144">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="0a4d1-145">**Sélectionner automatiquement les bénéficiaires**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-145">**Auto select designees**</span></span> | <span data-ttu-id="0a4d1-146">Spécifie s’il faut sélectionner automatiquement les personnes à charge et les bénéficiaires en fonction de leur éligibilité aux options du plan.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-146">Specifies whether to automatically select dependents and beneficiaries, based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="0a4d1-147">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-147">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="0a4d1-148">Configurer les paramètres du libre service employé</span><span class="sxs-lookup"><span data-stu-id="0a4d1-148">Configure Employee self-service parameters</span></span>

1. <span data-ttu-id="0a4d1-149">Dans l’espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-149">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="0a4d1-150">Dans l’onglet **Gestion des avantages**, spécifiez les valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="0a4d1-150">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="0a4d1-151">Champ</span><span class="sxs-lookup"><span data-stu-id="0a4d1-151">Field</span></span> | <span data-ttu-id="0a4d1-152">Description</span><span class="sxs-lookup"><span data-stu-id="0a4d1-152">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="0a4d1-153">**Vérification de l’avantage**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-153">**Benefit verification**</span></span> | <span data-ttu-id="0a4d1-154">Texte de vérification à utiliser lors du paiement des avantages en libre-service.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-154">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="0a4d1-155">**Sélectionner automatiquement les bénéficiaires**</span><span class="sxs-lookup"><span data-stu-id="0a4d1-155">**Auto select designees**</span></span> | <span data-ttu-id="0a4d1-156">Spécifie s’il faut sélectionner automatiquement les personnes à charge et les bénéficiaires en fonction de leur éligibilité aux options du plan.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-156">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="0a4d1-157">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0a4d1-157">Select **Save**.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]