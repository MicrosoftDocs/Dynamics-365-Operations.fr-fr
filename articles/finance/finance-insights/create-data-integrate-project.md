---
title: Créer un projet d’intégrateur de données (version préliminaire)
description: Cette rubrique explique comment créer un projet d’intégrateur de données.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 0029e093f524c61ff17a480ee3b881b3994ba95a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009442"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="d68d1-103">Créer un projet d’intégrateur de données (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="d68d1-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="d68d1-104">Cette rubrique explique comment créer un projet d’intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="d68d1-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="d68d1-105">Connectez-vous à Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="d68d1-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="d68d1-106">Accédez à **Espaces de travail \> Gestion des données** et sélectionnez **Entités de données**.</span><span class="sxs-lookup"><span data-stu-id="d68d1-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="d68d1-107">Attendez que toutes les entités de données aient été actualisées avant de passer à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="d68d1-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="d68d1-108">Ouvrez le [portail Power Apps](https://make.powerapps.com/) et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="d68d1-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="d68d1-109">Sélectionnez l’environnement approprié.</span><span class="sxs-lookup"><span data-stu-id="d68d1-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="d68d1-110">Sélectionnez **Données \> Connexions** dans le volet de navigation de gauche.</span><span class="sxs-lookup"><span data-stu-id="d68d1-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="d68d1-111">Connectez-vous aux instances appropriées des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d68d1-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="d68d1-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d68d1-112">Dynamics 365</span></span>
        - <span data-ttu-id="d68d1-113">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="d68d1-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="d68d1-114">Ouvrez les [environnements Power Apps](https://admin.powerapps.com/environments) et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="d68d1-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="d68d1-115">Sélectionnez **Intégrateur de données**.</span><span class="sxs-lookup"><span data-stu-id="d68d1-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="d68d1-116">Sélectionnez **Ensembles de connexions**.</span><span class="sxs-lookup"><span data-stu-id="d68d1-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="d68d1-117">Sélectionnez **Nouvel ensemble de connexions**.</span><span class="sxs-lookup"><span data-stu-id="d68d1-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="d68d1-118">Entrez un nom pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="d68d1-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="d68d1-119">Sélectionnez les connexions appropriées pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d68d1-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="d68d1-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d68d1-120">Dynamics 365</span></span>
        - <span data-ttu-id="d68d1-121">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="d68d1-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="d68d1-122">Sélectionnez le mappage d’organisation approprié.</span><span class="sxs-lookup"><span data-stu-id="d68d1-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="d68d1-123">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="d68d1-123">Select **Create**.</span></span>

5. <span data-ttu-id="d68d1-124">Ouvrez les [environnements Power Apps](https://admin.powerapps.com/environments) et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="d68d1-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="d68d1-125">Créez des projets d’intégration de données pour les modèles suivants à l’aide du jeu de connexions que vous venez de créer :</span><span class="sxs-lookup"><span data-stu-id="d68d1-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="d68d1-126">Résultats des analyses de paiement client (CDS à Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="d68d1-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="d68d1-127">Résultats des séries chronologiques de flux de trésorerie (CDS à Fin et Ops)</span><span class="sxs-lookup"><span data-stu-id="d68d1-127">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="d68d1-128">Résultats des séries chronologiques de budget (CDS à Fin et Ops)</span><span class="sxs-lookup"><span data-stu-id="d68d1-128">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="d68d1-129">Définissez la planification appropriée pour chaque projet.</span><span class="sxs-lookup"><span data-stu-id="d68d1-129">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="d68d1-130">Si vous ne voyez pas les entités requises dans CDS, allez à **Crédits et recouvrements > configuration > finance Insights> paramètres de Finance Insights**, activez la fonction de prédiction de paiement client et cliquez sur le bouton **Créer un modèle de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="d68d1-130">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="d68d1-131">Lorsque le déploiement du modèle d’IA est terminé (réussi ou échoué), les entités CDS nécessaires pour créer l’intégration seront déployées dans CDS.</span><span class="sxs-lookup"><span data-stu-id="d68d1-131">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="d68d1-132">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="d68d1-132">Privacy notice</span></span>

<span data-ttu-id="d68d1-133">Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.</span><span class="sxs-lookup"><span data-stu-id="d68d1-133">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
