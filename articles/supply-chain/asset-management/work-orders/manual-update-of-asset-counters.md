---
title: Mise à jour manuelle des compteurs d'actifs
description: Cette rubrique décrit les mises à jour manuelles des compteurs d'actifs dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875653"
---
# <a name="manual-update-of-asset-counters"></a>Mise à jour manuelle des compteurs d'actifs

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Les compteurs permettent de créer des enregistrements sur un actif concernant, par exemple, le nombre d'heures d'exploitation, ou les quantités produites.

Si le type de compteur sélectionné pour un compteur est défini pour hériter des contre-valeurs (**Gestion des actifs** > **Paramétrage** > **Types d'actif** > **Compteurs** > **Général** organisateur > bouton à bascule **Hériter des contre-valeurs d'actifs** défini sur « Oui »), alors, lorsque vous créez une ligne de compteur de ce type, chaque actif enfant qui utilise le même type de compteur est automatiquement mis à jour.

Dans **Tous les actifs**, vous créez enregistrements de compteur de type heures ou quantité sur un actif, selon vos lectures de l'actif.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**.

2. Sélectionnez l'actif dans la liste et cliquez sur **Compteurs**. Sur l'écran **Compteurs d'actifs**, vous découvrez une liste de tous les enregistrements de compteur précédents sur l'actif sélectionné.

3. Cliquez sur **Nouveau** pour créer un enregistrement. L'ID d'immobilisation est automatiquement inséré.

4. Dans le champ **Compteur**, sélectionnez le compteur pertinent. Seuls les compteurs associés au type d'actif sélectionné sur l'actif sont disponibles. L'unité associée est automatiquement insérée dans le champ **Unité**.

5. Sélectionnez la date et l'heure pour le compteur d'enregistrement.

6. Dans le champ **Valeur**, insérez le nombre depuis le dernier enregistrement de compteur, ou, dans le champ **Valeur associée**, insérez le nombre total.

- Si vous installez physiquement un nouveau compteur sur un actif, vous devez enregistrer la modification sur l'actif dans **Compteurs d'actifs**. Ensuite, vous devez créer deux lignes d'enregistrement avec des groupes date/d'heure identiques, puis sur la ligne concernant le nouveau compteur, activez la case à cocher **Réinitialiser le compteur**. Lorsque vous créez les deux lignes d'enregistrement, la première ligne doit être pour le compteur que vous remplacez. Dans le champ **Totaux**, le total correspond à la somme du total du compteur de toutes les valeurs enregistrées dans ce compteur type.  
- Si la case **Réinitialiser le compteur** est cochée sur un actif à l'aide d'un plan de maintenance avec un intervalle de type « Une fois à partir de… » ou « Une fois atteint… », le compteur est toujours actif sur la nouvelle ligne du compteur, car vous créez une ligne de compteur à part et commencez un nouveau compteur.

![Figure 1](media/11-work-orders.png)


Si vous devez effectuer des enregistrements de compteur sur plusieurs actifs, cela peut s'effectuer dans **Gestion des actifs** > **Recherches** > **Actifs** > **Compteurs d'actifs**.

>[!NOTE]
>Vous pouvez paramétrer une plage pour définir des écarts dans les enregistrements de compteur manuels, et le type de message qui doit être affiché si les enregistrements se font en dehors de la plage définie. Reportez-vous à la section [Compteurs](../setup-for-objects/counters.md) pour plus d'informations sur le paramétrage des compteurs.
