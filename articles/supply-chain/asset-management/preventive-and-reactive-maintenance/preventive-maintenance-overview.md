---
title: Vue d'ensemble de la maintenance préventive
description: Cette rubrique explique la maintenance préventive dans le module Gestion des actifs.
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
ms.openlocfilehash: 3b43c795426f40cb43962976824c44a7702d91b7
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875640"
---
# <a name="preventive-maintenance-overview"></a><span data-ttu-id="79b8a-103">Vue d'ensemble de la maintenance préventive</span><span class="sxs-lookup"><span data-stu-id="79b8a-103">Preventive maintenance overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="79b8a-104">Cette rubrique explique la maintenance préventive dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="79b8a-104">This topic explains preventive maintenance in Asset Management.</span></span> <span data-ttu-id="79b8a-105">La maintenance préventive désigne une discipline impliquant des opérations de maintenance planifiées, par exemple, l'entretien, le calibrage et les contrôles réguliers.</span><span class="sxs-lookup"><span data-stu-id="79b8a-105">Preventive maintenance is a discipline involving planned maintenance jobs, for example, regular service, calibration, and inspections.</span></span> <span data-ttu-id="79b8a-106">Dans **Gestion des actifs**, vous pouvez créer des plans de maintenance et les définir sur les actifs et les postes techniques.</span><span class="sxs-lookup"><span data-stu-id="79b8a-106">In **Asset Management**, you can create maintenance plans and set them up on assets and functional locations.</span></span> <span data-ttu-id="79b8a-107">Vous pouvez également configurer les visites de maintenance sur les postes techniques.</span><span class="sxs-lookup"><span data-stu-id="79b8a-107">You can also set up maintenance rounds on functional locations.</span></span> <span data-ttu-id="79b8a-108">Les plans de maintenance sur les actifs sont actifs, quel que soit l'emplacement d'installation de l'actif.</span><span class="sxs-lookup"><span data-stu-id="79b8a-108">Maintenance plans on assets are active regardless of where the asset is installed.</span></span> <span data-ttu-id="79b8a-109">Les plans de maintenance et les visites de maintenance sur le poste technique sont actifs pour les actifs actuellement installés à l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="79b8a-109">Maintenance plans and maintenance rounds on functional location are active for the assets currently installed at the location.</span></span> <span data-ttu-id="79b8a-110">Plutôt que de définir les plans de maintenance sur les actifs, ou de configurer les visites de maintenance sur les postes techniques, vous pouvez créer des visites de maintenance qui comprennent plusieurs actifs sur lesquels vous devez exécuter les types de tâches de maintenance associés dans la même routine de travail.</span><span class="sxs-lookup"><span data-stu-id="79b8a-110">Instead of setting up maintenance plans on assets, or setting up maintenance rounds on functional locations, you can create maintenance rounds that include multiple assets on which you need to perform related types of maintenance jobs in the same work routine.</span></span> <span data-ttu-id="79b8a-111">Les visites de maintenance créées depuis les actifs, plutôt que créées sur les postes techniques, indiquent que vous pouvez sélectionner plusieurs actifs pour une visite de maintenance, qui ne sont pas installés sur le même poste technique.</span><span class="sxs-lookup"><span data-stu-id="79b8a-111">Maintenance rounds created from assets - instead of created on functional locations - means that you can select a number of assets for one maintenance round, which are not installed on the same functional location.</span></span>

<span data-ttu-id="79b8a-112">Les plans de maintenance sont utilisés à des fins de maintenance préventive et réactive sur les actifs individuels.</span><span class="sxs-lookup"><span data-stu-id="79b8a-112">Maintenance plans are used for preventive and reactive maintenance on individual assets.</span></span> <span data-ttu-id="79b8a-113">Les visites de maintenance sont utilisés pour la maintenance préventive sur un groupe ou un ensemble d'actifs.</span><span class="sxs-lookup"><span data-stu-id="79b8a-113">Maintenance rounds are used for preventive maintenance on a group or a set of assets.</span></span> <span data-ttu-id="79b8a-114">Les plans de maintenance et les visites de maintenance sont utilisés pour générer les propositions des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="79b8a-114">Maintenance plans and maintenance rounds are used for generating work order proposals.</span></span> <span data-ttu-id="79b8a-115">Les propositions des ordres de travail sont enregistrées comme lignes du programme de maintenance, qui peuvent être regroupées et converties en ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="79b8a-115">The work order proposals are saved as maintenance schedule lines, which can be bundled and converted into work orders.</span></span>

<span data-ttu-id="79b8a-116">La figure ci-dessous offre une vue d'ensemble du flux de travail depuis la création des plans de maintenance et les visites de maintenance à la création des ordres de travail pour les actifs, selon ces plans de maintenance et visites de maintenance.</span><span class="sxs-lookup"><span data-stu-id="79b8a-116">The figure below provides an overview of the work flow from creating maintenance plans and maintenance rounds to creating work orders for assets, based on those maintenance plans and maintenance rounds.</span></span>

![Figure 1](media/01-preventive-maintenance.png)

