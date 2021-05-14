---
title: Activer la gestion de la qualité et de la non-conformité
description: Cette rubrique fournit une vue d'ensemble du processus de configuration et de paramétrage des fonctionnalités de gestion de la qualité et des non-conformités dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d5da648e31d07d054246f5d308a6c6cdeb506c
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956252"
---
# <a name="enable-quality-and-nonconformance-management"></a><span data-ttu-id="6faf3-103">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="6faf3-103">Enable quality and nonconformance management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6faf3-104">Cette rubrique fournit une vue d'ensemble du processus de configuration et de paramétrage des fonctionnalités de gestion de la qualité et des non-conformités dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6faf3-104">This topic provides an overview of the process for setting up and configuring quality and nonconformance management features in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a><span data-ttu-id="6faf3-105">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="6faf3-105">Enable quality and nonconformance management</span></span>

<span data-ttu-id="6faf3-106">Suivez ces étapes pour activer la gestion de la qualité sur votre système.</span><span class="sxs-lookup"><span data-stu-id="6faf3-106">Follow these steps to enable quality management on your system.</span></span>

1. <span data-ttu-id="6faf3-107">Allez dans **Gestion des stocks \> Configuration \> Paramètres de gestion des stocks et des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="6faf3-107">Go to **Inventory management \> Setup \> Inventory and warehouse management parameters**.</span></span>
1. <span data-ttu-id="6faf3-108">Sur l'onglet **Gestion de la qualité**, définissez l'option **Utiliser la gestion de la qualité** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="6faf3-108">On the **Quality management** tab, set the **Use quality management** option to *Yes*.</span></span>
1. <span data-ttu-id="6faf3-109">Dans le champ **Taux horaire**, entrez un taux horaire de main-œuvre dans la devise locale.</span><span class="sxs-lookup"><span data-stu-id="6faf3-109">In the **Hourly rate** field, enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="6faf3-110">Le taux horaire permet de calculer les coûts des opérations associées à une non-conformité.</span><span class="sxs-lookup"><span data-stu-id="6faf3-110">The hourly rate is used to calculate costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="6faf3-111">Le taux horaire et les coûts calculés fournissent des informations de référence pour une non-conformité.</span><span class="sxs-lookup"><span data-stu-id="6faf3-111">The hourly rate and calculated costs provide reference information for a nonconformance.</span></span> <span data-ttu-id="6faf3-112">Ils n’interagissent pas avec les autres fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="6faf3-112">They don't interact with other functionality.</span></span>
1. <span data-ttu-id="6faf3-113">Sélectionnez **Paramétrage d’état**.</span><span class="sxs-lookup"><span data-stu-id="6faf3-113">Select **Report setup**.</span></span>
1. <span data-ttu-id="6faf3-114">Ajoutez de nouvelles lignes pour les différents types d'état et sélectionnez le type de document à utiliser pour chaque état.</span><span class="sxs-lookup"><span data-stu-id="6faf3-114">Add new lines for the various report types, and select the type of document to use for each report.</span></span>
1. <span data-ttu-id="6faf3-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6faf3-115">Close the page.</span></span>
1. <span data-ttu-id="6faf3-116">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6faf3-116">Close the page.</span></span>

## <a name="quality-management-configuration-process"></a><span data-ttu-id="6faf3-117">Processus de configuration de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="6faf3-117">Quality management configuration process</span></span>

<span data-ttu-id="6faf3-118">Avant de pouvoir commencer à utiliser les fonctionnalités de gestion de la qualité et générer des ordres de qualité, vous devez configurer le système et le paramétrer.</span><span class="sxs-lookup"><span data-stu-id="6faf3-118">Before you can start to use the quality management features and generate quality orders, you must configure the system and prerequisites.</span></span> <span data-ttu-id="6faf3-119">Voici la liste des étapes requises pour configurer la gestion de la qualité.</span><span class="sxs-lookup"><span data-stu-id="6faf3-119">Here is a list of the steps that are required to configure quality management.</span></span>

1. <span data-ttu-id="6faf3-120">[Activer la gestion de la qualité et de la non-conformité](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="6faf3-120">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="6faf3-121">Optionnel : [Configurer les instruments de test](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-121">Optional: [Configure test instruments](quality-test-instruments.md).</span></span>
1. <span data-ttu-id="6faf3-122">[Configurer les tests](quality-tests.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-122">[Configure tests](quality-tests.md).</span></span>
1. <span data-ttu-id="6faf3-123">[Configurer les variables de test et les résultats](quality-test-variables.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-123">[Configure test variables and outcomes](quality-test-variables.md).</span></span>
1. <span data-ttu-id="6faf3-124">[Configurer les groupes de test](quality-test-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-124">[Configure test groups](quality-test-groups.md).</span></span>
1. <span data-ttu-id="6faf3-125">Optionnel : [Configurer les groupes de qualité et créer des liens vers les produits](quality-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-125">Optional: [Configure quality groups, and link to products](quality-groups.md).</span></span>
1. <span data-ttu-id="6faf3-126">Optionnel : [Configurer les associations de qualité](quality-associations.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-126">Optional: [Configure quality associations](quality-associations.md).</span></span>

<span data-ttu-id="6faf3-127">Une fois la configuration terminée, vous pouvez commencer à créer et à traiter des ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="6faf3-127">After the configuration is completed, you can start to create and process quality orders.</span></span> <span data-ttu-id="6faf3-128">Pour plus d’informations sur la création et l’utilisation des ordres de qualité, consultez [Ordres de qualité](quality-orders.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-128">For more information about how to create and work with quality orders, see [Quality orders](quality-orders.md).</span></span>

## <a name="nonconformance-management-configuration-process"></a><span data-ttu-id="6faf3-129">Processus de configuration de la gestion de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="6faf3-129">Nonconformance management configuration process</span></span>

<span data-ttu-id="6faf3-130">Avant de pouvoir commencer à utiliser les fonctionnalités de gestion de la non-conformité et générer des non-conformités, vous devez configurer le système et le paramétrer.</span><span class="sxs-lookup"><span data-stu-id="6faf3-130">Before you can start to use the nonconformance management features and generate nonconformances, you must configure the system and prerequisites.</span></span> <span data-ttu-id="6faf3-131">Voici la liste des étapes requises pour configurer la gestion de la non-conformité.</span><span class="sxs-lookup"><span data-stu-id="6faf3-131">Here is a list of the steps that are required to configure nonconformance management.</span></span>

1. <span data-ttu-id="6faf3-132">[Activer la gestion de la qualité et de la non-conformité](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="6faf3-132">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="6faf3-133">[Configurer les collaborateurs chargés d'approuver les non-conformités](quality-responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-133">[Configure workers who are responsible for approving nonconformances](quality-responsible-workers.md).</span></span>
1. <span data-ttu-id="6faf3-134">[Configurer les types de problèmes](quality-problem-types.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-134">[Configure problem types](quality-problem-types.md).</span></span>
1. <span data-ttu-id="6faf3-135">[Configurer les zones de mise en quarantaine](quality-quarantine-zones.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-135">[Configure quarantine zones](quality-quarantine-zones.md).</span></span>
1. <span data-ttu-id="6faf3-136">[Configurer les types de diagnostics](quality-diagnostic-types.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-136">[Configure diagnostic types](quality-diagnostic-types.md).</span></span>
1. <span data-ttu-id="6faf3-137">[Configurer les opérations](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-137">[Configure operations](quality-operations.md).</span></span>
1. <span data-ttu-id="6faf3-138">Optionnel : [Configurer les frais de qualité](quality-charges.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-138">Optional: [Configure quality charges](quality-charges.md).</span></span>

<span data-ttu-id="6faf3-139">Une fois la configuration terminée, vous pouvez commencer à créer et à traiter des non-conformités.</span><span class="sxs-lookup"><span data-stu-id="6faf3-139">After the configuration is completed, you can start to create and process nonconformances.</span></span> <span data-ttu-id="6faf3-140">Pour plus d'informations sur la création et le traitement des non-conformités, voir [Création et traitement des non-conformités](tasks/create-process-non-conformance.md).</span><span class="sxs-lookup"><span data-stu-id="6faf3-140">For more information about how to create and work with nonconformances, see [Create and process nonconformances](tasks/create-process-non-conformance.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6faf3-141">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6faf3-141">Additional resources</span></span>

- [<span data-ttu-id="6faf3-142">Vue d’ensemble de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="6faf3-142">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="6faf3-143">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="6faf3-143">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="6faf3-144">Gestion de la qualité pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="6faf3-144">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
