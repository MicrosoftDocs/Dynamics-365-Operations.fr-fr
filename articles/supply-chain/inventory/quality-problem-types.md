---
title: Types de problème pour les non-conformités
description: Cette rubrique décrit comment créer et utiliser les types de problème pour les non-conformités.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df509365f5c900898921acfbda380b5e20c7a251
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956659"
---
# <a name="problem-types-for-nonconformances"></a><span data-ttu-id="3acab-103">Types de problème pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="3acab-103">Problem types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3acab-104">Cette rubrique décrit comment créer et utiliser les types de problème pour les non-conformités.</span><span class="sxs-lookup"><span data-stu-id="3acab-104">This topic describes how to create and use problem types for nonconformances.</span></span>

<span data-ttu-id="3acab-105">La page **Types de problème** permet de définir une classification des problèmes de qualité susceptibles de se produire pour les divers types de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="3acab-105">You use the **Problem types** page to define a classification of the quality problems that might occur for the various nonconformance types.</span></span> <span data-ttu-id="3acab-106">Pour chaque type de problème que vous créez, vous devez spécifier les types de non-conformité avec lesquels le type de problème peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="3acab-106">For each problem type that you create, you must specify the types of nonconformances that the problem type can be used with.</span></span> <span data-ttu-id="3acab-107">Vous pouvez paramétrer les types de non-conformité suivants :</span><span class="sxs-lookup"><span data-stu-id="3acab-107">You can set up the following nonconformance types:</span></span>

- <span data-ttu-id="3acab-108">**Interne** - Les non-conformités de ce type sont liées aux stocks disponibles (par exemple, les ordres de qualité ou les ordres de contrôle).</span><span class="sxs-lookup"><span data-stu-id="3acab-108">**Internal** – Nonconformances of this type are related to on-hand inventory (for example, quality orders or quarantine orders).</span></span>
- <span data-ttu-id="3acab-109">**Client** - Les non-conformités de ce type sont liées aux commandes clients.</span><span class="sxs-lookup"><span data-stu-id="3acab-109">**Customer** – Nonconformances of this type are related to sales orders.</span></span>
- <span data-ttu-id="3acab-110">**Fournisseur** - Les non-conformités de ce type sont liées aux commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3acab-110">**Vendor** – Nonconformances of this type are related to purchase orders.</span></span>
- <span data-ttu-id="3acab-111">**Demande de service** - Les non-conformités de ce type sont liées aux commandes de service.</span><span class="sxs-lookup"><span data-stu-id="3acab-111">**Service request** – Nonconformances of this type are related to service orders.</span></span>
- <span data-ttu-id="3acab-112">**Production** – Les non-conformités de ce type sont liées aux lots de commande ou aux ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="3acab-112">**Production** – Nonconformances of this type are related to batch orders or production orders.</span></span>
- <span data-ttu-id="3acab-113">**Production de coproduits** – Les non-conformités de ce type sont liées aux lots de commande pour des coproduits.</span><span class="sxs-lookup"><span data-stu-id="3acab-113">**Co-product production** – Nonconformances of this type are related to batch orders for co-products.</span></span>

<span data-ttu-id="3acab-114">Lorsque vous créez un nouveau type de problème, sélectionnez **Types de non-conformité** dans le volet Actions pour créer une liste d'un ou plusieurs types de non-conformité autorisés pour le type de problème.</span><span class="sxs-lookup"><span data-stu-id="3acab-114">When you create a new problem type, select **Non conformance types** on the Action Pane to create a list of one or more nonconformance types that are authorized for the problem type.</span></span> <span data-ttu-id="3acab-115">Par exemple, un type de problème en lien avec un code défaut peut s'appliquer à tous les types de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="3acab-115">For example, a problem type that is related to a defect code might apply to all nonconformance types.</span></span> <span data-ttu-id="3acab-116">Cependant, un type de problème lié aux réclamations des clients peut s'appliquer uniquement aux types de non-conformité **Client** et **Demande de service**.</span><span class="sxs-lookup"><span data-stu-id="3acab-116">However, a problem type that is related to customer complaints might apply only to the **Customer** and **Service request** nonconformance types.</span></span>

## <a name="examples-of-problem-types"></a><span data-ttu-id="3acab-117">Exemples de types de problème</span><span class="sxs-lookup"><span data-stu-id="3acab-117">Examples of problem types</span></span>

<span data-ttu-id="3acab-118">Voici quelques exemples de scénarios de types de problème pouvant être utilisés avec les différents types de non-conformité :</span><span class="sxs-lookup"><span data-stu-id="3acab-118">Here are some examples of scenarios for problem types that can be used with the different nonconformance types:</span></span>

- <span data-ttu-id="3acab-119">**Client :** Un client a déposé une plainte, un client a effectué un retour ou des spécifications de qualité n'ont pas été respectées.</span><span class="sxs-lookup"><span data-stu-id="3acab-119">**Customer:** A customer filed a complaint, a customer made a return, or quality specifications weren't met.</span></span>
- <span data-ttu-id="3acab-120">**Fournisseur :** Le produit a été endommagé, les spécifications de qualité n'ont pas été respectées ou le mauvais produit a été reçu.</span><span class="sxs-lookup"><span data-stu-id="3acab-120">**Vendor:** The product was damaged, quality specifications weren't met, or the wrong product was received.</span></span>
- <span data-ttu-id="3acab-121">**Demande de service :** Les spécifications de qualité n'ont pas été respectées, un client a déposé une plainte ou une maintenance de la machine est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3acab-121">**Service request:** Quality specifications weren't met, a customer filed a complaint, or machine maintenance is required.</span></span>
- <span data-ttu-id="3acab-122">**Production :** Les spécifications de qualité n'ont pas été respectées, un entretien de la machine est nécessaire ou le produit a été endommagé.</span><span class="sxs-lookup"><span data-stu-id="3acab-122">**Production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>
- <span data-ttu-id="3acab-123">**Production de coproduits :** Les spécifications de qualité n'ont pas été respectées, un entretien de la machine est nécessaire ou le produit a été endommagé.</span><span class="sxs-lookup"><span data-stu-id="3acab-123">**Co-product production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a><span data-ttu-id="3acab-124">Créer un type de problème et l'affecter à des types de non-conformité</span><span class="sxs-lookup"><span data-stu-id="3acab-124">Create a problem type and assign it to nonconformance types</span></span>

1. <span data-ttu-id="3acab-125">Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Types de problème**.</span><span class="sxs-lookup"><span data-stu-id="3acab-125">Go to **Inventory management \> Setup \> Quality management \> Problem types**.</span></span>
1. <span data-ttu-id="3acab-126">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="3acab-126">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="3acab-127">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="3acab-127">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="3acab-128">**Type de problème** – Entrez un identificateur ou un nom unique pour le type de problème.</span><span class="sxs-lookup"><span data-stu-id="3acab-128">**Problem type** – Enter a unique ID or name for the problem type.</span></span>
    - <span data-ttu-id="3acab-129">**Description** - Entrez une description détaillée du type de problème.</span><span class="sxs-lookup"><span data-stu-id="3acab-129">**Description** – Enter a detailed description of the problem type.</span></span>

1. <span data-ttu-id="3acab-130">Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Types de non-conformité** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="3acab-130">While the new row is still selected, select **Non conformance types** on the Action Pane.</span></span>
1. <span data-ttu-id="3acab-131">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="3acab-131">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="3acab-132">Ensuite, pour la nouvelle ligne, définissez le champ **Type de non-conformité** sur le type de non-conformité que vous souhaitez autoriser pour le type de problème.</span><span class="sxs-lookup"><span data-stu-id="3acab-132">Then, for the new row, set the **Non conformance type** field to the nonconformance type that you want to allow for the problem type.</span></span>
1. <span data-ttu-id="3acab-133">Répétez l'étape précédente pour chaque type de non-conformité supplémentaire que vous souhaitez autoriser pour le type de problème.</span><span class="sxs-lookup"><span data-stu-id="3acab-133">Repeat the previous step for each additional nonconformance type that you want to authorize for the problem type.</span></span>
1. <span data-ttu-id="3acab-134">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="3acab-134">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3acab-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3acab-135">Additional resources</span></span>

- [<span data-ttu-id="3acab-136">Vue d’ensemble de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="3acab-136">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="3acab-137">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="3acab-137">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="3acab-138">Collaborateurs chargés d'approuver les non-conformités</span><span class="sxs-lookup"><span data-stu-id="3acab-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="3acab-139">Zones de contrôle pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="3acab-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="3acab-140">Types de diagnostic pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="3acab-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="3acab-141">Frais de qualité pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="3acab-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="3acab-142">Opérations pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="3acab-142">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="3acab-143">Gestion de la qualité pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="3acab-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
