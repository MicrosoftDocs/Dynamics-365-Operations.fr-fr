---
title: Le remboursement d’un ordre de retour est refusé
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque le remboursement d’un ordre de retour est refusé car la carte de crédit utilisée pour la facturation diffère de la carte utilisée lors de l’autorisation de paiement d’origine.
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
ms.openlocfilehash: 99fd4b816b1a3a1fe3c2d1579be45b43fdc3d385
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020754"
---
# <a name="refund-on-a-return-order-is-declined"></a><span data-ttu-id="d4732-103">Le remboursement d’un ordre de retour est refusé</span><span class="sxs-lookup"><span data-stu-id="d4732-103">Refund on a return order is declined</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d4732-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque le remboursement d’un ordre de retour est refusé car la carte de crédit utilisée pour la facturation diffère de la carte utilisée lors de l’autorisation de paiement d’origine.</span><span class="sxs-lookup"><span data-stu-id="d4732-104">This topic provides troubleshooting guidance that can help when a refund on a return order is declined because the credit card that is used for invoicing differs from the card that was used during the original payment authorization.</span></span>

## <a name="description"></a><span data-ttu-id="d4732-105">Description</span><span class="sxs-lookup"><span data-stu-id="d4732-105">Description</span></span>

<span data-ttu-id="d4732-106">Un remboursement est refusé lorsque la carte de crédit utilisée pour facturer un ordre de retour diffère de la carte utilisée lors de l’autorisation de paiement d’origine.</span><span class="sxs-lookup"><span data-stu-id="d4732-106">A refund is declined when the credit card that is used to invoice a return order differs from the card that was used during the original payment authorization.</span></span> <span data-ttu-id="d4732-107">Le message d’erreur suivant s’affiche : « L’état de certains paiements n’est pas correct pour la validation.</span><span class="sxs-lookup"><span data-stu-id="d4732-107">You receive the following error message: "Some payments are not in the correct status for posting.</span></span> <span data-ttu-id="d4732-108">Veuillez valider à nouveau l’état de tous les paiements avant la facturation. »</span><span class="sxs-lookup"><span data-stu-id="d4732-108">Please re-validate the status of all payments prior to invoicing."</span></span>

<span data-ttu-id="d4732-109">Les détails de l’autorisation de paiement comprendront le message d’erreur suivant : « SendRequest() de la passerelle Adyen a échoué avec le statut ’InternalServerError’.22144 ; réponse vide renvoyée par Adyen. (22001); »</span><span class="sxs-lookup"><span data-stu-id="d4732-109">The payment authorization details will include the following error message: "Adyen gateway SendRequest() failed with status 'InternalServerError'.22144; Empty response returned from Adyen.(22001);"</span></span>

![Erreur de remboursement refusé pour un ordre de retour](media/refund-order-decline.jpg)

## <a name="resolution"></a><span data-ttu-id="d4732-111">Résolution</span><span class="sxs-lookup"><span data-stu-id="d4732-111">Resolution</span></span>

### <a name="enable-blind-returns-in-adyen"></a><span data-ttu-id="d4732-112">Activer les retours à l’aveugle dans Adyen</span><span class="sxs-lookup"><span data-stu-id="d4732-112">Enable blind returns in Adyen</span></span>

<span data-ttu-id="d4732-113">Pour activer les retours à l’aveugle, suivez les étapes de [Résoudre les problèmes de connecteur de paiement Dynamics 365 pour Adyen](adyen-support.md) pour contacter l’équipe du support technique et demander que les retours à l’aveugle soient activés sur votre compte marchand Adyen.</span><span class="sxs-lookup"><span data-stu-id="d4732-113">To enable blind returns, follow the steps in [Troubleshoot Dynamics 365 Payment Connector for Adyen issues](adyen-support.md) to contact the Adyen support team and request that blind returns be enabled on your Adyen merchant account.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d4732-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d4732-114">Additional resources</span></span>

[<span data-ttu-id="d4732-115">Connecteur de paiement Dynamics 365 pour Adyen</span><span class="sxs-lookup"><span data-stu-id="d4732-115">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="d4732-116">Configurer le connecteur de paiement Adyen pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d4732-116">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
