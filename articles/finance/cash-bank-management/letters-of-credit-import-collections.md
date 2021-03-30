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
ms.openlocfilehash: 45eed711ace1534df462a21d0f37bdfaa09e6392
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253937"
---
# <a name="letters-of-credit-and-import-collections"></a><span data-ttu-id="081ef-104">Lettres de crédit et relances d’importation</span><span class="sxs-lookup"><span data-stu-id="081ef-104">Letters of credit and import collections</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="081ef-105">Cet article fournit des informations générales sur les lettres de crédit et des relances d’importation.</span><span class="sxs-lookup"><span data-stu-id="081ef-105">This article provides general information about letters of credit and import collections.</span></span> <span data-ttu-id="081ef-106">Ces deux types de documents bancaires sont fréquemment utilisés pour l’achat et la vente de biens au-delà des frontières internationales.</span><span class="sxs-lookup"><span data-stu-id="081ef-106">Both types of bank document are often used for the purchase and sale of goods across international borders.</span></span>

<a name="letters-of-credit"></a><span data-ttu-id="081ef-107">Lettres de crédit</span><span class="sxs-lookup"><span data-stu-id="081ef-107">Letters of credit</span></span>
-----------------

<span data-ttu-id="081ef-108">Les lettres de crédit sont utilisées dans le cadre des transactions internationales pour garantir l’exécution des paiements.</span><span class="sxs-lookup"><span data-stu-id="081ef-108">Letters of credit are used for international transactions and help guarantee that payments will be made.</span></span> <span data-ttu-id="081ef-109">Une lettre de crédit est un accord émis par une banque, dans lequel la banque accepte de garantir le paiement au nom de l’acheteur, si les conditions de l’accord entre l’acheteur et le vendeur sont satisfaites.</span><span class="sxs-lookup"><span data-stu-id="081ef-109">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to guarantee payment on behalf of a buyer, provided that the terms of the agreement between the buyer and seller are met.</span></span> <span data-ttu-id="081ef-110">Une lettre de crédit est également appelée crédit documentaire.</span><span class="sxs-lookup"><span data-stu-id="081ef-110">A letter of credit is also referred to as a documentary credit (DC).</span></span>

<span data-ttu-id="081ef-111">Pour une lettre de crédit d’importation, l’entité juridique est l’acheteur ou le candidat de la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="081ef-111">For an import letter of credit, the legal entity is the buyer or the applicant for the letter of credit.</span></span> <span data-ttu-id="081ef-112">Pour une lettre de crédit d’exportation, l’entité juridique est le vendeur ou le bénéficiaire de la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="081ef-112">For an export letter of credit, the legal entity is the seller or the beneficiary of the letter of credit.</span></span> <span data-ttu-id="081ef-113">Les parties suivantes sont impliquées dans une lettre de crédit :</span><span class="sxs-lookup"><span data-stu-id="081ef-113">The following parties are involved in a letter of credit:</span></span>

-   <span data-ttu-id="081ef-114">demandeur (acheteur) ayant l’intention de payer les biens ;</span><span class="sxs-lookup"><span data-stu-id="081ef-114">The applicant (buyer) who intends to pay for the goods</span></span>
-   <span data-ttu-id="081ef-115">bénéficiaire (vendeur) qui reçoit le paiement ;</span><span class="sxs-lookup"><span data-stu-id="081ef-115">The beneficiary (seller) who will receive the payment</span></span>
-   <span data-ttu-id="081ef-116">banque émettrice qui émet la lettre de crédit ;</span><span class="sxs-lookup"><span data-stu-id="081ef-116">The issuing bank that issues the letter of credit</span></span>
-   <span data-ttu-id="081ef-117">banque conseillère qui effectue la transaction au nom du demandeur.</span><span class="sxs-lookup"><span data-stu-id="081ef-117">The advising bank that carries out the transaction on behalf of the applicant</span></span>

<span data-ttu-id="081ef-118">La lettre de crédit inclut une description des biens, les documents requis, la date d’expédition et la date d’expiration après laquelle le paiement ne sera pas effectué.</span><span class="sxs-lookup"><span data-stu-id="081ef-118">The letter of credit includes a description of the goods, any required documents, the date of shipment, and the expiration date after which payment won't be made.</span></span> <span data-ttu-id="081ef-119">La banque émettrice prélève une marge pour la lettre de crédit.</span><span class="sxs-lookup"><span data-stu-id="081ef-119">The issuing bank collects a margin for the letter of credit.</span></span> 

<span data-ttu-id="081ef-120">Une lettre de crédit peut être **révocable** ou **irrévocable**.</span><span class="sxs-lookup"><span data-stu-id="081ef-120">A letter of credit can be **revocable** or **irrevocable**.</span></span> <span data-ttu-id="081ef-121">La nature d’une lettre de crédit peut être **transférable**, **non transférable** ou **revolving**.</span><span class="sxs-lookup"><span data-stu-id="081ef-121">The nature of a letter of credit can be **transferable**, **non-transferable**, or **revolving**.</span></span> <span data-ttu-id="081ef-122">En général, une lettre de crédit est un accord irrévocable et confirmé qui garantit l’exécution du paiement à un bénéficiaire spécifique suite à l’envoi d’une documentation d’expédition complète et précise.</span><span class="sxs-lookup"><span data-stu-id="081ef-122">Typically, a letter of credit is an irrevocable and confirmed agreement that payment will be made to a specific beneficiary upon submission of complete and accurate shipping documentation.</span></span>

## <a name="import-collections"></a><span data-ttu-id="081ef-123">Relances d’importation</span><span class="sxs-lookup"><span data-stu-id="081ef-123">Import collections</span></span>
<span data-ttu-id="081ef-124">Une relance d’importation est un accord entre la banque et l’exportateur (vendeur) dans lequel la banque accepte de transférer la documentation d’expédition à l’importateur international (acheteur).</span><span class="sxs-lookup"><span data-stu-id="081ef-124">An import collection is an agreement between the bank and the exporter (seller), in which the bank agrees to deliver the shipping documentation to the international importer (buyer).</span></span> <span data-ttu-id="081ef-125">La banque est supposée transmettre la documentation d’expédition dès réception du paiement pour les biens expédiés au comptant ou dès réception via d’une lettre de change signée pour le paiement.</span><span class="sxs-lookup"><span data-stu-id="081ef-125">The bank is expected to deliver the shipping documentation upon receipt of payment for the shipped goods in cash, or upon receipt of a signed draft toward the payment.</span></span> 

<span data-ttu-id="081ef-126">Une relance d’importation permet de garantir que le vendeur est payé lorsque l’acheteur récupère les documents d’expédition pour réceptionner la livraison des biens importés.</span><span class="sxs-lookup"><span data-stu-id="081ef-126">An import collection helps guarantee that the seller is paid when the buyer collects the shipping documents to take delivery of the imported goods.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]