---
title: Installer le complément Intelligence IoT dans LCS
description: Cette rubrique explique comment installer le complément Intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ae6b36c40d2f2f9e5266dfb3e2d1cbbb57755222
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3803089"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="ef66a-103">Installer le complément Intelligence IoT dans LCS</span><span class="sxs-lookup"><span data-stu-id="ef66a-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ef66a-104">Cette rubrique explique comment installer le complément Intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="ef66a-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="ef66a-105">Notez que les compléments ne peuvent pas être installés sur un environnement de démonstration/évaluation.</span><span class="sxs-lookup"><span data-stu-id="ef66a-105">Note that add-ins cannot be installed on a demo/trial environment.</span></span> <span data-ttu-id="ef66a-106">Avant de pouvoir installer le complément, vous devez [créer les ressources Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="ef66a-106">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="ef66a-107">Paramétrage de l’environnement LCS</span><span class="sxs-lookup"><span data-stu-id="ef66a-107">Set up the LCS environment</span></span>

1. <span data-ttu-id="ef66a-108">Ouvrez LCS et accédez à votre environnement Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ef66a-108">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="ef66a-109">Faites défiler jusqu’à la section **Compléments d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-109">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="ef66a-110">Sélectionnez **Installer un nouveau complément** pour afficher la liste des compléments qui ont été activés pour l’environnement.</span><span class="sxs-lookup"><span data-stu-id="ef66a-110">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="ef66a-111">Dans la boîte de dialogue **Sélectionner un complément à installer**, sélectionnez **Intelligence IoT**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-111">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="ef66a-112">Dans la boîte de dialogue **Complément d’installation**, fournissez les détails de votre hub IoT et de votre cache Redis.</span><span class="sxs-lookup"><span data-stu-id="ef66a-112">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="ef66a-113">Vous pouvez trouver les valeurs requises dans le coffre de clés que vous avez créé dans [Créer des ressources Azure](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="ef66a-113">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="ef66a-114">**ID client** - Dans le portail Azure, accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Vue d’ensemble** et copiez la valeur **ID répertoire**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-114">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="ef66a-115">Collez cette valeur dans la boite de dialogue **Complément d’installation**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-115">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="ef66a-116">**URI du coffre de clés de point d’extrémité compatible avec IoT Event Hub** - Accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Vue d’ensemble**et copiez la valeur du **Nom DNS**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-116">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="ef66a-117">Collez cette valeur dans la boite de dialogue **Complément d’installation**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-117">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="ef66a-118">**Nom secret du point de terminaison compatible avec IoT Event Hub** - Accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Secrets** et copiez le nom du secret dans lequel la chaîne de connexion du concentrateur d’événements du hub IoT est stockée.</span><span class="sxs-lookup"><span data-stu-id="ef66a-118">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="ef66a-119">Collez cette valeur dans la boite de dialogue **Complément d’installation**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-119">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="ef66a-120">**URI du coffre de clés du cache Redis** - Accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Vue d’ensemble**et copiez la valeur du **Nom DNS**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-120">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="ef66a-121">Collez cette valeur dans la boite de dialogue **Complément d’installation**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-121">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="ef66a-122">**Nom secret du point de terminaison du cache Redis** - Accédez au coffre de clés, puis, dans le volet de navigation de gauche, sélectionnez **Secrets** et copiez le nom du secret dans lequel la chaîne de connexion du cache Redis est stockée.</span><span class="sxs-lookup"><span data-stu-id="ef66a-122">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="ef66a-123">Collez cette valeur dans la boite de dialogue **Complément d’installation**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-123">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="ef66a-124">Cochez la case pour accepter les termes et conditions.</span><span class="sxs-lookup"><span data-stu-id="ef66a-124">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="ef66a-125">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-125">Select **Install**.</span></span>
8. <span data-ttu-id="ef66a-126">Une boîte de message s’affiche et indique : « Le complément a été correctement déclenché pour l’installation .</span><span class="sxs-lookup"><span data-stu-id="ef66a-126">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="ef66a-127">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-127">Select **OK**.</span></span>

<span data-ttu-id="ef66a-128">La configuration LCS est maintenant terminée.</span><span class="sxs-lookup"><span data-stu-id="ef66a-128">LCS setup is now completed.</span></span> <span data-ttu-id="ef66a-129">La prochaine étape consiste à [mettre en place les scénarios](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="ef66a-129">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="ef66a-130">Désinstaller le complément</span><span class="sxs-lookup"><span data-stu-id="ef66a-130">Uninstall the add-in</span></span>

1. <span data-ttu-id="ef66a-131">Dans Supply Chain Management, [désactivez les scénarios](iot-scenario-setup.md#how-to-disable-a-scenario).</span><span class="sxs-lookup"><span data-stu-id="ef66a-131">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#how-to-disable-a-scenario).</span></span>
2. <span data-ttu-id="ef66a-132">Dans LCS, accédez aux détails de l’environnement Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ef66a-132">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="ef66a-133">Faites défiler jusqu’à la section **Compléments d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="ef66a-133">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="ef66a-134">Sélectionnez **Désinstaller** pour le complément Intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="ef66a-134">Select **Uninstall** for the IoT Intelligence add-in.</span></span>
