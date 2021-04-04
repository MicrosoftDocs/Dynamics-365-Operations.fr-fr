---
title: Erreur de synchronisation des commandes liée au service de paiement par défaut
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider à corriger une erreur pouvant survenir lors de la synchronisation d’une commande en ligne.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: dd7c400f26b6fc7fbe1d4fec43a52295eb363333
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585315"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="92001-103">Erreur de synchronisation des commandes liée au service de paiement par défaut</span><span class="sxs-lookup"><span data-stu-id="92001-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="92001-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider à corriger une erreur pouvant survenir lors de la synchronisation d’une commande en ligne.</span><span class="sxs-lookup"><span data-stu-id="92001-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="92001-105">Description </span><span class="sxs-lookup"><span data-stu-id="92001-105">Description</span></span>

<span data-ttu-id="92001-106">Lorsque vous synchronisez une commande en ligne, le message d’erreur suivant s’affiche : « Un service de paiement par défaut est nécessaire pour traiter les transactions de carte de crédit ».</span><span class="sxs-lookup"><span data-stu-id="92001-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Erreur Service de paiement par défaut manquant](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="92001-108">Résolution</span><span class="sxs-lookup"><span data-stu-id="92001-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="92001-109">Confirmer ou définir le service de paiement par défaut dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="92001-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="92001-110">Pour confirmer ou définir le service de paiement par défaut dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="92001-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="92001-111">Accédez à **Comptabilité client \> Paramétrage des paiements \> Services de paiement**.</span><span class="sxs-lookup"><span data-stu-id="92001-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="92001-112">Assurez-vous que l’option **Processeur par défaut pour les nouvelles cartes de crédit** est définie sur **Oui** pour un service de paiement.</span><span class="sxs-lookup"><span data-stu-id="92001-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92001-113">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="92001-113">Additional resources</span></span>

[<span data-ttu-id="92001-114">Paramétrage, autorisation et capture de carte de crédit</span><span class="sxs-lookup"><span data-stu-id="92001-114">Credit card setup, authorization, and capture</span></span>](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
