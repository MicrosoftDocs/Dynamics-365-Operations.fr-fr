---
title: Confirmer les échéanciers de paiement par lots de la location d’actifs
description: Cette rubrique explique comment confirmer plusieurs échéanciers de paiement par lot.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9c680ea16e9f64107fde081c7e7763697356dcc1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971376"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a><span data-ttu-id="abea9-103">Confirmer les échéanciers de paiement par lots de la location d’actifs</span><span class="sxs-lookup"><span data-stu-id="abea9-103">Confirm Asset leasing payment schedules in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="abea9-104">Cette rubrique explique comment confirmer plusieurs échéanciers de paiement par lot.</span><span class="sxs-lookup"><span data-stu-id="abea9-104">This topic explains how to confirm multiple payment schedules in a batch.</span></span> <span data-ttu-id="abea9-105">Les échéanciers de paiement sont confirmés sur une base de location-à-location, soit par le biais du processus de confirmation par lot.</span><span class="sxs-lookup"><span data-stu-id="abea9-105">Payment schedules are confirmed either on a lease-to-lease basis or through the confirmation batch process.</span></span> <span data-ttu-id="abea9-106">Une écriture de journal ne peut être validée que pour une location dont l’échéancier de paiement est confirmé.</span><span class="sxs-lookup"><span data-stu-id="abea9-106">A journal entry can be posted only against a lease that has a confirmed payment schedule.</span></span> <span data-ttu-id="abea9-107">La confirmation de l’échéancier de paiement sert d’approbation finale des informations financières de la location.</span><span class="sxs-lookup"><span data-stu-id="abea9-107">Confirmation of the payment schedule serves as a final approval of the financial information for the lease.</span></span> <span data-ttu-id="abea9-108">Toutes les modifications futures des informations financières relatives à la location, telles que les paiements et la durée du bail, constituent un ajustement de la location et doivent être traitées de cette manière.</span><span class="sxs-lookup"><span data-stu-id="abea9-108">All future changes to the financial information for the lease, such as payments and the lease term, constitute a lease adjustment and should be processed in that way.</span></span>

<span data-ttu-id="abea9-109">Pour confirmer plusieurs échéanciers de paiement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="abea9-109">To confirm multiple payment schedules, follow these steps.</span></span>

1. <span data-ttu-id="abea9-110">Aller à **Location d’actifs \> Périodique \> Confirmation par lot**.</span><span class="sxs-lookup"><span data-stu-id="abea9-110">Go to **Asset leasing \> Periodic \> Confirmation batch**.</span></span>
2. <span data-ttu-id="abea9-111">Sur la page **Confirmation par lot**, sélectionnez **Confirmation par lot**.</span><span class="sxs-lookup"><span data-stu-id="abea9-111">On the **Confirmation batch** page, select **Confirmation batch**.</span></span>
3. <span data-ttu-id="abea9-112">Dans la boîte de dialogue qui s’affiche, filtrez les registres que vous souhaitez confirmer.</span><span class="sxs-lookup"><span data-stu-id="abea9-112">In the dialog box that appears, filter for the books that you want to confirm.</span></span>

    - <span data-ttu-id="abea9-113">Pour confirmer tous les registres d’un groupe de location spécifique, sélectionnez le groupe dans le champ **Groupe de location**.</span><span class="sxs-lookup"><span data-stu-id="abea9-113">To confirm all the books in a specific lease group, select the group in the **Lease group** field.</span></span>
    - <span data-ttu-id="abea9-114">Pour confirmer des registres spécifiques, sélectionnez les registres dans le champ **ID de registre**.</span><span class="sxs-lookup"><span data-stu-id="abea9-114">To confirm specific books, select the books in the **Book ID** field.</span></span>
    - <span data-ttu-id="abea9-115">Pour confirmer tous les registres, activez le paramètre **Pour tous les registres**.</span><span class="sxs-lookup"><span data-stu-id="abea9-115">To confirm all books, turn on the **For all books** parameter.</span></span>

<span data-ttu-id="abea9-116">Les informations relatives aux registres nouvellement confirmés sont affichées sur la page **Registres confirmés**.</span><span class="sxs-lookup"><span data-stu-id="abea9-116">Information for the newly confirmed books is shown on the **Confirmed books** page.</span></span> <span data-ttu-id="abea9-117">Une fois les échéanciers de paiement confirmés, les écritures de journal de reconnaissance initiale peuvent être imputées aux locations.</span><span class="sxs-lookup"><span data-stu-id="abea9-117">After the payment schedules are confirmed, the initial recognition journal entries can be posted against the leases.</span></span>
