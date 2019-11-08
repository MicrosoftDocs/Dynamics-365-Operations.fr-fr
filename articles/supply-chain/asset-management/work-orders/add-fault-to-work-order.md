---
title: Ajouter une défaillance à un bon de travail
description: Cette rubrique décrit comment ajouter des enregistrements de défaillance aux ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2b58cc31578d7bb102c6b5aa8b4ce2d6cfe8c893
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626199"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="e60f2-103">Ajoutez une erreur à l'ordre de travail</span><span class="sxs-lookup"><span data-stu-id="e60f2-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="e60f2-104">Vous pouvez ajouter les défaillances configurées dans le concepteur de défaillance d'un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="e60f2-104">You can add faults that were set up in the fault designer to a work order.</span></span> <span data-ttu-id="e60f2-105">Un ou plusieurs enregistrements de défaillance associés doivent être connectés aux types d'actifs utilisé pour l'actif sélectionné dans l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="e60f2-105">One or more fault records must be connected to the asset types that are used for the asset that is selected in the work order.</span></span> <span data-ttu-id="e60f2-106">Pour plus d'informations sur la configuration, voir [Gestion des défaillances](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="e60f2-106">For more information about the setup, see [Fault management](../setup-for-work-orders/fault-management.md).</span></span>

1. <span data-ttu-id="e60f2-107">Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="e60f2-107">Select **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="e60f2-108">Sélectionnez l'ordre de travail sur lequel faire un enregistrement de défaillance, puis, dans le volet Actions, sous l'onglet **Ordre de travail**, dans le groupe **Actif**, sélectionnez **Défaillance des actifs**.</span><span class="sxs-lookup"><span data-stu-id="e60f2-108">Select the work order to make a fault registration on, and then, on the Action Pane, on the **Work order** tab, in the **Asset** group, select **Asset fault**.</span></span>

3. <span data-ttu-id="e60f2-109">Dans l'organisateur **Symptômes**, sélectionnez **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="e60f2-109">On the **Symptoms** FastTab, select **Add line**.</span></span> <span data-ttu-id="e60f2-110">Un numéro séquentiel de défaillance est automatiquement entré dans le champ **Défaillance**.</span><span class="sxs-lookup"><span data-stu-id="e60f2-110">A sequential fault number is automatically entered in the **Fault** field.</span></span>

4. <span data-ttu-id="e60f2-111">Dans le champ **Symptôme de défaillance**, sélectionnez le symptôme approprié.</span><span class="sxs-lookup"><span data-stu-id="e60f2-111">In the **Fault symptom** field, select the relevant symptom.</span></span>

5. <span data-ttu-id="e60f2-112">Dans les champs **Zone de défaillance** et **Type de défaillance**, sélectionnez les valeurs appropriées.</span><span class="sxs-lookup"><span data-stu-id="e60f2-112">In the **Fault area** and **Fault type** fields, select the appropriate values.</span></span>

6. <span data-ttu-id="e60f2-113">Dans le champ **Date de la défaillance**, la date du jour est automatiquement insérée.</span><span class="sxs-lookup"><span data-stu-id="e60f2-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="e60f2-114">Vous pouvez sélectionner une date différente comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="e60f2-114">You can select a different date as you require.</span></span>

7. <span data-ttu-id="e60f2-115">Dans l'organisateur **Causes du symptôme sélectionné**, ajoutez une ligne pour décrire la cause du problème.</span><span class="sxs-lookup"><span data-stu-id="e60f2-115">On the **Causes for selected symptom** FastTab, add a line to describe the cause of the issue.</span></span>

8. <span data-ttu-id="e60f2-116">Dans l'organisateur **Solutions pour le symptôme sélectionné**, ajoutez une ligne pour décrire une solution possible pour le problème.</span><span class="sxs-lookup"><span data-stu-id="e60f2-116">On the **Remedies for selected symptom** FastTab, add a line to describe a possible solution to the issue.</span></span>

9. <span data-ttu-id="e60f2-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e60f2-117">Select **Save**.</span></span>

<span data-ttu-id="e60f2-118">L'illustration ci-dessous présente un exemple d'enregistrement de défaillance.</span><span class="sxs-lookup"><span data-stu-id="e60f2-118">The illustration below shows an example of a fault registration.</span></span>

![Figure 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="e60f2-120">Afficher les défaillances des actifs</span><span class="sxs-lookup"><span data-stu-id="e60f2-120">View asset faults</span></span>

<span data-ttu-id="e60f2-121">Dans la liste **Défaillances des actifs**, vous pouvez obtenir une vue d'ensemble de toutes les défaillances enregistrées sur les actifs.</span><span class="sxs-lookup"><span data-stu-id="e60f2-121">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="e60f2-122">Sur la page de liste **Défaillances des actifs**, vous pouvez obtenir une vue d'ensemble de toutes les défaillances enregistrées sur les actifs.</span><span class="sxs-lookup"><span data-stu-id="e60f2-122">On the **Asset faults** list page, you can get an overview of all faults that have been registered on assets.</span></span> <span data-ttu-id="e60f2-123">Pour ouvrir la page, sélectionnez **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Défaillances des actifs**.</span><span class="sxs-lookup"><span data-stu-id="e60f2-123">To open the page, select **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="e60f2-124">Imprimer l'état de défaillance de l'actif</span><span class="sxs-lookup"><span data-stu-id="e60f2-124">Print asset fault report</span></span>

<span data-ttu-id="e60f2-125">Dans la page de liste **Tous les actifs**, vous pouvez imprimer un état de défaillance de l'actif qui affiche tous les enregistrements de défaillance ainsi qu'une vue d'ensemble graphique des statistiques de défaillance.</span><span class="sxs-lookup"><span data-stu-id="e60f2-125">From the **All assets** list page, you can print an asset fault report that shows all fault registrations and a graphical overview of fault statistics.</span></span>

1. <span data-ttu-id="e60f2-126">Sélectionnez **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**.</span><span class="sxs-lookup"><span data-stu-id="e60f2-126">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="e60f2-127">Sélectionner l'actif pour lequel imprimer un état.</span><span class="sxs-lookup"><span data-stu-id="e60f2-127">Select the asset to print a fault report for.</span></span>

3. <span data-ttu-id="e60f2-128">Dans le volet Actions, sous l'onglet **Général**, dans le groupe **États**, cliquez sur **Défaillance des actifs**.</span><span class="sxs-lookup"><span data-stu-id="e60f2-128">On the Action Pane, on the **General** tab, in the **Reports** group, select **Asset fault**.</span></span>

4. <span data-ttu-id="e60f2-129">Entrez une période spécifique ou sélectionnez un type de défaillance.</span><span class="sxs-lookup"><span data-stu-id="e60f2-129">Enter a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="e60f2-130">Sélectionnez **OK** pour imprimer l'état.</span><span class="sxs-lookup"><span data-stu-id="e60f2-130">Select **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="e60f2-131">Pour imprimer un état de défaillance pour plusieurs actifs ou types d'actifs, sélectionnez **Gestion des actifs** > **États** > **Actifs** > **Défaillance des actifs**.</span><span class="sxs-lookup"><span data-stu-id="e60f2-131">To print a fault report for several assets or asset types, select **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

