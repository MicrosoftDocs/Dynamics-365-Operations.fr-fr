---
title: Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (11 janvier 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d49a4aca368e3de10ae37b56c6d286d78f7f369a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899172"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-11-2019"></a><span data-ttu-id="61b9d-103">Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (11 janvier 2019)</span><span class="sxs-lookup"><span data-stu-id="61b9d-103">What's new or changed in Dynamics 365 Talent - Core HR (January 11, 2019)</span></span>

<span data-ttu-id="61b9d-104">**Version 8.1.2100**</span><span class="sxs-lookup"><span data-stu-id="61b9d-104">**Build 8.1.2100**</span></span>

<span data-ttu-id="61b9d-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="61b9d-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="61b9d-106">Modifications</span><span class="sxs-lookup"><span data-stu-id="61b9d-106">Changes</span></span>

### <a name="validate-leave-requests-by-forecasting-available-balance"></a><span data-ttu-id="61b9d-107">Valider les demandes de congés en prévoyant le solde disponible</span><span class="sxs-lookup"><span data-stu-id="61b9d-107">Validate leave requests by forecasting available balance</span></span>
<span data-ttu-id="61b9d-108">Les modifications apportées dans cette version permettent aux employés de demander un congé à venir sans le soustraire de son solde actuel.</span><span class="sxs-lookup"><span data-stu-id="61b9d-108">Changes made in this release allow employees to request future leave time without subtracting from their current balance.</span></span> <span data-ttu-id="61b9d-109">Les workflows standard seront utilisées pour toute demande ultérieure.</span><span class="sxs-lookup"><span data-stu-id="61b9d-109">Standard workflows will be used for any future requests made.</span></span> <span data-ttu-id="61b9d-110">Pour plus d'informations, voir [Accorder des congés sur la base des heures travaillées](leave-accrue-hours-worked.md).</span><span class="sxs-lookup"><span data-stu-id="61b9d-110">For more information, read [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a><span data-ttu-id="61b9d-111">Afficher le solde des congés prévus dans ESS et People</span><span class="sxs-lookup"><span data-stu-id="61b9d-111">View forecasted leave balance in ESS and People</span></span>
<span data-ttu-id="61b9d-112">Cette fonction permet d'afficher les soldes pour les périodes de congés à venir par les RH, les responsables et les employés.</span><span class="sxs-lookup"><span data-stu-id="61b9d-112">This feature enables viewing of balances for future leave periods by HR, managers, and employees.</span></span> <span data-ttu-id="61b9d-113">Les employés peuvent afficher les futurs soldes dans l'espace de travail **Libre-service employé** et les RH ont accès aux mêmes informations via l'espace de travail **Personnes**.</span><span class="sxs-lookup"><span data-stu-id="61b9d-113">Employees can view future balances in the **Employee Self-Service** workspace and HR has access to the same information using the **People** workspace.</span></span>

### <a name="notifications-for-changing-leave-balances"></a><span data-ttu-id="61b9d-114">Notifications pour modifier les soldes de congés</span><span class="sxs-lookup"><span data-stu-id="61b9d-114">Notifications for changing leave balances</span></span>
<span data-ttu-id="61b9d-115">Les soldes de congés afficheront le solde actuel des employés.</span><span class="sxs-lookup"><span data-stu-id="61b9d-115">Leave balances will display the employees current balance.</span></span> <span data-ttu-id="61b9d-116">Les futurs soldes sont disponibles dans les espaces de travail **Libre-service employé** et **Personnes** en saisissant une « Date à compter de » pour calculer le solde prévu.</span><span class="sxs-lookup"><span data-stu-id="61b9d-116">Future balances are available on the **Employee Self-Service** and **People** workspaces by entering an “as of date” to calculate the forecasted balance.</span></span>

<span data-ttu-id="61b9d-117">La navigation a été ajoutée pour visualiser les soldes prévues dans les zones suivantes :</span><span class="sxs-lookup"><span data-stu-id="61b9d-117">Navigation has been added to view forecasted balances in the following areas:</span></span>
  - <span data-ttu-id="61b9d-118">Carte **Congés** sur l'espace de travail **Libre-service employé**.</span><span class="sxs-lookup"><span data-stu-id="61b9d-118">**Time off** card on the **Employee Self-Service** workspace.</span></span>
  - <span data-ttu-id="61b9d-119">Carte **Congés et absences** sur l'espace de travail **Libre-service Responsable**.</span><span class="sxs-lookup"><span data-stu-id="61b9d-119">**Leave and absence** card on the **Manager Self-Service** workspace.</span></span>
  - <span data-ttu-id="61b9d-120">Page**Congés et absences** sur l'espace de travail **Personnes**.</span><span class="sxs-lookup"><span data-stu-id="61b9d-120">**Leave and absence** page on the **People** workspace.</span></span>

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a><span data-ttu-id="61b9d-121">Autoriser les décimales pour les régimes de rémunération variable (plans de disponibilités)</span><span class="sxs-lookup"><span data-stu-id="61b9d-121">Allow decimals for Variable compensation plans (Cash plans)</span></span>
<span data-ttu-id="61b9d-122">Les primes de disponibilités variables et les plans ont désormais la flexibilité supplémentaire pour les montants et les remplacements pour les valeurs avec des montants en décimaux.</span><span class="sxs-lookup"><span data-stu-id="61b9d-122">Variable cash awards and plans now have the additional flexibility for amounts and overrides for values with decimal amounts.</span></span>

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a><span data-ttu-id="61b9d-123">Impossibilité de modifier les dates sur les inscriptions à la rémunération variable une fois que le plan est enregistré</span><span class="sxs-lookup"><span data-stu-id="61b9d-123">Unable to change the dates on Variable comp enrollments after the plan is saved</span></span>
<span data-ttu-id="61b9d-124">Cette modification autorise la mise à jour de la date finale du plan (étendue ou expirée) une fois le plan enregistré.</span><span class="sxs-lookup"><span data-stu-id="61b9d-124">This change allows for the plan end date to be updated (extended or expired) after the plan has been saved.</span></span> <span data-ttu-id="61b9d-125">Vous pouvez encore activer ou désactiver les plans indépendamment des dates de début ou de fin.</span><span class="sxs-lookup"><span data-stu-id="61b9d-125">You can still activate or de-activate plans independent of start and end dates.</span></span>

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a><span data-ttu-id="61b9d-126">Les informations relatives aux salaires disponibles lors de l'attribution du rôle de sécurité de l'administrateur des salaires</span><span class="sxs-lookup"><span data-stu-id="61b9d-126">Payroll information available when assigned the Payroll admin security role</span></span>
<span data-ttu-id="61b9d-127">Le rôle Administrateur des salaires a été mis à jour pour accéder aux informations relatives aux salaires pendant le processus de demande.</span><span class="sxs-lookup"><span data-stu-id="61b9d-127">The Payroll Administrator role has been updated to have access to the payroll information during the request process.</span></span>

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="61b9d-128">Libre-service employé | Hiérarchie des postes, depuis la vignette échoue à obtenir un nœud parent</span><span class="sxs-lookup"><span data-stu-id="61b9d-128">Employee self-service | Position hierarchy drill-down from tile fails to get parent node</span></span>
<span data-ttu-id="61b9d-129">Les modifications ont été apportées pour supprimer une erreur qui survenait lors de l'ajout de la hiérarchie des postes à de nouveaux espaces de travail et de l'accès à la structure organisationnelle.</span><span class="sxs-lookup"><span data-stu-id="61b9d-129">Changes have been made to eliminate an error that occurred when adding the position hierarchy to new workspaces and navigating within the organizational structure.</span></span>

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a><span data-ttu-id="61b9d-130">Nouveau message de validation lorsque la souche de nombre personnel est utilisée</span><span class="sxs-lookup"><span data-stu-id="61b9d-130">New validation message when personnel number sequence is in use</span></span>
<span data-ttu-id="61b9d-131">Une modification a été apportée pour clarifier le problème lorsque vous engagez un employé et que le numéro du personnel suivant est utilisé.</span><span class="sxs-lookup"><span data-stu-id="61b9d-131">A change has been made to clarify what the issue is when you hire an employee and the next personnel number is in use.</span></span>

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a><span data-ttu-id="61b9d-132">L'espace de travail Libre-service employé sélectionné comme page de démarrage initial</span><span class="sxs-lookup"><span data-stu-id="61b9d-132">Employee self-service workspace selected as the initial startup page</span></span>
<span data-ttu-id="61b9d-133">Lorsque l'espace de travail **Libre-service employé** est sélectionné comme page de démarrage initial pour un utilisateur et qu'un utilisateur n'a pas le rôle d'employé, le système redirigera vers le tableau de bord par défaut.</span><span class="sxs-lookup"><span data-stu-id="61b9d-133">When the **Employee self-service** workspace is selected as the initial startup page for a user and that user is not assigned the employee role, the system will redirect to the default dashboard.</span></span>

### <a name="termination-reason-code-updates-position-assignment-record"></a><span data-ttu-id="61b9d-134">Le code du motif de résiliation du contrat met à jour l'enregistrement d'attribution de poste</span><span class="sxs-lookup"><span data-stu-id="61b9d-134">Termination reason code updates position assignment record</span></span>
<span data-ttu-id="61b9d-135">Le code du motif de résiliation mettra désormais à jour l'attribution de poste lors de la résiliation du contrat d'un employé et la fin du poste.</span><span class="sxs-lookup"><span data-stu-id="61b9d-135">The termination reason code will now update the position assignment when terminating an employee and ending the position.</span></span> 
