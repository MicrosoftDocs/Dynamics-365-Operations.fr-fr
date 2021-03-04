---
title: Nomenclatures d'actif
description: Cette rubrique décrit les nomenclatures d'actif dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetStandardSparePartsItemGroup, EntAssetObjectBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f42646ae865cd530203c997fd10c8ccd59e7fa2b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428025"
---
# <a name="asset-boms"></a>Nomenclatures d'actif

[!include [banner](../../includes/banner.md)]

 

Cette rubrique décrit les nomenclatures d'actif dans le module Gestion des actifs. La page **Nomenclature des actifs** affiche la liste de tous les articles (pièces détachées et autres articles) qui sont utilisés dans un actif pendant toute sa durée de vie. Lorsque vous créez un actif, vous devez envisager de paramétrer une nomenclature des actifs dans le cadre de la procédure de paramétrage. Vous pouvez ainsi suivre l'historique des articles de l'actif à partir de la date de création.

Après avoir terminé une tâche de maintenance et enregistré la consommation d'articles sur un ordre de travail, vous pouvez suivre la consommation des pièces détachées et des autres articles utilisés dans l'actif. Cette fonctionnalité vous permet de conserver un enregistrement exhaustif de la consommation d'articles pour tous vos actifs. Par exemple, vous pouvez utiliser l'enregistrement pour surveiller si une pièce détachée spécifique est souvent remplacée, ou assurer le suivi des pièces détachées ou des autres articles qui sont actuellement utilisés dans un actif.

> [!NOTE]
> Sur un ordre de travail, la consommation d'articles peut inclure les pièces détachées et d'autres articles supplémentaires, tels que les lubrifiants, les boulons et les joints.

Une nomenclature des actifs peut être automatiquement mise à jour selon le paramétrage dans le module Gestion des actifs. Si un état du cycle de vie de l'ordre de travail a été créé pour gérer les ordres de travail finis ou terminés, et si l'option **Mettre à jour la nomenclature des actifs** pour cet état du cycle de vie de l'ordre de travail est définie sur **Oui** dans la page **États du cycle de vie de l'ordre de travail**, tous les articles utilisés sur l'ordre de travail sont automatiquement mis à jour dans la page **Nomenclature des actifs** lorsque l'ordre de travail est mis à jour sur cet état du cycle de vie. 


Vous pouvez également mettre à jour manuellement une nomenclature des actifs en créant de nouvelles lignes d'article dans la page **Nomenclature des actifs**.

Dans la page **Nomenclature des actifs**, vous pouvez suivre l'historique des pièces détachées pour les actifs après avoir enregistré la consommation d'articles sur un ordre de travail. Pour utiliser cette fonctionnalité, vous devez sélectionner les groupes d'articles qui doivent être utilisés pour l'enregistrement des pièces détachées dans la page **Groupes d'éléments de pièce détachée**.

Pour utiliser la fonctionnalité Nomenclature des actifs, vous devez d'abord paramétrer les groupes d'éléments de pièce détachée requis. Ensuite, si vous souhaitez mettre à jour automatiquement la nomenclature des actifs à la fin d'un ordre de travail, vous pouvez paramétrer un état du cycle de vie de l'ordre de travail pour gérer cette mise à jour. 


## <a name="set-up-spare-parts-item-groups"></a>Paramétrer des groupes d'éléments de pièce détachée

Le paramétrage de l'historique des pièces détachées est basé sur les groupes d'articles créés dans le module **Gestion des entrepôts et des stocks**. Dans le module Gestion des actifs, vous pouvez paramétrer des groupes d'articles afin de pouvoir suivre l'historique des pièces détachées pour les articles des groupes d'articles sélectionnés.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actif** \> **Groupes d'éléments de pièce détachée**.
2. Sélectionnez **Nouveau** pour paramétrer un groupe d'articles.
3. Dans le champ **Groupe d'articles**, sélectionnez le groupe. Le nom du groupe est automatiquement entré dans le champ **Nom**.

## <a name="view-and-update-asset-boms"></a>Afficher et mettre à jour les nomenclatures des actifs

Après avoir validé la consommation d'articles sur un ordre de travail, vous pouvez afficher la consommation enregistrée dans la page **Nomenclature des actifs**.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Actifs actifs**. Sélectionnez l'actif dans la liste, puis sélectionnez **Nomenclature des actifs**.

    > [!NOTE]
    > Pour afficher tous les enregistrements de consommation d'articles pour tous les actifs, sélectionnez **Gestion des actifs** \> **Recherches** \> **Actifs** \> **Nomenclature des actifs**.

2. Sélectionnez **Mettre à jour la nomenclature des actifs**. Vous pouvez ajouter des actifs, des types d'actifs et des ressources à la mise à jour si nécessaire en cliquant sur **Sélectionner**. Sélectionnez **OK** pour démarrer la mise à jour. Vous pouvez également paramétrer la fonction de mise à jour en tant que traitement par lots.
3. Si vous souhaitez afficher d'autres informations associées aux articles, vous pouvez ajouter des dimensions de stock. Sélectionnez **Stock** \> **Affichage des dimensions**, puis activez les cases à cocher des dimensions que vous souhaitez afficher. Pour conserver ce paramétrage pour tous les actifs dans la page **Nomenclature des actifs**, définissez l'option **Enregistrer le paramétrage** sur **Oui**.
4. Pour avoir une vue d'ensemble de l'emplacement d'utilisation dans le module Gestion des actifs de l'article sur la ligne sélectionnée, en ce qui concerne les actifs, les valeurs par défaut du type de tâche, les pièces détachées et les ordres de travail, sélectionnez **Cas d'emploi d'article**. 
5. Si vous souhaitez afficher uniquement les lignes d'article actives, sélectionnez **Afficher** \> **Actuel**. Pour afficher toutes les lignes d'article, y compris les lignes où la date d'expiration est antérieure à la date actuelle, sélectionnez **Afficher** \> **Tous**.

> [!NOTE]
> Après avoir terminé un ordre de travail, si certains articles ou certaines pièces détachées associés à l'actif ont expiré ou ont été remplacés par d'autres articles ou pièces détachés, nous vous recommandons de mettre à jour la nomenclature des actifs en conséquence.

## <a name="create-a-new-item-line-in-an-asset-bom"></a>Créer une ligne d'article dans une nomenclature des actifs

Vous pouvez créer manuellement des lignes d'article pour les actifs.

1. Dans la page **Nomenclature des actifs**, sélectionnez **Nouveau**.
2. Dans le champ **Actif**, sélectionnez l'actif pour lequel ajouter une ligne d'article.
3. Dans le champ **Numéro de ligne**, entrez un numéro de ligne séquentiel.
4. Dans le champ **Date d'effet**, entrez une date de début pour l'article.
5. Si l'article expire, dans le champ **Expiration**, entrez une date de fin.
6. Dans le champ **Numéro d'article**, sélectionnez l'article. Le nom est automatiquement entré dans le champ **Nom du produit**.
7. Dans le champ **Quantité**, entrez la quantité utilisée. Le champ **Unité** est mis à jour automatiquement.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]