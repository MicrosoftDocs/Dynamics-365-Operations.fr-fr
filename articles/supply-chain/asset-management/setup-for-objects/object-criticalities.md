---
title: Types d'élément critique de l'actif
description: La rubrique explique les types d'élément critique de l'actif dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9d2c5e8b6676abf03fe0d3de8b23f125713d6f2
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021702"
---
# <a name="asset-criticality-types"></a>Types d'élément critique de l'actif

[!include [banner](../../includes/banner.md)]

 

La rubrique explique les types d'élément critique de l'actif dans le module Gestion des actifs. L'élément critique de l'actif est lié aux actifs et est transféré aux ordres de travail. Il ne peut pas être modifié sur un ordre de travail. L'élément critique de l'actif est utilisé pour calculer l'élément critique de l'ordre de travail lors de la planification des ordres de travail. En d'autres termes, il est utilisé pour calculer dans quelle mesure une tâche de maintenance sur un actif affecte la planification de la production et la productivité dans votre société. Pour plus d'informations sur le paramétrage lié au calcul des scores pour la planification des ordres de travail, voir [Paramètres de gestion des actifs](../setup-for-objects/enterprise-asset-management-parameters.md).

Pour paramétrer l'élément critique, commencez par créer les types d'élément critique qui doivent être utilisés dans le paramétrage des actifs. Vous paramétrez ensuite les éléments critiques de l'actif.

## <a name="set-up-criticality-types"></a>Paramétrer les types d'élément critique

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Types d'élément critique**.
2. Sélectionnez **Nouveau** pour créer un enregistrement.
3. Dans le champ **Élément critique**, entrez un nombre indiquant l'élément critique.
4. Dans le champ **Nom**, entrez un nom pour le type d'élément critique.
5. Dans le champ **Facteur**, entrez un facteur. Ce facteur est utilisé lors du calcul de la planification des ordres de travail pour déterminer l'enregistrement d'élément critique qui doit être utilisé. (L'enregistrement avec le facteur le plus élevé est toujours utilisé). Ce paramètre est utile si, comme indiqué dans l'illustration suivante, les lignes d'élément critique sont créées avec la même valeur d'élément critique.

    ![Page des types d'éléments critiques](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a>Paramétrer les éléments critiques de l'actif

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Éléments critiques de l'actif**.
2. Sélectionnez **Nouveau** pour créer un enregistrement.
3. Selon le niveau de détail requis pour l'élément critique de l'actif, effectuez vos sélections appropriées dans les champs **Poste technique**, **Type d'actif**, **Fabricant**, **Modèle**, **Actif**, **Catégorie de type de tâche**, **Type de tâche**, **Variante du type de tâche** et **Demande de tâche**.

    > [!NOTE]
    > Lorsqu'un élément critique d'actif est sélectionné, le module Gestion des actifs recherche une correspondance possible dans tous les enregistrements d'élément critique d'actif. Il vérifie toujours la combinaison la plus spécifique en premier. En d'autres termes, le module Gestion des actifs vérifie d'abord l'enregistrement **Demande de tâche**. Si aucune correspondance n'est trouvée, il vérifie l'enregistrement **Variante du type de tâche**. Si aucune correspondance n'est trouvée, il vérifie l'enregistrement **Type de tâche**, etc. Comme vous pouvez voir dans la disposition de la page, ce comportement signifie que, pour trouver la combinaison la plus spécifique, le module Gestion des actifs recherche une correspondance dans chaque enregistrement en allant de la droite vers la gauche. Si aucune correspondance n'est trouvée, l'enregistrement par défaut qui ne comporte aucune sélection est utilisé.

4. Dans le champ **Élément critique**, sélectionnez l'une des valeurs d'élément critique que vous avez créées dans la procédure précédente.

### <a name="notes-about-criticality-setup"></a>Notes sur le paramétrage des éléments critiques

- Si vous modifiez un élément critique d'actif dans ce paramétrage après l'avoir déjà utilisé sur un ordre de travail, l'élément critique sur l'ordre de travail n'est pas mis à jour en conséquence.
- L'élément critique sur un ordre de travail est recalculé chaque fois qu'une ligne d'ordre de travail est ajoutée ou supprimée de l'ordre de travail.
- Si un ordre de travail contient plusieurs tâches d'ordre de travail, l'élément critique le plus élevé, selon le champ **Facteur** dans la page **Types d'élément critique**, est toujours utilisé sur l'ordre de travail.
- En général, l'élément critique de l'actif peut changer sur une période. L'élément critique peut être affecté par l'achat d'un nouvel équipement, les rénovations, etc. Pensez à réévaluer vos éléments critiques d'actif à des intervalles réguliers (par exemple, une fois par an ou tous les deux ans) pour vous assurer que vos définitions d'élément critique correspondent à votre paramétrage de production actuel.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]