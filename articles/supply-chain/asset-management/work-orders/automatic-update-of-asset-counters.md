---
title: Mise à jour automatique des compteurs d'actifs
description: Cette rubrique décrit les mises à jour automatiques des compteurs d'actifs dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fcc46fad8d57b7d4d57edfa4f2ae06de923d1c14
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209168"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="a8053-103">Mise à jour automatique des compteurs d'actifs</span><span class="sxs-lookup"><span data-stu-id="a8053-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a8053-104">Pour plus d'informations sur l'enregistrement manuel des compteurs d'actifs, voir [Mise à jour manuelle des compteurs d'actifs](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="a8053-104">For information about manual registration of asset counters, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span> <span data-ttu-id="a8053-105">Pour plus d'informations sur la configuration des compteurs d'actifs, voir [Compteurs](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="a8053-105">For information on how to set up asset counters, see [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="a8053-106">Des contre valeurs peuvent également être automatiquement mises à jour à partir des enregistrements de production, selon les heures de production ou la quantité produite.</span><span class="sxs-lookup"><span data-stu-id="a8053-106">Counter values can also be automatically updated from production registrations, based on the production hours or production quantity (that is, the quantity that is produced).</span></span> <span data-ttu-id="a8053-107">Cette mise à jour est effectuée sur la page **Mettre à jour les compteurs d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="a8053-107">This update is done on the **Update asset counters** page.</span></span> <span data-ttu-id="a8053-108">Vous pouvez mettre à jour un ou plusieurs actifs en définissant un paramètre, **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="a8053-108">You can update one or several assets by setting one parameter, **From date**.</span></span> <span data-ttu-id="a8053-109">Ce paramètre spécifie la date de début des enregistrements de production (heures ou quantités de production).</span><span class="sxs-lookup"><span data-stu-id="a8053-109">This parameter specifies the start date for production registrations (production hours or production quantities).</span></span> <span data-ttu-id="a8053-110">En d'autres termes, il spécifie la date à partir de laquelle des contre-valeurs doivent être mises à jour.</span><span class="sxs-lookup"><span data-stu-id="a8053-110">In other words, it specifies the date that counter values should be updated from.</span></span>

<span data-ttu-id="a8053-111">Tous les actifs associés à une ressource *et* ayant des compteurs d'actifs qui sont paramétrés pour être mis à jour selon la quantité produite et les heures de production, sont inclus dans une mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="a8053-111">All assets that are related to a resource, *and* that have asset counters that are set up to be updated based on the production hours or production quantity, will be included in an automatic update.</span></span> <span data-ttu-id="a8053-112">Des contre-valeurs sont créées.</span><span class="sxs-lookup"><span data-stu-id="a8053-112">New counter values will be created.</span></span>

<span data-ttu-id="a8053-113">Pour les compteurs basés sur la quantité de production, le nombre inclut la quantité correcte et la quantité erronée qui sont enregistrées.</span><span class="sxs-lookup"><span data-stu-id="a8053-113">For counters that are based on the production quantity, the count includes both the good quantity and the error quantity that are registered.</span></span> <span data-ttu-id="a8053-114">Si l'unité utilisée pour l'enregistrement de la quantité en production est différente de celle utilisée sur le compteur, la quantité est convertie afin de correspondre à l'unité du compteur.</span><span class="sxs-lookup"><span data-stu-id="a8053-114">If the unit that is used for production quantity registration differs from the unit that is used for the counter, the quantity is converted so that it corresponds to the counter unit.</span></span>

<span data-ttu-id="a8053-115">Comme mentionné ci-dessus, les compteurs automatiques peuvent être mis à jour à partir des enregistrements de production.</span><span class="sxs-lookup"><span data-stu-id="a8053-115">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="a8053-116">Par conséquent, l'actif pour lequel vous souhaitez mettre à jour automatiquement les compteurs doit être lié à une ressource (machine).</span><span class="sxs-lookup"><span data-stu-id="a8053-116">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="a8053-117">Lorsque des quantités produites ou des heures de production ont été enregistrées dans la ressource, vous pouvez mettre les compteurs d'actifs associés à jour.</span><span class="sxs-lookup"><span data-stu-id="a8053-117">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="a8053-118">Sélectionnez **Gestion des actifs** > **Périodique** > **Actifs** > **Mise à jour des compteurs d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="a8053-118">Select **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="a8053-119">Dans le champ **Date de début**, sélectionnez la date de début de la mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="a8053-119">In the **From date** field, select the start date of the automatic update.</span></span>

    >[!NOTE]
    ><span data-ttu-id="a8053-120">La date de ce champ est la date des « travaux en cours » des **Transactions de gamme** (champ **Contrôle de la production** > **Recherches et états** > **Production** > **Transactions de gamme** > **Date physique**).</span><span class="sxs-lookup"><span data-stu-id="a8053-120">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="a8053-121">Dans l'organisateur **Enregistrements à inclure**, vous pouvez sélectionner les actifs, les types d'actifs ou les ressources spécifiques pour la mise à jour automatique.</span><span class="sxs-lookup"><span data-stu-id="a8053-121">On the **Records to include** FastTab, you can select specific assets, asset types, or resources for the automatic update.</span></span> <span data-ttu-id="a8053-122">Sélectionnez **Filtrer**, puis effectuez les sélections appropriées.</span><span class="sxs-lookup"><span data-stu-id="a8053-122">Select **Filter**, and make the relevant selections.</span></span>

4. <span data-ttu-id="a8053-123">Sous le raccourci **Exécuter à l'arrière-plan**, vous pouvez configurer la mise à jour automatique comme traitement par lots comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="a8053-123">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

    <span data-ttu-id="a8053-124">L'illustration suivante présente un exemple de la boîte de dialogue **Mise à jour des compteurs d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="a8053-124">The illustration below shows an example of the **Update asset counters** dialog.</span></span>

    ![Figure 1](media/12-work-orders.png)

5. <span data-ttu-id="a8053-126">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8053-126">Select **OK**.</span></span> 

<span data-ttu-id="a8053-127">Après la mise à jour automatique du compteur d'actifs, vous pouvez afficher les enregistrements du compteur associés à l'actif sur la page **Compteurs d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="a8053-127">After the automatic asset counter update is done, you can view the counter registrations that are related to the asset on the **Asset counters** page.</span></span> <span data-ttu-id="a8053-128">Sélectionnez **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**, sélectionnez l'actif, puis, dans le volet Actions, sous l'onglet **Actif**, dans le groupe **Préventif**, sélectionnez **Compteurs**.</span><span class="sxs-lookup"><span data-stu-id="a8053-128">Select **Asset management** > **Common** > **Assets** > **All assets**, select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span>

<span data-ttu-id="a8053-129">Sur la page **Valeur agrégée de l'actif**, vous pouvez obtenir une vue d'ensemble du dernier enregistrement effectué sur tous les types de compteurs sur tous les actifs.</span><span class="sxs-lookup"><span data-stu-id="a8053-129">On the **Asset aggregated value** page, you can get an overview of the latest registration that have been made on all counter types on all assets.</span></span> <span data-ttu-id="a8053-130">Sélectionnez **Gestion des actifs** > **Recherches** > **Actifs** > **Valeur agrégée de l'actif**.</span><span class="sxs-lookup"><span data-stu-id="a8053-130">Select **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="a8053-131">Cette page est semblable à la page **Compteurs d'actifs**, mais vous ne pouvez ni ajouter ni modifier des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="a8053-131">This page resembles the **Asset counters** page, but you can't add or edit registrations.</span></span> <span data-ttu-id="a8053-132">Elle est uniquement destinée à la vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="a8053-132">It's for overview only.</span></span>

<span data-ttu-id="a8053-133">L'illustration suivante présente un exemple de la boîte de dialogue **Valeur agrégée de l'actif**.</span><span class="sxs-lookup"><span data-stu-id="a8053-133">The illustration below shows an example of the **Asset aggregated value** page.</span></span>

![Figure 2](media/13-work-orders.png)

<span data-ttu-id="a8053-135">Notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="a8053-135">Note the following points:</span></span>

- <span data-ttu-id="a8053-136">Vous pouvez toujours créer des enregistrements manuels de contre-valeur pour les types de compteurs qui sont automatiquement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="a8053-136">You can still create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="a8053-137">Pour plus d'informations, voir [Mise à jour manuelle des compteurs d'actifs](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="a8053-137">For more information, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span>

- <span data-ttu-id="a8053-138">Vous pouvez paramétrer les compteurs associés à un autre compteur.</span><span class="sxs-lookup"><span data-stu-id="a8053-138">You can set up counters that are related to another counter.</span></span> <span data-ttu-id="a8053-139">Dans ce cas, lorsqu'un compteur est mis à jour, les compteurs associés sont automatiquement mis à jour simultanément.</span><span class="sxs-lookup"><span data-stu-id="a8053-139">In this case, when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="a8053-140">Pour plus d'informations sur la configuration des compteurs associés, voir [Compteurs](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="a8053-140">For more information about how to set up related counters, see [Counters](../setup-for-objects/counters.md).</span></span>

