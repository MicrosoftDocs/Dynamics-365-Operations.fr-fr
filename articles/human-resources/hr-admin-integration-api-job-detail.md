---
title: API Détails de la mission
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Détails de la mission dans Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 562b9f505311b6cfe505a76fc5c0a384eb641936
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054762"
---
# <a name="job-detail-api"></a><span data-ttu-id="2b542-103">API Détails de la mission</span><span class="sxs-lookup"><span data-stu-id="2b542-103">Job detail API</span></span>

<span data-ttu-id="2b542-104">Cette rubrique fournit des détails et un exemple de requête pour l’entité Détails de la mission dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2b542-104">This topic provides details and an example query for the Job detail entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="2b542-105">Propriétés</span><span class="sxs-lookup"><span data-stu-id="2b542-105">Properties</span></span>

| <span data-ttu-id="2b542-106">Propriété</span><span class="sxs-lookup"><span data-stu-id="2b542-106">Property</span></span><br><span data-ttu-id="2b542-107">**Nom physique**</span><span class="sxs-lookup"><span data-stu-id="2b542-107">**Physical name**</span></span><br><span data-ttu-id="2b542-108">**_Type_**</span><span class="sxs-lookup"><span data-stu-id="2b542-108">**_Type_**</span></span> | <span data-ttu-id="2b542-109">Cas d’emploi</span><span class="sxs-lookup"><span data-stu-id="2b542-109">Use</span></span> | <span data-ttu-id="2b542-110">Description</span><span class="sxs-lookup"><span data-stu-id="2b542-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="2b542-111">**ID tâche**</span><span class="sxs-lookup"><span data-stu-id="2b542-111">**Job ID**</span></span><br><span data-ttu-id="2b542-112">mshr_jobid</span><span class="sxs-lookup"><span data-stu-id="2b542-112">mshr_jobid</span></span><br><span data-ttu-id="2b542-113">*Chaîne*</span><span class="sxs-lookup"><span data-stu-id="2b542-113">*String*</span></span> | <span data-ttu-id="2b542-114">Lecture seule</span><span class="sxs-lookup"><span data-stu-id="2b542-114">Read-only</span></span><br><span data-ttu-id="2b542-115">Requis</span><span class="sxs-lookup"><span data-stu-id="2b542-115">Required</span></span> | <span data-ttu-id="2b542-116">ID unique d'un poste.</span><span class="sxs-lookup"><span data-stu-id="2b542-116">Unique ID for a job.</span></span> |
| <span data-ttu-id="2b542-117">**Seuil bas du prix du marché**</span><span class="sxs-lookup"><span data-stu-id="2b542-117">**Market price low threshold**</span></span><br><span data-ttu-id="2b542-118">mshr_marketpricelowthreshold</span><span class="sxs-lookup"><span data-stu-id="2b542-118">mshr_marketpricelowthreshold</span></span><br><span data-ttu-id="2b542-119">*Décimal*</span><span class="sxs-lookup"><span data-stu-id="2b542-119">*Decimal*</span></span> | | <span data-ttu-id="2b542-120">Valeur GUID générée par le système pour identifier le poste de manière unique.</span><span class="sxs-lookup"><span data-stu-id="2b542-120">A system-generated GUID value to uniquely identify the position.</span></span>  |
