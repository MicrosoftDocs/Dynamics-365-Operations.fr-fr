---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (août 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 08/27/2018
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
ms.search.validFrom: 2018-08-27
ms.dyn365.ops.version: Talent August 2018 update
ms.openlocfilehash: be76f29dc9d38cdf3c2d56120a830acae69937a4
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "857012"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-august-2018"></a><span data-ttu-id="b0160-103">Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (août 2018)</span><span class="sxs-lookup"><span data-stu-id="b0160-103">What's new or changed in Dynamics 365 for Talent Core HR (August 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b0160-104">**Version 8.1.104**</span><span class="sxs-lookup"><span data-stu-id="b0160-104">**Build 8.1.104**</span></span>

<span data-ttu-id="b0160-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="b0160-105">This topic describes features that are either new or changed in Dynamics 365 for Talent Core HR.</span></span>

## <a name="view-expiring-records-in-manager-self-service"></a><span data-ttu-id="b0160-106">Afficher les enregistrements arrivant à expiration dans Responsable en libre-service</span><span class="sxs-lookup"><span data-stu-id="b0160-106">View expiring records in Manager self service</span></span>

<span data-ttu-id="b0160-107">Vous pouvez maintenant afficher les enregistrements arrivant à expiration dans Responsable en libre-service.</span><span class="sxs-lookup"><span data-stu-id="b0160-107">You can now view expiring records in Manager self-service.</span></span> <span data-ttu-id="b0160-108">De nouvelles options vous permettent de configurer les informations qui seront visibles par les responsables.</span><span class="sxs-lookup"><span data-stu-id="b0160-108">New options are allow you to configure what information will be available for managers to view.</span></span> <span data-ttu-id="b0160-109">Ces valeurs sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="b0160-109">These include:</span></span>

-   <span data-ttu-id="b0160-110">Certificats</span><span class="sxs-lookup"><span data-stu-id="b0160-110">Certificates</span></span>

-   <span data-ttu-id="b0160-111">Numéros d'identifications</span><span class="sxs-lookup"><span data-stu-id="b0160-111">Identification numbers</span></span>

-   <span data-ttu-id="b0160-112">Périodes d'essai</span><span class="sxs-lookup"><span data-stu-id="b0160-112">Probation periods</span></span>

-   <span data-ttu-id="b0160-113">Filtrages</span><span class="sxs-lookup"><span data-stu-id="b0160-113">Screenings</span></span>

-   <span data-ttu-id="b0160-114">Tests</span><span class="sxs-lookup"><span data-stu-id="b0160-114">Tests</span></span>

<span data-ttu-id="b0160-115">Cette fonctionnalité vous offre également la possibilité de spécifier la plage de jours dans lesquels rechercher des enregistrements arrivant à expiration.</span><span class="sxs-lookup"><span data-stu-id="b0160-115">This feature also gives you the ability to specify the range of days in which to look for expiring records.</span></span>

## <a name="configurable-transfer-actions"></a><span data-ttu-id="b0160-116">Actions de transfert configurables</span><span class="sxs-lookup"><span data-stu-id="b0160-116">Configurable transfer actions</span></span>

<span data-ttu-id="b0160-117">Vous pouvez configurer par rôle les options qui seront disponibles lors de la saisie d'une demande de transfert.</span><span class="sxs-lookup"><span data-stu-id="b0160-117">You can configure by role the options that will be available during the entry of a transfer request.</span></span> <span data-ttu-id="b0160-118">Cette fonctionnalité offre une flexibilité supplémentaire pour les rôles d'une organisation.</span><span class="sxs-lookup"><span data-stu-id="b0160-118">This feature provides additional flexibility across the roles in an organization.</span></span>

<span data-ttu-id="b0160-119">Par exemple, les responsables qui demandent des transferts d'employé peuvent ne pas avoir accès pour suggérer ou entrer des montants de rémunération ou sélectionner les listes de tâches qui seront associées à la demande de transfert.</span><span class="sxs-lookup"><span data-stu-id="b0160-119">For example, managers requesting employee transfers may not have access to suggest or enter compensation amounts or select the task lists that will be associated with the transfer request.</span></span> <span data-ttu-id="b0160-120">Dans ce cas, les responsables peuvent créer et soumettre des demandes de transfert mais ne sont pas autorisés à entrer des rémunérations ou des affectations de liste de tâches.</span><span class="sxs-lookup"><span data-stu-id="b0160-120">In this case, managers can create and submit transfer requests but are not allowed to enter compensation or task list assignments.</span></span> <span data-ttu-id="b0160-121">Dans cette même configuration, les ressources humaines pourront affecter les nouvelles valeurs de rémunération ainsi que des listes de contrôle supplémentaires à effectuer à la suite de l'exécution du transfert.</span><span class="sxs-lookup"><span data-stu-id="b0160-121">In this same configuration, HR will be able to assign the new compensation values as well as assign any additional checklists to be completed as a result of the transfer completing.</span></span>

<span data-ttu-id="b0160-122">Par défaut, les nouvelles options de configuration sont définies pour ne pas modifier les fonctionnalités avant cette mise à jour.</span><span class="sxs-lookup"><span data-stu-id="b0160-122">By default, the new configuration options are set to not change the capabilities prior to this update.</span></span>

## <a name="leave-and-absence"></a><span data-ttu-id="b0160-123">Congé et absence</span><span class="sxs-lookup"><span data-stu-id="b0160-123">Leave and absence</span></span>

<span data-ttu-id="b0160-124">Des champs de date supplémentaires sont maintenant disponibles dans Congé et absence.</span><span class="sxs-lookup"><span data-stu-id="b0160-124">There are now additional Date fields available in Leave and Absence.</span></span>

<span data-ttu-id="b0160-125">Cette fonctionnalité vous permet de définir la base de la période de régularisation au niveau du plan pour utiliser des dates spécifiques à l'employé.</span><span class="sxs-lookup"><span data-stu-id="b0160-125">With this feature you can set the accrual period basis at the plan level to use specific employee dates.</span></span> <span data-ttu-id="b0160-126">Cela permet d'utiliser des dates différentes de la date de début du plan pendant le processus de régularisation des congés.</span><span class="sxs-lookup"><span data-stu-id="b0160-126">This allows for dates other than the plan start date to be used during the leave accrual process.</span></span> <span data-ttu-id="b0160-127">Les options pour les dates spécifiques à l'employé incluent les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b0160-127">Options for employee specific dates include the following values:</span></span>

-   <span data-ttu-id="b0160-128">Personnalisé (disponible avant cette mise à jour)</span><span class="sxs-lookup"><span data-stu-id="b0160-128">Custom (available prior to this update)</span></span>

-   <span data-ttu-id="b0160-129">Date anniversaire</span><span class="sxs-lookup"><span data-stu-id="b0160-129">Anniversary date</span></span>

-   <span data-ttu-id="b0160-130">Date d'embauche d'origine</span><span class="sxs-lookup"><span data-stu-id="b0160-130">Original hire date</span></span>

-   <span data-ttu-id="b0160-131">Date d'ancienneté</span><span class="sxs-lookup"><span data-stu-id="b0160-131">Seniority date</span></span>

-   <span data-ttu-id="b0160-132">Date de début ajustée du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b0160-132">Worker’s adjusted start date</span></span>

-   <span data-ttu-id="b0160-133">Date de début du collaborateur</span><span class="sxs-lookup"><span data-stu-id="b0160-133">Worker’s start date</span></span>

<span data-ttu-id="b0160-134">Lorsque qu'il est configuré pour utiliser l'une des dates spécifiques à l'employé, le processus d'inscription utilisera la date spécifiée pour calculer les périodes de régularisation.</span><span class="sxs-lookup"><span data-stu-id="b0160-134">When configured to use one of the employee specific dates, the enrollment process will use the specified date to calculate the accrual periods.</span></span> <span data-ttu-id="b0160-135">La base de la période de régularisation est également affichée dans l'inscription de l'employé à un plan pour vous aider à comprendre ce qui est utilisé lors du processus de régularisation.</span><span class="sxs-lookup"><span data-stu-id="b0160-135">The accrual period basis is also displayed on the employee’s plan enrollment to help you understand what’s being used during the accrual process.</span></span>

## <a name="microsoft-word-integration"></a><span data-ttu-id="b0160-136">Intégration à Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="b0160-136">Microsoft Word integration</span></span>

<span data-ttu-id="b0160-137">Les modèles de document ont été activés via Core HR.</span><span class="sxs-lookup"><span data-stu-id="b0160-137">Document templates have been enabled throughout Core HR.</span></span> <span data-ttu-id="b0160-138">Cette fonctionnalité vous permet de créer des lettres et des états basés sur les modèles Word que vous créez.</span><span class="sxs-lookup"><span data-stu-id="b0160-138">This feature allows you to create letters and reports based on Word templates that you create.</span></span>

<span data-ttu-id="b0160-139">Des informations supplémentaires sur cette fonctionnalité sont disponibles dans le [Didacticiel pour l'intégration Office](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).</span><span class="sxs-lookup"><span data-stu-id="b0160-139">Additional information about this feature is available in the [Office integration tutorial](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).</span></span>


## <a name="other-fixes"></a><span data-ttu-id="b0160-140">Autres correctifs</span><span class="sxs-lookup"><span data-stu-id="b0160-140">Other fixes</span></span>

<span data-ttu-id="b0160-141">Cette version inclut également plusieurs correctifs de bogue, l'ajout de nouvelles entités, des correctifs aux entités existantes et des modifications d'étiquette localisées.</span><span class="sxs-lookup"><span data-stu-id="b0160-141">This release also includes a number of bug fixes, the addition of new entities, fixes to existing entities, and localized label changes.</span></span>
