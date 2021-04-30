---
title: Créer un groupe de baux
description: Cette rubrique explique comment paramétrer des groupes de baux. Les groupes de baux sont obligatoires pour créer de baux.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseGroupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 88a49e4db868078fd05875df33ca5727363aaa18
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881226"
---
# <a name="create-a-lease-group"></a>Créer un groupe de baux

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment paramétrer des groupes de baux. Les groupes de baux sont obligatoires pour créer de baux. Les registres de baux sont associés à chaque groupe de baux. Les registres de baux déterminent les registres par défaut qui doivent être créés pour chaque bail. Vous pouvez affecter des comptes spécifiques à un groupe de baux sur la page **Paramètres d’affichage du bail**.

## <a name="create-a-lease-book-and-add-a-lease-group"></a>Créer un registre de baux et ajouter un groupe de baux

1. Accédez à **Location d’actifs \> Configuration \> Groupes de baux**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un groupe de baux. Une ligne est ajoutée à la grille.
3. Sur la nouvelle ligne, dans le champ **Groupe de baux**, entrez une valeur.
4. Dans le champ **Description**, entrez une valeur.

Les informations que vous venez de saisir sont ajoutées au champ **Groupe de baux** sur la page **Ajouter un bail**.

## <a name="associate-a-book-with-a-lease-group"></a>Associer un registre à un groupe de baux

Après avoir créé des groupes de baux, vous pouvez attribuer des registres à chaque groupe. Lorsque vous créez un bail et que vous l’affectez à un groupe de baux, le système crée un ensemble de programmes pour chaque registre associé à ce groupe de baux.

> [!NOTE]
> Les registres doivent être configurés avant de pouvoir être affectés à un groupe de baux.

1. Accédez à **Location d’actifs \> Configuration \> Groupe de baux**.
2. Sélectionnez un groupe de baux, puis sélectionnez **Registres**.
3. Sélectionnez **Nouveau**, puis, dans le champ **Type de registre**, sélectionnez le registre à affecter au groupe de baux. Vous pouvez affecter plusieurs registres à un groupe de baux si un bail doit être comptabilisé de différentes manières.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
