---
title: Erreur Le type de paiement doit être une carte de crédit sur la page de commande client
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un message d’erreur s’affiche sur la page de commande client après la synchronisation d’une commande.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 20f18507dee330fd1affedeee092b3dfa7cc10bc
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585322"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>Erreur « Le type de paiement doit être une carte de crédit » sur la page de commande client

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un message d’erreur s’affiche sur la page de commande client après la synchronisation d’une commande.

## <a name="description"></a>Description 

Lorsque vous ouvrez la page de commande client après avoir synchronisé une commande, le message d’erreur suivant s’affiche : « Le type de paiement doit être une carte de crédit, car le numéro de carte de crédit a été spécifié ».

![Erreur Le type de paiement doit être une carte de crédit](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Résolution

### <a name="set-the-payment-type-in-commerce-headquarters"></a>Définir le type de paiement dans Commerce Headquarters

1. Accédez à **Comptabilité client \> Paramétrage des paiements \> Conditions de paiement**.
1. Dans le volet de navigation de gauche, sélectionnez vos conditions de paiement.
1. Dans le champ **Type de paiement**, assurez-vous que **Carte de crédit** est sélectionné.

## <a name="additional-resources"></a>Ressources supplémentaires

[Validation des ventes et des paiements en ligne](../tasks/posting-online-sales-payments.md)
