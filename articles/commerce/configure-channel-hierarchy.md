---
title: Configurer un canal pour une utiliser une hiérarchie de navigation du canal
description: Cette rubrique décrit comment configurer un canal pour utiliser une hiérarchie de navigation de canal dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7b5041d35d310125c314ab2cb77d3cc40cdb7113
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412172"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a><span data-ttu-id="1b5d1-103">Configurer un canal pour une utiliser une hiérarchie de navigation du canal</span><span class="sxs-lookup"><span data-stu-id="1b5d1-103">Configure a channel to use a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="1b5d1-104">Cette rubrique décrit comment configurer un canal pour utiliser une hiérarchie de navigation de canal dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-104">This topic describes how to configure a channel to use a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1b5d1-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="1b5d1-105">Overview</span></span>

<span data-ttu-id="1b5d1-106">Les hiérarchies de navigation de canal organisent les produits en catégories afin de pouvoir les parcourir dans un site de commerce électronique ou dans des points de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="1b5d1-106">Channel navigation hierarchies organize products into categories so that the products can be browsed on an e-Commerce site or at points of sale (POS).</span></span> <span data-ttu-id="1b5d1-107">Les canaux de vente au détail et en ligne doivent être configurés avec des hiérarchies de navigation des canaux.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-107">Retail and online channels must be configured with channel navigation hierarchies.</span></span>

## <a name="configure-the-channel"></a><span data-ttu-id="1b5d1-108">Configurer le canal</span><span class="sxs-lookup"><span data-stu-id="1b5d1-108">Configure the channel</span></span>

<span data-ttu-id="1b5d1-109">Pour configurer un canal afin d'utiliser une hiérarchie de navigation de canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-109">To configure a channel to use a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="1b5d1-110">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-110">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="1b5d1-111">Sélectionnez le canal à configurer.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-111">Select the channel to configure.</span></span>
1. <span data-ttu-id="1b5d1-112">Sur le volet Actions, sélectionnez **Paramétrer les métadonnées d'attribut**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-112">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="1b5d1-113">Dans la liste déroulante **Hiérarchie de catégories**, sélectionnez la hiérarchie de navigation de canal adéquate.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-113">In the **Category hierarchy** drop-down list, select the appropriate channel navigation hierarchy.</span></span>
1. <span data-ttu-id="1b5d1-114">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-114">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="1b5d1-115">Sous **Groupe d'attributs**, ajoutez tous les groupes d'attributs qui seront des attributs globaux pour tous les nœuds.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-115">Under **Attribute group**, add any attribute groups that will be global attributes for all nodes.</span></span>

<span data-ttu-id="1b5d1-116">L'image suivante montre comment configurer un canal afin d'utiliser une hiérarchie de navigation de canal.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-116">The following image shows how to configure a channel to use a channel navigation hierarchy.</span></span>

![Exemple de configuration de canal](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a><span data-ttu-id="1b5d1-118">Paramétrer les métadonnées d'attribut</span><span class="sxs-lookup"><span data-stu-id="1b5d1-118">Set attribute metadata</span></span>

<span data-ttu-id="1b5d1-119">La définition des métadonnées d'attribut permettra la configuration des attributs sur chaque nœud.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-119">Setting the attribute metadata will allow configuration of attributes on each node.</span></span>

<span data-ttu-id="1b5d1-120">Procédez comme suit pour configurer les métadonnées d'attributs.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-120">To set attribute metadata, follow these steps.</span></span>

1. <span data-ttu-id="1b5d1-121">Sur le volet Actions, sélectionnez **Paramétrer les métadonnées d'attribut**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-121">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="1b5d1-122">Pour chaque nœud, sélectionnez **Attributs de produit de canal**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-122">For each node select **Channel product attributes**.</span></span>
1. <span data-ttu-id="1b5d1-123">Définissez **Afficher l'attribut sur le canal** sur **Oui** et **Peut être affiné** sur **Oui**, pour activer des affinements sur ce canal.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-123">Set **Show attribute on channel** to **Yes** and **Can be refined** to **Yes**, to enable refiners on that channel.</span></span>
1. <span data-ttu-id="1b5d1-124">Après avoir configuré chaque nœud comme vous le souhaitez, dans le **Volet Actions**, sélectionnez le bouton **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-124">After configuring each node as desired, on the **Action pane**, select the **Save** button to save.</span></span>
1. <span data-ttu-id="1b5d1-125">Sélectionnez la **X** dans le coin supérieur droit pour quitter cet écran et revenir à la page **Catégories de canal et attributs de produit**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-125">Select the **X** in the top right corner to exit this screen back to the **Channel categories and product attributes** page.</span></span>

<span data-ttu-id="1b5d1-126">L'image suivante montre un exemple d'ensemble d'attributs de produit de canal configuré sur un nœud de catégorie de canal.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-126">The following image shows an example set of channel product attributes configured on a channel category node.</span></span>

![Attributs de canal sur un nœud de catégorie de canal](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a><span data-ttu-id="1b5d1-128">Publier des modifications</span><span class="sxs-lookup"><span data-stu-id="1b5d1-128">Publish changes</span></span>

<span data-ttu-id="1b5d1-129">Pour que les modifications prennent effet, vous devrez publier les modifications.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-129">For changes to take effect, you will need to publish the changes.</span></span>

<span data-ttu-id="1b5d1-130">Pour publier des modifications, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-130">To publish changes, follow these steps.</span></span>

1. <span data-ttu-id="1b5d1-131">Dans le volet Actions, sélectionnez **Publier les mises à jour du canal**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-131">On the action pane, select **Publish channel updates**.</span></span>
1. <span data-ttu-id="1b5d1-132">Dans le volet **Publier les mises à jour du canal**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-132">In the **Publish channel updates** pane, select **OK**.</span></span>

<span data-ttu-id="1b5d1-133">L'image suivante montre comment publier les mises à jour du canal.</span><span class="sxs-lookup"><span data-stu-id="1b5d1-133">The following image shows how to publish channel updates.</span></span>

![Publier les mises à jour du canal](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="1b5d1-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1b5d1-135">Additional resources</span></span>

[<span data-ttu-id="1b5d1-136">Créer une hiérarchie de navigation du canal</span><span class="sxs-lookup"><span data-stu-id="1b5d1-136">Create a channel navigation hierarchy</span></span>](create-channel-hierarchy.md)


