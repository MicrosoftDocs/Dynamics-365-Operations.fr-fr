---
title: Annuler des commandes de service
description: Vous pouvez annuler une commande de service ou une ligne de commande de service à partir de la commande de service elle-même ou annuler plusieurs commandes de service en exécutant une tâche périodique.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 779f535ac617d3f3940cc1b226fa53dc72e3411a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831600"
---
# <a name="cancel-service-orders"></a><span data-ttu-id="11add-103">Annuler des commandes de service</span><span class="sxs-lookup"><span data-stu-id="11add-103">Cancel service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="11add-104">Vous pouvez annuler une commande de service ou une ligne de commande de service à partir de la commande de service elle-même ou annuler plusieurs commandes de service en exécutant une tâche périodique.</span><span class="sxs-lookup"><span data-stu-id="11add-104">You can cancel a service order or service order line from the service order itself, or you can cancel multiple service orders by running a periodic job.</span></span>


> [!NOTE]
> <P><span data-ttu-id="11add-105">Vous ne pouvez pas annuler une commande de service si son stade ne le permet pas, si elle contient des demandes d’articles ou si elle a déjà été validée.</span><span class="sxs-lookup"><span data-stu-id="11add-105">Service orders cannot be canceled if the stage of the service order does not allow cancelation, if the service order has item requirements, or if the service order has already been posted.</span></span></P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a><span data-ttu-id="11add-106">Annulation d’une commande de service dans l’écran Commandes de service</span><span class="sxs-lookup"><span data-stu-id="11add-106">Cancel a service order in the Service orders form</span></span>

1.  <span data-ttu-id="11add-107">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="11add-107">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="11add-108">Sélectionnez la commande de service, puis dans le volet Actions, cliquez sur **Annuler la commande**.</span><span class="sxs-lookup"><span data-stu-id="11add-108">Select the service order, and on the Action Pane, click **Cancel order**.</span></span>

## <a name="cancel-a-service-order-line"></a><span data-ttu-id="11add-109">Annulation d’une ligne de commande de service</span><span class="sxs-lookup"><span data-stu-id="11add-109">Cancel a service order line</span></span>

1.  <span data-ttu-id="11add-110">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="11add-110">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="11add-111">Double-cliquez sur la commande de service qui contient la ligne à annuler.</span><span class="sxs-lookup"><span data-stu-id="11add-111">Double-click the service order that contains the line you want to cancel.</span></span>

2.  <span data-ttu-id="11add-112">Sélectionnez la ligne de commande de service à annuler, puis cliquez sur **Annuler la ligne de commande** pour modifier le statut de la ligne sur **Annulé**.</span><span class="sxs-lookup"><span data-stu-id="11add-112">Select the service order line that you want to cancel, and then click **Cancel order line** to change the status of the line to **Canceled**.</span></span>


> [!TIP]
> <P><span data-ttu-id="11add-113">Pour inverser l’annulation d’une ligne de commande de service et rétablir son statut sur <STRONG>Créé</STRONG>, cliquez sur <STRONG>Annuler l’annulation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="11add-113">To reverse the cancellation of a service order line and change the status back to <STRONG>Created</STRONG>, click <STRONG>Revoke cancel</STRONG>.</span></span></P>


## <a name="cancel-multiple-service-orders"></a><span data-ttu-id="11add-114">Annulation de plusieurs commandes de service</span><span class="sxs-lookup"><span data-stu-id="11add-114">Cancel multiple service orders</span></span>

1.  <span data-ttu-id="11add-115">Cliquez sur **Gestion des services** \> **Périodique** \> **Commandes de service** \> **Annuler des commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="11add-115">Click **Service management** \> **Periodic** \> **Service orders** \> **Cancel service orders**.</span></span>

2.  <span data-ttu-id="11add-116">Cliquez sur le bouton **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="11add-116">Click the **Select** button.</span></span>

3.  <span data-ttu-id="11add-117">Dans l’écran **Recherche**, dans la colonne **Critères**, sélectionnez les commandes de service à annuler.</span><span class="sxs-lookup"><span data-stu-id="11add-117">In the **Inquiry** form, in the **Criteria** column, select the service orders that you want to cancel.</span></span>

4.  <span data-ttu-id="11add-118">Cliquez sur **OK** pour fermer l’écran **Recherche**.</span><span class="sxs-lookup"><span data-stu-id="11add-118">Click **OK** to close the **Inquiry** form.</span></span>

5.  <span data-ttu-id="11add-119">Activez la case à cocher **Afficher Infos** pour générer une fenêtre Infos répertoriant les commandes de service annulées.</span><span class="sxs-lookup"><span data-stu-id="11add-119">Select the **Show Infolog** check box to generate an Infolog that lists the canceled service orders.</span></span>

6.  <span data-ttu-id="11add-120">Activez la case à cocher **Annuler l’annulation** pour inverser le statut **Annulé** d’une commande de service.</span><span class="sxs-lookup"><span data-stu-id="11add-120">Select the **Revoke cancel** check box if you want to reverse the **Canceled** status of a service order.</span></span>

7.  <span data-ttu-id="11add-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="11add-121">Click **OK**.</span></span>

<span data-ttu-id="11add-122">Soit les commandes de service sélectionnées sont annulées, soit leur statut de progression **Annulé** a été rétabli sur **En cours**.</span><span class="sxs-lookup"><span data-stu-id="11add-122">The selected service orders are either canceled or their progress status of **Canceled** has been reversed to **In process**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="11add-123">Si vous activez la case à cocher <STRONG>Annuler l’annulation</STRONG>, les commandes de service dont le statut de progression est <STRONG>Annulé</STRONG> sont rétablies et celles dont le statut de progression est <STRONG>En cours</STRONG> ne sont pas annulées.</span><span class="sxs-lookup"><span data-stu-id="11add-123">If you select the <STRONG>Revoke cancel</STRONG> check box, service orders with a progress status of <STRONG>Canceled</STRONG> are reversed and service orders with a progress status of <STRONG>In process</STRONG> are not canceled.</span></span></P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]