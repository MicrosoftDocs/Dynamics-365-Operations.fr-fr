---
title: "Créer automatiquement des commandes de service"
description: "Vous pouvez générer des commandes de service en fonction d'un accord de service pour la période de validité de l'accord de service."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2d942d4448e0f792945603d3f5960fb82095be30
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="automatically-create-service-orders"></a><span data-ttu-id="ff9b2-103">Créer automatiquement des commandes de service</span><span class="sxs-lookup"><span data-stu-id="ff9b2-103">Automatically create service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ff9b2-104">Vous pouvez générer des commandes de service en fonction d'un accord de service pour la période de validité de l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-104">You can generate service orders that are based on a service agreement for the valid period of the service agreement.</span></span>

<span data-ttu-id="ff9b2-105">Les commandes de service générées à partir d'un accord de service y sont toutes associées.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-105">The service orders that you generate from a service agreement are all attached to the service agreement.</span></span>

<span data-ttu-id="ff9b2-106">Les commandes de service sont générées automatiquement à partir des paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="ff9b2-106">Service orders are generated automatically from the following settings:</span></span>

  - <span data-ttu-id="ff9b2-107">l'intervalle de l'accord de service défini dans les lignes de l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-107">The service agreement interval that is set up in the service agreement lines.</span></span> <span data-ttu-id="ff9b2-108">Il indique la fréquence de création des lignes de commande de service.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-108">The service agreement interval indicates the frequency that service-order lines are created.</span></span> <span data-ttu-id="ff9b2-109">Pour plus d'informations, voir [Intervalles de services](service-intervals.md).</span><span class="sxs-lookup"><span data-stu-id="ff9b2-109">For more information, see [Service intervals](service-intervals.md).</span></span>

  - <span data-ttu-id="ff9b2-110">la période spécifiée pour définir la période de service dans les champs **Date de début** et **Date de fin** de l'écran **Créer des commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-110">The period that you specify to define the service period in the **From date** and **To date** fields in the **Create service orders** form.</span></span> <span data-ttu-id="ff9b2-111">Pour plus d'informations, voir [Création de commandes de service automatiquement](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="ff9b2-111">For more information, see [Create service orders automatically](create-service-orders-automatically.md).</span></span>

  - <span data-ttu-id="ff9b2-112">l'option **Combiner les commandes de service** de l'en-tête d'accord de service.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-112">The **Combine service orders** option on the service agreement header.</span></span> <span data-ttu-id="ff9b2-113">Cette option définit si des lignes de commande de service générées à partir d'un accord de service combinent les commandes de service sur la base de l'employé, de la tâche de service, de l'objet de service ou de l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-113">This option defines whether service order lines generated from a service agreement, combines service orders according to employee, service task, service object, or service agreement.</span></span> <span data-ttu-id="ff9b2-114">Pour plus d'informations, voir [Combiner les commandes de service](combine-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="ff9b2-114">For more information, see [Combine service orders](combine-service-orders.md).</span></span>

  - <span data-ttu-id="ff9b2-115">l'option **Fenêtre Délai** de la ligne d'accord de service.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-115">The **Time window** option on the service agreement line.</span></span> <span data-ttu-id="ff9b2-116">La fenêtre Délai définit le déplacement d'une commande de service en relation avec sa date calculée.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-116">The time window defines how far a service order line can move with regard to its calculated date.</span></span> <span data-ttu-id="ff9b2-117">Pour plus d'informations, voir [Fenêtre Délai](time-windows.md).</span><span class="sxs-lookup"><span data-stu-id="ff9b2-117">For more information, see [Time windows](time-windows.md).</span></span>


> [!NOTE]
> <P><span data-ttu-id="ff9b2-118">Si le jour spécifié pour une commande de service n'est pas en cours dans la calendrier sélectionné dans l'écran <STRONG>Paramètres de gestion des services</STRONG>, un message vous informe d'un conflit de calendrier.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-118">If the day that is specified for a service order is not open in the calendar that you have selected in the <STRONG>Service management parameters</STRONG> form, a message will indicate that there is a calendar conflict.</span></span> <span data-ttu-id="ff9b2-119">Vous pouvez ignorer le message. La commande de service est créée même si le jour est fermé sur la calendrier.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-119">You can safely ignore the message; the service order will be created, even though the day is closed on the calendar.</span></span></P>

## <a name="example-1"></a><span data-ttu-id="ff9b2-120">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="ff9b2-120">Example 1</span></span>

<span data-ttu-id="ff9b2-121">L'accord de service s'étend du 1er janvier 2012 au 31 décembre 2012.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-121">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="ff9b2-122">Si l'accord de service spécifié dans l'écran **Créer des commandes de service** s'étend du 1er novembre 2012 au 1er février 2013, les commandes de service sont créées du 1er novembre 2012 au 31 décembre 2012.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-122">If the service period that you specify in the **Create service orders** form is from November 1, 2012 until February 1, 2013, service orders are created from November 1, 2012 until December 31, 2012.</span></span>

## <a name="example-2"></a><span data-ttu-id="ff9b2-123">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="ff9b2-123">Example 2</span></span>

<span data-ttu-id="ff9b2-124">L'accord de service s'étend du 1er janvier 2012 au 31 décembre 2012.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-124">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="ff9b2-125">Deux lignes d'accord de service y sont associées.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-125">Two service agreement lines are attached to the service agreement.</span></span> <span data-ttu-id="ff9b2-126">La date de début de la première ligne d'accord de service est le 2 janvier 2012 et sa date de fin est le 1er mars 2012.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-126">The first service agreement line has a starting date on January 2, 2012 and an ending date on March 1, 2012.</span></span> <span data-ttu-id="ff9b2-127">La date de début de la deuxième ligne d'accord de service est le 1er avril 2012 et sa date de fin est le 31 décembre 2012.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-127">The second service agreement line has a starting date on April 1, 2012 and an ending date on December 31, 2012.</span></span> <span data-ttu-id="ff9b2-128">Vous spécifiez une période dans l'écran **Créer des commandes de service** qui s'étend du 1er octobre 2012 au 31 décembre 2012.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-128">You specify a period in the **Create service orders** form that is from October 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="ff9b2-129">Par conséquent, les commandes de service ne sont générées que pour la deuxième ligne d'accord car les dates de début et de fin de la première ligne d'accord sont antérieures à la période spécifiée pour la commande de service.</span><span class="sxs-lookup"><span data-stu-id="ff9b2-129">Therefore, service orders are generated only for the second agreement line, because the starting date and ending date of the first agreement line are before the period that you specified for the service order.</span></span>

  



