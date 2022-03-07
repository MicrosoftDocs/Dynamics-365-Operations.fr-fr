---
title: Comparaison des fonctionnalités dans le cloud et sur site
description: La rubrique indique les fonctionnalités prises en charge dans le cloud et sur site.
author: sericks007
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 497061500660e41c8f82c73e5dd6c085810c9209
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910447"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Comparaison des fonctions dans le cloud et sur site

[!include [banner](../includes/banner.md)]

Cette rubrique affiche une comparaison des fonctionnalités disponibles dans le cloud ou sur site pour les applications suivantes :

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

Les informations relatives aux [fonctionnalités de développement et d’administration](cloud-prem-comparison.md#development-and-administration-features) sont incluses, également.

Les tableaux suivants décrivent les zones d’application. La prise en charge en cloud et local est répertorié pour la fonctionnalité dans son ensemble. Lorsque des fonctionnalités spécifiques diffèrent de la zone en général, les fonctionnalités sont répertoriées sur une ligne distincte dans la colonne Fonctionnalité.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **Secteur**             | **Fonction**                | **Cloud** | **Sur site** |
|---------------------|-----------------------------|-----------|-----------------|
| Conformité et certifications        |                                                                                           | Oui       | Oui             |
|                                      | Type de certification SOC 1 Type 1                                                                | Oui       | Non              |
| Intégration et gestion des données      |                                                                                           | Oui       | Oui             |
|                                      | Exportation des données vers votre propre entrepôt de données                                                    | Oui       | Oui             |
|                                      | Activation de l’exportation des mises à jour incrémentielles vers une entité de données                                 | Oui       | Oui             |
|                                      | Intégration de données                                                                         | Oui       | Oui             |
| Gestion des documents                  |                                                                                           | Oui       | Oui             |
| Gestion financière                 |                                                                                           | Oui       | Oui             |
| ?                                 |                                                                                           | Oui       | Non              |
| Ressources humaines                      |                                                                                           | Oui       | Oui             |
| Intelligence                         |                                                                                           | Oui       | Oui             |
|                                      | Gestion des états électroniques                                                                 | Oui       | Oui             |
|                                      | ER : Intégration avec LCS                                                                  | Oui       | Non              |
|                                      | ER : Intégration avec SharePoint                                                           | Oui       | Non              |
|                                      | ER : Intégration avec Regulatory Configuration Service (RCS)                              | Oui       | Non              |
|                                      | ER : Utilise le système de fichiers local comme stockage des configurations ER accessibles via les référentiel ER | N°        | Oui             |
|                                      | Intégration à PowerBI.com                                                              | Oui       | N°              |
|                                      | Intégration à PowerBI Desktop                                                          | N°        | Oui             |
|                                      | Espaces de travail analytiques                                                                     | Oui       | N°              |
|                                      | Processus métier intelligent : Recommandations                                             | Oui       | N°              |
|                                      | Création d’états Power BI avec OData à l’aide des outils Power BI Desktop ou Excel PowerQuery    | Oui       | N°              |
|                                      | SQL Server Reporting Services (SSRS) prend en charge la mise à l’échelle                                 | Oui       | Oui             |
|                                      | La télémétrie est transférée dans le cloud                                                   | Oui       | N°              |
| Lifecycle Services                   |                                                                                           | Oui       | Oui             |
|                                      | Processus métier configurables                                                           | Oui       | Non              |
| Localisations                        |                                                                                           | Oui       | Oui             |
| Application, espaces de travail et plateforme mobiles |                                                                                           | Oui       | Oui             |
| Intégration Office                   |                                                                                           | Oui       | Oui             |
| Administration d’organisation          |                                                                                           | Oui       | Oui             |
| Paie                              |                                                                                           | Oui       | Oui             |
|                                      | Dépôt direct                                                                            | Oui       | Non              |
| Gestion et comptabilité du projet    |                                                                                           | Oui       | Oui             |
| Sécurité                             |                                                                                           | Oui       | Oui             |
| Gestion des services                   |                                                                                           | Oui       | Oui             |
| Client Web                           |                                                                                           | Oui       | Oui             |
|                                      | Enregistreur de tâches – Enregistrer ou charger des enregistrements à partir de la bibliothèque BPM                         | Oui       | Non              |
| Support                              |                                                                                           | Oui       | Oui             |
|                                      | Accès au support via le menu Aide et support                                             | Oui       | Non              |
|                                      | Événements commerciaux                                                                           | Oui       | Oui (soit une connectivité Internet est requise, soit des points de terminaison personnalisés doivent être implémentés pour envoyer/recevoir des événements commerciaux dans l’intranet)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Secteur**                | **Fonction**             | **Cloud** | **Sur site** |
|-------------------------|-------------------|-----------|-----------------|
| Gestion des actifs                     |                                                                                           | Oui       | Oui             |
| Conformité et certifications        |                                                                                           | Oui       | Oui             |
|                                      | Type de certification SOC 1 Type 1                                                                | Oui       | N°              |
| Contrôle de gestion                      |                                                                                           | Oui       | Oui             |
|                                      | Pack de contenu Contrôle de gestion pour Power BI                                                 | Oui       | N°              |
|                                      | Espace de travail Contrôle de gestion pour application mobile                                                  | Oui       | N°              |
| Gestion des coûts                      |                                                                                           | Oui       | Oui             |
|                                      | Pack de contenu de gestion des coûts pour Power BI                                                 | Oui       | N°              |
| Intégration et gestion des données      |                                                                                           | Oui       | Oui             |
|                                      | Extension pilotée par la configuration                                                            | Oui       | N°              |
|                                      | Exportation des données vers votre propre entrepôt de données                                                    | Oui       | Oui             |
|                                      | Activation de l’exportation des mises à jour incrémentielles vers une entité de données                                 | Oui       | Oui             |
|                                      | Intégration de données                                                                         | Oui       | Oui             |
| Gestion des documents                  |                                                                                           | Oui       | Oui             |
| Affiche l’aide                                 |                                                                                           | Oui       | Non              |
| Intelligence                         |                                                                                           | Oui       | Oui             |
|                                      | Gestion des états électroniques                                                                 | Oui       | Oui             |
|                                      | ER : Intégration avec LCS                                                                  | Oui       | Non              |
|                                      | ER : Intégration avec SharePoint                                                           | Oui       | Non              |
|                                      | ER : Intégration avec Regulatory Configuration Service (RCS)                              | Oui       | Non              |
|                                      | ER : Utilise le système de fichiers local comme stockage des configurations ER accessibles via les référentiel ER | N°        | Oui             |
|                                      | Intégration à PowerBI.com                                                              | Oui       | N°              |
|                                      | Intégration à PowerBI Desktop                                                          | N°        | Oui             |
|                                      | Espaces de travail analytiques                                                                     | Oui       | N°              |
|                                      | Processus métier intelligent : Recommandations                                             | Oui       | N°              |
|                                      | Création d’états Power BI avec OData à l’aide des outils Power BI Desktop ou Excel PowerQuery    | Oui       | N°              |
|                                      | SQL Server Reporting Services (SSRS) prend en charge la mise à l’échelle                                 | Oui       | Oui             |
|                                      | La télémétrie est transférée dans le cloud                                                   | Oui       | N°              |
| Gestion des stocks                 |                                                                                           | Oui       | Oui             |
| Lifecycle Services                   |                                                                                           | Oui       | Oui             |
|                                      | Processus métier configurables                                                           | Oui       | Non              |
| Localisations                        |                                                                                           | Oui       | Oui             |
| Fabrication                        |                                                                                           | Oui       | Oui             |
| Planification et prévisions      |                                                                                           | Oui       | Oui             |
| Service Optimisation de la planification                |                                                                                           | Oui       | N°              |
| Application, espaces de travail et plateforme mobiles |                                                                                           | Oui       | Oui             |
| Intégration Office                   |                                                                                           | Oui       | Oui             |
| Administration d’organisation          |                                                                                           | Oui       | Oui             |
| Approvisionnements             |                                                                                           | Oui       | Oui             |
|                                      | Extraction du catalogue externe à partir de la demande d’achat                                   | Oui       | N°              |
|                                      | États Power BI sur l’analyse des dépenses et des achats                                                  | Oui       | N°              |
| Gestion des informations sur les produits       |                                                                                           | Oui       | Oui             |
| Données de produit générique                  |                                                                                           | Oui       | Oui             |
| Production                           |                                                                                           | Oui       | Oui             |
|                                      | États Power BI sur les performances de la production                                                   | Oui       | N°              |
| Gestion et comptabilité des projets    |                                                                                           | Oui       | Oui             |
| Ventes                                |                                                                                           | Oui       | Oui             |
|                                      | États Power BI sur les performances de rentabilité et de ventes                                      | Oui       | N°              |
| Sécurité                             |                                                                                           | Oui       | Oui             |
| Gestion des services                   |                                                                                           | Oui       | Oui             |
| Gestion de la chaîne d’approvisionnement.              |                                                                                           | Oui       | Oui             |
| Gestion du transport            |                                                                                           | Oui       | Oui             |
| Collaboration du fournisseur                 |                                                                                           | Oui       | N°              |
| Gestion des entrepôts                 |                                                                                           | Oui       | Oui             |
|                                      | Application d’entrepôt mobile                                                                      | Oui       | Oui             |
|                                      | États Power BI d’entrepôt                                                              | Oui       | N°              |
| Client Web                           |                                                                                           | Oui       | Oui             |
|                                      | Enregistreur de tâches – Enregistrer ou charger des enregistrements à partir de la bibliothèque BPM                         | Oui       | Non              |
| Support                              |                                                                                           | Oui       | Oui             |
|                                      | Accès au support via le menu Aide et support                                             | Oui       | Non              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

Pour afficher une liste des fonctionnalités disponibles dans les déploiements sur site, voir [Fonctionnalités Commerce disponibles dans les déploiements sur site](../../../commerce/retail-onprem.md).

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **Secteur**         | **Fonctionnalité**         | **Cloud** | **Sur site** |
|------------------|---------------------|-----------|-----------------|
| Tous les domaines des ressources humaines | Toutes les fonctionnalités des ressources humaines | Oui       | Non              |

## <a name="development-and-administration-features"></a>Fonctionnalités de développement et d’administration

| **Secteur**                   | **Fonctionnalité**                               | **Cloud** | **Sur site** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| Version et test             |                                           | Oui       | Oui             |
| Extensibilité              |                                           | Oui       | Oui             |
| Surveillance et télémétrie   |                                           | Oui       | Oui             |
| Compatibilité de plateforme     |                                           | Oui       | Oui             |
| Maintenance                  |                                           | Oui       | Oui             |
|                            | Environnements de maintenance                    | Oui       | N°              |
| Analyseur de suivi               |                                           | Oui       | Oui             |
| PerfTimer                  |                                           | Oui       | Oui\*           |
| Mettre à niveau                    |                                           | Oui       | Oui             |
|                            | Mettre à niveau                                   | Oui       | N°              |
|                            | Mise à niveau et prise en charge des versions précédentes | Oui       | N°              |
| Développement Visual Studio  |                                           | Oui       | Oui             |

\* Dans les environnements sur site, PerfTimer affiche uniquement les résultats pour le client.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
