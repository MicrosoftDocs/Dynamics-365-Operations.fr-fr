---
title: Vue d'ensemble du développement
description: Ce guide du développeur fournit une référence à l'API et aux champs personnalisés. Il fournit également des informations sur l'intégration avec d'autres applications.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 517febd7967350956a28dfd9d11e4042456c7da0
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115388"
---
# <a name="development-overview"></a><span data-ttu-id="339ed-104">Vue d'ensemble du développement</span><span class="sxs-lookup"><span data-stu-id="339ed-104">Development overview</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="339ed-105">Ce guide du développeur fournit une référence à l'API et aux champs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="339ed-105">This Developer Guide provides an API and custom fields reference.</span></span> <span data-ttu-id="339ed-106">Il fournit également des informations sur l'intégration avec d'autres applications.</span><span class="sxs-lookup"><span data-stu-id="339ed-106">It also provides information on integrating with other apps.</span></span>

- [<span data-ttu-id="339ed-107">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="339ed-107">Overview</span></span>](hr-developer-overview.md)

- [<span data-ttu-id="339ed-108">Extension avec Power Apps et Power Automate</span><span class="sxs-lookup"><span data-stu-id="339ed-108">Extend with Power Apps and Power Automate</span></span>](hr-developer-power-apps.md)

- [<span data-ttu-id="339ed-109">Entités Human Resources dans Dataverse</span><span class="sxs-lookup"><span data-stu-id="339ed-109">Human Resources entities in Dataverse</span></span>](hr-developer-entities.md)

- [<span data-ttu-id="339ed-110">Champs personnalisés</span><span class="sxs-lookup"><span data-stu-id="339ed-110">Custom fields</span></span>](hr-developer-custom-fields.md)

- <span data-ttu-id="339ed-111">Configurer l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="339ed-111">Set up data integration</span></span>
  - [<span data-ttu-id="339ed-112">Choisir une technologie d'intégration de données</span><span class="sxs-lookup"><span data-stu-id="339ed-112">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)
  - [<span data-ttu-id="339ed-113">Configuration de l'intégration Dataverse</span><span class="sxs-lookup"><span data-stu-id="339ed-113">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)
  - [<span data-ttu-id="339ed-114">Configurer l’intégration avec Finance</span><span class="sxs-lookup"><span data-stu-id="339ed-114">Configure integration with Finance</span></span>](hr-admin-integration-finance.md)
  - [<span data-ttu-id="339ed-115">Configurer l’intégration avec Dayforce</span><span class="sxs-lookup"><span data-stu-id="339ed-115">Configure integration with Dayforce</span></span>](hr-admin-integration-dayforce.md)
  - [<span data-ttu-id="339ed-116">Créer une application d’exportation de données récurrentes</span><span class="sxs-lookup"><span data-stu-id="339ed-116">Create a recurring data export app</span></span>](hr-admin-integration-recurring-data-export.md)
  - <span data-ttu-id="339ed-117">Intégration avec Office</span><span class="sxs-lookup"><span data-stu-id="339ed-117">Integrate with Office</span></span>
    - [<span data-ttu-id="339ed-118">Didacticiel pour l’intégration Office</span><span class="sxs-lookup"><span data-stu-id="339ed-118">Office integration tutorial</span></span>](../dev-itpro/office-integration/office-integration-tutorial.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="339ed-119">Mettre à jour des données d’entité dans Excel</span><span class="sxs-lookup"><span data-stu-id="339ed-119">Update entity data in Excel</span></span>](../dev-itpro/office-integration/use-excel-add-in.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="339ed-120">Créer des expériences Ouvrir dans Excel</span><span class="sxs-lookup"><span data-stu-id="339ed-120">Create Open in Excel experiences</span></span>](../dev-itpro/office-integration/office-integration-edit-excel.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="339ed-121">Résoudre les problèmes d’intégration Office</span><span class="sxs-lookup"><span data-stu-id="339ed-121">Troubleshoot Office integration</span></span>](../dev-itpro/office-integration/office-integration-troubleshooting.md?toc=/dynamics365/unified-operations/talent/toc.json)

- <span data-ttu-id="339ed-122">Référence de l'API d'entité</span><span class="sxs-lookup"><span data-stu-id="339ed-122">Entity API reference</span></span>
  - [<span data-ttu-id="339ed-123">Authentification</span><span class="sxs-lookup"><span data-stu-id="339ed-123">Authentication</span></span>](hr-developer-api-authentication.md)
  - <span data-ttu-id="339ed-124">Entités</span><span class="sxs-lookup"><span data-stu-id="339ed-124">Entities</span></span>
    - [<span data-ttu-id="339ed-125">MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="339ed-125">MyLeaveRequests</span></span>](hr-developer-api-myleaverequests-overview.md)
    - [<span data-ttu-id="339ed-126">Soumettre une demande d'absence au workflow</span><span class="sxs-lookup"><span data-stu-id="339ed-126">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)

## <a name="see-also"></a><span data-ttu-id="339ed-127">Voir également :</span><span class="sxs-lookup"><span data-stu-id="339ed-127">See also</span></span>

- [<span data-ttu-id="339ed-128">Nouveautés ou modifications dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="339ed-128">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)
- [<span data-ttu-id="339ed-129">Guide d'administrationl</span><span class="sxs-lookup"><span data-stu-id="339ed-129">Administrator Guide</span></span>](hr-admin-overview.md)
- [<span data-ttu-id="339ed-130">Guide de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="339ed-130">User Guide</span></span>](hr-hrpro-overview.md)
