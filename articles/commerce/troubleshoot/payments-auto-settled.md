---
title: Les paiements sont automatiquement réglés avant que les commandes ne soient facturées ou expédiées
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un paiement est réglé dans le portail Adyen immédiatement lorsqu’une commande est passée, même si la commande client n’a pas été facturée ou expédiée.
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
ms.openlocfilehash: b4fd37a3c45f2559c9659f072ca0b6f02e712f53
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018258"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>Les paiements sont automatiquement réglés avant que les commandes ne soient facturées ou expédiées

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un paiement est réglé dans le portail Adyen immédiatement lorsqu’une commande est passée, même si la commande client n’a pas été facturée ou expédiée.

## <a name="description"></a>Description

Une fois la commande passée, le paiement est immédiatement réglé sur le portail Adyen, même si la commande client n’a pas été facturée ni expédiée.

## <a name="resolution"></a>Résolution

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Configurer la capture manuelle pour les paiements e-commerce dans le portail Adyen

Pour configurer la capture manuelle pour les paiements e-commerce dans le portail Adyen, procédez comme suit.

1. Connectez-vous au portail Adyen.
1. Dans le coin supérieur droit, sélectionnez votre compte marchand pour le canal d’e-commerce.
1. Dans la barre de navigation supérieure, sélectionnez **Compte**, puis **Paramètres**.
1. Dans le champ **Délai de capture**, sélectionnez **Manuel**.

    ![Paramètre du délai de capture dans le portail Adyen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>Ressources supplémentaires

[Capture de paiement Adyen](https://docs.adyen.com/point-of-sale/capturing-payments)

[Connecteur de paiement Dynamics 365 pour Adyen](../dev-itpro/adyen-connector.md)

[Configurer le connecteur de paiement Adyen pour Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
