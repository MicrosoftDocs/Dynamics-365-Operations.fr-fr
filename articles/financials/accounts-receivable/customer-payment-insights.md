---
title: "Informations sur le paiement client (aperçu)"
description: "Cette rubrique décrit comment les informations sur le paiement client peuvent vous aider à prévoir quand une facture sera payées et permettre aux organisations de créer des stratégies d'optimisation pour améliorer la probabilité d'être payées à temps."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: 
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="customer-payment-insights-preview"></a><span data-ttu-id="dca07-103">Informations sur le paiement client (aperçu)</span><span class="sxs-lookup"><span data-stu-id="dca07-103">Customer payment insights (preview)</span></span>

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="dca07-104">Cette fonctionnalité fait partie d'une version ciblée et n'est disponible que pour les utilisateurs qui ont choisi l'aperçu privé.</span><span class="sxs-lookup"><span data-stu-id="dca07-104">This feature is part of a targeted release and is only available to users who have opted into the Private Preview.</span></span> <span data-ttu-id="dca07-105">Cette fonctionnalité sera incluse dans une prochaine version à disponibilité générale.</span><span class="sxs-lookup"><span data-stu-id="dca07-105">This feature will be included in an upcoming general availability release.</span></span>

# <a name="overview"></a><span data-ttu-id="dca07-106">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="dca07-106">Overview</span></span>

<span data-ttu-id="dca07-107">Les organisations trouvent souvent difficiles de prévoir quand un client paiera ses factures.</span><span class="sxs-lookup"><span data-stu-id="dca07-107">Organizations often find it challenging to predict when a customer will pay their invoices.</span></span> <span data-ttu-id="dca07-108">Ce manque d'informations peut entraîner des prévisions de flux de trésorerie inexactes, des processus de collecte inefficaces et la possibilité de commandes effectuées avec des clients susceptibles d'entraîner un risque de crédit.</span><span class="sxs-lookup"><span data-stu-id="dca07-108">This lack of insight can lead to inaccurate cash flow forecasts, inefficient collection processes, and the possibility of orders being released to customers who may pose a credit risk.</span></span> <span data-ttu-id="dca07-109">Les informations sur le paiement client (aperçu) utilisent le Machine Learning pour prévoir quand une facture sera payée.</span><span class="sxs-lookup"><span data-stu-id="dca07-109">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="dca07-110">Elle fournissent également des stratégies d'optimisation qui peuvent être personnalisées pour optimiser la probabilité que les clients paient à temps.</span><span class="sxs-lookup"><span data-stu-id="dca07-110">It also provides optimization strategies that can be tailored to maximize the probability of customers paying on time.</span></span>

## <a name="predictions"></a><span data-ttu-id="dca07-111">Prédictions</span><span class="sxs-lookup"><span data-stu-id="dca07-111">Predictions</span></span>

<span data-ttu-id="dca07-112">Les prédictions de paiement permettent aux organisations d'améliorer leurs processus d'entreprise en les aidant à :</span><span class="sxs-lookup"><span data-stu-id="dca07-112">Payment predictions allow organizations to improve their business processes by helping to:</span></span>

-   <span data-ttu-id="dca07-113">Identifier facilement les factures prévues pour être payées en retard.</span><span class="sxs-lookup"><span data-stu-id="dca07-113">Easily identify the invoices that are predicted to be paid late.</span></span>
-   <span data-ttu-id="dca07-114">Prendre des mesures appropriées pour améliorer les chances d'obtenir un paiement dans les temps.</span><span class="sxs-lookup"><span data-stu-id="dca07-114">Take appropriate measures to improve chances of getting paid on time.</span></span>

<span data-ttu-id="dca07-115">Les informations sur le paiement client (aperçu) utilisent le Machine Learning pour prévoir quand une facture sera payée.</span><span class="sxs-lookup"><span data-stu-id="dca07-115">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="dca07-116">Elles utilisent les données de facture, de paiement et de client historiques pour créer un modèle de Machine Learning utilisé pour prédire quand une facture sera payée.</span><span class="sxs-lookup"><span data-stu-id="dca07-116">It uses historical invoice, payment, and customer data to create a machine learning model that is used to predict when an invoice will be paid.</span></span>

<span data-ttu-id="dca07-117">Pour chaque facture en cours, les informations sur le paiement client (aperçu) prédit trois probabilités de paiement :</span><span class="sxs-lookup"><span data-stu-id="dca07-117">For each open invoice, Customer payment insights (preview) predicts three payment probabilities:</span></span>

-  <span data-ttu-id="dca07-118">Probabilité du paiement effectué dans les temps (avant la date d'échéance de la facture).</span><span class="sxs-lookup"><span data-stu-id="dca07-118">Probability of payment being made on time (within the invoice due date).</span></span>
-  <span data-ttu-id="dca07-119">Probabilité de paiement effectué au cours des 30 jours précédant la date d'échéance de la facture.</span><span class="sxs-lookup"><span data-stu-id="dca07-119">Probability of payment being made within 30 days of the invoice due date.</span></span>
-  <span data-ttu-id="dca07-120">Probabilité de paiement effectué au cours des 30 jours suivant la date d'échéance de la facture.</span><span class="sxs-lookup"><span data-stu-id="dca07-120">Probability of payment being made beyond 30 days of the invoice due date.</span></span>

<span data-ttu-id="dca07-121">La probabilité des paiements peut être affichée dans la section des prédictions.</span><span class="sxs-lookup"><span data-stu-id="dca07-121">The probability of payments can be viewed in the prediction section.</span></span>

<span data-ttu-id="dca07-122">[![Prédictions de paiement](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span><span class="sxs-lookup"><span data-stu-id="dca07-122">[![Payment predictions](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span></span>

<span data-ttu-id="dca07-123">Chaque facture reçoit également une probabilité d'obtention de paiement à l'aide de l'un des trois scénarios de probabilités de paiement prédits défini ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="dca07-123">Each invoice is also assigned a winning probability of payment using one of the three predicted payment probabilities scenarios defined above.</span></span> <span data-ttu-id="dca07-124">Le scénario avec la probabilité la plus élevé de paiement est le scénario d'obtention.</span><span class="sxs-lookup"><span data-stu-id="dca07-124">The scenario with the highest probability of payment is the winning scenario.</span></span>


<span data-ttu-id="dca07-125">Par exemple, prenons une facture la prévision indique une probabilité de 71 % que la facture soit payée dans les délais, une probabilité de 13 % que la facture soit payée au cours des 30 jours précédant la date d'échéance, et une probabilité de 16 % que la facture soit payée au delà des 30 jours précédant la date d'échéance.</span><span class="sxs-lookup"><span data-stu-id="dca07-125">For example, let’s assume for an invoice the prediction shows a 71 percent probability that the invoice will be paid on time, 13 percent probability that the invoice will be paid within 30 days of due date, and 16 percent probability that the invoice will be paid beyond 30 days of the due date.</span></span> <span data-ttu-id="dca07-126">La probabilité la plus élevée indique que la facture sera dans le scénario de paiement dans les délais, ce qui signifie que la facture sera marquée par la probabilité d'être payée à temps.</span><span class="sxs-lookup"><span data-stu-id="dca07-126">The highest probability shows that the invoice will be in the on-time scenario, so the invoice will be tagged with the probability of being paid on time.</span></span>

<span data-ttu-id="dca07-127">[![Prédictions de paiement](./media/payment-predict.png)](./media/payment-predict.png)</span><span class="sxs-lookup"><span data-stu-id="dca07-127">[![Payment predictions](./media/payment-predict.png)](./media/payment-predict.png)</span></span>

## <a name="optimization-strategies"></a><span data-ttu-id="dca07-128">Stratégies d'optimisation</span><span class="sxs-lookup"><span data-stu-id="dca07-128">Optimization strategies</span></span>

<span data-ttu-id="dca07-129">Outre les prévisions de paiement, les informations sur le paiement client (aperçu) peuvent utiliser des stratégies d'optimisation pour améliorer les chances d'obtention du paiement à temps.</span><span class="sxs-lookup"><span data-stu-id="dca07-129">In addition to payment predictions, the Customer Payment Insights (preview) can use optimization strategies to improve the chances of getting paid on time.</span></span> <span data-ttu-id="dca07-130">Cela permet aux organisations d'effectuer des analyses prévisionnelles permettant aux utilisateurs d'ajuster les paramètres de facture et client puis de comparer l'effet correspondant à la probabilité de recevoir le paiement des factures à temps.</span><span class="sxs-lookup"><span data-stu-id="dca07-130">This lets organizations do 'What if' analysis by allowing users to adjust invoice and customer parameters and then compare the corresponding effect on the probability of receiving payment on invoices on time.</span></span>

<span data-ttu-id="dca07-131">Par exemple, une organisation peut souhaiter évaluer l'effet de la mise à jour de l'escompte de règlement sur les factures en fonction de la probabilité de recevoir le paiement dans les délais.</span><span class="sxs-lookup"><span data-stu-id="dca07-131">For example, an organization may want to evaluate the effect of updating the cash discount on invoices on the probability of receiving the payment on time.</span></span> <span data-ttu-id="dca07-132">Lorsque les factures sont optimisées pour utiliser la nouvelle remise, les utilisateurs peuvent analyser l'effet de l'application de la remise à la probabilité de recevoir des paiements pour ces factures à temps.</span><span class="sxs-lookup"><span data-stu-id="dca07-132">When the invoices are optimized to use the new discount, the users can review the effect of applying the discount on the probability of receiving payments for those invoices on time.</span></span> <span data-ttu-id="dca07-133">Si le coût d'application de la remise est minimal une fois comparé à l'avantage de collecter le paiement dans les délais, l'organisation peut choisir d'appliquer la remise sélectionnée à toutes les futures commandes en cours.</span><span class="sxs-lookup"><span data-stu-id="dca07-133">If the cost of applying the discount is minimal when compared to the benefit of collecting the payment on time, the organization may choose to apply the selected discount to all future open orders.</span></span>

> [!NOTE] 
> <span data-ttu-id="dca07-134">Actuellement, seule la remise est disponible comme stratégie d'optimisation des analyses de paiement client (aperçu).</span><span class="sxs-lookup"><span data-stu-id="dca07-134">Currently, only discount is available as an optimization strategy for Customer payment insights (preview).</span></span>

<span data-ttu-id="dca07-135">[![Prédictions optimisées](./media/optimized-pay.png)](./media/optimized-pay.png)</span><span class="sxs-lookup"><span data-stu-id="dca07-135">[![Optimized predictions](./media/optimized-pay.png)](./media/optimized-pay.png)</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="dca07-136">Comment obtenir des informations sur le paiement client (aperçu)</span><span class="sxs-lookup"><span data-stu-id="dca07-136">How to get Customer payment insights (preview)</span></span>

<span data-ttu-id="dca07-137">Si vous souhaitez pour tester les informations sur le paiement client (aperçu), envoyez un message e-mail à [l'équipe d'aperçu des informations financières](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="dca07-137">If you are interested in trying Customer payment insights (preview), please email [Finance Insights Preview team](mailto:fiap@microsoft.com).</span></span> 

## <a name="privacy-statement"></a><span data-ttu-id="dca07-138">Déclaration de confidentialité</span><span class="sxs-lookup"><span data-stu-id="dca07-138">Privacy Statement</span></span>

<span data-ttu-id="dca07-139">Les aperçus stockent les données client aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="dca07-139">Previews store customer data in the United States.</span></span> <span data-ttu-id="dca07-140">En outre, les aperçus (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 for Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d'un support limité.</span><span class="sxs-lookup"><span data-stu-id="dca07-140">In addition, previews (1) may utilize less privacy and security measures than the Dynamics 365 for Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>

