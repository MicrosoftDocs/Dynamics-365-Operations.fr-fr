---
title: Erreur de synchronisation des commandes liée au service de paiement par défaut
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider à corriger une erreur pouvant survenir lors de la synchronisation d’une commande en ligne.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 6f8e0ea7675ffc5cbada36207422b410234e33afcaec90636e90e573a90ac484
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715234"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Erreur de synchronisation des commandes liée au service de paiement par défaut

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider à corriger une erreur pouvant survenir lors de la synchronisation d’une commande en ligne.

## <a name="description"></a>Description

Lorsque vous synchronisez une commande en ligne, le message d’erreur suivant s’affiche : « Un service de paiement par défaut est nécessaire pour traiter les transactions de carte de crédit ».

![Erreur Service de paiement par défaut manquant.](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Résolution

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Confirmer ou définir le service de paiement par défaut dans Commerce Headquarters

Pour confirmer ou définir le service de paiement par défaut dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Comptabilité client \> Paramétrage des paiements \> Services de paiement**.
1. Assurez-vous que l’option **Processeur par défaut pour les nouvelles cartes de crédit** est définie sur **Oui** pour un service de paiement.

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrage, autorisation et capture de carte de crédit](../../finance/accounts-receivable/credit-card-authorizations.md)