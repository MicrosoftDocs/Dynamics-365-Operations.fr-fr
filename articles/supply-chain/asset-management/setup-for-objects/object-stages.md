---
title: États du cycle de vie de l'actif
description: Cette rubrique explique les états du cycle de vie de l'actif et les modèles de cycle de vie dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dffedfafd9d75320accf0e27f072bab6fd51f135
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016550"
---
# <a name="asset-lifecycle-states"></a>États du cycle de vie de l'actif

[!include [banner](../../includes/banner.md)]

 

Cette rubrique explique les états du cycle de vie de l'actif et les modèles de cycle de vie dans le module Gestion des actifs. Les états du cycle de vie de l'actif permettent de définir si un actif est actif ou inactif. Par exemple, vous pouvez paramétrer des états du cycle de vie de l'actif, comme **Créé**, **Actif** et **Terminé**.

> [!NOTE]
> - Les états du cycle de vie de la demande sont liés aux états du cycle de vie de l'actif. Ainsi, lorsqu'une demande est remplacée par un nouvel état du cycle de vie de la demande, l'actif joint à la demande est remplacé par un nouvel état du cycle de vie de l'actif. Par exemple, si l'état du cycle de vie d'une demande passe à **Entrant**, l'état du cycle de vie de l'actif joint est remplacé par l'état du cycle de vie sélectionné dans le champ **État du cycle de vie entrant** du raccourci **État du cycle de vie de l'actif** de la page **Modèles d'état du cycle de vie de l'actif**. 


Les états du cycle de vie de l'actif peuvent être paramétrés dans les modèles de cycle de vie de l'actif, où vous pouvez définir les états du cycle de vie requis pour différents types d'actifs. Vous paramétrez d'abord les états du cycle de vie. Vous créez ensuite un modèle de cycle de vie et sélectionnez les états du cycle de vie associés.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **États du cycle de vie**.
2. Sélectionnez **Nouveau** pour créer un état du cycle de vie de l'actif.
3. Dans le champ **État du cycle de vie**, entrez l'ID de l'état du cycle de vie.
4. Dans le champ **Nom**, entrez une description.

    Le champ **Modèles de cycle de vie** affiche le nombre de modèles de cycle de vie de l'actif qui utilisent l'état du cycle de vie de l'actif.

5. Définissez l'option **Actif** sur **Oui** si cet état du cycle de vie doit être actif (autrement dit, si des ordres de travail peuvent être créés pour les actifs qui figurent dans cet état du cycle de vie).
6. Définissez l'option **Supprimer les lignes de calendrier en cours** sur **Oui** si des lignes de calendrier en cours dont l'état du cycle de vie de l'actif est **Créé** doivent être supprimées lorsqu'elles sont dans cet état du cycle de vie. Ce paramètre est utile si vous souhaitez nettoyer les programmes de maintenance en cours qui ne sont plus pertinents pour l'actif (par exemple, si l'actif n'est plus actif).

> [!NOTE]
> Les états du cycle de vie de l'actif, les modèles de cycle de vie de l'actif et les types d'actif sont liés. Ils sont utilisés de la même manière que les états du cycle de vie de l'ordre de travail, les modèles de cycle de vie de l'ordre de travail et les types d'ordres de travail. 


Après avoir créé les états du cycle de vie de l'actif requis, vous pouvez paramétrer les états du cycle de vie dans les modèles de cycle de vie de l'actif.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Modèles de cycle de vie**.
2. Sélectionnez **Nouveau** pour créer un modèle de cycle de vie de l'actif.
3. Dans le champ **Modèle de cycle de vie**, entrez l'ID du modèle de cycle de vie.
4. Dans le champ **Nom**, entrez une description.

    Le champ **États du cycle de vie** affiche le nombre d'états du cycle de vie de l'actif qui sont sélectionnés dans le modèle de cycle de vie de l'actif. Le champ **Types d'actif** affiche le nombre de types d'actif qui utilisent le modèle de cycle de vie.

5. Dans le raccourci **États du cycle de vie**, sélectionnez les états du cycle de vie de l'actif qui doivent être inclus dans le modèle de cycle de vie de l'actif :

    - Pour utiliser un état du cycle de vie pour le modèle, sélectionnez-le dans la section **États du cycle de vie restants**, puis utilisez le bouton Flèche droite ![Flèche droite](media/15-setup-for-objects.png) pour le déplacer vers la section **États du cycle de vie sélectionnés**.
    - Pour utiliser tous les états du cycle de vie disponibles pour le modèle, sélectionnez le bouton **Tous les états du cycle de vie disponibles** ![Tous les états du cycle de vie disponibles](media/20-setup-for-objects.png). Tous les états du cycle de vie sont transférés vers la section **États du cycle de vie sélectionnés**.
    - Pour supprimer un état du cycle de vie du modèle, sélectionnez-le dans la section **États du cycle de vie sélectionnés**, puis utilisez le bouton Flèche gauche ![Flèche gauche](media/16-setup-for-objects.png) pour le déplacer vers la section **États du cycle de vie restants**.

6. Sélectionnez **Mises à jour de l'état du cycle de vie** pour définir les états du cycle de vie de l'actif qui peuvent suivre un état du cycle de vie sélectionné.
7. Vous utilisez le raccourci **État de l'actif** si vous gérez des actifs que vous recevez pour réparation. Dans la section **Entrant/Sortant**, vous pouvez sélectionner les états du cycle de vie de l'actif pour indiquer le workflow d'un actif que vous recevez pour réparation. Si vous offrez des actifs d'emprunt aux clients ou aux départements, dans la section **Emprunt**, vous pouvez sélectionner les états du cycle de vie pour les actifs d'emprunt.
