---
title: Espace de travail Gestion des immobilisations
description: "Cette rubrique fournit des informations sur l'espace de travail Gestion des immobilisations. Cet espace de travail affiche les informations liées aux immobilisations entrées dans le système. Il inclut une vue Synthèse et une vue Analyses."
author: saraschi
manager: AnnBe
ms.date: 10/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.assetid: 
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c544ae60433dd14d061bc1a78d5cad6577cf579d
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="fixed-asset-management-workspace"></a>Espace de travail Gestion des immobilisations

[!include[banner](../includes/banner.md)]

L'espace de travail **Gestion des immobilisations** affiche les informations liées aux immobilisations entrées dans le système. Cet espace de travail contient une vue Synthèse et une vue Analyses. L'onglet **Mon travail** affiche les vignettes de synthèse, les détails des immobilisations et les informations associées sur les immobilisations de la société actuelle. Vous pouvez également ajouter des analyses à la section Analyses Power BI directement dans l'espace de travail. L'onglet **Analyses - toutes les sociétés** utilise les fonctionnalités de Microsoft Power BI pour afficher les visuels associés aux immobilisations de toutes les sociétés.

## <a name="my-work"></a>Mon travail

### <a name="summary"></a>Synthèse

Les vignettes dans la section **Synthèse** fournissent une vue d'ensemble des immobilisations. Ces informations incluent des mesures sur les immobilisations qui n'ont pas encore été acquises, les immobilisations qui ont été acquises au cours de l'année et les immobilisations cédées au cours de l'année. La section **Synthèse** offre également la navigation rapide vers la page de liste **Immobilisation**, la proposition d'amortissement des lots et le journal des immobilisations.

### <a name="find-fixed-assets"></a>Rechercher des immobilisations

La section **Rechercher des immobilisations** vous permet de rechercher rapidement des immobilisations en fournissant le numéro de l'immobilisation, le groupe, le nom, l'emplacement ou la personne responsable de l'immobilisation. Toutes les immobilisations qui correspondent aux critères de recherche figurent dans la liste.

Dans la liste, vous pouvez afficher les pages suivantes :

 - Page **Détails** de l'immobilisation
 - Page **Registres** contenant tous les registres qui sont associés à l'immobilisation
 - Page **Évaluations d'immobilisation**

### <a name="valuations"></a>Évaluations

La page **Évaluations d'immobilisation** vous permet de consulter, sur une page, les informations les plus importantes sur une immobilisation, ainsi que les détails de tous les registres associés à l'immobilisation. L'option **Soldes** figurant dans la partie supérieure gauche de la page présente l'évaluation actuelle pour chaque registre associé à l'immobilisation. Vous pouvez explorer les valeurs pour afficher les transactions détaillées composant la valeur de synthèse. L'option **Profil** figurant dans la partie supérieure gauche de la page présente le programme d'amortissement pour chaque registre associé à l'immobilisation.

Vous pouvez accéder à la page **Évaluations d'immobilisation** de l'espace de travail **Gestion des immobilisations** ou à la page de liste **Immobilisation**.

### <a name="related-information"></a>Informations associées

Vous pouvez accéder directement à la page **Paramétrage des registres**, à la page **Recherche de transactions d'immobilisation** et à plusieurs états à l'aide des liens de la section **Informations associées** de l'espace de travail.

### <a name="analytics--all-companies"></a>Analyses - toutes les sociétés

La page **Analyses** fournit des mesures importantes sur les immobilisations dans toutes les entités juridiques du système. L'accès à cet onglet est contrôlé par tous les privilèges de sécurité Afficher l'analyse de l'immobilisation de la société.

Le tableau suivant indique les visualisations qui sont disponibles sur chaque page d'état.

| Page d'état            | Visualisation        |
|------------------------|----------------------|
| Évaluations d'immobilisation | Valeur nette totale |
| Évaluations d'immobilisation | Valeurs nettes par groupe d'immobilisations |
| Évaluations d'immobilisation | Valeurs d'acquisition |
| Évaluations d'immobilisation | Valeurs de cession |
| Évaluations d'immobilisation | Détails de l'immobilisation |
| Cartes d'évaluations        | Valeur nette totale |
| Cartes d'évaluations        | Emplacements d'immobilisation |
| Cartes d'évaluations        | Détails de l'immobilisation |

Pour afficher les analyses avec des données, vous devez actualiser la mesure de regroupement AssetTransactionMeasure sur la page **Magasin des entités**.

