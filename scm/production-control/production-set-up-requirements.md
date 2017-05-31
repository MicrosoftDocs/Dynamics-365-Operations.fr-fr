---
title: "Conditions requises pour le paramétrage de la production"
description: "Cet article fournit des informations sur les conditions requises pour le paramétrage avant d&quot;utiliser le contrôle de la production."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 2e39173ef6a27296a20d5f6e44ff6c728aa49c09
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="production-setup-requirements"></a>Conditions requises pour le paramétrage de la production

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les conditions requises pour le paramétrage avant d'utiliser le contrôle de la production. 

Le contrôle de la production figure dans les fonctionnalités d'autres modules. Cette interconnectivité permet de modifier les ordres de fabrication et de s'assurer qu'ils sont automatiquement mis à jour dans tous les autres processus et calculs associés du système. Les processus de paramétrage suivants sont listés dans leur ordre de réalisation.

## <a name="required-baseline-setup-in-other-modules"></a>Paramétrages de bases requis dans les autres modules
Vous devez paramétrer les informations des autres modules avant de pouvoir utiliser le module Contrôle de la production. Ce paramétrage inclut les tâches suivantes :

-   paramétrage des informations générales sur la société ;
-   paramétrage de la comptabilité ;
-   définition des groupes d'articles ;
-   paramétrage des comptes généraux pour les groupes d'articles ;
-   Paramétrage de la table des articles en stock dans le module Gestion des stocks.
-   Création de nomenclatures et de versions de nomenclature dans le module Gestion des stocks.

## <a name="required-calendar-and-resource-setup"></a>Paramétrage de calendrier et de ressource requis
Avant d'utiliser le module Contrôle de la production, ouvrez le module Administration d'organisation, puis créez et définissez le calendrier et les ressources opérationnelles dans l'ordre suivant :

1.  **Modèles de temps de travail** – Paramétrez les modèles de temps de travail pour définir les temps disponibles pour la planification de la production.
2.  **Calendriers** - Paramétrez les calendriers de temps de travail afin de définir quels jours de l'année sont disponibles pour la planification de la production.
3.  **Groupes de ressources** – Paramétrez les groupes de ressources pour regrouper les ressources opérationnelles afin d'obtenir une vue d'ensemble de la capacité libre lors de l'exécution de la planification. Vous ne devez pas paramétrer des groupes de ressources avant de paramétrer des ressources opérationnelles. Toutefois, il est recommandé de comprendre comment regrouper des ressources lorsque vous paramétrez le module Contrôle de la production.
4.  **Ressources** – Paramétrez des ressources opérationnelles afin de définir les ressources utilisées pour exécuter le processus de production et planifier la capacité.

## <a name="required-production-parameters-setup"></a>Paramétrage requis des paramètres de production
**Paramètres de contrôle de la production** – Définissez des paramètres de production de base afin de définir la manière dont le système gère et traite les ordres de fabrication. Définissez le mode de création, d'estimation, de planification et de consommation des ordres de fabrication. Vous pouvez également sélectionner le type de rétroaction souhaité et la manière dont le contrôle de gestion doit être réalisé.

## <a name="required-journal-name-identification"></a>Identification requise des noms de journal
**Noms des journaux de production** – Permet de spécifier les noms des journaux de production à utiliser afin d'enregistrer et de valider des transactions.

## <a name="setup-if-you-use-operations"></a>Paramétrage pour l'utilisation des opérations
Ces opérations représentent des activités spécifiques qui permettent de fabriquer le produit fini. **Remarque :** Vous devez savoir quelles sont les activités nécessaires à la fabrication de l'article, et l'ordre et les priorités de ces activités. Vous devez également savoir quelles ressources sont impliquées, et leur nombre.

1.  **Opérations** - Paramétrez des opérations afin de représenter les tâches à réaliser pour produire un article fini.
2.  **Relations** – Paramétrez des relations d'opération afin de définir les propriétés détaillées. Pour définir les relations d'opération, cliquez sur **Relations** sur la page **Opérations**.

## <a name="setup-if-you-use-routes"></a>Paramétrage pour l'utilisation des gammes
Si vous utilisez des gammes, les opérations doivent être définies pour chaque gamme de production que vous paramétrez. Une gamme représente le chemin suivi par l'article d'opération en opération, du début à la fin du processus de production.

1.  **Catégories de coûts** – Paramétrez des catégories de coûts afin de définir le coût par heure des processus spécifiés et les temps de réglage.
2.  **Groupes de coûts** – Paramétrez les groupes de coûts afin de créer et de mettre à jour les différents types de coûts.
3.  **Groupes de gammes** – Paramétrez des groupes de gammes pour définir les paramètres liés à des groupes de gammes. Vous devez paramétrer les groupes de gammes avant de pouvoir créer des gammes de production.
4.  **Gammes** – Paramétrez des gammes de production et définissez les paramètres par défaut afin de contrôler la planification, l'évaluation des coûts et le prix des opérations de gamme, ainsi que la progression de la génération d'états.
5.  **Gammes** – Paramétrez les versions de gamme afin d'autoriser les variations d'article en production.

## <a name="optional-advanced-settings"></a>Paramètres facultatifs et avancés
1.  **Groupes de productions** – Paramétrez les groupes de production afin de définir les relations entre l'ordre de fabrication et les comptes généraux. Ces derniers sont utilisés pour valider ou regrouper les ordres à des fins de génération d'états.
2.  **Regroupements de productions** – Créez des regroupements de production afin de regrouper les ordres de fabrication pour leur traitement urgent ou pour la suppression ou la validation des groupes d'ordres.
3.  **Propriétés** – Définissez les propriétés pour créer les attributs spéciaux que vous pouvez affecter à vos ressources pour contrôler la séquence de production. Ces attributs sont connectés au modèle de temps de travail.





