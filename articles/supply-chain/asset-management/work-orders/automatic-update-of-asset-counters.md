---
title: Mise à jour automatique des compteurs d'actifs
description: Cette rubrique décrit les mises à jour automatiques des compteurs d'actifs dans le module Gestion des actifs.
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875658"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="71312-103">Mise à jour automatique des compteurs d'actifs</span><span class="sxs-lookup"><span data-stu-id="71312-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="71312-104">La section précédente décrivait l'enregistrement manuel des compteurs d'actifs.</span><span class="sxs-lookup"><span data-stu-id="71312-104">In the previous section, manual registration of asset counters is described.</span></span> <span data-ttu-id="71312-105">Le paramétrage des compteurs d'actifs est décrit dans [Compteurs](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="71312-105">Setup of asset counters is described in [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="71312-106">Des contre valeurs peuvent également être automatiquement mises à jour à partir des enregistrements de production, selon les heures de production ou la quantité produite.</span><span class="sxs-lookup"><span data-stu-id="71312-106">Counter values can also be automatically updated from production registrations, based on production hours or production quantity.</span></span> <span data-ttu-id="71312-107">Cela est effectué dans la rubrique **Mise à jour des compteurs d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="71312-107">This is done in **Update asset counters**.</span></span> <span data-ttu-id="71312-108">Vous pouvez mettre à jour un ou plusieurs actifs en entrant un paramètre, **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="71312-108">You can update one or several assets by inserting one parameter, **From date**.</span></span> <span data-ttu-id="71312-109">Ce paramètre spécifie la date de début pour les enregistrements de production (heures de production ou quantité produite), à savoir la date de début à partir de laquelle les contre valeurs doivent être mises à jour.</span><span class="sxs-lookup"><span data-stu-id="71312-109">This parameter specifies the start date for production registrations (hours or quantity produced), meaning the start date from which counter values should be updated.</span></span>

<span data-ttu-id="71312-110">Tous les actifs associés à une ressource *et* ayant des compteurs d'actifs, qui sont paramétrés pour être mis à jour selon la quantité produite et les heures de production, sont inclus dans une mise à jour automatique, et de nouvelles contre-valeurs sont créées.</span><span class="sxs-lookup"><span data-stu-id="71312-110">All assets that are related to a resource *and* have asset counters, which are set up to be updated based on produced quantity or production hours, will be included in an automatic update, and new counter values will be created.</span></span>

<span data-ttu-id="71312-111">Concernant les compteurs basés sur la quantité de production, la quantité correcte et la quantité erronée enregistrée sont incluses dans le comptage.</span><span class="sxs-lookup"><span data-stu-id="71312-111">Regarding counters based on production quantity, good quantity as well as error quantity registered are included in the count.</span></span> <span data-ttu-id="71312-112">Si l'unité utilisée pour l'enregistrement de la quantité produite est différente de celle utilisée sur le compteur, la quantité est convertie pour correspondre à l'unité du compteur.</span><span class="sxs-lookup"><span data-stu-id="71312-112">If the unit used for produced quantity registration is different from the unit used on the counter, quantity is converted to correspond with the counter unit.</span></span>

<span data-ttu-id="71312-113">Comme mentionné ci-dessus, les compteurs automatiques peuvent être mis à jour à partir des enregistrements de production.</span><span class="sxs-lookup"><span data-stu-id="71312-113">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="71312-114">Par conséquent, l'actif pour lequel vous souhaitez mettre à jour automatiquement les compteurs doit être lié à une ressource (machine).</span><span class="sxs-lookup"><span data-stu-id="71312-114">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="71312-115">Les descriptions suivantes fournissent une vue d'ensemble du paramétrage et du traitement des ordres de fabrication (dans le module **Contrôle de la production**), qui sont utilisés comme base pour la mise à jour automatique des compteurs sur un actif dans le module **Gestion des actifs**.</span><span class="sxs-lookup"><span data-stu-id="71312-115">The following descriptions provide an overview of the setup and processing of production orders (in the **Production control** module), which is used as a basis for automatic update of counters on an asset in the **Asset management** module.</span></span>

<span data-ttu-id="71312-116">Lorsque des quantités produites ou des heures de production ont été enregistrées dans la ressource, vous pouvez mettre les compteurs d'actifs associés à jour.</span><span class="sxs-lookup"><span data-stu-id="71312-116">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="71312-117">Cliquez sur **Gestion des actifs** > **Périodique** > **Actifs** > **Mise à jour des compteurs d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="71312-117">Click **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="71312-118">Sélectionnez la date de début de la mise à jour automatique dans le champ **Date de début**.</span><span class="sxs-lookup"><span data-stu-id="71312-118">Select the start date of the automatic update in the **From date** field.</span></span>

>[!NOTE]
><span data-ttu-id="71312-119">La date de ce champ est la date des « travaux en cours » des **Transactions de gamme** (champ **Contrôle de la production** > **Recherches et états** > **Production** > **Transactions de gamme** > **Date physique**).</span><span class="sxs-lookup"><span data-stu-id="71312-119">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="71312-120">Si vous souhaitez sélectionner des actifs spécifiques, des types d'actifs ou des ressources pour la mise à jour automatique, cliquez sur **Filtre** sur l'organisateur **Enregistrements à inclure**, et faites les sélections appropriées.</span><span class="sxs-lookup"><span data-stu-id="71312-120">If you want to select specific assets, asset types, or resources for the automatic update, click **Filter** on the **Records to include** FastTab, and make the relevant selections.</span></span>

4. <span data-ttu-id="71312-121">Le cas échéant, vous pouvez configurer la mise à jour automatique comme traitement par lots sur l'organisateur **Exécuter à l'arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="71312-121">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

![Figure 1](media/12-work-orders.png)

5. <span data-ttu-id="71312-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="71312-123">Click **OK**.</span></span> <span data-ttu-id="71312-124">Lorsque la mise à jour automatique de compteurs d'actifs est effectuée, vous pouvez voir les enregistrements de compteurs liés à l'actif dans **Compteurs d'actifs** (**Gestion d'actifs** > **Commun** > **Actifs** > **Tous les actifs** > sélectionnez l'actif > le bouton **Compteurs**).</span><span class="sxs-lookup"><span data-stu-id="71312-124">When the automatic asset counter update is done, you can see the counter registrations related to the asset in **Asset counters** (**Asset management** > **Common** > **Assets** > **All assets** > select asset > **Counters** button).</span></span>

<span data-ttu-id="71312-125">Dans **Compteurs d'actifs totaux**, vous pouvez obtenir une vue d'ensemble du dernier enregistrement effectué sur tous les types de compteurs sur tous les actifs.</span><span class="sxs-lookup"><span data-stu-id="71312-125">In **Asset counter totals**, you can get an overview of the latest registration made on all counter types on all assets.</span></span> <span data-ttu-id="71312-126">Cliquez sur **Gestion des actifs** > **Recherches** > **Actifs** > **Valeur agrégée de l'actif**.</span><span class="sxs-lookup"><span data-stu-id="71312-126">Click **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="71312-127">La vue est très similaire à **Compteurs d'actifs**, mais vous ne pouvez ni ajouter ni modifier d'enregistrements dans **Valeur agrégée de l'actif**.</span><span class="sxs-lookup"><span data-stu-id="71312-127">The view is very similar to **Asset counters**, but you cannot add or edit registrations in **Asset aggregated value**.</span></span> <span data-ttu-id="71312-128">Ce champ est uniquement destiné à la vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="71312-128">It is for overview only.</span></span>

![Figure 2](media/13-work-orders.png)


- <span data-ttu-id="71312-130">Il est toujours possible de créer des enregistrements manuels de contre-valeur pour les types de compteurs qui sont automatiquement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="71312-130">It is still possible to create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="71312-131">Reportez-vous à la section « Mise à jour manuelle des compteurs d'actifs » pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="71312-131">Refer to the "Manual update of asset counters" section for more information.</span></span>
- <span data-ttu-id="71312-132">Vous pouvez paramétrer des compteurs liés à un autre compteur, ce qui signifie que lorsqu'un compteur est mis à jour, les compteurs associés sont automatiquement mis à jour simultanément.</span><span class="sxs-lookup"><span data-stu-id="71312-132">You can set up counters related to another counter, which means that when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="71312-133">Reportez-vous à la section [Compteurs](../setup-for-objects/counters.md) pour plus d'informations sur le paramétrage des compteurs associés.</span><span class="sxs-lookup"><span data-stu-id="71312-133">Refer to [Counters](../setup-for-objects/counters.md) regarding setup of related counters.</span></span>
