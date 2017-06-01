---
title: "Organisations et hiérarchies organisationnelles (Essentiel du commerce)"
description: "L&quot;essentiel du commerce comporte trois types d&quot;organisations internes que vous pouvez définir pour permettre à une organisation de réaliser un processus d&quot;entreprise ou d&quot;atteindre un objectif."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21251
ms.assetid: 2bfc6bfe-784b-42e8-8bf0-116e9f0a558e
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 17d434f5d49d544003ee7cb862391d88ac5c723a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="organizations-and-organizational-hierarchies-commerce-essentials"></a>Organisations et hiérarchies organisationnelles (Essentiel du commerce)

[!include[banner](includes/banner.md)]


L'essentiel du commerce comporte trois types d'organisations internes que vous pouvez définir pour permettre à une organisation de réaliser un processus d'entreprise ou d'atteindre un objectif. 

Une organisation est un groupe de personnes qui travaillent ensemble pour réaliser un processus entreprise ou atteindre un objectif. Une hiérarchie organisationnelle représente les relations entre les unités commerciales qui composent votre organisation.

## <a name="organizations"></a>Organisations
Dans Essentiel du commerce, vous pouvez définir les trois types suivants d'organisations internes : entités juridiques, sections et équipes. Dans Microsoft Dynamics AX, toutes les organisations internes sont des types de l'entité Partie. C'est pourquoi, ces organisations utilisent un carnet d'adresses pour stocker les informations d'adresse et de contact. Une partie (personne ou organisation) peut appartenir à un ou plusieurs carnets d'adresses.
### <a name="legal-entities"></a>Entités juridiques

Une entité juridique est une organisation qui dispose d'une structure juridique enregistrée ou légalement déclarée. Les entités juridiques peuvent passer des contrats juridiques et sont tenues de préparer des relevés faisant état de leurs performances. Une société est un type d'entité juridique dans Microsoft Dynamics AX et chaque entité juridique est associée à un ID société. Cette association existe, car un ID société, ou DataAreaId, est utilisé dans certaines modèles de données où les sociétés sont utilisées en tant que limite pour la sécurité des données. Les utilisateurs peuvent accéder aux données uniquement pour la société à laquelle ils sont actuellement connectés.

### <a name="operating-units"></a>Sections

Une section est une organisation utilisée pour partager le contrôle des ressources économiques et des processus opérationnels dans une société. Dans une section, les personnes ont la responsabilité d'optimiser l'utilisation des ressources rares, d'améliorer les processus et de justifier leurs performances. Dans Essentiel du commerce, les types d'unités opérationnelles incluent les centres de coût, les unités commerciales, les chaînes de valeur, les départements et les chaînes de vente au détail. Le tableau suivant fournit d'autres informations sur chaque type de section.
|                         |                                                                                         |                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Type d'unité opérationnelle** | **Description**                                                                         | **Objectif**                                                                                                                                 |
| Unité commerciale           | Section semi-autonome créée pour répondre aux objectifs commerciaux stratégiques. | Utilisée pour les états financiers basés sur les secteurs ou les lignes de produits que l'organisation gère indépendamment des entités juridiques. |
| Canal de vente au détail          | Une unité opérationnelle qui représente un magasin traditionnel.                             | Utilisé pour la gestion et le contrôle opérationnel d'un ou plusieurs magasins au sein d'une entité juridique ou entre plusieurs entités juridiques.                                                               |

## <a name="organizational-hierarchies"></a>Hiérarchies organisationnelles
Dans Essentiel du commerce, chaque hiérarchie est affectée à un objectif. L'objet d'une hiérarchie détermine les types d'organisations pouvant être inclus dans la hiérarchie. L'objet définit également dans quels scénarios d'application la hiérarchie peut être utilisée. Par exemple, une hiérarchie de ventes au détail peut servir à acheter et vendre des produits dans un magasin de vente au détail. Les organisations d'une hiérarchie peuvent partager des paramètres, des stratégies et des transactions. Une organisation peut hériter des paramètres de son organisation parent ou les remplacer. Cependant, les données principales partagées, telle que les produits et les carnets d'adresses, s'appliquent à l'ensemble de l'organisation et ne peuvent pas être remplacées pour les organisations individuelles.
### <a name="best-practices-for-setting-up-an-organization-in-a-hierarchy"></a>Pratiques recommandées en matière de configuration d'une organisation dans une hiérarchie

Les pratiques suivantes sont recommandées lorsque vous implémentez une hiérarchie d'organisation :
-   Créez un département pour spécifier l'intersection entre une entité juridique et une unité commerciale. Vous pouvez ensuite repositionner les données d'un département dans une entité juridique à des fins de génération d'états statutaires, ou dans une unité commerciale à des fins de génération d'états interne.
-   Dans une entité juridique unique, ne configurez pas plusieurs hiérarchies pour le même objet de hiérarchie.
-   Ne créez pas une hiérarchie pour chaque objet. Vous utilisez généralement une seule hiérarchie pour plusieurs objets. Par exemple, une hiérarchie de sections peut être affectée à tous les objets associés à une stratégie.
-   Créez des hiérarchies équilibrées. Dans une hiérarchie, tous les nœuds situés au même niveau par rapport au nœud racine sont définis en tant que niveau. Dans une hiérarchie équilibrée, un seul type de section peut avoir lieu à chaque niveau et la distance entre le nœud racine et chaque niveau est cohérent. S'il existe des niveaux intermédiaires entre un département et une entité juridique ou une unité commerciale, il se peut que des organisations fictives soient requises pour créer une hiérarchie équilibrée.
-   Ne configurez pas une hiérarchie distincte d'unités opérationnelles si la structure des entités juridiques correspond également à votre structure opérationnelle. Une hiérarchie mélangée d'entités juridiques et de sections peut servir les deux objets.
-   Avant de configurer des scénarios de restructuration majeurs, utilisez les dates d'effet de la hiérarchie pour réaliser une analyse des impacts et un test de contrôle.
-   Enregistrez une hiérarchie comme brouillon si vous pouvez modifier une hiérarchie avant de la publier.
-   Limitez le nombre d'utilisateurs disposant d'autorisations pour ajouter ou supprimer des organisations d'une hiérarchie dans un environnement de production. Ce nombre réduit permet d'éviter les erreurs coûteuses et la nécessité d'effectuer des corrections.

## <a name="retail-store-management"></a>Gestion du magasin de vente au détail
Le tableau suivant décrit les scénarios Essentiel du commerce où les hiérarchies d'organisation peuvent être utilisées.
| Tâche                                                                           | Description                                                                                                                                                                                                                                                                                                | Objectif de la hiérarchie    |
|--------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Gestion de l'assortiments de vente au détail                                                      | Identifiez les produits disponibles dans chaque magasin de vente au détail.                                                                                                                                                                                                                                             | Assortiment de vente au détail    |
| Gestion du réassort de la vente au détail                                                    | Permet de regrouper les magasins pour réapprovisionner le stock en fonction de règles de réapprovisionnement.                                                                                                                                                                                                                                          | Réapprovisionnement de la vente au détail |
| Données d'état des magasins                                                         | Permet de regrouper les magasins pour la génération d'états.                                                                                                                                                                                                                                                                                | Génération d'états sur les ventes au détail     |
| Validation du stock, calcul de relevés ou validation de relevés pour un groupe de magasins | Créez un groupe de magasins qui peuvent être affectés à un traitement par lots. Lorsque vous définissez un traitement par lots pour valider le stock, calculer les relevés ou valider les relevés, vous pouvez spécifier la hiérarchie à laquelle la tâche s'applique. Lorsque des magasins sont ajoutés à la hiérarchie où qu'ils en sont supprimés, vous ne devez pas modifier le traitement par lots. | Validation de Retail POS   |






