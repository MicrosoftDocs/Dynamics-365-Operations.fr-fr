---
title: Configuration des types de congé et d'absence
description: Configurez les types de congés que les employés peuvent prendre dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1748ec2a888a50af9b9260720dfd439adc4686f9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009054"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="98f05-103">Configuration des types de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="98f05-103">Configure leave and absence types</span></span>

<span data-ttu-id="98f05-104">Les types de congés dans Dynamics 365 Human Resources définissent les différents types d'absences que les employés peuvent signaler.</span><span class="sxs-lookup"><span data-stu-id="98f05-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="98f05-105">Vous pouvez adapter les types de congés en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="98f05-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="98f05-106">Voici des exemples de types de congés :</span><span class="sxs-lookup"><span data-stu-id="98f05-106">Examples of leave types include:</span></span>

- <span data-ttu-id="98f05-107">Congés payés</span><span class="sxs-lookup"><span data-stu-id="98f05-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="98f05-108">Congés non payés</span><span class="sxs-lookup"><span data-stu-id="98f05-108">Unpaid leave</span></span>
- <span data-ttu-id="98f05-109">Congés payés</span><span class="sxs-lookup"><span data-stu-id="98f05-109">Paid vacation</span></span>
- <span data-ttu-id="98f05-110">Congé maladie</span><span class="sxs-lookup"><span data-stu-id="98f05-110">Sick leave</span></span>
- <span data-ttu-id="98f05-111">Congés maladie</span><span class="sxs-lookup"><span data-stu-id="98f05-111">Medical leave</span></span>
- <span data-ttu-id="98f05-112">Congés parentaux</span><span class="sxs-lookup"><span data-stu-id="98f05-112">Family leave</span></span>
- <span data-ttu-id="98f05-113">Invalidité à court terme</span><span class="sxs-lookup"><span data-stu-id="98f05-113">Short-term disability</span></span>
- <span data-ttu-id="98f05-114">Congé de deuil</span><span class="sxs-lookup"><span data-stu-id="98f05-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="98f05-115">Ajouter un type de congé</span><span class="sxs-lookup"><span data-stu-id="98f05-115">Add a leave type</span></span>

1. <span data-ttu-id="98f05-116">Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="98f05-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="98f05-117">Sous **Configuration**, sélectionnez **Types de congé et d'absence**.</span><span class="sxs-lookup"><span data-stu-id="98f05-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="98f05-118">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="98f05-118">Select **New**.</span></span>

4. <span data-ttu-id="98f05-119">Entrez un nom pour le type de congé sous **Type**, sélectionnez un workflow dans **ID workflow** et entrez une description sous **Description**.</span><span class="sxs-lookup"><span data-stu-id="98f05-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="98f05-120">Dans **Général**, sélectionnez **Aucun**, **Planifié**, ou **non planifié** dans me menu déroulant **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="98f05-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="98f05-121">Sélectionnez un code de rémunération dans le menu déroulant **Code de rémunération**.</span><span class="sxs-lookup"><span data-stu-id="98f05-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="98f05-122">Sous **Code motif obligatoire**, choisissez si vous souhaitez exiger un code de motif.</span><span class="sxs-lookup"><span data-stu-id="98f05-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="98f05-123">Si vous souhaitez exiger des codes de motif, vous devrez peut-être les ajouter.</span><span class="sxs-lookup"><span data-stu-id="98f05-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="98f05-124">Sous **Codes motif**, sélectionnez **Ajouter**, sélectionnez un code de motif, puis cochez la case **Activé** à côté.</span><span class="sxs-lookup"><span data-stu-id="98f05-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="98f05-125">Sous **Restreindre l'accès aux rôles sélectionnés**, choisissez si vous souhaitez restreindre l'accès.</span><span class="sxs-lookup"><span data-stu-id="98f05-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="98f05-126">Sélectionnez ensuite les rôles de sécurité sous **Rôles de sécurité pour ce type de congé**.</span><span class="sxs-lookup"><span data-stu-id="98f05-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="98f05-127">Les rôles de sécurité sont définis dans le workflow que vous avez sélectionné sous **ID workflow**plus tôt dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="98f05-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="98f05-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="98f05-128">Select **Save**.</span></span>

## <a name="configure-preview-features"></a><span data-ttu-id="98f05-129">Configuration des fonctionnalités d'aperçu</span><span class="sxs-lookup"><span data-stu-id="98f05-129">Configure preview features</span></span>

<span data-ttu-id="98f05-130">Si vous avez activé les fonctionnalités d'aperçu pour les congés et les absences, vous devez également configurer des paramètres pour elles.</span><span class="sxs-lookup"><span data-stu-id="98f05-130">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="98f05-131">Définissez les options d'arrondi pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="98f05-131">Set rounding options for the leave type.</span></span> <span data-ttu-id="98f05-132">Les options incluent **Aucun**, **Haut**, **Bas** et **Le plus proche**.</span><span class="sxs-lookup"><span data-stu-id="98f05-132">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="98f05-133">Vous pouvez également définir la précision d'arrondi pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="98f05-133">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="98f05-134">Définissez **Correction des congés** pour le type de congés.</span><span class="sxs-lookup"><span data-stu-id="98f05-134">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="98f05-135">Lorsque vous sélectionnez cette option, Human Resources utilise le nombre de congés qui tombent un jour ouvrable pour déterminer comment cumuler des congés pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="98f05-135">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="98f05-136">Par exemple, si le jour de Noël tombe un lundi, Human Resources soustraira un jour du type de congé lors du traitement des régularisations.</span><span class="sxs-lookup"><span data-stu-id="98f05-136">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="98f05-137">Vous définissez des congés dans le calendrier du temps de travail.</span><span class="sxs-lookup"><span data-stu-id="98f05-137">You set holidays in the working time calendar.</span></span> <span data-ttu-id="98f05-138">Pour plus d'informations, voir [Création d'un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="98f05-138">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="98f05-139">Voir également :</span><span class="sxs-lookup"><span data-stu-id="98f05-139">See also</span></span>

- [<span data-ttu-id="98f05-140">Vue d'ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="98f05-140">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="98f05-141">Création d'un plan de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="98f05-141">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="98f05-142">Création d'un calendrier du temps de travail</span><span class="sxs-lookup"><span data-stu-id="98f05-142">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)