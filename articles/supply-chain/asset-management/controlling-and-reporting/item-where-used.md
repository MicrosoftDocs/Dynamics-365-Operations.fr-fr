---
title: Cas d'emploi d'article
description: Cette rubrique explique comment obtenir une vue d'ensemble de l'emplacement d'utilisation d'un article dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: db0932c5a52030c1a7f0411163aee120e2173ca0
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021137"
---
# <a name="item-where-used"></a>Cas d'emploi d'article

[!include [banner](../../includes/banner.md)]

 

Vous pouvez effectuer un calcul pour un article spécifique pour obtenir une vue d'ensemble de son emplacement d'utilisation dans le module Gestion des actifs. Les résultats indiquent le contexte dans lequel l'article était utilisé pendant toute sa durée de vie. La page **Cas d'emploi d'article** peut être ouverte à partir du menu principal Gestion des actifs, et elle est également accessible à partir des pages suivantes :

- [Nomenclatures d'actif](../objects/object-BOM.md)

- [Pièces détachées sur Valeurs par défaut du type d'actif](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [Catégories de type de tâche de maintenance et types de tâches de maintenance, variantes de type de tâche de maintenance, opérations de tâches de maintenance et listes de contrôle de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [Prévision en matière de maintenance](../work-orders/maintenance-forecasts.md)

- [Approvisionnement](../work-orders/procurement.md)

- [Achats de l'ordre de travail](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Effectuer un calcul de cas d'emploi d'article

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Cas d'emploi d'article** ou cliquez sur le bouton **Cas d'emploi d'article** sur l'une des pages mentionnées ci-dessus.

2. Dans la boîte de dialogue **Cas d'emploi d'article**, sélectionnez l'article pour lequel vous souhaitez effectuer le calcul dans le champ **Numéro d’article**.

3. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes d'article en fonction des postes techniques. 

    Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes d'article pour un poste technique s'affichent dans le niveau supérieur. Par conséquent, la relation/quantité d'une ligne peut être ajoutée à partir des emplacements fonctionnels situés à un niveau inférieur. 
    
    Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes d'article sur tous les niveaux du poste technique auxquels ils sont liés.

4. Dans la section **Inclure**, sélectionnez « Oui » sur les boutons bascule à inclure dans le calcul.

5. Cliquez sur **OK** pour démarrer le calcul.

6. Dans l'onglet **Cas d'emploi d'article**, sélectionnez les boutons **Grouper par** pour afficher le niveau requis de détail du calcul. Les boutons **Grouper par** sélectionnés sont mis en surbrillance. Cliquez sur un bouton pour l'activer ou le désactiver.

7. Si vous souhaitez afficher d'autres dimensions associées à l'article, cliquez sur **Afficher les dimensions**, puis sélectionnez les dimensions à afficher.

## <a name="example"></a>Exemple

Dans la capture d'écran ci-dessous, vous verrez un exemple de calcul de cas d'emploi d'article pour le numéro d'article « 1000 ».

![Exemple de calcul de cas d'emploi d'article](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]