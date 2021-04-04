---
title: Synchroniser la date et l’heure dans les tâches d’importation
description: Utilisez les fuseaux horaires UTC dans les tâches d’importation pour éviter les problèmes de conversion de fuseau horaire.
author: Sunil-Garg
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ce3bf39e8342d3fe19a253f6d17684b2bd0aec0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570477"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a><span data-ttu-id="95a1f-103">Synchroniser la date et l’heure dans les tâches d’importation</span><span class="sxs-lookup"><span data-stu-id="95a1f-103">Synchronize date and time in import jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95a1f-104">Il est important de définir le fuseau horaire de votre tâche d’importation sur le temps universel coordonné (UTC).</span><span class="sxs-lookup"><span data-stu-id="95a1f-104">It's important to set the time zone for your import job to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="95a1f-105">Vous pouvez voir des dates et des heures inattendues dans vos données importées si vous utilisez un paramètre différent.</span><span class="sxs-lookup"><span data-stu-id="95a1f-105">You might see unexpected dates and times in your imported data if you use a different setting.</span></span> <span data-ttu-id="95a1f-106">Sans le paramètre correct, le processus d’importation convertit la date UTC au format local, puis les paramètres système la convertit à nouveau.</span><span class="sxs-lookup"><span data-stu-id="95a1f-106">Without the correct setting, the import process converts the UTC date to the local format, and then system settings converts it again.</span></span>

<span data-ttu-id="95a1f-107">Cette double conversion fait changer les dates entre les applications.</span><span class="sxs-lookup"><span data-stu-id="95a1f-107">This dual conversion causes dates to change between applications.</span></span> <span data-ttu-id="95a1f-108">Par exemple, la double conversion pourrait faire en sorte que la date de début d’un employé soit différente entre Dynamics 365 Human Resources et Dynamics 365 Finance en raison de différences dans les fuseaux horaires locaux.</span><span class="sxs-lookup"><span data-stu-id="95a1f-108">For example, the dual conversion could cause an employee's start date to be different between Dynamics 365 Human Resources and Dynamics 365 Finance due to differences in local time zones.</span></span> <span data-ttu-id="95a1f-109">La définition de la tâche d’importation sur UTC résout ce problème.</span><span class="sxs-lookup"><span data-stu-id="95a1f-109">Setting the import job to UTC resolves this problem.</span></span>

1. <span data-ttu-id="95a1f-110">Dans Dynamics 365 Finance and Operations, sélectionnez **Gestion de données**.</span><span class="sxs-lookup"><span data-stu-id="95a1f-110">In Dynamics 365 Finance and Operations, select **Data management**.</span></span>

2. <span data-ttu-id="95a1f-111">Sélectionnez **Importer des projets**, puis sélectionnez le projet.</span><span class="sxs-lookup"><span data-stu-id="95a1f-111">Select **Import projects**, and then select the project.</span></span>

3. <span data-ttu-id="95a1f-112">Sous **Format de date source**, sélectionnez **CSV-Unicode**.</span><span class="sxs-lookup"><span data-stu-id="95a1f-112">Under **Source date format**, select **CSV-Unicode**.</span></span>

   <span data-ttu-id="95a1f-113">[![Changer le format de date source en UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span><span class="sxs-lookup"><span data-stu-id="95a1f-113">[![Change source date format to UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span></span>

4. <span data-ttu-id="95a1f-114">Changez le champ **Fuseau horaire** sur **Fuseau horaire universel coordonné** et changez le champ **Langue** sur **Fr-FR**.</span><span class="sxs-lookup"><span data-stu-id="95a1f-114">Change **Timezone** to **Coordinated Universal Timezone**, and change **Language** to **En-US**.</span></span>




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]