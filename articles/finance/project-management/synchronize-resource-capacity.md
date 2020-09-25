---
title: Synchroniser une capacité de ressource
description: Cette rubrique fournit des informations sur la synchronisation de la capacité d’une ressource entre les calendriers et les projets.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760542"
---
# <a name="synchronize-resource-capacity"></a><span data-ttu-id="f42b2-103">Synchroniser une capacité de ressource</span><span class="sxs-lookup"><span data-stu-id="f42b2-103">Synchronize resource capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f42b2-104">Les processus de synchronisation des ressources permettent de garantir que les informations de calendrier et de calendrier de base soient réinjectées dans la planification des ressources de projet.</span><span class="sxs-lookup"><span data-stu-id="f42b2-104">The processes for resource synchronization help guarantee that information for the calendar and base calendar trickles down into project resource scheduling.</span></span> <span data-ttu-id="f42b2-105">Si le calendrier est modifié, les processus décrivent les mises à jour obligatoires dans la planification des ressources de projet.</span><span class="sxs-lookup"><span data-stu-id="f42b2-105">If the calendar is changed, the processes make the required updates to the scheduling of project resources.</span></span> <span data-ttu-id="f42b2-106">Les processus permettent également d’améliorer les performances, car les informations sur les ressources du calendrier sont synchronisées avec l’avance.</span><span class="sxs-lookup"><span data-stu-id="f42b2-106">The processes also help improve performance, because the calendar's resource information is synchronized in advance.</span></span> <span data-ttu-id="f42b2-107">Par conséquent, les mises à jour avec les informations de planification des ressources se produisent plus rapidement.</span><span class="sxs-lookup"><span data-stu-id="f42b2-107">Therefore, updates to resource scheduling information occur more quickly.</span></span> <span data-ttu-id="f42b2-108">Nous vous recommandons de planifier des processus en tant que traitement par lots plutôt qu’un à la fois.</span><span class="sxs-lookup"><span data-stu-id="f42b2-108">We recommend that you schedule the processes as a batch instead of one at a time.</span></span> <span data-ttu-id="f42b2-109">Sinon, il existe un risque que quelqu’un oublie les dates incluses lorsque les informations ont été synchronisées pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="f42b2-109">Otherwise, there is a risk that someone will forget the inclusive dates when the information was last synchronized.</span></span> <span data-ttu-id="f42b2-110">Si les dates incluses ne sont pas utilisées, des écarts peuvent se produire au cours de la synchronisation de la date.</span><span class="sxs-lookup"><span data-stu-id="f42b2-110">If inclusive dates aren't used, gaps can occur during date synchronization.</span></span>

![Synchronisation du calendrier](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a><span data-ttu-id="f42b2-112">Synchroniser les reports de capacité des ressources</span><span class="sxs-lookup"><span data-stu-id="f42b2-112">Synchronize resource capacity roll-ups</span></span>

<span data-ttu-id="f42b2-113">Le processus de synchronisation est conçu pour synchroniser toutes les informations du calendrier des ressources.</span><span class="sxs-lookup"><span data-stu-id="f42b2-113">The synchronization process is designed to synchronize all resource calendar information.</span></span> <span data-ttu-id="f42b2-114">Ces informations incluent des informations de base du calendrier sur toutes les modifications apportées à la table de capacité du calendrier des ressources du projet.</span><span class="sxs-lookup"><span data-stu-id="f42b2-114">This information includes base calendar information about any changes to the project's Resource calendar capacity table.</span></span> <span data-ttu-id="f42b2-115">Si de nouvelles ressources sont ajoutées au projet, la synchronisation permet de garantir que les informations de calendrier mises à jour sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="f42b2-115">If new resources are added in the project, synchronization helps guarantee that the updated calendar information is available.</span></span> <span data-ttu-id="f42b2-116">Cette synchronisation peut être effectuée à tout moment.</span><span class="sxs-lookup"><span data-stu-id="f42b2-116">This synchronization can be done at any time.</span></span>

<span data-ttu-id="f42b2-117">Nous vous recommandons d’utiliser un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="f42b2-117">We recommend that you use a batch.</span></span> <span data-ttu-id="f42b2-118">Les options sont disponibles lors de la synchronisation des réservations de capacité.</span><span class="sxs-lookup"><span data-stu-id="f42b2-118">The options are available during synchronization of capacity reservations.</span></span>

1. <span data-ttu-id="f42b2-119">Sélectionnez **Gestion de projets et comptabilité** &gt; **Périodique** &gt; **Synchronisation des capacités** &gt; **Synchroniser les reports de capacité des ressources**.</span><span class="sxs-lookup"><span data-stu-id="f42b2-119">Select **Project management and accounting** &gt; **Periodic** &gt; **Capacity synchronization** &gt; **Synchronize resources capacity roll-ups**.</span></span>
2. <span data-ttu-id="f42b2-120">Définissez les options dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="f42b2-120">Set the options in the following table.</span></span>

    | <span data-ttu-id="f42b2-121">Option</span><span class="sxs-lookup"><span data-stu-id="f42b2-121">Option</span></span>      | <span data-ttu-id="f42b2-122">Description</span><span class="sxs-lookup"><span data-stu-id="f42b2-122">Description</span></span> |
    |-------------|-------------|
    | <span data-ttu-id="f42b2-123">Code période</span><span class="sxs-lookup"><span data-stu-id="f42b2-123">Period code</span></span> | <span data-ttu-id="f42b2-124">Permet de sélectionner un code intervalle de dates de comptabilité pour définir les dates de début et de fin du processus de synchronisation pour les reports de capacité des ressources.</span><span class="sxs-lookup"><span data-stu-id="f42b2-124">Optionally select the General ledger date interval code to set the start and end dates for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="f42b2-125">Date de début</span><span class="sxs-lookup"><span data-stu-id="f42b2-125">Start date</span></span>  | <span data-ttu-id="f42b2-126">Entrez la date de début du processus de synchronisation pour les reports de capacité des ressources.</span><span class="sxs-lookup"><span data-stu-id="f42b2-126">Enter the start date for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="f42b2-127">Date de fin</span><span class="sxs-lookup"><span data-stu-id="f42b2-127">End date</span></span>    | <span data-ttu-id="f42b2-128">Entrez la date de fin du processus de synchronisation pour les reports de capacité des ressources.</span><span class="sxs-lookup"><span data-stu-id="f42b2-128">Enter the end date for the synchronization process for resource capacity roll-ups.</span></span> |

<span data-ttu-id="f42b2-129">[![Processus de synchronisation](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span><span class="sxs-lookup"><span data-stu-id="f42b2-129">[![Synchronization process](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span></span>
