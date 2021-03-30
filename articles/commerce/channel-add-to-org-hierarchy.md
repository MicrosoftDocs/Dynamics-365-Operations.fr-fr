---
title: Ajouter un canal à une hiérarchie d'organisation
description: Cette rubrique décrit comment ajouter un canal à une hiérarchie d’organisation dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 4212797d2959c4f8b0d60e6b45de76ffc3ee0dc2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216748"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a><span data-ttu-id="ce57a-103">Ajouter un canal à une hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="ce57a-103">Add a channel to an organizational hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ce57a-104">Cette rubrique décrit comment ajouter un canal à une hiérarchie d’organisation dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ce57a-104">This topic describes how to add a channel to an organizational hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ce57a-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="ce57a-105">Overview</span></span>

<span data-ttu-id="ce57a-106">Les canaux doivent être associés à une ou plusieurs hiérarchies d'organisation.</span><span class="sxs-lookup"><span data-stu-id="ce57a-106">Channels need to be associated with one or more organizational hierarchies.</span></span> <span data-ttu-id="ce57a-107">Avant de créer des canaux, vous devez confirmer que vos hiérarchies d'organisation ont été configurées.</span><span class="sxs-lookup"><span data-stu-id="ce57a-107">Before creating channels, you need to confirm that your organizational hierarchies have been set up.</span></span>  

<span data-ttu-id="ce57a-108">Voir [Hiérarchies d'organisation](channels-org-hierarchies.md) pour plus de détails sur la création de hiérarchies d'organisation.</span><span class="sxs-lookup"><span data-stu-id="ce57a-108">See [Organizational hierarchies](channels-org-hierarchies.md) for more details on how to create organizational hierarchies.</span></span>

## <a name="select-a-hierarchy"></a><span data-ttu-id="ce57a-109">Sélectionner une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="ce57a-109">Select a hierarchy</span></span>

<span data-ttu-id="ce57a-110">Pour sélectionner une hiérarchie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ce57a-110">To select a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="ce57a-111">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Hiérarchies d'organisation**.</span><span class="sxs-lookup"><span data-stu-id="ce57a-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="ce57a-112">Dans la liste, sélectionnez la hiérarchie d'organisation à laquelle vous allez ajouter le canal.</span><span class="sxs-lookup"><span data-stu-id="ce57a-112">From the list, select the organization hierarchy that you'll be adding the channel to.</span></span>
1. <span data-ttu-id="ce57a-113">Dans le volet Actions, sélectionnez **Afficher** pour afficher les détails de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="ce57a-113">On the action pane, select **View** to view hierarchy details.</span></span>

<span data-ttu-id="ce57a-114">L'image suivante montre les détails de la hiérarchie d'organisation pour la hiérarchie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ce57a-114">The following image shows organizational hierarchy details for the selected hierarchy.</span></span>

![Détails de la hiérarchie d'organisation pour la hiérarchie sélectionnée](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a><span data-ttu-id="ce57a-116">Ajouter un canal à un nœud de hiérarchie</span><span class="sxs-lookup"><span data-stu-id="ce57a-116">Add a channel to a hierachy node</span></span>

<span data-ttu-id="ce57a-117">Pour ajouter un canal à un nœud de hiérarchie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ce57a-117">To add a channel to a hierachy node, follow these steps.</span></span>

1. <span data-ttu-id="ce57a-118">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ce57a-118">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="ce57a-119">Sélectionnez le nœud de hiérarchie auquel vous souhaitez ajouter le canal, puis dans la liste déroulante **Insérer**, sélectionnez **Canal de vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="ce57a-119">Select the hierachy node you want the channel added to, then from the **Insert** drop-down list, select **Retail Channel**.</span></span> 
1. <span data-ttu-id="ce57a-120">Sélectionnez le canal à ajouter, puis le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce57a-120">Select the channel to add, then select the **OK** button.</span></span>
1. <span data-ttu-id="ce57a-121">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce57a-121">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="ce57a-122">Dans le volet Actions, sélectionnez **Publier** et fournissez une **Date d'effet** dans le passé pour que cette action entre en vigueur immédiatement.</span><span class="sxs-lookup"><span data-stu-id="ce57a-122">On the action pane, select **Publish** and provide an **Effective date** in the past to have this action go into effect immediately.</span></span>

<span data-ttu-id="ce57a-123">L'image suivante montre comment sélectionner un canal à ajouter à un nœud de hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="ce57a-123">The following image shows how to select a channel to add to a hierarchy node.</span></span>

![Sélectionner un canal à ajouter à un nœud de hiérarchie](media/channel-add-to-org-hierarchy-2.png)

<span data-ttu-id="ce57a-125">L'image suivante montre une hiérarchie avec plusieurs canaux ajoutés.</span><span class="sxs-lookup"><span data-stu-id="ce57a-125">The following image shows a hierarchy with various channels added.</span></span>

![Une hiérarchie avec plusieurs canaux ajoutés](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="ce57a-127">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ce57a-127">Additional resources</span></span>

[<span data-ttu-id="ce57a-128">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="ce57a-128">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="ce57a-129">Configuration requise pour le paramétrage de canaux</span><span class="sxs-lookup"><span data-stu-id="ce57a-129">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="ce57a-130">Vue d'ensemble des organisations et des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="ce57a-130">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="ce57a-131">Planifier votre hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="ce57a-131">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="ce57a-132">Hiérarchies de l'organisation</span><span class="sxs-lookup"><span data-stu-id="ce57a-132">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="ce57a-133">Paramétrer un canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="ce57a-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="ce57a-134">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="ce57a-134">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]