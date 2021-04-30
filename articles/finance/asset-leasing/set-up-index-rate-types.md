---
title: Configurer les taux d’indexation
description: Cette rubrique explique comment paramétrer des taux d’indexation. Les taux d’indexation sont requis si votre organisation associe les montants des paiements de location à un ensemble de taux d’indexation.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 40f230a9d69a142b18eb27a2d5e420dbadc600d2
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880958"
---
# <a name="set-up-index-rates"></a>Configurer les taux d’indexation

[!include [banner](../includes/banner.md)]

Si les paiements de location dépendent d’un indice, les types de taux d’indexation peuvent être ajoutés et gérés dans le système. Pour réévaluer les paiements de location de la page **Type de taux d’indexation**, le processus de réévaluation du taux d’indexation utilise le taux d’indexation le plus récent à partir de la date de réévaluation.

Pour ajouter des types de taux d’indexation et des taux d’indexation, procédez comme suit.

1. Accédez à **Location d’actifs \> Configuration \> Types de taux d’indexation**.
2. Sélectionnez **Nouveau**.
3. Dans les champs appropriés, saisissez le type de taux et le nom du taux d’indexation.
4. Pour ajouter une nouvelle valeur de taux d’indexation, sélectionnez le type de taux d’indexation, puis sélectionnez **Ajouter**.
5. Sélectionnez la date de début effective du taux et sélectionnez la valeur du taux.

Vous devez sélectionner soit **Différence de valeur de taux d’indexation** ou **Valeur du taux d’indexation** comme méthode du taux d’indexation.

- Sélectionnez la méthode **Différence de valeur de taux d’indexation** pour calculer un nouveau paiement de location, sur la base de la différence entre le taux d’indexation à la date de début et le taux d’indexation le plus récent. Le taux d’indexation est défini dans le champ **Taux d’indexation (%)**.
- Sélectionnez la méthode **Valeur du taux d’indexation** pour calculer le paiement de location en utilisant le pourcentage spécifié dans le champ **Taux d’indexation (%)**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
