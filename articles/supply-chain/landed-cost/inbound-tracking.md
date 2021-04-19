---
title: Effectuer le suivi des voyages entrants et des parcours du conteneur d’expédition
description: Cette rubrique explique comment utiliser la page de suivi des appels entrants pour suivre la progression de vos voyages et des trajets de conteneurs d’expédition.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 40f8e48b8e52c109023cf0ea5a55657754e1d5b3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823383"
---
# <a name="track-inbound-voyages-and-shipping-container-journeys"></a>Effectuer le suivi des voyages entrants et des parcours du conteneur d’expédition

[!include [banner](../../includes/banner.md)]

La page de **suivi des appels entrants** pour suivre la progression de vos voyages et des trajets de conteneurs d’expédition. Chaque voyage et voyage est décomposé par *Activités*, chacun ayant sa propre ligne sur la page. Vous pouvez utiliser la page pour afficher et saisir des dates estimées et des dates réelles par activité.

En règle générale, selon la configuration dans le [Centre de contrôle de suivi](delivery-information-setup.md#tracking-control-center), ces activités affichent automatiquement la date de débarquement estimée à la destination finale. Selon la configuration, la date finale met généralement à jour la date de livraison ou la date confirmée sur les lignes de commande d’achat. Pour les lignes d’ordre de transfert, vous pouvez configurer le système pour mettre à jour la date de réception.

Pour ouvrir la page **Suivi entrant**, allez à **Prix au débarquement \> Suivi \> Suivi entrant**.

## <a name="filter-the-activities-list"></a>Filtrer la liste des activités

Vous pouvez utiliser les champs **Voyage** et **conteneur de livraison** en haut de la page **Suivi entrant** pour filtrer la page afin qu’elle n’affiche que les activités associées au voyage et / ou au conteneur d’expédition sélectionnés.

## <a name="update-tracking-information"></a>Mettre à jour des informations de suivi

Pour mettre à jour l’horaire d’un voyage ou d’un trajet, entrez la date de début de la première activité. La date de fin estimée de la dernière activité est ensuite mise à jour. La configuration de chaque étape et modèle de parcours dans le [Centre de contrôle de suivi](delivery-information-setup.md#tracking-control-center) détermine les délais estimés. Les dates de fin estimées utilisent le délai à partir de la date de début de l’activité. Ensuite, lorsque la date de fin réelle est enregistrée, la date de début de l’activité suivante est mise à jour à la même date que la date de fin réelle de l’activité précédente. Le délai d’exécution réel est mis à jour afin que la comparaison et l’analyse puissent être effectuées. Des notes supplémentaires peuvent être saisies dans le champ **Note**.

L’ordre des activités dans la grille est déterminé par l’ordre des étapes dans le modèle de parcours correspondant. Si l’ordre des étapes du trajet associé change, la commande de suivi change également.

Vous pouvez mettre à jour les dates de tous les conteneurs en sélectionnant **Mettre à jour la date de début** ou **Mettre à jour la date de fin réelle** dans le volet Actions. Vous pouvez également saisir les dates par conteneur sur l’envoi. Cette approche permet une plus grande flexibilité, car les conteneurs peuvent être divisés dans un environnement à trajets multiples.

## <a name="buttons-on-the-action-pane"></a>Boutons sur le volet Action

Vous pouvez utiliser les boutons du volet Actions de la page **Suivi entrant** pour travailler avec les voyages et trajets entrants. Le tableau suivant décrit les boutons disponibles.

| Bouton | Description |
|---|---|
| Modifier | Modifier un voyage ou un voyage de conteneur d’expédition. |
| Créer | Créer un voyage ou un voyage de conteneur d’expédition. |
| Retirer | Supprimer un voyage ou un voyage de conteneur d’expédition sélectionné. |
| Mettre à jour la date de début | Mettez à jour la date de début d’une activité pour tous les conteneurs d’un voyage. Lorsque la date de début d’une activité ou d’une étape spécifique d’un voyage est mise à jour, les dates de début estimées suivantes sont mises à jour en fonction du délai spécifié. |
| Mettre à jour la date de fin réelle | Mettez à jour la date de fin d’une activité pour tous les conteneurs d’un voyage. Lorsque la date de fin d’une activité est mise à jour, les activités suivantes sont mises à jour en fonction du délai spécifié. |
| Ajouter des activités | Ajouter manuellement une activité ou un voyage. Par exemple, vous pouvez ajouter une activité de fumigation. L’ajout peut entraîner une modification de la date de livraison confirmée des marchandises à bord du navire ou du voyage. Lorsqu’une activité est ajoutée au trajet, les jours estimés ne sont pas saisis tant que la date de début d’un tronçon de trajet n’est pas mise à jour. |

## <a name="information-and-settings-on-the-overview-tab"></a>Informations et paramètres de l’onglet Présentation

L’onglet **Aperçu** affiche une liste de toutes les activités appartenant au voyage et / ou au conteneur d’expédition sélectionné en haut de la page. Le tableau suivant décrit les champs disponibles dans l’en-tête pour chaque activité.

| Champ | Description |
|---|---|
| Étape | ID d’étape de l’activité, tel que défini par le modèle de parcours. |
| Mode de livraison | Méthode de transport prévu pour l’activité. |
| Activité | Ce champ identifie généralement le travail ou la tâche associé à l’activité. Les exemples typiques incluent *Navigation* et *Autorisation*. |
| Description | Une description détaillée de l’activité. |
| Date de début | Ce champ affiche initialement la date de début estimée de l’activité. Cependant, une fois que la date de fin réelle de l’activité précédente a été saisie, elle affiche la date de début réelle. Ce champ est utilisé pour déterminer la date de fin estimée, en fonction du délai. |
| Date de fin estimée | La valeur de ce champ est calculée en fonction de la date de début et du délai. Vous ne modifierez généralement pas la valeur directement. |
| Date de fin réelle | Un utilisateur doit mettre à jour ce champ dès que possible après que l’activité s’est produite. Le délai de livraison réel est ensuite mis à jour. |
| Jours estimés | Nombre de jours estimé à la réalisation de l’activité. |
| Jours réels | Nombre de jours réel à la réalisation de l’activité. |
| Note | Utilisez ce champ pour ajouter des notes diverses et des détails sur l’activité. |

## <a name="information-and-settings-on-the-general-tab"></a>Informations et paramètres de l’onglet Général

L’onglet **Général** affiche des informations sur le tronçon sélectionné sur l’onglet **Aperçu**. Bien qu’il répète certaines des informations qui apparaissent sur l’onglet **Aperçu**, il comprend également des informations supplémentaires sur le tronçon sélectionné.
