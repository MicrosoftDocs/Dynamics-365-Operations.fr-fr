---
title: Conventions de location d’actifs
description: Cet article décrit les conventions d’actifs loués.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f2f0e21b20a969c0847ce3a6eb167287c1d7ee3e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898267"
---
# <a name="asset-leasing-conventions"></a>Conventions de location d’actifs

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article décrit les conventions d’actifs loués. Les conventions de location sont utilisées pour déterminer la date de début d’un registre des baux. Si la convention de location est définie sur **Aucun**, la date de début est la même que la date de début du bail (c’est-à-dire la valeur du champ **Date de début du bail**). Si la convention de location est définie sur **Mois complet**, la date de début est le premier jour du mois où tombe la date de début du bail.

La date de début détermine la date de début de la période pour les plans d’amortissement du passif et des actifs. Les charges d’intérêts et les charges d’amortissement sont comptabilisées à la date de fin de la période des plans correspondants. La comptabilisation initiale et l’écriture dans le journal d’ajustement sont enregistrées à la date de début.

> [!NOTE]
> La fonctionnalité pour les conventions de location doit être activée via la gestion des fonctionnalités. Dans l’espace de travail **Gestion des fonctionnalités**, recherchez et sélectionnez la fonction intitulée **Convention de location pour la location d’actifs**, puis sélectionnez **Activer maintenant**.

Les conventions de location sont affectées à la configuration d’un registre d’actifs de location.

Pour afficher ou attribuer la convention de location, procédez comme suit.

1. Accédez à **Location d’actifs \> Configuration \> registres de baux**.
2. Dans le champ **Convention de location**, sélectionnez l’une des valeurs suivantes.

    | Convention de leasing | Description |
    |--------------------|-------------|
    | None               | Les plans d’amortissement du passif et des actifs commencent à la date de début du contrat de location, car la date de début correspond à la date de début du contrat de location. La date de fin est un mois plus tard. Cette convention de location ne garantit pas la comptabilisation des intérêts le dernier jour de chaque mois. |
    | Mois complet         | Pour les contrats de location dont la date de début survient à n’importe quel moment du mois, les calendriers d’amortissement du passif et des actifs commencent à accumuler des charges le premier jour de ce mois. Cette convention de location garantit que les intérêts courent le dernier jour de chaque mois pendant tout le mois. |

3. Sélectionnez **Enregistrer**.

Lorsqu’un contrat de location est créé, la date de début de chaque registre est automatiquement saisie en fonction de la date de début qui est entrée pour le contrat de location et de la convention de location spécifiée pour le registre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
