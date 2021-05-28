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
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a><span data-ttu-id="71c19-103">Les paiements sont automatiquement réglés avant que les commandes ne soient facturées ou expédiées</span><span class="sxs-lookup"><span data-stu-id="71c19-103">Payments are automatically settled before orders are invoiced or shipped</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="71c19-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un paiement est réglé dans le portail Adyen immédiatement lorsqu’une commande est passée, même si la commande client n’a pas été facturée ou expédiée.</span><span class="sxs-lookup"><span data-stu-id="71c19-104">This topic provides troubleshooting guidance that can help when a payment is settled in the Adyen portal immediately after an order is placed, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="description"></a><span data-ttu-id="71c19-105">Description</span><span class="sxs-lookup"><span data-stu-id="71c19-105">Description</span></span>

<span data-ttu-id="71c19-106">Une fois la commande passée, le paiement est immédiatement réglé sur le portail Adyen, même si la commande client n’a pas été facturée ni expédiée.</span><span class="sxs-lookup"><span data-stu-id="71c19-106">After an order is placed, the payment is immediately settled in the Adyen portal, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="resolution"></a><span data-ttu-id="71c19-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="71c19-107">Resolution</span></span>

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a><span data-ttu-id="71c19-108">Configurer la capture manuelle pour les paiements e-commerce dans le portail Adyen</span><span class="sxs-lookup"><span data-stu-id="71c19-108">Configure manual capture for e-commerce payments in the Adyen portal</span></span>

<span data-ttu-id="71c19-109">Pour configurer la capture manuelle pour les paiements e-commerce dans le portail Adyen, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="71c19-109">To configure manual capture for e-commerce payments in the Adyen portal, follow these steps.</span></span>

1. <span data-ttu-id="71c19-110">Connectez-vous au portail Adyen.</span><span class="sxs-lookup"><span data-stu-id="71c19-110">Sign in to the Adyen portal.</span></span>
1. <span data-ttu-id="71c19-111">Dans le coin supérieur droit, sélectionnez votre compte marchand pour le canal d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="71c19-111">In the upper-right corner, select your merchant account for the e-commerce channel.</span></span>
1. <span data-ttu-id="71c19-112">Dans la barre de navigation supérieure, sélectionnez **Compte**, puis **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="71c19-112">On the top navigation, select **Account**, and then select **Settings**.</span></span>
1. <span data-ttu-id="71c19-113">Dans le champ **Délai de capture**, sélectionnez **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="71c19-113">In the **Capture Delay** field, select **manual**.</span></span>

    ![Paramètre du délai de capture dans le portail Adyen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a><span data-ttu-id="71c19-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="71c19-115">Additional resources</span></span>

[<span data-ttu-id="71c19-116">Capture de paiement Adyen</span><span class="sxs-lookup"><span data-stu-id="71c19-116">Adyen payment capture</span></span>](https://docs.adyen.com/point-of-sale/capturing-payments)

[<span data-ttu-id="71c19-117">Connecteur de paiement Dynamics 365 pour Adyen</span><span class="sxs-lookup"><span data-stu-id="71c19-117">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="71c19-118">Configurer le connecteur de paiement Adyen pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="71c19-118">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
