---
title: L’option Enregistrer pour mon prochain paiement n’apparaît pas
description: Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque la case à cocher Enregistrer pour mon prochain paiement n’apparaît pas sous Mode de paiement sur la page de paiement d’un site e-commerce.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: d0b398a4ffc5fb698ea04ba8642d05ccd4caf04c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287482"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>L’option « Enregistrer pour mon prochain paiement » n’apparaît pas

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque la case à cocher **Enregistrer pour mon prochain paiement** n’apparaît pas sous **Mode de paiement** sur la page de paiement d’un site e-commerce.

## <a name="description"></a>Description

La case à cocher **Enregistrer pour mon prochain paiement** n’apparaît pas dans la section **Mode de paiement** sur la page de paiement d’un site e-commerce.

L’illustration suivante montre un exemple de page de paiement qui inclut la case à cocher **Enregistrer pour mon prochain paiement**.

![Case à cocher Enregistrer pour mon prochain paiement dans le module Paiement.](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Résolution

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Vérifiez que le connecteur de paiement Dynamics 365 pour Adyen est correctement configuré dans Commerce Headquarters

Pour vérifier que le connecteur de paiement Dynamics 365 pour Adyen est correctement configuré dans Commerce Headquarters, suivez ces étapes.

1. Accédez à **Commerce et vente au détail \> Canaux \> Magasins en ligne**.
1. Sélectionnez le magasin en ligne.
1. Sur le raccourci **Comptes de paiement**, assurez-vous que le champ **Autoriser l’enregistrement des informations de paiement dans e-commerce** est défini sur **Vraie**.

![Autoriser l’enregistrement des informations de paiement dans le champ e-commerce dans Commerce Headquarters.](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Paiement](../payment-module.md)

[Enregistrement des instruments de paiement en ligne avec le connecteur Adyen](../dev-itpro/adyen-connector-listPI.md)
