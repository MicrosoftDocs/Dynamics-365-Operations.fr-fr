---
title: Configuration d’un parcours à plusieurs étapes
description: Cette rubrique décrit comment configurer les voyages en plusieurs étapes pour le module de coût au débarquement.
author: Weijiesa
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMLegTable, ITMJourneyTable, ITMActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c65a3d3971593ccf832a6af3c8c27d56a68b46c8
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689717"
---
# <a name="multi-leg-journey-setup"></a>Configuration d’un parcours à plusieurs étapes

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment configurer les voyages en plusieurs étapes pour le module de **coût au débarquement**.

## <a name="legs"></a>Étapes

Les étapes sont utilisées pour identifier des parties distinctes d’un voyage. Chaque étape est construite en sélectionnant les ports d’expédition "à" et "de", ainsi que la méthode de transport utilisée pour cette étape. Les délais peuvent être associés à chaque étape. Les délais peuvent aider à suivre une expédition et peuvent également être utilisés pour calculer la date de livraison estimée des marchandises lors d’un voyage. De plus, lorsqu’une étape d’un voyage est terminée, le statut du voyage, le conteneur d’expédition et les lignes de commande d’achat associées peuvent être mis à jour via la configuration de contrôle de suivi. Les étapes peuvent être utilisées par un seul modèle de voyage, ou elles peuvent être réutilisées par plusieurs modèles de voyage. Le chargement des conteneurs, les douanes et le transport local sont généralement configurés comme des étapes, et un port d’expédition non spécifique est utilisé pour eux.

Pour utiliser des étapes, accédez à **Coût au débarquement \> Configuration de voyage à plusieurs étapes \> Étapes**. Là, vous pouvez afficher, ouvrir, créer et supprimer des enregistrements pour les segments. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque enregistrement.

| Champ | Description |
|---|---|
| Étape | Entrez un nom/numéro d’identification unique pour l’étape de trajet. |
| Description | Permet d’entrer une description l’étape du trajet. Typiquement, cette description identifie les ports "vers" et "de", ou l’étape du voyage. |
| Port de départ | Entrez le point d’origine des marchandises sur l’étape. |
| Port d’arrivée | Entrez le point de destination des marchandises sur l’étape. |
| Mode de livraison | Entrez le mode de transport de l’étape. |

## <a name="journey-templates"></a>Modèles de parcours

Un modèle de voyage définit le voyage à plusieurs étapes entre deux ports que les marchandises voyagent au cours d’un voyage. Les étapes du voyage sont combinées pour identifier le temps qui sera nécessaire pour que les marchandises voyagent du point d’origine du vendeur à la destination finale de l’entrepôt. Lorsque les étapes sont placées sur le modèle de voyage dans un ordre spécifique, les délais indiqueront la date de chaque étape et l’état du voyage, le conteneur et les lignes d’achat pour le voyage. Vous utilisez le [Centre de contrôle de suivi](delivery-information-setup.md) pour configurer les délais associés à chaque étape constituant le modèle de parcours. Le modèle de voyage est également utilisé lors de la configuration des coûts automatiques d’un voyage. Lorsqu’un trajet est défini, le coût associé au transport des marchandises peut être défini sur la page des coûts auto.

Pour utiliser des modèles de trajet, accédez à **Coût au débarquement \> Configuration de voyage à plusieurs étapes \> modèles de trajet**. Là, vous pouvez afficher, ouvrir, créer et supprimer des modèles de trajet.

Pour chaque modèle de parcours, définissez les champs suivants sur l’en-tête.

| Champ | Description |
|---|---|
| Modèle de parcours | Entrez un nom/numéro d’identification unique pour le modèles de trajet. Le modèle de voyage décrit généralement le point d’origine et le point de destination du voyage. |
| Description | Permet d’entrer une description du modèles de trajet. La description indique généralement les ports "vers" et "de", ainsi que le type de déplacement. |

Dans la section **Lignes**, ajoutez une ligne pour chaque étape du voyage et mettez les lignes dans l’ordre. Utilisez les flèches **Haut** et **Bas** sur la barre d’outils pour changer l’ordre des lignes. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque ligne.

| Champ | Description |
|---|---|
| Étape | Sélectionnez une étape à ajouter au voyage. |
| Description | Description de l’étape. |
| Port de départ | Le port est le point d’origine des marchandises sur l’étape. Ce port est le port "vers" utilisé pour déterminer les coûts automobiles d’un voyage. |
| Port d’arrivée | Port de destination finale des marchandises sur l’étape. |
| Mode de livraison | Mode de livraison utilisé pour l’étape. |
| Port de départ du parcours | Si le port spécifié pour l’étape est utilisé pour déterminer les coûts automatiques, cochez cette case pour l’identifier en tant que port "trajet depuis". Ce port sera indiqué sur l’en-tête du voyage. |
| Port d’arrivée du parcours | Si le port spécifié pour l’étape est utilisé pour déterminer les coûts automatiques, cochez cette case pour l’identifier en tant que port "trajet vers". Ce port sera indiqué sur l’en-tête du voyage. |
| Société d’expédition | Sélectionnez le transporteur utilisé pour l’étape. |

## <a name="activities"></a>Activités

Les paramètres sur la page **Activités** établissent les types d’activités qui peuvent se produire au port de destination d’un tronçon. Les utilisateurs qui travaillent sur la page **Tous les conteneurs d’expédition** peut sélectionner parmi ces valeurs lorsqu’elle estime la durée de chaque activité et enregistre la durée réelle à des fins de comparaison.

Pour configurer vos activités, accédez à **Prix au débarquement \> Configuration des voyages multi-étapes \> Activités**. Vous pouvez ajouter, supprimer et modifier des activités avec les boutons du volet Actions.

Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque activité dans la grille.

| Champ | Description |
|---|---|
| Activité | Le nom de l’activité. |
| Description | Description de l’activité. |
| Société d’expédition | Le compte fournisseur du transporteur associé à l’activité. |
