---
title: Le remboursement d’un ordre de retour est refusé
description: Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque le remboursement d’un ordre de retour est refusé car la carte de crédit utilisée pour la facturation diffère de la carte utilisée lors de l’autorisation de paiement d’origine.
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
ms.openlocfilehash: d8d1c40673d4b159a7b7bf00bf6011ba45f47edd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268230"
---
# <a name="refund-on-a-return-order-is-declined"></a>Le remboursement d’un ordre de retour est refusé

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque le remboursement d’un ordre de retour est refusé car la carte de crédit utilisée pour la facturation diffère de la carte utilisée lors de l’autorisation de paiement d’origine.

## <a name="description"></a>Description

Un remboursement est refusé lorsque la carte de crédit utilisée pour facturer un ordre de retour diffère de la carte utilisée lors de l’autorisation de paiement d’origine. Le message d’erreur suivant s’affiche : « L’état de certains paiements n’est pas correct pour la validation. Veuillez valider à nouveau l’état de tous les paiements avant la facturation. »

Les détails de l’autorisation de paiement comprendront le message d’erreur suivant : « SendRequest() de la passerelle Adyen a échoué avec le statut ’InternalServerError’.22144 ; réponse vide renvoyée par Adyen. (22001); »

![Erreur de remboursement refusé pour un ordre de retour.](media/refund-order-decline.jpg)

## <a name="resolution"></a>Résolution

### <a name="enable-blind-returns-in-adyen"></a>Activer les retours à l’aveugle dans Adyen

Pour activer les retours à l’aveugle, suivez les étapes de [Résoudre les problèmes de connecteur de paiement Dynamics 365 pour Adyen](adyen-support.md) pour contacter l’équipe du support technique et demander que les retours à l’aveugle soient activés sur votre compte marchand Adyen.

## <a name="additional-resources"></a>Ressources supplémentaires

[Connecteur de paiement Dynamics 365 pour Adyen](../dev-itpro/adyen-connector.md)

[Configurer le connecteur de paiement Adyen pour Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
