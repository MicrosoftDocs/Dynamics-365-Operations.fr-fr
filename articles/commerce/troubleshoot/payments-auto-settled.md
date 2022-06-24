---
title: Les paiements sont automatiquement réglés avant que les commandes ne soient facturées ou expédiées
description: Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un paiement est réglé dans le portail Adyen immédiatement lorsqu’une commande est passée, même si la commande client n’a pas été facturée ou expédiée.
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
ms.openlocfilehash: c01a2fda54e198a43fa84ae83686fc1701958b6b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890267"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>Les paiements sont automatiquement réglés avant que les commandes ne soient facturées ou expédiées

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un paiement est réglé dans le portail Adyen immédiatement lorsqu’une commande est passée, même si la commande client n’a pas été facturée ou expédiée.

## <a name="description"></a>Description

Une fois la commande passée, le paiement est immédiatement réglé sur le portail Adyen, même si la commande client n’a pas été facturée ni expédiée.

## <a name="resolution"></a>Résolution

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Configurer la capture manuelle pour les paiements e-commerce dans le portail Adyen

Pour configurer la capture manuelle pour les paiements e-commerce dans le portail Adyen, procédez comme suit.

1. Connectez-vous au portail Adyen.
1. Dans le coin supérieur droit, sélectionnez votre compte marchand pour le canal d’e-commerce.
1. Dans la barre de navigation supérieure, sélectionnez **Compte**, puis **Paramètres**.
1. Dans le champ **Délai de capture**, sélectionnez **Manuel**.

    ![Paramètre du délai de capture dans le portail Adyen.](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>Ressources supplémentaires

[Capture de paiement Adyen](https://docs.adyen.com/point-of-sale/capturing-payments)

[Dynamics 365 Payment Connector pour Adyen](../dev-itpro/adyen-connector.md)

[Configurer le connecteur de paiement Adyen pour Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
