---
title: Création de commandes de service automatiquement
description: Vous pouvez créer des commandes de service pour un ou plusieurs accords de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 914df1626b02110264b895e82dc9301f3aa0afce
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985116"
---
# <a name="create-service-orders-automatically"></a><span data-ttu-id="fa0f6-103">Création de commandes de service automatiquement</span><span class="sxs-lookup"><span data-stu-id="fa0f6-103">Create service orders automatically</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="fa0f6-104">Vous pouvez créer des commandes de service pour un ou plusieurs accords de service.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-104">You can create service orders for one service agreement or for several service agreements.</span></span> <span data-ttu-id="fa0f6-105">Lorsqu'elles sont créées, vous pouvez afficher vos commandes de service dans l'écran **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-105">When they are created, you can view your service orders in the **Service orders** form.</span></span>

<span data-ttu-id="fa0f6-106">Les commandes de service sont créées uniquement pour la période valide de l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-106">Service orders are created only for the valid period of the service agreement.</span></span> <span data-ttu-id="fa0f6-107">Si l'intervalle que vous spécifiez dans l'écran **Créer des commandes de service** se situe avant la date de début ou après la date de fin de l'accord de service, les commandes de service sont créées uniquement pour la partie de l'intervalle s'inscrivant dans les dates de l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-107">If the interval that you specify in the **Create service orders** form is before the starting date or after the ending date of the service agreement, service orders are created only for the part of the interval that is within the service agreement dates.</span></span>

<span data-ttu-id="fa0f6-108">Lorsque vous créez des commandes de service manuellement ou automatiquement à partir de la ligne d'accord de service, la commande de service doit avoir lieu dans l'intervalle de temps défini par les dates de début et de fin de la ligne, sauf si vous ne spécifiez pas de date de fin dans la ligne.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-108">When you create service orders manually or automatically from the service agreement line, the service order must be in the time interval that is defined by the starting and ending dates for the line, unless you do not specify an ending date on the line.</span></span>

## <a name="create-service-orders-automatically-for-a-service-agreement"></a><span data-ttu-id="fa0f6-109">Création automatique de commandes de service pour un accord de service</span><span class="sxs-lookup"><span data-stu-id="fa0f6-109">Create service orders automatically for a service agreement</span></span>

1.  <span data-ttu-id="fa0f6-110">Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-110">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="fa0f6-111">Sélectionnez un accord de service.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-111">Select a service agreement.</span></span>

3.  <span data-ttu-id="fa0f6-112">Cliquez sur l'onglet **Livrer**, puis sur **Commandes de service prévisionnelles**.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-112">Click the **Deliver** tab, and then click **Planned service orders**.</span></span>

4.  <span data-ttu-id="fa0f6-113">Spécifiez les dates dans les champs **Date de début** et **Date de fin** pour définir la période de service.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-113">Specify dates in the **From date** and **To date** fields to define the service period.</span></span>

5.  <span data-ttu-id="fa0f6-114">Activez la case à cocher **Afficher Infos** pour afficher la liste des commandes de service créées.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-114">Select the **Show Infolog** check box to display a list of the service orders that are created.</span></span>

6.  <span data-ttu-id="fa0f6-115">Sélectionnez les types de transaction dans le groupe de champs **Inclure les types de transaction**.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-115">Select transaction types in the **Include transaction types** field group.</span></span> <span data-ttu-id="fa0f6-116">Les types de transactions représentent les lignes créées dans l'accord de service et chaque type de transaction que vous sélectionnez génère plusieurs commandes de service, en fonction de l'intervalle de service spécifié sur la ligne d'accord de service.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-116">The transaction types represent the lines that are created in the service agreement, and each transaction type that you select generates several service orders, depending on the service interval that is specified on the service agreement line.</span></span>

7.  <span data-ttu-id="fa0f6-117">Pour créer des commandes de service manquantes au sein d'une série continue de commandes de service, activez la case à cocher **Continu**.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-117">To create any service orders that are missing from continuous series of service orders, select the **Continuous** check box.</span></span>

8.  <span data-ttu-id="fa0f6-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-118">Click **OK**.</span></span>

## <a name="create-service-orders-automatically-for-several-service-agreements"></a><span data-ttu-id="fa0f6-119">Création automatique de commandes de service pour plusieurs accords de service</span><span class="sxs-lookup"><span data-stu-id="fa0f6-119">Create service orders automatically for several service agreements</span></span>

1.  <span data-ttu-id="fa0f6-120">Cliquez sur **Gestion des services** \> **Périodique** \> **Commandes de service** \> **Créer des commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-120">Click **Service management** \> **Periodic** \> **Service orders** \> **Create service orders**.</span></span>

2.  <span data-ttu-id="fa0f6-121">Cliquez sur **Sélectionner** afin d'opérer des sélections pour ajouter ou supprimer des critères à utiliser pour créer des commandes de service.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-121">Click **Select** to make selections to add or remove criteria to use to create service orders.</span></span>

3.  <span data-ttu-id="fa0f6-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa0f6-122">Click **OK**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa0f6-123">Voir également :</span><span class="sxs-lookup"><span data-stu-id="fa0f6-123">See also</span></span>

[<span data-ttu-id="fa0f6-124">Commandes de service</span><span class="sxs-lookup"><span data-stu-id="fa0f6-124">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="fa0f6-125">Créer automatiquement des commandes de service</span><span class="sxs-lookup"><span data-stu-id="fa0f6-125">Automatically create service orders</span></span>](auto-create-service-orders.md)

  


