---
title: Créer un projet d’intégrateur de données (version préliminaire)
description: Cette rubrique explique comment créer un projet d’intégrateur de données.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 59f85c64ea7b1f539a245e08b76bd6a34797b0ca
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186466"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="88ae2-103">Créer un projet d’intégrateur de données (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="88ae2-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="88ae2-104">Cette rubrique explique comment créer un projet d’intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="88ae2-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="88ae2-105">Connectez-vous à Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="88ae2-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="88ae2-106">Accédez à **Espaces de travail \> Gestion des données** et sélectionnez **Entités de données**.</span><span class="sxs-lookup"><span data-stu-id="88ae2-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="88ae2-107">Attendez que toutes les entités de données aient été actualisées avant de passer à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="88ae2-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="88ae2-108">Ouvrez le [portail Power Apps](https://make.powerapps.com/) et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="88ae2-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="88ae2-109">Sélectionnez l’environnement approprié.</span><span class="sxs-lookup"><span data-stu-id="88ae2-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="88ae2-110">Sélectionnez **Données \> Connexions** dans le volet de navigation de gauche.</span><span class="sxs-lookup"><span data-stu-id="88ae2-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="88ae2-111">Connectez-vous aux instances appropriées des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="88ae2-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="88ae2-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="88ae2-112">Dynamics 365</span></span>
        - <span data-ttu-id="88ae2-113">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="88ae2-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="88ae2-114">Ouvrez les [environnements Power Apps](https://admin.powerapps.com/environments) et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="88ae2-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="88ae2-115">Sélectionnez **Intégrateur de données**.</span><span class="sxs-lookup"><span data-stu-id="88ae2-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="88ae2-116">Sélectionnez **Ensembles de connexions**.</span><span class="sxs-lookup"><span data-stu-id="88ae2-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="88ae2-117">Sélectionnez **Nouvel ensemble de connexions**.</span><span class="sxs-lookup"><span data-stu-id="88ae2-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="88ae2-118">Entrez un nom pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="88ae2-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="88ae2-119">Sélectionnez les connexions appropriées pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="88ae2-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="88ae2-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="88ae2-120">Dynamics 365</span></span>
        - <span data-ttu-id="88ae2-121">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="88ae2-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="88ae2-122">Sélectionnez le mappage d’organisation approprié.</span><span class="sxs-lookup"><span data-stu-id="88ae2-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="88ae2-123">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="88ae2-123">Select **Create**.</span></span>

5. <span data-ttu-id="88ae2-124">Ouvrez les [environnements Power Apps](https://admin.powerapps.com/environments) et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="88ae2-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="88ae2-125">Créez des projets d’intégration de données pour les modèles suivants à l’aide du jeu de connexions que vous venez de créer :</span><span class="sxs-lookup"><span data-stu-id="88ae2-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="88ae2-126">Résultats des analyses de paiement client (CDS à Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="88ae2-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
            - <span data-ttu-id="88ae2-127">Si vous utilisez la version 10.0.17 ou une version ultérieure, vous devez utiliser le modèle nommé Résultats des analyses de paiement client (CDS à Fin and Ops 10.0.17 +).</span><span class="sxs-lookup"><span data-stu-id="88ae2-127">If you are using version 10.0.17 or later, you need to use the template named, Customer payment insights result (CDS to Fin and Ops 10.0.17+).</span></span>
        - <span data-ttu-id="88ae2-128">Résultats des séries chronologiques de flux de trésorerie (CDS à Fin et Ops)</span><span class="sxs-lookup"><span data-stu-id="88ae2-128">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="88ae2-129">Résultats des séries chronologiques de budget (CDS à Fin et Ops)</span><span class="sxs-lookup"><span data-stu-id="88ae2-129">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="88ae2-130">Définissez la planification appropriée pour chaque projet.</span><span class="sxs-lookup"><span data-stu-id="88ae2-130">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="88ae2-131">Si vous ne voyez pas les entités requises dans CDS, allez à **Crédits et recouvrements > configuration > Informations financières> paramètres de Informations financières**, activez la fonction de prédiction de paiement client et cliquez sur le bouton **Créer un modèle de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="88ae2-131">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="88ae2-132">Lorsque le déploiement du modèle d’IA est terminé (réussi ou échoué), les entités CDS nécessaires pour créer l’intégration seront déployées dans CDS.</span><span class="sxs-lookup"><span data-stu-id="88ae2-132">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
