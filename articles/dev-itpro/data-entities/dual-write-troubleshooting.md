---
title: Guide de résolution des problèmes d'intégration de données
description: Cette rubrique fournit des informations sur le dépannage de l'intégration des données entre Microsoft Dynamics 365 for Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797273"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="f4667-103">Guide de résolution des problèmes d'intégration de données</span><span class="sxs-lookup"><span data-stu-id="f4667-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a><span data-ttu-id="f4667-104">Activez le traçage de plug-ins dans Common Data Service et vérifiez les détails de l'erreur de plug-in en double écriture</span><span class="sxs-lookup"><span data-stu-id="f4667-104">Enable Plugin Trace in Common Data Service and check the dual-write Plugin error details</span></span>

<span data-ttu-id="f4667-105">Si vous faites face à un problème ou à une erreur avec la synchronisation en double écriture, vous pouvez examiner les erreurs dans le journal de suivi :</span><span class="sxs-lookup"><span data-stu-id="f4667-105">If you are facing an issue or error with dual-write synchronization, you can inspect the errors in the trace log:</span></span>

1. <span data-ttu-id="f4667-106">Avant de pouvoir examiner les erreurs, vous devez activer le traçage de plug-ins à l'aide de les instructions du [Plug-in de Registre](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) pour activer le traçage de plug-ins.</span><span class="sxs-lookup"><span data-stu-id="f4667-106">Before you can inspect the errors, you must enable Plugin trace using the instructions in [Register plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) to enable Plugin trace.</span></span> <span data-ttu-id="f4667-107">Vous pouvez désormais examiner les erreurs.</span><span class="sxs-lookup"><span data-stu-id="f4667-107">Now you can inspect the errors.</span></span>
2. <span data-ttu-id="f4667-108">Connectez-vous à Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="f4667-108">Login to Dynamics 365 for Sales.</span></span>
3. <span data-ttu-id="f4667-109">Cliquez sur l'icône Paramètres (engrenage), et sélectionnez **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="f4667-109">Click on the Settings icon (a gear), and select **Advanced Settings**.</span></span>
4. <span data-ttu-id="f4667-110">Dans le menu **Paramètres**, choisissez **Personnalisation > journal de suivi des plug-ins**.</span><span class="sxs-lookup"><span data-stu-id="f4667-110">In the **Settings** menu, choose **Customization > Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="f4667-111">Cliquez sur le nom de type **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** pour afficher les détails de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="f4667-111">Click the type name **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** to display the error details.</span></span>

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a><span data-ttu-id="f4667-112">Vérifier les erreurs de synchronisation en double écriture dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f4667-112">Check dual-write synchronization errors in Finance and Operations</span></span>

<span data-ttu-id="f4667-113">Vous pouvez vérifier les erreurs au cours des tests en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="f4667-113">You can check the errors during testing by following these steps:</span></span>

+ <span data-ttu-id="f4667-114">Connectez-vous à LifeCycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f4667-114">Login to LifeCycle Services (LCS).</span></span>
+ <span data-ttu-id="f4667-115">Ouvrez le projet LCS que vous avez choisi pour effectuer le test de double écriture.</span><span class="sxs-lookup"><span data-stu-id="f4667-115">Open the LCS project that you chose to perform dual-write testing.</span></span>
+ <span data-ttu-id="f4667-116">Accédez aux Environnements hébergés dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="f4667-116">Go to Cloud Hosted Environments.</span></span>
+ <span data-ttu-id="f4667-117">Machine virtuelle de Bureau à distance vers Finance and Operations à l'aide du compte local qui s'affiche dans LCS.</span><span class="sxs-lookup"><span data-stu-id="f4667-117">Remote desktop to Finance and Operations VM using local account that is displayed in LCS.</span></span>
+ <span data-ttu-id="f4667-118">Ouvrez la visionneuse d'événements.</span><span class="sxs-lookup"><span data-stu-id="f4667-118">Open the event viewer.</span></span> 
+ <span data-ttu-id="f4667-119">Accédez à **Journaux des applications et des services > Microsoft > Dynamics > AX-DualWriteSync > Opérationnel**.</span><span class="sxs-lookup"><span data-stu-id="f4667-119">Navigate to **Applications and Services logs > Microsoft > Dynamics > AX-DualWriteSync > Operational**.</span></span> <span data-ttu-id="f4667-120">Les erreurs et les détails sont affichés.</span><span class="sxs-lookup"><span data-stu-id="f4667-120">The errors and details are displayed.</span></span>

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a><span data-ttu-id="f4667-121">Procédure pour supprimer un lien et lier un autre environnement Common Data Service avec Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f4667-121">How to unlink and link another Common Data Service environment from Finance and Operations</span></span>

<span data-ttu-id="f4667-122">Vous pouvez mettre à jour les liens en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="f4667-122">You can update links by following these steps:</span></span>

+ <span data-ttu-id="f4667-123">Accédez à l'environnement Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f4667-123">Navigate to the Finance and Operations environment.</span></span>
+ <span data-ttu-id="f4667-124">Ouvrez Gestion des données.</span><span class="sxs-lookup"><span data-stu-id="f4667-124">Open Data Management.</span></span>
+ <span data-ttu-id="f4667-125">Cliquez sur **Lien vers CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="f4667-125">Click on **Link to CDS for apps**.</span></span>
+ <span data-ttu-id="f4667-126">Sélectionnez toutes les mises en correspondance en cours d'exécution et cliquez sur **Arrêter**.</span><span class="sxs-lookup"><span data-stu-id="f4667-126">Select all the running mappings and click **Stop**.</span></span> 
+ <span data-ttu-id="f4667-127">Sélectionnez toutes les mises en correspondance et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="f4667-127">Select all the mappings and click **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4667-128">L'option **Supprimer** ne s'affiche pas si le modèle **CustomerV3-Account** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f4667-128">The **Delete** option will not appear if **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="f4667-129">Désactivez-le si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f4667-129">Unselect it if needed.</span></span> <span data-ttu-id="f4667-130">**CustomerV3-Account** est un modèle anciennement mis en service et fonctionne avec la solution Prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="f4667-130">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="f4667-131">Comme il est disponible mondialement, il s'affiche sous tous les modèles.</span><span class="sxs-lookup"><span data-stu-id="f4667-131">Because it is globally released, it shows up under all templates.</span></span>

+ <span data-ttu-id="f4667-132">Cliquez sur **Supprimer le lien avec l'environnement**.</span><span class="sxs-lookup"><span data-stu-id="f4667-132">Click **Unlink environment**.</span></span>
+ <span data-ttu-id="f4667-133">Cliquez sur **Oui** pour confirmer.</span><span class="sxs-lookup"><span data-stu-id="f4667-133">Click **Yes** for confirmation.</span></span>
+ <span data-ttu-id="f4667-134">Pour lier le nouvel environnement, suivez les étapes du [guide d'installation](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="f4667-134">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>

