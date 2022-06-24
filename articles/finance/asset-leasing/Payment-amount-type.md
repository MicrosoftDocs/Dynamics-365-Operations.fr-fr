---
title: Ajouter des types de montant de paiement
description: Cet article explique comment configurer les types de montant de paiement dans la location d’actifs.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 03fc903e6cfe78ef2fed7e3a0744a8f809f6892d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891607"
---
# <a name="add-payment-amount-types"></a>Ajouter des types de montant de paiement

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer les types de montant de paiement dans la location d’actifs. De cette façon, vous pouvez détailler le montant du paiement de location au lieu d’ajouter le montant forfaitaire sur les lignes de l’échéancier de paiement.

Pour ajouter des types de montant de paiement, procédez comme suit.

1. Accédez à **Location d’actifs \> Configuration \> Types de montant de paiement**.
2. Cliquez sur **Nouveau**.
3. Entrez le nouveau type de paiement et une description.

> [!NOTE]
> Pour la réévaluation de l’indice IFRS 16, vous devez créer un type de montant de paiement et le marquer comme **Utilisé pour la réévaluation de l’indice IRFS 16**. Ce type de montant de paiement sera utilisé lorsque le processus de réévaluation de l’indice sera exécuté par rapport au registre IFRS 16, et il prendra en compte les changements qui se sont produits en raison du processus de réévaluation de l’indice.
>
> Quand l’option **Répartition du paiement** dans le bail est définie sur **Oui**, si la réévaluation de l’indice IFRS 16 est exécutée, mais qu’il n’y a pas de type de paiement pour IFRS 16, le processus n’aboutira pas.

Un seul enregistrement peut être marqué comme **Utilisé pour la réévaluation de l’indice IFRS 16**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
