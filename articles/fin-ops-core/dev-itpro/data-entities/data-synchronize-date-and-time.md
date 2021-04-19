---
title: Synchroniser la date et l’heure dans les tâches d’importation
description: Utilisez les fuseaux horaires UTC dans les tâches d’importation pour éviter les problèmes de conversion de fuseau horaire.
author: Sunil-Garg
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
ms.openlocfilehash: 41c0ec805a20a525989e0133e5dffb29ce3fed39
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748667"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a><span data-ttu-id="aeb06-103">Synchroniser la date et l’heure dans les tâches d’importation</span><span class="sxs-lookup"><span data-stu-id="aeb06-103">Synchronize date and time in import jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aeb06-104">Il est important de définir le fuseau horaire de votre tâche d’importation sur le temps universel coordonné (UTC).</span><span class="sxs-lookup"><span data-stu-id="aeb06-104">It's important to set the time zone for your import job to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="aeb06-105">Vous pouvez voir des dates et des heures inattendues dans vos données importées si vous utilisez un paramètre différent.</span><span class="sxs-lookup"><span data-stu-id="aeb06-105">You might see unexpected dates and times in your imported data if you use a different setting.</span></span> <span data-ttu-id="aeb06-106">Sans le paramètre correct, le processus d’importation convertit la date UTC au format local, puis les paramètres système la convertit à nouveau.</span><span class="sxs-lookup"><span data-stu-id="aeb06-106">Without the correct setting, the import process converts the UTC date to the local format, and then system settings converts it again.</span></span>

<span data-ttu-id="aeb06-107">Cette double conversion fait changer les dates entre les applications.</span><span class="sxs-lookup"><span data-stu-id="aeb06-107">This dual conversion causes dates to change between applications.</span></span> <span data-ttu-id="aeb06-108">Par exemple, la double conversion pourrait faire en sorte que la date de début d’un employé soit différente entre Dynamics 365 Human Resources et Dynamics 365 Finance en raison de différences dans les fuseaux horaires locaux.</span><span class="sxs-lookup"><span data-stu-id="aeb06-108">For example, the dual conversion could cause an employee's start date to be different between Dynamics 365 Human Resources and Dynamics 365 Finance due to differences in local time zones.</span></span> <span data-ttu-id="aeb06-109">La définition de la tâche d’importation sur UTC résout ce problème.</span><span class="sxs-lookup"><span data-stu-id="aeb06-109">Setting the import job to UTC resolves this problem.</span></span>

1. <span data-ttu-id="aeb06-110">Dans Dynamics 365 Finance and Operations, sélectionnez **Gestion de données**.</span><span class="sxs-lookup"><span data-stu-id="aeb06-110">In Dynamics 365 Finance and Operations, select **Data management**.</span></span>

2. <span data-ttu-id="aeb06-111">Sélectionnez **Importer des projets**, puis sélectionnez le projet.</span><span class="sxs-lookup"><span data-stu-id="aeb06-111">Select **Import projects**, and then select the project.</span></span>

3. <span data-ttu-id="aeb06-112">Sous **Format de date source**, sélectionnez **CSV-Unicode**.</span><span class="sxs-lookup"><span data-stu-id="aeb06-112">Under **Source date format**, select **CSV-Unicode**.</span></span>

   <span data-ttu-id="aeb06-113">[![Changer le format de date source en UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span><span class="sxs-lookup"><span data-stu-id="aeb06-113">[![Change source date format to UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span></span>

4. <span data-ttu-id="aeb06-114">Changez le champ **Fuseau horaire** sur **Fuseau horaire universel coordonné** et changez le champ **Langue** sur **Fr-FR**.</span><span class="sxs-lookup"><span data-stu-id="aeb06-114">Change **Timezone** to **Coordinated Universal Timezone**, and change **Language** to **En-US**.</span></span>




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]