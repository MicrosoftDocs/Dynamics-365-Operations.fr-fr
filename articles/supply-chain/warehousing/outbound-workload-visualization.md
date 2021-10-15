---
title: Visualisation de la charge de travail sortante
description: Cette rubrique fournit des informations sur la visualisation de la charge de travail sortante. Cette fonctionnalité permet aux responsables d’entrepôt et aux superviseurs de créer des graphiques de charge de travail personnalisés qui peuvent être utilisés pour surveiller la progression du travail en cours et la quantité qui reste. Les gestionnaires d’entrepôt peuvent créer plusieurs vues et configurer une actualisation automatique selon leurs besoins.
author: Mirzaab
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-08-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 8416d43fe2b8b08e4d66434a1d95daa4b01a0fa4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576158"
---
# <a name="outbound-workload-visualization"></a>Visualisation de la charge de travail sortante

[!include [banner](../includes/banner.md)]

Les capacités de configuration avancées accessibles depuis la page **Visualisation de la charge de travail sortante** permettent aux responsables d’entrepôt et aux superviseurs de créer des graphiques de charge de travail personnalisés qui peuvent être utilisés pour surveiller la progression du travail en cours et la quantité qui reste. Les gestionnaires d’entrepôt peuvent créer plusieurs vues et configurer une actualisation automatique selon leurs besoins. Les visualisations de charge de travail sortante peuvent être affichées sur les pages de performances de l’entrepôt.

Cette fonctionnalité peut être utilisée pour suivre la progression du travail de prélèvement. La fonctionnalité est intégrée à la gestion de la main-d’œuvre et, si la gestion de la main-d’œuvre est configurée, les visualisations de la charge de travail sortante peuvent afficher un calcul du nombre d’heures restantes pour le travail de prélèvement affiché (filtré).

## <a name="turn-on-the-outbound-workload-visualization-feature"></a>Activer la fonctionnalité de visualisation de la charge de travail sortante

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Visualisation de la charge de travail sortante*

## <a name="set-up-outbound-workload-visualizations"></a>Configuration des visualisations de la charge de travail sortante

Pour configurer vos visualisations, créez une collection de filtres (vues) et concevez chaque filtre de sorte qu’il affiche un type d’analyse différent. Utilisez la page **Configurer les filtres** pour concevoir les filtres.

Pour configurer une visualisation de la charge de travail sortante, procédez comme suit.

1. Aller à **Gestion des entrepôts \> Rapports de surveillance des entrepôts \> Visualisation de la charge de travail sortante**.

    La page **Visualisation de la charge de travail sortante** apparaît. Une fois que vous avez créé des filtres, cette page affichera votre visualisation. Vous pouvez créer autant de filtres que vous le souhaitez. Tous les filtres que vous créez sont enregistrés sous votre compte utilisateur, afin que vous puissiez les utiliser ultérieurement. En d’autres termes, chaque utilisateur aura son propre ensemble de filtres qu’il a créé. Ces filtres ne seront pas partagés avec d’autres utilisateurs.

1. Sur la page **Visualisation de la charge de travail sortante**, dans le volet Actions, sur l’onglet **Filtres**, sélectionnez **Configurer les filtres**.
1. Sur la page **Configurer les filtres**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter un filtre, puis définissez les champs suivants pour celui-ci :

    - **Tableau des groupes de l’axe X** – Sélectionnez le tableau contenant le champ à utiliser pour regrouper les valeurs de l’axe X.
    - **Champ du groupe de l’axe X** – Parmi les champs de la table que vous avez sélectionnés dans le **Tableau des groupes de l’axe X**, sélectionnez le champ à utiliser pour regrouper les valeurs de l’axe X.
    - **Tableau des valeurs de l’axe X** – Sélectionnez le tableau contenant le champ à utiliser pour analyser de manière avancée les groupes.
    - **Champ de la valeur de l’axe X** – Parmi les champs de la table que vous avez sélectionnés dans le **Tableau des valeurs de l’axe X**, sélectionnez le champ qui fournit les valeurs à analyser pour chaque groupe.
    - **Actualisation automatique** – Sélectionnez si la visualisation doit être actualisée automatiquement.
    - **Intervalle d’actualisation (minutes)** – Entrez le nombre de minutes entre les actualisations automatiques.
    - **Niveau d’affichage** – Sélectionnez si le graphique doit afficher des lignes ouvertes ou des nombres d’en-têtes ouverts.
    - **Type de prélèvement** – Si vous définissez le champ **Niveau d’affichage** sur _Lignes ouvertes_, indiquez si le nombre de lignes de travail ouvertes dans le graphique doit inclure les prélèvements initiaux, les prélèvements par étapes ou à la fois les prélèvements initiaux et les prélèvements par étapes.
    - **Site** – Sélectionnez le site pour lequel charger le graphique.
    - **Entrepôt** – Sélectionnez l’entrepôt pour lequel charger le graphique.
    - **Jours à inclure** – Entrez le nombre de jours dans le passé pour lesquels le graphique doit être généré.
    - **Type d’ordre de travail** – Sélectionnez les types d’ordre de travail sortant sur lesquels filtrer.

    ![Configurer la page des filtres.](media/work-viz-filters-1.png "Configurer la page des filtres")

1. Fermez la page **Configurer les filtres** pour revenir à la page **Visualisations de la charge de travail sortante**.

    La page **Visualisations de la charge de travail sortante** affiche désormais des données, basées sur vos nouveaux paramètres de filtre. Votre nouveau filtre est maintenant disponible et est sélectionné dans le champ **Filtre**. Les champs suivants sont disponibles en haut du graphique :

    - **Filtre** – Ce champ comprend tous les filtres que vous avez créés jusqu’à présent. Sélectionnez un filtre pour afficher ses données dans le graphique.
    - **Dernière actualisation** – Ce champ indique la date et l’heure de la dernière mise à jour des informations du graphique.
    - **Temps estimé/réel** – Si des normes du travail sont définies dans votre système, définissez cette option sur *Oui* pour afficher les temps de prélèvement estimés cumulés en haut de chaque colonne du graphique. Si vous n’utilisez pas les normes du travail, cette option n’est pas disponible.

    ![Exemple de visualisation.](media/work-viz-chart.png "Exemple de visualisation")

1. Sélectionnez n’importe quelle barre du graphique pour afficher les détails de la ligne de travail associée.

    ![Détails de la ligne de travail.](media/work-viz-work-details.png "Détails de la ligne de travail")

## <a name="example-outbound-workload-visualization-for-zones"></a>Exemple : Visualisation de la charge de travail sortante pour les zones

Pour cet exemple, vous souhaitez configurer une visualisation qui montre les lignes de travail pour chaque zone et le statut de chaque ligne de travail (_Ouvert_, _Fermé_ ou _Annulé_). Dans ce cas, vous pouvez configurer un filtre avec les paramètres suivants :

- **Nom du filtre** – Entrez un nom pour ce filtre (tel que _Zone et statut de travail_).
- **Description** – Entrez une brève description pour ce filtre (tel que _Zone et statut de travail_).
- **Tableau des groupes de l’axe X** – Sélectionnez _Emplacements._
- **Groupe de l’axe X** – Sélectionnez _ID de zone_.
- **Tableau des valeurs de l’axe X** – Sélectionnez _Travail_, car vous souhaitez afficher le travail par zone.
- **Champ de valeur de l’axe X** – Sélectionnez _Statut du travail_, car vous souhaitez afficher le statut du travail.
- **Actualisation automatique** – Sélectionnez si la visualisation doit être actualisée automatiquement.
- **Type de prélèvement** – Sélectionnez _Prélèvements initiaux et prélèvements par étapes_, car vous souhaitez inclure à la fois les sélections initiales et les sélections à partir des emplacements temporaires. En d’autres termes, vous souhaitez essentiellement inclure toutes les lignes de travail de prélèvement dont vous disposez.
- **Niveau d’affichage** – Sélectionnez _Lignes ouvertes_, car vous souhaitez afficher les informations par ligne et non par en-tête de travail.

L’illustration suivante présente un exemple du graphique en résultant.

![Visualisation du statut de la zone et du travail.](media/work-viz-chart.png "Visualisation du statut de la zone et du travail")

Ce graphique montre deux zones nommées **ATELIER** et **VRAC**, plus une zone nommée **Vide**. La zone **Vide** représente toutes les lignes de travail qui ne sont membres d’aucune zone. Le graphique montre toujours toutes les données filtrées non liées comme **Vides**, pour offrir autant de visibilité que possible. Dans la zone **ATELIER**, le graphique montre trois lignes fermées et quatre lignes ouvertes. Dans la zone **VRAC**, le graphique montre quatre lignes fermées, une ligne ouverte et 24 lignes annulées. Enfin, le graphique montre huit lignes fermées qui ne font partie d’aucune zone et sont donc répertoriées comme **Vides**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]