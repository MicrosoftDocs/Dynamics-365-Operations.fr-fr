---
title: Éliminer une estimation de projet
description: Cette rubrique fournit des informations sur l'élimination d'une estimation de projet une fois celle-ci terminée.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410218"
---
# <a name="eliminate-a-project-estimate"></a><span data-ttu-id="9ee0c-103">Éliminer une estimation de projet</span><span class="sxs-lookup"><span data-stu-id="9ee0c-103">Eliminate a project estimate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ee0c-104">Les estimations de projet fournissent la vue financière du travail estimé et planifié pour un projet.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-104">Project estimates provide the financial view for work that is estimated and scheduled for a project.</span></span> <span data-ttu-id="9ee0c-105">Pour utiliser des estimations pour un projet, vous devez associer le projet à un projet d'estimation.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-105">To work with estimates for a project, you must attach the project to an estimate project.</span></span> <span data-ttu-id="9ee0c-106">Un projet d'estimation est toujours basé sur un projet existant, mais plusieurs projets peuvent faire référence à un seul projet d'estimation.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-106">An estimate project is always based on an existing project, however multiple projects can refer to a single estimate project.</span></span> <span data-ttu-id="9ee0c-107">Seuls les projets à prix fixe et les projets d'investissement peuvent être attachés aux projets d'estimation, et ces projets doivent appartenir au même groupe de projets que le projet d'estimation.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-107">Only fixed-price and investment projects can be attached to estimate projects, and those projects must belong to the same project group as the estimate project.</span></span>

<span data-ttu-id="9ee0c-108">Pour éliminer un projet d'estimation, celui-ci doit être terminé.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-108">To eliminate an estimate project, it must be complete.</span></span> <span data-ttu-id="9ee0c-109">Les étapes suivantes expliquent comment éliminer une estimation.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-109">The following steps explain how to eliminate an estimate.</span></span>

1. <span data-ttu-id="9ee0c-110">Accédez à **Gestion de projet et comptabilité** > **Tous les projets** et ouvrez le projet.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-110">Go to **Project management and accounting** > **All Projects** and open the project.</span></span> 
2. <span data-ttu-id="9ee0c-111">Dans l'onglet **Gérer**, sélectionnez **Estimations** et dans la page **Estimation**, sélectionnez **Éliminer**.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-111">On the **Manage** tab, select **Estimates**, and on the **Estimate** page select **Eliminate**.</span></span>
3. <span data-ttu-id="9ee0c-112">Dans la page **Éliminer l'estimation** de l'onglet **Général**, définissez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ee0c-112">On the **Eliminate estimate** page on the **General** tab, set the following options:</span></span>

   - <span data-ttu-id="9ee0c-113">**Code période** : sélectionnez le code période pour choisir les projets d'estimation appropriés.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-113">**Period code**: Select the period code to choose the appropriate estimate projects.</span></span> 
   - <span data-ttu-id="9ee0c-114">**Date de l'estimation** : sélectionnez la date d'estimation appropriée à éliminer.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-114">**Estimate date**: Select the appropriate estimate date for elimination.</span></span>
   - <span data-ttu-id="9ee0c-115">**Éliminer avec avertissements de travaux en cours** : activez cette option pour fournir une notification lorsqu'une estimation associée à un travail en cours (WIP) va être supprimée.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-115">**Eliminate with WIP warnings**: Enable this option to provide notification when an estimate that is associated with a work in progress (WIP) will be eliminated.</span></span> <span data-ttu-id="9ee0c-116">Lorsque cette option n'est pas activée, l'élimination ne peut pas se poursuivre lorsque des transactions non estimées existent.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-116">When this option is not enabled, elimination can’t continue if any non-estimated transactions exist.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="9ee0c-117">Cette option n'est disponible que lorsque l'élimination est appliquée à un projet d'estimation.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-117">This option is available only when elimination is applied to an estimate project.</span></span> <span data-ttu-id="9ee0c-118">Elle n'est pas disponible si vous utilisez des validations périodiques.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-118">It is not available if you are using periodic postings.</span></span> <span data-ttu-id="9ee0c-119">Ce paramètre fonctionne avec les paramètres de l'onglet **Estimation** de la page **Paramètres du projet**, dans le groupe de champs **Autoriser l'élimination lorsque des transactions non estimées existent**.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-119">This setting works with the settings on the **Estimate** tab on the **Project parameters** page, in the **Allow elimination when non-estimated transactions exist** field group.</span></span>
   - <span data-ttu-id="9ee0c-120">**Définir la phase sur Terminé** : activez cette option pour définir la phase du projet d'estimation sur **Terminé** après avoir exécuté l'élimination.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-120">**Set stage to Finished**: Enable this option to set the estimate project’s stage to **Finished** after you run the elimination.</span></span>
   - <span data-ttu-id="9ee0c-121">**Imprimer la liste d'estimations** : sélectionnez les informations à inclure lors de l'impression de la liste des projets d'estimation.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-121">**Print estimate list**: Select the information to be included when the estimate list is printed.</span></span>
   - <span data-ttu-id="9ee0c-122">**Afficher la page Infos** : activez cette option pour afficher la page Infos.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-122">**Show Infolog**: Enable this option to display the Infolog.</span></span>
   - <span data-ttu-id="9ee0c-123">**Date de validation** : choisissez la date de validation dans la comptabilité de l'estimation.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-123">**Posting date**: Choose the ledger posting date of the estimate.</span></span>

4.  <span data-ttu-id="9ee0c-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-124">Select **OK**.</span></span>
5. <span data-ttu-id="9ee0c-125">Une fois le processus d'élimination terminé, le projet d'estimation éliminé s'affiche avec une valeur négative.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-125">After the elimination process is complete, the eliminated estimate project is displayed with a negative value.</span></span> 

<span data-ttu-id="9ee0c-126">Si vous n'aviez pas l'intention d'éliminer une estimation, vous pouvez sélectionner l'estimation éliminée et sélectionner **Annuler l'élimination**.</span><span class="sxs-lookup"><span data-stu-id="9ee0c-126">If you did not intend to eliminate an estimate, you can select the eliminated estimate and select **Reverse elimination**.</span></span>   
