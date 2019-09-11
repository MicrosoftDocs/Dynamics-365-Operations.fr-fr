---
title: Types d'ordre d'exécution
description: Cette rubrique explique les types d'ordre de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 57120b51c069e49697f8ec4357265974a0d3afb4
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874576"
---
# <a name="work-order-types"></a>Types d'ordre d'exécution

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Les types d'ordre de travail sont utilisés pour classer les ordres de travail par catégorie. Par exemple, des ordres de travail peuvent être associés à la maintenance préventive ou à la maintenance corrective.

Un type d'ordre de travail définit une affiliation au modèle du cycle de vie de l'ordre de travail. Un modèle de cycle de vie de l'ordre de travail définit les états du cycle de vie de l'ordre de travail qui peuvent être définis sur un ordre de travail. (Parmi des exemples d'états du cycle de vie de l'ordre de travail figurent **Créé**, **En cours** et **Terminé**.)

Pour plus d'informations sur les états du cycle de vie de l'ordre de travail et les étapes du projet, consultez [États du cycle de vie de l'ordre de travail](work-order-lifecycle-states.md).

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Types d'ordre de travail**.
2. Sélectionnez **Nouveau** pour créer un type d'ordre de travail.
3. Dans le champ **Type d'ordre de travail**, saisissez un ID pour le type d'ordre de travail.
4. Dans le champ **Nom**, entrez un nom.
5. Dans le champ **Modèle du cycle de vie de l'ordre de travail**, sélectionnez un modèle de cycle de vie.
5. Définissez l'option **Un agent de maintenance** sur **Oui** si toutes les tâches de l'ordre de travail associées à un ordre de travail de ce type doivent être planifiées au même agent de maintenance.
6. Dans le champ **Type de coût**, sélectionnez **Correctif**, **Préventif** ou **Investissement**, le cas échéant. Toutes les tâches de l'ordre de travail sur un ordre de travail doivent avoir le même type de coût.
7. Dans la section **Obligatoire**, définissez les options appropriées sur **Oui** pour spécifier que les informations relatives au temps d'arrêt pour maintenance ou à une panne sont ajoutées à un ordre de travail de ce type.

    > [!NOTE]
    > Les options de la section **Obligatoire** sont associées aux options sur l'organisateur **Valider** de la page **États du cycle de vie de l'ordre de travail** (**Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **États du cycle de vie**).

8. Sélectionnez **Enregistrer**.

![Figure 1](media/16-setup-for-work-orders.png)
