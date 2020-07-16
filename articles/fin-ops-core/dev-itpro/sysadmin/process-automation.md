---
title: Automatisation des processus
description: Cette rubrique fournit des détails sur la façon dont l'automatisation des processus permet une planification simple des processus qui seront exécutés par le serveur de traitement par lots.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 06/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: 2ab4e7510ff98b9fbf0223096b905e9de47f52e1
ms.sourcegitcommit: 1833c1e07a32c8ad41e4a1516e78100ae04a2156
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "3508183"
---
# <a name="process-automation"></a><span data-ttu-id="2ea0a-103">Automatisation des processus</span><span class="sxs-lookup"><span data-stu-id="2ea0a-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2ea0a-104">L'automatisation des processus permet une planification simple des processus qui seront exécutés par le serveur de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="2ea0a-105">La vue calendrier mise à jour du travail planifié permet aux utilisateurs finaux d'afficher le travail planifié et terminé et de prendre des mesures appropriées.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="2ea0a-106">Administration</span><span class="sxs-lookup"><span data-stu-id="2ea0a-106">Administration</span></span>

<span data-ttu-id="2ea0a-107">La page d'administration centrale de toutes les automatisations de processus se trouve dans le module Administration système sous le menu **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="2ea0a-108">Cette page répertoriera tous les processus automatisés (séries) configurés dans le système.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="2ea0a-109">Elle vous permettra également d'ajouter de nouvelles automatisations de processus directement à partir de cette page.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="2ea0a-110">Une fois une série configurée, vous pouvez gérer chaque série à partir de cette liste.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="2ea0a-111">Vous pouvez choisir de modifier toute la série, de la supprimer, d'afficher toutes les occurrences dans une vue liste ou de désactiver la série si vous souhaitez interrompre le travail planifié pendant une certaine période.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-111">You can chose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a period of time.</span></span> 

## <a name="calendar-view"></a><span data-ttu-id="2ea0a-112">Vue calendrier</span><span class="sxs-lookup"><span data-stu-id="2ea0a-112">Calendar view</span></span> 
<span data-ttu-id="2ea0a-113">L'un des principaux avantages de l'automatisation des processus est la possibilité d'afficher le travail planifié dans une simple vue de calendrier.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-113">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="2ea0a-114">Cette vue vous permet d'afficher le travail pour une semaine à la fois.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-114">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="2ea0a-115">Cette vue est disponible sur le côté droit de la page **Automatisation des processus**.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-115">You will see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="2ea0a-116">Elle sera remplie avec le travail planifié pour la série sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-116">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="2ea0a-117">[![Calendrier d'automatisation des processus](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="2ea0a-117">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="2ea0a-118">Modifications d'occurrence</span><span class="sxs-lookup"><span data-stu-id="2ea0a-118">Occurrence changes</span></span>
<span data-ttu-id="2ea0a-119">Chaque occurrence peut être modifiée sans avoir d'incidence sur les autres occurrences définies par la série d'origine.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-119">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="2ea0a-120">Les occurrences du travail planifié peuvent être modifiées dans la vue calendrier en sélectionnant le bouton **Afficher/Modifier** et en sélectionnant **Occurrence**.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-120">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="2ea0a-121">Cela vous permet d'accéder à tous les paramètres affichés initialement dans l'assistant de configuration de série tout en vous offrant la possibilité d'effectuer une modification unique pour l'occurrence sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-121">This allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="2ea0a-122">Une occurrence du travail planifié peut également être désactivée en sélectionnant le bouton **Désactiver** dans la vue calendrier.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-122">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span> 

## <a name="developer-documentation"></a><span data-ttu-id="2ea0a-123">Documentation du développeur</span><span class="sxs-lookup"><span data-stu-id="2ea0a-123">Developer documentation</span></span> 
<span data-ttu-id="2ea0a-124">La documentation du développeur est en cours de rédaction pour permettre aux développeurs d'étendre le cadre d'automatisation des processus.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-124">Developer documentation is currently being written to allow developers to extend the process automation framework.</span></span> <span data-ttu-id="2ea0a-125">Cette documentation fournira des informations sur la façon dont vous pouvez créer des processus personnalisés qui doivent être exécutés par le serveur de traitement par lots planifié avec l'assistant d'automatisation des processus et qui apparaissent automatiquement dans la vue calendrier.</span><span class="sxs-lookup"><span data-stu-id="2ea0a-125">This documentation will provide information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>
