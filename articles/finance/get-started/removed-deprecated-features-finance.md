---
title: Fonctions supprimées ou obsolètes dans Dynamics 365 Finance
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: ec13076e6a05c3402af566487f7921f6971da215
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127975"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a><span data-ttu-id="fab2c-103">Fonctions supprimées ou obsolètes dans Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="fab2c-103">Removed or deprecated features in Dynamics 365 Finance</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fab2c-104">Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="fab2c-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Finance.</span></span>

- <span data-ttu-id="fab2c-105">Une fonction *supprimée* n'est plus disponible dans le produit.</span><span class="sxs-lookup"><span data-stu-id="fab2c-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="fab2c-106">Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.</span><span class="sxs-lookup"><span data-stu-id="fab2c-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="fab2c-107">Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification.</span><span class="sxs-lookup"><span data-stu-id="fab2c-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="fab2c-108">Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="fab2c-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="fab2c-109">Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fab2c-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a><span data-ttu-id="fab2c-110">Fonctions supprimées ou obsolètes dans Finance and Operations version 10.0.12</span><span class="sxs-lookup"><span data-stu-id="fab2c-110">Features removed or deprecated in the Finance 10.0.12 release</span></span>

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a><span data-ttu-id="fab2c-111">États SSRS polonais : Registre de la TVA d'aval, Registre de la TVA sur les achats, Synthèse du registre de la TVA de l'UE - Référence de fonctionnalité PL-00014</span><span class="sxs-lookup"><span data-stu-id="fab2c-111">Polish SSRS reports: Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="fab2c-112">**Motif de l'abandon/de la suppression**</span><span class="sxs-lookup"><span data-stu-id="fab2c-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="fab2c-113">Pas autorisé légalement.</span><span class="sxs-lookup"><span data-stu-id="fab2c-113">Not legally required.</span></span>  |
| <span data-ttu-id="fab2c-114">**Remplacé par une autre fonctionnalité ?**</span><span class="sxs-lookup"><span data-stu-id="fab2c-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="fab2c-115">Oui (format Excel pour fichier d'audit standard avec déclaration de TVA - JPK_VDEK)</span><span class="sxs-lookup"><span data-stu-id="fab2c-115">Yes (Excel format for Standard Audit File with VAT declaration - JPK_VDEK)</span></span> |
| <span data-ttu-id="fab2c-116">**Zones de produit affectées**</span><span class="sxs-lookup"><span data-stu-id="fab2c-116">**Product areas affected**</span></span>         | <span data-ttu-id="fab2c-117">Demande</span><span class="sxs-lookup"><span data-stu-id="fab2c-117">Application</span></span> |
| <span data-ttu-id="fab2c-118">**Option de déploiement**</span><span class="sxs-lookup"><span data-stu-id="fab2c-118">**Deployment option**</span></span>              | <span data-ttu-id="fab2c-119">Tout</span><span class="sxs-lookup"><span data-stu-id="fab2c-119">All</span></span> |
| <span data-ttu-id="fab2c-120">**État**</span><span class="sxs-lookup"><span data-stu-id="fab2c-120">**Status**</span></span>                         | <span data-ttu-id="fab2c-121">Obsolète : d'ici le 1er juillet 2021, nous prévoyons de ne plus prendre en charge les états SSRS : **Registre de TVA d'aval, Registre de TVA sur les achats, Synthèse du registre de la TVA de l'UE - Référence de fonctionnalité PL-00014**.</span><span class="sxs-lookup"><span data-stu-id="fab2c-121">Deprecated: By July 1, 2021, we plan to no longer support the SSRS reports: **Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014**.</span></span> <span data-ttu-id="fab2c-122">Un exemple de format Excel pour le fichier d'audit standard avec déclaration de TVA (JPK_VDEK) sera introduit à la place.</span><span class="sxs-lookup"><span data-stu-id="fab2c-122">Excel format example for Standard Audit File with VAT declaration (JPK_VDEK) will be introduced instead.</span></span> |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a><span data-ttu-id="fab2c-123">Fonctions supprimées ou obsolètes dans Finance and Operations version 10.0.7</span><span class="sxs-lookup"><span data-stu-id="fab2c-123">Features removed or deprecated in the Finance 10.0.7 release</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="fab2c-124">La boîte de dialogue de demande de modification du workflow n'inclut plus de liste déroulante de sélection de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="fab2c-124">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="fab2c-125">**Motif de l'abandon/de la suppression**</span><span class="sxs-lookup"><span data-stu-id="fab2c-125">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="fab2c-126">Remplacé par la fonctionnalité avec sélection de groupes de comptes.</span><span class="sxs-lookup"><span data-stu-id="fab2c-126">Changed to the feature with account groups selection.</span></span>  |
| <span data-ttu-id="fab2c-127">**Remplacé par une autre fonctionnalité ?**</span><span class="sxs-lookup"><span data-stu-id="fab2c-127">**Replaced by another feature?**</span></span>   | <span data-ttu-id="fab2c-128">Oui</span><span class="sxs-lookup"><span data-stu-id="fab2c-128">Yes</span></span> |
| <span data-ttu-id="fab2c-129">**Zones de produit affectées**</span><span class="sxs-lookup"><span data-stu-id="fab2c-129">**Product areas affected**</span></span>         | <span data-ttu-id="fab2c-130">Flux de travail</span><span class="sxs-lookup"><span data-stu-id="fab2c-130">Workflow</span></span> |
| <span data-ttu-id="fab2c-131">**Option de déploiement**</span><span class="sxs-lookup"><span data-stu-id="fab2c-131">**Deployment option**</span></span>              | <span data-ttu-id="fab2c-132">Tout</span><span class="sxs-lookup"><span data-stu-id="fab2c-132">All</span></span> |
| <span data-ttu-id="fab2c-133">**État**</span><span class="sxs-lookup"><span data-stu-id="fab2c-133">**Status**</span></span>                         | <span data-ttu-id="fab2c-134">Obsolète : À partir du 1er décembre 2020, nous prévoyons de ne plus prendre en charge les types de documents chinois paramétrés sans sélection de groupes de comptes.</span><span class="sxs-lookup"><span data-stu-id="fab2c-134">Deprecated: By December 1, 2020, we plan to no longer support Chinese voucher types setup without Account groups selection.</span></span> <span data-ttu-id="fab2c-135">Pour plus d'informations sur la nouvelle conception dans [Nouveautés de la version 10.0.7](whats-new-changed-10-0-7.md).</span><span class="sxs-lookup"><span data-stu-id="fab2c-135">Find more details about the new design in [What's new in 10.0.7](whats-new-changed-10-0-7.md).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="fab2c-136">Annonces précédentes sur les fonctions supprimées ou obsolètes</span><span class="sxs-lookup"><span data-stu-id="fab2c-136">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="fab2c-137">Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="fab2c-137">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
