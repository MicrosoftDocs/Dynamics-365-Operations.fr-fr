---
title: Frais pour les opérations de non-conformité
description: Cette rubrique décrit comment créer des frais de qualité pouvant être utilisés avec des opérations de non-conformité.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dfa424e94048aa9eb1ce4da9aa69e8d4df71cefb
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956652"
---
# <a name="charges-for-nonconformance-operations"></a><span data-ttu-id="10234-103">Frais pour les opérations de non-conformité</span><span class="sxs-lookup"><span data-stu-id="10234-103">Charges for nonconformance operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="10234-104">Cette rubrique décrit comment créer des frais de qualité pouvant être utilisés avec des opérations de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="10234-104">This topic describes how to create quality charges that can be used with operations for a nonconformance.</span></span>

<span data-ttu-id="10234-105">La page **Frais de qualité** permet de définir les types de frais qui peuvent être ajoutés aux opérations de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="10234-105">You use the **Quality charges** page to define the types of charges that can be added to operations for a nonconformance.</span></span> <span data-ttu-id="10234-106">Les frais vous permettent de suivre les détails à propos des frais ou des charges que vous devez à un client pour des produits non conformes, ou qu'un fournisseur vous doit pour des produits non conformes que vous avez reçus.</span><span class="sxs-lookup"><span data-stu-id="10234-106">Charges let you track details about fees or charges that you owe to a customer for nonconforming products, or that a vendor owes to you for nonconforming products that you received.</span></span> <span data-ttu-id="10234-107">Vous pouvez également utiliser des frais pour suivre les coûts nécessaires pour les fournisseurs ou les services externes pour effectuer une opération.</span><span class="sxs-lookup"><span data-stu-id="10234-107">You might also use charges to track costs that are required for external vendors or services to perform an operation.</span></span>

## <a name="examples-of-quality-charges"></a><span data-ttu-id="10234-108">Exemples de frais de qualité</span><span class="sxs-lookup"><span data-stu-id="10234-108">Examples of quality charges</span></span>

<span data-ttu-id="10234-109">Vous travaillez pour une entreprise de fabrication.</span><span class="sxs-lookup"><span data-stu-id="10234-109">You work for a manufacturing company.</span></span> <span data-ttu-id="10234-110">Votre entreprise a des contrats avec plusieurs fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="10234-110">Your company has contracts with several vendors.</span></span> <span data-ttu-id="10234-111">Ces contrats décrivent des normes pour l'expédition à temps, les dommages et la qualité des produits pour les articles.</span><span class="sxs-lookup"><span data-stu-id="10234-111">Those contracts outline standards for on-time shipment, damages, and product quality for items.</span></span> <span data-ttu-id="10234-112">De même, plusieurs de vos clients ont des accords avec votre entreprise concernant les retours, les dommages et la qualité des produits.</span><span class="sxs-lookup"><span data-stu-id="10234-112">Likewise, several of your customers have agreements with your company about returns, damages, and product quality.</span></span>

<span data-ttu-id="10234-113">Une grille tarifaire est définie pour chaque circonstance et spécifiée dans le contrat.</span><span class="sxs-lookup"><span data-stu-id="10234-113">A fee structure is defined for each circumstance and specified in the contract.</span></span> <span data-ttu-id="10234-114">Vous pouvez configurer des frais de qualité pour décrire les différents types de frais, tels que *Dommages*, *Retard de livraison* et *Qualité*.</span><span class="sxs-lookup"><span data-stu-id="10234-114">You can configure quality charges to outline the various types of charges, such as *Damages*, *Late shipment*, and *Quality*.</span></span> <span data-ttu-id="10234-115">Ensuite, lorsque vous créez une non-conformité, vous devez ajouter une ou plusieurs opérations.</span><span class="sxs-lookup"><span data-stu-id="10234-115">Then, when you create a nonconformance, you add one or more operations.</span></span> <span data-ttu-id="10234-116">Pour chaque opération, sélectionnez des **Frais** pour définir les détails.</span><span class="sxs-lookup"><span data-stu-id="10234-116">For each operation, you select **Charges** to define the details about the fees.</span></span>

## <a name="create-a-quality-charge"></a><span data-ttu-id="10234-117">Créer des frais de qualité</span><span class="sxs-lookup"><span data-stu-id="10234-117">Create a quality charge</span></span>

1. <span data-ttu-id="10234-118">Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Frais de qualité**.</span><span class="sxs-lookup"><span data-stu-id="10234-118">Go to **Inventory management \> Setup \> Quality management \> Quality charges**.</span></span>
1. <span data-ttu-id="10234-119">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="10234-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="10234-120">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="10234-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="10234-121">**Code de frais** - Entrez un identifiant ou un nom unique pour les frais de qualité.</span><span class="sxs-lookup"><span data-stu-id="10234-121">**Charges code** – Enter a unique ID or name for the quality charge.</span></span>
    - <span data-ttu-id="10234-122">**Description** - Entrez une description détaillée des frais de qualité.</span><span class="sxs-lookup"><span data-stu-id="10234-122">**Description** – Enter a detailed description of the quality charge.</span></span>

1. <span data-ttu-id="10234-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="10234-123">Close the page.</span></span>

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a><span data-ttu-id="10234-124">Ajouter une charge de qualité à une opération suite à une non-conformité</span><span class="sxs-lookup"><span data-stu-id="10234-124">Add a quality charge to an operation for a nonconformance</span></span>

<span data-ttu-id="10234-125">Pour plus de détails sur la façon d'ajouter des opérations à une non-conformité et de leur appliquer des frais, voir [Opérations pour les non-conformités](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="10234-125">For details about how to add operations to a nonconformance and apply charges to them, see [Operations for nonconformances](quality-operations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="10234-126">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="10234-126">Additional resources</span></span>

- [<span data-ttu-id="10234-127">Vue d’ensemble de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="10234-127">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="10234-128">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="10234-128">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="10234-129">Collaborateurs chargés d'approuver les non-conformités</span><span class="sxs-lookup"><span data-stu-id="10234-129">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="10234-130">Zones de contrôle pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="10234-130">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="10234-131">Types de diagnostic pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="10234-131">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="10234-132">Frais de qualité pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="10234-132">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="10234-133">Opérations pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="10234-133">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="10234-134">Gestion de la qualité pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="10234-134">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
