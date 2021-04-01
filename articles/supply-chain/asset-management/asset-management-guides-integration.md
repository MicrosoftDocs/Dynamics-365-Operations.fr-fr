---
title: Intégration de Dynamics 365 Supply Chain Management (Gestion des actifs) avec Dynamics 365 Guides
description: Cette rubrique explique comment intégrer le module Gestion des actifs dans Microsoft Dynamics 365 Supply Chain Management avec Dynamics 365 Guides pour bénéficier de guides de réalité mixte dans vos workflows de service et de maintenance au quotidien.
author: kamaybac
manager: tfehr
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: e3e9e74397faec12f6eecff1f562fd9d731ac5e2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230150"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a><span data-ttu-id="3d18b-103">Intégration de Dynamics 365 Supply Chain Management (Gestion des actifs) avec Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="3d18b-103">Integrate Dynamics 365 Supply Chain Management (Asset management) with Dynamics 365 Guides</span></span>

<span data-ttu-id="3d18b-104">Vous pouvez intégrer le module **Gestion des actifs** dans Microsoft Dynamics 365 Supply Chain Management avec Dynamics 365 Guides pour bénéficier de guides de réalité mixte dans vos workflows de service et de maintenance au quotidien.</span><span class="sxs-lookup"><span data-stu-id="3d18b-104">You can integrate the **Asset management** module in Microsoft Dynamics 365 Supply Chain Management with Dynamics 365 Guides to take advantage of mixed-reality guides in your day-to-day service and maintenance workflows.</span></span> <span data-ttu-id="3d18b-105">Si un guide est associé à un ordre de travail Gestion des actifs, un collaborateur qui ouvre la liste de contrôle de maintenance de l’ordre de travail dans l’application mobile Supply Chain Management (Dynamics 365) voit qu’un guide est disponible.</span><span class="sxs-lookup"><span data-stu-id="3d18b-105">If a guide is associated with an Asset Management work order, a worker who opens the work order's maintenance checklist in the Supply Chain Management (Dynamics 365) mobile app sees that a guide is available.</span></span> <span data-ttu-id="3d18b-106">Le collaborateur peut alors trouver et ouvrir le guide dans l’application Dynamics 365 Guides HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3d18b-106">The worker can then find and open the guide in the Dynamics 365 Guides HoloLens app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d18b-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="3d18b-107">Prerequisites</span></span>

<span data-ttu-id="3d18b-108">Avant de pouvoir joindre des guides aux bons de travail de gestion des actifs, vous devez remplir ces conditions préalables :</span><span class="sxs-lookup"><span data-stu-id="3d18b-108">Before you can attach guides to Asset management work orders, you must complete these prerequisites:</span></span>

- <span data-ttu-id="3d18b-109">[Configurer Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="3d18b-109">[Set up Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 or later.</span></span>
- <span data-ttu-id="3d18b-110">[Activer la double écriture pour les applications Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="3d18b-110">[Turn on dual-write for Supply Chain Management apps](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span></span>
- <span data-ttu-id="3d18b-111">[Activer le vol](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) pour la fonctionnalité **MRGuidesFeature**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-111">[Turn on flight](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) for the **MRGuidesFeature** feature.</span></span> <span data-ttu-id="3d18b-112">(Pour les environnements de production, vous devez d’abord soumettre un ticket d’assistance pour que votre locataire soit ajouté au groupe de pilotage.)</span><span class="sxs-lookup"><span data-stu-id="3d18b-112">(For production environments, you must first submit a support ticket to have your tenant added to the flighting group.)</span></span>
- <span data-ttu-id="3d18b-113">[Activez les clés de configuration suivantes](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) sur la page **Configuration des licences** :</span><span class="sxs-lookup"><span data-stu-id="3d18b-113">[Turn on the following configuration keys](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) on the **License configuration** page:</span></span>

    - <span data-ttu-id="3d18b-114">Gestion des actifs \> Gestion des actifs de réalité mixte</span><span class="sxs-lookup"><span data-stu-id="3d18b-114">Asset management \> Asset management mixed reality</span></span>
    - <span data-ttu-id="3d18b-115">Réalité mixte \> Guide de réalité mixte</span><span class="sxs-lookup"><span data-stu-id="3d18b-115">Mixed reality \> Mixed reality guide</span></span>

- <span data-ttu-id="3d18b-116">[Configurer Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="3d18b-116">[Set up Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 or later.</span></span>

## <a name="use-dynamics-365-guides-with-asset-management"></a><span data-ttu-id="3d18b-117">Utiliser Dynamics 365 Guides avec le module Gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="3d18b-117">Use Dynamics 365 Guides with Asset management</span></span>

<span data-ttu-id="3d18b-118">Pour associer un guide, vous utilisez une ligne de liste de contrôle de maintenance dans Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="3d18b-118">To associate a guide, you use a maintenance checklist line in Asset management.</span></span> <span data-ttu-id="3d18b-119">Vous pouvez créer l’association via un modèle de liste de contrôle de maintenance, un type de travail de maintenance ou un ordre de travail, car les trois contiennent des lignes de liste de contrôle de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3d18b-119">You can create the association through a maintenance checklist template, a maintenance job type, or a work order, because all three contain maintenance checklist lines.</span></span> <span data-ttu-id="3d18b-120">Vous pouvez gagner du temps en utilisant un modèle, car un modèle peut être associé à tous les types de travaux de maintenance qui l’utilisent.</span><span class="sxs-lookup"><span data-stu-id="3d18b-120">You can save time by using a template, because a template can be associated with all the maintenance job types that use it.</span></span> <span data-ttu-id="3d18b-121">Par exemple, un guide associé à un type de travail de maintenance est automatiquement associé à tous les ordres de travail qui spécifient ce type de travail.</span><span class="sxs-lookup"><span data-stu-id="3d18b-121">For example, a guide that is associated with a maintenance job type is automatically associated with all work orders that specify that job type.</span></span> <span data-ttu-id="3d18b-122">D’un autre côté, un guide associé directement à un ordre de travail n’existe que pour cet ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3d18b-122">On the other hand, a guide that is associated directly with a work order exists only for that work order.</span></span>

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a><span data-ttu-id="3d18b-123">Associer un guide à un modèle de liste de contrôle de maintenance</span><span class="sxs-lookup"><span data-stu-id="3d18b-123">Associate a guide with a maintenance checklist template</span></span>

<span data-ttu-id="3d18b-124">Pour associer un guide à un modèle de liste de contrôle de maintenance, suivez cette procédure.</span><span class="sxs-lookup"><span data-stu-id="3d18b-124">To associate a guide with a maintenance checklist template, follow these steps.</span></span>

1. <span data-ttu-id="3d18b-125">Créez un guide en utilisant les applications Dynamics 365 Guides PC et HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3d18b-125">Create a guide by using the Dynamics 365 Guides PC and HoloLens apps.</span></span> <span data-ttu-id="3d18b-126">Pour plus d’informations sur le mode de création d’un guide, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3d18b-126">For information about how to create a guide, see the following topics:</span></span>

    - [<span data-ttu-id="3d18b-127">Utiliser l’application PC pour créer un guide</span><span class="sxs-lookup"><span data-stu-id="3d18b-127">Use the PC app to create a guide</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [<span data-ttu-id="3d18b-128">Utiliser l’application HoloLens pour placer vos hologrammes</span><span class="sxs-lookup"><span data-stu-id="3d18b-128">Use the HoloLens app to place your holograms</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. <span data-ttu-id="3d18b-129">Dans Supply Chain Management, [créez un modèle de liste de contrôle de maintenance](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span><span class="sxs-lookup"><span data-stu-id="3d18b-129">In Supply Chain Management, [create a maintenance checklist template](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span></span>
1. <span data-ttu-id="3d18b-130">Associez le guide que vous avez créé à une ligne de liste de contrôle de maintenance dans le nouveau modèle de liste de contrôle de maintenance :</span><span class="sxs-lookup"><span data-stu-id="3d18b-130">Associate the guide that you created with a maintenance checklist line in the new maintenance checklist template:</span></span>

    1. <span data-ttu-id="3d18b-131">Sur le raccourci **Lignes de liste de contrôle de maintenance**, sélectionnez la ligne à laquelle vous souhaitez associer le guide.</span><span class="sxs-lookup"><span data-stu-id="3d18b-131">On the **Maintenance checklist lines** FastTab, select the line that you want to associate the guide with.</span></span>
    1. <span data-ttu-id="3d18b-132">Dans le raccourci **Guides associés**, sélectionnez **Ajouter un guide**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-132">On the **Associated guides** FastTab, select **Add Guide**.</span></span>

        <span data-ttu-id="3d18b-133">![Associer un guide à un modèle de ligne de contrôle de maintenance](media/am-guides-integration-add-guide.png "Associer un guide à un modèle de ligne de contrôle de maintenance")</span><span class="sxs-lookup"><span data-stu-id="3d18b-133">![Associate a guide with a maintenance checklist line](media/am-guides-integration-add-guide.png "Associate a guide with a maintenance checklist line")</span></span>

    1. <span data-ttu-id="3d18b-134">Dans le champ **Nom**, sélectionnez un guide, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-134">In the **Name** field, select a guide, and then select **Save**.</span></span>

        <span data-ttu-id="3d18b-135">![Sélectionner un guide dans le champ Nom](media/am-guides-integration-select-guide.png "Sélectionner un guide dans le champ Nom")</span><span class="sxs-lookup"><span data-stu-id="3d18b-135">![Select a guide in the Name field](media/am-guides-integration-select-guide.png "Select a guide in the Name field")</span></span>

1. <span data-ttu-id="3d18b-136">Associer le modèle de liste de contrôle de maintenance à un type de tâche :</span><span class="sxs-lookup"><span data-stu-id="3d18b-136">Associate the maintenance checklist template with a job type:</span></span>

    1. <span data-ttu-id="3d18b-137">[Créer un type de tâche de maintenance](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) ou sélectionner un type de tâche de maintenance existant.</span><span class="sxs-lookup"><span data-stu-id="3d18b-137">[Create a maintenance job type](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type), or select an existing maintenance job type.</span></span>
    1. <span data-ttu-id="3d18b-138">Dans le volet Actions, sélectionnez **Valeurs par défaut du type de tâche de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-138">On the Action Pane, select **Maintenance job type defaults**.</span></span>

        <span data-ttu-id="3d18b-139">![Bouton Valeurs par défaut du type de tâche de maintenance](media/am-guides-integration-job-defaults.png "Bouton Valeurs par défaut du type de tâche de maintenance")</span><span class="sxs-lookup"><span data-stu-id="3d18b-139">![Maintenance job type defaults button](media/am-guides-integration-job-defaults.png "Maintenance job type defaults button")</span></span>

    1. <span data-ttu-id="3d18b-140">Créez une ligne, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-140">Create a line, and then select **Save**.</span></span>

        <span data-ttu-id="3d18b-141">![Créer une ligne](media/am-guides-integration-add-line.png "Créer une ligne").</span><span class="sxs-lookup"><span data-stu-id="3d18b-141">![Create a line](media/am-guides-integration-add-line.png "Create a line")</span></span>

    1. <span data-ttu-id="3d18b-142">Dans le volet Actions, sélectionnez **Liste de contrôle de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-142">On the Action Pane, select **Maintenance checklist**.</span></span>

        <span data-ttu-id="3d18b-143">![Bouton Liste de contrôle de maintenance](media/am-guides-integration-maintenance-checklist.png "Bouton Liste de contrôle de maintenance")</span><span class="sxs-lookup"><span data-stu-id="3d18b-143">![Maintenance checklist button](media/am-guides-integration-maintenance-checklist.png "Maintenance checklist button")</span></span>

    1. <span data-ttu-id="3d18b-144">Dans le raccourci **Lignes de liste de contrôle de maintenance**, ajoutez une ligne, puis remplacez la valeur du champ **Type** par **Modèle**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-144">On the **Maintenance checklist lines** FastTab, add a line, and then change the value of the **Type** field to **Template**.</span></span>

        <span data-ttu-id="3d18b-145">![Changer la valeur Type](media/am-guides-integration-checklist-lines.png "Changer la valeur Type")</span><span class="sxs-lookup"><span data-stu-id="3d18b-145">![Change the Type value](media/am-guides-integration-checklist-lines.png "Change the Type value")</span></span>

    1. <span data-ttu-id="3d18b-146">Dans le raccourci **Détails de la ligne**, dans le champ **Modèle**, sélectionnez le modèle auquel vous avez associé le guide, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-146">On the **Line details** FastTab, in the **Template** field, select the template that you associated the guide with, and then select **Save**.</span></span>

        <span data-ttu-id="3d18b-147">![Sélectionner le modèle](media/am-guides-integration-checklist-line-details.png "Sélectionner le modèle")</span><span class="sxs-lookup"><span data-stu-id="3d18b-147">![Select the template](media/am-guides-integration-checklist-line-details.png "Select the template")</span></span>

1. <span data-ttu-id="3d18b-148">[Créez un bon de travail](work-orders/manually-created-workorders.md#create-work-order), puis sélectionnez le type de tâche de maintenance qui utilise le modèle de liste de contrôle de maintenance auquel vous avez associé le guide.</span><span class="sxs-lookup"><span data-stu-id="3d18b-148">[Create a work order](work-orders/manually-created-workorders.md#create-work-order), and then select the maintenance job type that uses the maintenance checklist template that you associated the guide with.</span></span> <span data-ttu-id="3d18b-149">Le guide est automatiquement associé à l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3d18b-149">The guide is automatically associated with the work order.</span></span>

    <span data-ttu-id="3d18b-150">![Sélectionner le type de tâche de maintenance](media/am-guides-integration-create-work-order.png "Sélectionner le type de tâche de maintenance")</span><span class="sxs-lookup"><span data-stu-id="3d18b-150">![Select a maintenance job type](media/am-guides-integration-create-work-order.png "Select a maintenance job type")</span></span>

1. <span data-ttu-id="3d18b-151">Affichez le guide qui est associé à l’ordre de travail et aux collaborateurs :</span><span class="sxs-lookup"><span data-stu-id="3d18b-151">View the guide that is associated with the work order and workers:</span></span>

    1. <span data-ttu-id="3d18b-152">Ouvrez l’[Espace de travail mobile de gestion des actifs](asset-management-mobile-workspace.md) pour accéder à l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3d18b-152">Open the [Asset management mobile workspace](asset-management-mobile-workspace.md) to access the work order.</span></span>
    1. <span data-ttu-id="3d18b-153">[Ouvrez la liste de contrôle de maintenance](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) pour l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3d18b-153">[Open the maintenance checklist](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) for the work order.</span></span>
    1. <span data-ttu-id="3d18b-154">Sélectionnez une ligne de liste de contrôle pour voir le guide associé.</span><span class="sxs-lookup"><span data-stu-id="3d18b-154">Select a checklist line to see the associated guide.</span></span>

        <span data-ttu-id="3d18b-155">![Guide associé à une ligne de liste de contrôle](media/am-guides-integration-show-guide.png "Guide associé à une ligne de liste de contrôle")</span><span class="sxs-lookup"><span data-stu-id="3d18b-155">![Guide associated with a checklist line](media/am-guides-integration-show-guide.png "Guide associated with a checklist line")</span></span>

    1. <span data-ttu-id="3d18b-156">Ouvrez le guide dans HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3d18b-156">Open the guide on HoloLens.</span></span>

        <span data-ttu-id="3d18b-157">![Ouvrer le guide dans HoloLens](media/am-guides-integration-hololens-select.png "Ouvrir le guide dans HoloLens")</span><span class="sxs-lookup"><span data-stu-id="3d18b-157">![Open the guide on HoloLens](media/am-guides-integration-hololens-select.png "Open the guide on HoloLens")</span></span>

> [!NOTE]
> <span data-ttu-id="3d18b-158">Vous pouvez également associer un guide directement dans la liste de contrôle de maintenance d’un ordre de travail ou d’un type de travail.</span><span class="sxs-lookup"><span data-stu-id="3d18b-158">You can also associate a guide directly in the maintenance checklist of a work order or a job type.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d18b-159">Il existe un problème connu où, lorsque vous associez un modèle de liste de contrôle de maintenance à un type de tâche de maintenance par défaut, le guide lié au modèle n’apparaît pas dans le raccourci **Guides associés** de la page **Valeurs par défaut du type de tâche de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-159">There is a known issue where, when you associate a maintenance checklist template with a default maintenance job type, the guide that is linked to the template doesn't appear on the **Associated guides** FastTab of the **Maintenance job type defaults** page.</span></span> <span data-ttu-id="3d18b-160">Cependant, le guide apparaîtra après que ce type de travail soit appliqué à un ordre de travail dans le raccourci **Guides associés**.</span><span class="sxs-lookup"><span data-stu-id="3d18b-160">However, the guide will appear after that job type is applied to a work order on the **Associated guides** FastTab.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d18b-161">Voir également :</span><span class="sxs-lookup"><span data-stu-id="3d18b-161">See also</span></span>

- [<span data-ttu-id="3d18b-162">Vue d’ensemble de la double écriture</span><span class="sxs-lookup"><span data-stu-id="3d18b-162">Dual-write overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [<span data-ttu-id="3d18b-163">Vue d’ensemble de la gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="3d18b-163">Asset management overview</span></span>](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]