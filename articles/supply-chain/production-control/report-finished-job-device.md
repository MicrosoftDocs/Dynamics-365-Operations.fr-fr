---
title: Déclarer comme terminé à un emplacement qui ne fait pas l'objet d'un contrôle de contenant depuis le périphérique pour le bon de travail
description: Cette rubrique décrit le processus pour compléter les produits finis sur un ordre de fabrication dans le stock lorsqu'un contenant contrôle l'emplacement.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: 74e1e30f5afe51cd0ecec2530ffcb9a59eec5fee
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367243"
---
# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="d7375-103">Déclarer comme terminé à un emplacement qui ne fait pas l'objet d'un contrôle de contenant depuis le périphérique pour le bon de travail</span><span class="sxs-lookup"><span data-stu-id="d7375-103">Report as finished to a license plate controlled location from the Job card device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7375-104">Le processus nommé Déclaration de fin complète des produits finis sur un ordre de fabrication au stock.</span><span class="sxs-lookup"><span data-stu-id="d7375-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="d7375-105">Si le produit fini est activé pour les processus avancés d'entrepôt, le produit est déclaré comme fini à un emplacement appelé l'emplacement de sortie de production.</span><span class="sxs-lookup"><span data-stu-id="d7375-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="d7375-106">Pour plus d'informations sur le paramétrage de l'emplacement de sortie de production, voir [Emplacement de sortie de production](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="d7375-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="d7375-107">Si l'emplacement de sortie de production est contrôlé par le contenant, un contenant doit être fourni lors du signalement comme terminé.</span><span class="sxs-lookup"><span data-stu-id="d7375-107">If the production output location is license plate controlled, then a license plate must be provided when reporting as finished.</span></span> <span data-ttu-id="d7375-108">Le champ **Contenant** est visible sous l'invite **Saisie de l'avancement** sur la page **Périphérique des bons de travail**.</span><span class="sxs-lookup"><span data-stu-id="d7375-108">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="d7375-109">Le champ n'est visible que sur l'invite **Signaler les progrès** lorsque vous créez un rapport sur la dernière opération de l'ordre de fabrication et que l'article de l'ordre de fabrication est activé pour les processus de gestion de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d7375-109">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order and the item for the production order is enabled for the warehouse management processes.</span></span>

<span data-ttu-id="d7375-110">Il existe deux options pour fournir le contenant :</span><span class="sxs-lookup"><span data-stu-id="d7375-110">There are two options for providing the license plate:</span></span>

- <span data-ttu-id="d7375-111">L'utilisateur sélectionne un contenant existant dans le champ de contenant.</span><span class="sxs-lookup"><span data-stu-id="d7375-111">The user selects an existing license plate in the license plate field.</span></span>
- <span data-ttu-id="d7375-112">Le contenant est automatiquement généré à partir d'une souche de numéros et par défaut dans le champ du contenant.</span><span class="sxs-lookup"><span data-stu-id="d7375-112">The license plate is automatically generated from a number sequence and defaulted to the license plate field.</span></span>

<span data-ttu-id="d7375-113">L'option de génération automatique de contenant est configurée en sélectionnant l'option **Générer un contenant** sur la page **Configurer le bon de travail pour les périphériques**.</span><span class="sxs-lookup"><span data-stu-id="d7375-113">The option to have the license plate generated automatically is configured by selecting the option **Generate license plate** on the **Configure job card for devices** page.</span></span>
