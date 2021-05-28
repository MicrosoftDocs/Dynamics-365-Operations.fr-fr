---
title: Erreur Le type de paiement doit être une carte de crédit sur la page de commande client
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un message d’erreur s’affiche sur la page de commande client après la synchronisation d’une commande.
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
ms.openlocfilehash: 5be19949e9d1dbc43fdd3e6def119effa50a34d0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018408"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a><span data-ttu-id="f9339-103">Erreur « Le type de paiement doit être une carte de crédit » sur la page de commande client</span><span class="sxs-lookup"><span data-stu-id="f9339-103">"Payment type must be credit card" error on the sales order page</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f9339-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un message d’erreur s’affiche sur la page de commande client après la synchronisation d’une commande.</span><span class="sxs-lookup"><span data-stu-id="f9339-104">This topic provides troubleshooting guidance that can help when an error message is shown on the sales order page after an order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="f9339-105">Description</span><span class="sxs-lookup"><span data-stu-id="f9339-105">Description</span></span>

<span data-ttu-id="f9339-106">Lorsque vous ouvrez la page de commande client après avoir synchronisé une commande, le message d’erreur suivant s’affiche : « Le type de paiement doit être une carte de crédit, car le numéro de carte de crédit a été spécifié ».</span><span class="sxs-lookup"><span data-stu-id="f9339-106">When you open the sales order page after you sync an order, you receive the following error message: "The payment type must be credit card, since the credit card number has been specified."</span></span>

![Erreur Le type de paiement doit être une carte de crédit](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a><span data-ttu-id="f9339-108">Résolution</span><span class="sxs-lookup"><span data-stu-id="f9339-108">Resolution</span></span>

### <a name="set-the-payment-type-in-commerce-headquarters"></a><span data-ttu-id="f9339-109">Définir le type de paiement dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="f9339-109">Set the payment type in Commerce headquarters</span></span>

1. <span data-ttu-id="f9339-110">Accédez à **Comptabilité client \> Paramétrage des paiements \> Conditions de paiement**.</span><span class="sxs-lookup"><span data-stu-id="f9339-110">Go to **Accounts receivable \> Payment setup \> Terms of payment**.</span></span>
1. <span data-ttu-id="f9339-111">Dans le volet de navigation de gauche, sélectionnez vos conditions de paiement.</span><span class="sxs-lookup"><span data-stu-id="f9339-111">In the left navigation, select your terms of payment.</span></span>
1. <span data-ttu-id="f9339-112">Dans le champ **Type de paiement**, assurez-vous que **Carte de crédit** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f9339-112">In the **Payment type** field, make sure that **Credit card** is selected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f9339-113">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f9339-113">Additional resources</span></span>

[<span data-ttu-id="f9339-114">Validation des ventes et des paiements en ligne</span><span class="sxs-lookup"><span data-stu-id="f9339-114">Posting of online sales and payments</span></span>](../tasks/posting-online-sales-payments.md)
