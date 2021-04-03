---
title: Choisir une technologie d’intégration de données
description: Cet article fournit des informations sur l’intégration aux données gérées par Human Resources. Il décrit différentes technologies d’intégration pour vous aider à décider quelles technologies correspondent le mieux à vos besoins.
author: andreabichsel
manager: tfehr
ms.date: 02/28/2020
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
ms.openlocfilehash: b2bd8707d873955ec53dcaebb503a6c8e666d9f8
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465844"
---
# <a name="choose-a-data-integration-technology"></a>Choisir une technologie d’intégration de données

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article fournit des informations sur l’intégration aux données gérées par Dynamics 365 Human Resources. Il décrit différentes technologies d’intégration pour vous aider à décider quelles technologies correspondent le mieux à vos besoins.

## <a name="data-integration-background"></a>Arrière-plan de l’intégration des données

Les données d’entreprise sont un atout clé qui rend votre entreprise unique. Les données de votre entreprise sont très précieuses. Vous pouvez utiliser les relations entre les données collectées dans l’ensemble de votre entreprise pour améliorer les processus métier et Business Intelligence dans votre organisation. Nous nous efforçons de fournir un accès facile, sécurisé et stable à vos données d’entreprise, quel que soit le système d’où elles proviennent.

De tous temps, l’intégration de données entre plusieurs systèmes a été difficile.
Microsoft prend des mesures pour faciliter l’intégration des données, et un grand pas vers cet objectif est atteint grâce à [Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Human Resources fait de Dataverse l’interface publique préférée pour les données des ressources humaines. Au fil du temps, nous prévoyons que toutes les données les plus importantes gérées par les ressources humaines seront affichées dans Dataverse. Nous recommandons Dataverse comme la technologie de choix pour la plupart des applications d’intégration.

Nous réalisons que Dataverse peut ne pas encore contenir toutes les données dont votre application a besoin. Nous réalisons également que le calendrier de votre projet pourrait nécessiter une technologie alternative. Assurez-vous de nous faire savoir quand Dataverse ne répond pas à vos besoins d’intégration.

## <a name="integration-technologies"></a>Technologies d’intégration

Les sections suivantes décrivent les différentes technologies d’intégration de données disponibles pour une utilisation avec Human Resources.

### <a name="dataverse-tables"></a>Tables Dataverse

Dataverse est l’interface de données publique préférée pour Human Resources. Elle est issue de la plate-forme Dynamics 365 XRM, qui est utilisée par les solutions [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement).

Dataverse offre une plateforme et une API pour les tables de données. Lorsque vous déployez Human Resources, il se connecte à une instance Dataverse. Les entités pour les données Human Resources se déploient dans cette instance Dataverse. Les tables et leurs données sont disponibles pour toute application pouvant se connecter à l’instance Dataverse. Human Resources synchronise les données vers et depuis les tables Dataverse.

> [!NOTE]
> Les entités Human Resources correspondent aux tables Dataverse. Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

Lorsque les tables de données requises par vos applications d’intégration sont dans Dataverse, vous pouvez utiliser pleinement [Dataverse et les API qu’il prend en charge](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Parmi les API prises en charge se trouve l’[API Web Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), qui fournit une implémentation OData pour accéder aux données Dataverse.

Les tables Dataverse et leurs API associées sont la meilleure option pour accéder aux données de Human Resources à partir d’applications Web, de services Web/d’API et de toute autre application qui se connecte aux flux OData.

> [!NOTE]
> La décision de faire de Dataverse l’interface de données préférée pour Human Resources étant relativement récente, vous pouvez constater que les entités de données de Human Resources dont vous avez besoin pour votre intégration ne sont pas encore disponibles dans Dataverse.
> </br>
> Pour une liste des entités Human Resources disponibles dans Dataverse, voir [Human Resources et Dataverse](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities).
> </br>
> Si les entités de Human Resources requises pour votre intégration ne sont pas encore disponibles, vous devrez attendre que les entités de données soient disponibles ou vous devrez utiliser l’une des autres technologies d’intégration décrites ci-dessous.
> </br>
> Par défaut, l’intégration de Dataverse est désactivée dans les nouveaux environnements qui ne comprennent pas les données de démonstration fournies. Elle est activée dans les nouveaux environnements qui incluent des données de démonstration, et les environnements commencent la synchronisation des données provisionnées. Lorsque votre environnement est prêt à synchroniser les données, vous pouvez activer l’intégration.

### <a name="dmfdixf-entities"></a>Entités DMF/DIXF

Human Resources, basée principalement sur la même plateforme que les applications Finance and Operations, fournit un [cadre de gestion des données (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json). DMF est également appelé Data Import Export Framework (DIXF). Human Resources propose un ensemble d’entités de données que vous pouvez utiliser pour importer et exporter des données des ressources humaines. Tandis que les tables Dataverse sont l’interface d’intégration de données préférée pour Human Resources, les entités DMF seront toujours utiles dans certaines circonstances, telles que :

- Les tables Dataverse ne sont pas encore disponibles.

- L’intégration nécessite des capacités d’importation / exportation de données en masse hautes performances.

> [!NOTE]
> Les entités Human Resources correspondent aux tables Dataverse. Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

Les entités DMF fournissent actuellement la couverture de données la plus complète pour les données de Human Resources.

DMF n’est pas approprié pour les intégrations en temps réel, par exemple lorsque vous avez besoin d’une rétroaction immédiate de l’utilisateur dans une interface utilisateur. Les opérations de package sont des traitements par lots prévus et ont souvent une latence minimale de 1 à 2 minutes avant que le service de traitement par lots ne prélève la tâche pour exécution, plus le temps nécessaire pour exécuter l’opération d’importation/d’exportation.

DMF peut être la meilleure option lorsqu’un débit élevé est requis (comme une importation / exportation planifiée de plusieurs milliers d’enregistrements).

> [!NOTE]
> DMF n’est pas disponible pour Attract et Onboard.

### <a name="dmf-package-rest-api"></a>API REST DMF Package

Le DMF fournit une [API REST](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) pour manipuler des paquets de données. Cette API peut être utilisée pour interagir par programmation avec le DMF, permettant des actions telles que :

- L’importation d’un paquet de données.

- L’exportation d’un paquet de données.

- La vérification de l’état d’une opération d’importation / exportation.

L’API REST DMF Package est entièrement prise en charge dans Human Resources.

### <a name="azure-sql-db-byod"></a>BDD Azure SQL (BYOD)

DMF fournit en outre une fonctionnalité puissante (connue sous le nom [Apportez votre propre base de données](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database), ou BYOD) qui permet à Human Resources d’exporter des données vers votre propre base de données SQL Microsoft Azure. Cette capacité offre une énorme flexibilité. Lorsque les données sont présentes dans votre propre base de données SQL, vous pouvez utiliser n’importe quelle application ou middleware pouvant se connecter à une banque de données SQL.

BYOD est principalement une solution en lecture seule. Bien que vous puissiez manipuler et stocker les données que vous souhaitez dans la base de données SQL Azure (comme pour les mashups de données), les données stockées dans la base de données SQL Azure ne seront pas synchronisées avec Human Resources.

Le BYOD est approprié pour les solutions de reporting, les intégrations de données, les mashups de données, comme source de données pour un pipeline [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/).

> [!NOTE]
> BYOD n’est pas disponible pour Attract et Onboard.

### <a name="odata-enabled-entities"></a>Entités compatibles OData

La plupart des entités DMF sont également activées pour l’accès via le service de données Human Resources (OData). La documentation fournie pour le [service OData de Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) s’applique à Human Resources, sauf pour la création de vos propres entités exposées à OData.

Tandis que Dataverse et l’implémentation OData fournie par Dataverse (à travers l’[API Web Dynamics 365](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) est préférable au service de données de Human Resources, le service de données de Human Resources a actuellement une couverture d’entité plus complète pour les données Human Resources.

### <a name="excel-add-in"></a>Complément Excel

Le [Complément Excel](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) utilise des entités compatibles OData sous la surface. Il fournit un moyen pratique pour un utilisateur final de récupérer et de modifier des données de Human Resources via l’interface utilisateur Excel familière.

Le complément Excel est approprié pour les importations / exportations de données ad hoc par des experts du domaine métier. Pour une intégration de données récurrente qui nécessite une automatisation programmatique, une autre technologie d’intégration sera plus appropriée.

### <a name="data-integrator"></a>Data Integrator

Vous pouvez utiliser le [Service d’intégrateur de données](https://docs.microsoft.com/powerapps/administrator/data-integrator) pour intégrer des données vers et depuis Dataverse. L’intégrateur de données peut être utilisé pour définir des projets d’intégration (souvent basés sur des modèles prédéfinis que les développeurs d’applications ont adaptés à des intégrations spécifiques). Vous pouvez planifier les projets d’intégration pour s’exécuter automatiquement selon un calendrier récurrent ou être exécutés manuellement.

Les projets Data Integrator conviennent aux intégrations par lots Dataverse. Ils constituent un choix parfait pour les intégrations entre la famille d’applications Dynamics 365. À titre d’exemple, Microsoft fournit un modèle d’intégration de données qui peut être utilisé pour intégrer les données de Human Resources dans Dynamics 365 Finance. Vous pouvez en savoir plus sur le modèle dans [Intégration depuis Dynamics 365 Human Resources à Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

Data Integrator prend en charge [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) via sa [Fonction de requête avancée](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering). Power Query fournit un filtrage et une transformation des données puissants et flexibles, y compris le langage de formule M enrichi. Vous connaissez probablement déjà Power Query si vous avez développé des rapports Power BI.

## <a name="deciding-on-an-integration-technology"></a>Décider d’une technologie d’intégration

Avec autant de technologies d’intégration différentes disponibles, il peut parfois être difficile de décider de l’approche d’intégration à utiliser. À mesure que la couverture des données dans Dataverse mûrit, la décision deviendra plus facile, Dataverse étant l’interface de données préférée dans la plupart des cas. Mais jusque-là, vous constaterez peut-être que Dataverse ne répond pas encore à vos besoins. Le tableau suivant permet de résumer certaines des caractéristiques clés des différentes options de technologie d’intégration.

| Technologie/Outil/API    | Intégrations récurrentes                   | Synchrone / asynchrone                    | Accès par programmation via une API        | Volumes de données appropriés                                   | Couverture de données                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Tables Dataverse           | Oui, en utilisant Data Integrator ou un middleware | Synchrone, asynchrone, par lots (via Data Integrator) | Oui, via l’API Web Dynamics 365 (OData) | Varie selon le cas d’utilisation (prend en charge la pagination pour une utilisation interactive) | Amélioration <sup>2</sup>                       |
| Entités DMF           | Oui, planifié via un middleware        | Asynchrone, par lots                                | Oui, via l’API REST DMF Package         | Élevée (des centaines de milliers d’enregistrements)                    | Élevée                                |
| API REST DMF Package   | Oui, planifié via un middleware        | Asynchrone, par lots                                | Oui                                       | Élevée (des centaines de milliers d’enregistrements)                    | L’API prend en charge toutes les entités DMF       |
| BYOD                   | Oui, planifiée par l’administrateur de Human Resources        | Asynchrone, par lots                                | Non<sup>3</sup>                                    | Élevée (des centaines de milliers d’enregistrements)                    | Prend en charge toutes les entités DMF           |
| Entités compatibles OData | Oui, en utilisant un middleware                    | Synchroniser                                        | Oui, via le service de données Human Resources (OData)  | Varie selon le cas d’utilisation (prend en charge la pagination pour une utilisation interactive) | Élevée                                |
| Complément Excel           | Non                                       | Synchroniser                                        | Non                                        | Moyen (des dizaines de milliers d’enregistrements)                      | Prend en charge toutes les entités compatibles OData |
| Data Integrator        | Oui, prévu dans Data Integrator        | Asynchrone, par lots                                | N°                                        | Varie selon le cas d’utilisation                                       | Prend en charge toutes les tables Dataverse           |

<sup>2</sup>Microsoft investit massivement dans l’augmentation de la couverture de données pour les tables Dataverse. Nous vous recommandons d’utiliser Dataverse lorsque la couverture est disponible. Actuellement, la couverture des données de Dataverse est faible par rapport aux entités DMF et OData.

<sup>3</sup>La base de données SQL est accessible par programme.


[!INCLUDE[footer-include](../includes/footer-banner.md)]