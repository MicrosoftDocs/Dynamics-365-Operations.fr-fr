---
title: La page de saisie de la carte de crédit affiche une erreur lors du paiement
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque la section Mode de paiement n’est pas chargée et affiche un message d’erreur.
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
ms.openlocfilehash: ea9105481e6c5812565f0d3604906c905bcb5443
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018504"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a><span data-ttu-id="e89b4-103">La page de saisie de la carte de crédit affiche une erreur lors du paiement</span><span class="sxs-lookup"><span data-stu-id="e89b4-103">Credit card entry page shows an error at checkout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e89b4-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque la section **Mode de paiement** n’est pas chargée et affiche un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e89b4-104">This topic provides troubleshooting guidance that can help when the **Payment method** section isn't loaded and shows an error message.</span></span>

## <a name="description"></a><span data-ttu-id="e89b4-105">Description</span><span class="sxs-lookup"><span data-stu-id="e89b4-105">Description</span></span>

<span data-ttu-id="e89b4-106">Lorsque vous ouvrez la page de paiement d’une boutique en ligne, la section **Mode de paiement** n’est pas chargée et le message d’erreur suivant s’affiche : « Une erreur s’est produite.</span><span class="sxs-lookup"><span data-stu-id="e89b4-106">When you open the checkout page of an online store, the **Payment method** section isn't loaded, and the following error message is shown: "Something went wrong.</span></span> <span data-ttu-id="e89b4-107">Réessayez ultérieurement. »</span><span class="sxs-lookup"><span data-stu-id="e89b4-107">Please try again later."</span></span>

![Erreur Module Paiement](media/payment-module-error.jpg)

## <a name="resolution"></a><span data-ttu-id="e89b4-109">Résolution</span><span class="sxs-lookup"><span data-stu-id="e89b4-109">Resolution</span></span>

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a><span data-ttu-id="e89b4-110">Attendez que le cache Commerce Scale Unit expire</span><span class="sxs-lookup"><span data-stu-id="e89b4-110">Wait for the Commerce Scale Unit cache to expire</span></span>

<span data-ttu-id="e89b4-111">Les paramètres du service de paiement sur la page de paiement de la boutique en ligne sont mis en cache sur Commerce Scale Unit et leur affichage sur le site d’e-commerce peut prendre jusqu’à 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="e89b4-111">The payment service settings on the online store's checkout page are cached on the Commerce Scale Unit and can take up to 15 minutes to appear on the e-commerce site.</span></span> <span data-ttu-id="e89b4-112">Ces paramètres de service de paiement incluent les modifications de l’ID du compte marchand, de la clé API cloud et de divers paramètres de configuration liés au mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="e89b4-112">These payment service settings include changes to the merchant account ID, cloud API key, and various configuration settings that are related to the payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e89b4-113">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e89b4-113">Additional resources</span></span>

[<span data-ttu-id="e89b4-114">Paramétrer un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="e89b4-114">Set up an online channel</span></span>](../channel-setup-online.md)
