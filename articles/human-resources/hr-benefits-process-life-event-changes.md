---
title: Traitement des changements d’événement de vie
description: Traitez les changements d’événements de vie dans Microsoft Dynamics 365 Human Resources pour les changements d’événements de vie.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d32d6ba893a99149e27f644ac80e430db3c08fa0
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112548"
---
# <a name="process-life-event-changes"></a><span data-ttu-id="99439-103">Traitement des changements d’événement de vie</span><span class="sxs-lookup"><span data-stu-id="99439-103">Process life event changes</span></span>

<span data-ttu-id="99439-104">Traitez les changements d’événements de vie dans Microsoft Dynamics 365 Human Resources pour deux changements d’événements de vie :</span><span class="sxs-lookup"><span data-stu-id="99439-104">Process life event changes in Microsoft Dynamics 365 Human Resources for two life event changes:</span></span>

- <span data-ttu-id="99439-105">Changements d’anniversaire</span><span class="sxs-lookup"><span data-stu-id="99439-105">Birthday changes</span></span>
- <span data-ttu-id="99439-106">Changements d’expiration de remplacement de règle d’éligibilité</span><span class="sxs-lookup"><span data-stu-id="99439-106">Eligibility rule override expiration changes</span></span> 

1. <span data-ttu-id="99439-107">Dans l’espace de travail **Gestion des avantages**, sous **Traitement**, sélectionnez **Traitement de modification des événements de vie**.</span><span class="sxs-lookup"><span data-stu-id="99439-107">In the **Benefits management** workspace, under **Processing**, select **Life event change processing**.</span></span>

2. <span data-ttu-id="99439-108">Dans la boîte de dialogue **Exécuter le processus des modifications d’événement de vie**, spécifiez des valeurs pour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="99439-108">In the **Run life event change process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="99439-109">Champ</span><span class="sxs-lookup"><span data-stu-id="99439-109">Field</span></span> | <span data-ttu-id="99439-110">Description</span><span class="sxs-lookup"><span data-stu-id="99439-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="99439-111">Période d’inscription</span><span class="sxs-lookup"><span data-stu-id="99439-111">Enrollment period</span></span> | <span data-ttu-id="99439-112">Période d’inscription pour laquelle traiter les modifications d’événement de vie.</span><span class="sxs-lookup"><span data-stu-id="99439-112">The enrollment period to process life event changes for.</span></span> |
   | <span data-ttu-id="99439-113">Entité juridique</span><span class="sxs-lookup"><span data-stu-id="99439-113">Legal entity</span></span> | <span data-ttu-id="99439-114">Entité juridique pour laquelle traiter les modifications d’événement de vie.</span><span class="sxs-lookup"><span data-stu-id="99439-114">The legal entity to process life event changes for.</span></span> |

3. <span data-ttu-id="99439-115">Si vous souhaitez exécuter le processus en arrière-plan, sélectionnez **Exécuter à l’arrière-plan** et effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="99439-115">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="99439-116">Entrez les informations pour le processus.</span><span class="sxs-lookup"><span data-stu-id="99439-116">Enter information for the process.</span></span>

   2. <span data-ttu-id="99439-117">Pour configurer une tâche récurrente, sélectionnez **Récurrence**, saisissez les informations de récurrence et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="99439-117">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="99439-118">Pour configurer une alerte emploi, sélectionnez **Alertes**, sélectionnez les alertes à recevoir, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="99439-118">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="99439-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99439-119">Select **OK**.</span></span> <span data-ttu-id="99439-120">Le processus s’exécutera avec les paramètres que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="99439-120">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="99439-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99439-121">Select **OK**.</span></span>
