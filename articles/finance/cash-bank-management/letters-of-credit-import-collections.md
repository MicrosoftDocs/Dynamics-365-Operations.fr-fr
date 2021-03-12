---
title: Lettres de crédit et relances d’importation
description: Cet article fournit des informations générales sur les lettres de crédit et des relances d’importation. Ces deux types de documents bancaires sont fréquemment utilisés pour l’achat et la vente de biens au-delà des frontières internationales.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLCImport
audience: Application User
ms.reviewer: roschlom
ms.custom: 18321
ms.assetid: 5c97ab81-632b-4043-a940-674bcb496c80
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad39951902395ebd2f78169f77e8d1a2e03a5762
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978837"
---
# <a name="letters-of-credit-and-import-collections"></a><span data-ttu-id="fe51d-104">Lettres de crédit et relances d’importation</span><span class="sxs-lookup"><span data-stu-id="fe51d-104">Letters of credit and import collections</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fe51d-105">Cet article fournit des informations générales sur les lettres de crédit et des relances d’importation.</span><span class="sxs-lookup"><span data-stu-id="fe51d-105">This article provides general information about letters of credit and import collections.</span></span> <span data-ttu-id="fe51d-106">Ces deux types de documents bancaires sont fréquemment utilisés pour l’achat et la vente de biens au-delà des frontières internationales.</span><span class="sxs-lookup"><span data-stu-id="fe51d-106">Both types of bank document are often used for the purchase and sale of goods across international borders.</span></span>

<a name="letters-of-credit"></a><span data-ttu-id="fe51d-107">Lettres de crédit</span><span class="sxs-lookup"><span data-stu-id="fe51d-107">Letters of credit</span></span>
-----------------

<span data-ttu-id="fe51d-108">Les lettres de crédit sont utilisées dans le cadre des transactions internationales pour garantir l’exécution des paiements.</span><span class="sxs-lookup"><span data-stu-id="fe51d-108">Letters of credit are used for international transactions and help guarantee that payments will be made.</span></span> <span data-ttu-id="fe51d-109">Une lettre de crédit est un accord émis par une banque, dans lequel la banque accepte de garantir le paiement au nom de l’acheteur, si les conditions de l’accord entre l’acheteur et le vendeur sont satisfaites.</span><span class="sxs-lookup"><span data-stu-id="fe51d-109">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to guarantee payment on behalf of a buyer, provided that the terms of the agreement between the buyer and seller are met.</span></span> <span data-ttu-id="fe51d-110">Une lettre de crédit est également appelée crédit documentaire.</span><span class="sxs-lookup"><span data-stu-id="fe51d-110">A letter of credit is also referred to as a documentary credit (DC).</span></span>

<span data-ttu-id="fe51d-111">Pour une lettre de crédit d’importation, l’entité juridique est l’acheteur ou le candidat de la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="fe51d-111">For an import letter of credit, the legal entity is the buyer or the applicant for the letter of credit.</span></span> <span data-ttu-id="fe51d-112">Pour une lettre de crédit d’exportation, l’entité juridique est le vendeur ou le bénéficiaire de la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="fe51d-112">For an export letter of credit, the legal entity is the seller or the beneficiary of the letter of credit.</span></span> <span data-ttu-id="fe51d-113">Les parties suivantes sont impliquées dans une lettre de crédit :</span><span class="sxs-lookup"><span data-stu-id="fe51d-113">The following parties are involved in a letter of credit:</span></span>

-   <span data-ttu-id="fe51d-114">demandeur (acheteur) ayant l’intention de payer les biens ;</span><span class="sxs-lookup"><span data-stu-id="fe51d-114">The applicant (buyer) who intends to pay for the goods</span></span>
-   <span data-ttu-id="fe51d-115">bénéficiaire (vendeur) qui reçoit le paiement ;</span><span class="sxs-lookup"><span data-stu-id="fe51d-115">The beneficiary (seller) who will receive the payment</span></span>
-   <span data-ttu-id="fe51d-116">banque émettrice qui émet la lettre de crédit ;</span><span class="sxs-lookup"><span data-stu-id="fe51d-116">The issuing bank that issues the letter of credit</span></span>
-   <span data-ttu-id="fe51d-117">banque conseillère qui effectue la transaction au nom du demandeur.</span><span class="sxs-lookup"><span data-stu-id="fe51d-117">The advising bank that carries out the transaction on behalf of the applicant</span></span>

<span data-ttu-id="fe51d-118">La lettre de crédit inclut une description des biens, les documents requis, la date d’expédition et la date d’expiration après laquelle le paiement ne sera pas effectué.</span><span class="sxs-lookup"><span data-stu-id="fe51d-118">The letter of credit includes a description of the goods, any required documents, the date of shipment, and the expiration date after which payment won't be made.</span></span> <span data-ttu-id="fe51d-119">La banque émettrice prélève une marge pour la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="fe51d-119">The issuing bank collects a margin for the letter of credit.</span></span> 

<span data-ttu-id="fe51d-120">Une lettre de crédit peut être **révocable** ou **irrévocable**.</span><span class="sxs-lookup"><span data-stu-id="fe51d-120">A letter of credit can be **revocable** or **irrevocable**.</span></span> <span data-ttu-id="fe51d-121">La nature d’une lettre de crédit peut être **transférable**, **non transférable** ou **revolving**.</span><span class="sxs-lookup"><span data-stu-id="fe51d-121">The nature of a letter of credit can be **transferable**, **non-transferable**, or **revolving**.</span></span> <span data-ttu-id="fe51d-122">En général, une lettre de crédit est un accord irrévocable et confirmé qui garantit l’exécution du paiement à un bénéficiaire spécifique suite à l’envoi d’une documentation d’expédition complète et précise.</span><span class="sxs-lookup"><span data-stu-id="fe51d-122">Typically, a letter of credit is an irrevocable and confirmed agreement that payment will be made to a specific beneficiary upon submission of complete and accurate shipping documentation.</span></span>

## <a name="import-collections"></a><span data-ttu-id="fe51d-123">Relances d’importation</span><span class="sxs-lookup"><span data-stu-id="fe51d-123">Import collections</span></span>
<span data-ttu-id="fe51d-124">Une relance d’importation est un accord entre la banque et l’exportateur (vendeur) dans lequel la banque accepte de transférer la documentation d’expédition à l’importateur international (acheteur).</span><span class="sxs-lookup"><span data-stu-id="fe51d-124">An import collection is an agreement between the bank and the exporter (seller), in which the bank agrees to deliver the shipping documentation to the international importer (buyer).</span></span> <span data-ttu-id="fe51d-125">La banque est supposée transmettre la documentation d’expédition dès réception du paiement pour les biens expédiés au comptant ou dès réception via d’une lettre de change signée pour le paiement.</span><span class="sxs-lookup"><span data-stu-id="fe51d-125">The bank is expected to deliver the shipping documentation upon receipt of payment for the shipped goods in cash, or upon receipt of a signed draft toward the payment.</span></span> 

<span data-ttu-id="fe51d-126">Une relance d’importation permet de garantir que le vendeur est payé lorsque l’acheteur récupère les documents d’expédition pour réceptionner la livraison des biens importés.</span><span class="sxs-lookup"><span data-stu-id="fe51d-126">An import collection helps guarantee that the seller is paid when the buyer collects the shipping documents to take delivery of the imported goods.</span></span>



