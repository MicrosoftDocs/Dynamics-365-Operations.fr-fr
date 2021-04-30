---
title: Générer et réviser les entités de paie
description: Cette rubrique décrit comment générer et examiner les entités de paie.
author: andreabichsel
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c6e043498d4e36e38575a16c6475a5edfef51fc6
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881983"
---
# <a name="generate-payroll-entities"></a><span data-ttu-id="78b92-103">Générer les entités de paie</span><span class="sxs-lookup"><span data-stu-id="78b92-103">Generate payroll entities</span></span>

<span data-ttu-id="78b92-104">Utilisez cette fonction OData pour générer les entités nécessaires à l'intégration de la paie.</span><span class="sxs-lookup"><span data-stu-id="78b92-104">Use this OData function to generate the entities needed for payroll integration.</span></span> <span data-ttu-id="78b92-105">Si des modifications sont apportées à ces entités dans Human Resources, telles que l'ajout de champs personnalisés, cette fonction peut être appelée à nouveau pour actualiser les métadonnées de chaque entité.</span><span class="sxs-lookup"><span data-stu-id="78b92-105">If any changes are made to these entities in Human Resources, such as adding custom fields, this function can be called again to refresh the metadata of each entity.</span></span> <span data-ttu-id="78b92-106">La réponse contient un ID d'opération que vous pouvez surveiller afin de savoir quand le processus de génération est terminé.</span><span class="sxs-lookup"><span data-stu-id="78b92-106">The response contains an operation ID that you can monitor so you know when the generation process has completed.</span></span>

<span data-ttu-id="78b92-107">**Demande**</span><span class="sxs-lookup"><span data-stu-id="78b92-107">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/RefreshHumanResourcesVirtualEntities
```

<span data-ttu-id="78b92-108">**corps**</span><span class="sxs-lookup"><span data-stu-id="78b92-108">**body**</span></span>

```json
{
    "PhysicalNames" : ["PayrollEmployeeEntity", "HcmWorkerBaseEntity", "PayrollPositionEntity", "PayrollPositionJobEntity", "PayrollWorkerAddressEntity", "HcmJobDetailEntity", "HcmCompFixedPlanTableEntity", "PayrollFixedCompensationPlanEntity", "HcmEmploymentDetailEntity"]
}
```

<span data-ttu-id="78b92-109">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="78b92-109">**Response**</span></span>

```json
{
    "AsyncOperationId": "8b98d338-f939-4c86-9a91-80b76b6ab2ea"
}
```

## <a name="review-payroll-entities"></a><span data-ttu-id="78b92-110">Réviser les entités de paie</span><span class="sxs-lookup"><span data-stu-id="78b92-110">Review payroll entities</span></span>

<span data-ttu-id="78b92-111">Utilisez cette API pour récupérer une liste des entités qui ont été générées avec succès et sont prêtes à être utilisées.</span><span class="sxs-lookup"><span data-stu-id="78b92-111">Use this API to retrieve a list of the entities that have been successfully generated and are ready for use.</span></span>

<span data-ttu-id="78b92-112">**Demande**</span><span class="sxs-lookup"><span data-stu-id="78b92-112">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hrvirtualentitycatalogs?$filter=mshr_hasbeengenerated eq true
```

<span data-ttu-id="78b92-113">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="78b92-113">**Response**</span></span>

```json
{
      "value": [
        {
            "mshr_physicalname": "PayrollWorkerAddressEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-1c00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmJobDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6400-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmCompFixedPlanTableEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6b00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollEmployeeEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6d00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmEmploymentDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-7e00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollFixedCompensationPlanEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-9300-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmWorkerBaseEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-c000-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollPositionJobEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-e700-005001000000",
            "mshr_refresh": null
        }
    ]
}
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]