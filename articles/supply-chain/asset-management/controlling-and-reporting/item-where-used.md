---
title: Cas d'emploi d'article
description: Cette rubrique explique comment obtenir une vue d'ensemble de l'emplacement d'utilisation d'un article dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 84ab803aedf5b803b6c5f39ff1907726335cb45d
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918324"
---
# <a name="item-where-used"></a>Cas d'emploi d'article

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Vous pouvez effectuer un calcul pour un article spécifique pour obtenir une vue d'ensemble de son emplacement d'utilisation dans le module Gestion des actifs. Les résultats indiquent le contexte dans lequel l'article était utilisé pendant toute sa durée de vie. La page **Cas d'emploi d'article** peut être ouverte à partir du menu principal Gestion des actifs, et elle est également accessible à partir des pages suivantes :

[Nomenclature des actifs](../objects/object-BOM.md)

[Pièces détachées sur Valeurs par défaut du type d'actif](../setup-for-objects/object-types.md)

[Prévision d'article sur Prévision du type de tâche de maintenance par défaut](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

[Prévisions en matière de maintenance de l'ordre de travail](../work-orders/maintenance-forecasts.md)

[Demande d'achat de l'ordre de travail](../work-orders/procurement.md)

[Achats de l'ordre de travail](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Effectuer un calcul de cas d'emploi d'article

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Cas d'emploi d'article** ou cliquez sur le bouton **Cas d'emploi d'article** sur l'une des pages mentionnées ci-dessus.

2. Dans la boîte de dialogue **Cas d'emploi d'article**, sélectionnez l'article pour lequel vous souhaitez effectuer le calcul dans le champ **Numéro d’article**.

3. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes d'article en fonction des postes techniques. Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes d'article pour un poste technique s'affichent dans le niveau supérieur. Par conséquent, la relation/quantité d'une ligne peut être ajoutée à partir des emplacements fonctionnels situés à un niveau inférieur. Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes d'article sur tous les niveaux du poste technique auxquels ils sont liés.

4. Dans la section **Inclure**, sélectionnez « Oui » sur les boutons bascule à inclure dans le calcul.

5. Cliquez sur **OK** pour démarrer le calcul.

6. Dans l'onglet **Cas d'emploi d'article** > dans les groupes du volet Actions **Grouper par...**, cliquez sur les boutons appropriés pour afficher le niveau requis de détail du calcul. Les boutons sélectionnés du volet Actions sont mis en surbrillance. Cliquez sur un bouton pour l'activer ou le désactiver.

7. Si vous souhaitez afficher d'autres dimensions associées à l'article, cliquez sur **Afficher les dimensions**, puis sélectionnez les dimensions à afficher.

Dans l'illustration ci-dessous, vous verrez un exemple de calcul de cas d'emploi d'article pour le numéro d'article « 1000 ».

![Figure 1](media/12-controlling-and-reporting.png)

