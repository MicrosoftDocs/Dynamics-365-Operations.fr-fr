---
title: Emplacement de la demande de recrutement
description: Cet article décrit l’entité Emplacement de la demande de recrutement pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: d31af9ab62db310b89fbc7a2d7099621b59a356d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893814"
---
# <a name="recruiting-request-location"></a>Emplacement de la demande de recrutement


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’entité Emplacement de la demande de recrutement pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmrecruitingrequestlocationentity

### <a name="description"></a>Description

Liste des emplacements définis comme tels où les employés recrutés travailleront une fois embauchés. Ce sont des emplacements créés à travers des entités juridiques.

### <a name="json-representation"></a>Représentation JSON

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID emplacement**<br>mshr_locationid<br>*Chaîne* | Écriture unique<br>Requis | Identificateur généré par le système, lisible par l’utilisateur pour l’emplacement de recrutement. |
| **Emplacement de la demande de recrutement**<br>mshr_recruitingrequestlocationid<br>*Chaîne* | Écriture unique<br>Requis | Identificateur unique défini par l’utilisateur pour l’emplacement de recrutement. |
| **ID de l’entité Emplacement de la demande de recrutement**<br>mshr_hcmrecruitingrequestlocationentityid<br>*GUID* | Lecture seule<br>Requis | Identificateur unique généré par le système pour le dossier d’emplacement de la demande de recrutement. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture/écriture<br>Requis | Description de l’emplacement. |
| **ID pays/région**<br>mshr_countryregionid<br>*Chaîne* | Lecture seule<br>Facultatif | Spécifie le pays ou la région où le candidat a la citoyenneté. |
| **Valeur de l’ID pays/région**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_logisticaddresscountryregionentityid de l’entité mshr_logisticsaddresscountryregionentity | Identificateur unique généré par le système du pays ou de la région de l’adresse. |
| **ZipCode**<br>mshr_zipcode<br>*Chaîne* | Lecture seule<br>Facultatif | Code postal. |
| **Rue**<br>mshr_street<br>*Chaîne* | Lecture seule<br>Facultatif | Nom de la rue. |
| **Ville**<br>mshr_city<br>*Chaîne* | Lecture seule<br>Facultatif | Ville. |
| **État**<br>mshr_state<br>*Chaîne* | Lecture seule<br>Facultatif | Région ou province. |
| **Département**<br>mshr_county<br>*Chaîne* | Lecture seule<br>Facultatif | Département. |
| **Téléphone**<br>mshr_telephone<br>*Chaîne* | Lecture/écriture<br>Facultatif | Numéro de téléphone de l’emplacement. |
| **Adresse e-mail**<br>mshr_email<br>*Chaîne* | Lecture/écriture<br>Facultatif | Adresse e-mail. |
| **InternetAddress**<br>mshr_internetaddress<br>*Chaîne* | Lecture/écriture<br>Facultatif | URL du site Web de l’emplacement. |
| **ID zone de données**<br>mshr_dataareaid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Spécifie l’entité juridique (société). |
| **Valeur de l’ID zone de données**<br>_mshr_dataareaid_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : cdm_companyid de l’entité cdm_company entity | Valeur GUID générée par le système identifiant l’entité juridique (société). |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
