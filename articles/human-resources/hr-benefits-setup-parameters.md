---
title: Configuration des paramètres de gestion des avantages
description: Configurez les paramètres de gestion des avantages dans Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3e001c08751ea9c8bcab0e11a04b6cf639e51d1d
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429983"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="745ca-103">Définir les paramètres de gestion des avantages</span><span class="sxs-lookup"><span data-stu-id="745ca-103">Set Benefits management parameters</span></span>

<span data-ttu-id="745ca-104">Avant de pouvoir configurer des plans de congés dans Microsoft Dynamics 365 Human Resources, vous devez configurer les paramètres de gestion des avantages.</span><span class="sxs-lookup"><span data-stu-id="745ca-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="745ca-105">Ces paramètres définissent les valeurs par défaut, les codes motif et d'autres options.</span><span class="sxs-lookup"><span data-stu-id="745ca-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="745ca-106">Configuration des paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="745ca-106">Configure general parameters</span></span>

1. <span data-ttu-id="745ca-107">Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="745ca-107">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="745ca-108">Dans l'onglet **Général**, spécifiez les valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="745ca-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="745ca-109">Champ</span><span class="sxs-lookup"><span data-stu-id="745ca-109">Field</span></span> | <span data-ttu-id="745ca-110">Description</span><span class="sxs-lookup"><span data-stu-id="745ca-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="745ca-111">**Pays/région**</span><span class="sxs-lookup"><span data-stu-id="745ca-111">**Country/region**</span></span> | <span data-ttu-id="745ca-112">Le champ **Pays/région** détermine l'ordre d'affichage des codes postaux/états.</span><span class="sxs-lookup"><span data-stu-id="745ca-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="745ca-113">Le pays sélectionné s'affiche en premier dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="745ca-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="745ca-114">**Code motif de l'inscription**</span><span class="sxs-lookup"><span data-stu-id="745ca-114">**Enrollment reason code**</span></span> | <span data-ttu-id="745ca-115">Sélectionnez un code motif par défaut à utiliser lors de la création des plans d'employé pendant le traitement de l'inscription ouverte.</span><span class="sxs-lookup"><span data-stu-id="745ca-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="745ca-116">**Code motif de l'annulation**</span><span class="sxs-lookup"><span data-stu-id="745ca-116">**Cancellation reason code**</span></span> | <span data-ttu-id="745ca-117">Code motif à utiliser lorsqu'un plan d'avantages des employés est annulé.</span><span class="sxs-lookup"><span data-stu-id="745ca-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="745ca-118">Il s'affiche dans une boîte de dialogue pendant le processus d'annulation.</span><span class="sxs-lookup"><span data-stu-id="745ca-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="745ca-119">Les utilisateurs peuvent modifier le **Code du motif de l'annulation** si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="745ca-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="745ca-120">**Rouvrir le code motif**</span><span class="sxs-lookup"><span data-stu-id="745ca-120">**Reopen reason code**</span></span> | <span data-ttu-id="745ca-121">Code motif à utiliser lorsqu'un plan d'avantages des employés est rouvert.</span><span class="sxs-lookup"><span data-stu-id="745ca-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="745ca-122">Il s'affiche dans une boîte de dialogue pendant le processus d'annulation.</span><span class="sxs-lookup"><span data-stu-id="745ca-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="745ca-123">Les utilisateurs peuvent modifier le **Rouvrir le code motif** si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="745ca-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="745ca-124">**Code motif de l'événement de vie**</span><span class="sxs-lookup"><span data-stu-id="745ca-124">**Life event reason code**</span></span> | <span data-ttu-id="745ca-125">Code motif à utiliser si un événement de vie se produit.</span><span class="sxs-lookup"><span data-stu-id="745ca-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="745ca-126">**Modifier le taux du code motif**</span><span class="sxs-lookup"><span data-stu-id="745ca-126">**Rate change reason code**</span></span> | <span data-ttu-id="745ca-127">Code motif à utiliser lors de l'annulation et de la réouverture d'un plan d'avantages des employés pendant le processus de mise à jour du changement de taux.</span><span class="sxs-lookup"><span data-stu-id="745ca-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="745ca-128">Il indique quels enregistrements ont été modifiés par le processus de mise à jour du changement de taux.</span><span class="sxs-lookup"><span data-stu-id="745ca-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="745ca-129">**Nouvelle embauche admissible**</span><span class="sxs-lookup"><span data-stu-id="745ca-129">**New hire eligible**</span></span> | <span data-ttu-id="745ca-130">Spécifie si les nouvelles embauches sont admissibles.</span><span class="sxs-lookup"><span data-stu-id="745ca-130">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="745ca-131">**Période d'inscription du nouvel employé**</span><span class="sxs-lookup"><span data-stu-id="745ca-131">**New hire enrollment period**</span></span> | <span data-ttu-id="745ca-132">Période pendant laquelle la nouvelle inscription est autorisée.</span><span class="sxs-lookup"><span data-stu-id="745ca-132">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="745ca-133">**Remarque** : ce paramètre remplace toute nouvelle période d'inscription à l'embauche que vous avez définie dans la règle d'admissibilité du plan.</span><span class="sxs-lookup"><span data-stu-id="745ca-133">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> | 
   | <span data-ttu-id="745ca-134">**Événements de vie activés**</span><span class="sxs-lookup"><span data-stu-id="745ca-134">**Life events enabled**</span></span> | <span data-ttu-id="745ca-135">Active les événements de vie.</span><span class="sxs-lookup"><span data-stu-id="745ca-135">Enables life events.</span></span> |
   | <span data-ttu-id="745ca-136">**Masquer les écrans d'avantages existants**</span><span class="sxs-lookup"><span data-stu-id="745ca-136">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="745ca-137">Vous permet de masquer les anciens écrans d'avantages.</span><span class="sxs-lookup"><span data-stu-id="745ca-137">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="745ca-138">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="745ca-138">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="745ca-139">Configurer les paramètres du libre-service employé.</span><span class="sxs-lookup"><span data-stu-id="745ca-139">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="745ca-140">Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="745ca-140">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="745ca-141">Dans l'onglet **Libre-service employé**, spécifiez les valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="745ca-141">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="745ca-142">Champ</span><span class="sxs-lookup"><span data-stu-id="745ca-142">Field</span></span> | <span data-ttu-id="745ca-143">Description</span><span class="sxs-lookup"><span data-stu-id="745ca-143">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="745ca-144">**Vérification de l'avantage**</span><span class="sxs-lookup"><span data-stu-id="745ca-144">**Benefit verification**</span></span> | <span data-ttu-id="745ca-145">Texte de vérification à utiliser lors du paiement des avantages en libre-service.</span><span class="sxs-lookup"><span data-stu-id="745ca-145">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="745ca-146">**Sélectionner automatiquement les bénéficiaires**</span><span class="sxs-lookup"><span data-stu-id="745ca-146">**Auto select designees**</span></span> | <span data-ttu-id="745ca-147">Spécifie s'il faut sélectionner automatiquement les personnes à charge et les bénéficiaires en fonction de leur éligibilité aux options du plan.</span><span class="sxs-lookup"><span data-stu-id="745ca-147">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="745ca-148">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="745ca-148">Select **Save**.</span></span>
