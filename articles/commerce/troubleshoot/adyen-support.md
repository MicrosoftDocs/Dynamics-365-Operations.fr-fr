---
title: Résoudre les problèmes de connecteur de paiement Dynamics 365 pour Adyen
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent vous aider à obtenir de l’aide lorsque vous rencontrez des problèmes avec le connecteur de paiement Microsoft Dynamics 365 pour Adyen.
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
ms.openlocfilehash: f01db3fa670355696c094be544775a3abc557a70
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585314"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a><span data-ttu-id="224fc-103">Résoudre les problèmes de connecteur de paiement Dynamics 365 pour Adyen</span><span class="sxs-lookup"><span data-stu-id="224fc-103">Troubleshoot Dynamics 365 Payment Connector for Adyen issues</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="224fc-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent vous aider à obtenir de l’aide lorsque vous rencontrez des problèmes avec le connecteur de paiement Microsoft Dynamics 365 pour Adyen.</span><span class="sxs-lookup"><span data-stu-id="224fc-104">This topic provides troubleshooting guidance that can help you get support when you have issues with the Microsoft Dynamics 365 Payment Connector for Adyen.</span></span>

## <a name="description"></a><span data-ttu-id="224fc-105">Description </span><span class="sxs-lookup"><span data-stu-id="224fc-105">Description</span></span>

<span data-ttu-id="224fc-106">Vous rencontrez des problèmes avec le connecteur de paiement Dynamics 365 pour Adyen dans les domaines suivants et vous avez besoin de l’assistance de l’équipe Adyen :</span><span class="sxs-lookup"><span data-stu-id="224fc-106">You have issues with the Dynamics 365 Payment Connector for Adyen in the following areas, and you require support from the Adyen team:</span></span>

- <span data-ttu-id="224fc-107">Configuration du point de vente (PDV), du point de vente moderne (MPOS), du centre d’appels ou de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="224fc-107">Configuration of Point of sale (POS), Modern point of sale (MPOS), call center, or Dynamics 365 Commerce</span></span>
- <span data-ttu-id="224fc-108">Numéro de référence du fournisseur de services de paiement Adyen (par exemple, si vous avez des questions sur les refus, y compris les refus \[MKE\] de saisie manuelle avec les touches)</span><span class="sxs-lookup"><span data-stu-id="224fc-108">The Adyen payment service provider (PSP) reference number (for example, if you have questions about refusals, including manual key entry \[MKE\] refusals)</span></span>
- <span data-ttu-id="224fc-109">Tout ce qui ne fonctionne pas dans les environnements de test ou de prestataires en direct</span><span class="sxs-lookup"><span data-stu-id="224fc-109">Anything that isn't working in test or live merchant environments</span></span>

## <a name="resolution"></a><span data-ttu-id="224fc-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="224fc-110">Resolution</span></span>

<span data-ttu-id="224fc-111">Utilisez le modèle d’e-mail suivant pour démarrer le processus d’assistance avec l’équipe Adyen.</span><span class="sxs-lookup"><span data-stu-id="224fc-111">Use the following email template to start the support process with the Adyen team.</span></span> <span data-ttu-id="224fc-112">Pour accélérer la résolution des problèmes, assurez-vous que l’e-mail contient tous les détails requis.</span><span class="sxs-lookup"><span data-stu-id="224fc-112">To expedite troubleshooting, make sure that the email contains all the required details.</span></span>

| <span data-ttu-id="224fc-113">Champ</span><span class="sxs-lookup"><span data-stu-id="224fc-113">Field</span></span>        | <span data-ttu-id="224fc-114">Valeur </span><span class="sxs-lookup"><span data-stu-id="224fc-114">Value</span></span> |
|--------------|-------|
| <span data-ttu-id="224fc-115">Destination</span><span class="sxs-lookup"><span data-stu-id="224fc-115">To</span></span>           | `support@adyen.com` |
| <span data-ttu-id="224fc-116">Cc</span><span class="sxs-lookup"><span data-stu-id="224fc-116">Cc</span></span>           | |
| <span data-ttu-id="224fc-117">Ligne d'objet</span><span class="sxs-lookup"><span data-stu-id="224fc-117">Subject line</span></span> | <span data-ttu-id="224fc-118">Microsoft Dynamics Support Request</span><span class="sxs-lookup"><span data-stu-id="224fc-118">Microsoft Dynamics Support Request</span></span> |
| <span data-ttu-id="224fc-119">Corps</span><span class="sxs-lookup"><span data-stu-id="224fc-119">Body</span></span>         | <p><span data-ttu-id="224fc-120">Chers membres du support,</span><span class="sxs-lookup"><span data-stu-id="224fc-120">Hi Support,</span></span></p><p><span data-ttu-id="224fc-121">Merci de nous aider concernant le problème suivant :</span><span class="sxs-lookup"><span data-stu-id="224fc-121">Please provide support for the following issue:</span></span></p><ul><li><span data-ttu-id="224fc-122">Compte de marchand</span><span class="sxs-lookup"><span data-stu-id="224fc-122">Merchant account</span></span></li><li><span data-ttu-id="224fc-123">Environnement (Test/Prod)</span><span class="sxs-lookup"><span data-stu-id="224fc-123">Environment (Test/Prod)</span></span></li><li><span data-ttu-id="224fc-124">Canal (PDV/Centre d’appels/e-commerce Commerce)</span><span class="sxs-lookup"><span data-stu-id="224fc-124">Channel (POS/call center/Commerce e-commerce)</span></span></li><li><span data-ttu-id="224fc-125">Numéro de référence PSP, si le problème concernait une transaction spécifique (vous pouvez trouver le numéro de référence PSP sur le reçu, dans l’Espace client Adyen ou dans le menu des transactions du terminal de PDV.)</span><span class="sxs-lookup"><span data-stu-id="224fc-125">PSP reference number, if the issue involved a specific transaction (You can find the PSP reference number on the receipt, in the Adyen Customer Area, or on the transactions menu on the POS terminal.)</span></span></li><li><span data-ttu-id="224fc-126">Capture d’écran ou photo du message d’erreur, le cas échéant</span><span class="sxs-lookup"><span data-stu-id="224fc-126">Screenshot or photo of the error message, if applicable</span></span></li><li><span data-ttu-id="224fc-127">Journaux de l’Observateur d’événements (au format .txt)</span><span class="sxs-lookup"><span data-stu-id="224fc-127">Event Viewer logs (in .txt format)</span></span></li><li><span data-ttu-id="224fc-128">Description du problème et étapes de résolution des problèmes que vous avez essayées</span><span class="sxs-lookup"><span data-stu-id="224fc-128">Description of the issue and troubleshooting steps that you've tried</span></span></li></ul> |

## <a name="additional-resources"></a><span data-ttu-id="224fc-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="224fc-129">Additional resources</span></span>

[<span data-ttu-id="224fc-130">Accepter les paiements avec le connecteur Adyen pour Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="224fc-130">Accept payments with the Adyen connector for Dynamics 365 Commerce</span></span>](https://www.adyen.com/partners/dynamics-365-commerce)

[<span data-ttu-id="224fc-131">Connecteur de paiement Dynamics 365 pour Adyen</span><span class="sxs-lookup"><span data-stu-id="224fc-131">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="224fc-132">Configurer le connecteur de paiement Adyen pour Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="224fc-132">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
