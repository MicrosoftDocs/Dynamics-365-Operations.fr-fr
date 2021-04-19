---
title: L’option Enregistrer pour mon prochain paiement n’apparaît pas
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque la case à cocher Enregistrer pour mon prochain paiement n’apparaît pas sous Mode de paiement sur la page de paiement d’un site d’e-commerce.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 7e3156d1aa9a05dc5d159b6f9b33ae341de640bf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801697"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a><span data-ttu-id="a8e45-103">L’option « Enregistrer pour mon prochain paiement » n’apparaît pas</span><span class="sxs-lookup"><span data-stu-id="a8e45-103">"Save for my next payment" option doesn't appear</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a8e45-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque la case à cocher **Enregistrer pour mon prochain paiement** n’apparaît pas sous **Mode de paiement** sur la page de paiement d’un site d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a8e45-104">This topic provides troubleshooting guidance that can help when the **Save for my next payment** check box doesn't appear under **Payment method** on an e-commerce site's checkout page.</span></span>

## <a name="description"></a><span data-ttu-id="a8e45-105">Description</span><span class="sxs-lookup"><span data-stu-id="a8e45-105">Description</span></span>

<span data-ttu-id="a8e45-106">La case à cocher **Enregistrer pour mon prochain paiement** n’apparaît pas dans la section **Mode de paiement** sur la page de paiement d’un site d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="a8e45-106">The **Save for my next payment** check box doesn't appear in the **Payment method** section on an e-commerce site's checkout page.</span></span>

<span data-ttu-id="a8e45-107">L’illustration suivante montre un exemple de page de paiement qui inclut la case à cocher **Enregistrer pour mon prochain paiement**.</span><span class="sxs-lookup"><span data-stu-id="a8e45-107">The following illustration shows an example of a checkout page that includes the **Save for my next payment** check box.</span></span>

![Case à cocher Enregistrer pour mon prochain paiement dans le module Paiement](media/payment-module-save-payment.jpg)

## <a name="resolution"></a><span data-ttu-id="a8e45-109">Résolution</span><span class="sxs-lookup"><span data-stu-id="a8e45-109">Resolution</span></span>

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a><span data-ttu-id="a8e45-110">Vérifiez que le connecteur de paiement Dynamics 365 pour Adyen est correctement configuré dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="a8e45-110">Verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters</span></span>

<span data-ttu-id="a8e45-111">Pour vérifier que le connecteur de paiement Dynamics 365 pour Adyen est correctement configuré dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a8e45-111">To verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a8e45-112">Accédez à **Commerce et vente au détail \> Canaux \> Magasins en ligne**.</span><span class="sxs-lookup"><span data-stu-id="a8e45-112">Go to **Retail and Commerce \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="a8e45-113">Sélectionnez le magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="a8e45-113">Select the online store.</span></span>
1. <span data-ttu-id="a8e45-114">Sur le raccourci **Comptes de paiement**, assurez-vous que le champ **Autoriser l’enregistrement des informations de paiement dans l’e-commerce** est défini sur **True**.</span><span class="sxs-lookup"><span data-stu-id="a8e45-114">On the **Payment accounts** FastTab, make sure that the **Allow saving payment information in e-commerce** field is set to **True**.</span></span>

![Autoriser l’enregistrement des informations de paiement dans le champ e-commerce dans Commerce Headquarters](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a><span data-ttu-id="a8e45-116">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a8e45-116">Additional resources</span></span>

[<span data-ttu-id="a8e45-117">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="a8e45-117">Payment module</span></span>](../payment-module.md)

[<span data-ttu-id="a8e45-118">Enregistrement des instruments de paiement en ligne avec le Connecteur Adyen</span><span class="sxs-lookup"><span data-stu-id="a8e45-118">Saving online payment instruments with the Adyen connector</span></span>](../dev-itpro/adyen-connector-listPI.md)
