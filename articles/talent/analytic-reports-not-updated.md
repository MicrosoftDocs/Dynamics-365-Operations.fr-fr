---
title: Les états analytiques ne sont pas mis à jour
description: Cette rubrique explique comment procéder si les modifications des données d'un client n'apparaissent pas dans les espaces de travail du client.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 46f426a4b0012e87b4d9d21032870ac7fc33c4ae
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304333"
---
# <a name="analytic-reports-are-not-updated"></a><span data-ttu-id="80b41-103">Les états analytiques ne sont pas mis à jour</span><span class="sxs-lookup"><span data-stu-id="80b41-103">Analytic reports are not updated</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="80b41-104">**Problème**</span><span class="sxs-lookup"><span data-stu-id="80b41-104">**Issue**</span></span>

<span data-ttu-id="80b41-105">Les modifications des données d'un client n'apparaissent pas dans les onglets **Analyses** des espaces de travail du client.</span><span class="sxs-lookup"><span data-stu-id="80b41-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="80b41-106">**Cause**</span><span class="sxs-lookup"><span data-stu-id="80b41-106">**Cause**</span></span>

<span data-ttu-id="80b41-107">Par défaut, les états Microsoft Power BI sont actualisés toutes les quatre heures, selon le programme de traitement par lots de mesure du déploiement.</span><span class="sxs-lookup"><span data-stu-id="80b41-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="80b41-108">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="80b41-108">**Resolution**</span></span>

<span data-ttu-id="80b41-109">Ce problème peut seulement être une question de temps.</span><span class="sxs-lookup"><span data-stu-id="80b41-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="80b41-110">Procédez comme suit pour démarrer le traitement par lots et mettre à jour les espaces de travail d'analyses.</span><span class="sxs-lookup"><span data-stu-id="80b41-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="80b41-111">Ouvrez la page **Traitements par lots** dans **Administration du système \> Liens \> Traitements par lots \> Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="80b41-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="80b41-112">Sinon, utilisez la recherche, et entrez **Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="80b41-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="80b41-113">Recherchez la tâche **Mesure du déploiement** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="80b41-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="80b41-114">Sélectionnez **Modifier** en haut de la page, puis définissez le date/heure de début prévue sur une valeur qui actualise les analyses au plus près de l'heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="80b41-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Traitements par lots](media/batch-jobs.png)
