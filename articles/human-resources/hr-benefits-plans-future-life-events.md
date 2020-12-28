---
title: Configuration des événements de vie futurs
description: Vous pouvez planifier des événements de vie futurs dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 78c65faa4ae0f428184700a912998e9dded026c5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418457"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="a2c14-103">Configuration des événements de vie futurs</span><span class="sxs-lookup"><span data-stu-id="a2c14-103">Configure future life events</span></span>

<span data-ttu-id="a2c14-104">Vous pouvez planifier des événements de vie futurs dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a2c14-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="a2c14-105">Dans l'espace de travail **Gestion des avantages**, sous **Configuration**, sélectionnez **Événement de vie futurs**.</span><span class="sxs-lookup"><span data-stu-id="a2c14-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="a2c14-106">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a2c14-106">Select **New**.</span></span>

3. <span data-ttu-id="a2c14-107">Spécifiez les valeurs les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="a2c14-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="a2c14-108">Champ</span><span class="sxs-lookup"><span data-stu-id="a2c14-108">Field</span></span> | <span data-ttu-id="a2c14-109">Description</span><span class="sxs-lookup"><span data-stu-id="a2c14-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="a2c14-110">Date de l'événement de vie</span><span class="sxs-lookup"><span data-stu-id="a2c14-110">Life event date</span></span> | <span data-ttu-id="a2c14-111">Le système traite tous les événements de la période d'inscription qui se produisent jusqu'à cette date.</span><span class="sxs-lookup"><span data-stu-id="a2c14-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="a2c14-112">Événement de vie enregistré</span><span class="sxs-lookup"><span data-stu-id="a2c14-112">Life event logged</span></span> | <span data-ttu-id="a2c14-113">Date et heure de consignation de l'événement de vie.</span><span class="sxs-lookup"><span data-stu-id="a2c14-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="a2c14-114">Type de journal</span><span class="sxs-lookup"><span data-stu-id="a2c14-114">Log type</span></span> | <span data-ttu-id="a2c14-115">Indique si l'action est l'une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="a2c14-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="a2c14-116">- **Mettre à jour** – modification à un enregistrement existant qui effectue le suivi des événements de vie</span><span class="sxs-lookup"><span data-stu-id="a2c14-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="a2c14-117">- **Insérer** - création d'un nouvel enregistrement d'événement de vie</span><span class="sxs-lookup"><span data-stu-id="a2c14-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="a2c14-118">ID du type d'événement de vie</span><span class="sxs-lookup"><span data-stu-id="a2c14-118">Life event type ID</span></span> | <span data-ttu-id="a2c14-119">Identificateur unique pour le type d'événement de vie.</span><span class="sxs-lookup"><span data-stu-id="a2c14-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="a2c14-120">Type d'événement de vie</span><span class="sxs-lookup"><span data-stu-id="a2c14-120">Life event type</span></span> | <span data-ttu-id="a2c14-121">Catalyseur pour mettre à jour l'inscription aux avantages d'un employé.</span><span class="sxs-lookup"><span data-stu-id="a2c14-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="a2c14-122">Pour plus de détails, voir la section Déclencheurs d'événements de vie.</span><span class="sxs-lookup"><span data-stu-id="a2c14-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="a2c14-123">État </span><span class="sxs-lookup"><span data-stu-id="a2c14-123">Status</span></span> | <span data-ttu-id="a2c14-124">Indique si l'événement de vie a été traité ou non.</span><span class="sxs-lookup"><span data-stu-id="a2c14-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="a2c14-125">Ligne</span><span class="sxs-lookup"><span data-stu-id="a2c14-125">Line</span></span> | <span data-ttu-id="a2c14-126">Numéro de ligne du futur événement de vie.</span><span class="sxs-lookup"><span data-stu-id="a2c14-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="a2c14-127">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a2c14-127">Select **Save**.</span></span> 
