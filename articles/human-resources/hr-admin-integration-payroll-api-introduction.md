---
title: Présentation de l'API d'intégration de la paie
description: Cette rubrique décrit l'API d'intégration de la paie de Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a7be5ad42642de48ffdb2731a1300a953c5ede4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022761"
---
# <a name="payroll-integration-api-introduction"></a>Présentation de l'API d'intégration de la paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ce document décrit l'API d'intégration de la paie de Dynamics 365 Human Resources. L'API permet de rationnaliser de bout en bout les intégrations entre Human Resources et les systèmes de paie partenaires. L'expérience intégrée commence dans Human Resources avec le profil du collaborateur, le salaire et les déductions, et les informations sur les cotisations. Lorsque vous embauchez un collaborateur et que vous saisissez le profil et les informations de paie requis dans Human Resources, le système de paie extrait ces informations pour les utiliser lors du traitement de la paie. Toutes les mises à jour apportées aux informations du collaborateur ou de la paie sont également extraites pour être utilisées dans les cycles de paie ultérieurs.

![Flux d’intégration de la paie](media/hr-admin-integration-payroll-api-introduction-flow.png)

Pour permettre l’intégration, Human Resources comprend les composants suivants :

- Fonctionnalité pour marquer un collaborateur comme Prêt pour le paiement
- Une API d’intégration ouvrant la nouvelle fonctionnalité à l’intégration d’applications

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Cette API repose sur Microsoft Dataverse (auparavant Common Data Service). Toutes les interactions RESTful avec cette API se font via l’API Web Microsoft Dataverse, qui utilise OData. Cette API est un sous-ensemble de l’API Web Dataverse. L’API Web Dataverse définit des caractéristiques telles que l’authentification, les SLA, les lots, le contrôle de la concurrence et la gestion des erreurs.

Pour plus d’informations générales sur l’API Web Microsoft Dataverse :

- [Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)
- [Utiliser l’API Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)
- [Guide du développeur Microsoft Dataverse](/powerapps/developer/data-platform)

Cette documentation comprend des détails et des conseils pour les développeurs sur l'utilisation de l'API Web Dataverse, y compris les rubriques suivantes :

- [S'authentifier auprès de Microsoft Dataverse avec l'API Web](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [Effectuer des opérations à l'aide de l'API Web](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [Utiliser Postman avec l'API Web](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [Utiliser le suivi des modifications pour synchroniser les données avec des systèmes externes](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Tables virtuelles pour Human Resources dans Dataverse

Les points de terminaison de l’API d’intégration de la paie utilisent les capacités de la plateforme de table virtuelle de Microsoft Dataverse. Par défaut, les tables virtuelles et leurs points de terminaison d’API associés ne sont pas déployés pour les environnements Human Resources, ce qui permet aux organisations de déterminer quels points de terminaison OData seront exposés pour l’environnement. Pour utiliser l’API, les tables virtuelles des entités Ressources humaines doivent être générées pour l’environnement.

Pour plus d’informations sur la génération des tables virtuelles pour l’API, consultez [Configurer les tables virtuelles Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Modèle de données

Le diagramme suivant illustre les relations au sein de l’API. Plusieurs types ont des clés étrangères vers d’autres entités préexistantes dans Human Resources qui ne sont pas illustrées ici. Ce document fournit des informations sur les entités spécifiques aux scénarios d’intégration de la paie. Cependant, il existe de nombreuses autres entités dans l’API Web Dataverse pour Human Resources qui peuvent également être pertinentes pour votre intégration. Certaines de ces entités sont référencées dans des relations de clé étrangère ou des propriétés de navigation.

![Modèle de données de l’API d’intégration de la paie](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a>Collaborateur avec paie et entités associées

Entités :

- [Employé avec paie](hr-admin-integration-payroll-api-payroll-employee.md)
- [Adresse du collaborateur avec paie](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [Régime de rémunération fixe avec paie](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Tâche du poste de paie](hr-admin-integration-payroll-api-payroll-position-job.md)
- [Poste de paie](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a>Voir également :

[Générer et réviser les entités de paie](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[Configurer les paramètres de Human Resources](hr-setup-parameters.md)<br>
[Configurer les paramètres partagés de Human Resources](hr-setup-shared-parameters.md)<br>
[Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Utiliser l’API Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]