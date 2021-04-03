---
title: Configurer des hiérarchies d'organisation
description: Cette rubrique décrit comment configurer des hiérarchies d’organisation dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 490d466c10cfe0640f8fbcf8fe2298536e499d9b
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477994"
---
# <a name="set-up-organization-hierarchies"></a><span data-ttu-id="478ee-103">Configurer des hiérarchies d’organisation</span><span class="sxs-lookup"><span data-stu-id="478ee-103">Set up organization hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="478ee-104">Cette rubrique décrit comment configurer des hiérarchies d’organisation dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="478ee-104">This topic describes how to set up organization hierarchies in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="478ee-105">Avant de créer des canaux, vous voudrez vous assurer d'avoir configuré vos hiérarchies d'organisation.</span><span class="sxs-lookup"><span data-stu-id="478ee-105">Before creating channels, you'll want to ensure you have set up your organization hierarchies.</span></span>

<span data-ttu-id="478ee-106">Les hiérarchies d'organisation vous permettent d'afficher et de créer des états relatifs à votre entreprise à partir de perspectives différentes.</span><span class="sxs-lookup"><span data-stu-id="478ee-106">You can use organization hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="478ee-107">Par exemple, vous pouvez paramétrer une hiérarchie pour les déclarations légales ou fiscales.</span><span class="sxs-lookup"><span data-stu-id="478ee-107">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="478ee-108">Vous pouvez ensuite paramétrer une autre hiérarchie pour déclarer des informations financières qui ne sont pas requises par la loi, mais qui sont utilisées à des fins de déclaration interne.</span><span class="sxs-lookup"><span data-stu-id="478ee-108">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span>

<span data-ttu-id="478ee-109">Vous devez créer des organisations avant de créer une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="478ee-109">Before you create an organization hierarchy, you must create organizations.</span></span> <span data-ttu-id="478ee-110">Pour plus d'informations, voir [Créer des entités juridiques](channels-legal-entities.md) ou [Créer des unités opérationnelles](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="478ee-110">For more information, see [Create legal entities](channels-legal-entities.md) or [Create operating units](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span></span>


<span data-ttu-id="478ee-111">Pour plus d'informations, voir les rubriques suivantes.</span><span class="sxs-lookup"><span data-stu-id="478ee-111">For more information, see the following topics.</span></span>
- [<span data-ttu-id="478ee-112">Vue d'ensemble des organisations et des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="478ee-112">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="478ee-113">Planifier votre hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="478ee-113">Plan your organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="478ee-114">Créer une hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="478ee-114">Create an organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a><span data-ttu-id="478ee-115">Créer une hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="478ee-115">Create an organizational hierarchy</span></span>

<span data-ttu-id="478ee-116">Procédez comme suit pour créer une hiérarchie organisationnelle.</span><span class="sxs-lookup"><span data-stu-id="478ee-116">To create an organizational hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="478ee-117">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Hiérarchies d'organisation**.</span><span class="sxs-lookup"><span data-stu-id="478ee-117">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="478ee-118">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="478ee-118">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="478ee-119">Dans le champ **Nom**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="478ee-119">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="478ee-120">Dans la section **Objectif**, sélectionnez **Affecter un objectif**.</span><span class="sxs-lookup"><span data-stu-id="478ee-120">In the **Purpose** section, select **Assign purpose**.</span></span>
1. <span data-ttu-id="478ee-121">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="478ee-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="478ee-122">Sélectionnez un objet à affecter à la hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="478ee-122">Select a purpose to assign to your organization hierarchy.</span></span>
1. <span data-ttu-id="478ee-123">Dans le section **Hiérarchies affectées**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="478ee-123">In the **Assigned hierarchies** section, select **Add**.</span></span>
1. <span data-ttu-id="478ee-124">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="478ee-124">In the list, mark the selected row.</span></span> <span data-ttu-id="478ee-125">Recherchez la hiérarchie que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="478ee-125">Find the hierarchy you just created.</span></span>
1. <span data-ttu-id="478ee-126">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="478ee-126">Select **OK**.</span></span>

<span data-ttu-id="478ee-127">L'image suivante montre un exemple de hiérarchie organisationnelle créée pour un ensemble fictif de magasins « Adventure Works ».</span><span class="sxs-lookup"><span data-stu-id="478ee-127">The following image shows an example organizational hierarchy created for a fictitious "Adventure Works" set of stores.</span></span>

![Exemple de hiérarchie organisationnelle](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a><span data-ttu-id="478ee-129">Ajout d'organisations à une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="478ee-129">Add organizations to a hierarchy</span></span>

<span data-ttu-id="478ee-130">Pour ajouter des organisations à une hiérarchie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="478ee-130">To add organizations to a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="478ee-131">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="478ee-131">In the list, find and select the desired record.</span></span> <span data-ttu-id="478ee-132">Sélectionnez votre hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="478ee-132">Select your hierarchy.</span></span>
1. <span data-ttu-id="478ee-133">Dans le volet Actions, sélectionnez **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="478ee-133">On the action pane, select **View**.</span></span>
1. <span data-ttu-id="478ee-134">Ajoutez des organisations, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="478ee-134">Add organizations, as necessary.</span></span>
1. <span data-ttu-id="478ee-135">Pour ajouter une organisation, sélectionnez **Éditer** puis **Insérer**.</span><span class="sxs-lookup"><span data-stu-id="478ee-135">To add an organization, select **Edit** and then select **Insert**.</span></span> <span data-ttu-id="478ee-136">Lorsque vous avez apporté les modifications, vous pouvez enregistrer un brouillon et publier les modifications.</span><span class="sxs-lookup"><span data-stu-id="478ee-136">When you are done making changes you can save a draft and publish the changes.</span></span>

<span data-ttu-id="478ee-137">L'image suivante montre une entité juridique ajoutée à la racine de la hiérarchie avec quatre centres de coûts ajoutés pour les canaux « Mall », « Outlet », « Online » et « Call Center ».</span><span class="sxs-lookup"><span data-stu-id="478ee-137">The following image shows a legal entity added at the hierarchy root with four cost centers added for "Mall", "Outlet", "Online" and "Call Center" channels.</span></span> <span data-ttu-id="478ee-138">Divers canaux de vente au détail, de centres d'appels et en ligne peuvent ensuite être ajoutés à chacun.</span><span class="sxs-lookup"><span data-stu-id="478ee-138">Various retail, call center and online channels can then be added to each.</span></span>

![Exemple de concepteur de hiérarchies](media/hierarchy-designer.png)

## <a name="additional-resources"></a><span data-ttu-id="478ee-140">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="478ee-140">Additional resources</span></span>

[<span data-ttu-id="478ee-141">Vue d'ensemble des organisations et des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="478ee-141">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="478ee-142">Planifier votre hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="478ee-142">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="478ee-143">Créer des entités juridiques</span><span class="sxs-lookup"><span data-stu-id="478ee-143">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="478ee-144">Créer des unités opérationnelles</span><span class="sxs-lookup"><span data-stu-id="478ee-144">Create operating units</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="478ee-145">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="478ee-145">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="478ee-146">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="478ee-146">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
