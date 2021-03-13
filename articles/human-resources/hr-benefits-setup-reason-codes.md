---
title: Paramétrer des codes motif
description: Dynamics 365 Human Resources utilise des codes de motif pour expliquer pourquoi les avantages d'un employé changent.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae82c8312d344f5380adec8413766304681a0a05
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112501"
---
# <a name="set-up-reason-codes"></a><span data-ttu-id="3ec14-103">Paramétrer des codes motif</span><span class="sxs-lookup"><span data-stu-id="3ec14-103">Set up reason codes</span></span>

<span data-ttu-id="3ec14-104">Dynamics 365 Human Resources utilise des codes de motif pour expliquer pourquoi les avantages d'un employé changent.</span><span class="sxs-lookup"><span data-stu-id="3ec14-104">Dynamics 365 Human Resources uses reason codes to explain why an employee’s benefits are changing.</span></span>

> [!NOTE]
> <span data-ttu-id="3ec14-105">Depuis janvier 2021, les codes motif migrent vers l'espace de travail **Gestion du personnel** au lieu de l'espace de travail **Gestion des avantages**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-105">As of January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="3ec14-106">Pour plus d'informations, voir [Migrer manuellement les codes motif vers la gestion du personnel](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span><span class="sxs-lookup"><span data-stu-id="3ec14-106">For more information, see [Manually migrate reason codes to Personnel management](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span></span>

## <a name="create-reason-codes"></a><span data-ttu-id="3ec14-107">Créer des codes motifs</span><span class="sxs-lookup"><span data-stu-id="3ec14-107">Create reason codes</span></span>

1. <span data-ttu-id="3ec14-108">Dans l'espace de travail **Gestion du personnel** (ou l'espace de travail **Gestion des avantages** si vos codes motifs n'ont pas encore migré), sélectionnez **Liens**, puis **Codes motifs**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-108">In the **Personnel management** workspace (or **Benefits management** workspace if your reason codes haven't yet migrated), select **Links**, and then select **Reason codes**.</span></span>

2. <span data-ttu-id="3ec14-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-109">Select **New**.</span></span>

3. <span data-ttu-id="3ec14-110">Spécifiez les valeurs des champs suivants :</span><span class="sxs-lookup"><span data-stu-id="3ec14-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="3ec14-111">Champ</span><span class="sxs-lookup"><span data-stu-id="3ec14-111">Field</span></span> | <span data-ttu-id="3ec14-112">Description</span><span class="sxs-lookup"><span data-stu-id="3ec14-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="3ec14-113">**Code motif**</span><span class="sxs-lookup"><span data-stu-id="3ec14-113">**Reason code**</span></span> | <span data-ttu-id="3ec14-114">Nom unique pour identifier la raison pour laquelle un employé modifierait la souscription à un régime de prestations.</span><span class="sxs-lookup"><span data-stu-id="3ec14-114">A unique name to identify the reason an employee would change a benefit plan enrollment.</span></span> |
   | <span data-ttu-id="3ec14-115">**Description**</span><span class="sxs-lookup"><span data-stu-id="3ec14-115">**Description**</span></span> | <span data-ttu-id="3ec14-116">Description du code motif.</span><span class="sxs-lookup"><span data-stu-id="3ec14-116">A description of the reason code.</span></span> |

4. <span data-ttu-id="3ec14-117">Sous **Scénarios applicables**, définissez **Gestion des avantages** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-117">Under **Applicable scenarios**, set **Benefits management** to **Yes**.</span></span> <span data-ttu-id="3ec14-118">(Ne s'applique pas si vos codes motif n'ont pas encore migré vers l'espace de travail **Gestion du personnel**.)</span><span class="sxs-lookup"><span data-stu-id="3ec14-118">(Not applicable if your reason codes haven't yet migrated to the **Personnel management** workspace.)</span></span>

5. <span data-ttu-id="3ec14-119">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-119">Select **Save**.</span></span>

## <a name="manually-migrate-reason-codes-to-personnel-management"></a><span data-ttu-id="3ec14-120">Migrer manuellement les codes motif vers Gestion du personnel</span><span class="sxs-lookup"><span data-stu-id="3ec14-120">Manually migrate reason codes to Personnel management</span></span>

<span data-ttu-id="3ec14-121">En janvier 2021, les codes motif ont migré vers l'espace de travail **Gestion du personnel** au lieu de l'espace de travail **Gestion des avantages**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-121">In January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="3ec14-122">La plupart des données de code motif migreront automatiquement dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="3ec14-122">Most reason code data will automatically migrate in your environment.</span></span> <span data-ttu-id="3ec14-123">Il est possible que certaines données de code motif ne migrent pas.</span><span class="sxs-lookup"><span data-stu-id="3ec14-123">Some reason code data might not migrate.</span></span> <span data-ttu-id="3ec14-124">Par exemple, les codes motif ont désormais un maximum de 15 caractères, de sorte que ceux de plus de 15 caractères ne migreront pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="3ec14-124">For example, reason codes now have a 15-character maximum, so any reason codes longer than 15 characters won't migrate automatically.</span></span>

<span data-ttu-id="3ec14-125">Vous verrez une bannière sur la page **Liens** de l'espace de travail **Gestion des avantages** vous informant de la migration et indiquant si des codes motif n'ont pas migré.</span><span class="sxs-lookup"><span data-stu-id="3ec14-125">You'll see a banner on the **Links** page of the **Benefits management** workspace informing you about the migration and whether any reason codes didn't migrate.</span></span>

1. <span data-ttu-id="3ec14-126">Sélectionnez **Codes motif** pour plus de détails sur l'état de la migration.</span><span class="sxs-lookup"><span data-stu-id="3ec14-126">Select **Reason codes** for details about migration status.</span></span>

   <span data-ttu-id="3ec14-127">[![Codes motif](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span><span class="sxs-lookup"><span data-stu-id="3ec14-127">[![Reason codes](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span></span>

2. <span data-ttu-id="3ec14-128">Sélectionnez un code motif dont la migration a échoué.</span><span class="sxs-lookup"><span data-stu-id="3ec14-128">Select a reason code that failed to migrate.</span></span>

   <span data-ttu-id="3ec14-129">[![Statut de migration du code motif](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span><span class="sxs-lookup"><span data-stu-id="3ec14-129">[![Reason code migration status](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span></span>

3. <span data-ttu-id="3ec14-130">Sélectionnez **Migrer le code motif**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-130">Select **Migrate reason code**.</span></span>

   <span data-ttu-id="3ec14-131">[![Migrer le code motif](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span><span class="sxs-lookup"><span data-stu-id="3ec14-131">[![Migrate reason code](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span></span>

4. <span data-ttu-id="3ec14-132">Dans le volet **Bénéficier de la migration du code motif**, vous avez deux options pour mapper à un code motif de gestion du personnel :</span><span class="sxs-lookup"><span data-stu-id="3ec14-132">In the **Benefit reason code migration** pane, you have two options for mapping to a Personnel management reason code:</span></span>

   - <span data-ttu-id="3ec14-133">Pour utiliser un code motif existant dans la gestion du personnel, choisissez-en un dans le menu déroulant **Utiliser le code motif existant**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-133">To use an existing reason code in Personnel management, choose one from the **Use existing reason code** dropdown.</span></span>
     > [!NOTE]
     > <span data-ttu-id="3ec14-134">Vous ne pouvez utiliser un code motif existant dans Gestion du personnel que si un autre code motif de Gestion des avantages n'y a pas déjà été migré.</span><span class="sxs-lookup"><span data-stu-id="3ec14-134">You can only use an existing reason code in Personnel management if another Benefits management reason code hasn't already migrated to it.</span></span>
   - <span data-ttu-id="3ec14-135">Pour créer un nouveau code motif dans la gestion du personnel, saisissez-en un nouveau dans **Nouveau code motif**, puis entrez une description dans **Nouvelle description**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-135">To create a new reason code in Personnel management, enter a new one in **New reason code**, and then enter a description in **New description**.</span></span>

   <span data-ttu-id="3ec14-136">[![Mettre en correspondance vers un code motif de Gestion du personnel](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span><span class="sxs-lookup"><span data-stu-id="3ec14-136">[![Map to a Personnel management reason code](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span></span>

<span data-ttu-id="3ec14-137">Une fois les codes motif migrés vers Gestion du personnel, l'option permettant de les utiliser dans Gestion des avantages est automatiquement définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="3ec14-137">After reason codes migrate to Personnel management, the option for using them in Benefits management is automatically set to **Yes**.</span></span>

<span data-ttu-id="3ec14-138">[![Utiliser le code motif dans Gestion des avantages](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span><span class="sxs-lookup"><span data-stu-id="3ec14-138">[![Use reason code in Benefits management](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span></span>