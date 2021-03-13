---
title: Traitez les modifications de taux
description: Traitez les modifications de taux de prestations dans Microsoft Dynamics 365 Human Resources lorsqu’un régime de prestations sociales nouveau ou existant a changé et que les paramètres des règles d’admissibilité doivent être actualisés.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f326957d5f33607e434f99563cfeb528c05f258d
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112520"
---
# <a name="process-rate-changes"></a><span data-ttu-id="0a124-103">Traitez les modifications de taux</span><span class="sxs-lookup"><span data-stu-id="0a124-103">Process rate changes</span></span>

<span data-ttu-id="0a124-104">Traitez les modifications de taux de prestations dans Microsoft Dynamics 365 Human Resources lorsqu’un régime de prestations sociales nouveau ou existant a changé et que les paramètres des règles d’admissibilité doivent être actualisés.</span><span class="sxs-lookup"><span data-stu-id="0a124-104">Process benefit rate changes in Microsoft Dynamics 365 Human Resources when a new or existing benefit plan has a change in eligibility rule settings.</span></span> <span data-ttu-id="0a124-105">Si une nouvelle règle d’éligibilité est créée et affectée au plan, le système réexécute l’admissibilité des collaborateurs pour vérifier s’ils sont toujours éligibles au plan en fonction des nouvelles options d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="0a124-105">If a new eligibility rule is created and assigned to the plan, this prompts the system to rerun worker eligibility to check if workers may now be eligible for the plan based on new eligibility options.</span></span> 

1. <span data-ttu-id="0a124-106">Dans l’espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Traitement d’un changement de taux**.</span><span class="sxs-lookup"><span data-stu-id="0a124-106">In the **Benefits management** workspace, under **Processing**, select **Rate change update processing**.</span></span>

2. <span data-ttu-id="0a124-107">Dans la boîte de dialogue **Exécuter le processus de changement de taux d’avantages**, spécifiez des valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="0a124-107">In the **Run benefit rate update process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="0a124-108">Champ</span><span class="sxs-lookup"><span data-stu-id="0a124-108">Field</span></span> | <span data-ttu-id="0a124-109">Description</span><span class="sxs-lookup"><span data-stu-id="0a124-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="0a124-110">**Période d’inscription**</span><span class="sxs-lookup"><span data-stu-id="0a124-110">**Enrollment period**</span></span> | <span data-ttu-id="0a124-111">La période d’inscription pour traiter les modifications de taux.</span><span class="sxs-lookup"><span data-stu-id="0a124-111">The enrollment period to process rate changes for.</span></span> |

3. <span data-ttu-id="0a124-112">Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0a124-112">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="0a124-113">Entrez les informations pour le processus.</span><span class="sxs-lookup"><span data-stu-id="0a124-113">Enter information for the process.</span></span>

   2. <span data-ttu-id="0a124-114">Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a124-114">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="0a124-115">Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a124-115">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="0a124-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a124-116">Select **OK**.</span></span> <span data-ttu-id="0a124-117">Le processus s’exécutera avec les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="0a124-117">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="0a124-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a124-118">Select **OK**.</span></span>
