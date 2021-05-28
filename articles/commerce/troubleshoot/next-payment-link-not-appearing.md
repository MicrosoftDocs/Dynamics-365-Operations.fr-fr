---
title: L’option Enregistrer pour mon prochain paiement n’apparaît pas
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque la case à cocher Enregistrer pour mon prochain paiement n’apparaît pas sous Mode de paiement sur la page de paiement d’un site d’e-commerce.
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
ms.openlocfilehash: af19a3abd78d543d82f7a8d017e2dc413115a6d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018432"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>L’option « Enregistrer pour mon prochain paiement » n’apparaît pas

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque la case à cocher **Enregistrer pour mon prochain paiement** n’apparaît pas sous **Mode de paiement** sur la page de paiement d’un site d’e-commerce.

## <a name="description"></a>Description

La case à cocher **Enregistrer pour mon prochain paiement** n’apparaît pas dans la section **Mode de paiement** sur la page de paiement d’un site d’e-commerce.

L’illustration suivante montre un exemple de page de paiement qui inclut la case à cocher **Enregistrer pour mon prochain paiement**.

![Case à cocher Enregistrer pour mon prochain paiement dans le module Paiement](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Résolution

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Vérifiez que le connecteur de paiement Dynamics 365 pour Adyen est correctement configuré dans Commerce Headquarters

Pour vérifier que le connecteur de paiement Dynamics 365 pour Adyen est correctement configuré dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Canaux \> Magasins en ligne**.
1. Sélectionnez le magasin en ligne.
1. Sur le raccourci **Comptes de paiement**, assurez-vous que le champ **Autoriser l’enregistrement des informations de paiement dans l’e-commerce** est défini sur **True**.

![Autoriser l’enregistrement des informations de paiement dans le champ e-commerce dans Commerce Headquarters](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Paiement](../payment-module.md)

[Enregistrement des instruments de paiement en ligne avec le Connecteur Adyen](../dev-itpro/adyen-connector-listPI.md)
