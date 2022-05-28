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
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c6396b8c12520abb0e33cda713d5483f61610db4
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726520"
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
