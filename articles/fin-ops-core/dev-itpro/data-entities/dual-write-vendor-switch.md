---
title: Permuter entre les configurations de fournisseur
description: Cette rubrique décrit comment basculer entre l'intégration des données fournisseur entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
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
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 204d788e72e79e7acf744d24cbeacb0f9b47da7d
ms.sourcegitcommit: 3306e451f04df01c51d8d332306b135d8ae1e254
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2019
ms.locfileid: "2902723"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="dd51f-103">Permuter entre les configurations de fournisseur</span><span class="sxs-lookup"><span data-stu-id="dd51f-103">Switch between vendor designs</span></span>

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="dd51f-104">Flux de données fournisseur</span><span class="sxs-lookup"><span data-stu-id="dd51f-104">Vendor data flow</span></span> 

<span data-ttu-id="dd51f-105">Si vous souhaitez utiliser d'autres applications Dynamics 365 pour la gestion des fournisseurs, et si vous souhaitez isoler les informations fournisseur des informations client, vous pouvez utiliser la conception de fournisseur de base.</span><span class="sxs-lookup"><span data-stu-id="dd51f-105">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Flux de fournisseur de base](media/dual-write-vendor-data-flow.png)
 
<span data-ttu-id="dd51f-107">Si vous souhaitez utiliser d'autres applications Dynamics 365 pour la gestion des fournisseurs, et que vous souhaitez continuer d'utiliser l'entité **Compte** pour stocker les informations fournisseur, vous pouvez utiliser la nouvelle conception de fournisseur étendue.</span><span class="sxs-lookup"><span data-stu-id="dd51f-107">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="dd51f-108">Dans cette conception, les informations fournisseur étendues telles que le statut En attente du fournisseur et le profil du fournisseur sont stockées dans l'entité **fournisseurs** dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="dd51f-108">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Flux de fournisseur étendu](media/dual-write-vendor-detail.jpg)
 
<span data-ttu-id="dd51f-110">Procédez comme suit pour utiliser la conception étendue de fournisseur :</span><span class="sxs-lookup"><span data-stu-id="dd51f-110">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="dd51f-111">Le pack de solution **SupplyChainCommon** contient les modèles de processus de workflow comme le montre l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="dd51f-111">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dd51f-112">![Modèles de processus de workflow](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="dd51f-112">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="dd51f-113">Permet de créer de nouveaux processus de workflow à l'aide des modèles de processus de workflow :</span><span class="sxs-lookup"><span data-stu-id="dd51f-113">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="dd51f-114">Créez un nouveau processus de workflow pour l'entité **Fournisseur** à l'aide du modèle de processus de workflow **Créer des fournisseurs dans l'entité de compte** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd51f-114">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="dd51f-115">Ce workflow traite le scénario de création du fournisseur pour l'entité **Compte**.</span><span class="sxs-lookup"><span data-stu-id="dd51f-115">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="dd51f-116">![Créer des fournisseurs dans l'entité Compte](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="dd51f-116">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="dd51f-117">Créez un nouveau processus de workflow pour l'entité **Fournisseur** à l'aide du modèle de processus de workflow **Mettre à jour l'entité Comptes** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd51f-117">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="dd51f-118">Ce workflow traite le scénario de mise à jour du fournisseur pour l'entité **Compte**.</span><span class="sxs-lookup"><span data-stu-id="dd51f-118">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="dd51f-119">![Mettre à jour l'entité Comptes](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="dd51f-119">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="dd51f-120">Créez de nouveaux processus de workflow depuis les modèles créés sur l'entité **Comptes**.</span><span class="sxs-lookup"><span data-stu-id="dd51f-120">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="dd51f-121">![Créer des fournisseurs dans l'entité Fournisseurs](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="dd51f-121">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="dd51f-122">![Mettre à jour l'entité Fournisseurs](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="dd51f-122">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="dd51f-123">Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d'arrière plan selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="dd51f-123">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="dd51f-124">![Convertir vers un workflow d'arrière-plan](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="dd51f-124">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="dd51f-125">Activez les workflows que vous avez créés sur les entités **Compte** et **Fournisseur** pour commencer à utiliser l'entité **Compte** pour enregistrer les informations fournisseur.</span><span class="sxs-lookup"><span data-stu-id="dd51f-125">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the **Account** entity for storing vendor information.</span></span> 
 
