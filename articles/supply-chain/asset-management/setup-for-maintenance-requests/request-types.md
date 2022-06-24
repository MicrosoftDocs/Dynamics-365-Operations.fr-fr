---
title: Types de demandes de maintenance
description: Cet article explique comment paramétrer des types de demandes de maintenance dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a2d707cc9c0aa4863968651a8434883cc1322eb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888699"
---
# <a name="maintenance-request-types"></a>Types de demandes de maintenance

[!include [banner](../../includes/banner.md)]

 

Les types de demandes de maintenance permettent de classer par catégorie les demandes de maintenance. Par exemple, des types de demandes de maintenance peuvent être associés à la maintenance préventive et à la maintenance corrective. Un type de demande de maintenance spécial peut être utilisé pour gérer la réparation des actifs (réparation au dépôt).

Un type de demande de maintenance définit l’affiliation à un groupe d’états du cycle de vie de la demande de maintenance (modèle de cycle de vie de maintenance). Les modèles de cycle de vie de la demande de maintenance définissent les états du cycle de vie qui peuvent être définis pour une demande de maintenance. (**Créé**, **Actif** et **Terminé** sont des exemples d’états du cycle de vie de la demande de maintenance).

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Demandes de maintenance** \> **Types de demandes de maintenance**.
2. Sélectionnez **Nouveau** pour créer un type de demande de maintenance.
3. Dans le champ **Type de demande de maintenance**, entrez un ID pour le type de demande de maintenance.
4. Dans le champ **Nom**, entrez un nom.
5. Dans le raccourci **Général**, dans le champ **Modèle de cycle de vie des demandes de maintenance**, sélectionnez un modèle de cycle de vie de la demande de maintenance.
6. Dans le champ **Type d’ordre de travail**, sélectionnez un type d’ordre de travail. Lorsqu’une demande de maintenance est convertie en bon de travail, le type d’ordre de travail associé au type de demande de maintenance est automatiquement attribué à l’ordre de travail.

L’illustration suivante présente un exemple de la page **Types de demandes de maintenance**.

![Page Types de demandes de maintenance.](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]