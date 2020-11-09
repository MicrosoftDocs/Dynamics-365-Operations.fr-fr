---
title: Examiner l'état d'une expérience
description: Cette rubrique explique l'état d'une expérience dans le cycle de vie de l'expérimentation dans Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: eea67ddc1718902198b74614ee1a910fc6e29c1d
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097068"
---
# <a name="review-the-status-of-an-experiment"></a><span data-ttu-id="9ed65-103">Examiner l'état d'une expérience</span><span class="sxs-lookup"><span data-stu-id="9ed65-103">Review the status of an experiment</span></span>
<span data-ttu-id="9ed65-104">La configuration et l’exécution d’une expérience dans Dynamics 365 Commerce comportent de nombreuses étapes.</span><span class="sxs-lookup"><span data-stu-id="9ed65-104">There are many steps involved in setting up and running an experiment in Dynamics 365 Commerce.</span></span> <span data-ttu-id="9ed65-105">Pour plus d'informations sur le cycle de vie de l'expérimentation, consultez [Expérimentation dans Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9ed65-105">For information about the experimentation lifecycle, see [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="9ed65-106">Pour savoir où se situe une expérience dans le cycle de vie, dans le générateur de site Commerce, sélectionnez **Expériences** dans le volet de navigation de gauche.</span><span class="sxs-lookup"><span data-stu-id="9ed65-106">To learn where an experiment is in the lifecycle, in Commerce site builder select **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="9ed65-107">Une liste des expériences s'affiche et indique l'état de chaque expérience dans Commerce et dans le service tiers utilisé pour permettre la création des expériences, attribuer des variantes et analyser les données.</span><span class="sxs-lookup"><span data-stu-id="9ed65-107">A list of experiments is displayed with the status of each experiment in both Commerce and the third-party service that is being used to enable the creation of experiments, assign variations, and analyze data.</span></span>

<span data-ttu-id="9ed65-108">Dans la colonne **État de Commerce** , les valeurs suivantes peuvent être affichées.</span><span class="sxs-lookup"><span data-stu-id="9ed65-108">In the **Commerce status** column, the following values may be displayed.</span></span> 
- <span data-ttu-id="9ed65-109">**Brouillon** - L'expérience est connectée à une page ou à un fragment dans Commerce et est en cours de modification.</span><span class="sxs-lookup"><span data-stu-id="9ed65-109">**Draft** - The experiment is connected to a page or fragment in Commerce and is being edited.</span></span>
- <span data-ttu-id="9ed65-110">**Publié** - Les variantes de l'expérience sont prêtes à être affichées sur votre site web.</span><span class="sxs-lookup"><span data-stu-id="9ed65-110">**Published** - The experiment variations are ready to be displayed on your website.</span></span> <span data-ttu-id="9ed65-111">Si l'expérience est en cours d'exécution dans le service tiers, les utilisateurs du site web verront une variante de la page ou du fragment sélectionné par le service tiers.</span><span class="sxs-lookup"><span data-stu-id="9ed65-111">If the experiment is running in the third-party service, website users will see a variation of the page or fragment as selected by the third-party service.</span></span>
- <span data-ttu-id="9ed65-112">**Non publié** - L'expérience n'est plus disponible sur votre site web.</span><span class="sxs-lookup"><span data-stu-id="9ed65-112">**Unpublished** - The experiment is no longer available on your website.</span></span> <span data-ttu-id="9ed65-113">Les utilisateurs du site web ne verront que la version par défaut de la page ou du fragment, même si l'expérience est exécutée dans le service tiers.</span><span class="sxs-lookup"><span data-stu-id="9ed65-113">Website users will only see the default version of the page or fragment even if the experiment is running in the third-party service.</span></span>
- <span data-ttu-id="9ed65-114">**Terminé** - L'expérience est terminée et une variante a été promue et mise en ligne pour tous les utilisateurs du site web.</span><span class="sxs-lookup"><span data-stu-id="9ed65-114">**Completed** - The experiment has run its course and a variation was promoted to live for all website users.</span></span>

<span data-ttu-id="9ed65-115">De même, dans la colonne **État du tiers** , les valeurs suivantes peuvent être affichées pour indiquer l'état des expériences dans le service tiers.</span><span class="sxs-lookup"><span data-stu-id="9ed65-115">Similarly, in the **third-party status** column, the following values may be displayed to indicate what status the experiments are in the third-party service.</span></span>
- <span data-ttu-id="9ed65-116">**Brouillon** - L'expérience est configurée dans le service tiers mais n'a pas été lancée.</span><span class="sxs-lookup"><span data-stu-id="9ed65-116">**Draft** - The experiment is set up in the third-party service but hasn't been started.</span></span>
- <span data-ttu-id="9ed65-117">**En cours** - L'expérience a été lancée dans le service tiers et collecte des données.</span><span class="sxs-lookup"><span data-stu-id="9ed65-117">**Running** - The experiment was started in the third-party service and is collecting data.</span></span>
- <span data-ttu-id="9ed65-118">**Suspendu** - L'expérience est suspendue et ne collecte pas de données.</span><span class="sxs-lookup"><span data-stu-id="9ed65-118">**Paused** - The experiment is paused and not collecting data.</span></span> <span data-ttu-id="9ed65-119">Vous devez reprendre l'expérience pour qu'elle collecte à nouveau des données.</span><span class="sxs-lookup"><span data-stu-id="9ed65-119">You must resume the experiment for it to collect data again.</span></span>
- <span data-ttu-id="9ed65-120">**Archivé** - L'expérience est terminée et a été ajoutée au catalogue dans le service tiers à titre de référence.</span><span class="sxs-lookup"><span data-stu-id="9ed65-120">**Archived** - The experiment has run its course and has been cataloged in the third-party service for future reference.</span></span>

<span data-ttu-id="9ed65-121">Le diagramme ci-dessous montre les deux ensembles d'états et leurs liens.</span><span class="sxs-lookup"><span data-stu-id="9ed65-121">The diagram below shows both sets of statuses and how they relate to each other.</span></span>

<span data-ttu-id="9ed65-122">[ ![États de l'expérimentation](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9ed65-122">[ ![Experimentation statuses](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span></span>
