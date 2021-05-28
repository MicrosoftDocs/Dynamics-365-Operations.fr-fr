---
title: Types de diagnostic pour les non-conformités
description: Cette rubrique décrit comment utiliser et créer des types de diagnostic pouvant être utilisés avec des non-conformités.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7a5c593f1d9e8f7a77f693f6e652e9355a985fb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022274"
---
# <a name="diagnostic-types-for-nonconformances"></a><span data-ttu-id="01ca8-103">Types de diagnostic pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="01ca8-103">Diagnostic types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="01ca8-104">Cette rubrique décrit comment utiliser et créer des types de diagnostic pouvant être utilisés avec des non-conformités.</span><span class="sxs-lookup"><span data-stu-id="01ca8-104">This topic describes how to use and create diagnostic types that can be used with nonconformances.</span></span>

<span data-ttu-id="01ca8-105">La page **Types de diagnostic** permet de définir une classification des actions de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="01ca8-105">You use the **Diagnostic types** page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="01ca8-106">Ensuite, lorsque vous créez une correction pour une non-conformité, vous devez sélectionner un diagnostic.</span><span class="sxs-lookup"><span data-stu-id="01ca8-106">Then, when you create a correction for a nonconformance, you select a diagnostic.</span></span> <span data-ttu-id="01ca8-107">Une correction spécifie le type d’action de diagnostic à prendre pour une non-conformité approuvée, ainsi que la personne qui doit exécuter cette action.</span><span class="sxs-lookup"><span data-stu-id="01ca8-107">A correction specifies what type of diagnostic action should be taken for an approved nonconformance, and who should take that action.</span></span> <span data-ttu-id="01ca8-108">Elle spécifie également la date de fin demandée et la date de fin prévue.</span><span class="sxs-lookup"><span data-stu-id="01ca8-108">It also specifies the requested completion date and the planned completion date.</span></span>

## <a name="examples-of-diagnostic-types"></a><span data-ttu-id="01ca8-109">Exemples de types de diagnostic</span><span class="sxs-lookup"><span data-stu-id="01ca8-109">Examples of diagnostic types</span></span>

<span data-ttu-id="01ca8-110">Vous travaillez pour une entreprise de fabrication et plusieurs articles ont échoué aux tests de qualité.</span><span class="sxs-lookup"><span data-stu-id="01ca8-110">You work for a manufacturing company, and several items have failed quality tests.</span></span> <span data-ttu-id="01ca8-111">Ces articles sont placés dans une zone de quarantaine et marqués comme produits non conformes.</span><span class="sxs-lookup"><span data-stu-id="01ca8-111">Those items are moved into a quarantine area and marked as nonconforming products.</span></span> <span data-ttu-id="01ca8-112">Un enregistrement de non-conformité est créé dans Microsoft Dynamics 365 Supply Chain Management pour suivre les détails grâce à la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="01ca8-112">A nonconformance record is created in Microsoft Dynamics 365 Supply Chain Management to track the details through issue resolution.</span></span>

<span data-ttu-id="01ca8-113">Dans ce cas, les problèmes de qualité se produisent parce que les roulements de la machine qui emballe les articles se sont détériorés et surchauffent.</span><span class="sxs-lookup"><span data-stu-id="01ca8-113">In this case, the quality issues are occurring because bearings in the machine that packages the items have gone bad and are overheating.</span></span> <span data-ttu-id="01ca8-114">Pour résoudre ce problème il faut remplacer les pièces de la machine.</span><span class="sxs-lookup"><span data-stu-id="01ca8-114">The correction for this problem is to replace the parts in the machine.</span></span>

<span data-ttu-id="01ca8-115">Lorsque vous configurez les types de diagnostic, vous pouvez créer plusieurs enregistrements, chacun représentant un type de problème différent que la machine peut rencontrer.</span><span class="sxs-lookup"><span data-stu-id="01ca8-115">When you configure the diagnostic types, you can create multiple records, each of which represents a different type of problem that the machine might have.</span></span> <span data-ttu-id="01ca8-116">Vous pouvez également créer un type de diagnostic générique qui représente la réparation de la machine.</span><span class="sxs-lookup"><span data-stu-id="01ca8-116">Alternatively, you can create one generic diagnostic type that represents machine repair.</span></span>

## <a name="create-a-diagnostic-type"></a><span data-ttu-id="01ca8-117">Créer un type de diagnostic</span><span class="sxs-lookup"><span data-stu-id="01ca8-117">Create a diagnostic type</span></span>

1. <span data-ttu-id="01ca8-118">Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Types de diagnostics**.</span><span class="sxs-lookup"><span data-stu-id="01ca8-118">Go to **Inventory management \> Setup \> Quality management \> Diagnostic types**.</span></span>
1. <span data-ttu-id="01ca8-119">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="01ca8-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="01ca8-120">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="01ca8-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="01ca8-121">**Diagnostic** – Entrez un identificateur ou un nom unique pour le type de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="01ca8-121">**Diagnostic** – Enter a unique ID or name for the diagnostic type.</span></span>
    - <span data-ttu-id="01ca8-122">**Description** - Entrez une description détaillée du type de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="01ca8-122">**Description** – Enter a detailed description of the diagnostic type.</span></span>

1. <span data-ttu-id="01ca8-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="01ca8-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="01ca8-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="01ca8-124">Additional resources</span></span>

- [<span data-ttu-id="01ca8-125">Vue d’ensemble de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="01ca8-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="01ca8-126">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="01ca8-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="01ca8-127">Collaborateurs chargés d'approuver les non-conformités</span><span class="sxs-lookup"><span data-stu-id="01ca8-127">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="01ca8-128">Zones de contrôle pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="01ca8-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="01ca8-129">Types de problème pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="01ca8-129">Problem types for nonconformances</span></span>](quality-problem-types.md)
- [<span data-ttu-id="01ca8-130">Frais de qualité pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="01ca8-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="01ca8-131">Opérations pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="01ca8-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="01ca8-132">Gestion de la qualité pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="01ca8-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
