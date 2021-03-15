---
title: Types d'actif
description: Cette rubrique explique comment créer des types d'actif dans le module Gestion des actifs. Elle décrit également les éléments associés aux types d'actif.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectJobType, EntAssetObjectType, EntAssetObjectTypeDefaultSparePart, EntAssetObjectTypeDefaultSparePartApprove, EntAssetObjectTypeDefaultCreateCombinations, EntAssetObjectTypeDefault, EntAssetObjectTypeDefaultCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 295840c12f89bc6c6a4d53023985259ac761d6b2
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017415"
---
# <a name="asset-types"></a>Types d'actif

[!include [banner](../../includes/banner.md)]



Cette rubrique explique comment créer des types d'actif. Elle décrit également les éléments associés aux types d'actif. Les types d'actif sont utilisés comme catégories générales pour les actifs. Les machines CNC, les équipements de mesure et les moteurs de camion sont des exemples. Les types d'actif sont utilisés pour gérer les types de tâche de maintenance (tâches de maintenance), les états du cycle de vie de l'actif, les compteurs, les attributs d'actif, les modèles d'évaluation des conditions et les modèles d'actif qui peuvent être sélectionnés pour un actif. Lorsque vous créez un actif, vous devez indiquer son type.

Pour chaque type d'actif, des variations du paramétrage du type d'actif peuvent être créées. Par exemple, si un type d'actif est nommé **Camions**, vous pouvez créer des variations de ce type d'actif pour différents fabricants d'actif et modèles d'actif. À chaque paramétrage du type d'actif, vous pouvez ajouter les pièces détachées et les plans de maintenance requis.

Tout d'abord, vous paramétrez les types d'actif requis. Ensuite, vous créez les modèles d'actif qui doivent être associés aux types d'actif. Enfin, dans la page **Valeurs par défaut du type d'actif**, vous créez toutes les variations de types d'actif qui sont nécessaires pour votre équipement.

## <a name="create-an-asset-type"></a>Créer un type d'actif

1. Sélectionnez **Gestion des actifs** > **Paramétrage** > **Types d'actif** > **Types d'actif**.
2. Sélectionnez **Nouveau** pour créer un type d'actif.
3. Dans le champ **Type d'actif**, entrez un ID de type d'actif.
4. Dans le champ **Nom**, entrez un nom.
5. Dans le champ **Modèle de cycle de vie de l'actif**, sélectionnez un modèle de cycle de vie de l'actif. Pour plus d'informations sur les états du cycle de vie de l'actif et les modèles de cycle de vie de l'actif, voir [États du cycle de vie de l'actif](object-stages.md).
6. Définissez l'option **Total** sur **Oui** si les valeurs KPI résumées doivent être calculées pour les actifs de ce type.
7. Sélectionnez **Enregistrer**.
8. Dans l'organisateur **Types de tâches de maintenance**, sélectionnez les types de tâches de maintenance qui doivent être associés au type d'actif :

    - Pour sélectionner un type de tâche de maintenance, sélectionnez-le dans le champ **Types de tâche de maintenance restants**, puis utilisez le bouton Flèche droite ![bouton Flèche droite](media/29-setup-for-objects.png) pour le déplacer vers la section **Types de tâche de maintenance sélectionnés**.
    - Pour sélectionner tous les types de tâche de maintenance disponibles, utilisez le bouton ![Transférer tout](media/30-setup-for-objects.png). Tous les types de tâche de maintenance sont transférés du champ **Types de tâche de maintenance restants** vers le champ **Types de tâche de maintenance sélectionnés**.
    - Pour annuler la sélection d'un type de tâche de maintenance, sélectionnez-le dans le champ **Types de tâche de maintenance sélectionnés**, puis utilisez le bouton Flèche gauche ![bouton Flèche gauche](media/31-setup-for-objects.png) pour le déplacer vers le champ **Types de tâche de maintenance restants**.

9. Vous pouvez également sélectionner les compteurs qui doivent être associées au type d'actif. Dans le raccourci **Compteurs**, effectuez vos sélections à l'aide des méthodes décrites pour les types de tâche de maintenance à l'étape 8. Pour plus d'informations sur la configuration des compteurs, voir [Compteurs](counters.md).
10. Vous pouvez également sélectionner les types d'attribut qui doivent être associés au type d'actif. Dans le raccourci **Types d'attribut**, effectuez vos sélections à l'aide des méthodes décrites pour les types de tâche de maintenance à l'étape 8. Ensuite, pour créer la séquence préférée de types d'attribut, sélectionnez un type d'attribut dans le champ **Types d'attribut sélectionnés**, puis utilisez les boutons Flèche haut et Flèche bas pour le déplacer. La séquence de types d'attributs s'affichera sur les actifs qui utilisent ce type d'actif. Pour plus d'informations sur les attributs d'actif, voir [Types d'attribut de maintenance](../setup-for-functional-locations/specification-types.md).

    > [!NOTE]
    > Lorsque vous ajoutez de nouveaux types d'attribut dans le raccourci **Types d'attribut**, les actifs existants sont automatiquement mis à jour avec ces informations.

11. Vous pouvez également sélectionner les modèles d'évaluation des conditions qui doivent être associés au type d'actif. Dans le raccourci **Évaluations des conditions**, effectuez vos sélections à l'aide des méthodes décrites pour les types de tâche de maintenance à l'étape 8. Pour plus d'informations sur les modèles et les enregistrements d'évaluation des conditions, voir [Évaluation des conditions](../setup-for-objects/condition-assessment.md).
12. Le raccourci **Modèle d'actif** affiche toutes les combinaisons de fabricants et de modèles d'actif qui sont paramétrées sur le type d'actif sélectionné. Pour afficher les combinaisons divisées en fonction du fabricant, sélectionnez **Modèle d'actif** pour ouvrir la page **Modèle d'actif**.

    Dans la page **Modèle d'actif**, vous pouvez ajouter des relations entre le modèle d'actif et le type d'actif. En outre, dans la page **Types d'actif**, vous pouvez ajouter des relations entre le fabricant d'actif et le modèle d'actif directement à un type d'actif. Enfin, dans la page **Modèle d'actif** (**Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Modèle d'actif**), vous pouvez créer des relations entre le fabricant d'actif, le modèle d'actif et le type d'actif. Par conséquent, il existe trois manières de paramétrer et de modifier les relations entre le fabricant d'actif, le modèle d'actif et le type d'actif. Toutes les combinaisons disponibles s'affichent selon des perspectives différentes, et vous pouvez sélectionner votre point d'entrée préféré lorsque vous définissez le paramétrage.

> [!NOTE]
> - Si vous sélectionnez les compteurs sur un type d'actif, les sélections sont automatiquement mises à jour sur la page **Compteurs** (**Gestion des actifs** > **Paramétrage** > **Actifs** > **Types d'actifs** > **Compteurs**).
> - Les champs de la section **Détails** du raccourci **Général** affichent le nombre de types de tâche de maintenance, de compteurs, d'attributs, etc., qui sont paramétrés sur le type d'actif sélectionné.

Généralement, les ordres de travail créés manuellement sont associés à la maintenance corrective, tandis que les ordres de travail créés automatiquement sont associés à la maintenance préventive. Lorsque vous créez manuellement des ordres de travail, seuls les types de tâche de maintenance sélectionnés dans le raccourci **Types de tâche de maintenance** de la page **Types d'actif** peuvent être utilisés. Toutefois, les ordres de travail créés automatiquement peuvent utiliser tous les types de tâche de maintenance que vous créez dans la page **Types de tâche de maintenance** (**Gestion des actifs** \> **Paramétrage** \> **Tâches** \> **Types de tâche de maintenance**).

## <a name="create-asset-type-setup-lines"></a>Créer des lignes de paramétrage du type d'actif

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Types d'actif** \> **Paramétrage du type d'actif**. Sinon, sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Types d'actif** \> **Types d'actif**, sélectionnez un type d'actif, puis sélectionnez **Paramétrage du type d'actif**.
2. La première fois que vous utilisez la page **Paramétrage du type d'actif**, vous trouverez le bouton **Créer des combinaisons** utile. Vous pouvez utiliser ce bouton pour créer rapidement toutes les combinaisons d'un modèle d'actif sur un type d'actif. Sélectionnez **Créer des combinaisons**, sélectionnez le type d'actif pour lequel créer des combinaisons, puis sélectionnez **OK**.

    > [!NOTE]
    > Si vous n'utilisez pas toutes les combinaisons de paramétrage du type d'actif qui ont été créées automatiquement, vous pouvez supprimer un paramétrage en le sélectionnant et en cliquant sur **Supprimer**.

3. Sélectionnez **Nouveau** pour créer manuellement un paramétrage du type d'actif.
4. Selon la spécificité du paramétrage du type d'actif, effectuez vos sélections dans les champs **Type d'actif**, **Fabricant** et **Modèle**.
5. Si un contrat de garantie est associé au type d'actif, sélectionnez le contrat dans les champs **Garantie fournisseur** et **Garantie client**. 
6. Dans le raccourci **Pièces détachées**, sélectionnez **Ajouter** pour ajouter des pièces détachées au paramétrage du type d'actif.
7. Pour approuver une pièce détachée, sélectionnez la ligne de pièce détachée, puis sélectionnez **Approuver**. Vous pouvez sélectionner plusieurs lignes pour approbation.
8. Pour voir si une pièce détachée est utilisée ailleurs dans le module Gestion des actifs (par exemple, pour les actifs et les ordres de travail), sélectionnez la ligne de pièce détachée, puis sélectionnez **Cas d'emploi d'article** pour ouvrir la page **Cas d'emploi d'article**. Pour afficher toutes les pièces détachées actives dans la liste, activez la case à cocher **Actif**. Pour afficher uniquement les pièces détachées approuvées, activez la case à cocher **Approuvé**.
9. Dans le raccourci **Plans de maintenance**, sélectionnez **Ajouter** pour ajouter des plans de maintenance au paramétrage de type d'actif sélectionné.
10. Pour copier un paramétrage de type d'actif vers un autre paramétrage, vous pouvez utiliser la fonction de copie. Sélectionnez le paramétrage de type actif vers lequel copier un paramétrage, sélectionnez **Copier le paramétrage**, puis sélectionnez le paramétrage de type actif à partir duquel copier le paramétrage. Les paramètres des différentes options déterminent la quantité d'informations incluses. Lorsque vous avez terminé, sélectionnez **Ajouter** pour copier le paramétrage.

> [!NOTE]
> Si plusieurs lignes de pièce détachée et lignes de plan de maintenance seront réutilisées, la fonction de copie vous permet de paramétrer rapidement et facilement des données pour plusieurs combinaisons de paramétrage de type d'actif.

## <a name="spare-parts-on-the-asset-type-setup"></a>Pièces détachées pour le paramétrage du type d'actif

Comme décrit dans la section « Créer des lignes de paramétrage du type d'actif », les pièces détachées sont paramétrées sur les modèles d'actif dans la page **Paramétrage du type d'actif**. Par conséquent, lorsque vous ouvrez la page **Paramétrage du type d'actif**, seules les pièces détachées associées à la combinaison sélectionnée d'un type d'actif, d'un fabricant d'actif et d'un modèle d'actif s'affichent. Pour afficher la liste de tous les enregistrements de pièce détachée, ouvrez la page **Pièces détachées** (**Gestion des actifs** \> **Recherches** \> **Pièces détachées**).

Dans la page **Pièces détachées**, vous pouvez également créer des pièces détachées pour les combinaisons existantes d'un type d'actif, d'un fabricant d'actif et d'un modèle d'actif. Vous pouvez choisir si vous préférez créer des enregistrements de pièce détachée sur la page **Paramétrage du type d'actif** ou la page **Pièces détachées**. La page **Paramétrage du type d'actif** donne une vue d'ensemble des données de la combinaison sélectionnée d'un type d'actif, d'un fabricant d'actif et d'un modèle d'actif, tandis que la page **Pièces détachée** donne une vue d'ensemble complète de toutes les lignes de paramétrage du type d'actif. Si la page **Pièces détachées** contient plusieurs enregistrements, la page **Paramétrage du type d'actif** vous donne une meilleure vue d'ensemble.

Pour voir si la pièce détachée sur la ligne sélectionnée est utilisée ailleurs dans le module Gestion des actifs (par exemple, pour les actifs et les ordres de travail), sélectionnez **Cas d'emploi d'article** pour ouvrir la page **Cas d'emploi d'article**. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]