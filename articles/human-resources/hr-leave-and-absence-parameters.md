---
title: Configuration des paramètres de congé et d’absence
description: Définissez les paramètres des ressources humaines pour les congés et les absences dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e1b2de94f9d9ac1ada16b6ef0e7628edbc9d683f
ms.sourcegitcommit: ffb5998e611b83c2e4f98323f39e3e8f6419c652
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2020
ms.locfileid: "4418591"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="1d3d2-103">Configuration des paramètres de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="1d3d2-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="1d3d2-104">Avant de configurer des plans de congé et d’absence dans Dynamics 365 Human Resources, il est judicieux de vérifier la configuration de tous les paramètres des ressources humaines associés, notamment :</span><span class="sxs-lookup"><span data-stu-id="1d3d2-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="1d3d2-105">Souche de numéros pour les demandes de congé</span><span class="sxs-lookup"><span data-stu-id="1d3d2-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="1d3d2-106">Paramètres relatifs au Family Medical and Leave Act (FMLA)</span><span class="sxs-lookup"><span data-stu-id="1d3d2-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="1d3d2-107">Paramètres en libre-service des employés pour les demandes de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="1d3d2-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="1d3d2-108">Paramètres de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="1d3d2-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="1d3d2-109">Afficher et modifier les paramètres des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="1d3d2-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="1d3d2-110">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="1d3d2-111">Sous **Configuration**, sélectionnez **Paramètres des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="1d3d2-112">Sur l’onglet **Souches de numéros**, vérifiez le **Code souche de N°** pour **ID de demande de congé** et changez si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="1d3d2-113">Ce paramètre détermine la souche utilisée pour attribuer automatiquement les ID aux demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="1d3d2-114">Sur l’onglet **FMLA**, vérifiez les paramètres FMLA et modifiez-les si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="1d3d2-115">Sur l’onglet **Libre-service employé**, indiquez si les gestionnaires peuvent saisir des demandes de congé et d’absence au nom de leurs employés.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="1d3d2-116">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-116">Select **Save**.</span></span>

>[!IMPORTANT]
><span data-ttu-id="1d3d2-117">L'affichage des congés et des absences dans les entreprises est actuellement en version préliminaire.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-117">Viewing leave and absence across companies is currently in preview.</span></span> <span data-ttu-id="1d3d2-118">Vous devrez l'activer dans votre environnement de **bac à sable** pour afficher l'option de congé et d'absence.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-118">You'll need to enable it in your **Sandbox** environment to display the option for leave and absence.</span></span> <span data-ttu-id="1d3d2-119">Pour plus d’informations sur l'activation des fonctionnalités d'évaluation, voir [Gérer les fonctionnalités](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="1d3d2-119">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="view-and-change-human-resources-shared-parameters"></a><span data-ttu-id="1d3d2-120">Afficher et modifier les paramètres partagés des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="1d3d2-120">View and change Human resources shared parameters</span></span>

1. <span data-ttu-id="1d3d2-121">Sur la page **Gestion du personnel**, sélectionnez l'onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-121">On the **Personnel management** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="1d3d2-122">Sous **Configuration**, sélectionnez **Paramètres partagés des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-122">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="1d3d2-123">Sur l'onglet **Accès anticipé**, sélectionnez **Oui** pour **Activer l'affichage des congés intersociétés** pour permettre la visualisation des congés dans toute l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-123">On the **Advance access** tab, select **Yes** for **Enable cross company leave view** to allow leave to be viewed across company.</span></span>

4. <span data-ttu-id="1d3d2-124">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-124">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="1d3d2-125">Afficher et modifier les paramètres de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="1d3d2-125">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="1d3d2-126">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-126">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="1d3d2-127">Sous **Configuration**, sélectionnez **Paramètres de congé et d’absence**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-127">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="1d3d2-128">Dans l’onglet **Général**, définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="1d3d2-128">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="1d3d2-129">Définissez **Unités de congé et d’absence** sur des heures ou des jours.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-129">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="1d3d2-130">S’il s’agit de jours, vous pouvez sélectionner **Activer la définition d’une demi-journée** pour permettre aux employés de choisir la première ou la seconde partie de la journée dans leurs demandes de congés.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-130">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="1d3d2-131">Sélectionnez **Date d’entrée en vigueur des mois de service** pour déterminer quand les taux de régularisation entrent en vigueur pour les plans de congé avec les mois de service.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-131">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="1d3d2-132">Sélectionnez **Calcul du solde** pour afficher les soldes à partir d’aujourd’hui ou de la période de régularisation.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-132">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="1d3d2-133">Si vous sélectionnez **Solde à ce jour**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à ce jour.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-133">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="1d3d2-134">Si vous sélectionnez **Solde à compter de la période de régularisation**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à partir de la période de régularisation définie par la fréquence dans le plan de congés.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-134">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="1d3d2-135">Définissez l’heure de début du report de la tâche par lots d’expiration.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-135">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="1d3d2-136">Sélectionnez **Oui** pour **Autoriser les employés à acheter des congés** et **Autoriser les employés à vendre des congés**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-136">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="1d3d2-137">Si vous sélectionnez **Oui** pour ces options, vous pouvez créer des stratégies d’achat et de vente de congés et permettre aux employés de soumettre des demandes d’achat et de vente de congés.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-137">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="1d3d2-138">Configurer les paramètres de calendrier</span><span class="sxs-lookup"><span data-stu-id="1d3d2-138">Configure calendar parameters</span></span>

1. <span data-ttu-id="1d3d2-139">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-139">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="1d3d2-140">Sous **Configuration**, sélectionnez **Paramètres de congé et d’absence**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-140">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="1d3d2-141">Sur l’onglet **Calendrier**, modifiez les paramètres de calendrier si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-141">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="1d3d2-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1d3d2-142">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d3d2-143">Voir également :</span><span class="sxs-lookup"><span data-stu-id="1d3d2-143">See also</span></span>

- [<span data-ttu-id="1d3d2-144">Vue d’ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="1d3d2-144">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
