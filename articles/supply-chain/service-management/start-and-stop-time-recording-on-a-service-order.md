---
title: Démarrage et arrêt de l'enregistrement de l'heure dans une commande de service
description: Démarrage et arrêt de l'enregistrement de l'heure dans une commande de service.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16d9f48ed38a5033fab94d45821f0ed6f7f1f011
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558386"
---
# <a name="start-and-stop-time-recording-on-a-service-order"></a><span data-ttu-id="1d6fa-103">Démarrage et arrêt de l'enregistrement de l'heure dans une commande de service</span><span class="sxs-lookup"><span data-stu-id="1d6fa-103">Start and stop time recording on a service order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="1d6fa-104">Cette procédure permet de démarrer et d'arrêter l'enregistrement d'heure pour une commande de service pour laquelle un contrat SLA est défini.</span><span class="sxs-lookup"><span data-stu-id="1d6fa-104">Use this procedure to start and stop time recording for a service order for which a service level agreement is defined.</span></span>

## <a name="start-time-recording"></a><span data-ttu-id="1d6fa-105">Démarrage de l'enregistrement de l'heure</span><span class="sxs-lookup"><span data-stu-id="1d6fa-105">Start time recording</span></span>

1.  <span data-ttu-id="1d6fa-106">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="1d6fa-106">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="1d6fa-107">Cliquez sur l'onglet **Commande de service**. Dans le volet **Actions**, dans le groupe **Contrat de niveau de service**, cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="1d6fa-107">Click the **Service order** tab. On the **Action Pane**, in the **Service level agreement** group, click **Start**.</span></span>

3.  <span data-ttu-id="1d6fa-108">Entrez les date et heure auxquelles l'enregistrement de l'heure doit commencer.</span><span class="sxs-lookup"><span data-stu-id="1d6fa-108">Enter the date and time that the time recording should be started.</span></span>

## <a name="stop-time-recording"></a><span data-ttu-id="1d6fa-109">Arrêter l'enregistrement de l'heure</span><span class="sxs-lookup"><span data-stu-id="1d6fa-109">Stop time recording</span></span>

1.  <span data-ttu-id="1d6fa-110">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="1d6fa-110">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="1d6fa-111">Cliquez sur l'onglet **Commande de service**. Dans le volet **Actions**, dans le groupe **Contrat de niveau de service**, cliquez sur **Arrêter**.</span><span class="sxs-lookup"><span data-stu-id="1d6fa-111">Click the **Service order** tab. On the **Action Pane**, in the **Service level agreement** group, click **Stop**.</span></span>

3.  <span data-ttu-id="1d6fa-112">Entrez les date et heure auxquelles l'enregistrement de l'heure doit être arrêté.</span><span class="sxs-lookup"><span data-stu-id="1d6fa-112">Enter the date and time that the time recording should be stopped.</span></span>

4.  <span data-ttu-id="1d6fa-113">Sélectionnez **Ajouter un motif de révocation** et sélectionnez un code motif dans la liste **Code motif du stade** si vous souhaitez indiquer la raison de l'arrêt de l'enregistrement de l'heure.</span><span class="sxs-lookup"><span data-stu-id="1d6fa-113">Select **Add a revocation reason**, and select a reason code in the **Stage reason code** list to provide a reason for stopping the time recording.</span></span>


> [!NOTE]
> <P><span data-ttu-id="1d6fa-114">Si <STRONG>Code motif du dépassement de l'heure</STRONG> est sélectionné dans l'écran <STRONG>Paramètres de gestion des services</STRONG>, vous devez fournir un code motif avant de pouvoir arrêter l'enregistrement de l'heure.</span><span class="sxs-lookup"><span data-stu-id="1d6fa-114">If <STRONG>Reason code on exceeding time</STRONG> is selected in the <STRONG>Service management parameters</STRONG> form, you must provide a reason code before you can stop the time recording.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="1d6fa-115">Voir également :</span><span class="sxs-lookup"><span data-stu-id="1d6fa-115">See also</span></span>

<span data-ttu-id="1d6fa-116">[Démarrer l'enregistrement de l'heure du contrat SLA (écran)](https://technet.microsoft.com/en-us/library/hh242297\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="1d6fa-116">[Start SLA time recording (form)](https://technet.microsoft.com/en-us/library/hh242297\(v=ax.60\))</span></span>

<span data-ttu-id="1d6fa-117">[Arrêter l'enregistrement de l'heure du contrat SLA (écran)](https://technet.microsoft.com/en-us/library/hh242241\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="1d6fa-117">[Stop SLA time recording (form)](https://technet.microsoft.com/en-us/library/hh242241\(v=ax.60\))</span></span>

  


