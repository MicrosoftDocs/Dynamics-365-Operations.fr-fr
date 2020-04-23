---
title: Configuration des types de congé et d'absence
description: Configurez les types de congés que les employés peuvent prendre dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
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
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198048"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="dc03d-103">Configuration des types de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="dc03d-103">Configure leave and absence types</span></span>

<span data-ttu-id="dc03d-104">Les types de congés dans Dynamics 365 Human Resources définissent les différents types d'absences que les employés peuvent signaler.</span><span class="sxs-lookup"><span data-stu-id="dc03d-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="dc03d-105">Vous pouvez adapter les types de congés en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="dc03d-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="dc03d-106">Voici des exemples de types de congés :</span><span class="sxs-lookup"><span data-stu-id="dc03d-106">Examples of leave types include:</span></span>

- <span data-ttu-id="dc03d-107">Congés payés</span><span class="sxs-lookup"><span data-stu-id="dc03d-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="dc03d-108">Congés non payés</span><span class="sxs-lookup"><span data-stu-id="dc03d-108">Unpaid leave</span></span>
- <span data-ttu-id="dc03d-109">Congés payés</span><span class="sxs-lookup"><span data-stu-id="dc03d-109">Paid vacation</span></span>
- <span data-ttu-id="dc03d-110">Congé maladie</span><span class="sxs-lookup"><span data-stu-id="dc03d-110">Sick leave</span></span>
- <span data-ttu-id="dc03d-111">Congés maladie</span><span class="sxs-lookup"><span data-stu-id="dc03d-111">Medical leave</span></span>
- <span data-ttu-id="dc03d-112">Congés parentaux</span><span class="sxs-lookup"><span data-stu-id="dc03d-112">Family leave</span></span>
- <span data-ttu-id="dc03d-113">Invalidité à court terme</span><span class="sxs-lookup"><span data-stu-id="dc03d-113">Short-term disability</span></span>
- <span data-ttu-id="dc03d-114">Congé de deuil</span><span class="sxs-lookup"><span data-stu-id="dc03d-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="dc03d-115">Ajouter un type de congé</span><span class="sxs-lookup"><span data-stu-id="dc03d-115">Add a leave type</span></span>

1. <span data-ttu-id="dc03d-116">Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="dc03d-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dc03d-117">Sous **Configuration**, sélectionnez **Types de congé et d'absence**.</span><span class="sxs-lookup"><span data-stu-id="dc03d-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="dc03d-118">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="dc03d-118">Select **New**.</span></span>

4. <span data-ttu-id="dc03d-119">Entrez un nom pour le type de congé sous **Type**, sélectionnez un workflow dans **ID workflow** et entrez une description sous **Description**.</span><span class="sxs-lookup"><span data-stu-id="dc03d-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="dc03d-120">Dans **Général**, sélectionnez **Aucun**, **Planifié**, ou **non planifié** dans me menu déroulant **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="dc03d-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="dc03d-121">Sélectionnez un code de rémunération dans le menu déroulant **Code de rémunération**.</span><span class="sxs-lookup"><span data-stu-id="dc03d-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="dc03d-122">Sous **Code motif obligatoire**, choisissez si vous souhaitez exiger un code de motif.</span><span class="sxs-lookup"><span data-stu-id="dc03d-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="dc03d-123">Si vous souhaitez exiger des codes de motif, vous devrez peut-être les ajouter.</span><span class="sxs-lookup"><span data-stu-id="dc03d-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="dc03d-124">Sous **Codes motif**, sélectionnez **Ajouter**, sélectionnez un code de motif, puis cochez la case **Activé** à côté.</span><span class="sxs-lookup"><span data-stu-id="dc03d-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="dc03d-125">Sous **Restreindre l'accès aux rôles sélectionnés**, choisissez si vous souhaitez restreindre l'accès.</span><span class="sxs-lookup"><span data-stu-id="dc03d-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="dc03d-126">Sélectionnez ensuite les rôles de sécurité sous **Rôles de sécurité pour ce type de congé**.</span><span class="sxs-lookup"><span data-stu-id="dc03d-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="dc03d-127">Les rôles de sécurité sont définis dans le workflow que vous avez sélectionné sous **ID workflow**plus tôt dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="dc03d-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="dc03d-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="dc03d-128">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="dc03d-129">Configurer les règles de type de congé</span><span class="sxs-lookup"><span data-stu-id="dc03d-129">Configure leave type rules</span></span>

1. <span data-ttu-id="dc03d-130">Définissez les options d'arrondi pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="dc03d-130">Set rounding options for the leave type.</span></span> <span data-ttu-id="dc03d-131">Les options incluent **Aucun**, **Haut**, **Bas** et **Le plus proche**.</span><span class="sxs-lookup"><span data-stu-id="dc03d-131">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="dc03d-132">Vous pouvez également définir la précision d'arrondi pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="dc03d-132">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="dc03d-133">Définissez **Correction des congés** pour le type de congés.</span><span class="sxs-lookup"><span data-stu-id="dc03d-133">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="dc03d-134">Lorsque vous sélectionnez cette option, Human Resources utilise le nombre de congés qui tombent un jour ouvrable pour déterminer comment cumuler des congés pour le type de congé.</span><span class="sxs-lookup"><span data-stu-id="dc03d-134">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="dc03d-135">Par exemple, si le jour de Noël tombe un lundi, Human Resources soustraira un jour du type de congé lors du traitement des régularisations.</span><span class="sxs-lookup"><span data-stu-id="dc03d-135">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="dc03d-136">Vous définissez des congés dans le calendrier du temps de travail.</span><span class="sxs-lookup"><span data-stu-id="dc03d-136">You set holidays in the working time calendar.</span></span> <span data-ttu-id="dc03d-137">Pour plus d'informations, voir [Création d'un calendrier du temps de travail](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="dc03d-137">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
## <a name="configure-preview-features"></a><span data-ttu-id="dc03d-138">Configuration des fonctionnalités d'aperçu</span><span class="sxs-lookup"><span data-stu-id="dc03d-138">Configure preview features</span></span>

<span data-ttu-id="dc03d-139">Si vous avez activé les fonctionnalités d'aperçu pour les congés et les absences, vous devez également configurer des paramètres pour elles.</span><span class="sxs-lookup"><span data-stu-id="dc03d-139">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="dc03d-140">Sélectionnez le type de congé pour le report des soldes à transférer.</span><span class="sxs-lookup"><span data-stu-id="dc03d-140">Choose the leave type for carry forward balances to be transferred to.</span></span> <span data-ttu-id="dc03d-141">Vous pouvez également créer un nouveau type de congé pour le report.</span><span class="sxs-lookup"><span data-stu-id="dc03d-141">You can also create a new leave type for carry forward.</span></span> 

## <a name="see-also"></a><span data-ttu-id="dc03d-142">Voir également :</span><span class="sxs-lookup"><span data-stu-id="dc03d-142">See also</span></span>

- [<span data-ttu-id="dc03d-143">Vue d'ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="dc03d-143">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="dc03d-144">Créer un plan de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="dc03d-144">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="dc03d-145">Création d'un calendrier du temps de travail</span><span class="sxs-lookup"><span data-stu-id="dc03d-145">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
