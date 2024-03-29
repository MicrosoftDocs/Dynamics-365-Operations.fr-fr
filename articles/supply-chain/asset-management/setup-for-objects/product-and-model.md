---
title: Fabricants et modèles d’actif
description: Cet article explique comment paramétrer des fabricants d’actif et des modèles associés dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b00cb62926f3a482ec655235b6e2f5880edbcd04
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016273"
---
# <a name="asset-manufacturers-and-models"></a>Fabricants et modèles d’actif

[!include [banner](../../includes/banner.md)]

 

Cet article explique comment paramétrer des fabricants d’actif et des modèles associés dans le module Gestion des actifs. Les modèles peuvent être associés à des types d’actif.

## <a name="set-up-product-model-relations"></a>Définir les relations entre le produit et le modèle

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Actifs** \> **Fabricant et modèle**.
2. Sélectionnez **Nouveau** pour créer un produit.
3. Dans le champ **Fabricant**, entrez un nom pour le fabricant d’actif.
4. Entrez une description dans le champ **Description**.
5. Dans le raccourci **Modèles**, sélectionnez **Ajouter** pour créer un modèle d’actif qui doit être associé au fabricant d’actif.
6. Dans le champ **Modèle**, entrez un nom pour le modèle d’actif.
7. Entrez une description dans le champ **Description**.
8. Dans le champ **Type d’actif**, sélectionnez le type d’actif auquel le modèle de fabricant doit être associé.

    > [!NOTE]
    > Vous pouvez également définir des relations pour les types, les fabricants et les modèles d’actif dans la recherche **Types d’actif**. Pour plus d’informations, voir [Types d’actif](../setup-for-objects/object-types.md).

    Dans le raccourci **Détails**, le champ **Modèles** affiche le nombre de modèles d’actif qui sont paramétrés sur le fabricant d’actif sélectionné. Le champ **Actifs** affiche le nombre d’actifs qui utilisent le fabricant sélectionné.
    
    Le champ **Actifs** affiche le nombre d’objets qui utilisent le modèle de fabricant.

> [!NOTE]
> Un type d’actif peut ne pas avoir de relations de modèle de fabricant, il peut être associé à un modèle de fabricant d’actif ou il peut être associé à plusieurs modèles de fabricant d’actif. Si un type d’actif est associé à au moins un modèle de fabricant, seules les combinaisons paramétrées dans la recherche **Modèle de fabricant** peuvent être sélectionnées dans les pages Gestion des actifs où une combinaison d’un type, d’un fabricant et d’un modèle d’actif peut être paramétrée. Ces pages incluent **Tous les actifs**, **Niveaux de service d’actifs**, **Valeurs par défaut du type de tâche** et **Lignes de budget de maintenance**. Si certains types d’actif ne sont associés à aucun modèle de fabricant, seuls les types d’actif et les modèles de fabricant qui n’ont aucun relation avec les types d’actif, s’affichent sur les pages.

## <a name="select-a-manufacturer-and-model-on-an-object"></a>Sélectionnez un fabricant et un modèle sur un objet

1. Sélectionnez **Gestion des actifs** \> **_Actifs_* \> **Tous les actifs**.
2. Dans la colonne **Actif**, sélectionnez le lien de l’actif. La page **Détails** s’affiche.
3. Sélectionnez **Modifier**.
4. Dans le raccourci **Général**, sélectionnez des valeurs dans les champs **Fabricant** et **Modèle**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]