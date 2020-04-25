---
title: Mise à jour manuelle des compteurs d'actifs
description: Cette rubrique décrit les mises à jour manuelles des compteurs d'actifs dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9d9cd755f5dec125676a8dbefe63a64e226366ed
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204514"
---
# <a name="manual-update-of-asset-counters"></a>Mise à jour manuelle des compteurs d'actifs

[!include [banner](../../includes/banner.md)]



Les compteurs permettent de créer des enregistrements sur un actif, comme des enregistrements du nombre d'heures fonctionnelles de l'actif ou la quantité produite.

Le type de compteur sélectionné pour un compteur peut être défini pour hériter des valeurs du compteur. En d'autres termes, l'option **Hériter des contre-valeurs d'actifs** est définie sur **Oui** dans l'organisateur **Général** de la page **Compteurs** (**Gestion des actifs** > **Paramétrage** > **Types d'actifs** > **Compteurs**). Dans ce cas, lorsque vous créez une ligne de compteur de ce type, chaque actif enfant qui utilise le même type de compteur est automatiquement mis à jour.

Sur la page **Tous les actifs**, vous créez enregistrements de compteur de type heures ou quantité sur un actif, selon vos lectures de l'actif.

1. Sélectionnez **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**.

2. Sélectionnez l'actif, puis dans le volet Actions, sous l'onglet **Actif**, dans le groupe **Préventif**, sélectionnez **Compteurs**. La page **Compteurs d'actifs** affiche une liste de tous les enregistrements de compteur précédents effectués sur l'actif sélectionné.

3. Sélectionnez **Nouveau** pour créer une inscription. L'ID actif est automatiquement entré dans le champ **Actif**.

4. Dans le champ **Compteur**, sélectionnez le compteur pertinent. Seuls les compteurs associés au type d'actif sélectionné sur l'actif sont disponibles pour sélection. L'unité associée est automatiquement entrée dans le champ **Unité**.

5. Dans le champ **Enregistré**, sélectionnez la date et l'heure d'enregistrement du compteur.

6. Dans le champ **Valeur**, entrez le numéro depuis le dernier enregistrement du compteur. Sinon, dans le champ **Valeur associée**, entrez le total.

Notez les points suivants :

- Si vous installez physiquement un nouveau compteur sur un actif, vous devez enregistrer la modification sur l'actif sur la page **Compteurs d'actifs**. Ensuite, vous devez créer deux lignes d'enregistrement avec des horodatages identiques. La première ligne doit être pour le compteur que vous remplacez. Sur la ligne associée au nouveau compteur, activez la case à cocher **Réinitialiser le compteur**. Dans le champ **Totaux**, le total correspond à la somme des totaux du compteur de toutes les valeurs enregistrées dans ce compteur type.

- Si la case **Réinitialiser le compteur** est cochée sur un actif à l'aide d'un plan de maintenance avec un intervalle de type « Une fois à partir de… » ou « Une fois atteint… », le compteur est toujours actif sur la nouvelle ligne du compteur, car vous créez une ligne de compteur à part et commencez un nouveau compteur.

L'illustration suivante présente un exemple de la boîte de dialogue **Compteurs d'actif**.

![Figure 1](media/11-work-orders.png)

Sur la page **Compteurs d'actif** (**Gestion des actifs** > **Recherches** > **Actifs** > **Compteurs d'actif**), vous pouvez effectuer des enregistrements de compteur sur plusieurs actifs en même temps, comme vous le souhaitez.

>[!NOTE]
>Vous pouvez paramétrer une plage pour définir des écarts entre les enregistrements de compteur manuels. Vous pouvez également spécifier le type de message qui s'affiche si les enregistrements se situent en dehors de la plage définie. Pour plus d'informations sur la configuration des compteurs, voir [Compteurs](../setup-for-objects/counters.md).

