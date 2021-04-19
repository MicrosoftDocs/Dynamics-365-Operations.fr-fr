---
title: Interrompre les configurations dans le référentiel RCS Global
description: Cette rubrique décrit comment interrompre les configurations dans le référentiel RCS Global.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 25ad0744e7c3320505c13c465d440b6a364da47c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840290"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a><span data-ttu-id="864bc-103">Interrompre les configurations dans le référentiel RCS Global</span><span class="sxs-lookup"><span data-stu-id="864bc-103">Discontinue configurations in the RCS Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="864bc-104">Cette rubrique décrit comment interrompre une configuration dans le référentiel RCS Global.</span><span class="sxs-lookup"><span data-stu-id="864bc-104">This topic describes how to discontinue configuration in the RCS Global repository.</span></span> <span data-ttu-id="864bc-105">Auparavant, il était possible de supprimer uniquement les configurations qui n’étaient plus nécessaires.</span><span class="sxs-lookup"><span data-stu-id="864bc-105">Previously, it was possible only to delete configurations that were no longer required.</span></span> <span data-ttu-id="864bc-106">Cependant, vous pouvez maintenant marquer une configuration lancée comme **Interrompue** dans le référentiel RCS Global.</span><span class="sxs-lookup"><span data-stu-id="864bc-106">However now you can mark a released configuration as **Discontinued** in the RCS Global repository.</span></span> <span data-ttu-id="864bc-107">Avec cette fonctionnalité, vous pouvez également effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="864bc-107">With this functionality, you can also do the following:</span></span> 
 
 - <span data-ttu-id="864bc-108">Fournir des notifications à l’avance lorsque l’interruption d’une configuration est interrompue.</span><span class="sxs-lookup"><span data-stu-id="864bc-108">Provide up front notifications when a configuration is planned to be discontinued.</span></span>
 - <span data-ttu-id="864bc-109">Incluez les détails applicables sur la configuration de remplacement.</span><span class="sxs-lookup"><span data-stu-id="864bc-109">Include applicable details about the replacement configuration.</span></span>
 - <span data-ttu-id="864bc-110">Définissez une valeur pour **Date de fin de prise en charge** pour la configuration spécifique afin d’informer l’utilisateur de la date d’interruption.</span><span class="sxs-lookup"><span data-stu-id="864bc-110">Set a **Supported until** date for the specific configuration to inform the user when it will be discontinued.</span></span>

<span data-ttu-id="864bc-111">Lorsque vous interrompez la version d’une configuration, vous pouvez spécifier les informations facultatives suivantes :</span><span class="sxs-lookup"><span data-stu-id="864bc-111">When you discontinue a configuration version, you can specify the following optional information:</span></span>

  - <span data-ttu-id="864bc-112">**Configuration de remplacement**</span><span class="sxs-lookup"><span data-stu-id="864bc-112">**Replacement configuration**</span></span>
  - <span data-ttu-id="864bc-113">**Version de configuration de remplacement**</span><span class="sxs-lookup"><span data-stu-id="864bc-113">**Replacement configuration version**</span></span>
  - <span data-ttu-id="864bc-114">**Note libre** : Utilisez ce champ pour fournir des liens vers des documentations ou des références</span><span class="sxs-lookup"><span data-stu-id="864bc-114">**Free text note**: Use this field to provide documentation links or references</span></span>
  - <span data-ttu-id="864bc-115">**Date de fin de prise en charge** : Ce champ fournit la date proposée jusqu’à laquelle la configuration / version actuelle sera prise en charge.</span><span class="sxs-lookup"><span data-stu-id="864bc-115">**Supported until**: This field provides the proposed date up to which the current configuration/version will be supported.</span></span> <span data-ttu-id="864bc-116">Cette date doit être mise à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="864bc-116">This date must be updated manually.</span></span>
  
<span data-ttu-id="864bc-117">Pour interrompre la configuration, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="864bc-117">To discontinue the configuration, complete the following steps.</span></span> 

1. <span data-ttu-id="864bc-118">Sélectionnez si vous souhaitez interrompre une seule version ou toutes les versions avec les mêmes paramètres en une seule opération en définissant **Toutes les versions** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="864bc-118">Select whether you want to discontinue a single version or all versions with the same settings in one operation by setting **All versions** to **Yes**.</span></span> 
2. <span data-ttu-id="864bc-119">Définissez le paramètre **Interrompre** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="864bc-119">Set the **Discontinue** parameter to **Yes**.</span></span>
3. <span data-ttu-id="864bc-120">Sélectionnez **OK** pour interrompre les configurations.</span><span class="sxs-lookup"><span data-stu-id="864bc-120">Select **OK** to discontinue the configurations.</span></span> <span data-ttu-id="864bc-121">Le champ **Date d’interruption** sera rempli lorsque vous enregistrez les modifications.</span><span class="sxs-lookup"><span data-stu-id="864bc-121">The **Discontinued date** field will be populated when you save the changes.</span></span>

![Interrompre les informations de configuration](media/Discontinue-details-2.png)
  
<span data-ttu-id="864bc-123">Vous pouvez rétablir la configuration sur **Partagé** ou ajuster les informations d’interruption à tout moment.</span><span class="sxs-lookup"><span data-stu-id="864bc-123">You can revert configuration back to **Shared** or adjust discontinuation information at any time.</span></span> <span data-ttu-id="864bc-124">Si vous partagez une configuration, spécifiez la valeur pour **Date de fin de prise en charge** et toutes les autres informations relatives à l’interruption pour indiquer les interruptions futures que vous prévoyez.</span><span class="sxs-lookup"><span data-stu-id="864bc-124">If you share a configuration, specify the **Supported until** date and all other information related to the discontinuation to indicate your plans for future discontinuation.</span></span>

<span data-ttu-id="864bc-125">Si vous souhaitez partager des informations sur une interruption planifiée, avant d’interrompre réellement la configuration, l’utilisateur peut préremplir tous les champs liés au remplacement, mais laisser le paramètre **Interrompre** défini sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="864bc-125">If you want to share information about a planned discontinuation, prior to actually discontinuing the configuration, user is able to prefill all fields related to replacement but leave the **Discontinue** parameter set to **No**.</span></span>

> [!NOTE]
> <span data-ttu-id="864bc-126">L’interruption ne limite pas les opérations avec les configurations.</span><span class="sxs-lookup"><span data-stu-id="864bc-126">Discontinuation doesn't limit operations with configurations.</span></span> <span data-ttu-id="864bc-127">Vous pouvez continuer à importer, exécuter ou dériver les configurations. Ces champs sont indicatifs.</span><span class="sxs-lookup"><span data-stu-id="864bc-127">You can continue to import, run, or derive the configurations, these fields are informational.</span></span>

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a><span data-ttu-id="864bc-128">Finance prend en charge l’affichage de ces informations à partir de la version 10.0.14</span><span class="sxs-lookup"><span data-stu-id="864bc-128">Finance supports displaying this information starting in version 10.0.14</span></span>

<span data-ttu-id="864bc-129">À partir de la version 10.0.14, Dynamics 365 Finance prend en charge l’affichage des informations relatives aux interruptions.</span><span class="sxs-lookup"><span data-stu-id="864bc-129">Starting in version 10.0.14, Dynamics 365 Finance supports displaying discontinuation information.</span></span> <span data-ttu-id="864bc-130">Sur la page **Référentiel global**, vous pouvez afficher les informations à jour relatives aux interruptions.</span><span class="sxs-lookup"><span data-stu-id="864bc-130">On the **Global repository** page, you can view up to date information related to discontinuation.</span></span> <span data-ttu-id="864bc-131">Par défaut, les configurations interrompues sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="864bc-131">By default, configurations that are discontinued are filtered out.</span></span>
  
<span data-ttu-id="864bc-132">La page **Configurations importées** (ERSolutionTable) affiche les configurations qui étaient déjà interrompues lors de leur importation.</span><span class="sxs-lookup"><span data-stu-id="864bc-132">The **Imported configurations** (ERSolutionTable) page, shows configurations that were already discontinued when there were imported.</span></span> <span data-ttu-id="864bc-133">Pour les configurations qui ont été interrompues après l’importation, les informations d’interruption peuvent être synchronisées en exécutant la tâche **Importer les mises à jour des configurations**.</span><span class="sxs-lookup"><span data-stu-id="864bc-133">For those configurations that were discontinued after import, the discontinuation information can be synchronized by running the **Import configurations updates** job.</span></span>


