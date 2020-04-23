---
title: Commandes client de projet pour les projets en régie
description: Cette rubrique explique comment créer des commandes client basées sur un projet pour les projets en régie.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: d19ee9de70cd14c78a997b7a87c10b53ab3917b0
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249091"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a>Commandes client de projet pour les projets en régie

[!include[banner](../includes/banner.md)]

Cette rubrique décrit comment créer une commande client pour un projet. Les commandes client ne peuvent être créées que pour les projets du type **régie**.

Si un projet en régie a plusieurs sources de financement dans le contrat de projet, vous devez activer le paramètre **Autoriser les commandes client pour les projets avec plusieurs sources de financement** dans la page **Paramètres de gestion de projets et de comptabilité**. 

> [!NOTE]
> - La prise en charge des commandes client de projets avec plusieurs sources de financement est disponible depuis la version de l'application 10.0.2.
> - Le paramètre permettant d'activer la prise en charge des commandes client de projet avec plusieurs sources de financement sera supprimé dans la vague de publications d'avril 2020, après quoi la fonctionnalité sera toujours activée.

Vous pouvez créer des commandes client basée sur un projet de deux manières :

- Accédez au projet lui-même. Dans le volet Actions, sélectionnez **Gestion > Tâches d'article > Commandes client**. Les informations du projet passent par défaut sur les commandes client du projet. Si le contrat de projet comporte plusieurs sources de financement, vous devez sélectionner la source de financement pour définir le client pour la commande client. S'il n'y a qu'une source de financement pour le projet, le client est automatiquement défini.
- Accédez à la page de liste **Toutes les commandes client** et créez une commande client. Vous devez sélectionner le projet pour la commande client. Une fois le projet sélectionnée, le client est défini à partir de la source de financement, ou vous devez sélectionner la source de financement si le contrat de projet en inclut plusieurs.

