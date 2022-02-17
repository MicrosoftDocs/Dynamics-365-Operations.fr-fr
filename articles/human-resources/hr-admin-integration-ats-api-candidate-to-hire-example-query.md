---
title: Exemple de requête pour l’entité Candidat à l’embauche
description: Cette rubrique fournit un exemple de requête pour l’entité Candidat à l’embauche dans Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: edb8687b9dae0afc1bc15a3a5c197e14e7e8cf1e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069219"
---
# <a name="example-query-for-candidate-to-hire"></a>Exemple de requête pour l’entité Candidat à l’embauche


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique fournit un exemple de requête pour l’entité Candidat à l’embauche dans Dynamics 365 Human Resources.

Cette rubrique fournit un exemple illustrant comment vous pouvez utiliser les *insertions profondes* pour créer tous les détails d’un nouveau dossier de candidature en une seule opération d’API. Pour plus d’informations sur les insertions profondes, voir [Créer des enregistrements d’entité associés en une seule opération](/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).

L’entité **mshr_hcmcandidatetohireentity** est unique en raison de sa relation avec l’entité **mshr_dirpersonentity**. De nombreuses propriétés de **mshr_hcmcandidatetohireentity** (par exemple, **mshr_firstname**, **mshr_lastname**, et **mshr_birthdate**) sont dérivées du dossier **mshr_dirpersonentity**. Si vous publiez un nouveau dossier de candidature sur **mshr_hcmcandidatetohireentity** sans utiliser d’insertions profondes, vous pouvez définir des valeurs pour ces propriétés directement sur le dossier **mshr_hcmcandidatetohireentity**. Le dossier **mshr_dirpersonentity** associé est créé implicitement avec les valeurs définies pour les propriétés. Vous pouvez ensuite créer tout autre enregistrement d’entité associé (comme des compétences ou une formation) en tant qu’appels d’API distincts.

Si, toutefois, vous souhaitez utiliser des insertions profondes pour créer toutes les entités associées en une seule opération, les propriétés spécifiques à l’entité **mshr_dirpersonentity** doivent être définies à ce niveau imbriqué de l’opération.

Cet exemple montre comment créer un dossier de candidature, le dossier de la personne associée, ainsi que les compétences et la formation de la personne dans trois niveaux imbriqués à l’aide d’insertions profondes dans une seule opération d’API.

> [!NOTE]
> L’exemple n’inclut pas toutes les propriétés de chacune des entités API. Il est simplifié à des fins de démonstration.

**Demande**

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

**Réponse**

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
