---
title: Dépannage des états analytiques
description: Cet article explique comment procéder si les modifications des données d'un client n'apparaissent pas dans les espaces de travail du client.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 99d9eb3a16e6470820a2eb0a19c1d50e89bd3d36
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008963"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="cffb0-103">Dépannage des états analytiques</span><span class="sxs-lookup"><span data-stu-id="cffb0-103">Troubleshoot analytic reports</span></span>

<span data-ttu-id="cffb0-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="cffb0-104">**Issue**</span></span>

<span data-ttu-id="cffb0-105">Les modifications des données d'un client n'apparaissent pas dans les onglets **Analyses** des espaces de travail du client.</span><span class="sxs-lookup"><span data-stu-id="cffb0-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="cffb0-106">**Cause**</span><span class="sxs-lookup"><span data-stu-id="cffb0-106">**Cause**</span></span>

<span data-ttu-id="cffb0-107">Par défaut, les états Microsoft Power BI sont actualisés toutes les quatre heures, selon le programme de traitement par lots de mesure du déploiement.</span><span class="sxs-lookup"><span data-stu-id="cffb0-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="cffb0-108">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="cffb0-108">**Resolution**</span></span>

<span data-ttu-id="cffb0-109">Ce problème peut seulement être une question de temps.</span><span class="sxs-lookup"><span data-stu-id="cffb0-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="cffb0-110">Procédez comme suit pour démarrer le traitement par lots et mettre à jour les espaces de travail d'analyses.</span><span class="sxs-lookup"><span data-stu-id="cffb0-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="cffb0-111">Ouvrez la page **Traitements par lots** dans **Administration du système \> Liens \> Traitements par lots \> Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="cffb0-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="cffb0-112">Sinon, utilisez la recherche, et entrez **Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="cffb0-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="cffb0-113">Recherchez la tâche **Mesure du déploiement** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="cffb0-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="cffb0-114">Sélectionnez **Modifier** en haut de la page, puis définissez le date/heure de début prévue sur une valeur qui actualise les analyses au plus près de l'heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="cffb0-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Traitements par lots](media/batch-jobs.png)
