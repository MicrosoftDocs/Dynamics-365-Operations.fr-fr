---
title: Configurer une expérience
description: Cette rubrique décrit comment configurer une expérience dans un service tiers.
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
ms.openlocfilehash: 29c21ceb4c259f463f4a039942e51141201a9809
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097045"
---
# <a name="set-up-an-experiment"></a><span data-ttu-id="310a7-103">Configurer une expérience</span><span class="sxs-lookup"><span data-stu-id="310a7-103">Set up an experiment</span></span>

<span data-ttu-id="310a7-104">Après avoir [défini une hypothèse et déterminé les métriques de réussite que vous souhaitez utiliser](experimentation-identify.md), vous devrez configurer votre expérience dans le service tiers.</span><span class="sxs-lookup"><span data-stu-id="310a7-104">After you [define a hypothesis and determine what success metrics you want to use](experimentation-identify.md), you'll need to set up your experiment in the third-party service.</span></span> <span data-ttu-id="310a7-105">Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l'exécution d'une expérience sur un site web d'e-commerce dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="310a7-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="310a7-106">Les étapes supplémentaires sont traitées dans d'autres rubriques.</span><span class="sxs-lookup"><span data-stu-id="310a7-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="310a7-107">[ ![Expérimentation parcours utilisateur - Configurer](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="310a7-107">[ ![Experimentation user journey - Setup](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span></span>


## <a name="set-up-your-experiment-in-the-third-party-service"></a><span data-ttu-id="310a7-108">Configurer votre expérience dans le service tiers</span><span class="sxs-lookup"><span data-stu-id="310a7-108">Set up your experiment in the third-party service</span></span>
<span data-ttu-id="310a7-109">Vous devriez maintenant avoir choisi votre service tiers chargé d'exécuter et de surveiller votre expérience, et avoir configuré le connecteur d'expérimentation.</span><span class="sxs-lookup"><span data-stu-id="310a7-109">By now you should have chosen your third-party service to run and monitor your experiment, and set up the experimentation connector.</span></span> <span data-ttu-id="310a7-110">Ces conditions préalables sont répertoriées dans [Expérimentation dans Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="310a7-110">These prerequisites are listed in  [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="310a7-111">Suivez les étapes requises pour créer votre expérience dans le service tiers.</span><span class="sxs-lookup"><span data-stu-id="310a7-111">Follow the steps required to create your experiment in the third-party service.</span></span> <span data-ttu-id="310a7-112">Si le connecteur est correctement configuré, la liste complète des expériences que vous avez configurées dans le service tiers apparaîtra dans le générateur de site Commerce dans un délai d'environ 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="310a7-112">If the connector is configured properly, the complete list of experiments you set up in the third-party service will appear in Commerce site builder within about 5 minutes.</span></span>

## <a name="set-up-your-success-metrics"></a><span data-ttu-id="310a7-113">Configurer vos métriques de réussite</span><span class="sxs-lookup"><span data-stu-id="310a7-113">Set up your success metrics</span></span>
<span data-ttu-id="310a7-114">Chaque expérience a besoin de métriques pour mesurer l'impact des variantes et valider l'hypothèse.</span><span class="sxs-lookup"><span data-stu-id="310a7-114">Every experiment needs metrics to measure the impact of the variations and to validate the hypothesis.</span></span> <span data-ttu-id="310a7-115">Suivez les étapes ci-dessous pour activer le calcul des métriques dans le service tiers à l'aide des événements de télémétrie en ligne de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="310a7-115">Follow the steps below to enable the computation of metrics in the third-party service using live telemetry events from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="310a7-116">Pour paramétrer vos métriques de réussite, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="310a7-116">To set up your success metrics, follow these steps.</span></span>

1. <span data-ttu-id="310a7-117">Dans le générateur de site Commerce, sélectionnez **Pages** dans le volet de navigation de gauche, puis sélectionnez la page pour laquelle vous souhaitez collecter des métriques.</span><span class="sxs-lookup"><span data-stu-id="310a7-117">In Commerce site builder, select **Pages** in the left navigation pane, and then select the page that you want to collect metrics for.</span></span> 
1. <span data-ttu-id="310a7-118">Accédez à la section **ID d'événement à suivre** dans le volet des propriétés situé à droite de la page ou du module dont vous souhaitez effectuer le suivi.</span><span class="sxs-lookup"><span data-stu-id="310a7-118">Go to the **Event IDs to track** section in the right property pane of the page or module you want to track.</span></span>
1. <span data-ttu-id="310a7-119">Sélectionnez **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="310a7-119">Select **View**.</span></span> <span data-ttu-id="310a7-120">Une liste de tous les ID d'événement s'affiche.</span><span class="sxs-lookup"><span data-stu-id="310a7-120">A list of all event IDs is displayed.</span></span> <span data-ttu-id="310a7-121">Copiez l'événement dont vous souhaitez effectuer le suivi et collez la clé d'événement à l'emplacement désigné dans le service tiers.</span><span class="sxs-lookup"><span data-stu-id="310a7-121">Copy the event you want to track, and paste the event key into the designated location in the third-party service.</span></span> <span data-ttu-id="310a7-122">Si vous avez besoin de plusieurs événements, copiez les clés une par une.</span><span class="sxs-lookup"><span data-stu-id="310a7-122">If you need more than one event, copy the keys one at a time.</span></span> 
    - <span data-ttu-id="310a7-123">Pour savoir comment afficher tous les événements et attributs disponibles, y compris les affichages de pages et le suivi des revenus, consultez [Événements des composants Commerce pour les diagnostics et le dépannage](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="310a7-123">To learn how to view all of the available events and attributes, including page views and revenue tracking, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>
1. <span data-ttu-id="310a7-124">Prenez toutes les autres mesures requises dans le service tiers pour procéder au suivi des métriques.</span><span class="sxs-lookup"><span data-stu-id="310a7-124">Take any other steps for tracking metrics as required in the third-party service.</span></span>

## <a name="previous-step"></a><span data-ttu-id="310a7-125">Étape précédente</span><span class="sxs-lookup"><span data-stu-id="310a7-125">Previous step</span></span>
[<span data-ttu-id="310a7-126">Identifier une hypothèse et déterminer les métriques pour une expérience</span><span class="sxs-lookup"><span data-stu-id="310a7-126">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md) 


## <a name="next-step"></a><span data-ttu-id="310a7-127">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="310a7-127">Next step</span></span>
[<span data-ttu-id="310a7-128">Connecter et modifier une expérience</span><span class="sxs-lookup"><span data-stu-id="310a7-128">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)
