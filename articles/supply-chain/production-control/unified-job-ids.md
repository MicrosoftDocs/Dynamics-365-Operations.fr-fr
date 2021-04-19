---
title: Souche de numéros unifiés pour les ID tâche
description: Cette fonction fournit une souche de numéros unique et unifiée qui génère des ID de tâche pour les modules Contrôle de la production, Exécution de la fabrication et Pointage.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824940"
---
# <a name="unified-number-sequence-for-job-ids"></a>Souche de numéros unifiés pour les ID tâche

[!include [banner](../includes/banner.md)]

Cette fonction fournit une souche de numéros unique et unifiée qui génère des ID de tâche pour les modules Contrôle de la production, Exécution de la fabrication et Pointage. Auparavant, vous pouviez choisir une souche de numéros différente pour chacun de ces modules, ce qui pouvait entraîner des conflits d’ID de tâche si deux ou plusieurs de ces souches utilisaient un format identique. Un tel conflit peut entraîner une corruption des données.

## <a name="turn-on-this-feature-for-your-system"></a>Activez cette fonctionnalité pour votre système

Si votre système n’inclut pas déjà la fonctionnalité décrite dans cette rubrique, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Souche de numéros unifiée pour les ID de tâche*.

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a>Paramétrer la souche de numéros unifiée pour les ID de tâche

Après avoir activé cette fonctionnalité, les paramètres de souche de numéros **Identification de tâche** situés sur les pages de paramètres des modules Contrôle de production, Exécution de la fabrication et Pointage seront obsolètes et un nouveau champ **ID de tâche unifié** sera ajouté. La valeur **ID de tâche unifié** est partagée par les trois modules. Cela garantit que tous les modules font référence à la même souche de numéros. Les ID de tâche seront donc uniques dans les trois modules et aucun conflit ne se produira jamais.

Pour paramétrer la souche de numéros unifiée pour les ID de tâche :

1. Activez la fonction comme décrit dans la section précédente.
1. Identifiez la souche de numéros que vous souhaitez utiliser pour vos ID de tâche unifiés ou créez-en une nouvelle. Pour plus d’informations, voir [Vue d’ensemble des souches de numéros](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).
1. Accédez à la page **Paramètres de contrôle de la production**, **Paramètres d’exécution de la fabrication**, ou **Paramètres de pointage**. Peu importe celle que vous choisissez, car lorsque vous définissez ce paramètre sur l’une de ces pages, toutes les autres pages se mettront à jour automatiquement.
1. Ouvrez l’onglet **Souche de numéros** sur la page des paramètres sélectionnée.
1. Attribuez le **Code de souche de numéros** que vous avez identifié précédemment dans la ligne de la grille **ID de tâche unifiés**.
