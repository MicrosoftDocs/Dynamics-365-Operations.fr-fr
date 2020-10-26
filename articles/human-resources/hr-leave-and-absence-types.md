---
title: Configuration des types de congé et d'absence
description: Configurez les types de congés que les employés peuvent prendre dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 6e6ca7d04b86232ba48474fcbe288a18995661ae
ms.sourcegitcommit: 6a89816f94c8cdcae6e56fa89843eb99c28b21fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "3969020"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="646c3-103">Configuration des types de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="646c3-103">Configure leave and absence types</span></span>

<span data-ttu-id="646c3-104">Les types de congés dans Dynamics 365 Human Resources définissent les différents types d'absences que les employés peuvent signaler.</span><span class="sxs-lookup"><span data-stu-id="646c3-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="646c3-105">Vous pouvez adapter les types de congés en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="646c3-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="646c3-106">Voici des exemples de types de congés :</span><span class="sxs-lookup"><span data-stu-id="646c3-106">Examples of leave types include:</span></span>

- <span data-ttu-id="646c3-107">Congés payés</span><span class="sxs-lookup"><span data-stu-id="646c3-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="646c3-108">Congés non payés</span><span class="sxs-lookup"><span data-stu-id="646c3-108">Unpaid leave</span></span>
- <span data-ttu-id="646c3-109">Congés payés</span><span class="sxs-lookup"><span data-stu-id="646c3-109">Paid vacation</span></span>
- <span data-ttu-id="646c3-110">Congé maladie</span><span class="sxs-lookup"><span data-stu-id="646c3-110">Sick leave</span></span>
- <span data-ttu-id="646c3-111">Congés maladie</span><span class="sxs-lookup"><span data-stu-id="646c3-111">Medical leave</span></span>
- <span data-ttu-id="646c3-112">Congés parentaux</span><span class="sxs-lookup"><span data-stu-id="646c3-112">Family leave</span></span>
- <span data-ttu-id="646c3-113">Invalidité à court terme</span><span class="sxs-lookup"><span data-stu-id="646c3-113">Short-term disability</span></span>
- <span data-ttu-id="646c3-114">Congé de deuil</span><span class="sxs-lookup"><span data-stu-id="646c3-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="646c3-115">Ajouter un type de congé</span><span class="sxs-lookup"><span data-stu-id="646c3-115">Add a leave type</span></span>

1. <span data-ttu-id="646c3-116">Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="646c3-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="646c3-117">Sous **Configuration**, sélectionnez **Types de congé et d'absence**.</span><span class="sxs-lookup"><span data-stu-id="646c3-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="646c3-118">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="646c3-118">Select **New**.</span></span>

4. <span data-ttu-id="646c3-119">Entrez un nom pour le type de congé sous **Type**, sélectionnez un workflow dans **ID workflow** et entrez une description sous **Description**.</span><span class="sxs-lookup"><span data-stu-id="646c3-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="646c3-120">Dans **Général**, sélectionnez **Aucun**, **Planifié**, ou **non planifié** dans me menu déroulant **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="646c3-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="646c3-121">Sélectionnez un code de rémunération dans le menu déroulant **Code de rémunération**.</span><span class="sxs-lookup"><span data-stu-id="646c3-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="646c3-122">Sous **Code motif obligatoire**, choisissez si vous souhaitez exiger un code de motif.</span><span class="sxs-lookup"><span data-stu-id="646c3-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="646c3-123">Si vous souhaitez exiger des codes de motif, vous devrez peut-être les ajouter.</span><span class="sxs-lookup"><span data-stu-id="646c3-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="646c3-124">Sous **Codes motif**, sélectionnez **Ajouter**, sélectionnez un code de motif, puis cochez la case **Activé** à côté.</span><span class="sxs-lookup"><span data-stu-id="646c3-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="646c3-125">Sous **Restreindre l'accès aux rôles sélectionnés**, choisissez si vous souhaitez restreindre l'accès.</span><span class="sxs-lookup"><span data-stu-id="646c3-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="646c3-126">Sélectionnez ensuite les rôles de sécurité sous **Rôles de sécurité pour ce type de congé**.</span><span class="sxs-lookup"><span data-stu-id="646c3-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="646c3-127">Les rôles de sécurité sont définis dans le workflow que vous avez sélectionné sous **ID workflow**plus tôt dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="646c3-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="646c3-128">Sous **Couleur du calendrier**, choisissez la couleur à afficher sur les calendriers de congé et d'absence pour ce type de congé.</span><span class="sxs-lookup"><span data-stu-id="646c3-128">Under **Calendar color**, choose what color to display on leave and absence calendars for this leave type.</span></span> 

10. <span data-ttu-id="646c3-129">En dessous de **Relations de suspension**, choisissez si vous souhaitez que ce type de congé suspende un autre type de congé ou soit suspendu par un autre type de congé.</span><span class="sxs-lookup"><span data-stu-id="646c3-129">Under **Suspension relations**, choose if you want to have this leave type either suspend another leave type or be suspended by another leave type.</span></span> <span data-ttu-id="646c3-130">Lorsqu'une demande de congé est soumise pour le type de congé suspendu, une suspension de congé est automatiquement créée pour le type de congé suspendu.</span><span class="sxs-lookup"><span data-stu-id="646c3-130">When a leave of absence request is submitted for the suspending leave type, a leave suspension will automatically be created for the suspended leave type.</span></span> 

10. <span data-ttu-id="646c3-131">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="646c3-131">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="646c3-132">Configurer les règles de type de congé</span><span class="sxs-lookup"><span data-stu-id="646c3-132">Configure leave type rules</span></span>

1. <span data-ttu-id="646c3-133">Définissez les options d'arrondi pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="646c3-133">Set rounding options for the leave type.</span></span> <span data-ttu-id="646c3-134">Les options incluent **Aucun**, **Haut**, **Bas** et **Le plus proche**.</span><span class="sxs-lookup"><span data-stu-id="646c3-134">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="646c3-135">Vous pouvez également définir la précision d'arrondi pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="646c3-135">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="646c3-136">Définissez **Correction des congés** pour le type de congés.</span><span class="sxs-lookup"><span data-stu-id="646c3-136">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="646c3-137">Lorsque vous sélectionnez cette option, Human Resources utilise le nombre de congés qui tombent un jour ouvrable pour déterminer comment cumuler des congés pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="646c3-137">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="646c3-138">Par exemple, si le jour de Noël tombe un lundi, Human Resources soustraira un jour du type de congé lors du traitement des régularisations.</span><span class="sxs-lookup"><span data-stu-id="646c3-138">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="646c3-139">Vous définissez des congés dans le calendrier du temps de travail.</span><span class="sxs-lookup"><span data-stu-id="646c3-139">You set holidays in the working time calendar.</span></span> <span data-ttu-id="646c3-140">Pour plus d'informations, voir [Création d'un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="646c3-140">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
 3. <span data-ttu-id="646c3-141">Définissez **Report de type de congé** pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="646c3-141">Set **Carry-forward leave type** for the leave type.</span></span> <span data-ttu-id="646c3-142">Lorsque vous sélectionnez cette option, tous les soldes de report seront transférés vers le type de congé spécifié.</span><span class="sxs-lookup"><span data-stu-id="646c3-142">When you select this option, any carry-forward balances will be transferred to the specified leave type.</span></span> <span data-ttu-id="646c3-143">Le report de type de congé doit également être inclus dans le plan de congé et d'absence.</span><span class="sxs-lookup"><span data-stu-id="646c3-143">The carry-forward leave type also needs to be included in the leave and absence plan.</span></span> 
 
 4. <span data-ttu-id="646c3-144">Définissez **Règles d'expiration** pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="646c3-144">Define **Expiration rules** for the leave type.</span></span> <span data-ttu-id="646c3-145">Lorsque vous configurez cette option, vous pouvez choisir l'unité jours ou mois et définir la durée de l'expiration.</span><span class="sxs-lookup"><span data-stu-id="646c3-145">When you configure this option, you can choose the unit of days or months and set the duration for the expiry.</span></span> <span data-ttu-id="646c3-146">Vous pouvez également définir la date d'entrée en vigueur de la règle d'expiration.</span><span class="sxs-lookup"><span data-stu-id="646c3-146">You can also set the effective date of the expiration rule.</span></span> <span data-ttu-id="646c3-147">Tout solde de congé existant au moment de l'expiration sera soustrait du type de congé et sera reflété dans le solde de congé.</span><span class="sxs-lookup"><span data-stu-id="646c3-147">Any leave balances that exist at the time of expiry will be subtracted from the leave type and will be reflected in the leave balance.</span></span> 
 
 
## <a name="see-also"></a><span data-ttu-id="646c3-148">Voir également :</span><span class="sxs-lookup"><span data-stu-id="646c3-148">See also</span></span>

- [<span data-ttu-id="646c3-149">Vue d'ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="646c3-149">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="646c3-150">Créer un plan de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="646c3-150">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="646c3-151">Créer un calendrier du temps de travail</span><span class="sxs-lookup"><span data-stu-id="646c3-151">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
- [<span data-ttu-id="646c3-152">Suspendre les congés</span><span class="sxs-lookup"><span data-stu-id="646c3-152">Suspend leave</span></span>](hr-leave-and-absence-suspend-leave.md)

