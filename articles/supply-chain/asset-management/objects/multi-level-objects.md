---
title: Actifs à plusieurs niveaux
description: Cet article explique comment créer et supprimer des actifs à plusieurs niveaux.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34ab83c9f9673c39006b3985ebaac9e17a45da82
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908770"
---
# <a name="multi-level-assets"></a>Actifs à plusieurs niveaux

[!include [banner](../../includes/banner.md)]

 

Cet article explique comment créer et supprimer des actifs à plusieurs niveaux. Vous pouvez créer des actifs et des sous-actifs associés dans une structure arborescente hiérarchique. De cette manière, vous pouvez afficher les relations et les dépendances entre les actifs. Les tâches de maintenance peuvent être associées à tous les niveaux de la structure arborescente. Des statistiques peuvent également être créées à un niveau particulier ou en tant que somme de tous les sous-niveaux.

Sur la page de liste **Tous les actifs** (**Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les actifs**), la colonne **Actif** répertorie les actifs dans l’ordre hiérarchique. La colonne **Parent** affiche le parent associé. En outre, si les actifs et les sous-actifs ont déjà été créés, la section **Arborescence d’actifs** du volet **Informations associées** affiche les actifs sous forme de structure arborescente.

Pour plus d’informations sur la création d’un actif, voir [Créer un actif](../objects/create-an-object.md). Pour créer un sous-actif, sélectionnez l’actif parent dans le champ **Parent** sur l’organisateur **Général**.

## <a name="copy-an-asset-or-asset-structure"></a>Copier un actif ou une structure d’actif

Si votre société a plusieurs structures d’actifs similaires, vous pouvez utiliser la fonction Copier dans Gestion des actifs pour en créer rapidement.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les actifs**.
2. Sur la page de liste **Tous les actifs**, sélectionnez l’actif à copier. Par exemple, si vous souhaitez copier la structure d’actif complète, y compris les sous-actifs, sélectionnez un actif parent.
3. Sélectionnez **Copier l’actif**. Dans la section **Copier depuis**, le champ **Actif** est défini sur l’actif sélectionné dans la page de liste.
4. Dans la section **Copier vers**, dans le champ **Actif**, entrez le nom du nouvel actif.
5. Si l’actif créé doit faire partie d’une structure d’actif existante, dans la section **Actif parent**, dans le champ **Actif**, sélectionnez un ID parent.
6. Cliquez sur **OK**. La nouvelle structure d’actif est affichée sur la page de liste **Tous les actifs**. Tous les attributs d’actif, plans de maintenance et visites de maintenance associés à l’actif copié sont transférés vers le nouvel actif ou la nouvelle structure d’actif.

Lorsque vous copiez une structure d’actif, les sous-actifs de la nouvelle structure ont le même nom que les sous-actifs que vous avez copiés. Une fois la procédure de copie terminée, vous pouvez aisément modifier le nom et d’autres paramètres d’un actif. Sélectionnez l’actif sur la page de liste **Tous les actifs**, puis sélectionnez le bouton **Modifier**.

> [!NOTE]
> Lorsque vous copiez un actif ou une structure d’actif, l’état du cycle de vie du nouvel actif est réinitialisé à l’état que vous avez défini comme l’état de cycle de vie initial pour les actifs. Le poste technique est redéfini sur le poste technique par défaut.

## <a name="delete-an-asset-or-asset-structure"></a>Supprimer un actif ou une structure d’actif

Si un actif a des sous-actifs associés, vous pouvez le supprimer uniquement si aucune demande de maintenant, tâche d’ordre de travail, enregistrement de défaillance ou évaluation des conditions ne sont enregistrés sur l’un des actifs.

1. Sur la page de liste **Tous les actifs**, sélectionnez l’actif à supprimer.
2. Sélectionnez **Supprimer**.

> [!NOTE]
> Si vous ne pouvez pas supprimer un actif à l’aide de cette procédure, vous pouvez également paramétrer un état du cycle de vie de l’actif à cet effet. Par exemple, vous pouvez paramétrer un état du cycle de vie **Mis au rebut** ou **Supprimé** sur la page **États du cycle de vie de l’actif**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]