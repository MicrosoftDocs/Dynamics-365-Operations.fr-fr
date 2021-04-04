---
title: Création manuelle de commandes de service
description: Vous pouvez créer des commandes de service manuellement à l’aide d’un accord de service ou de l’écran **Commandes de service**.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72b600bc59119a6304fa043240a34051435f8691
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470951"
---
# <a name="create-service-orders-manually"></a><span data-ttu-id="13d75-103">Création manuelle de commandes de service</span><span class="sxs-lookup"><span data-stu-id="13d75-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="13d75-104">Vous pouvez créer des commandes de service manuellement à l’aide d’un accord de service ou de l’écran **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="13d75-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="13d75-105">Vous pouvez également créer une commande de service à partir d’un projet.</span><span class="sxs-lookup"><span data-stu-id="13d75-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="13d75-106">Vous pouvez utiliser des processus automatisés pour créer des commandes de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="13d75-107">Création manuelle d’une commande de service à partir d’un accord de service</span><span class="sxs-lookup"><span data-stu-id="13d75-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="13d75-108">Sélectionnez **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.</span><span class="sxs-lookup"><span data-stu-id="13d75-108">Select **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="13d75-109">Sélectionnez un accord de service ou créez-en un nouveau.</span><span class="sxs-lookup"><span data-stu-id="13d75-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="13d75-110">Cliquez sur l’onglet **Livrer** et, dans le groupe **Créer**, sélectionnez **Commandes de service prévisionnelles** pour ouvrir le formulaire **Créer des commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="13d75-110">Select the **Deliver** tab and in the **Create** group select **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="13d75-111">Création manuelle d’une commande de service dans l’écran Commandes de service</span><span class="sxs-lookup"><span data-stu-id="13d75-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="13d75-112">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="13d75-112">Select **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="13d75-113">Sélectionnez **Nouveau** pour créer un ordre de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-113">Select **New** to create a new service order.</span></span>

3.  <span data-ttu-id="13d75-114">Créez les lignes d’ordre de service pour la commande de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="13d75-115">Si la case à cocher <STRONG>Autoriser sans accord de service</STRONG> de l’écran <STRONG>Paramètres de gestion des services</STRONG> est activée, vous pouvez valider les transactions à partir des lignes de commande de service sans lier la commande de service à un accord de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="13d75-116">Si la case à cocher est désactivée, vous devez au moins lier la commande de service créée manuellement à un projet avant de valider les lignes de commande de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="13d75-117">Création d’une commande de service à partir d’un projet</span><span class="sxs-lookup"><span data-stu-id="13d75-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="13d75-118">Accédez à **Gestion et comptabilité des projets** \> **Commun** \> **Projets** \> **Tous les projets**.</span><span class="sxs-lookup"><span data-stu-id="13d75-118">Go to **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="13d75-119">Dans le formulaire **Projets**, dans le volet **Actions**, cliquez sur l’onglet **Gérer** \> **Service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="13d75-119">In the **Projects** form, on the **Action Pane**, select the **Manage** tab \> select **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="13d75-120">Suivez la procédure précédente de création manuelle d’une commande de service dans l’écran **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="13d75-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="13d75-121">Le champ **ID projet** affiche la référence du projet.</span><span class="sxs-lookup"><span data-stu-id="13d75-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="13d75-122">Si la case à cocher <STRONG>Autoriser sans accord de service</STRONG> de l’écran <STRONG>Paramètres de gestion des services</STRONG> est activée, vous pouvez valider les transactions à partir des lignes de commande de service sans lier la commande de service à un accord de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="13d75-123">Si la case à cocher est désactivée, vous devez au moins lier la commande de service créée manuellement à un projet avant de valider les lignes de commande de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="13d75-124">Création d’une commande de service à partir de l’écran Commande client</span><span class="sxs-lookup"><span data-stu-id="13d75-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="13d75-125">Vous pouvez créer une commande de service dans l’écran **Commandes client** à l’aide de l’Assistant **Créer une nouvelle commande de service basée sur la commande client**.</span><span class="sxs-lookup"><span data-stu-id="13d75-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="13d75-126">Accédez à **Ventes et marketing** \> **Commun** \> **Commandes client** \> **Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="13d75-126">Go to **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="13d75-127">Ouvrez les commandes clients concernées.</span><span class="sxs-lookup"><span data-stu-id="13d75-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="13d75-128">Sous l’onglet **Commande client**, cliquez sur **Commande de service** pour démarrer l’Assistant **Créer une commande de service basée sur la commande client**.</span><span class="sxs-lookup"><span data-stu-id="13d75-128">On the **Sales order** tab, select **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="13d75-129">Cliquez sur **Suivant \>**, puis effectuez les étapes suivantes dans la page **Sélectionner l’accord pour la commande de service** :</span><span class="sxs-lookup"><span data-stu-id="13d75-129">Select **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="13d75-130">Le champ **Accord de service** permet de sélectionner l’accord de service auquel la nouvelle commande de service doit être associée.</span><span class="sxs-lookup"><span data-stu-id="13d75-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="13d75-131">Facultatif : le champ **ID projet** permet d’associer cette commande de service à un projet particulier.</span><span class="sxs-lookup"><span data-stu-id="13d75-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="13d75-132">Cliquez sur **Suivant \>**, puis effectuez les étapes suivantes dans la page **Créer une commande de service** :</span><span class="sxs-lookup"><span data-stu-id="13d75-132">Select **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="13d75-133">Dans le champ **Durée de service préférée**, entrez une date et une heure pour le début de l’appel de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="13d75-134">Facultatif : modifiez le texte dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="13d75-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="13d75-135">Par défaut, ce champ contient la description de l’accord de service sélectionné dans la page précédente.</span><span class="sxs-lookup"><span data-stu-id="13d75-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="13d75-136">Dans le champ **Responsable**, sélectionnez l’ID de l’employé responsable de l’accord, puis, si vous le connaissez, entrez l’ID du technicien favori du client pour l’appel de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="13d75-137">Dans le champ **ID contact**, sélectionnez la personne à contacter au sein de la société du client concernant cette commande de service.</span><span class="sxs-lookup"><span data-stu-id="13d75-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="13d75-138">Sélectionnez **Suivant \>**, puis **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="13d75-138">Select **Next \>**, and then select **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="13d75-139">Voir également :</span><span class="sxs-lookup"><span data-stu-id="13d75-139">See also</span></span>

[<span data-ttu-id="13d75-140">Commandes de service</span><span class="sxs-lookup"><span data-stu-id="13d75-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="13d75-141">Créer automatiquement des commandes de service</span><span class="sxs-lookup"><span data-stu-id="13d75-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="13d75-142">[Créer des commandes de service (écran classe)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="13d75-142">[Create service orders (class form)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span></span> 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]