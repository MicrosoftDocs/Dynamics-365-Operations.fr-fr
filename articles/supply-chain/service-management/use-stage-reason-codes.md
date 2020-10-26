---
title: Utilisation des codes motif de stade
description: Un code motif permet d'indiquer pourquoi un contrat de niveau de service a été annulé ou pourquoi la limite de temps définie par un contrat de niveau de service a été dépassée.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74594871e9eeed86ae2914d1e5a08c0af28ab643
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985092"
---
# <a name="use-stage-reason-codes"></a><span data-ttu-id="7ec92-103">Utilisation des codes motif de stade</span><span class="sxs-lookup"><span data-stu-id="7ec92-103">Use stage reason codes</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="7ec92-104">Un code motif permet d'indiquer pourquoi un contrat de niveau de service a été annulé ou pourquoi la limite de temps définie par un contrat de niveau de service a été dépassée.</span><span class="sxs-lookup"><span data-stu-id="7ec92-104">You use a reason code to indicate why a service level agreement (SLA) has been canceled, or why a service order has exceeded the time limit that is you define in the SLA.</span></span>

<span data-ttu-id="7ec92-105">Vous pouvez également indiquer qu'un code motif est nécessaire lorsqu'un contrat SLA est annulé ou lorsque la limite de temps définie dans un contrat SLA a été dépassée.</span><span class="sxs-lookup"><span data-stu-id="7ec92-105">You can also specify that a reason code is required when an SLA is canceled, or when the time limit exceeds the time that is specified in the SLA for the service order.</span></span>

<span data-ttu-id="7ec92-106">Si vous avez spécifié qu'un code motif est requis, vous devez entrer un code motif dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7ec92-106">If you have specified that a reason code is required, you must enter a reason code in the following situations:</span></span>

  - <span data-ttu-id="7ec92-107">lorsqu'une commande de service est déplacée à un stade qui arrête l'enregistrement du temps contre le contrat SLA pour cette commande de service ;</span><span class="sxs-lookup"><span data-stu-id="7ec92-107">When a service order is moved to a stage that stops time recording against the SLA for the service order.</span></span>

  - <span data-ttu-id="7ec92-108">lorsqu'une commande de service est terminée ;</span><span class="sxs-lookup"><span data-stu-id="7ec92-108">When the service order is signed off.</span></span>

  - <span data-ttu-id="7ec92-109">lorsque l'enregistrement du temps est arrêté manuellement.</span><span class="sxs-lookup"><span data-stu-id="7ec92-109">When time recording is manually stopped.</span></span>

## <a name="set-up-reason-codes"></a><span data-ttu-id="7ec92-110">Paramétrer des codes motif</span><span class="sxs-lookup"><span data-stu-id="7ec92-110">Set up reason codes</span></span>

1.  <span data-ttu-id="7ec92-111">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Commandes de service** \> **Codes motif du stade**.</span><span class="sxs-lookup"><span data-stu-id="7ec92-111">Click **Service management** \> **Setup** \> **Service orders** \> **Stage reason codes**.</span></span>

2.  <span data-ttu-id="7ec92-112">Dans l'écran **Codes motif du stade**, cliquez sur **Nouveau** pour créer un code motif de stade.</span><span class="sxs-lookup"><span data-stu-id="7ec92-112">In the **Stage reason codes** form, click **New** to create a new reason code.</span></span>

3.  <span data-ttu-id="7ec92-113">Dans le champ **Codes motif du stade**, entrez un code motif de stade unique.</span><span class="sxs-lookup"><span data-stu-id="7ec92-113">In the **Stage reason code** field, enter a unique stage reason code.</span></span>

4.  <span data-ttu-id="7ec92-114">Dans le champ **Description**, entrez une description du code motif de stade.</span><span class="sxs-lookup"><span data-stu-id="7ec92-114">In the **Description** field, enter a description of the stage reason code.</span></span>

5.  <span data-ttu-id="7ec92-115">Fermez l'écran pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="7ec92-115">Close the form to save your changes.</span></span>

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a><span data-ttu-id="7ec92-116">Demande des codes motif lors de l'annulation d'un contrat de niveau service</span><span class="sxs-lookup"><span data-stu-id="7ec92-116">Require reason codes when a service level agreement is canceled</span></span>

1.  <span data-ttu-id="7ec92-117">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Paramètres de gestion des services**.</span><span class="sxs-lookup"><span data-stu-id="7ec92-117">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="7ec92-118">Dans l'écran **Paramètres de gestion des services**, cliquez sur le lien **Général**, puis activez la case à cocher **Code motif de l'annulation**.</span><span class="sxs-lookup"><span data-stu-id="7ec92-118">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on canceling** check box.</span></span>

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a><span data-ttu-id="7ec92-119">Demande des codes motif lors du dépassement de la limite de temps définie par le contrat SLA</span><span class="sxs-lookup"><span data-stu-id="7ec92-119">Require reason codes when the a service order exceeds the time limit that is set by the service level agreement</span></span>

1.  <span data-ttu-id="7ec92-120">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Paramètres de gestion des services**.</span><span class="sxs-lookup"><span data-stu-id="7ec92-120">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="7ec92-121">Dans l'écran **Paramètres de gestion des services**, cliquez sur le lien **Général**, puis activez la case à cocher **Code motif du dépassement de l'heure**.</span><span class="sxs-lookup"><span data-stu-id="7ec92-121">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on exceeding time** check box.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ec92-122">Voir également :</span><span class="sxs-lookup"><span data-stu-id="7ec92-122">See also</span></span>

[<span data-ttu-id="7ec92-123">Démarrage et arrêt de l'enregistrement de l'heure dans une commande de service</span><span class="sxs-lookup"><span data-stu-id="7ec92-123">Start and stop time recording on a service order</span></span>](start-and-stop-time-recording-on-a-service-order.md)

  


