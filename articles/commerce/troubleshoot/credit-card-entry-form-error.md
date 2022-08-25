---
title: La page de saisie de la carte de crédit affiche une erreur lors du paiement
description: Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque la section Mode de paiement n’est pas chargée et affiche un message d’erreur.
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
ms.openlocfilehash: 25f0dde83efff7c1d9a2a456270f5d48047f44ba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269753"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>La page de saisie de la carte de crédit affiche une erreur lors du paiement

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque la section **Mode de paiement** n’est pas chargée et affiche un message d’erreur.

## <a name="description"></a>Description

Lorsque vous ouvrez la page de paiement d’une boutique en ligne, la section **Mode de paiement** n’est pas chargée et le message d’erreur suivant s’affiche : « Une erreur s’est produite. Réessayez ultérieurement. »

![Erreur Module Paiement.](media/payment-module-error.jpg)

## <a name="resolution"></a>Résolution

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Attendez que le cache Commerce Scale Unit expire

Les paramètres du service de paiement sur la page de paiement de la boutique en ligne sont mis en cache sur Commerce Scale Unit et leur affichage sur le site d’e-commerce peut prendre jusqu’à 15 minutes. Ces paramètres de service de paiement incluent les modifications de l’ID du compte marchand, de la clé API cloud et de divers paramètres de configuration liés au mode de paiement.

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrer un canal en ligne](../channel-setup-online.md)
