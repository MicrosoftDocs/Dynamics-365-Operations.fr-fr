---
title: Ajout d'une adresse à une commande de service
description: Cette rubrique explique comment ajouter une adresse du client à une commande de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
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
ms.openlocfilehash: 41497eacae8bcc0e57df8062f7f318a39c2b4909
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428071"
---
# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="ec8a0-103">Ajout d'une adresse à une commande de service</span><span class="sxs-lookup"><span data-stu-id="ec8a0-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ec8a0-104">Cette rubrique explique comment ajouter une adresse du client à une commande de service.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="ec8a0-105">Lorsque vous créez une commande de service, les informations d'adresse sont transférées à partir du projet auquel la commande de service est associée.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="ec8a0-106">Toutefois, vous pouvez sélectionner un autre emplacement à partir des adresses qui sont déjà entrées dans Microsoft Dynamics AX pour des clients, des fournisseurs, des sites, des entrepôts, des commandes de service, et des projets.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="ec8a0-107">Vous pouvez aussi créer une nouvelle adresse.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-107">You can also create a new address.</span></span> <span data-ttu-id="ec8a0-108">Par défaut, la nouvelle adresse est transférée au projet.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="ec8a0-109">Toutefois, vous pouvez spécifier que la nouvelle adresse n'est applicable qu'à cette instance de service.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="ec8a0-110">Dans ce cas, la nouvelle adresse n'est pas transférée au projet.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="ec8a0-111">Créer une adresse de client pour une commande de service</span><span class="sxs-lookup"><span data-stu-id="ec8a0-111">Create a customer address for a service order</span></span>

<span data-ttu-id="ec8a0-112">Pour ajouter une adresse à une commande de service, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ec8a0-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="ec8a0-113">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="ec8a0-114">Ouvrez la commande de service pour laquelle vous souhaitez créer une adresse.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="ec8a0-115">Dans le volet **Actions**, cliquez sur **Modifier**, puis sur **Vue de l'en-tête**.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="ec8a0-116">Dans l'organisateur **Adresse**, cliquez sur **Ajouter une adresse**.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="ec8a0-117">Dans l'écran **Nouvelle adresse**, entrez un nom unique pour l'adresse et renseignez les autres champs.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="ec8a0-118">Si vous entrez le même nom comme adresse existante, les informations entrées dans les champs restants remplaceront les informations relatives à l'adresse existante.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="ec8a0-119">Cliquez sur **OK** pour copier la nouvelle adresse sur votre commande de service.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="ec8a0-120">Spécification d'une autre adresse dans une commande de service</span><span class="sxs-lookup"><span data-stu-id="ec8a0-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="ec8a0-121">Pour ajouter une adresse alternative à une commande de service, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ec8a0-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="ec8a0-122">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="ec8a0-123">Ouvrez la commande de service pour laquelle vous souhaitez entrer une adresse alternative.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="ec8a0-124">Dans le volet **Actions**, cliquez sur **Modifier**, puis sur **Vue de l'en-tête**.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="ec8a0-125">Dans l'organisateur **Adresse**, cliquez sur **Autre adresse**.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="ec8a0-126">Dans l'écran **Sélection d'adresse**, dans le champ **Type d'enregistrement**, sélectionnez **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="ec8a0-127">Sélectionnez une adresse, puis cliquez sur **OK** pour la copier sur votre commande de service.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  


