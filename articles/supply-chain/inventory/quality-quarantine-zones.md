---
title: Zones de contrôle pour les non-conformités
description: Cette rubrique décrit comment créer et utiliser des zones de contrôle pour les non-conformités.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80f4b9dfc7882af4570bf1908784b8d114396402
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021802"
---
# <a name="quarantine-zones-for-nonconformances"></a><span data-ttu-id="55b9c-103">Zones de contrôle pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="55b9c-103">Quarantine zones for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55b9c-104">Cette rubrique décrit comment créer et utiliser des zones de contrôle pour les non-conformités.</span><span class="sxs-lookup"><span data-stu-id="55b9c-104">This topic describes how to create and use quarantine zones for nonconformances.</span></span>

<span data-ttu-id="55b9c-105">La page **Zones de contrôle** permet de définir les zones pouvant être affectées aux non-conformités.</span><span class="sxs-lookup"><span data-stu-id="55b9c-105">You use the **Quarantine zones** page to define zones that can be assigned to nonconformances.</span></span> <span data-ttu-id="55b9c-106">Lorsque vous créez une non-conformité, vous pouvez définir les champs **Zone de contrôle** et **Type de contrôle** sur l'onglet **Général** de la page **Non-conformités**.</span><span class="sxs-lookup"><span data-stu-id="55b9c-106">When you create a nonconformance, you can set the **Quarantine zone** and **Quarantine type** fields on the **General** tab of the **Non conformances** page.</span></span> <span data-ttu-id="55b9c-107">Le champ **Zone de contrôle** indique généralement la zone ou l'emplacement où se trouve l'élément.</span><span class="sxs-lookup"><span data-stu-id="55b9c-107">The **Quarantine zone** field typically indicates the area or location where the item is located.</span></span> <span data-ttu-id="55b9c-108">Le champ **Type de contrôle** définit l'élément comme *Utilisation limitée* ou *Inutilisable*.</span><span class="sxs-lookup"><span data-stu-id="55b9c-108">The **Quarantine type** field defines the item as either *Restricted usage* or *Unusable*.</span></span>

<span data-ttu-id="55b9c-109">Lorsque vous imprimez un rapport de non-conformité ou de corrections pour une non-conformité, vous pouvez afficher la zone de contrôle où se trouve l'élément.</span><span class="sxs-lookup"><span data-stu-id="55b9c-109">When you print a nonconformance or corrections report for a nonconformance, you can view the quarantine zone where the item is located.</span></span>

<span data-ttu-id="55b9c-110">Vous pouvez également imprimer une étiquette de non-conformité pour une non-conformité.</span><span class="sxs-lookup"><span data-stu-id="55b9c-110">You can also print a nonconformance tag for a nonconformance.</span></span> <span data-ttu-id="55b9c-111">Cet état indique la zone de quarantaine affectée et les informations relatives à l’utilisation, afin de fournir des instructions sur la gestion du matériel défectueux.</span><span class="sxs-lookup"><span data-stu-id="55b9c-111">This report shows the assigned quarantine zone and information about usage to provide guidance about how defective material should be handled.</span></span> <span data-ttu-id="55b9c-112">Les zones de contrôle peuvent correspondre à des emplacements de stockage ou à des ressources opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="55b9c-112">The quarantine zones might correspond to inventory locations or operations resources.</span></span>

## <a name="examples-of-quarantine-zones"></a><span data-ttu-id="55b9c-113">Exemples de zones de contrôle</span><span class="sxs-lookup"><span data-stu-id="55b9c-113">Examples of quarantine zones</span></span>

### <a name="example-1"></a><span data-ttu-id="55b9c-114">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="55b9c-114">Example 1</span></span>

<span data-ttu-id="55b9c-115">Vous travaillez dans une entreprise de fabrication de matériel électronique qui produit et distribue des téléviseurs, des haut-parleurs et des lecteurs multimédias.</span><span class="sxs-lookup"><span data-stu-id="55b9c-115">You work at an electronics manufacturing company that produces and distributes televisions, speakers, and media players.</span></span> <span data-ttu-id="55b9c-116">Dans ce cas, vous pouvez configurer une zone de contrôle pour représenter chaque type de produit.</span><span class="sxs-lookup"><span data-stu-id="55b9c-116">In this case, you can configure a quarantine zone to represent each type of product.</span></span>

### <a name="example-2"></a><span data-ttu-id="55b9c-117">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="55b9c-117">Example 2</span></span>

<span data-ttu-id="55b9c-118">Trois bacs et deux racks sont utilisés pour stocker les articles non conformes.</span><span class="sxs-lookup"><span data-stu-id="55b9c-118">Three bins and two racks are used to store items that are nonconforming.</span></span> <span data-ttu-id="55b9c-119">Dans ce cas, vous pouvez configurer cinq zones de contrôle, une pour chaque bac et chaque rack.</span><span class="sxs-lookup"><span data-stu-id="55b9c-119">In this case, you can configure five quarantine zones, one for each bin and each rack.</span></span>

## <a name="create-a-quarantine-zone"></a><span data-ttu-id="55b9c-120">Créer une zone de contrôle</span><span class="sxs-lookup"><span data-stu-id="55b9c-120">Create a quarantine zone</span></span>

1. <span data-ttu-id="55b9c-121">Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Zones de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="55b9c-121">Go to **Inventory management \> Setup \> Quality management \> Quarantine zones**.</span></span>
1. <span data-ttu-id="55b9c-122">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="55b9c-122">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="55b9c-123">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="55b9c-123">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="55b9c-124">**Zone de contrôle** - Entrez un ID ou un nom unique pour la zone de contrôle.</span><span class="sxs-lookup"><span data-stu-id="55b9c-124">**Quarantine zone** – Enter a unique ID or name for the quarantine zone.</span></span>
    - <span data-ttu-id="55b9c-125">**Description** - Entrez une description détaillée de la zone de contrôle.</span><span class="sxs-lookup"><span data-stu-id="55b9c-125">**Description** – Enter a detailed description of the quarantine zone.</span></span>

1. <span data-ttu-id="55b9c-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="55b9c-126">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="55b9c-127">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="55b9c-127">Additional resources</span></span>

- [<span data-ttu-id="55b9c-128">Vue d’ensemble de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="55b9c-128">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="55b9c-129">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="55b9c-129">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="55b9c-130">Collaborateurs chargés d'approuver les non-conformités</span><span class="sxs-lookup"><span data-stu-id="55b9c-130">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="55b9c-131">Types de problème pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="55b9c-131">Problem types for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="55b9c-132">Types de diagnostic pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="55b9c-132">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="55b9c-133">Frais de qualité pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="55b9c-133">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="55b9c-134">Opérations pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="55b9c-134">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="55b9c-135">Gestion de la qualité pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="55b9c-135">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
