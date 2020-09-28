---
title: Synchroniser une capacité de ressource
description: Cette rubrique fournit des informations sur la synchronisation de la capacité d’une ressource entre les calendriers et les projets.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760542"
---
# <a name="synchronize-resource-capacity"></a>Synchroniser une capacité de ressource

[!include [banner](../includes/banner.md)]

Les processus de synchronisation des ressources permettent de garantir que les informations de calendrier et de calendrier de base soient réinjectées dans la planification des ressources de projet. Si le calendrier est modifié, les processus décrivent les mises à jour obligatoires dans la planification des ressources de projet. Les processus permettent également d’améliorer les performances, car les informations sur les ressources du calendrier sont synchronisées avec l’avance. Par conséquent, les mises à jour avec les informations de planification des ressources se produisent plus rapidement. Nous vous recommandons de planifier des processus en tant que traitement par lots plutôt qu’un à la fois. Sinon, il existe un risque que quelqu’un oublie les dates incluses lorsque les informations ont été synchronisées pour la dernière fois. Si les dates incluses ne sont pas utilisées, des écarts peuvent se produire au cours de la synchronisation de la date.

![Synchronisation du calendrier](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a>Synchroniser les reports de capacité des ressources

Le processus de synchronisation est conçu pour synchroniser toutes les informations du calendrier des ressources. Ces informations incluent des informations de base du calendrier sur toutes les modifications apportées à la table de capacité du calendrier des ressources du projet. Si de nouvelles ressources sont ajoutées au projet, la synchronisation permet de garantir que les informations de calendrier mises à jour sont disponibles. Cette synchronisation peut être effectuée à tout moment.

Nous vous recommandons d’utiliser un traitement par lots. Les options sont disponibles lors de la synchronisation des réservations de capacité.

1. Sélectionnez **Gestion de projets et comptabilité** &gt; **Périodique** &gt; **Synchronisation des capacités** &gt; **Synchroniser les reports de capacité des ressources**.
2. Définissez les options dans le tableau suivant.

    | Option      | Description |
    |-------------|-------------|
    | Code période | Permet de sélectionner un code intervalle de dates de comptabilité pour définir les dates de début et de fin du processus de synchronisation pour les reports de capacité des ressources. |
    | Date de début  | Entrez la date de début du processus de synchronisation pour les reports de capacité des ressources. |
    | Date de fin    | Entrez la date de fin du processus de synchronisation pour les reports de capacité des ressources. |

[![Processus de synchronisation](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)
