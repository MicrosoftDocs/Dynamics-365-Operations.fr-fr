---
title: Exemple de requête pour l’entité Candidat à l’embauche
description: Cette rubrique fournit un exemple de requête pour l’entité Candidat à l’embauche dans Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2fc08586914fd3815b0da062f24d83ac550302f
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467623"
---
# <a name="example-query-for-candidate-to-hire"></a><span data-ttu-id="0bd26-103">Exemple de requête pour l’entité Candidat à l’embauche</span><span class="sxs-lookup"><span data-stu-id="0bd26-103">Example query for Candidate to hire</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0bd26-104">Cette rubrique fournit un exemple de requête pour l’entité Candidat à l’embauche dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0bd26-104">This topic provides an example query for the Candidate to hire entity in Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="0bd26-105">Cette rubrique fournit un exemple illustrant comment vous pouvez utiliser les *insertions profondes* pour créer tous les détails d’un nouveau dossier de candidature en une seule opération d’API.</span><span class="sxs-lookup"><span data-stu-id="0bd26-105">This topic provides an example demonstrating how you can use *deep inserts* to create all the detail of a new candidate record in a single API operation.</span></span> <span data-ttu-id="0bd26-106">Pour plus d’informations sur les insertions profondes, voir [Créer des enregistrements d’entité associés en une seule opération](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).</span><span class="sxs-lookup"><span data-stu-id="0bd26-106">For more information about deep inserts, see [Create related entity records in one operation](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).</span></span>

<span data-ttu-id="0bd26-107">L’entité **mshr_hcmcandidatetohireentity** est unique en raison de sa relation avec l’entité **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="0bd26-107">The **mshr_hcmcandidatetohireentity** entity is unique because of its relationship to the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="0bd26-108">De nombreuses propriétés de **mshr_hcmcandidatetohireentity** (par exemple, **mshr_firstname**, **mshr_lastname**, et **mshr_birthdate**) sont dérivées du dossier **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="0bd26-108">Many of the properties on the **mshr_hcmcandidatetohireentity** (for example, **mshr_firstname**, **mshr_lastname**, and **mshr_birthdate**) are derived from the **mshr_dirpersonentity** record.</span></span> <span data-ttu-id="0bd26-109">Si vous publiez un nouveau dossier de candidature sur **mshr_hcmcandidatetohireentity** sans utiliser d’insertions profondes, vous pouvez définir des valeurs pour ces propriétés directement sur le dossier **mshr_hcmcandidatetohireentity**.</span><span class="sxs-lookup"><span data-stu-id="0bd26-109">If you post a new candidate record to **mshr_hcmcandidatetohireentity** without using deep inserts, you can define values for these properties directly on the **mshr_hcmcandidatetohireentity** record.</span></span> <span data-ttu-id="0bd26-110">Le dossier **mshr_dirpersonentity** associé est créé implicitement avec les valeurs définies pour les propriétés.</span><span class="sxs-lookup"><span data-stu-id="0bd26-110">The associated **mshr_dirpersonentity** record is created implicitly with the defined values for the properties.</span></span> <span data-ttu-id="0bd26-111">Vous pouvez ensuite créer tout autre enregistrement d’entité associé (comme des compétences ou une formation) en tant qu’appels d’API distincts.</span><span class="sxs-lookup"><span data-stu-id="0bd26-111">You can then create any other related entity records (such as skills or education) as separate API calls.</span></span>

<span data-ttu-id="0bd26-112">Si, toutefois, vous souhaitez utiliser des insertions profondes pour créer toutes les entités associées en une seule opération, les propriétés spécifiques à l’entité **mshr_dirpersonentity** doivent être définies à ce niveau imbriqué de l’opération.</span><span class="sxs-lookup"><span data-stu-id="0bd26-112">If, however, you want to use deep inserts to create all related entities in one operation, the properties specific to the **mshr_dirpersonentity** entity must be defined on that nested level of the operation.</span></span>

<span data-ttu-id="0bd26-113">Cet exemple montre comment créer un dossier de candidature, le dossier de la personne associée, ainsi que les compétences et la formation de la personne dans trois niveaux imbriqués à l’aide d’insertions profondes dans une seule opération d’API.</span><span class="sxs-lookup"><span data-stu-id="0bd26-113">This example shows how you can create a candidate record, the associated person record, and the person's skills and education in three nested levels using deep inserts in a single API operation.</span></span>

> [!NOTE]
> <span data-ttu-id="0bd26-114">L’exemple n’inclut pas toutes les propriétés de chacune des entités API.</span><span class="sxs-lookup"><span data-stu-id="0bd26-114">The example does not include all properties of each of the API entities.</span></span> <span data-ttu-id="0bd26-115">Il est simplifié à des fins de démonstration.</span><span class="sxs-lookup"><span data-stu-id="0bd26-115">It is simplified for demonstration purposes.</span></span>

<span data-ttu-id="0bd26-116">**Demande**</span><span class="sxs-lookup"><span data-stu-id="0bd26-116">**Request**</span></span>

```http

POST [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities
Content-Type: application/json; charset=utf-8
OData-MaxVersion: 4.0
OData-Version: 4.0
Accept: application/json

{
    "mshr_dataareaid": "usmf",
    "mshr_recruitingrequestid": "USMF-000141",
    "mshr_positionid": "000601",
    "mshr_iswillingtorelocate": 200000000,
    "mshr_availabilitydate": "2021-03-18",
    "mshr_comments": "Evelyn's experience is exactly what we need for this position.",
    "mshr_FK_Person_id":
        {
            "mshr_firstname": "Evelyn",
            "mshr_lastname": "Chambers",
            "mshr_namesequencedisplayas": "FirstMiddleLast",
            "mshr_FK_HcmPersonSkillEntity_Person":
            [
                {
                    "mshr_skillid": "CustFocus",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                },
                {
                    "mshr_skillid": "CashFlow",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                }
            ],
            "mshr_FK_HcmPersonEducationEntity_Person": [
                {
                    "mshr_creditbasis": 200000000,
                    "mshr_enddate": "2021-02-22T00:00:00Z",
                    "mshr_educationlevelid": "Bachelor",
                    "mshr_creditsearned": 0,
                    "mshr_startdate": "2017-02-21T00:00:00Z",
                    "mshr_creditscompleted": 0,
                    "mshr_educationinstitutionid": "Cottonwood Univ",
                    "mshr_educationdisciplineid": "Business Mgmt",
                    "mshr_durationunit": 200000000
                }              
            ]
        }
}
```

<span data-ttu-id="0bd26-117">**Réponse**</span><span class="sxs-lookup"><span data-stu-id="0bd26-117">**Response**</span></span>

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a><span data-ttu-id="0bd26-118">Voir également :</span><span class="sxs-lookup"><span data-stu-id="0bd26-118">See also</span></span>

[<span data-ttu-id="0bd26-119">Introduction à l’API d’intégration du système de suivi des candidats</span><span class="sxs-lookup"><span data-stu-id="0bd26-119">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]