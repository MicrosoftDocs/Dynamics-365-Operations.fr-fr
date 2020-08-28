---
title: Confirmer les expéditions sortantes des traitements par lots
description: Cette rubrique décrit comment configurer un traitement par lots qui confirme automatiquement les expéditions des ordres de transfert sortants pour les chargements prêts à être expédiés.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 41dbfb90b7b19c964e725ee0a4c769402414fb17
ms.sourcegitcommit: 27233e0fda61dac541c5210ca8d94ab4ba74966f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2020
ms.locfileid: "3652232"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a><span data-ttu-id="16574-103">Confirmer les expéditions sortantes des traitements par lots</span><span class="sxs-lookup"><span data-stu-id="16574-103">Confirm outbound shipments from batch jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16574-104">Cette rubrique décrit comment configurer un traitement par lots qui confirme automatiquement les expéditions des ordres de transfert sortants pour les chargements prêts à être expédiés.</span><span class="sxs-lookup"><span data-stu-id="16574-104">This topic describes how to set up a batch job that automatically confirms outbound transfer-order shipments for ready-to-ship loads.</span></span> <span data-ttu-id="16574-105">Le traitement par lots décrit ici s’applique uniquement aux expéditions des ordres de transfert, et non aux commandes client.</span><span class="sxs-lookup"><span data-stu-id="16574-105">The batch job described here only applies to transfer order shipments, not to sales orders.</span></span>

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a><span data-ttu-id="16574-106">Activer la fonctionnalité Confirmer les expéditions sortantes des traitements par lots</span><span class="sxs-lookup"><span data-stu-id="16574-106">Enable the Confirm outbound shipments from batch jobs feature</span></span>

<span data-ttu-id="16574-107">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="16574-107">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="16574-108">Les administrateurs peuvent utiliser la page [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="16574-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="16574-109">La fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="16574-109">The feature is listed as:</span></span>

- <span data-ttu-id="16574-110">**Module** - *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="16574-110">**Module** - *Warehouse management*</span></span>
- <span data-ttu-id="16574-111">**Nom de la fonctionnalité** - *Confirmer les expéditions sortantes des traitements par lots*</span><span class="sxs-lookup"><span data-stu-id="16574-111">**Feature name** - *Confirm outbound shipments from batch jobs*</span></span>

## <a name="process-outbound-shipments"></a><span data-ttu-id="16574-112">Traiter les expéditions sortantes</span><span class="sxs-lookup"><span data-stu-id="16574-112">Process outbound shipments</span></span>

<span data-ttu-id="16574-113">Pour paramétrer un traitement par lots planifié pour exécuter la confirmation des expéditions sortantes pour les chargements prêts à être expédiés :</span><span class="sxs-lookup"><span data-stu-id="16574-113">To set up a scheduled batch job to run the outbound shipment confirmation for loads that are ready to ship:</span></span>

1. <span data-ttu-id="16574-114">Allez dans **Gestion des entrepôts \> Tâches périodiques \> Traiter les expéditions sortantes**.</span><span class="sxs-lookup"><span data-stu-id="16574-114">Go to **Warehouse management \> Periodic tasks \> Process outbound shipments**.</span></span>
1. <span data-ttu-id="16574-115">La boîte de dialogue **Confirmer l’expédition** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="16574-115">The **Confirm shipment** dialog box opens.</span></span> <span data-ttu-id="16574-116">Dans l’organisateur **Enregistrements à inclure**, sélectionnez **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="16574-116">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="16574-117">La boîte de dialogue de l’éditeur de requêtes s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="16574-117">The query editor dialog box opens.</span></span> <span data-ttu-id="16574-118">Dans l’onglet **Plage**, ajoutez une ligne avec les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="16574-118">On the **Range** tab, add a row with the following values:</span></span>
    - <span data-ttu-id="16574-119">**Table** - *Chargements*</span><span class="sxs-lookup"><span data-stu-id="16574-119">**Table** - *Loads*</span></span>
    - <span data-ttu-id="16574-120">**Table dérivée** - *Chargements*</span><span class="sxs-lookup"><span data-stu-id="16574-120">**Derived table** - *Loads*</span></span>
    - <span data-ttu-id="16574-121">**Champ** - *Statut du chargement*</span><span class="sxs-lookup"><span data-stu-id="16574-121">**Field** - *Load status*</span></span>
    - <span data-ttu-id="16574-122">**Critères** - *Chargé*</span><span class="sxs-lookup"><span data-stu-id="16574-122">**Criteria** - *Loaded*</span></span>
1. <span data-ttu-id="16574-123">Cliquez sur **OK** pour revenir à la boite de dialogue **Confirmer l’expédition**.</span><span class="sxs-lookup"><span data-stu-id="16574-123">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="16574-124">Dans l’organisateur **Exécuter en arrière-plan**, définissez **Traitement par lots** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="16574-124">On the **Run in the background** FastTab, set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="16574-125">Dans l’organisateur **Exécuter en arrière-plan**, sélectionnez **Récurrence**.</span><span class="sxs-lookup"><span data-stu-id="16574-125">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="16574-126">La boîte de dialogue **Définir la récurrence** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="16574-126">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="16574-127">Définissez le programme d’exécution selon les besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="16574-127">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="16574-128">Cliquez sur **OK** pour revenir à la boite de dialogue **Confirmer l’expédition**.</span><span class="sxs-lookup"><span data-stu-id="16574-128">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="16574-129">Cliquez sur **OK** dans la boîte de dialogue **Confirmer l’expédition** pour ajouter le traitement par lots à la file d’attente des traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="16574-129">Select **OK** on the **Confirm shipment** dialog box to add the batch job to the batch queue.</span></span>

<span data-ttu-id="16574-130">Pour plus d’informations, voir [Vue d’ensemble du traitement par lots](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="16574-130">For more information, see [Batch processing overview](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span></span>