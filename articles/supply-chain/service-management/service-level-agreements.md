---
title: Vue d'ensemble des contrats de niveau de service
description: Dans le cadre d'un contrat de niveau de service, le client accepte un temps de réponse minimal (de l'enregistrement du problème par la société de service jusqu'à la résolution du problème).
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01cdfe519e55ca2a9aa17f4ac181ee675b2793cf
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982353"
---
# <a name="service-level-agreements-overview"></a><span data-ttu-id="08ae5-103">Vue d'ensemble des contrats de niveau de service</span><span class="sxs-lookup"><span data-stu-id="08ae5-103">Service level agreements overview</span></span>       

[!include [banner](../includes/banner.md)]


<span data-ttu-id="08ae5-104">Un contrat de niveau de service (SLA) est un contrat conclu entre une société de service et un client de service.</span><span class="sxs-lookup"><span data-stu-id="08ae5-104">A service level agreement (SLA) is an agreement between a service company and a service customer.</span></span> <span data-ttu-id="08ae5-105">Dans le cadre d'un contrat SLA, le client accepte un temps de réponse minimal (de l'enregistrement du problème par la société de service jusqu'à la résolution du problème).</span><span class="sxs-lookup"><span data-stu-id="08ae5-105">In a SLA, the customer agrees to a minimum response time based on when the service company records the issue and when the issue is resolved.</span></span>

<span data-ttu-id="08ae5-106">Un contrat SLA applique un niveau de service standard offert aux clients et indique de façon transparente la date d'exécution d'une tâche de service pour une société de service.</span><span class="sxs-lookup"><span data-stu-id="08ae5-106">A SLA enforces a standard level of service that is offered to customers, and also makes it transparent to a service company when a service job should be completed.</span></span>

<span data-ttu-id="08ae5-107">Plusieurs contrats SLA peuvent être créés pour offrir aux clients de service différents niveaux de service.</span><span class="sxs-lookup"><span data-stu-id="08ae5-107">Any number of SLAs can be created to offer service customers different levels of service.</span></span>

## <a name="create-a-service-level-agreement"></a><span data-ttu-id="08ae5-108">Création d'un contrat de niveau de service</span><span class="sxs-lookup"><span data-stu-id="08ae5-108">Create a service level agreement</span></span>

1.  <span data-ttu-id="08ae5-109">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Accords de service** \> **Contrats de niveau de service**.</span><span class="sxs-lookup"><span data-stu-id="08ae5-109">Click **Service management** \> **Setup** \> **Service agreements** \> **Service level agreements**.</span></span>

2.  <span data-ttu-id="08ae5-110">Tapez un nom pour le contrat de niveau de service dans le champ **Contrat de niveau de service**.</span><span class="sxs-lookup"><span data-stu-id="08ae5-110">Type a name for the service level agreement in the **Service level agreement** field.</span></span>

3.  <span data-ttu-id="08ae5-111">Entrez le temps que vous souhaitez accorder pour l'achèvement des appels de service associés au contrat de niveau de service.</span><span class="sxs-lookup"><span data-stu-id="08ae5-111">Type the time that you want to allow for completion of service calls that are attached to the service level agreement.</span></span> <span data-ttu-id="08ae5-112">Sélectionnez ensuite un calendrier si vous souhaitez baser le contrat de niveau de service sur un calendrier spécifique.</span><span class="sxs-lookup"><span data-stu-id="08ae5-112">Then select a calendar if you want to base the service level agreement on a specific calendar.</span></span>

## <a name="apply-a-service-level-agreement"></a><span data-ttu-id="08ae5-113">Application d'un contrat de niveau de service</span><span class="sxs-lookup"><span data-stu-id="08ae5-113">Apply a service level agreement</span></span>

<span data-ttu-id="08ae5-114">Le contrat SLA est appliqué directement à un accord de service.</span><span class="sxs-lookup"><span data-stu-id="08ae5-114">The SLA is applied directly to a service agreement.</span></span>

<span data-ttu-id="08ae5-115">Les commandes de service créées manuellement et associées à un accord de service avec un contrat SLA sont évaluées par rapport à ce contrat.</span><span class="sxs-lookup"><span data-stu-id="08ae5-115">Service orders that you create manually and attach to a service agreement that has an SLA are measured against that SLA.</span></span>

<span data-ttu-id="08ae5-116">Les commandes de service créées automatiquement ne sont pas associées à un contrat SLA.</span><span class="sxs-lookup"><span data-stu-id="08ae5-116">Service orders that you create automatically are not attached to an SLA.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a><span data-ttu-id="08ae5-117">Application du contrat de niveau de service à l'accord de service</span><span class="sxs-lookup"><span data-stu-id="08ae5-117">Apply the service level agreement to the service agreement</span></span>

1.  <span data-ttu-id="08ae5-118">Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.</span><span class="sxs-lookup"><span data-stu-id="08ae5-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="08ae5-119">Sélectionnez le contrat de service auquel appliquer le contrat SLA, puis cliquez sur **Modifier** dans le volet **Actions**.</span><span class="sxs-lookup"><span data-stu-id="08ae5-119">Select the service agreement that you want to apply the SLA to, and then click **Edit** on the **Action Pane**.</span></span>

2.  <span data-ttu-id="08ae5-120">Dans le champ **Contrat de niveau de service**, sélectionnez le contrat SLA à affecter.</span><span class="sxs-lookup"><span data-stu-id="08ae5-120">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a><span data-ttu-id="08ae5-121">Application du contrat de niveau de service à un groupe d'accords de service</span><span class="sxs-lookup"><span data-stu-id="08ae5-121">Apply the service level agreement to the service agreement group</span></span>

1.  <span data-ttu-id="08ae5-122">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Accords de service** \> **Groupes d'accords de service**.</span><span class="sxs-lookup"><span data-stu-id="08ae5-122">Click **Service management** \> **Setup** \> **Service agreements** \> **Service agreement groups**.</span></span>

2.  <span data-ttu-id="08ae5-123">Dans le champ **Contrat de niveau de service**, sélectionnez le contrat SLA à affecter.</span><span class="sxs-lookup"><span data-stu-id="08ae5-123">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="track-time-on-a-service-order-against-an-sla"></a><span data-ttu-id="08ae5-124">Suivi de la durée dans une commande de service par rapport à un contrat SLA</span><span class="sxs-lookup"><span data-stu-id="08ae5-124">Track time on a service order against an SLA</span></span>

<span data-ttu-id="08ae5-125">Lorsque vous créez une commande de service pour un accord de service auquel le contrat SLA est affecté, l'intervalle pour la fourniture de service est initialisé, et le système commence à suivre le délai de livraison.</span><span class="sxs-lookup"><span data-stu-id="08ae5-125">When you create a new service order for a service agreement that an SLA is assigned to, the time interval for the delivery of the service is initiated, and the system starts to track the delivery time.</span></span> <span data-ttu-id="08ae5-126">Vous pouvez également définir les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="08ae5-126">Additionally, you can set the following options:</span></span>

  - <span data-ttu-id="08ae5-127">démarrage et arrêt de l'enregistrement de l'heure dans la commande de service pour enregistrer la durée totale passée sur les commandes de service ;</span><span class="sxs-lookup"><span data-stu-id="08ae5-127">You can start and stop time recording on the service order to register the total amount of time that is spent on service orders.</span></span>

  - <span data-ttu-id="08ae5-128">Vous pouvez contrôler la conformité avec le délai défini dans le contrat de niveau de service.</span><span class="sxs-lookup"><span data-stu-id="08ae5-128">You can monitor compliance with the time interval that is set in the service level agreement.</span></span>

  - <span data-ttu-id="08ae5-129">Vous pouvez définir des codes motif si le délai du contrat de niveau de service est dépassé.</span><span class="sxs-lookup"><span data-stu-id="08ae5-129">You can define reason codes that must be set if the time interval of the service level agreement is exceeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="08ae5-130">Voir également :</span><span class="sxs-lookup"><span data-stu-id="08ae5-130">See also</span></span>

[<span data-ttu-id="08ae5-131">Affichage de la conformité avec les contrats SLA</span><span class="sxs-lookup"><span data-stu-id="08ae5-131">View compliance with service level agreements</span></span>](view-compliance-with-service-level-agreements.md)

  


