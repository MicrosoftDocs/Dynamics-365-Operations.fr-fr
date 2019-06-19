---
title: Paramétrer des scénarios de règlement de facture
description: Cette rubrique décrit la procédure de configuration de Dynamics 365 for Retail pour prendre en charge différents scénarios relatifs aux règlements de facture.
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b7132dc9b3c78fa04fcfc38ea72b5678ad08deb2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564968"
---
# <a name="set-up-pay-invoice-scenarios"></a><span data-ttu-id="e8cf0-103">Paramétrer des scénarios de règlement de facture</span><span class="sxs-lookup"><span data-stu-id="e8cf0-103">Set up pay invoice scenarios</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e8cf0-104">La fonctionnalité Payer la facture de Dynamics 365 for Retail a été développée pour prendre en charge ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e8cf0-104">The Pay invoice functionality in Dynamics 365 for Retail has been expanded to support:</span></span>

- <span data-ttu-id="e8cf0-105">Le règlement de plusieurs factures de commande client dans une transaction de point de vente unique.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-105">Payoff of multiple sales order invoices in a single POS transaction.</span></span>
- <span data-ttu-id="e8cf0-106">Le paiement de différents types de facture client, y compris des factures financières, des factures basées sur des projets et des avoirs.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-106">Payment of various customer invoice types including free text invoices, project-based invoices, and credit notes.</span></span>

<span data-ttu-id="e8cf0-107">Pour activer ces scénarios, le profil de fonctionnalité pour les magasins doit être configuré, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-107">To enable these scenarios, the functionality profile for stores must be configured as outlined in below.</span></span>

1. <span data-ttu-id="e8cf0-108">Accédez à **Vente au détail \> Paramétrage du canal \> Paramétrage Point de vente \> Profils Point de vente \> Profils de fonctionnalité** et sélectionnez un profil associé au magasin auquel vous souhaitez apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-108">Go to **Retail \> Channel setup \> POS setup \> POS profiles \> Functionality profiles** and select a profile that's linked to the stores that you want to make the changes for.</span></span>
2. <span data-ttu-id="e8cf0-109">Dans l'onglet **Fonctions**, configurez les paramètres suivants selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-109">On the **Functions** tab, configure the following parameters as needed.</span></span>

    - <span data-ttu-id="e8cf0-110">**Facture de commande client** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler une ou plusieurs factures basées sur une commande client dans une transaction de point de vente unique.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-110">**Sales order invoice** – Select **Yes** to allow users to pay one or more sales order-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="e8cf0-111">**Facture financière** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler une ou plusieurs factures financières dans une transaction de point de vente unique.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-111">**Free text invoice** – Select **Yes** to allow users to pay one or more free text-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="e8cf0-112">**Facture de projet** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler une ou plusieurs factures de projet dans une transaction de point de vente unique.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-112">**Project invoice** – Select **Yes** to allow users to pay one or more project-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="e8cf0-113">**Commande client - Avoir** : Sélectionnez **Oui** pour autoriser les utilisateurs à régler plusieurs avoirs basés sur des commandes dans le cadre des factures en cours ou pour rembourser un avoir en cours à un client.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-113">**Sales order credit note** – Select **Yes** to allow users to settle multiple sales order-based credit notes against open invoices or process a refund to the customer for an open credit note.</span></span>

> [!NOTE]
> <span data-ttu-id="e8cf0-114">Le paiement ou le règlement des montants partiels n'est pas encore pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e8cf0-114">Payment or settlement of partial amounts is not yet supported.</span></span>
