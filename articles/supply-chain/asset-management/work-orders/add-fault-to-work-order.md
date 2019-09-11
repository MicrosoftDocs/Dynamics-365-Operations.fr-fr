---
title: Ajouter une défaillance à un bon de travail
description: Cette rubrique décrit comment ajouter des enregistrements de défaillance aux ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875656"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="fcc34-103">Ajouter une défaillance à un bon de travail</span><span class="sxs-lookup"><span data-stu-id="fcc34-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="fcc34-104">Vous pouvez ajouter le paramétrage des défaillances dans le concepteur de défaillance d'un bon de travail.</span><span class="sxs-lookup"><span data-stu-id="fcc34-104">You can add faults set up in the fault designer to a work order.</span></span> <span data-ttu-id="fcc34-105">L'actif sélectionné dans l'ordre de travail doit contenir des types d'actif ayant un ou plusieurs enregistrements de défaillance associés.</span><span class="sxs-lookup"><span data-stu-id="fcc34-105">The asset selected in the work order must contain asset types that have one or more fault records connected to it.</span></span> <span data-ttu-id="fcc34-106">En savoir plus sur le paramétrage dans la section [Gestion des défaillances](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="fcc34-106">Read more about setup in the [Fault management](../setup-for-work-orders/fault-management.md) section.</span></span>

1. <span data-ttu-id="fcc34-107">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-107">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="fcc34-108">Dans la liste, sélectionnez l'ordre de travail dans lequel vous souhaitez effectuer un enregistrement de défaillance et cliquez sur **Défaillance des actifs**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-108">In the list, select the work order on which you want to make a fault registration and click **Asset fault**.</span></span>

3. <span data-ttu-id="fcc34-109">Dans l'organisateur **Symptômes**, cliquez sur **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-109">On the **Symptoms** FastTab, click **Add line**.</span></span> <span data-ttu-id="fcc34-110">Un numéro séquentiel de défaillance est automatiquement inséré dans le champ **Problème**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-110">A sequential fault number is automatically inserted in the **Fault** field.</span></span>

4. <span data-ttu-id="fcc34-111">Sélectionnez le symptôme approprié dans le champ **Symptôme de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-111">Select the relevant symptom in the **Fault symptom** field.</span></span>

5. <span data-ttu-id="fcc34-112">Sélectionnez **Zone de défaillance** et **Type de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-112">Select **Fault area** and **Fault type**.</span></span>

6. <span data-ttu-id="fcc34-113">Dans le champ **Date de la défaillance**, la date du jour est automatiquement insérée.</span><span class="sxs-lookup"><span data-stu-id="fcc34-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="fcc34-114">Si nécessaire, vous pouvez sélectionner une autre date.</span><span class="sxs-lookup"><span data-stu-id="fcc34-114">You can select another date, if necessary.</span></span>

7. <span data-ttu-id="fcc34-115">Dans l'organisateur **Causes du symptôme sélectionné**, ajoutez une ligne décrivant la cause du problème.</span><span class="sxs-lookup"><span data-stu-id="fcc34-115">On the **Causes for selected symptom** FastTab, add a line describing the cause of the problem.</span></span>

8. <span data-ttu-id="fcc34-116">Dans l'organisateur **Solutions pour le symptôme sélectionné**, ajoutez une ligne décrivant une solution possible pour le problème.</span><span class="sxs-lookup"><span data-stu-id="fcc34-116">On the **Remedies for selected symptom** FastTab, add a line describing a possible solution to the problem.</span></span>

9. <span data-ttu-id="fcc34-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-117">Click **Save**.</span></span>

![Figure 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="fcc34-119">Afficher les défaillances des actifs</span><span class="sxs-lookup"><span data-stu-id="fcc34-119">View asset faults</span></span>

<span data-ttu-id="fcc34-120">Dans la liste **Défaillances des actifs**, vous pouvez obtenir une vue d'ensemble de toutes les défaillances enregistrées sur les actifs.</span><span class="sxs-lookup"><span data-stu-id="fcc34-120">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="fcc34-121">Cliquez sur **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Défaillances des actifs** pour ouvrir la liste.</span><span class="sxs-lookup"><span data-stu-id="fcc34-121">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults** to open the list.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="fcc34-122">Imprimer l'état de défaillance de l'actif</span><span class="sxs-lookup"><span data-stu-id="fcc34-122">Print asset fault report</span></span>

<span data-ttu-id="fcc34-123">Dans la page de liste **Tous les actifs**, vous pouvez imprimer un état de défaillance de l'actif affichant tous les enregistrements de défaillance ainsi qu'une vue d'ensemble graphique des statistiques de défaillance.</span><span class="sxs-lookup"><span data-stu-id="fcc34-123">From the **All assets** list page, you can print an asset fault report displaying all fault registrations as well as a graphic overview of fault statistics.</span></span>

1. <span data-ttu-id="fcc34-124">Cliquez sur **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-124">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="fcc34-125">Dans la liste **Actifs**, sélectionnez l'actif pour lequel vous souhaitez imprimer l'état de défaillance.</span><span class="sxs-lookup"><span data-stu-id="fcc34-125">In the **Assets** list, select the asset for which you want to print a fault report.</span></span>

3. <span data-ttu-id="fcc34-126">Dans l'onglet **Général** > section **États**, cliquez sur **Défaillance des actifs**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-126">On the **General** tab > **Reports section**, click **Asset fault**.</span></span>

4. <span data-ttu-id="fcc34-127">Insérez une période spécifique ou sélectionnez un type de défaillance.</span><span class="sxs-lookup"><span data-stu-id="fcc34-127">Insert a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="fcc34-128">Cliquez sur **OK** pour imprimer l'état.</span><span class="sxs-lookup"><span data-stu-id="fcc34-128">Click **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="fcc34-129">Vous pouvez également imprimer un état de défaillance pour plusieurs actifs ou types d'actif en cliquant sur **Gestion des actifs** > **États** > **Actifs** > **Défaillance des actifs**.</span><span class="sxs-lookup"><span data-stu-id="fcc34-129">You can also print a fault report for several assets or asset types by clicking **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

