---
title: Configuration des paramètres de congé et d’absence
description: Définissez les paramètres des ressources humaines pour les congés et les absences dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
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
ms.openlocfilehash: 196c3901b5bc19f73b882bac7d3361e5bcc37e07
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712374"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="e3975-103">Configuration des paramètres de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="e3975-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="e3975-104">Avant de configurer des plans de congé et d’absence dans Dynamics 365 Human Resources, il est judicieux de vérifier la configuration de tous les paramètres des ressources humaines associés, notamment :</span><span class="sxs-lookup"><span data-stu-id="e3975-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="e3975-105">Souche de numéros pour les demandes de congé</span><span class="sxs-lookup"><span data-stu-id="e3975-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="e3975-106">Paramètres relatifs au Family Medical and Leave Act (FMLA)</span><span class="sxs-lookup"><span data-stu-id="e3975-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="e3975-107">Paramètres en libre-service des employés pour les demandes de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="e3975-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="e3975-108">Paramètres de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="e3975-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="e3975-109">Afficher et modifier les paramètres des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="e3975-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="e3975-110">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="e3975-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="e3975-111">Sous **Configuration**, sélectionnez **Paramètres des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="e3975-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="e3975-112">Sur l’onglet **Souches de numéros**, vérifiez le **Code souche de N°** pour **ID de demande de congé** et changez si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e3975-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="e3975-113">Ce paramètre détermine la souche utilisée pour attribuer automatiquement les ID aux demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="e3975-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="e3975-114">Sur l’onglet **FMLA**, vérifiez les paramètres FMLA et modifiez-les si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e3975-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="e3975-115">Sur l’onglet **Libre-service employé**, indiquez si les gestionnaires peuvent saisir des demandes de congé et d’absence au nom de leurs employés.</span><span class="sxs-lookup"><span data-stu-id="e3975-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="e3975-116">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e3975-116">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="e3975-117">Afficher et modifier les paramètres de congé et d’absence</span><span class="sxs-lookup"><span data-stu-id="e3975-117">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="e3975-118">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="e3975-118">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="e3975-119">Sous **Configuration**, sélectionnez **Paramètres de congé et d’absence**.</span><span class="sxs-lookup"><span data-stu-id="e3975-119">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="e3975-120">Dans l’onglet **Général**, définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e3975-120">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="e3975-121">Définissez **Unités de congé et d’absence** sur des heures ou des jours.</span><span class="sxs-lookup"><span data-stu-id="e3975-121">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="e3975-122">S’il s’agit de jours, vous pouvez sélectionner **Activer la définition d’une demi-journée** pour permettre aux employés de choisir la première ou la seconde partie de la journée dans leurs demandes de congés.</span><span class="sxs-lookup"><span data-stu-id="e3975-122">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="e3975-123">Sélectionnez **Date d’entrée en vigueur des mois de service** pour déterminer quand les taux de régularisation entrent en vigueur pour les plans de congé avec les mois de service.</span><span class="sxs-lookup"><span data-stu-id="e3975-123">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="e3975-124">Sélectionnez **Calcul du solde** pour afficher les soldes à partir d’aujourd’hui ou de la période de régularisation.</span><span class="sxs-lookup"><span data-stu-id="e3975-124">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="e3975-125">Si vous sélectionnez **Solde à ce jour**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à ce jour.</span><span class="sxs-lookup"><span data-stu-id="e3975-125">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="e3975-126">Si vous sélectionnez **Solde à compter de la période de régularisation**, le solde affiche le total de toutes les régularisations, des ajustements et des demandes à partir de la période de régularisation définie par la fréquence dans le plan de congés.</span><span class="sxs-lookup"><span data-stu-id="e3975-126">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="e3975-127">Définissez l’heure de début du report de la tâche par lots d’expiration.</span><span class="sxs-lookup"><span data-stu-id="e3975-127">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="e3975-128">Sélectionnez **Oui** pour **Autoriser les employés à acheter des congés** et **Autoriser les employés à vendre des congés**.</span><span class="sxs-lookup"><span data-stu-id="e3975-128">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="e3975-129">Si vous sélectionnez **Oui** pour ces options, vous pouvez créer des stratégies d’achat et de vente de congés et permettre aux employés de soumettre des demandes d’achat et de vente de congés.</span><span class="sxs-lookup"><span data-stu-id="e3975-129">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="e3975-130">Configurer les paramètres de calendrier</span><span class="sxs-lookup"><span data-stu-id="e3975-130">Configure calendar parameters</span></span>

1. <span data-ttu-id="e3975-131">Dans la page **Plans de congé et d’absence**, sélectionnez l’onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="e3975-131">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="e3975-132">Sous **Configuration**, sélectionnez **Paramètres de congé et d’absence**.</span><span class="sxs-lookup"><span data-stu-id="e3975-132">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="e3975-133">Sur l’onglet **Calendrier**, modifiez les paramètres de calendrier si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e3975-133">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="e3975-134">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e3975-134">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3975-135">Voir également :</span><span class="sxs-lookup"><span data-stu-id="e3975-135">See also</span></span>

- [<span data-ttu-id="e3975-136">Vue d’ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="e3975-136">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
