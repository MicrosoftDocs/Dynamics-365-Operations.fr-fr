---
title: Paramétrage du projet de l’ordre de travail
description: Cette rubrique explique le paramétrage du projet de l’ordre de travail dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjectSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb897ca0a7e9c45ee55244189bb1b487fbddf0714ad3ea0cac26eb7bac36a07f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754081"
---
# <a name="work-order-project-setup"></a>Paramétrage du projet de l’ordre de travail

[!include [banner](../../includes/banner.md)]

 

Dans le module **Gestion des actifs**, une relation de projet est requise pour chaque tâche de l’ordre de travail. Le projet associé à une tâche de l’ordre de travail vous permet de suivre les coût sur différents projets associés au module Gestion des actifs, comme les projets de maintenance interne, les projets de gestion de service et les projets d’investissement. 

## <a name="project-setup-for-a-work-order-job"></a>Configuration des projets pour une tâche de l’ordre de travail

Lorsque vous créez une tâche de l’ordre de travail sur un ordre de travail, le paramétrage de projet dans le module **Gestion de projets et comptabilité** et le paramétrage de projet de l’ordre de travail dans le module **Gestion des actifs** déterminent la manière dont les projets peuvent être utilisés pour le contrôle des coûts sur l’actif sélectionné sous cette tâche de l’ordre de travail. Cette section décrit les parties suivantes du paramétrage de projet utilisé pour un ordre de travail : le projet parent (ID de projet), le type de projet, les activités de projet et les dimensions financières :

- Lorsque vous créez une tâche de l’ordre de travail sur un ordre de travail, un ID de projet unique et une activité de projet associée sont automatiquement créés à cet effet. Toutefois, si plusieurs tâches de l’ordre de travail sur un ordre de travail incluent le même actif, le même ID de projet est utilisé pour elles. En d’autres termes, un ID de projet est créé pour chaque actif d’un ordre de travail.

    - Le projet parent (ID projet) pour une tâche de l’ordre de travail se trouve dans le paramétrage du projet parent. (Pour en savoir plus sur la configuration du projet parent, consultez la section suivante). Par exemple, si vous associez un client ou un poste technique à un projet parent spécifique, le projet parent est utilisé chaque fois que vous créez des ordres de travail pour ce client ou ce poste technique. Si vous n’associez pas d’ID projet spécifique, par exemple, un poste technique, le prochain projet parent pertinent dans le paramétrage du projet de l’ordre de travail est utilisé.
    - Un type de projet est nécessaire pour chaque ID de projet. Le type de projet est dans le paramétrage de la configuration du groupe de projets. (Pour en savoir plus sur la configuration du groupe de projets, consultez la section suivante.) Si aucune correspondance n’est trouvée dans la configuration du groupe de projets, la configuration du groupe de projets sur le projet parent est utilisée.
    - Le paramétrage pour les activités de projet nécessaires sur les prévisions et les journaux est copié du projet parent vers le projet de l’ordre de travail. Si les options **Heure**, **Dépense** et **Article** sont définies sur **Oui** pour le projet qui est utilisé comme projet parent, une activité de projet est obligatoire pour les prévisions et journaux. (Pour accéder à ces options, sélectionnez **Gestion de projets et comptabilité** \> **Project** \> **Tous les projets**, puis sélectionnez le projet qui est utilisé comme projet parent. Les options sont dans la section **Demander une activité sur les journaux** sur l’organisateur **Paramétrage** .)

- Les dimensions financières sont copiées depuis l’actif et fusionnées avec le projet parent.

La section suivante explique la procédure de paramétrage des projets parents et des groupes de projets. Le projet parent et les groupes parents sont utilisés pour contrôler les ordres de travail. Ils sont également utilisés pour générer un état sur les ordres de travail.

## <a name="set-up-work-order-projects"></a>Configurer des projets de l’ordre de travail

Avant de commencer à créer des ordres de travail, vous devez configurer les projets de l’ordre de travail. La page **Configuration du projet de l’ordre de travail** (**Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Paramétrage de Projet**) contient deux onglets : **Projet parent** et **Groupe de projets**.

Sur l’onglet **Projet parent**, vous pouvez paramétrer les relations de projet qui peuvent être utilisées si aucun projet n’est paramétré sur l’actif sélectionné dans la tâche de l’ordre de travail. Un paramétrage de projet parent n’est pas requis si votre société utilise des projets d’actif. Cela est utile uniquement si vous souhaitez utiliser des projets de l’ordre de travail plutôt que des projets d’actif. Dans ce cas, vous devez paramétrer au moins un projet parent.

Dans l’onglet **Groupe de projets**, vous pouvez paramétrer des groupes de projets qui peuvent être associés à des types d’ordre de travail, des types d’actifs et des actifs.

Les groupes de projets peuvent être utilisés pour créer les catégories spécifiques (groupes) utilisées pour le contrôle des coûts. Par exemple, lors de la création des groupes de projets pour les types d’actifs ou types d’ordres de travail spécifiques, vous pouvez effectuer un suivi détaillé des coûts de maintenance par type.

Les groupes de projet ne sont pas obligatoires. Si vous ne paramétrez pas les groupes de projets, le projet parent est utilisé afin de déterminer le groupe de projet et un projet enfant est créé depuis le groupe de projets du projet parent.

Le paramétrage permet l’intégration complète au module **Gestion de projets et comptabilité**. Par conséquent, vous pouvez suivre les coûts liés aux ordres de travail dans les projets associés. La procédure suivante décrit le paramétrage des projets de l’ordre de travail.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Paramétrage du projet**.
2. Sur l’onglet **Projet parent**, sélectionnez **Ajouter**.
3. Dans les champs **Type d’ordre d’exécution**, **Poste technique**, **Type d’actif** et **Actif**, sélectionnez les valeurs comme vous le souhaitez. Pour chaque ligne ajoutée, vous pouvez définir un seul champ ou plusieurs champs. Le nombre de champs que vous attribuez détermine la combinaison utilisée lorsqu’un ID projet est sélectionné dans le module Gestion des actifs. 

    Si vous sélectionnez un poste technique, les emplacements enfants associés sont automatiquement inclus. Si vous sélectionnez un actif, vous pouvez créer plus de lignes de paramétrage de projet de l’ordre de travail pour le même actif, mais vous pouvez sélectionner différents projets pour cet actif.

4. Dans le champ **ID projet**, sélectionnez le projet qui doit être associé au paramétrage créé à l’étape 3.
5. Si le paramétrage de projet est valide pour une seule période limitée, sélectionnez une date de fin dans le champ **Date de fin**. Sinon, sélectionnez **Aucune**.

    Par défaut, la date de début est la date à laquelle vous ajoutez le projet de l’ordre de travail à la page. Cela est contrôlé par le champ **Début de validité**, qui est masqué par défaut. Pour afficher le champ **Début de validité**, sélectionnez **Afficher** \> **Tout**. Vous pouvez ensuite utiliser le champ **Début de validité** avec le champ **Date de fin** pour paramétrer une période limitée de validité du projet de l’ordre de travail.

    ![Page Configuration de projet d’ordres de travail.](media/17-setup-for-work-orders.png)

6. Sur l’onglet **Groupe de projets**, sélectionnez **Ajouter**.
7. Dans le champ **Type d’ordre de travail**, sélectionnez un type d’ordre de travail.
8. Si vous souhaitez que l’association de groupe de projets soit plus spécifique, sélectionnez un type d’actif dans le champ **Type d’actif** ou un actif dans le champ **Actif**.
9. Dans le champ **Groupe de projets**, sélectionnez le groupe de projets devant être associé au type d’ordre de travail. Par exemple, un type d’ordre de travail intitulé **Maintenance préventive** peut être associé à un groupe de projets intitulé **Maint prev** ou **Interne**. Sinon, un ordre de travail de type **Investissement** utilisé pour les ordres de travail associés aux investissements et aux immobilisations peut être associé à un groupe de projets nommé **Investir** ou **Investissement**.
10. Sélectionnez **Enregistrer**.

![Page Configuration de projet d’ordres de travail, Ajouter un ordre de travail.](media/18-setup-for-work-orders.png)

> [!NOTE]
> Chaque fois qu’une ligne d’ordre de travail est créée, le module Gestion des actifs recherche un groupe de projets qui doit être associé au projet de la tâche de l’ordre de travail. La recherche est basée sur le paramétrage décrit dans cette rubrique. Chaque groupe de projets a un type de projet associé. Les groupes de projets dont le projet est de type **Régie** ou **Prix fixe** sont valides uniquement pour les actifs associés à un compte client.
>
> Pour les projets parents et les groupes de projets, quand le système sélectionne le projet ou le groupe de projets de l’ordre de travail disponible, la sélection est basée sur les enregistrements que vous avez créés à l’aide de la procédure précédente. Le module Gestion des actifs parcourt les enregistrements associés au projet de l’ordre de travail pour vérifier une correspondance éventuelle. Il vérifie toujours la combinaison la plus spécifique en premier. En d’autres termes, le projet parent de l’ordre de travail, le module Gestion des actifs recherche d’abord une correspondance éventuelle pour le champ **Actif**. Si aucune correspondance n’est trouvée, il recherche une correspondance pour le champ **Type d’actif**. Si aucune correspondance n’est trouvée, il recherche une correspondance pour le champ **Poste technique**, etc. Comme vous pouvez voir dans la disposition de la page **Paramétrage du projet de l’ordre de travail**, ce comportement signifie que, pour trouver la combinaison la plus spécifique, le module Gestion des actifs recherche une correspondance dans chaque enregistrement en allant de la droite vers la gauche. Si aucune correspondance n’est détectée, l’enregistrement par défaut où seul un ID de projet est sélectionné est utilisé. Le processus pour trouver le groupe de projets associé est similaire. Le module Gestion des actifs vérifie d’abord une correspondance éventuelle pour le champ **Actif**, puis le champ **Type d’actif**, puis le champ **Type d’ordre de travail**. Si aucune correspondance n’est détectée, l’enregistrement par défaut où seul un groupe de projets est sélectionné est utilisé.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]