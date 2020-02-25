---
title: Choisir une technologie d'intégration de données
description: Cet article fournit des conseils sur les différentes options d'intégration des données gérées par Human Resources, en décrivant les caractéristiques des différentes technologies d'intégration afin que les intégrateurs puissent prendre des décisions éclairées concernant les technologies qui correspondent le mieux à leurs besoins.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: f2de5dd41c00e6546b4a4feadaf5774430d572bb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029886"
---
# <a name="choose-a-data-integration-technology"></a>Choisir une technologie d'intégration de données

Dynamics 365 Human Resources gère les données métier utiles dans une variété de processus métier. Cet article fournit des conseils sur les différentes options d'intégration des données gérées par Human Resources, en décrivant les caractéristiques des différentes technologies d'intégration afin que les intégrateurs puissent prendre des décisions éclairées concernant les technologies qui correspondent le mieux à leurs besoins.

## <a name="data-integration-vision"></a>Vision de l'intégration des données

Microsoft considère les données d'entreprise comme un atout clé qui rend votre entreprise unique. Les données de votre entreprise sont très précieuses. Les données collectées et conservées par une partie de l'entreprise sont liées aux données collectées par une autre partie de l'entreprise, et ces relations peuvent être utilisées pour améliorer les processus métier et l'intelligence commerciale dans votre organisation. Fournir un accès facile, sécurisé et stable à vos données d'entreprise, quel que soit le système « propriétaire » des données, est un principe clé de la vision que nous avons pour l'intégration des données avec Human Resources.

De tous temps, l'intégration de données entre plusieurs systèmes a été difficile.
Microsoft prend des mesures pour faciliter l'intégration des données, et un grand pas vers cet objectif est atteint grâce à [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

À l'avenir, Human Resources font de Common Data Service l'interface publique préférée pour les données des ressources humaines. Au fil du temps, nous prévoyons que toutes les données les plus importantes gérées par les ressources humaines seront affichées dans Common Data Service. Nous recommandons Common Data Service comme la technologie de choix pour la plupart des applications d'intégration. Bien que nous soyons conscients que toutes les données dont votre application peut avoir besoin ne sont pas actuellement présentes dans Common Data Service, et que les délais de votre projet peuvent nécessiter une technologie alternative, veuillez nous informer lorsque Common Data Service ne répond pas à vos besoins d'intégration.

## <a name="integration-technologies"></a>Technologies d'intégration

Les sections suivantes décrivent les différentes technologies d'intégration de données disponibles pour une utilisation avec Human Resources.

### <a name="common-data-service-entities"></a>Entités Common Data Service

Common Data Service est l'interface de données publique préférée pour Human Resources. Common Data Service est construit sur une plate-forme mature, issue de la plate-forme « XRM » Dynamics 365, sur laquelle les solutions [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement) sont construites.

Common Data Service fournit une plate-forme pour les entités de données et une API pour accéder à ces entités. Lorsque Human Resources est déployé dans votre organisation, Human Resources est connecté à une instance Common Data Service et les entités qui gèrent les données de Human Resources sont déployées dans cette instance Common Data Service, en mettant les entités et leurs données à la disposition de toute application pouvant se connecter à l'instance Common Data Service. Selon les applications Human Resources que vous utilisez, Human Resources effectue des opérations de données directement sur les entités Common Data Service (c'est le cas pour Attract et Onboard) ou synchronise les données vers / depuis les entités Common Data Service.

Une fois que les entités de données qui exposent les données requises par vos applications d'intégration sont présentes dans Common Data Service, vous pouvez utiliser pleinement [Common Data Service et les API qu'il prend en charge](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Parmi les API prises en charge se trouve l'[API Web Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), qui fournit une implémentation OData pour accéder aux données Common Data Service.

Les entités Common Data Service et les API associées sont la meilleure option pour accéder aux données de Human Resources à partir d'applications Web, de services Web/d'API et de toute autre application qui se connecte aux flux OData.

> [!NOTE]
> Avec la décision de faire de Common Data Service l'interface de données préférée pour Human Resources étant relativement récent, vous pouvez constater que les entités de données de Human Resources dont vous avez besoin pour votre intégration ne sont pas encore disponibles dans Common Data Service<sup>1</sup>. Si les entités de Human Resources requises pour votre intégration ne sont pas encore disponibles, vous devrez attendre que les entités de données soient disponibles ou vous devrez utiliser l'une des autres technologies d'intégration décrites ci-dessous.
> 
> Par défaut, l'intégration de Common Data Service est désactivée dans les nouveaux environnements qui ne comprennent pas les données de démonstration fournies. Elle est activée dans les nouveaux environnements qui incluent des données de démonstration, et les environnements commencent la synchronisation des données provisionnées. Lorsque votre environnement est prêt à synchroniser les données, vous pouvez activer l'intégration.

<sup>1 </sup>Pour une liste des entités Human Resources disponibles dans Common Data Service, voir [Human Resources et Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities). Pour Attract et Onboard, toutes les entités sont disponibles dans Common Data Service.

### <a name="dmfdixf-entities"></a>Entités DMF/DIXF

Human Resources, construit principalement sur la même plate-forme que les applications Finance and Operations, fournit un [Cadre de gestion des données (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json), parfois également appelé Data Import Export Framework ou DIXF, et un ensemble d'entités de données qui peuvent être utilisées pour importer / exporter des données vers / depuis Human Resources. Tandis que les entités Common Data Service sont l'interface d'intégration de données préférée pour Human Resources, les entités DMF seront toujours utiles dans certaines circonstances, telles que :

- Les entités Common Data Service ne sont pas encore disponibles.

- L'intégration nécessite des capacités d'importation / exportation de données en masse hautes performances.

Les entités DMF fournissent actuellement la couverture de données la plus complète pour les données de Human Resources.

DMF n'est pas approprié pour les intégrations en temps réel (comme lorsque la rétroaction immédiate de l'utilisateur dans une interface utilisateur est requise), car les opérations de package sont des travaux par lots planifiés et auront souvent un minimum de 1 à 2 minutes de latence avant que le service par lots ne choisisse le travail pour exécution, plus le temps nécessaire pour terminer l'opération d'importation / exportation.

DMF peut être la meilleure option lorsqu'un débit élevé est requis (comme une importation / exportation planifiée de plusieurs milliers d'enregistrements).

> [!NOTE]
> DMF n'est pas disponible pour Attract et Onboard.

### <a name="dmf-package-rest-api"></a>API REST DMF Package

Le DMF fournit une [API REST](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) pour manipuler des paquets de données. Cette API peut être utilisée pour interagir par programmation avec le DMF, permettant des actions telles que :

- L'importation d'un paquet de données.

- L'exportation d'un paquet de données.

- La vérification de l'état d'une opération d'importation / exportation.

L'API REST DMF Package est entièrement prise en charge dans Human Resources : Core HR.

### <a name="azure-sql-db-byod"></a>BDD Azure SQL (BYOD)

DMF fournit en outre une fonctionnalité puissante (généralement connue sous le nom [Apportez votre propre base de données](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database), ou BYOD) qui permet à human Resources d'exporter des données vers votre propre base de données SQL Microsoft Azure. Cela offre une grande flexibilité, car lorsque les données sont présentes dans votre propre base de données SQL, vous pouvez utiliser n'importe quelle application ou middleware pouvant se connecter à une banque de données SQL.

Le BYOD doit généralement être considéré comme une solution en lecture seule. Bien que vous puissiez manipuler et stocker les données que vous souhaitez dans la base de données SQL Azure (comme pour les mashups de données), les données stockées dans la base de données SQL Azure ne seront pas synchronisées avec Human Resources.

Le BYOD est approprié pour les solutions de reporting, les intégrations de données, les mashups de données, comme source de données pour un pipeline [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/).

> [!NOTE]
> BYOD n'est pas disponible pour Attract et Onboard.

### <a name="odata-enabled-entities"></a>Entités compatibles OData

La plupart des entités DMF sont également activées pour l'accès via le service de données Human Resources (OData). La documentation fournie pour le [Service OData Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) s'applique généralement à Human Resources, bien que la documentation sur la création de vos propres entités exposées à OData ne s'applique pas.

Tandis que Common Data Service et l'implémentation OData fournie par Common Data Service (à travers l'[API Web Dynamics 365](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) est préférable au service de données de Human Resources, le service de données de Human Resources a actuellement une couverture d'entité plus complète pour les données Human Resources.

### <a name="excel-add-in"></a>Complément Excel

Le [Complément Excel](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) utilise des entités compatibles OData sous la surface. Il fournit un moyen pratique pour un utilisateur final de récupérer et de modifier des données de Human Resources via l'interface utilisateur Excel familière.

Le complément Excel est approprié pour les importations / exportations de données ad hoc par des experts du domaine métier. Pour une intégration de données récurrente qui nécessite une automatisation programmatique, une autre technologie d'intégration sera plus appropriée.

### <a name="data-integrator"></a>Data Integrator

L'expérience de l'administrateur Common Data Service fournit un [Service d'intégrateur de données](https://docs.microsoft.com/powerapps/administrator/data-integrator) qui peut être utilisé pour les intégrations de données vers / depuis Common Data Service. L'intégrateur de données peut être utilisé pour définir des projets d'intégration (souvent basés sur des modèles prédéfinis que les développeurs d'applications ont adaptés à des intégrations spécifiques). Les projets d'intégration peuvent être planifiés pour s'exécuter automatiquement selon un calendrier récurrent ou être exécutés manuellement.

Les projets Data Integrator conviennent aux intégrations par lots Common Data Service et constituent un excellent choix pour les intégrations entre la famille d'applications Dynamics 365. À titre d'exemple, Microsoft fournit un modèle d'intégration de données prêt à l'emploi qui peut être utilisé pour intégrer les données de Human Resources dans Dynamics 365 Finance. Pour plus d'informations, voir [Intégration de Dynamics 365 Human Resources dans Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

Data Integrator prend également en charge [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) (via sa [Fonction de requête avancée](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering)).
Power Query fournit un filtrage et une transformation des données puissants et flexibles, y compris le langage de formule M riche, et sera probablement familier à ceux qui ont de l'expérience dans le développement de rapports Power BI.

## <a name="deciding-on-an-integration-technology"></a>Décider d'une technologie d'intégration

Avec autant de technologies d'intégration différentes disponibles, il peut parfois être difficile de décider de l'approche d'intégration à utiliser. Au fil du temps, et en particulier à mesure que la couverture des données dans Common Data Servicemûrit, la décision deviendra plus facile, avec Common Data Service étant l'interface de données préférée dans la plupart des cas. Mais jusque-là, vous constaterez peut-être que Common Data Service ne répond pas encore à vos besoins. Le tableau suivant permet de résumer certaines des caractéristiques clés des différentes options de technologie d'intégration.

| Technologie/Outil/API    | Intégrations récurrentes                   | Synchrone / asynchrone                    | Accès par programmation via une API        | Volumes de données appropriés                                   | Couverture de données                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Entités Common Data Service           | Oui, en utilisant Data Integrator ou un middleware | Synchrone, asynchrone, par lots (via Data Integrator) | Oui, via l'API Web Dynamics 365 (OData) | Varie selon le cas d'utilisation (prend en charge la pagination pour une utilisation interactive) | Amélioration <sup>2</sup>                       |
| Entités DMF           | Oui, planifié via un middleware        | Asynchrone, par lots                                | Oui, via l'API REST DMF Package         | Élevée (des centaines de milliers d'enregistrements)                    | Élevée                                |
| API REST DMF Package   | Oui, planifié via un middleware        | Asynchrone, par lots                                | Oui                                       | Élevée (des centaines de milliers d'enregistrements)                    | L'API prend en charge toutes les entités DMF       |
| BYOD                   | Oui, planifiée par l'administrateur de Human Resources        | Asynchrone, par lots                                | Non<sup>3</sup>                                    | Élevée (des centaines de milliers d'enregistrements)                    | Prend en charge toutes les entités DMF           |
| Entités compatibles OData | Oui, en utilisant un middleware                    | Synchroniser                                        | Oui, via le service de données Human Resources (OData)  | Varie selon le cas d'utilisation (prend en charge la pagination pour une utilisation interactive) | Élevée                                |
| Complément Excel           | Non                                       | Synchroniser                                        | Non                                        | Moyen (des dizaines de milliers d'enregistrements)                      | Prend en charge toutes les entités compatibles OData |
| Data Integrator        | Oui, prévu dans Data Integrator        | Asynchrone, par lots                                | Non                                        | Varie selon le cas d'utilisation                                       | Prend en charge toutes les entités Common Data Service           |

<sup>2</sup>Microsoft investit massivement dans l'augmentation de la couverture de données pour Common Data Service et recommande Common Data Service comme interface de données préférée lorsque la couverture est disponible. Actuellement, la couverture des données de Common Data Service est faible par rapport aux entités DMF et OData.

<sup>3</sup>La base de données SQL est accessible par programme.

## <a name="summary"></a>Synthèse

Les données de votre entreprise sont un atout précieux, mais leur valeur peut être considérablement diminuée s'il est difficile d'utiliser les données à vos fins spécifiques (telles que les rapports, les mashups de données ou les applications personnalisées). Dynamics 365 Human Resources fournit plusieurs technologies pour travailler avec vos données en dehors de l'interface utilisateur de l'application Human Resources (UI), permettant aux applications d'intégration d'accéder aux données. Cette rubrique a décrit les technologies d'intégration disponibles et certaines de leurs principales caractéristiques. Ces informations devraient vous aider à prendre de meilleures décisions sur les approches à exploiter pour vos projets d'intégration.

