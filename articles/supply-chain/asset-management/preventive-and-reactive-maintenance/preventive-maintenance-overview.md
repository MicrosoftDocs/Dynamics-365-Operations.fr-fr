---
title: Vue d'ensemble de la maintenance préventive
description: Cette rubrique explique la maintenance préventive dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
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
ms.openlocfilehash: 2d079c10331360c035ff800650ed3102c2cc3ad4
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569982"
---
# <a name="preventive-maintenance-overview"></a><span data-ttu-id="125ef-103">Vue d'ensemble de la maintenance préventive</span><span class="sxs-lookup"><span data-stu-id="125ef-103">Preventive maintenance overview</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="125ef-104">Cette rubrique explique la maintenance préventive dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="125ef-104">This topic explains preventive maintenance in Asset Management.</span></span> <span data-ttu-id="125ef-105">La maintenance préventive désigne une discipline impliquant des opérations de maintenance planifiées, par exemple, l'entretien, le calibrage et les contrôles réguliers.</span><span class="sxs-lookup"><span data-stu-id="125ef-105">Preventive maintenance is a discipline involving planned maintenance jobs, for example, regular service, calibration, and inspections.</span></span> <span data-ttu-id="125ef-106">Dans **Gestion des actifs**, vous pouvez créer des plans de maintenance et les définir sur les actifs et les postes techniques.</span><span class="sxs-lookup"><span data-stu-id="125ef-106">In **Asset Management**, you can create maintenance plans and set them up on assets and functional locations.</span></span> <span data-ttu-id="125ef-107">Vous pouvez également configurer les visites de maintenance sur les postes techniques.</span><span class="sxs-lookup"><span data-stu-id="125ef-107">You can also set up maintenance rounds on functional locations.</span></span> <span data-ttu-id="125ef-108">Les plans de maintenance sur les actifs sont actifs, quel que soit l'emplacement d'installation de l'actif.</span><span class="sxs-lookup"><span data-stu-id="125ef-108">Maintenance plans on assets are active regardless of where the asset is installed.</span></span> <span data-ttu-id="125ef-109">Les plans de maintenance et les visites de maintenance sur le poste technique sont actifs pour les actifs actuellement installés à l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="125ef-109">Maintenance plans and maintenance rounds on functional location are active for the assets currently installed at the location.</span></span> <span data-ttu-id="125ef-110">Plutôt que de définir les plans de maintenance sur les actifs, ou de configurer les visites de maintenance sur les postes techniques, vous pouvez créer des visites de maintenance qui comprennent plusieurs actifs sur lesquels vous devez exécuter les types de tâches de maintenance associés dans la même routine de travail.</span><span class="sxs-lookup"><span data-stu-id="125ef-110">Instead of setting up maintenance plans on assets, or setting up maintenance rounds on functional locations, you can create maintenance rounds that include multiple assets on which you need to perform related types of maintenance jobs in the same work routine.</span></span> <span data-ttu-id="125ef-111">Les visites de maintenance créées depuis les actifs, plutôt que créées sur les postes techniques, indiquent que vous pouvez sélectionner plusieurs actifs pour une visite de maintenance, qui ne sont pas installés sur le même poste technique.</span><span class="sxs-lookup"><span data-stu-id="125ef-111">Maintenance rounds created from assets - instead of created on functional locations - means that you can select a number of assets for one maintenance round, which are not installed on the same functional location.</span></span>

<span data-ttu-id="125ef-112">Les plans de maintenance sont utilisés à des fins de maintenance préventive et réactive sur les actifs individuels.</span><span class="sxs-lookup"><span data-stu-id="125ef-112">Maintenance plans are used for preventive and reactive maintenance on individual assets.</span></span> <span data-ttu-id="125ef-113">Les visites de maintenance sont utilisés pour la maintenance préventive sur un groupe ou un ensemble d'actifs.</span><span class="sxs-lookup"><span data-stu-id="125ef-113">Maintenance rounds are used for preventive maintenance on a group or a set of assets.</span></span> <span data-ttu-id="125ef-114">Les plans de maintenance et les visites de maintenance sont utilisés pour générer les propositions des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="125ef-114">Maintenance plans and maintenance rounds are used for generating work order proposals.</span></span> <span data-ttu-id="125ef-115">Les propositions des ordres de travail sont enregistrées comme lignes du programme de maintenance, qui peuvent être regroupées et converties en ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="125ef-115">The work order proposals are saved as maintenance schedule lines, which can be bundled and converted into work orders.</span></span>

<span data-ttu-id="125ef-116">L'illustration suivante offre une vue d'ensemble du flux de travail depuis la création des plans de maintenance et les visites de maintenance à la création des ordres de travail pour les actifs, selon ces plans de maintenance et visites de maintenance.</span><span class="sxs-lookup"><span data-stu-id="125ef-116">The following illustration provides an overview of the work flow from creating maintenance plans and maintenance rounds to creating work orders for assets, based on those maintenance plans and maintenance rounds.</span></span>

![Figure 1](media/01-preventive-maintenance.png)

