---
title: "Paramétrer des scénarios de règlement de facture"
description: "Cette rubrique décrit la procédure de configuration de Dynamics 365 for Retail pour prendre en charge différents scénarios relatifs aux règlements de facture."
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 3331b984693c58c6ee8c49b98ed7d3a8df5b79ff
ms.openlocfilehash: 53c4b9a9c9dac1add7021d909b2c8900d11e5c0c
ms.contentlocale: fr-fr
ms.lasthandoff: 12/04/2018

---
# <a name="set-up-pay-invoice-scenarios"></a><span data-ttu-id="e57de-103">Paramétrer des scénarios de règlement de facture</span><span class="sxs-lookup"><span data-stu-id="e57de-103">Set up pay invoice scenarios</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e57de-104">La fonctionnalité Payer la facture de Dynamics 365 for Retail a été développée pour prendre en charge ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e57de-104">The Pay invoice functionality in Dynamics 365 for Retail has been expanded to support:</span></span>
- <span data-ttu-id="e57de-105">Le règlement de plusieurs factures de commande client dans une transaction de point de vente unique.</span><span class="sxs-lookup"><span data-stu-id="e57de-105">Payoff of multiple sales order invoices in a single POS transaction.</span></span>
- <span data-ttu-id="e57de-106">Le paiement de différents types de facture client, y compris des factures financières, des factures basées sur des projets et des avoirs.</span><span class="sxs-lookup"><span data-stu-id="e57de-106">Payment of various customer invoice types including free text invoices, project-based invoices, and credit notes.</span></span>

<span data-ttu-id="e57de-107">Pour activer ces scénarios, le profil de fonctionnalité pour les magasins doit être configuré, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e57de-107">To enable these scenarios, the functionality profile for stores must be configured as outlined in below.</span></span>  

1. <span data-ttu-id="e57de-108">Accédez à **Vente au détail > Paramétrage du canal > Paramétrage Point de vente > Profils Point de vente > Profils de fonctionnalité** et sélectionnez un profil associé au magasin auquel vous souhaitez apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="e57de-108">Go to **Retail > Channel setup > POS setup > POS profiles > Functionality profiles** and select a profile that's linked to the stores that you want to make the changes for.</span></span>

1. <span data-ttu-id="e57de-109">Dans l'onglet **Fonctions**, configurez les paramètres suivants selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="e57de-109">On the **Functions** tab, configure the following parameters as needed.</span></span>

    - <span data-ttu-id="e57de-110">**Facture de commande client** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler une ou plusieurs factures basées sur une commande client dans une transaction de point de vente unique.</span><span class="sxs-lookup"><span data-stu-id="e57de-110">**Sales order invoice** - Select **Yes** to allow users to pay one or more sales order-based invoices in a single POS transaction.</span></span>

    - <span data-ttu-id="e57de-111">**Facture financière** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler une ou plusieurs factures financières dans une transaction de point de vente unique.</span><span class="sxs-lookup"><span data-stu-id="e57de-111">**Free text invoice** - Select **Yes** to allow users to pay one or more free text-based invoices in a single POS transaction.</span></span>

    - <span data-ttu-id="e57de-112">**Facture de projet** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler une ou plusieurs factures de projet dans une transaction de point de vente unique.</span><span class="sxs-lookup"><span data-stu-id="e57de-112">**Project invoice** - Select **Yes** to allow users to pay one or more project-based invoices in a single POS transaction.</span></span>

    - <span data-ttu-id="e57de-113">**Commande client - Avoir** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler plusieurs avoirs basés sur des commandes dans le cadre des factures en cours ou pour rembourser un avoir en cours à un client.</span><span class="sxs-lookup"><span data-stu-id="e57de-113">**Sales order credit note** - Select **Yes** to allow users to settle multiple sales order-based credit notes against open invoices or process a refund to the customer for an open credit note.</span></span>

> [!NOTE]
> <span data-ttu-id="e57de-114">Le paiement ou le règlement des montants partiels n'est pas encore pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e57de-114">Payment or settlement of partial amounts is not yet supported.</span></span>

